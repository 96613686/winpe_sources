# Microsoft.Crm.Setup.Common.UI.PathSelectControl::InitializeComponent

- ea: `0xa580`
- end: `0xae23`
- name: `Microsoft.Crm.Setup.Common.UI.PathSelectControl::InitializeComponent`
- size: `2211`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa460`

## callees

- `0xa580`

## string_xrefs

- `0xacae`: `$this.AccessibleDescription`
- `0xacc4`: `$this.AccessibleName`
- `0xa5d3`: `buttonBrowse.AccessibleDescription`
- `0xa5ee`: `buttonBrowse.AccessibleName`
- `0xa580`: `Microsoft.Crm.Setup.Common.PathSelectControl`
- `0xa7e3`: `Microsoft.Crm.Setup.Common.UI.PathSelectControl`
- `0xadf8`: `Microsoft.Crm.Setup.Common.UI.PathSelectControl`
- `0xa812`: `textPath.AccessibleDescription`
- `0xa82d`: `textPath.AccessibleName`
- `0xa848`: `textPath.Anchor`
- `0xa863`: `textPath.AutoSize`
- `0xa87e`: `textPath.BackgroundImage`
- `0xa899`: `textPath.Dock`
- `0xa8b4`: `textPath.Enabled`
- `0xa8cf`: `textPath.Font`
- `0xa8ea`: `textPath.ImeMode`
- `0xa905`: `textPath.Location`
- `0xa920`: `textPath.MaxLength`
- `0xa93b`: `textPath.Multiline`
- `0xa955`: `textPath`
- `0xa966`: `textPath.PasswordChar`
- `0xa981`: `textPath.RightToLeft`
- `0xa99c`: `textPath.ScrollBars`
- `0xa9b7`: `textPath.Size`
- `0xa9d2`: `textPath.TabIndex`
- `0xa9ed`: `textPath.Text`
- `0xaa08`: `textPath.TextAlign`
- `0xaa23`: `textPath.Visible`
- `0xaa3e`: `textPath.WordWrap`
- `0xaa87`: `labelPath.AccessibleDescription`
- `0xaaa2`: `labelPath.AccessibleName`
- `0xaabd`: `labelPath.Anchor`
- `0xaad8`: `labelPath.AutoSize`
- `0xaaf3`: `labelPath.Dock`
- `0xab0e`: `labelPath.Enabled`
- `0xab29`: `labelPath.Font`
- `0xab44`: `labelPath.Image`
- `0xab5f`: `labelPath.ImageAlign`
- `0xab7a`: `labelPath.ImageIndex`
- `0xab95`: `labelPath.ImeMode`
- `0xabb0`: `labelPath.Location`
- `0xabca`: `labelPath`
- `0xabdb`: `labelPath.RightToLeft`
- `0xabf6`: `labelPath.Size`
- `0xac11`: `labelPath.TabIndex`
- `0xac2c`: `labelPath.Text`
- `0xac47`: `labelPath.TextAlign`
- `0xac62`: `labelPath.Visible`
- `0xac98`: `folderBrowserDialog.SelectedPath`
- `0xadbc`: `PathSelectControl`

## pseudocode

```c

