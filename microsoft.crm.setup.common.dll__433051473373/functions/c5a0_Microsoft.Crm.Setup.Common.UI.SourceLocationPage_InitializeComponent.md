# Microsoft.Crm.Setup.Common.UI.SourceLocationPage::InitializeComponent

- ea: `0xc5a0`
- end: `0xceb0`
- name: `Microsoft.Crm.Setup.Common.UI.SourceLocationPage::InitializeComponent`
- size: `2320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc550`

## callees

- `0x10ac0`
- `0x10be0`
- `0x10fc0`
- `0x10fe0`
- `0x111c0`

## string_xrefs

- `0xcd25`: `$this.AccessibleDescription`
- `0xcd3b`: `$this.AccessibleName`
- `0xca5e`: `buttonBrowse.AccessibleDescription`
- `0xca79`: `buttonBrowse.AccessibleName`
- `0xcca1`: `folderBrowserDialog.SelectedPath`
- `0xc5a0`: `Microsoft.Crm.Setup.Common.SourceLocationPage`
- `0xc5fe`: `labelSourceFolder.AccessibleDescription`
- `0xc619`: `labelSourceFolder.AccessibleName`
- `0xc800`: `textBoxSourceFolder.AccessibleDescription`
- `0xc81b`: `textBoxSourceFolder.AccessibleName`
- `0xcce3`: `sourcePanel.AccessibleName`

## pseudocode

```c

```

## disassembly

