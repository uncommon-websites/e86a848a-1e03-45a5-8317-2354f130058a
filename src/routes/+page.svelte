<script lang="ts">
	// Icons
	const icons = {
		logo: `<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 text-blue-500"><path d="M12 2L14.5 9H22L16 13.5L18.5 21L12 16.5L5.5 21L8 13.5L2 9H9.5L12 2Z" fill="currentColor" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/></svg>`, // Placeholder for flower
		clock: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>`,
		arrowRight: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="5" y1="12" x2="19" y2="12"/><polyline points="12 5 19 12 12 19"/></svg>`,
		reflection: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>`,
		productivity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>`,
		memory: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M9.5 2A2.5 2.5 0 0 1 12 4.5v15a2.5 2.5 0 0 1-4.96.44 2.5 2.5 0 0 1-2.96-3.08 3 3 0 0 1-.34-5.58 2.5 2.5 0 0 1 1.32-4.24 2.5 2.5 0 0 1 1.98-3A2.5 2.5 0 0 1 9.5 2Z"/><path d="M14.5 2A2.5 2.5 0 0 0 12 4.5v15a2.5 2.5 0 0 0 4.96.44 2.5 2.5 0 0 0 2.96-3.08 3 3 0 0 0 .34-5.58 2.5 2.5 0 0 0-1.32-4.24 2.5 2.5 0 0 0-1.98-3A2.5 2.5 0 0 0 14.5 2Z"/></svg>`,
		clarity: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 2v4"/><path d="M12 18v4"/><path d="M4.93 4.93l2.83 2.83"/><path d="M16.24 16.24l2.83 2.83"/><path d="M2 12h4"/><path d="M18 12h4"/><path d="M4.93 19.07l2.83-2.83"/><path d="M16.24 7.76l2.83-2.83"/></svg>`,
		speedometer: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M22 12A10 10 0 0 0 12 2v10z"/></svg>`, // Simplified
		shield: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>`,
		sparkles: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/></svg>`,
		soundwave: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><path d="M12 2v20"/><path d="M16 6v12"/><path d="M20 10v4"/><path d="M8 6v12"/><path d="M4 10v4"/></svg>`,
		plus: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>`,
		check: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="20 6 9 17 4 12"/></svg>`,
		calendar: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>`,
		repeat: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><polyline points="17 1 21 5 17 9"/><path d="M3 11V9a4 4 0 0 1 4-4h14"/><polyline points="7 23 3 19 7 15"/><path d="M21 13v2a4 4 0 0 1-4 4H3"/></svg>`,
		search: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>`,
		camera: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M23 19a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h4l2-3h6l2 3h4a2 2 0 0 1 2 2z"/><circle cx="12" cy="13" r="4"/></svg>`,
		mic: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M12 1a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" y1="19" x2="12" y2="23"/><line x1="8" y1="23" x2="16" y2="23"/></svg>`,
		download: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>`,
		layout: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><rect x="3" y="3" width="18" height="18" rx="2" ry="2"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="9" y1="21" x2="9" y2="9"/></svg>`,
		target: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="6"/><circle cx="12" cy="12" r="2"/></svg>`,
		list: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><line x1="8" y1="6" x2="21" y2="6"/><line x1="8" y1="12" x2="21" y2="12"/><line x1="8" y1="18" x2="21" y2="18"/><line x1="3" y1="6" x2="3.01" y2="6"/><line x1="3" y1="12" x2="3.01" y2="12"/><line x1="3" y1="18" x2="3.01" y2="18"/></svg>`,
		link: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/></svg>`,
		maximize: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M8 3H5a2 2 0 0 0-2 2v3m18 0V5a2 2 0 0 0-2-2h-3m0 18h3a2 2 0 0 0 2-2v-3M3 16v3a2 2 0 0 0 2 2h3"/></svg>`,
		externalLink: `<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-4 h-4"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>`,
	};
</script>

