Rich push notifications
=

Notification payload will includes message ID (already does for some providers)
Message ID will be used to request PushData from service (endpoint already exists. Some changes are required)
Service will return pushData according to device type (for now, same data for all devices, but differentiation by device and variant is possible)

PushData contract
-

  [{
		device : 511,
		variant : null,
		pushData : {
			initial : {
				title : "...",
				text : "...",
				imageUrl : "...", // either image or long text can be displayed in notification extended view (but not both)
				longText : "...", // show image if exist, if not - show long text
				defaultAction : {
					type : 1, // enum: 1 = open app (default), 2 = navigate to page / tab / item, 3 = play audio, 4 = play video, ...
					meta : {
						...
					}, // page ID, tab ID, video URL, etc.
				},
				buttons : [{
						title : "...",
						iconUrl : "...",
						actions : [{
								type : 2, // enum: 1 = open app (default), 2 = navigate to page / tab / item, 3 = play audio, 4 = play video, ...
								meta : {
									...
								}, // page ID, tab ID, video URL, etc.
							}
						]
					}, {
						title : "...",
						iconUrl : "...",
						actions : [{
								type : 4, // enum: 1 = open app (default), 2 = navigate to page / tab / item, 3 = play audio, 4 = play video, ...
								meta : {
									...
								}, // page ID, tab ID, video URL, etc.
							}
						]
					}
				]
			},
			inApp : {
				display : 1, // enum: 1 = dialog, 2 = full screen, ...
				title : "...",
				html : "...",
				buttons : [{
						title : "...",
						iconUrl : "...",
						actions : [{
								type : 4, // enum: 1 = open app (default), 2 = navigate to page / tab / item, 3 = play audio, 4 = play video, ...
								meta : {
									...
								}, // page ID, tab ID, video URL, etc.
							}
						]
					}
				]
			}
		}
	 }
  ]
