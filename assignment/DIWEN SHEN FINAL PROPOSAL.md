# CPLN 692 FINAL PROJECT PROPOSAL
# DIWEN SHEN


## Problem / Question

Cities often do a good job visualizing rail routes in their transit systems. However, cities often do a poor job providing clear information on how their bus routes function, even though in most cities buses make up the majority of transit ridership. 

- I will seek to build an interactive tool to easily visualize how the SEPTA bus system works in Philadelphia, focusing on providing information on the frequency of each route -- the key piece of missing information in almost all transit information maps. 

- Using frequency and travel time information scrapped from the web, I will also seek to map out isochrones. Isochrones are defined as the area you can get to by public transit within a certain amount of time (eg. 30min, 45min etc.), including transfers. The advantage of high frequency routes is that transferring between routes is very easy, and thus the usefulness of each route is greatly expanded.


## The data

- SEPTA bus route and bus stop data (GeoJSON)
- SEPTA schedules (Webpage for each line)


## Technologies and Functionality

- Automatically download and parse data from SEPTA's website to calculate the midday frequency for each bus route. (Implementation: on the webpage of each bus line, use JavaScript/HTML to identify the first departure after 12pm; then identify the second departure right after the first one, and subtract the two departures to calculate the frequency)

- Map out bus and transit lines using different filters and styles based on frequency.

- Using frequency information, given a user inputed location, map out the area this person can get to in 30 min by using transit. (Implementation: calculate the distance from the user inputed location to the nearest transit stop; based on network distance, and assumed travel speed by transit and walking, calculate and map out where the user can get to by transit, including expected waiting time (1/2 * frequency). Stretch goal: incorporate transfer time)

Libraries: leaflet, turf, jQuery, underscore, Carto


## Design spec

#### User experience

At a high level, how do you expect people to use your application?
- Users are any person wishing to explorer his/her transit options from any spontaneous location in Philadelphia

What do they gain from your application' use?
- Users would be able to quickly understand which bus and transit routes are frequent and available to use whenever the user to prepared to travel. The user would also be able see the approximate range he/she can travel to using transit in 30 min or 45 min.

Are there any website/application examples in the wild to which you can compare your final?
- http://humantransit.org/2016/08/26634.html


#### Layouts and visual design

Standard toolbar (on the left) and map (on the right) would suffice.

- The toolbar needs to contain filters, and when requested, display information on bus and transit lines and distance able to travel.

- The map needs to map out bus and transit lines styled according to frequency, and show area the user can travel to within 30 min or 45 min.


## Anticipated difficulties

- Large dataset and slow processing time
- Scrapping data from SEPTA's website
- Calculating network distance and travel times given multiple modes and transfers (maybe stretch goal)


## Missing pieces

- Efficiency implementation of functionality similar to ArcGIS's network analyst, and dealign with large datasets.
