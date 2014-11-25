title: How to create a navigation menu

# How to create a navigation menu

In this how-to, we'll create a simple menu which you can use as the primary navigation for your website. This outputs a
top level menu with a nested second level using the `Menu` loop and a `Children` loop.

**mysite/templates/Page.ss**

	:::ss
	<ul>
		<% loop $Menu(1) %>
			<li>
				<a href="$Link" title="Go to the $Title page" class="$LinkingMode">
					$MenuTitle
				</a>

				<% if $LinkOrSection == section %>
					<% if $Children %>
						<li><ul class="secondary">
							<% loop $Children %>
								<li class="$LinkingMode"><a href="$Link">$MenuTitle</a></li>
							<% end_loop %>
						</ul></li>
					<% end_if %>
				<% end_if %>
			</li>
		<% end_loop %>
	</ul>

## Related

* [Template syntax](../syntax)
* [Common variables](../common_variables)