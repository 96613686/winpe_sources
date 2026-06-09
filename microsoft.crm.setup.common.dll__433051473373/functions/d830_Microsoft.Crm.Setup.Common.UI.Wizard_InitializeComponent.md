# Microsoft.Crm.Setup.Common.UI.Wizard::InitializeComponent

- ea: `0xd830`
- end: `0xfb93`
- name: `Microsoft.Crm.Setup.Common.UI.Wizard::InitializeComponent`
- size: `9059`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd730`

## string_xrefs

- `0xf969`: `$this.AccessibleDescription`
- `0xf97f`: `$this.AccessibleName`
- `0xfaea`: `$this.MaximumSize`
- `0xfb00`: `$this.MinimumSize`
- `0xd830`: `Microsoft.Crm.Setup.Common.Wizard`
- `0xd95b`: `buttonPanel.AccessibleDescription`
- `0xd976`: `buttonPanel.AccessibleName`
- `0xdc4d`: `cancelButton.AccessibleDescription`
- `0xdc68`: `cancelButton.AccessibleName`
- `0xdea1`: `finishButton.AccessibleDescription`
- `0xdebc`: `finishButton.AccessibleName`
- `0xe123`: `nextButton.AccessibleDescription`
- `0xe13e`: `nextButton.AccessibleName`
- `0xe399`: `backButton.AccessibleDescription`
- `0xe3b4`: `backButton.AccessibleName`
- `0xe6bf`: `headerPanel.AccessibleDescription`
- `0xe6da`: `headerPanel.AccessibleName`
- `0xe907`: `headerDetailsLabel.AccessibleDescription`
- `0xe922`: `headerDetailsLabel.AccessibleName`
- `0xeb28`: `headerTitleLabel.AccessibleDescription`
- `0xeb43`: `headerTitleLabel.AccessibleName`
- `0xed2e`: `headerPictureBox.AccessibleDescription`
- `0xed49`: `headerPictureBox.AccessibleName`
- `0xeefa`: `datamigration.AccessibleDescription`
- `0xef15`: `datamigration.AccessibleName`
- `0xf0f9`: `pagePanel.AccessibleDescription`
- `0xf114`: `pagePanel.AccessibleName`
- `0xf31a`: `spacerPanel.AccessibleDescription`
- `0xf335`: `spacerPanel.AccessibleName`
- `0xf52b`: `labelBottomSeparator.AccessibleDescription`
- `0xf546`: `labelBottomSeparator.AccessibleName`
- `0xf72d`: `labelTopSeparator.AccessibleDescription`
- `0xf748`: `labelTopSeparator.AccessibleName`

## pseudocode

```c