<div class="min-h-screen bg-white">
	<!-- Header -->
	<header class="flex items-center justify-between px-6 py-4 max-w-7xl mx-auto">
		<div class="flex items-center gap-2">
			<!-- Logo Icon -->
			<div class="text-primary-600">
				<svg viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6">
					<path d="M12 2C13.1 2 14 2.9 14 4C14 5.1 13.1 6 12 6C10.9 6 10 5.1 10 4C10 2.9 10.9 2 12 2ZM12 22C10.9 22 10 21.1 10 20C10 18.9 10.9 18 12 18C13.1 18 14 18.9 14 20C14 21.1 13.1 22 12 22ZM6 12C6 10.9 5.1 10 4 10C2.9 10 2 10.9 2 12C2 13.1 2.9 14 4 14C5.1 14 6 13.1 6 12ZM22 12C22 13.1 21.1 14 20 14C18.9 14 18 13.1 18 12C18 10.9 18.9 10 20 10C21.1 10 22 10.9 22 12ZM17.66 7.34C18.44 6.56 19.7 6.56 20.48 7.34C21.26 8.12 21.26 9.38 20.48 10.16C19.7 10.94 18.44 10.94 17.66 10.16C16.88 9.38 16.88 8.12 17.66 7.34ZM6.34 16.66C5.56 17.44 4.3 17.44 3.52 16.66C2.74 15.88 2.74 14.62 3.52 13.84C4.3 13.06 5.56 13.06 6.34 13.84C7.12 14.62 7.12 15.88 6.34 16.66ZM16.66 17.66C15.88 18.44 15.88 19.7 16.66 20.48C17.44 21.26 18.7 21.26 19.48 20.48C20.26 19.7 20.26 18.44 19.48 17.66C18.7 16.88 18.7 15.62 17.92 14.84L16.66 17.66ZM7.34 6.34C8.12 5.56 8.12 4.3 7.34 3.52C6.56 2.74 5.3 2.74 4.52 3.52C3.74 4.3 3.74 5.56 4.52 6.34C5.3 7.12 6.56 7.12 7.34 6.34Z" />
					<circle cx="12" cy="12" r="3" class="text-primary-500" />
				</svg>
			</div>
			<span class="font-bold text-xl tracking-tight">Roochi</span>
		</div>
		<nav class="flex items-center gap-6 text-sm font-medium">
			<a href="#" class="text-gray-600 hover:text-gray-900">Docs</a>
			<a href="#" class="bg-gray-100 px-4 py-2 rounded-lg text-gray-900 hover:bg-gray-200 transition-colors">Sign In</a>
		</nav>
	</header>

	<main>
		<!-- Hero Section -->
		<section class="max-w-4xl mx-auto px-6 pt-12 pb-20 text-center">
			<div class="inline-flex items-center gap-2 text-gray-500 text-sm mb-6">
				{@html icons.camera}
				<span>AI-Powered Documentation</span>
			</div>
			
			<h1 class="text-5xl md:text-6xl font-bold tracking-tight text-gray-900 mb-6 leading-[1.1]">
				Turn tribal knowledge into searchable docs
			</h1>
			
			<p class="text-xl text-gray-600 mb-10 max-w-2xl mx-auto">
				Automated screen capture and AI processing that transforms your team's expertise into instant documentation.
			</p>

			<div class="flex flex-col sm:flex-row items-center justify-center gap-4 max-w-lg mx-auto mb-16">
				<div class="relative w-full">
					<input 
						type="email" 
						placeholder="Your work email" 
						class="w-full pl-4 pr-12 py-3 rounded-xl border border-gray-200 focus:outline-none focus:ring-2 focus:ring-primary-500/20 focus:border-primary-500 transition-all"
					/>
					<button class="absolute right-2 top-1/2 -translate-y-1/2 p-1.5 text-gray-400 hover:text-gray-600">
						{@html icons.arrowRight}
					</button>
				</div>
				<div class="text-xs text-left text-gray-500 w-full sm:w-auto shrink-0">
					Start your free trial,<br>no credit card required.
				</div>
			</div>

			<!-- App Screenshot Placeholder -->
			<div class="relative rounded-2xl border border-gray-200 shadow-2xl bg-white overflow-hidden aspect-[16/10] mb-12 group">
				<!-- This represents the complex app interface -->
				<div class="absolute inset-0 bg-gray-50 flex">
					<!-- Sidebar -->
					<div class="w-64 border-r border-gray-200 bg-white p-4 hidden md:flex flex-col gap-4">
						<div class="h-8 w-full bg-gray-100 rounded animate-pulse"></div>
						<div class="space-y-2">
							<div class="h-4 w-3/4 bg-gray-100 rounded"></div>
							<div class="h-4 w-1/2 bg-gray-100 rounded"></div>
							<div class="h-4 w-5/6 bg-gray-100 rounded"></div>
						</div>
					</div>
					<!-- Main Content -->
					<div class="flex-1 p-6">
						<div class="h-8 w-1/3 bg-gray-100 rounded mb-6"></div>
						<div class="space-y-4">
							<div class="h-32 w-full bg-white border border-gray-200 rounded-xl p-4 shadow-sm">
								<div class="flex gap-3 mb-3">
									<div class="w-8 h-8 rounded-full bg-gray-200"></div>
									<div class="space-y-1">
										<div class="h-3 w-24 bg-gray-200 rounded"></div>
										<div class="h-3 w-16 bg-gray-100 rounded"></div>
									</div>
								</div>
								<div class="h-2 w-full bg-gray-100 rounded mb-2"></div>
								<div class="h-2 w-5/6 bg-gray-100 rounded"></div>
							</div>
							<div class="h-32 w-full bg-white border border-gray-200 rounded-xl p-4 shadow-sm"></div>
						</div>
					</div>
				</div>
				
				<!-- Overlay text to indicate it's a screenshot -->
				<div class="absolute inset-0 flex items-center justify-center bg-black/5 opacity-0 group-hover:opacity-100 transition-opacity pointer-events-none">
					<span class="bg-white px-4 py-2 rounded-full shadow-sm text-sm font-medium">App Interface</span>
				</div>
			</div>

			<!-- Bottom Icons -->
			<div class="flex flex-wrap justify-center gap-8 md:gap-12 text-sm font-medium text-gray-700">
				<div class="flex items-center gap-2">
					{@html icons.camera}
					<span>Auto-capture</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.sparkles}
					<span>AI processing</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.search}
					<span>Instant search</span>
				</div>
				<div class="flex items-center gap-2">
					{@html icons.link}
					<span>Team sharing</span>
				</div>
			</div>
		</section>

		<!-- Features Grid -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-12 max-w-lg leading-tight">
				Documentation that writes itself while you work.
			</h2>

			<div class="grid grid-cols-1 md:grid-cols-3 gap-6">
				<!-- Card 1 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.camera}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Automated capture</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Screen recordings transform into step-by-step documentation automatically</p>
					</div>
				</div>

				<!-- Card 2 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.sparkles}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">AI processing</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Advanced AI extracts key information and creates searchable knowledge</p>
					</div>
				</div>

				<!-- Card 3 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.search}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Instant search</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Find any process, conversation, or detail in seconds across all docs</p>
					</div>
				</div>

				<!-- Card 4 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.speedometer}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Zero friction</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Pre-configured workflows that work immediately, no setup required</p>
					</div>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-50 p-8 rounded-2xl flex flex-col items-start h-64">
					<div class="mb-auto text-gray-900">
						{@html icons.link}
					</div>
					<div>
						<h3 class="font-bold text-lg mb-2 text-gray-900">Team knowledge</h3>
						<p class="text-sm text-gray-600 leading-relaxed">Share expertise across your team and onboard new members instantly</p>
					</div>
				</div>
			</div>
		</section>

		<!-- CRM Intelligence Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-primary-100 text-primary-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Relationship Intelligence
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Capture the $50B CRM market
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					AI-powered insights that transform customer interactions into actionable intelligence for your sales team.
				</p>
			</div>

			<div class="bg-primary-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-8">
					<!-- Left Visual: Customer Profile -->
					<div class="relative bg-white rounded-2xl shadow-lg p-6 overflow-hidden min-h-[300px]">
						<div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-primary-500 to-primary-600"></div>
						<div class="flex items-center gap-3 mb-6">
							<div class="w-10 h-10 rounded-full bg-gradient-to-br from-primary-600 to-primary-400 flex items-center justify-center text-white font-bold text-xs">
								AC
							</div>
							<div>
								<div class="font-bold text-gray-900">Acme Corp</div>
								<div class="text-xs text-primary-600 font-medium uppercase tracking-wider">Enterprise Account</div>
							</div>
						</div>
						<div class="space-y-4 text-sm">
							<div class="bg-primary-50 p-4 rounded-xl text-gray-800">
								<div class="font-semibold mb-2">Last Interaction</div>
								<p class="text-xs">Demo call discussing API integration needs. Key decision maker: Sarah Chen (CTO). Budget approved for Q2.</p>
							</div>
							<div class="flex gap-2 flex-wrap">
								<span class="bg-gray-900 text-white px-3 py-1 rounded-full text-xs font-medium">Hot Lead</span>
								<span class="bg-gray-900 text-white px-3 py-1 rounded-full text-xs font-medium">Enterprise</span>
							</div>
							<div class="flex gap-2 flex-wrap">
								<span class="bg-gray-900 text-white px-3 py-1 rounded-full text-xs font-medium">Tech Stack: React</span>
								<span class="bg-gray-900 text-white px-3 py-1 rounded-full text-xs font-medium">Team: 50+</span>
							</div>
						</div>
						<div class="mt-6">
							<button class="w-full py-2 border border-primary-200 text-primary-700 font-medium rounded-lg hover:bg-primary-50 transition-colors">
								View full profile
							</button>
						</div>
					</div>

					<!-- Right Visual: Insights Interface -->
					<div class="bg-white rounded-2xl shadow-lg p-6 min-h-[300px] flex flex-col">
						<div class="flex items-center gap-2 mb-4 text-xs text-gray-400 border-b border-gray-100 pb-2">
							<div class="w-2 h-2 rounded-full bg-primary-500"></div>
							<span>AI-Generated Insights</span>
						</div>
						<div class="flex-1 space-y-4">
							<div class="border border-gray-100 rounded-lg p-4">
								<h4 class="font-bold text-gray-900 text-sm mb-1">Customer Intent Analysis</h4>
								<div class="text-xs text-gray-500 mb-2">Based on 12 interactions</div>
								<p class="text-xs text-gray-600 line-clamp-3">
									Strong buying signals detected. Customer mentioned "scaling challenges" 3x in recent calls. Competitor comparison with Salesforce indicates high purchase intent.
								</p>
							</div>
							<div class="flex gap-2 items-center text-xs text-gray-500">
								<div class="flex -space-x-2">
									<div class="w-6 h-6 rounded-full bg-primary-200 border-2 border-white"></div>
									<div class="w-6 h-6 rounded-full bg-primary-300 border-2 border-white"></div>
								</div>
								<span>Analyzed by AI</span>
							</div>
							<div class="space-y-3 pt-2">
								<div class="flex gap-3">
									<div class="w-6 h-6 rounded-full bg-gray-800 shrink-0"></div>
									<div class="text-xs text-gray-800">
										<p class="font-bold mb-1">What's the next best action for Acme Corp?</p>
									</div>
								</div>
								<div class="flex gap-3">
									<div class="w-6 h-6 rounded-full bg-primary-500 shrink-0"></div>
									<div class="text-xs text-gray-600 bg-gray-50 p-3 rounded-lg rounded-tl-none">
										<p>Schedule technical deep-dive with Sarah Chen. Share case study from similar fintech client. Prepare ROI calculator showing 40% time savings.</p>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>

				<!-- Bottom Visual: Processing -->
				<div class="bg-white rounded-2xl shadow-lg p-6 md:p-8">
					<div class="relative mb-8">
						<input type="text" value="Recording customer demo call..." class="w-full bg-gray-50 border-none rounded-xl py-4 pl-12 pr-4 text-gray-500 focus:ring-0" readonly />
						<div class="absolute left-4 top-1/2 -translate-y-1/2 text-gray-400">
							{@html icons.camera}
						</div>
						<div class="absolute right-4 top-1/2 -translate-y-1/2 flex gap-2 text-gray-400">
							<div class="w-2 h-2 rounded-full bg-red-500 animate-pulse"></div>
						</div>
					</div>

					<div class="flex justify-center mb-8">
						<span class="bg-gray-100 text-gray-500 text-xs px-3 py-1 rounded-full">AI is processing your screen capture</span>
					</div>

					<div class="bg-primary-50/50 rounded-xl p-6 border border-primary-100">
						<div class="space-y-3">
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full bg-primary-500 animate-pulse"></div>
								<span class="text-sm text-gray-700">Roochi is analyzing</span>
							</div>
							<div class="flex items-start gap-3">
								<div class="w-3 h-3 rounded-full bg-green-500 mt-1"></div>
								<div class="text-sm text-gray-700">
									<span class="font-medium">Extracted</span> 
									<span class="font-bold bg-white px-1 rounded border border-gray-200 mx-1">24 key points</span> 
									from conversation and identified 
									<span class="font-bold bg-white px-1 rounded border border-gray-200 mx-1">3 action items</span> 
									for follow-up.
									<p class="text-xs text-gray-500 mt-1 max-w-md">Detected customer pain points around onboarding time. Roochi is cross-referencing with similar customer profiles.</p>
								</div>
							</div>
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full bg-green-500"></div>
								<span class="text-sm text-gray-700">Created doc in <span class="bg-primary-500 text-white px-2 py-0.5 rounded text-xs font-bold">Sales Calls</span></span>
							</div>
							<div class="flex items-center gap-3">
								<div class="w-3 h-3 rounded-full border-2 border-gray-300 border-t-gray-500 animate-spin"></div>
								<span class="text-sm text-gray-500">Updating CRM with <span class="text-primary-500">customer insights</span></span>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="grid grid-cols-1 md:grid-cols-2 gap-x-12 gap-y-4 max-w-4xl">
				<p class="text-xl text-gray-600 mb-6 md:col-span-2 leading-relaxed">
					Roochi captures every customer interaction, extracts insights automatically, and helps your sales team close deals faster with AI-powered intelligence.
				</p>
				
				<div class="space-y-4">
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.sparkles}
						<span>Auto-capture interactions</span>
					</div>
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.target}
						<span>Extract buying signals</span>
					</div>
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.plus}
						<span>Build customer profiles</span>
					</div>
				</div>

				<div class="space-y-4">
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.layout}
						<span>Connect conversation threads</span>
					</div>
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.maximize}
						<span>Generate action items</span>
					</div>
					<div class="flex items-center gap-3 text-gray-800 font-medium">
						{@html icons.externalLink}
						<span>Sync with your CRM</span>
					</div>
				</div>
			</div>
		</section>

		<!-- Scale Section -->
		<section class="max-w-6xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Built to Scale
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					From startup to 100K users
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Start with your sales team, scale across your entire organization with enterprise-grade infrastructure.
				</p>
			</div>

			<div class="bg-gray-50 rounded-3xl p-8 md:p-12 mb-16">
				<div class="bg-white rounded-2xl shadow-sm p-6 md:p-8 max-w-3xl mx-auto">
					<!-- Stats -->
					<div class="grid grid-cols-4 gap-4 mb-8">
						<div class="bg-primary-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-primary-800 mb-1">Active Users</div>
							<div class="text-2xl font-bold text-primary-900">2.4K</div>
						</div>
						<div class="bg-green-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-green-800 mb-1">Docs Created</div>
							<div class="text-2xl font-bold text-green-900">18K</div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">Searches</div>
							<div class="text-2xl font-bold text-gray-900">45K</div>
						</div>
						<div class="bg-gray-100 p-3 rounded-xl">
							<div class="text-xs font-bold text-gray-600 mb-1">Time Saved</div>
							<div class="text-2xl font-bold text-gray-900">320h</div>
						</div>
					</div>

					<!-- Growth Milestones -->
					<div class="space-y-6">
						<div>
							<div class="text-xs font-bold text-primary-500 mb-2 tracking-wide">CURRENT PHASE</div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-primary-500 flex items-center justify-center cursor-pointer bg-primary-500"></div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">Enterprise Sales Teams</h4>
									<p class="text-xs text-gray-500 mt-1">Capturing tribal knowledge from sales calls, demos, and customer interactions across 50+ enterprise accounts.</p>
									<div class="text-xs text-primary-500 mt-1 font-medium">ACTIVE · 2,400 USERS</div>
								</div>
							</div>
						</div>

						<div>
							<div class="text-xs font-bold text-gray-400 mb-2 tracking-wide">NEXT MILESTONE</div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-gray-300 group-hover:border-gray-400 cursor-pointer"></div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">Customer Success Teams</h4>
									<p class="text-xs text-gray-500 mt-1">Expand to customer success and support teams to capture onboarding workflows and troubleshooting guides.</p>
									<div class="flex gap-2 text-xs text-gray-400 mt-1">
										<span>TARGET · 10K USERS</span>
									</div>
								</div>
							</div>
						</div>

						<div>
							<div class="flex gap-4 items-start group">
								<div class="mt-1 w-5 h-5 rounded-full border-2 border-gray-300 cursor-pointer"></div>
								<div class="flex-1">
									<h4 class="font-bold text-gray-900">Product & Engineering</h4>
									<p class="text-xs text-gray-500 mt-1">Scale to product and engineering teams for technical documentation and knowledge sharing.</p>
									<div class="text-xs text-gray-400 mt-1">TARGET · 25K USERS</div>
								</div>
							</div>
						</div>

						<div>
							<div class="text-xs font-bold text-gray-400 mb-2 tracking-wide">LONG-TERM VISION</div>
							<div class="space-y-3 opacity-60">
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Full enterprise deployment — all departments</span>
								</div>
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">Cross-company knowledge network — 100K users</span>
								</div>
								<div class="flex gap-4 items-center">
									<div class="w-5 h-5 rounded-full border-2 border-gray-300"></div>
									<span class="text-sm text-gray-600">AI-powered organizational intelligence platform</span>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row gap-8 md:items-start justify-between">
				<div class="flex gap-6 text-sm font-medium text-gray-600">
					<div class="flex items-center gap-2">
						{@html icons.speedometer}
						<span>Fast deployment</span>
					</div>
					<div class="flex items-center gap-2">
						{@html icons.shield}
						<span>Enterprise security</span>
					</div>
					<div class="flex items-center gap-2">
						{@html icons.target}
						<span>Scalable infrastructure</span>
					</div>
				</div>
				<p class="text-xl text-gray-600 max-w-lg leading-relaxed">
					Pre-configured workflows that work immediately. No complex setup, no training required—just instant value for your team.
				</p>
			</div>
		</section>

		<!-- Use Cases Section -->
		<section class="max-w-7xl mx-auto px-6 py-20">
			<div class="mb-16">
				<span class="inline-block bg-gray-100 text-gray-700 px-3 py-1 rounded-full text-xs font-semibold uppercase tracking-wide mb-6">
					Use cases
				</span>
				<h2 class="text-4xl md:text-5xl font-bold text-gray-900 mb-6 tracking-tight">
					Built for busy founders
				</h2>
				<p class="text-xl text-gray-600 max-w-2xl leading-relaxed">
					Roochi helps early-stage startup founders capture customer insights without spending hours on manual research.
				</p>
			</div>

			<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
				<!-- Card 1 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Sales call documentation</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Automatically capture and document every sales conversation with searchable transcripts and key insights.</p>
				</div>
				<!-- Card 2 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Customer discovery</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Record customer interviews and extract pain points, feature requests, and buying signals automatically.</p>
				</div>
				<!-- Card 3 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Product demos</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Turn product demonstrations into reusable documentation that sales teams can reference anytime.</p>
				</div>
				<!-- Card 4 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Onboarding guides</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Create step-by-step onboarding documentation by simply recording your screen during walkthroughs.</p>
				</div>

				<!-- Card 5 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Process documentation</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Capture internal processes and workflows without interrupting your team's productivity.</p>
				</div>
				<!-- Card 6 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Competitive intelligence</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Document competitor analysis and market research findings in a searchable knowledge base.</p>
				</div>
				<!-- Card 7 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Team training</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Build a library of training materials by capturing expert knowledge from your best performers.</p>
				</div>
				<!-- Card 8 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Support tickets</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Document common issues and solutions to build a comprehensive support knowledge base.</p>
				</div>

				<!-- Card 9 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Feature requests</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Track and organize customer feature requests with context from actual conversations.</p>
				</div>
				<!-- Card 10 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">Meeting notes</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Never miss important details from customer meetings with AI-generated summaries and action items.</p>
				</div>
				<!-- Card 11 -->
				<div class="bg-gray-100 p-6 rounded-xl min-h-[200px] flex flex-col">
					<h3 class="font-bold text-gray-900 mb-2">CRM enrichment</h3>
					<p class="text-xs text-gray-600 mt-auto leading-relaxed">Automatically update your CRM with insights from every customer interaction.</p>
				</div>
			</div>
		</section>

		<!-- Footer -->
		<footer class="max-w-7xl mx-auto px-6 py-12 border-t border-gray-100">
			<div class="grid grid-cols-1 md:grid-cols-2 gap-8">
				<div>
					<h4 class="font-bold text-sm text-gray-900 mb-4">Resources</h4>
					<div class="grid grid-cols-2 gap-x-8 gap-y-3 text-xs text-gray-600">
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.sparkles} AI-powered documentation
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.camera} Getting started with Roochi
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.link} CRM integrations
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.target} Sales team best practices
						</a>
						<a href="#" class="flex items-center gap-2 hover:text-gray-900">
							{@html icons.search} Search & discovery tips
						</a>
					</div>
				</div>
			</div>

			<div class="flex flex-col md:flex-row justify-between items-center mt-12 pt-8 text-xs text-gray-400">
				<div class="flex items-center gap-2 mb-4 md:mb-0">
					<div class="w-6 h-6 text-gray-300">
						<svg viewBox="0 0 24 24" fill="currentColor" class="w-full h-full">
							<path d="M12 2C13.1 2 14 2.9 14 4C14 5.1 13.1 6 12 6C10.9 6 10 5.1 10 4C10 2.9 10.9 2 12 2ZM12 22C10.9 22 10 21.1 10 20C10 18.9 10.9 18 12 18C13.1 18 14 18.9 14 20C14 21.1 13.1 22 12 22ZM6 12C6 10.9 5.1 10 4 10C2.9 10 2 10.9 2 12C2 13.1 2.9 14 4 14C5.1 14 6 13.1 6 12ZM22 12C22 13.1 21.1 14 20 14C18.9 14 18 13.1 18 12C18 10.9 18.9 10 20 10C21.1 10 22 10.9 22 12ZM17.66 7.34C18.44 6.56 19.7 6.56 20.48 7.34C21.26 8.12 21.26 9.38 20.48 10.16C19.7 10.94 18.44 10.94 17.66 10.16C16.88 9.38 16.88 8.12 17.66 7.34ZM6.34 16.66C5.56 17.44 4.3 17.44 3.52 16.66C2.74 15.88 2.74 14.62 3.52 13.84C4.3 13.06 5.56 13.06 6.34 13.84C7.12 14.62 7.12 15.88 6.34 16.66ZM16.66 17.66C15.88 18.44 15.88 19.7 16.66 20.48C17.44 21.26 18.7 21.26 19.48 20.48C20.26 19.7 20.26 18.44 19.48 17.66C18.7 16.88 18.7 15.62 17.92 14.84L16.66 17.66ZM7.34 6.34C8.12 5.56 8.12 4.3 7.34 3.52C6.56 2.74 5.3 2.74 4.52 3.52C3.74 4.3 3.74 5.56 4.52 6.34C5.3 7.12 6.56 7.12 7.34 6.34Z" />
						</svg>
					</div>
					<div>
						<p>Copyright © 2025 Roochi Inc.</p>
						<p>All rights reserved. Terms of Service & Privacy Policy.</p>
					</div>
				</div>
				<div class="bg-gray-200 text-gray-600 px-3 py-1 rounded text-xs font-medium">
					Status
				</div>
			</div>
		</footer>

	</main>
</div>

