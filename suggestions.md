Here are the 3 improvements I suggested earlier at the start of the review — the ones that give the biggest impact for the least work.

⸻

1️⃣ Show the Route on the Map (Most Important UX Fix)

Right now when a user clicks “Get Directions”, nothing changes visually on the map.

Add a route line so users can see where they are going.

Example JS

function drawRoute(){

const svg = document.querySelector(".map-roads")

const path = document.createElementNS(
"http://www.w3.org/2000/svg",
"path"
)

path.setAttribute(
"d",
"M280 190 Q260 170 220 150"
)

path.setAttribute("stroke","#3d9bff")
path.setAttribute("stroke-width","3")
path.setAttribute("fill","none")
path.setAttribute("stroke-dasharray","6 4")

svg.appendChild(path)

}

Call it when the user presses:

Get Directions →

Result:
	•	map feels interactive
	•	demo looks much more realistic

⸻

2️⃣ Sync Shelter Cards With Map

Right now the map and the shelter list are separate.

Make them linked.

Example behaviour:

Click shelter card →
• highlight marker
• show popup
• center attention

Example

function focusShelter(id){

const marker =
document.querySelector(`[data-id="${id}"]`)

marker.style.transform = "scale(1.3)"

showPopup(id, marker)

}

This improves navigation clarity.

⸻

3️⃣ Show Why the AI Chose the Shelter

When the route result appears, show the AI decision reasoning.

Add a small box like:

AI Recommendation

✓ Closest available shelter
✓ Medical facilities available
✓ Low crowd density
✓ Safe road access

Example HTML:

<div class="ai-explain">

<strong>AI Recommendation</strong>

<ul>
<li>Closest available shelter</li>
<li>Medical facilities available</li>
<li>Low crowd density</li>
<li>Safe road access</li>

</ul>

</div>

Why this matters:

Users trust systems more when they understand why decisions were made.

⸻

Why These 3 Matter

Improvement	Impact
Route line	makes map feel real
Map/list sync	improves usability
AI reasoning	increases trust

Together they turn your demo from static UI → believable product.

⸻

If you want, I can also show the single highest-impact improvement for your demo (takes 8 lines) that will make judges instantly say “oh wow.”