```asm
0xc5a0  ldstr    aMicrosoftCrmSe_6// "Microsoft.Crm.Setup.Common.SourceLocati"...
0xc5a5  ldtoken  Microsoft.Crm.Setup.Common.UI.SourceLocationPage
0xc5aa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xc5af  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xc5b4  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0xc5b9  stloc.0
0xc5ba  ldarg.0
0xc5bb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xc5c0  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc5c5  ldarg.0
0xc5c6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.TextBox::.ctor()
0xc5cb  stfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc5d0  ldarg.0
0xc5d1  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Button::.ctor()
0xc5d6  stfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.SourceLocationPage::buttonBrowse
0xc5db  ldarg.0
0xc5dc  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FolderBrowserDialog::.ctor()
0xc5e1  stfld    class [System.Windows.Forms]System.Windows.Forms.FolderBrowserDialog Microsoft.Crm.Setup.Common.UI.SourceLocationPage::folderBrowserDialog
0xc5e6  ldarg.0
0xc5e7  newobj   instance void [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel::.ctor()
0xc5ec  stfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.SourceLocationPage::sourcePanel
0xc5f1  ldarg.0
0xc5f2  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xc5f7  ldarg.0
0xc5f8  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc5fd  ldloc.0
0xc5fe  ldstr    aLabelsourcefol// "labelSourceFolder.AccessibleDescription"
0xc603  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xc608  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xc60d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xc612  ldarg.0
0xc613  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc618  ldloc.0
0xc619  ldstr    aLabelsourcefol_0// "labelSourceFolder.AccessibleName"
0xc61e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xc623  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xc628  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xc62d  ldarg.0
0xc62e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc633  ldloc.0
0xc634  ldstr    aLabelsourcefol_1// "labelSourceFolder.Anchor"
0xc639  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc63e  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0xc643  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xc648  ldarg.0
0xc649  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc64e  ldloc.0
0xc64f  ldstr    aLabelsourcefol_2// "labelSourceFolder.AutoSize"
0xc654  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc659  unbox.any [mscorlib]System.Boolean
0xc65e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xc663  ldarg.0
0xc664  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc669  ldloc.0
0xc66a  ldstr    aLabelsourcefol_3// "labelSourceFolder.Dock"
0xc66f  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc674  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0xc679  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xc67e  ldarg.0
0xc67f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc684  ldloc.0
0xc685  ldstr    aLabelsourcefol_4// "labelSourceFolder.Enabled"
0xc68a  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc68f  unbox.any [mscorlib]System.Boolean
0xc694  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xc699  ldarg.0
0xc69a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc69f  ldc.i4.3
0xc6a0  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_FlatStyle(valuetype [System.Windows.Forms]System.Windows.Forms.FlatStyle)
0xc6a5  ldarg.0
0xc6a6  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc6ab  ldloc.0
0xc6ac  ldstr    aLabelsourcefol_5// "labelSourceFolder.Font"
0xc6b1  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc6b6  castclass [System.Drawing]System.Drawing.Font
0xc6bb  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0xc6c0  ldarg.0
0xc6c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc6c6  ldloc.0
0xc6c7  ldstr    aLabelsourcefol_6// "labelSourceFolder.Image"
0xc6cc  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc6d1  castclass [System.Drawing]System.Drawing.Image
0xc6d6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_Image(class [System.Drawing]System.Drawing.Image)
0xc6db  ldarg.0
0xc6dc  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc6e1  ldloc.0
0xc6e2  ldstr    aLabelsourcefol_7// "labelSourceFolder.ImageAlign"
0xc6e7  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc6ec  unbox.any [System.Drawing]System.Drawing.ContentAlignment
0xc6f1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImageAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xc6f6  ldarg.0
0xc6f7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc6fc  ldloc.0
0xc6fd  ldstr    aLabelsourcefol_8// "labelSourceFolder.ImageIndex"
0xc702  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc707  unbox.any [mscorlib]System.Int32
0xc70c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImageIndex(int32)
0xc711  ldarg.0
0xc712  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc717  ldloc.0
0xc718  ldstr    aLabelsourcefol_9// "labelSourceFolder.ImeMode"
0xc71d  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc722  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0xc727  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xc72c  ldarg.0
0xc72d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc732  ldloc.0
0xc733  ldstr    aLabelsourcefol_10// "labelSourceFolder.Location"
0xc738  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc73d  unbox.any [System.Drawing]System.Drawing.Point
0xc742  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xc747  ldarg.0
0xc748  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc74d  ldstr    aLabelsourcefol_11// "labelSourceFolder"
0xc752  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xc757  ldarg.0
0xc758  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc75d  ldloc.0
0xc75e  ldstr    aLabelsourcefol_12// "labelSourceFolder.RightToLeft"
0xc763  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc768  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0xc76d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0xc772  ldarg.0
0xc773  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc778  ldloc.0
0xc779  ldstr    aLabelsourcefol_13// "labelSourceFolder.Size"
0xc77e  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc783  unbox.any [System.Drawing]System.Drawing.Size
0xc788  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xc78d  ldarg.0
0xc78e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc793  ldloc.0
0xc794  ldstr    aLabelsourcefol_14// "labelSourceFolder.TabIndex"
0xc799  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc79e  unbox.any [mscorlib]System.Int32
0xc7a3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xc7a8  ldarg.0
0xc7a9  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc7ae  ldloc.0
0xc7af  ldstr    aLabelsourcefol_15// "labelSourceFolder.Text"
0xc7b4  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xc7b9  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xc7be  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xc7c3  ldarg.0
0xc7c4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc7c9  ldloc.0
0xc7ca  ldstr    aLabelsourcefol_16// "labelSourceFolder.TextAlign"
0xc7cf  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc7d4  unbox.any [System.Drawing]System.Drawing.ContentAlignment
0xc7d9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xc7de  ldarg.0
0xc7df  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.SourceLocationPage::labelSourceFolder
0xc7e4  ldloc.0
0xc7e5  ldstr    aLabelsourcefol_17// "labelSourceFolder.Visible"
0xc7ea  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc7ef  unbox.any [mscorlib]System.Boolean
0xc7f4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xc7f9  ldarg.0
0xc7fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc7ff  ldloc.0
0xc800  ldstr    aTextboxsourcef// "textBoxSourceFolder.AccessibleDescripti"...
0xc805  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xc80a  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xc80f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xc814  ldarg.0
0xc815  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc81a  ldloc.0
0xc81b  ldstr    aTextboxsourcef_0// "textBoxSourceFolder.AccessibleName"
0xc820  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xc825  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xc82a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xc82f  ldarg.0
0xc830  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc835  ldloc.0
0xc836  ldstr    aTextboxsourcef_1// "textBoxSourceFolder.Anchor"
0xc83b  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc840  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0xc845  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xc84a  ldarg.0
0xc84b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc850  ldloc.0
0xc851  ldstr    aTextboxsourcef_2// "textBoxSourceFolder.AutoSize"
0xc856  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc85b  unbox.any [mscorlib]System.Boolean
0xc860  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xc865  ldarg.0
0xc866  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc86b  ldloc.0
0xc86c  ldstr    aTextboxsourcef_3// "textBoxSourceFolder.BackgroundImage"
0xc871  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc876  castclass [System.Drawing]System.Drawing.Image
0xc87b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackgroundImage(class [System.Drawing]System.Drawing.Image)
0xc880  ldarg.0
0xc881  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc886  ldloc.0
0xc887  ldstr    aTextboxsourcef_4// "textBoxSourceFolder.Dock"
0xc88c  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc891  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0xc896  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xc89b  ldarg.0
0xc89c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc8a1  ldloc.0
0xc8a2  ldstr    aTextboxsourcef_5// "textBoxSourceFolder.Enabled"
0xc8a7  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc8ac  unbox.any [mscorlib]System.Boolean
0xc8b1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xc8b6  ldarg.0
0xc8b7  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc8bc  ldloc.0
0xc8bd  ldstr    aTextboxsourcef_6// "textBoxSourceFolder.Font"
0xc8c2  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc8c7  castclass [System.Drawing]System.Drawing.Font
0xc8cc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0xc8d1  ldarg.0
0xc8d2  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc8d7  ldloc.0
0xc8d8  ldstr    aTextboxsourcef_7// "textBoxSourceFolder.ImeMode"
0xc8dd  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc8e2  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0xc8e7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xc8ec  ldarg.0
0xc8ed  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc8f2  ldloc.0
0xc8f3  ldstr    aTextboxsourcef_8// "textBoxSourceFolder.Location"
0xc8f8  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc8fd  unbox.any [System.Drawing]System.Drawing.Point
0xc902  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xc907  ldarg.0
0xc908  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc90d  ldloc.0
0xc90e  ldstr    aTextboxsourcef_9// "textBoxSourceFolder.MaxLength"
0xc913  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc918  unbox.any [mscorlib]System.Int32
0xc91d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_MaxLength(int32)
0xc922  ldarg.0
0xc923  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc928  ldloc.0
0xc929  ldstr    aTextboxsourcef_10// "textBoxSourceFolder.Multiline"
0xc92e  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc933  unbox.any [mscorlib]System.Boolean
0xc938  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBoxBase::set_Multiline(bool)
0xc93d  ldarg.0
0xc93e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc943  ldstr    aTextboxsourcef_11// "textBoxSourceFolder"
0xc948  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xc94d  ldarg.0
0xc94e  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc953  ldloc.0
0xc954  ldstr    aTextboxsourcef_12// "textBoxSourceFolder.PasswordChar"
0xc959  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc95e  unbox.any [mscorlib]System.Char
0xc963  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_PasswordChar(char)
0xc968  ldarg.0
0xc969  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc96e  ldloc.0
0xc96f  ldstr    aTextboxsourcef_13// "textBoxSourceFolder.RightToLeft"
0xc974  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc979  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0xc97e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0xc983  ldarg.0
0xc984  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc989  ldloc.0
0xc98a  ldstr    aTextboxsourcef_14// "textBoxSourceFolder.ScrollBars"
0xc98f  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc994  unbox.any [System.Windows.Forms]System.Windows.Forms.ScrollBars
0xc999  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_ScrollBars(valuetype [System.Windows.Forms]System.Windows.Forms.ScrollBars)
0xc99e  ldarg.0
0xc99f  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc9a4  ldloc.0
0xc9a5  ldstr    aTextboxsourcef_15// "textBoxSourceFolder.Size"
0xc9aa  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc9af  unbox.any [System.Drawing]System.Drawing.Size
0xc9b4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xc9b9  ldarg.0
0xc9ba  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc9bf  ldloc.0
0xc9c0  ldstr    aTextboxsourcef_16// "textBoxSourceFolder.TabIndex"
0xc9c5  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xc9ca  unbox.any [mscorlib]System.Int32
0xc9cf  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xc9d4  ldarg.0
0xc9d5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc9da  ldloc.0
0xc9db  ldstr    aTextboxsourcef_17// "textBoxSourceFolder.Text"
0xc9e0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0xc9e5  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xc9ea  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xc9ef  ldarg.0
0xc9f0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xc9f5  ldloc.0
0xc9f6  ldstr    aTextboxsourcef_18// "textBoxSourceFolder.TextAlign"
0xc9fb  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xca00  unbox.any [System.Windows.Forms]System.Windows.Forms.HorizontalAlignment
0xca05  callvirt instance void [System.Windows.Forms]System.Windows.Forms.TextBox::set_TextAlign(valuetype [System.Windows.Forms]System.Windows.Forms.HorizontalAlignment)
0xca0a  ldarg.0
0xca0b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.SourceLocationPage::textBoxSourceFolder
0xca10  ldloc.0
0xca11  ldstr    aTextboxsourcef_19// "textBoxSourceFolder.Visible"
0xca16  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0xca1b  unbox.any [mscorlib]System.Boolean
  ... truncated ...
```
