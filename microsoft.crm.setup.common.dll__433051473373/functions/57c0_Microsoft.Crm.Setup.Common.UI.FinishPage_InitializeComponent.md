# Microsoft.Crm.Setup.Common.UI.FinishPage::InitializeComponent

- ea: `0x57c0`
- end: `0x6b7c`
- name: `Microsoft.Crm.Setup.Common.UI.FinishPage::InitializeComponent`
- size: `5052`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x56d0`

## callees

- `0x10ac0`
- `0x10c40`
- `0x10fc0`
- `0x10fe0`

## string_xrefs

- `0x68e9`: `$this.AccessibleDescription`
- `0x68ff`: `$this.AccessibleName`
- `0x57c0`: `Microsoft.Crm.Setup.Common.FinishPage`
- `0x5855`: `pictureBoxLogo.AccessibleDescription`
- `0x5870`: `pictureBoxLogo.AccessibleName`
- `0x5a21`: `labelTitle.AccessibleDescription`
- `0x5a3c`: `labelTitle.AccessibleName`
- `0x5c17`: `labelDetails.AccessibleDescription`
- `0x5c32`: `labelDetails.AccessibleName`
- `0x5e0d`: `checkBoxRestart.AccessibleDescription`
- `0x5e28`: `checkBoxRestart.AccessibleName`
- `0x6054`: `labelInstructions.AccessibleDescription`
- `0x606f`: `labelInstructions.AccessibleName`
- `0x624a`: `linkLabelLogFile.AccessibleDescription`
- `0x6265`: `linkLabelLogFile.AccessibleName`
- `0x6280`: `linkLabelLogFile.Anchor`
- `0x629b`: `linkLabelLogFile.AutoSize`
- `0x62b6`: `linkLabelLogFile.Dock`
- `0x62d1`: `linkLabelLogFile.Enabled`
- `0x62ec`: `linkLabelLogFile.Font`
- `0x6307`: `linkLabelLogFile.Image`
- `0x6322`: `linkLabelLogFile.ImageAlign`
- `0x633d`: `linkLabelLogFile.ImageIndex`
- `0x6358`: `linkLabelLogFile.ImeMode`
- `0x6373`: `linkLabelLogFile.LinkArea`
- `0x638e`: `linkLabelLogFile.Location`
- `0x63a8`: `linkLabelLogFile`
- `0x63b9`: `linkLabelLogFile.RightToLeft`
- `0x63d4`: `linkLabelLogFile.Size`
- `0x63ef`: `linkLabelLogFile.TabIndex`
- `0x6416`: `linkLabelLogFile.Text`
- `0x6431`: `linkLabelLogFile.TextAlign`
- `0x644c`: `linkLabelLogFile.Visible`
- `0x647e`: `linkLabelPostInstallAction.AccessibleDescription`
- `0x6499`: `linkLabelPostInstallAction.AccessibleName`
- `0x64b4`: `linkLabelPostInstallAction.Anchor`
- `0x64cf`: `linkLabelPostInstallAction.AutoSize`
- `0x64ea`: `linkLabelPostInstallAction.Dock`
- `0x6505`: `linkLabelPostInstallAction.Enabled`
- `0x6520`: `linkLabelPostInstallAction.Font`
- `0x653b`: `linkLabelPostInstallAction.Image`
- `0x6556`: `linkLabelPostInstallAction.ImageAlign`
- `0x6571`: `linkLabelPostInstallAction.ImageIndex`
- `0x658c`: `linkLabelPostInstallAction.ImeMode`
- `0x65a7`: `linkLabelPostInstallAction.LinkArea`
- `0x65c2`: `linkLabelPostInstallAction.Location`
- `0x65dc`: `linkLabelPostInstallAction`
- `0x65ed`: `linkLabelPostInstallAction.RightToLeft`
- `0x6608`: `linkLabelPostInstallAction.Size`
- `0x6623`: `linkLabelPostInstallAction.TabIndex`
- `0x663e`: `linkLabelPostInstallAction.Text`
- `0x6659`: `linkLabelPostInstallAction.TextAlign`
- `0x6674`: `linkLabelPostInstallAction.Visible`
- `0x66a7`: `checkBoxLaunchApp.AccessibleDescription`
- `0x66c2`: `checkBoxLaunchApp.AccessibleName`

## pseudocode

```c

