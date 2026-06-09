# Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::InitializeComponent

- ea: `0x7070`
- end: `0x7f7a`
- name: `Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::InitializeComponent`
- size: `3850`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7020`

## string_xrefs

- `0x7d56`: `$this.AccessibleDescription`
- `0x7d6c`: `$this.AccessibleName`
- `0x70e4`: `labelDetails.AccessibleDescription`
- `0x70ff`: `labelDetails.AccessibleName`
- `0x7070`: `Microsoft.Crm.Setup.Common.FileLocatorDialog`
- `0x72da`: `textBoxLocation.AccessibleDescription`
- `0x72f5`: `textBoxLocation.AccessibleName`
- `0x7521`: `buttonBrowse.AccessibleDescription`
- `0x753c`: `buttonBrowse.AccessibleName`
- `0x7749`: `buttonCancel.AccessibleDescription`
- `0x7764`: `buttonCancel.AccessibleName`
- `0x7966`: `buttonOK.AccessibleDescription`
- `0x7981`: `buttonOK.AccessibleName`
- `0x7b83`: `groupBoxSplitter.AccessibleDescription`
- `0x7b9e`: `groupBoxSplitter.AccessibleName`
- `0x7d19`: `openFileDialog.Filter`
- `0x7d34`: `openFileDialog.Title`
- `0x7ef4`: `$this.MaximumSize`
- `0x7f11`: `$this.MinimumSize`

## pseudocode

```c

