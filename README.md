# Uber_Air__NYC
Business Case Study of Air Taxi and Sky Ports for New York City

![Uber Air Image](/img/190216_190529_entry_jpg.jpg)

## Background

In 2019, Uber announced that Uber Air flying taxis will take off in Dallas, Los Angeles and Melbourne in 2023. Uber Air is a shared air transporation service between suburbs and cities to start, and ultimately within cities. The company believes Urban Air Mobility(UAM) presents an opportunity to decongest road traffic, improve mobility, give back time to those trapped in daily traffic, and unlock the potential of cities worldwide.

Uber Air's ecosystem consists of 4 fundamental systems, OEM partnerships for electric VTOLs(vertical take-off and landing vehicles), infrastructure partnerships for skyports, airspace management system and multimodal journey, that the Uber Elevate team and its partners are developing.

VTOLs are similar to helicopters and will carry four passengers at low altitude from skyports in each metro area and will seamlessly string a ground transportation segment to a skyport, with a pooled point-to-point flight, and a just-in-time ground transportation leg to a rider’s final destination. The short flights will start at $5 per mile, so a 20-mile trip would add up to about $100 though Uber Elevate officials anticipate that the cost will go down eventually. 

Above mentioned cities have already put together elaborate plans and designs for their services and skyports, but what about New York?


### Market consideration for Uber Air

A typical Uber Air market will usually have the following characteristics.

#### Size (land area)

A large human settlement spread over a large area, e.g Dallas/Fort Worth (DFW) Metroplex encompasses 4,848 square miles, and Los Angeles (LA) metro land area is spread over 8,928 square miles. 

New York City has an estimated 2019 population of 8,336,817 distributed over about 302.6 square miles (784 km2), which is not spread wide enough. However, the New York metropolitan area is the largest metropolitan area in the world by urban landmass, at 3,450.2 sq mi (8,936 km2).

#### Population and population density

The population is greater than 1 million and the population density is greater than 1,000 people per square mile. 

The New York metropolitan area is the most populous in the United States, as defined by both the Metropolitan Statistical Area (20.3 million residents in 2017) and the Combined Statistical Area (23.7 million residents in 2016).

#### Existing transportation network

An expansive ground transportation network that includes public transportation systems. A strong existing transportation network is essential, as riders will be provided the option of an existing form of ground transportation to and from skyports as part of the Uber Air journey. 

New York City's transportation system includes subway, bus, ferry, Taxi as well as FHV(For-hire Vehicles). 

#### At least one large airport

Airports typically aggregate transportation demand. Airports that are separated from the city center by a trip of an hour or more due to distance, traffic, or other bottlenecks, provide a compelling use case for a foundational route. 

New York has three robust airports in JFK, Newark and LaGuardia.

#### Traffic congestion

Increasing traffic congestion that results in high travel times and congestion costs. For example, in 2019, each vehicle commuter, in DFW Metroplex, spent 45 hours in traffic at an annual congestion cost of $1,160. Similarly, annual congestion cost in LA area is $2,440. The ideal city is polycentric, with multiple dense nodes of development separated by frequent congestion. 

According to INRIX 2019 Traffic Scorecard Report, New York City is 4th most congested city in the US and 14th in the world with 140 hours spent in congestions.

#### Stable environmental conditions

Adverse weather conditions can influence many components of Uber Air, including operational reliability, service supply, and rider comfort.


## Data

![NYC Taxi Zone](/img/nyc_boroughs.png)

Yellow Taxi Trip Records from NYC Taxi & Lomousine Commision contains fields capturing:

- Vendor ID
- pick-up and drop-off dates/times
- pick-up and drop-off locations
- trip_distance
- passenger count
- itemized fares
- rate types
- payment types

Yellow Taxi Trip Records dataset has the most variety of fields as well as the size large enough to investigate the usage of cars as public transportation in NYC. Though the size of dataset for High Volume For-Hire Vehicles(Uber, Lyft, Via & etc) has surpassed Yellow Taxi in recent years, FHVHV datasets unfortunately lack some important fields such as fare amount to gain more interesting insight.

Here, we are looking at Yellow Taxi data from 2019 to evaluate 'normal' level of activties considering the unusual disruption in social activities in 2020 due to pandemic.

2019 Yellow Taxi Trip Data:
https://data.cityofnewyork.us/Transportation/2019-Yellow-Taxi-Trip-Data/2upf-qytp

NYC Taxi Zones
https://data.cityofnewyork.us/Transportation/NYC-Taxi-Zones/d3c5-ddgc


## Questions

For the initial launch of Uber Air's service in NYC:

1. Where should it run?

2. When should it run?

3. How can we validate the values proposed?

# Location of Service: Where should Uber Air run?

Initially, looked up the count of pick up/drop off records by boroughs:

![Boroughs_Activities](/img/borough_pudo.png)

Manhattan takes up more 90% of the pick up/drop off locations.

To get a closer look at areas with highest demand, I looked at top 5 pick up/drop off zones by their count.

- Top 5 pickup zones : 
    * Upper East Side South 
    * Midtown Center 
    * Upper East Side North 
    * Midtown East 
    * Penn Station/Madison Square West 

- Top 5 drop-off zones : 
    * Upper East Side North 
    * Midtown Center 
    * Upper East Side South 
    * Murray Hill and Times Square/Theatre District 
    
![zones_Activities](/img/pu_do_nyc.png)

From the figures above, we can see that despite the top 5 pickup/dropoff zones, many other zones in Manhattan are also popular.

The zone in the lower-right corner that shows quite high number of demans is Queens, where JFK Airport is located. JFK is ranked at 7th pick-up location and 38th drop-off location among top 50 zones. La Guardia Air port ranks at the 14th in pick-up locations and 35th in drop-off locations. Rest of top 50 zones were in Manhattan.

### Trip Distance: How far are the trips?
![trip_distance_distribution](/img/distance.png)

JFK is on average 14.1 miles away from Manhattan and LaGuardia is 15.1 miles away. More than 96% of trips are short distance trips with trip distance less than 15 miles.

### Pick UP/Drop off for Short Distance Trips
![short_PUDO](/img/short_d_PUDO.png)

### Pick Up/Drop off for Long Distance Trips
![long_PUDO](/img/long_d_PUDO.png)

## Answer: Upper East Side Manhattan to JFK Airport

Because Uber Air requires Skyport for Landing Zone, I wouldn't make sense for it to launch the service with the need to build multiple skyports within Manhattan. Instead, providing a service from JFK airport to an area with highest demand for transportation in the city would be a sound choice.

# Time of Service: When should Uber Air run?
![time_operation](/img/short_long.png)

I recommend operating between 12PM to 10PM with expanded capacity for 2PM to 8PM.


# Passengers
![passengers](/img/passengers.png)

Most of the Yellow Taxi trips regardless of its distance transport a single passenger. Uber Air is a shared ride system for 4 passenger VTOLs, which means 1 VTOL can replace 4 Yellow Taxi trips to JFK. This will be useful in serving Uber's goal to resolve traffic congestion.

# Rates
![rates](/img/rate.png)

1. Standard rate
2. JFK
3. Newark
4. Nassau or Westchester
5. Negotiated fare
6. Group ride

Here is a problem. There is a flat rate offer for JFK at $52 to $58 depending on traffic surcharge. You can see in long distance trips that the flat rates for Airports become more common. 

This is an issue we have to investigate because Uber Air won’t be able to undercut the price.



