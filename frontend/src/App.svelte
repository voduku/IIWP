<script>
	import './app.css';

	// Example: allow dynamic theming based on country
	let country = 'usa';

	const backgrounds = {
		usa: 'linear-gradient(135deg, rgba(0,60,130,0.20), rgba(180,20,20,0.15))',
		vietnam: 'linear-gradient(135deg, rgba(255,0,0,0.20), rgba(255,180,0,0.15))',
		japan: 'linear-gradient(135deg, rgba(255,255,255,0.5), rgba(200,0,0,0.15))'
	};

	// Example accent colors by country
	const accentMap = {
		usa: '0 70 150',
		vietnam: '220 0 0',
		japan: '180 0 0'
	};

	// Update global CSS variables when country changes
	$: document.documentElement.style.setProperty('--accent', accentMap[country]);
	$: document.documentElement.style.setProperty('--accent-light', accentMap[country] + ' / 0.18');
</script>

<!-- Full-screen background -->
<div class="min-h-screen p-8" style="background: {backgrounds[country]};">
	<!-- Example center container -->
	<div class="max-w-3xl mx-auto space-y-6">
		<!-- Example glass container -->
		<div class="glass p-8 text-white">
			<h1 class="text-4xl font-bold mb-4">If I Was President</h1>
			<p class="opacity-90 mb-6">A place to imagine policies that could improve your country.</p>

			<button class="accent-btn"> Example Glass Button </button>
		</div>

		<!-- Example card with white background for readability -->
		<div class="card-white">
			<h2 class="text-xl font-semibold mb-2">Readable Card</h2>
			<p>This is a white card component perfect for long policy text.</p>
		</div>
	</div>
</div>

<style>
	/* Per-component styles (optional) */
</style>