```

## disassembly

```asm
0x7070  ldstr    aMicrosoftCrmSe_2// "Microsoft.Crm.Setup.Common.FileLocatorD"...
0x7075  ldtoken  Microsoft.Crm.Setup.Common.UI.FileLocatorDialog
0x707a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x707f  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x7084  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x7089  stloc.0
0x708a  ldarg.0
0x708b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0x7090  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x7095  ldarg.0
0x7096  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0x709b  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x70a0  ldarg.0
0x70a1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x70a6  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::buttonBrowse
0x70ab  ldarg.0
0x70ac  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x70b1  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::buttonCancel
0x70b6  ldarg.0
0x70b7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0x70bc  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::buttonOK
0x70c1  ldarg.0
0x70c2  newobj   instance void [System.Windows.Forms]System.Windows.Forms.GroupBox::.ctor()
0x70c7  stfld    class [System.Windows.Forms]System.Windows.Forms.GroupBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::groupBoxSplitter
0x70cc  ldarg.0
0x70cd  newobj   instance void [System.Windows.Forms]System.Windows.Forms.OpenFileDialog::.ctor()
0x70d2  stfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::openFileDialog
0x70d7  ldarg.0
0x70d8  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0x70dd  ldarg.0
0x70de  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x70e3  ldloc.0
0x70e4  ldstr    aLabeldetailsAc// "labelDetails.AccessibleDescription"
0x70e9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x70ee  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x70f3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x70f8  ldarg.0
0x70f9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x70fe  ldloc.0
0x70ff  ldstr    aLabeldetailsAc_0// "labelDetails.AccessibleName"
0x7104  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x7109  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x710e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x7113  ldarg.0
0x7114  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x7119  ldloc.0
0x711a  ldstr    aLabeldetailsAn// "labelDetails.Anchor"
0x711f  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7124  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0x7129  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x712e  ldarg.0
0x712f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x7134  ldloc.0
0x7135  ldstr    aLabeldetailsAu// "labelDetails.AutoSize"
0x713a  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x713f  unbox.any [mscorlib]System.Boolean
0x7144  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x7149  ldarg.0
0x714a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x714f  ldloc.0
0x7150  ldstr    aLabeldetailsDo// "labelDetails.Dock"
0x7155  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x715a  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0x715f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x7164  ldarg.0
0x7165  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x716a  ldloc.0
0x716b  ldstr    aLabeldetailsEn// "labelDetails.Enabled"
0x7170  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7175  unbox.any [mscorlib]System.Boolean
0x717a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x717f  ldarg.0
0x7180  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x7185  ldloc.0
0x7186  ldstr    aLabeldetailsFo// "labelDetails.Font"
0x718b  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7190  castclass [System.Drawing]System.Drawing.Font
0x7195  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0x719a  ldarg.0
0x719b  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x71a0  ldloc.0
0x71a1  ldstr    aLabeldetailsIm// "labelDetails.Image"
0x71a6  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x71ab  castclass [System.Drawing]System.Drawing.Image
0x71b0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_Image(class [System.Drawing]System.Drawing.Image)
0x71b5  ldarg.0
0x71b6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x71bb  ldloc.0
0x71bc  ldstr    aLabeldetailsIm_0// "labelDetails.ImageAlign"
0x71c1  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x71c6  unbox.any [System.Drawing]System.Drawing.ContentAlignment
0x71cb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImageAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0x71d0  ldarg.0
0x71d1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x71d6  ldloc.0
0x71d7  ldstr    aLabeldetailsIm_1// "labelDetails.ImageIndex"
0x71dc  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x71e1  unbox.any [mscorlib]System.Int32
0x71e6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImageIndex(int32)
0x71eb  ldarg.0
0x71ec  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x71f1  ldloc.0
0x71f2  ldstr    aLabeldetailsIm_2// "labelDetails.ImeMode"
0x71f7  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x71fc  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0x7201  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0x7206  ldarg.0
0x7207  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x720c  ldloc.0
0x720d  ldstr    aLabeldetailsLo// "labelDetails.Location"
0x7212  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7217  unbox.any [System.Drawing]System.Drawing.Point
0x721c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x7221  ldarg.0
0x7222  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x7227  ldstr    aLabeldetails// "labelDetails"
0x722c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7231  ldarg.0
0x7232  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x7237  ldloc.0
0x7238  ldstr    aLabeldetailsRi// "labelDetails.RightToLeft"
0x723d  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7242  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0x7247  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0x724c  ldarg.0
0x724d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x7252  ldloc.0
0x7253  ldstr    aLabeldetailsSi// "labelDetails.Size"
0x7258  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x725d  unbox.any [System.Drawing]System.Drawing.Size
0x7262  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x7267  ldarg.0
0x7268  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x726d  ldloc.0
0x726e  ldstr    aLabeldetailsTa// "labelDetails.TabIndex"
0x7273  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7278  unbox.any [mscorlib]System.Int32
0x727d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x7282  ldarg.0
0x7283  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x7288  ldloc.0
0x7289  ldstr    aLabeldetailsTe// "labelDetails.Text"
0x728e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x7293  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x7298  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x729d  ldarg.0
0x729e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x72a3  ldloc.0
0x72a4  ldstr    aLabeldetailsTe_0// "labelDetails.TextAlign"
0x72a9  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x72ae  unbox.any [System.Drawing]System.Drawing.ContentAlignment
0x72b3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0x72b8  ldarg.0
0x72b9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::labelDetails
0x72be  ldloc.0
0x72bf  ldstr    aLabeldetailsVi// "labelDetails.Visible"
0x72c4  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x72c9  unbox.any [mscorlib]System.Boolean
0x72ce  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0x72d3  ldarg.0
0x72d4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x72d9  ldloc.0
0x72da  ldstr    aTextboxlocatio// "textBoxLocation.AccessibleDescription"
0x72df  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x72e4  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x72e9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x72ee  ldarg.0
0x72ef  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x72f4  ldloc.0
0x72f5  ldstr    aTextboxlocatio_0// "textBoxLocation.AccessibleName"
0x72fa  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x72ff  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x7304  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x7309  ldarg.0
0x730a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x730f  ldloc.0
0x7310  ldstr    aTextboxlocatio_1// "textBoxLocation.Anchor"
0x7315  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x731a  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0x731f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0x7324  ldarg.0
0x7325  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x732a  ldloc.0
0x732b  ldstr    aTextboxlocatio_2// "textBoxLocation.AutoSize"
0x7330  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7335  unbox.any [mscorlib]System.Boolean
0x733a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0x733f  ldarg.0
0x7340  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x7345  ldloc.0
0x7346  ldstr    aTextboxlocatio_3// "textBoxLocation.BackgroundImage"
0x734b  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7350  castclass [System.Drawing]System.Drawing.Image
0x7355  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackgroundImage(class [System.Drawing]System.Drawing.Image)
0x735a  ldarg.0
0x735b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x7360  ldloc.0
0x7361  ldstr    aTextboxlocatio_4// "textBoxLocation.Dock"
0x7366  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x736b  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0x7370  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0x7375  ldarg.0
0x7376  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x737b  ldloc.0
0x737c  ldstr    aTextboxlocatio_5// "textBoxLocation.Enabled"
0x7381  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7386  unbox.any [mscorlib]System.Boolean
0x738b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x7390  ldarg.0
0x7391  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x7396  ldloc.0
0x7397  ldstr    aTextboxlocatio_6// "textBoxLocation.Font"
0x739c  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x73a1  castclass [System.Drawing]System.Drawing.Font
0x73a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0x73ab  ldarg.0
0x73ac  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x73b1  ldloc.0
0x73b2  ldstr    aTextboxlocatio_7// "textBoxLocation.ImeMode"
0x73b7  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x73bc  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0x73c1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0x73c6  ldarg.0
0x73c7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x73cc  ldloc.0
0x73cd  ldstr    aTextboxlocatio_8// "textBoxLocation.Location"
0x73d2  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x73d7  unbox.any [System.Drawing]System.Drawing.Point
0x73dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x73e1  ldarg.0
0x73e2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x73e7  ldloc.0
0x73e8  ldstr    aTextboxlocatio_9// "textBoxLocation.MaxLength"
0x73ed  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x73f2  unbox.any [mscorlib]System.Int32
0x73f7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_MaxLength(int32)
0x73fc  ldarg.0
0x73fd  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x7402  ldloc.0
0x7403  ldstr    aTextboxlocatio_10// "textBoxLocation.Multiline"
0x7408  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x740d  unbox.any [mscorlib]System.Boolean
0x7412  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_Multiline(bool)
0x7417  ldarg.0
0x7418  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x741d  ldstr    aTextboxlocatio_11// "textBoxLocation"
0x7422  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x7427  ldarg.0
0x7428  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x742d  ldloc.0
0x742e  ldstr    aTextboxlocatio_12// "textBoxLocation.PasswordChar"
0x7433  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7438  unbox.any [mscorlib]System.Char
0x743d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_PasswordChar(char)
0x7442  ldarg.0
0x7443  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x7448  ldloc.0
0x7449  ldstr    aTextboxlocatio_13// "textBoxLocation.RightToLeft"
0x744e  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7453  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0x7458  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0x745d  ldarg.0
0x745e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x7463  ldloc.0
0x7464  ldstr    aTextboxlocatio_14// "textBoxLocation.ScrollBars"
0x7469  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x746e  unbox.any [System.Windows.Forms]System.Windows.Forms.ScrollBars
0x7473  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_ScrollBars(valuetype [System.Windows.Forms]System.Windows.Forms.ScrollBars)
0x7478  ldarg.0
0x7479  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x747e  ldloc.0
0x747f  ldstr    aTextboxlocatio_15// "textBoxLocation.Size"
0x7484  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x7489  unbox.any [System.Drawing]System.Drawing.Size
0x748e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x7493  ldarg.0
0x7494  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x7499  ldloc.0
0x749a  ldstr    aTextboxlocatio_16// "textBoxLocation.TabIndex"
0x749f  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x74a4  unbox.any [mscorlib]System.Int32
0x74a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0x74ae  ldarg.0
0x74af  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x74b4  ldloc.0
0x74b5  ldstr    aTextboxlocatio_17// "textBoxLocation.Text"
0x74ba  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x74bf  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x74c4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x74c9  ldarg.0
0x74ca  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x74cf  ldloc.0
0x74d0  ldstr    aTextboxlocatio_18// "textBoxLocation.TextAlign"
0x74d5  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x74da  unbox.any [System.Windows.Forms]System.Windows.Forms.HorizontalAlignment
0x74df  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_TextAlign(valuetype [System.Windows.Forms]System.Windows.Forms.HorizontalAlignment)
0x74e4  ldarg.0
0x74e5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::textBoxLocation
0x74ea  ldloc.0
0x74eb  ldstr    aTextboxlocatio_19// "textBoxLocation.Visible"
  ... truncated ...
```