```

## disassembly

```asm
0xd830  ldstr    aMicrosoftCrmSe_8// "Microsoft.Crm.Setup.Common.Wizard"
0xd835  ldtoken  Microsoft.Crm.Setup.Common.UI.Wizard
0xd83a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd83f  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xd844  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0xd849  stloc.0
0xd84a  ldarg.0
0xd84b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0xd850  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd855  ldarg.0
0xd856  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0xd85b  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::headerPanel
0xd860  ldarg.0
0xd861  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0xd866  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::headerTitlePanel
0xd86b  ldarg.0
0xd86c  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0xd871  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::pagePanel
0xd876  ldarg.0
0xd877  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0xd87c  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::spacerPanel
0xd881  ldarg.0
0xd882  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0xd887  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonSpacerPanel
0xd88c  ldarg.0
0xd88d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xd892  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::cancelButton
0xd897  ldarg.0
0xd898  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xd89d  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::finishButton
0xd8a2  ldarg.0
0xd8a3  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xd8a8  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::nextButton
0xd8ad  ldarg.0
0xd8ae  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xd8b3  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::backButton
0xd8b8  ldarg.0
0xd8b9  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xd8be  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.Wizard::headerDetailsLabel
0xd8c3  ldarg.0
0xd8c4  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xd8c9  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.Wizard::headerTitleLabel
0xd8ce  ldarg.0
0xd8cf  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0xd8d4  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.Wizard::headerPictureBox
0xd8d9  ldarg.0
0xd8da  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0xd8df  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.Wizard::datamigration
0xd8e4  ldarg.0
0xd8e5  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xd8ea  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.Wizard::labelBottomSeparator
0xd8ef  ldarg.0
0xd8f0  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xd8f5  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.Wizard::labelTopSeparator
0xd8fa  ldarg.0
0xd8fb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0xd900  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::TopSpacerPanel
0xd905  ldarg.0
0xd906  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd90b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xd910  ldarg.0
0xd911  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::headerPanel
0xd916  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xd91b  ldarg.0
0xd91c  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xd921  ldarg.0
0xd922  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd927  ldc.i4.0
0xd928  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xd92d  ldarg.0
0xd92e  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd933  ldc.i4.2
0xd934  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xd939  ldarg.0
0xd93a  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd93f  ldloc.0
0xd940  ldstr    aButtonpanelFlo// "buttonPanel.FlowDirection"
0xd945  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xd94a  unbox.any [System.Windows.Forms]System.Windows.Forms.FlowDirection
0xd94f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::set_FlowDirection(valuetype [System.Windows.Forms]System.Windows.Forms.FlowDirection)
0xd954  ldarg.0
0xd955  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd95a  ldloc.0
0xd95b  ldstr    aButtonpanelAcc// "buttonPanel.AccessibleDescription"
0xd960  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xd965  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xd96a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xd96f  ldarg.0
0xd970  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd975  ldloc.0
0xd976  ldstr    aButtonpanelAcc_0// "buttonPanel.AccessibleName"
0xd97b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xd980  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xd985  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xd98a  ldarg.0
0xd98b  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd990  ldloc.0
0xd991  ldstr    aButtonpanelAnc// "buttonPanel.Anchor"
0xd996  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xd99b  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0xd9a0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xd9a5  ldarg.0
0xd9a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd9ab  ldloc.0
0xd9ac  ldstr    aButtonpanelAut// "buttonPanel.AutoScroll"
0xd9b1  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xd9b6  unbox.any [mscorlib]System.Boolean
0xd9bb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScroll(bool)
0xd9c0  ldarg.0
0xd9c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd9c6  ldloc.0
0xd9c7  ldstr    aButtonpanelAut_0// "buttonPanel.AutoScrollMargin"
0xd9cc  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xd9d1  unbox.any [System.Drawing]System.Drawing.Size
0xd9d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMargin(valuetype [System.Drawing]System.Drawing.Size)
0xd9db  ldarg.0
0xd9dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd9e1  ldloc.0
0xd9e2  ldstr    aButtonpanelAut_1// "buttonPanel.AutoScrollMinSize"
0xd9e7  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xd9ec  unbox.any [System.Drawing]System.Drawing.Size
0xd9f1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMinSize(valuetype [System.Drawing]System.Drawing.Size)
0xd9f6  ldarg.0
0xd9f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xd9fc  ldloc.0
0xd9fd  ldstr    aButtonpanelAut_2// "buttonPanel.AutoSize"
0xda02  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xda07  unbox.any [mscorlib]System.Boolean
0xda0c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xda11  ldarg.0
0xda12  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xda17  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0xda1c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xda21  ldarg.0
0xda22  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xda27  ldloc.0
0xda28  ldstr    aButtonpanelBac// "buttonPanel.BackgroundImage"
0xda2d  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xda32  castclass [System.Drawing]System.Drawing.Image
0xda37  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackgroundImage(class [System.Drawing]System.Drawing.Image)
0xda3c  ldarg.0
0xda3d  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xda42  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xda47  ldarg.0
0xda48  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonSpacerPanel
0xda4d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xda52  ldarg.0
0xda53  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xda58  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xda5d  ldarg.0
0xda5e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::cancelButton
0xda63  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xda68  ldarg.0
0xda69  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xda6e  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xda73  ldarg.0
0xda74  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::finishButton
0xda79  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xda7e  ldarg.0
0xda7f  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xda84  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xda89  ldarg.0
0xda8a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::nextButton
0xda8f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xda94  ldarg.0
0xda95  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xda9a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xda9f  ldarg.0
0xdaa0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::backButton
0xdaa5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection::Add(class [System.Windows.Forms]System.Windows.Forms.Control)
0xdaaa  ldarg.0
0xdaab  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdab0  ldloc.0
0xdab1  ldstr    aButtonpanelDoc// "buttonPanel.Dock"
0xdab6  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdabb  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0xdac0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xdac5  ldarg.0
0xdac6  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdacb  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0xdad0  ldc.i4.8
0xdad1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::set_Right(int32)
0xdad6  ldarg.0
0xdad7  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdadc  ldloc.0
0xdadd  ldstr    aButtonpanelEna// "buttonPanel.Enabled"
0xdae2  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdae7  unbox.any [mscorlib]System.Boolean
0xdaec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xdaf1  ldarg.0
0xdaf2  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdaf7  ldloc.0
0xdaf8  ldstr    aButtonpanelFon// "buttonPanel.Font"
0xdafd  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdb02  castclass [System.Drawing]System.Drawing.Font
0xdb07  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0xdb0c  ldarg.0
0xdb0d  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdb12  ldloc.0
0xdb13  ldstr    aButtonpanelIme// "buttonPanel.ImeMode"
0xdb18  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdb1d  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0xdb22  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xdb27  ldarg.0
0xdb28  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdb2d  ldloc.0
0xdb2e  ldstr    aButtonpanelLoc// "buttonPanel.Location"
0xdb33  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdb38  unbox.any [System.Drawing]System.Drawing.Point
0xdb3d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xdb42  ldarg.0
0xdb43  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdb48  ldstr    aButtonpanel// "buttonPanel"
0xdb4d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xdb52  ldarg.0
0xdb53  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdb58  ldloc.0
0xdb59  ldstr    aButtonpanelRig// "buttonPanel.RightToLeft"
0xdb5e  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdb63  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0xdb68  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0xdb6d  ldarg.0
0xdb6e  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdb73  ldloc.0
0xdb74  ldstr    aButtonpanelSiz// "buttonPanel.Size"
0xdb79  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdb7e  unbox.any [System.Drawing]System.Drawing.Size
0xdb83  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xdb88  ldarg.0
0xdb89  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdb8e  ldloc.0
0xdb8f  ldstr    aButtonpanelTab// "buttonPanel.TabIndex"
0xdb94  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdb99  unbox.any [mscorlib]System.Int32
0xdb9e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xdba3  ldarg.0
0xdba4  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdba9  ldc.i4.1
0xdbaa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Panel::set_TabStop(bool)
0xdbaf  ldarg.0
0xdbb0  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdbb5  ldloc.0
0xdbb6  ldstr    aButtonpanelTex// "buttonPanel.Text"
0xdbbb  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xdbc0  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xdbc5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xdbca  ldarg.0
0xdbcb  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xdbd0  ldloc.0
0xdbd1  ldstr    aButtonpanelVis// "buttonPanel.Visible"
0xdbd6  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdbdb  unbox.any [mscorlib]System.Boolean
0xdbe0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xdbe5  ldarg.0
0xdbe6  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonSpacerPanel
0xdbeb  ldloc.0
0xdbec  ldstr    aButtonspacerpa// "buttonSpacerPanel.Anchor"
0xdbf1  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdbf6  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0xdbfb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xdc00  ldarg.0
0xdc01  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonSpacerPanel
0xdc06  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Control()
0xdc0b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xdc10  ldarg.0
0xdc11  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonSpacerPanel
0xdc16  ldloc.0
0xdc17  ldstr    aButtonspacerpa_0// "buttonSpacerPanel.Size"
0xdc1c  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdc21  unbox.any [System.Drawing]System.Drawing.Size
0xdc26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xdc2b  ldarg.0
0xdc2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonSpacerPanel
0xdc31  ldloc.0
0xdc32  ldstr    aButtonspacerpa_1// "buttonSpacerPanel.Dock"
0xdc37  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdc3c  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0xdc41  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xdc46  ldarg.0
0xdc47  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::cancelButton
0xdc4c  ldloc.0
0xdc4d  ldstr    aCancelbuttonAc// "cancelButton.AccessibleDescription"
0xdc52  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xdc57  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xdc5c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xdc61  ldarg.0
0xdc62  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::cancelButton
0xdc67  ldloc.0
0xdc68  ldstr    aCancelbuttonAc_0// "cancelButton.AccessibleName"
0xdc6d  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xdc72  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xdc77  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xdc7c  ldarg.0
0xdc7d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::cancelButton
0xdc82  ldloc.0
0xdc83  ldstr    aCancelbuttonAn// "cancelButton.Anchor"
0xdc88  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xdc8d  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0xdc92  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xdc97  ldarg.0
  ... truncated ...
```
