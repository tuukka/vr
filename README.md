# vr.js

This is a node.js module for fetching info from VR's Junat kartalla-service.

You can fetch info from different stations and trains.

Many thanks to Apps4Finland for documenting the API: http://apps4finland.fi/fi/data/junat-kartalla-palvelun-rajapinta/
They want to notify that the service is still in the development, can change or might go down.
Also apparently this shouldn't be used, unless you are making an entry to Apps4Finland contest.

## Install

<pre>
  npm install vr
</pre>

## How to use

There's three methods in this module.

### getStationInfo

Gives you station's departing and arriving trains. You need to use code names for station names. For example, Lahti is LH.

<pre>
  var vr = require('vr');
  
  vr.getStationInfo('LH', function (info) {
    console.log(info);
  });
</pre>

### getTrains

Gives you all trains that are on the tracks at the moment.

<pre>
  var vr = require('vr');
  
  vr.getTrains(function (trains) {
    console.log(trains);
  });
</pre>

### getTrain

Gives information about the stations that the train with given guid goes by. Also gives latitude/longitude, speed and direction of train.
(Use guid from getStationInfo/getTrains in this.)

<pre>
  var vr = require('vr');
  
  vr.getTrain('S79', function (train) {
    console.log(train);
  });
</pre>