```

## disassembly

```asm
0x57c0  ldstr    aMicrosoftCrmSe_1// "Microsoft.Crm.Setup.Common.FinishPage"
0x57c5  ldtoken  Microsoft.Crm.Setup.Common.UI.FinishPage
0x57ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x57cf  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x57d4  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x57d9  stloc.0
0x57da  ldarg.0
0x57db  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0x57e0  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x57e5  ldarg.0
0x57e6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x57eb  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x57f0  ldarg.0
0x57f1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x57f6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelDetails
0x57fb  ldarg.0
0x57fc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x5801  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxRestart
0x5806  ldarg.0
0x5807  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x580c  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelInstructions
0x5811  ldarg.0
0x5812  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x5817  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.FinishPage::linkLabelLogFile
0x581c  ldarg.0
0x581d  newobj   instance void [System.Windows.Forms]System.Windows.Forms.LinkLabel::.ctor()
0x5822  stfld    class [System.Windows.Forms]System.Windows.Forms.LinkLabel Microsoft.Crm.Setup.Common.UI.FinishPage::linkLabelPostInstallAction
0x5827  ldarg.0
0x5828  newobj   instance void [System.Windows.Forms]System.Windows.Forms.CheckBox::.ctor()
0x582d  stfld    class [System.Windows.Forms]System.Windows.Forms.CheckBox Microsoft.Crm.Setup.Common.UI.FinishPage::checkBoxLaunchApp
0x5832  ldarg.0
0x5833  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x5838  ldarg.0
0x5839  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0x583e  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.FinishPage::finishPanel
0x5843  ldarg.0
0x5844  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0x5849  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.FinishPage::finishInfoPanel
0x584e  ldarg.0
0x584f  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x5854  ldloc.0
0x5855  ldstr    aPictureboxlogo// "pictureBoxLogo.AccessibleDescription"
0x585a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x585f  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x5864  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x5869  ldarg.0
0x586a  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x586f  ldloc.0
0x5870  ldstr    aPictureboxlogo_0// "pictureBoxLogo.AccessibleName"
0x5875  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x587a  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x587f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x5884  ldarg.0
0x5885  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x588a  ldloc.0
0x588b  ldstr    aPictureboxlogo_1// "pictureBoxLogo.Anchor"
0x5890  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5895  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0x589a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x589f  ldarg.0
0x58a0  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x58a5  ldloc.0
0x58a6  ldstr    aPictureboxlogo_2// "pictureBoxLogo.BackgroundImage"
0x58ab  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x58b0  castclass [System.Drawing]System.Drawing.Image
0x58b5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackgroundImage(class [System.Drawing]System.Drawing.Image)
0x58ba  ldarg.0
0x58bb  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x58c0  ldloc.0
0x58c1  ldstr    aPictureboxlogo_3// "pictureBoxLogo.Dock"
0x58c6  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x58cb  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0x58d0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x58d5  ldarg.0
0x58d6  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x58db  ldloc.0
0x58dc  ldstr    aPictureboxlogo_4// "pictureBoxLogo.Enabled"
0x58e1  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x58e6  unbox.any [mscorlib]System.Boolean
0x58eb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x58f0  ldarg.0
0x58f1  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x58f6  ldloc.0
0x58f7  ldstr    aPictureboxlogo_5// "pictureBoxLogo.Font"
0x58fc  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5901  castclass [System.Drawing]System.Drawing.Font
0x5906  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0x590b  ldarg.0
0x590c  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x5911  ldloc.0
0x5912  ldstr    aPictureboxlogo_6// "pictureBoxLogo.Image"
0x5917  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x591c  castclass [System.Drawing]System.Drawing.Image
0x5921  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_Image(class [System.Drawing]System.Drawing.Image)
0x5926  ldarg.0
0x5927  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x592c  ldloc.0
0x592d  ldstr    aPictureboxlogo_7// "pictureBoxLogo.ImeMode"
0x5932  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5937  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0x593c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0x5941  ldarg.0
0x5942  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x5947  ldloc.0
0x5948  ldstr    aPictureboxlogo_8// "pictureBoxLogo.Location"
0x594d  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5952  unbox.any [System.Drawing]System.Drawing.Point
0x5957  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x595c  ldarg.0
0x595d  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x5962  ldstr    aPictureboxlogo_9// "pictureBoxLogo"
0x5967  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x596c  ldarg.0
0x596d  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x5972  ldloc.0
0x5973  ldstr    aPictureboxlogo_10// "pictureBoxLogo.RightToLeft"
0x5978  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x597d  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0x5982  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0x5987  ldarg.0
0x5988  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x598d  ldloc.0
0x598e  ldstr    aPictureboxlogo_11// "pictureBoxLogo.Size"
0x5993  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5998  unbox.any [System.Drawing]System.Drawing.Size
0x599d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x59a2  ldarg.0
0x59a3  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x59a8  ldloc.0
0x59a9  ldstr    aPictureboxlogo_12// "pictureBoxLogo.SizeMode"
0x59ae  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x59b3  unbox.any [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode
0x59b8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_SizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode)
0x59bd  ldarg.0
0x59be  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x59c3  ldloc.0
0x59c4  ldstr    aPictureboxlogo_13// "pictureBoxLogo.TabIndex"
0x59c9  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x59ce  unbox.any [mscorlib]System.Int32
0x59d3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabIndex(int32)
0x59d8  ldarg.0
0x59d9  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x59de  ldc.i4.0
0x59df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0x59e4  ldarg.0
0x59e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x59ea  ldloc.0
0x59eb  ldstr    aPictureboxlogo_14// "pictureBoxLogo.Text"
0x59f0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x59f5  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x59fa  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x59ff  ldarg.0
0x5a00  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.FinishPage::pictureBoxLogo
0x5a05  ldloc.0
0x5a06  ldstr    aPictureboxlogo_15// "pictureBoxLogo.Visible"
0x5a0b  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5a10  unbox.any [mscorlib]System.Boolean
0x5a15  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x5a1a  ldarg.0
0x5a1b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5a20  ldloc.0
0x5a21  ldstr    aLabeltitleAcce// "labelTitle.AccessibleDescription"
0x5a26  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x5a2b  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x5a30  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x5a35  ldarg.0
0x5a36  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5a3b  ldloc.0
0x5a3c  ldstr    aLabeltitleAcce_0// "labelTitle.AccessibleName"
0x5a41  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x5a46  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x5a4b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x5a50  ldarg.0
0x5a51  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5a56  ldloc.0
0x5a57  ldstr    aLabeltitleAnch// "labelTitle.Anchor"
0x5a5c  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5a61  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0x5a66  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x5a6b  ldarg.0
0x5a6c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5a71  ldloc.0
0x5a72  ldstr    aLabeltitleAuto// "labelTitle.AutoSize"
0x5a77  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5a7c  unbox.any [mscorlib]System.Boolean
0x5a81  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x5a86  ldarg.0
0x5a87  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5a8c  ldloc.0
0x5a8d  ldstr    aLabeltitleDock// "labelTitle.Dock"
0x5a92  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5a97  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0x5a9c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x5aa1  ldarg.0
0x5aa2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5aa7  ldloc.0
0x5aa8  ldstr    aLabeltitleEnab// "labelTitle.Enabled"
0x5aad  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5ab2  unbox.any [mscorlib]System.Boolean
0x5ab7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x5abc  ldarg.0
0x5abd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5ac2  ldloc.0
0x5ac3  ldstr    aLabeltitleFont// "labelTitle.Font"
0x5ac8  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5acd  castclass [System.Drawing]System.Drawing.Font
0x5ad2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0x5ad7  ldarg.0
0x5ad8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5add  ldloc.0
0x5ade  ldstr    aLabeltitleImag// "labelTitle.Image"
0x5ae3  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5ae8  castclass [System.Drawing]System.Drawing.Image
0x5aed  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_Image(class [System.Drawing]System.Drawing.Image)
0x5af2  ldarg.0
0x5af3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5af8  ldloc.0
0x5af9  ldstr    aLabeltitleImag_0// "labelTitle.ImageAlign"
0x5afe  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5b03  unbox.any [System.Drawing]System.Drawing.ContentAlignment
0x5b08  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImageAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0x5b0d  ldarg.0
0x5b0e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5b13  ldloc.0
0x5b14  ldstr    aLabeltitleImag_1// "labelTitle.ImageIndex"
0x5b19  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5b1e  unbox.any [mscorlib]System.Int32
0x5b23  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImageIndex(int32)
0x5b28  ldarg.0
0x5b29  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5b2e  ldloc.0
0x5b2f  ldstr    aLabeltitleImem// "labelTitle.ImeMode"
0x5b34  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5b39  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0x5b3e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0x5b43  ldarg.0
0x5b44  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5b49  ldloc.0
0x5b4a  ldstr    aLabeltitleLoca// "labelTitle.Location"
0x5b4f  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5b54  unbox.any [System.Drawing]System.Drawing.Point
0x5b59  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x5b5e  ldarg.0
0x5b5f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5b64  ldstr    aLabeltitle// "labelTitle"
0x5b69  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x5b6e  ldarg.0
0x5b6f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5b74  ldloc.0
0x5b75  ldstr    aLabeltitleRigh// "labelTitle.RightToLeft"
0x5b7a  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5b7f  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0x5b84  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0x5b89  ldarg.0
0x5b8a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5b8f  ldloc.0
0x5b90  ldstr    aLabeltitleSize// "labelTitle.Size"
0x5b95  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5b9a  unbox.any [System.Drawing]System.Drawing.Size
0x5b9f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x5ba4  ldarg.0
0x5ba5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5baa  ldloc.0
0x5bab  ldstr    aLabeltitleTabi// "labelTitle.TabIndex"
0x5bb0  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5bb5  unbox.any [mscorlib]System.Int32
0x5bba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x5bbf  ldarg.0
0x5bc0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5bc5  ldloc.0
0x5bc6  ldstr    aLabeltitleText// "labelTitle.Text"
0x5bcb  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x5bd0  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x5bd5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x5bda  ldarg.0
0x5bdb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5be0  ldloc.0
0x5be1  ldstr    aLabeltitleText_0// "labelTitle.TextAlign"
0x5be6  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5beb  unbox.any [System.Drawing]System.Drawing.ContentAlignment
0x5bf0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0x5bf5  ldarg.0
0x5bf6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelTitle
0x5bfb  ldloc.0
0x5bfc  ldstr    aLabeltitleVisi// "labelTitle.Visible"
0x5c01  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x5c06  unbox.any [mscorlib]System.Boolean
0x5c0b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x5c10  ldarg.0
0x5c11  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelDetails
0x5c16  ldloc.0
0x5c17  ldstr    aLabeldetailsAc// "labelDetails.AccessibleDescription"
0x5c1c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x5c21  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x5c26  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x5c2b  ldarg.0
0x5c2c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FinishPage::labelDetails
0x5c31  ldloc.0
0x5c32  ldstr    aLabeldetailsAc_0// "labelDetails.AccessibleName"
0x5c37  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
  ... truncated ...
```
