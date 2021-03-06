### TabControl SelectionChanged event and SelectedContent property

|   |   |
|---|---|
|Details|Starting with the .NET Framework 4.7.1, a <code>T:System.Windows.Controls.TabControl</code> updates the value of its <code>P:System.Windows.Controls.TabControl.SelectedContent</code> property before raising the <code>E:System.Windows.Controls.Primitives.Selector.SelectionChanged</code> event, when its selection changes.In the .NET Framework 4.7 and earlier versions, the update to SelectedContent happened after the event.|
|Suggestion|Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the <code>&lt;runtime&gt;</code> section of the application configuration file:<pre><code>&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the <code>&lt;runtime&gt;</code> section of the application .configuration file:<pre><code>&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Scope|Minor|
|Version|4.7.1|
|Type|Retargeting|
|Affected APIs|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|

