# Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::InitializeComponent

- ea: `0x4b70`
- end: `0x4edb`
- name: `Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::InitializeComponent`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4a10`

## callees

- `0x10fc0`
- `0x10fe0`

## string_xrefs

- `0x4b70`: `Microsoft.Crm.Setup.Common.DiagnosticsPage`
- `0x4ba2`: `resultsPanel.AccessibleDescription`
- `0x4bbd`: `resultsPanel.AccessibleName`
- `0x4d80`: `$this.AccessibleDescription`
- `0x4d96`: `$this.AccessibleName`

## pseudocode

```c

```

## disassembly

```asm
0x4b70  ldstr    aMicrosoftCrmSe_0// "Microsoft.Crm.Setup.Common.DiagnosticsP"...
0x4b75  ldtoken  Microsoft.Crm.Setup.Common.UI.DiagnosticsPage
0x4b7a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4b7f  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x4b84  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x4b89  stloc.0
0x4b8a  ldarg.0
0x4b8b  newobj   instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::.ctor()
0x4b90  stfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4b95  ldarg.0
0x4b96  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x4b9b  ldarg.0
0x4b9c  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4ba1  ldloc.0
0x4ba2  ldstr    aResultspanelAc// "resultsPanel.AccessibleDescription"
0x4ba7  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x4bac  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x4bb1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x4bb6  ldarg.0
0x4bb7  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4bbc  ldloc.0
0x4bbd  ldstr    aResultspanelAc_0// "resultsPanel.AccessibleName"
0x4bc2  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x4bc7  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x4bcc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x4bd1  ldarg.0
0x4bd2  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4bd7  ldc.i4.4
0x4bd8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x4bdd  ldarg.0
0x4bde  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4be3  ldloc.0
0x4be4  ldstr    aResultspanelAu// "resultsPanel.AutoScroll"
0x4be9  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4bee  unbox.any [mscorlib]System.Boolean
0x4bf3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScroll(bool)
0x4bf8  ldarg.0
0x4bf9  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4bfe  ldloc.0
0x4bff  ldstr    aResultspanelAu_0// "resultsPanel.AutoScrollMargin"
0x4c04  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4c09  unbox.any [System.Drawing]System.Drawing.Size
0x4c0e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMargin(valuetype [System.Drawing]System.Drawing.Size)
0x4c13  ldarg.0
0x4c14  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4c19  ldloc.0
0x4c1a  ldstr    aResultspanelAu_1// "resultsPanel.AutoScrollMinSize"
0x4c1f  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4c24  unbox.any [System.Drawing]System.Drawing.Size
0x4c29  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMinSize(valuetype [System.Drawing]System.Drawing.Size)
0x4c2e  ldarg.0
0x4c2f  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4c34  ldloc.0
0x4c35  ldstr    aResultspanelBa// "resultsPanel.BackgroundImage"
0x4c3a  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4c3f  castclass [System.Drawing]System.Drawing.Image
0x4c44  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackgroundImage(class [System.Drawing]System.Drawing.Image)
0x4c49  ldarg.0
0x4c4a  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4c4f  ldc.i4.5
0x4c50  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x4c55  ldarg.0
0x4c56  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4c5b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0x4c60  ldc.i4.4
0x4c61  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::set_All(int32)
0x4c66  ldarg.0
0x4c67  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4c6c  ldloc.0
0x4c6d  ldstr    aResultspanelEn// "resultsPanel.Enabled"
0x4c72  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4c77  unbox.any [mscorlib]System.Boolean
0x4c7c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x4c81  ldarg.0
0x4c82  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4c87  ldloc.0
0x4c88  ldstr    aResultspanelFo// "resultsPanel.Font"
0x4c8d  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4c92  castclass [System.Drawing]System.Drawing.Font
0x4c97  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0x4c9c  ldarg.0
0x4c9d  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4ca2  ldloc.0
0x4ca3  ldstr    aResultspanelIm// "resultsPanel.ImeMode"
0x4ca8  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4cad  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0x4cb2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0x4cb7  ldarg.0
0x4cb8  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4cbd  ldloc.0
0x4cbe  ldstr    aResultspanelLo// "resultsPanel.Location"
0x4cc3  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4cc8  unbox.any [System.Drawing]System.Drawing.Point
0x4ccd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x4cd2  ldarg.0
0x4cd3  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4cd8  ldstr    aResultspanel// "resultsPanel"
0x4cdd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x4ce2  ldarg.0
0x4ce3  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4ce8  ldnull
0x4ce9  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::set_ResultsReady(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel/ResultsReadyCallback)
0x4cee  ldarg.0
0x4cef  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4cf4  ldloc.0
0x4cf5  ldstr    aResultspanelRi// "resultsPanel.RightToLeft"
0x4cfa  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4cff  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0x4d04  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0x4d09  ldarg.0
0x4d0a  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4d0f  ldc.i4.1
0x4d10  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::set_RunOne(bool)
0x4d15  ldarg.0
0x4d16  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4d1b  ldloc.0
0x4d1c  ldstr    aResultspanelSi// "resultsPanel.Size"
0x4d21  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4d26  unbox.any [System.Drawing]System.Drawing.Size
0x4d2b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x4d30  ldarg.0
0x4d31  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4d36  ldnull
0x4d37  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::set_Sniffer(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.EDWTool)
0x4d3c  ldarg.0
0x4d3d  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4d42  ldnull
0x4d43  callvirt instance void [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::set_SnifferToRun(class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.BaseGroup)
0x4d48  ldarg.0
0x4d49  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4d4e  ldloc.0
0x4d4f  ldstr    aResultspanelTa// "resultsPanel.TabIndex"
0x4d54  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4d59  unbox.any [mscorlib]System.Int32
0x4d5e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x4d63  ldarg.0
0x4d64  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4d69  ldloc.0
0x4d6a  ldstr    aResultspanelVi// "resultsPanel.Visible"
0x4d6f  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4d74  unbox.any [mscorlib]System.Boolean
0x4d79  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x4d7e  ldarg.0
0x4d7f  ldloc.0
0x4d80  ldstr    aThisAccessible// "$this.AccessibleDescription"
0x4d85  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x4d8a  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x4d8f  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x4d94  ldarg.0
0x4d95  ldloc.0
0x4d96  ldstr    aThisAccessible_0// "$this.AccessibleName"
0x4d9b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x4da0  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x4da5  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x4daa  ldarg.0
0x4dab  ldloc.0
0x4dac  ldstr    aThisAutoscroll// "$this.AutoScroll"
0x4db1  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4db6  unbox.any [mscorlib]System.Boolean
0x4dbb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScroll(bool)
0x4dc0  ldarg.0
0x4dc1  ldloc.0
0x4dc2  ldstr    aThisAutoscroll_0// "$this.AutoScrollMargin"
0x4dc7  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4dcc  unbox.any [System.Drawing]System.Drawing.Size
0x4dd1  call     instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMargin(valuetype [System.Drawing]System.Drawing.Size)
0x4dd6  ldarg.0
0x4dd7  ldloc.0
0x4dd8  ldstr    aThisAutoscroll_1// "$this.AutoScrollMinSize"
0x4ddd  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4de2  unbox.any [System.Drawing]System.Drawing.Size
0x4de7  call     instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMinSize(valuetype [System.Drawing]System.Drawing.Size)
0x4dec  ldarg.0
0x4ded  ldloc.0
0x4dee  ldstr    aThisBackground// "$this.BackgroundImage"
0x4df3  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4df8  castclass [System.Drawing]System.Drawing.Image
0x4dfd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackgroundImage(class [System.Drawing]System.Drawing.Image)
0x4e02  ldarg.0
0x4e03  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x4e08  ldarg.0
0x4e09  ldfld    class [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel Microsoft.Crm.Setup.Common.UI.DiagnosticsPage::resultsPanel
0x4e0e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ResultsPanel::get_ContainerPanel()
0x4e13  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x4e18  ldarg.0
0x4e19  ldloc.0
0x4e1a  ldstr    aThisEnabled// "$this.Enabled"
0x4e1f  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4e24  unbox.any [mscorlib]System.Boolean
0x4e29  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x4e2e  ldarg.0
0x4e2f  ldloc.0
0x4e30  ldstr    aThisFont// "$this.Font"
0x4e35  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4e3a  castclass [System.Drawing]System.Drawing.Font
0x4e3f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0x4e44  ldarg.0
0x4e45  ldloc.0
0x4e46  ldstr    aThisHeaderdeta// "$this.HeaderDetails"
0x4e4b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x4e50  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x4e55  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::set_HeaderDetails(string value)
0x4e5a  ldarg.0
0x4e5b  ldloc.0
0x4e5c  ldstr    aThisHeadertitl// "$this.HeaderTitle"
0x4e61  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x4e66  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x4e6b  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::set_HeaderTitle(string value)
0x4e70  ldarg.0
0x4e71  ldloc.0
0x4e72  ldstr    aThisImemode// "$this.ImeMode"
0x4e77  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4e7c  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0x4e81  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0x4e86  ldarg.0
0x4e87  ldloc.0
0x4e88  ldstr    aThisLocation// "$this.Location"
0x4e8d  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4e92  unbox.any [System.Drawing]System.Drawing.Point
0x4e97  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x4e9c  ldarg.0
0x4e9d  ldstr    aDiagnosticspag// "DiagnosticsPage"
0x4ea2  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x4ea7  ldarg.0
0x4ea8  ldloc.0
0x4ea9  ldstr    aThisRighttolef// "$this.RightToLeft"
0x4eae  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4eb3  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0x4eb8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0x4ebd  ldarg.0
0x4ebe  ldloc.0
0x4ebf  ldstr    aThisSize// "$this.Size"
0x4ec4  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x4ec9  unbox.any [System.Drawing]System.Drawing.Size
0x4ece  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x4ed3  ldarg.0
0x4ed4  ldc.i4.0
0x4ed5  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x4eda  ret
```
