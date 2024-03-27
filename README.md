
# Team 3 MIST 4610 Group Project 1

## Team Name:
20244 Group 3


## Team Members:
1. Nicolle Serafin [@nikkiserafin](url)
2. Shubhangi Khanna [@shubbykhanna]
3. Jay Dumon [@JayDumon]
4. Ryan Cullen [@javaprogrammer2023]
5. Elyssa Abbott [@elyssaabbott]

## Problem Description:
We are the owner/operator of a tennis club needing to build a relational database. The central entity is the Members entity - Members being each person who has a membership at the tennis club. Members have the ability to reserve facility spaces (courts and club rooms), purchase tennis necessities (attire, racket, shoes,etc.), and develop their tennis skillset through lessons with tennis coaches or playing matches in a league. Through modeling these relationships in depth, we aim to precisely model these relationships, create sample data, add attributes to our entities, and perform valuable queries to effectively model our tennis club's operations.

## Data model:
Explanation of data model:

Our model is based on a hypothetical tennis club. Members is the central entity including a member identification number, their first and last name, contact information, other personal information (age and gender), membership level, their team, and their coach if they have one.

There are also many membership options members can opt into. Each level provides members different perks correlated to the club. Each level has a price. This is why we created a One-To-Many Relationship for membership levels and members. Each membership level can have multiple members, but only a member can be part of one membership level.

Coaches have their own entity. The Coaches entity includes their coach identification number, first and last name, qualifications, availability, and their own membership level. There is a One-To-Many Relationship between MembershipLevels and Coaches because one specific membership is for all the coaches. Members do not have to have a coach, but they can only have one coach at a time. Coaches have to coach at least one member, but can coach more than one member. That is why there is a One-To-Many Relationship between Coaches and Members.

All members are able to make purchases at the tennis club as a part of their membership. They can make purchases directly from their memberID. There is a One-To-Many Relationship between Members and Purchases because one member may make many purchases, but the purchase can only belong to one member. The Purchases entity includes the purchaseID, date and time of the purchase, amount of the purchase, memberID, and itemID the member purchased. This corresponds directly to the Items entity. The Items entity includes the itemID, itemName, quantityInStock, sellingPrice, manufacturingCost, and vendor. There is a One-To-Many Relationship between Items and Purchases because one item may be purchased multiple times. To clarify, there may be multiple identical items in stock for purchase.

EventReservations is an entity at the tennis club for members to reserve for personal use. There is a One-To-Many Relationship between Members and EventReservations because a member can make many reservations, but does not have to. This entity includes the reservationID, name of the event, location of the event, date and time of the reservation, and the memberID.

Members can opt in to play for the club's tennis team. To clarify, Members have the option to join a home team, but do not have to. Our tennis team will play matches against different teams in the area in the same league. The home team has a specific teamID, teamName, as well as the number of players on their team. HomeTeams and Members have a One-To-Many Relationship; multiple members can be on the same team. The home team has the ability to play multiple Matches, giving HomeTeams and Matches a One-To-Many Relationship. The Matches entity includes matchID, homeScore, awayScore, date and time of the match, teamID, the court location of the match, and the leagueID. Basing our scoring method off of Junior Play, the matches will only be played first to win 8 games. Lastly, the HomeTeams can play multiple Matches in the same league. To clarify, Leagues and Matches have a One-To-Many Relationship. Members can play multiple Matches but only in one league. The Leagues entity has two attributes - leagieID and leagueName.

As a perk, Members are able to reserve courts as a part of all MembershipLevels (Silver, Gold, Platinum, Coach). The CourtReservations entity includes the reservationID, the date and time of the court reservation, the memberID, and courtID. There is a One-To-Many Relationship between Members and CourtReservations. One member can have multiple CourtReservations, but not at the same time. There is a One-To-Many Relationship between Courts and CourtReservations. One reservation can only reserve one court. The Courts entity includes the courtNumber, the surfaceType of the court, and whether the court is inside or outside. There is a One-To-Many Relationship between Courts and Matches because many Matches can be played on the same court if the timing is different. In other words, multiple Matches can be played on multiple Courts, but multiple Matches can be played on the same court at different times.

The next entity is CourtMaintenance which includes maintenanceID, the date and time of the scheduled maintenance, the maintenance worker's ID number, and the court that they maintained. There is a One-To-Many Relationship between Courts and CourtMaintenance. One court can be maintained by multiple workers.

The last entity is MaintenanceCrew which describes the specific employee maintaining the court. This includes employeeID, the employee's first and last name, and contact information. There is a One-To-Many Relationship between MaintenanceCrew and CourtMaintenance because one crew member can have multiple maintenance jobs.

## Data Dictionary:



## Queries:
