# Microsoft.Crm.Setup.Common.UI.InstallLocationPage::InitializeComponent

- ea: `0x8130`
- end: `0x836f`
- name: `Microsoft.Crm.Setup.Common.UI.InstallLocationPage::InitializeComponent`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x80a0`

## callees

- `0xb1b0`
- `0xb1d0`
- `0xb200`
- `0xb450`
- `0x10ac0`
- `0x10b80`
- `0x10be0`
- `0x111c0`

## string_xrefs

- `0x823c`: `pathSpace`
- `0x824c`: `pathSpace`
- `0x82a1`: `folderSelectPanel.AccessibleName`
- `0x8321`: `InstallLocationPage`

## pseudocode

```c

```

## disassembly

```asm
0x8130  ldtoken  Microsoft.Crm.Setup.Common.InstallLocationPage
0x8135  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x813a  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(class [mscorlib]System.Type)
0x813f  stloc.0
0x8140  ldarg.0
0x8141  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FolderBrowserDialog::.ctor()
0x8146  stfld    class [System.Windows.Forms]System.Windows.Forms.FolderBrowserDialog Microsoft.Crm.Setup.Common.UI.InstallLocationPage::folderBrowserDialog
0x814b  ldarg.0
0x814c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x8151  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.InstallLocationPage::browseButton
0x8156  ldarg.0
0x8157  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x815c  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x8161  ldarg.0
0x8162  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x8167  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderLabel
0x816c  ldarg.0
0x816d  newobj   instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::.ctor()
0x8172  stfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x8177  ldarg.0
0x8178  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0x817d  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.InstallLocationPage::folderSelectPanel
0x8182  ldarg.0
0x8183  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x8188  ldloc.0
0x8189  ldarg.0
0x818a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.InstallLocationPage::browseButton
0x818f  ldstr    aBrowsebutton// "browseButton"
0x8194  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0x8199  ldarg.0
0x819a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.InstallLocationPage::browseButton
0x819f  ldstr    aBrowsebutton// "browseButton"
0x81a4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x81a9  ldarg.0
0x81aa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.InstallLocationPage::browseButton
0x81af  ldarg.0
0x81b0  ldftn    instance void Microsoft.Crm.Setup.Common.UI.InstallLocationPage::BrowseButton_Click(object sender, class [mscorlib]System.EventArgs e)
0x81b6  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81bb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0x81c0  ldloc.0
0x81c1  ldarg.0
0x81c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x81c7  ldstr    aTargetfolderte// "targetFolderTextBox"
0x81cc  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0x81d1  ldarg.0
0x81d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x81d7  ldstr    aTargetfolderte// "targetFolderTextBox"
0x81dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x81e1  ldarg.0
0x81e2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x81e7  ldarg.0
0x81e8  ldftn    instance void Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox_TextChanged(object sender, class [mscorlib]System.EventArgs e)
0x81ee  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x81f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_TextChanged(class [mscorlib]System.EventHandler)
0x81f8  ldloc.0
0x81f9  ldarg.0
0x81fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderLabel
0x81ff  ldstr    aTargetfolderla// "targetFolderLabel"
0x8204  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0x8209  ldarg.0
0x820a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderLabel
0x820f  call     class [System.Windows.Forms]System.Windows.Forms.Cursor [System.Windows.Forms]System.Windows.Forms.Cursors::get_IBeam()
0x8214  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Cursor(class [System.Windows.Forms]System.Windows.Forms.Cursor)
0x8219  ldarg.0
0x821a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderLabel
0x821f  ldstr    aTargetfolderla// "targetFolderLabel"
0x8224  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8229  ldarg.0
0x822a  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x822f  ldc.i4.0
0x8230  callvirt instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::set_AdminInstall(bool value)
0x8235  ldloc.0
0x8236  ldarg.0
0x8237  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x823c  ldstr    aPathspace// "pathSpace"
0x8241  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0x8246  ldarg.0
0x8247  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x824c  ldstr    aPathspace// "pathSpace"
0x8251  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x8256  ldarg.0
0x8257  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x825c  ldstr    asc_18D5A// ""
0x8261  callvirt instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::set_Path(string value)
0x8266  ldarg.0
0x8267  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x826c  ldc.i4.m1
0x826d  conv.i8
0x826e  callvirt instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::set_SpaceRequired(int64 value)
0x8273  ldarg.0
0x8274  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.InstallLocationPage::folderSelectPanel
0x8279  ldc.i4.0
0x827a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::set_FlowDirection(valuetype [System.Windows.Forms]System.Windows.Forms.FlowDirection)
0x827f  ldarg.0
0x8280  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.InstallLocationPage::folderSelectPanel
0x8285  ldloc.0
0x8286  ldstr    aFolderselectpa// "folderSelectPanel.Size"
0x828b  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x8290  unbox.any [System.Drawing]System.Drawing.Size
0x8295  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x829a  ldarg.0
0x829b  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.InstallLocationPage::folderSelectPanel
0x82a0  ldloc.0
0x82a1  ldstr    aFolderselectpa_0// "folderSelectPanel.AccessibleName"
0x82a6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x82ab  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x82b0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x82b5  ldarg.0
0x82b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.InstallLocationPage::folderSelectPanel
0x82bb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82c0  ldarg.0
0x82c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x82c6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x82cb  ldarg.0
0x82cc  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.InstallLocationPage::folderSelectPanel
0x82d1  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82d6  ldarg.0
0x82d7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.InstallLocationPage::browseButton
0x82dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x82e1  ldarg.0
0x82e2  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82e7  ldarg.0
0x82e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderLabel
0x82ed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x82f2  ldarg.0
0x82f3  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x82f8  ldarg.0
0x82f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.InstallLocationPage::folderSelectPanel
0x82fe  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x8303  ldarg.0
0x8304  call     instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0x8309  ldarg.0
0x830a  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x830f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0x8314  ldloc.0
0x8315  ldarg.0
0x8316  ldstr    aThis// "$this"
0x831b  callvirt instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::ApplyResources(object, string)
0x8320  ldarg.0
0x8321  ldstr    aInstalllocatio_1// "InstallLocationPage"
0x8326  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x832b  ldarg.0
0x832c  ldarg.0
0x832d  ldftn    instance void Microsoft.Crm.Setup.Common.UI.InstallLocationPage::InstallLocationPage_NextClicked(object sender, class Microsoft.Crm.Setup.Common.UI.NavigationEventArgs e)
0x8333  newobj   instance void Microsoft.Crm.Setup.Common.UI.NavigationEventHandler::.ctor(object object, native int method)
0x8338  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::add_NextClicked(class Microsoft.Crm.Setup.Common.UI.NavigationEventHandler value)
0x833d  ldarg.0
0x833e  ldarg.0
0x833f  ldftn    instance void Microsoft.Crm.Setup.Common.UI.InstallLocationPage::InstallLocationPage_BackClicked(object sender, class Microsoft.Crm.Setup.Common.UI.NavigationEventArgs e)
0x8345  newobj   instance void Microsoft.Crm.Setup.Common.UI.NavigationEventHandler::.ctor(object object, native int method)
0x834a  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::add_BackClicked(class Microsoft.Crm.Setup.Common.UI.NavigationEventHandler value)
0x834f  ldarg.0
0x8350  ldarg.0
0x8351  ldftn    instance void Microsoft.Crm.Setup.Common.UI.InstallLocationPage::InstallLocationPage_PageActivated(object sender, class [mscorlib]System.EventArgs e)
0x8357  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x835c  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::add_PageActivated(class [mscorlib]System.EventHandler value)
0x8361  ldarg.0
0x8362  ldc.i4.0
0x8363  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::ResumeLayout(bool)
0x8368  ldarg.0
0x8369  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::PerformLayout()
0x836e  ret
```
