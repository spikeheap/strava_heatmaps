# Strava heatmap visualiser

This project was part of [RemoteHack
#4](https://remotehack.space/hacks/04.html), and was created by
[@nimphal](https://github.com/nimphal) and [@spikeheap](https://github.com/spikeheap).


The premise of this hack was to take your Strava activities, and generate
something like the heatmap (e.g.
https://www.strava.com/athletes/39726/heatmaps/285a7b19#7/51.13111/-1.13159),
showing changes over time.

You can generate your Strava Heatmap at: https://www.strava.com/athlete/heatmaps

## Caveats ⚠️

1. This is NOT PRODUCTION WORTHY.
2. You'll need to pull the activities from Strava manually. For the purposes of
   the hack day, we used our [Strava API
   keys](https://www.strava.com/settings/api) and
   [Postman](https://www.postman.com) to extract our activities into a single
   JSON file. This repository does not contain code to update/pull activities
   from Strava (yet).

## Dependencies
- https://momentjs.com/docs/
- https://leafletjs.com
- https://github.com/jieter/Leaflet.encoded

## Notes

- Leaflet path options: https://leafletjs.com/reference-1.6.0.html#path

- JQ join arrays in separate files: `jq -s add file1 file2`

#### Strava API

API Docs
- Get my activities (summary): https://developers.strava.com/docs/reference/#api-Activities-getLoggedInAthleteActivities
  - returns Summary object (without route)

- https://developers.strava.com/docs/reference/#api-Activities-getActivityById
  - returns DetailedActivity, which contains the activity polyline: https://developers.strava.com/docs/reference/#api-Activities-getActivityById

Strava uses the [Google Encoded Polyline Algorithm Format](https://developers.google.com/maps/documentation/utilities/polylinealgorithm).

# License
This project is released under the MIT license.