```

## disassembly

```asm
0xa580  ldstr    aMicrosoftCrmSe_4// "Microsoft.Crm.Setup.Common.PathSelectCo"...
0xa585  ldtoken  Microsoft.Crm.Setup.Common.UI.PathSelectControl
0xa58a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa58f  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xa594  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0xa599  stloc.0
0xa59a  ldarg.0
0xa59b  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xa5a0  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa5a5  ldarg.0
0xa5a6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xa5ab  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa5b0  ldarg.0
0xa5b1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xa5b6  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSelectControl::labelPath
0xa5bb  ldarg.0
0xa5bc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FolderBrowserDialog::.ctor()
0xa5c1  stfld    class [System.Windows.Forms]System.Windows.Forms.FolderBrowserDialog Microsoft.Crm.Setup.Common.UI.PathSelectControl::folderBrowserDialog
0xa5c6  ldarg.0
0xa5c7  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xa5cc  ldarg.0
0xa5cd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa5d2  ldloc.0
0xa5d3  ldstr    aButtonbrowseAc// "buttonBrowse.AccessibleDescription"
0xa5d8  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xa5dd  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa5e2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xa5e7  ldarg.0
0xa5e8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa5ed  ldloc.0
0xa5ee  ldstr    aButtonbrowseAc_0// "buttonBrowse.AccessibleName"
0xa5f3  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xa5f8  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa5fd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xa602  ldarg.0
0xa603  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa608  ldloc.0
0xa609  ldstr    aButtonbrowseAn// "buttonBrowse.Anchor"
0xa60e  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa613  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0xa618  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xa61d  ldarg.0
0xa61e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa623  ldloc.0
0xa624  ldstr    aButtonbrowseBa// "buttonBrowse.BackgroundImage"
0xa629  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa62e  castclass [System.Drawing]System.Drawing.Image
0xa633  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackgroundImage(class [System.Drawing]System.Drawing.Image)
0xa638  ldarg.0
0xa639  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa63e  ldloc.0
0xa63f  ldstr    aButtonbrowseDo// "buttonBrowse.Dock"
0xa644  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa649  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0xa64e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xa653  ldarg.0
0xa654  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa659  ldloc.0
0xa65a  ldstr    aButtonbrowseEn// "buttonBrowse.Enabled"
0xa65f  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa664  unbox.any [mscorlib]System.Boolean
0xa669  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xa66e  ldarg.0
0xa66f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa674  ldloc.0
0xa675  ldstr    aButtonbrowseFl// "buttonBrowse.FlatStyle"
0xa67a  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa67f  unbox.any [System.Windows.Forms]System.Windows.Forms.FlatStyle
0xa684  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0xa689  ldarg.0
0xa68a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa68f  ldloc.0
0xa690  ldstr    aButtonbrowseFo// "buttonBrowse.Font"
0xa695  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa69a  castclass [System.Drawing]System.Drawing.Font
0xa69f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0xa6a4  ldarg.0
0xa6a5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa6aa  ldloc.0
0xa6ab  ldstr    aButtonbrowseIm// "buttonBrowse.Image"
0xa6b0  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa6b5  castclass [System.Drawing]System.Drawing.Image
0xa6ba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_Image(class [System.Drawing]System.Drawing.Image)
0xa6bf  ldarg.0
0xa6c0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa6c5  ldloc.0
0xa6c6  ldstr    aButtonbrowseIm_0// "buttonBrowse.ImageAlign"
0xa6cb  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa6d0  unbox.any [System.Drawing]System.Drawing.ContentAlignment
0xa6d5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_ImageAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xa6da  ldarg.0
0xa6db  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa6e0  ldloc.0
0xa6e1  ldstr    aButtonbrowseIm_1// "buttonBrowse.ImageIndex"
0xa6e6  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa6eb  unbox.any [mscorlib]System.Int32
0xa6f0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_ImageIndex(int32)
0xa6f5  ldarg.0
0xa6f6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa6fb  ldloc.0
0xa6fc  ldstr    aButtonbrowseIm_2// "buttonBrowse.ImeMode"
0xa701  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa706  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0xa70b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xa710  ldarg.0
0xa711  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa716  ldloc.0
0xa717  ldstr    aButtonbrowseLo// "buttonBrowse.Location"
0xa71c  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa721  unbox.any [System.Drawing]System.Drawing.Point
0xa726  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xa72b  ldarg.0
0xa72c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa731  ldstr    aButtonbrowse// "buttonBrowse"
0xa736  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa73b  ldarg.0
0xa73c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa741  ldloc.0
0xa742  ldstr    aButtonbrowseRi// "buttonBrowse.RightToLeft"
0xa747  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa74c  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0xa751  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0xa756  ldarg.0
0xa757  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa75c  ldloc.0
0xa75d  ldstr    aButtonbrowseSi// "buttonBrowse.Size"
0xa762  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa767  unbox.any [System.Drawing]System.Drawing.Size
0xa76c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xa771  ldarg.0
0xa772  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa777  ldloc.0
0xa778  ldstr    aButtonbrowseTa// "buttonBrowse.TabIndex"
0xa77d  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa782  unbox.any [mscorlib]System.Int32
0xa787  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xa78c  ldarg.0
0xa78d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa792  ldloc.0
0xa793  ldstr    aButtonbrowseTe// "buttonBrowse.Text"
0xa798  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xa79d  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa7a2  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xa7a7  ldarg.0
0xa7a8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa7ad  ldloc.0
0xa7ae  ldstr    aButtonbrowseTe_0// "buttonBrowse.TextAlign"
0xa7b3  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa7b8  unbox.any [System.Drawing]System.Drawing.ContentAlignment
0xa7bd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ButtonBase::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xa7c2  ldarg.0
0xa7c3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa7c8  ldloc.0
0xa7c9  ldstr    aButtonbrowseVi// "buttonBrowse.Visible"
0xa7ce  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa7d3  unbox.any [mscorlib]System.Boolean
0xa7d8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xa7dd  ldarg.0
0xa7de  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xa7e3  ldstr    aMicrosoftCrmSe_5// "Microsoft.Crm.Setup.Common.UI.PathSelec"...
0xa7e8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0xa7ed  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xa7f2  brfalse.s loc_A80B
0xa7f4  ldarg.0
0xa7f5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.PathSelectControl::buttonBrowse
0xa7fa  ldarg.0
0xa7fb  ldftn    instance void Microsoft.Crm.Setup.Common.UI.PathSelectControl::ButtonBrowse_Click(object sender, class [mscorlib]System.EventArgs e)
0xa801  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xa806  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::add_Click(class [mscorlib]System.EventHandler)
0xa80b  ldarg.0
0xa80c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa811  ldloc.0
0xa812  ldstr    aTextpathAccess// "textPath.AccessibleDescription"
0xa817  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xa81c  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa821  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xa826  ldarg.0
0xa827  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa82c  ldloc.0
0xa82d  ldstr    aTextpathAccess_0// "textPath.AccessibleName"
0xa832  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xa837  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa83c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xa841  ldarg.0
0xa842  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa847  ldloc.0
0xa848  ldstr    aTextpathAnchor// "textPath.Anchor"
0xa84d  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa852  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0xa857  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xa85c  ldarg.0
0xa85d  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa862  ldloc.0
0xa863  ldstr    aTextpathAutosi// "textPath.AutoSize"
0xa868  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa86d  unbox.any [mscorlib]System.Boolean
0xa872  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xa877  ldarg.0
0xa878  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa87d  ldloc.0
0xa87e  ldstr    aTextpathBackgr// "textPath.BackgroundImage"
0xa883  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa888  castclass [System.Drawing]System.Drawing.Image
0xa88d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackgroundImage(class [System.Drawing]System.Drawing.Image)
0xa892  ldarg.0
0xa893  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa898  ldloc.0
0xa899  ldstr    aTextpathDock// "textPath.Dock"
0xa89e  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa8a3  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0xa8a8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xa8ad  ldarg.0
0xa8ae  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa8b3  ldloc.0
0xa8b4  ldstr    aTextpathEnable// "textPath.Enabled"
0xa8b9  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa8be  unbox.any [mscorlib]System.Boolean
0xa8c3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xa8c8  ldarg.0
0xa8c9  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa8ce  ldloc.0
0xa8cf  ldstr    aTextpathFont// "textPath.Font"
0xa8d4  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa8d9  castclass [System.Drawing]System.Drawing.Font
0xa8de  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0xa8e3  ldarg.0
0xa8e4  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa8e9  ldloc.0
0xa8ea  ldstr    aTextpathImemod// "textPath.ImeMode"
0xa8ef  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa8f4  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0xa8f9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xa8fe  ldarg.0
0xa8ff  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa904  ldloc.0
0xa905  ldstr    aTextpathLocati// "textPath.Location"
0xa90a  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa90f  unbox.any [System.Drawing]System.Drawing.Point
0xa914  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xa919  ldarg.0
0xa91a  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa91f  ldloc.0
0xa920  ldstr    aTextpathMaxlen// "textPath.MaxLength"
0xa925  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa92a  unbox.any [mscorlib]System.Int32
0xa92f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_MaxLength(int32)
0xa934  ldarg.0
0xa935  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa93a  ldloc.0
0xa93b  ldstr    aTextpathMultil// "textPath.Multiline"
0xa940  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa945  unbox.any [mscorlib]System.Boolean
0xa94a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_Multiline(bool)
0xa94f  ldarg.0
0xa950  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa955  ldstr    aTextpath// "textPath"
0xa95a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xa95f  ldarg.0
0xa960  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa965  ldloc.0
0xa966  ldstr    aTextpathPasswo// "textPath.PasswordChar"
0xa96b  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa970  unbox.any [mscorlib]System.Char
0xa975  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_PasswordChar(char)
0xa97a  ldarg.0
0xa97b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa980  ldloc.0
0xa981  ldstr    aTextpathRightt// "textPath.RightToLeft"
0xa986  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa98b  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0xa990  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0xa995  ldarg.0
0xa996  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa99b  ldloc.0
0xa99c  ldstr    aTextpathScroll// "textPath.ScrollBars"
0xa9a1  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa9a6  unbox.any [System.Windows.Forms]System.Windows.Forms.ScrollBars
0xa9ab  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_ScrollBars(valuetype [System.Windows.Forms]System.Windows.Forms.ScrollBars)
0xa9b0  ldarg.0
0xa9b1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa9b6  ldloc.0
0xa9b7  ldstr    aTextpathSize// "textPath.Size"
0xa9bc  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa9c1  unbox.any [System.Drawing]System.Drawing.Size
0xa9c6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xa9cb  ldarg.0
0xa9cc  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa9d1  ldloc.0
0xa9d2  ldstr    aTextpathTabind// "textPath.TabIndex"
0xa9d7  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xa9dc  unbox.any [mscorlib]System.Int32
0xa9e1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xa9e6  ldarg.0
0xa9e7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.PathSelectControl::textPath
0xa9ec  ldloc.0
0xa9ed  ldstr    aTextpathText// "textPath.Text"
0xa9f2  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xa9f7  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xa9fc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xaa01  ldarg.0
  ... truncated ...
```
