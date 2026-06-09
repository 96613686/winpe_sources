# Microsoft.Crm.Setup.Common.UI.WaitMessage::InitializeComponent

- ea: `0xd0b0`
- end: `0xd68c`
- name: `Microsoft.Crm.Setup.Common.UI.WaitMessage::InitializeComponent`
- size: `1500`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xcff0`

## string_xrefs

- `0xd49c`: `$this.AccessibleDescription`
- `0xd4ad`: `$this.AccessibleName`
- `0xd5f2`: `$this.MaximumSize`
- `0xd60f`: `$this.MinimumSize`
- `0xd0b0`: `Microsoft.Crm.Setup.Common.WaitMessage`
- `0xd0ed`: `labelWaitMessage.AccessibleDescription`
- `0xd103`: `labelWaitMessage.AccessibleName`
- `0xd2d4`: `pictureBox.AccessibleDescription`
- `0xd2ea`: `pictureBox.AccessibleName`

## pseudocode

```c

```

## disassembly

```asm
0xd0b0  ldstr    aMicrosoftCrmSe_7// "Microsoft.Crm.Setup.Common.WaitMessage"
0xd0b5  ldtoken  Microsoft.Crm.Setup.Common.UI.WaitMessage
0xd0ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd0bf  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0xd0c4  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0xd0c9  stloc.0
0xd0ca  ldarg.0
0xd0cb  newobj   instance void [System.Windows.Forms]System.Windows.Forms.Label::.ctor()
0xd0d0  stfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd0d5  ldarg.0
0xd0d6  newobj   instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::.ctor()
0xd0db  stfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd0e0  ldarg.0
0xd0e1  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::SuspendLayout()
0xd0e6  ldarg.0
0xd0e7  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd0ec  ldloc.0
0xd0ed  ldstr    aLabelwaitmessa// "labelWaitMessage.AccessibleDescription"
0xd0f2  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xd0f7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xd0fc  ldarg.0
0xd0fd  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd102  ldloc.0
0xd103  ldstr    aLabelwaitmessa_0// "labelWaitMessage.AccessibleName"
0xd108  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xd10d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xd112  ldarg.0
0xd113  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd118  ldloc.0
0xd119  ldstr    aLabelwaitmessa_1// "labelWaitMessage.Anchor"
0xd11e  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd123  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0xd128  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xd12d  ldarg.0
0xd12e  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd133  ldloc.0
0xd134  ldstr    aLabelwaitmessa_2// "labelWaitMessage.AutoSize"
0xd139  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd13e  unbox.any [mscorlib]System.Boolean
0xd143  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AutoSize(bool)
0xd148  ldarg.0
0xd149  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd14e  ldloc.0
0xd14f  ldstr    aLabelwaitmessa_3// "labelWaitMessage.Dock"
0xd154  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd159  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0xd15e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xd163  ldarg.0
0xd164  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd169  ldloc.0
0xd16a  ldstr    aLabelwaitmessa_4// "labelWaitMessage.Enabled"
0xd16f  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd174  unbox.any [mscorlib]System.Boolean
0xd179  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xd17e  ldarg.0
0xd17f  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd184  ldloc.0
0xd185  ldstr    aLabelwaitmessa_5// "labelWaitMessage.Font"
0xd18a  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd18f  castclass [System.Drawing]System.Drawing.Font
0xd194  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0xd199  ldarg.0
0xd19a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd19f  ldloc.0
0xd1a0  ldstr    aLabelwaitmessa_6// "labelWaitMessage.Image"
0xd1a5  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd1aa  castclass [System.Drawing]System.Drawing.Image
0xd1af  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_Image(class [System.Drawing]System.Drawing.Image)
0xd1b4  ldarg.0
0xd1b5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd1ba  ldloc.0
0xd1bb  ldstr    aLabelwaitmessa_7// "labelWaitMessage.ImageAlign"
0xd1c0  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd1c5  unbox.any [System.Drawing]System.Drawing.ContentAlignment
0xd1ca  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImageAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xd1cf  ldarg.0
0xd1d0  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd1d5  ldloc.0
0xd1d6  ldstr    aLabelwaitmessa_8// "labelWaitMessage.ImageIndex"
0xd1db  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd1e0  unbox.any [mscorlib]System.Int32
0xd1e5  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImageIndex(int32)
0xd1ea  ldarg.0
0xd1eb  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd1f0  ldloc.0
0xd1f1  ldstr    aLabelwaitmessa_9// "labelWaitMessage.ImeMode"
0xd1f6  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd1fb  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0xd200  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xd205  ldarg.0
0xd206  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd20b  ldloc.0
0xd20c  ldstr    aLabelwaitmessa_10// "labelWaitMessage.Location"
0xd211  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd216  unbox.any [System.Drawing]System.Drawing.Point
0xd21b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xd220  ldarg.0
0xd221  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd226  ldstr    aLabelwaitmessa_11// "labelWaitMessage"
0xd22b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xd230  ldarg.0
0xd231  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd236  ldloc.0
0xd237  ldstr    aLabelwaitmessa_12// "labelWaitMessage.RightToLeft"
0xd23c  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd241  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0xd246  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0xd24b  ldarg.0
0xd24c  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd251  ldloc.0
0xd252  ldstr    aLabelwaitmessa_13// "labelWaitMessage.Size"
0xd257  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd25c  unbox.any [System.Drawing]System.Drawing.Size
0xd261  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xd266  ldarg.0
0xd267  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd26c  ldloc.0
0xd26d  ldstr    aLabelwaitmessa_14// "labelWaitMessage.TabIndex"
0xd272  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd277  unbox.any [mscorlib]System.Int32
0xd27c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_TabIndex(int32)
0xd281  ldarg.0
0xd282  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd287  ldloc.0
0xd288  ldstr    aLabelwaitmessa_15// "labelWaitMessage.Text"
0xd28d  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xd292  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xd297  ldarg.0
0xd298  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd29d  ldloc.0
0xd29e  ldstr    aLabelwaitmessa_16// "labelWaitMessage.TextAlign"
0xd2a3  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd2a8  unbox.any [System.Drawing]System.Drawing.ContentAlignment
0xd2ad  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Label::set_TextAlign(valuetype [System.Drawing]System.Drawing.ContentAlignment)
0xd2b2  ldarg.0
0xd2b3  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.WaitMessage::labelWaitMessage
0xd2b8  ldloc.0
0xd2b9  ldstr    aLabelwaitmessa_17// "labelWaitMessage.Visible"
0xd2be  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd2c3  unbox.any [mscorlib]System.Boolean
0xd2c8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xd2cd  ldarg.0
0xd2ce  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd2d3  ldloc.0
0xd2d4  ldstr    aPictureboxAcce// "pictureBox.AccessibleDescription"
0xd2d9  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xd2de  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xd2e3  ldarg.0
0xd2e4  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd2e9  ldloc.0
0xd2ea  ldstr    aPictureboxAcce_0// "pictureBox.AccessibleName"
0xd2ef  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xd2f4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xd2f9  ldarg.0
0xd2fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd2ff  ldloc.0
0xd300  ldstr    aPictureboxAnch// "pictureBox.Anchor"
0xd305  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd30a  unbox.any [System.Windows.Forms]System.Windows.Forms.AnchorStyles
0xd30f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Anchor(valuetype [System.Windows.Forms]System.Windows.Forms.AnchorStyles)
0xd314  ldarg.0
0xd315  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd31a  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::get_Transparent()
0xd31f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xd324  ldarg.0
0xd325  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd32a  ldloc.0
0xd32b  ldstr    aPictureboxBack// "pictureBox.BackgroundImage"
0xd330  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd335  castclass [System.Drawing]System.Drawing.Image
0xd33a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackgroundImage(class [System.Drawing]System.Drawing.Image)
0xd33f  ldarg.0
0xd340  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd345  ldloc.0
0xd346  ldstr    aPictureboxDock// "pictureBox.Dock"
0xd34b  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd350  unbox.any [System.Windows.Forms]System.Windows.Forms.DockStyle
0xd355  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Dock(valuetype [System.Windows.Forms]System.Windows.Forms.DockStyle)
0xd35a  ldarg.0
0xd35b  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd360  ldloc.0
0xd361  ldstr    aPictureboxEnab// "pictureBox.Enabled"
0xd366  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd36b  unbox.any [mscorlib]System.Boolean
0xd370  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0xd375  ldarg.0
0xd376  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd37b  ldloc.0
0xd37c  ldstr    aPictureboxFont// "pictureBox.Font"
0xd381  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd386  castclass [System.Drawing]System.Drawing.Font
0xd38b  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0xd390  ldarg.0
0xd391  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd396  ldloc.0
0xd397  ldstr    aPictureboxImag// "pictureBox.Image"
0xd39c  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd3a1  castclass [System.Drawing]System.Drawing.Image
0xd3a6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_Image(class [System.Drawing]System.Drawing.Image)
0xd3ab  ldarg.0
0xd3ac  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd3b1  ldloc.0
0xd3b2  ldstr    aPictureboxImem// "pictureBox.ImeMode"
0xd3b7  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd3bc  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0xd3c1  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0xd3c6  ldarg.0
0xd3c7  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd3cc  ldloc.0
0xd3cd  ldstr    aPictureboxLoca// "pictureBox.Location"
0xd3d2  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd3d7  unbox.any [System.Drawing]System.Drawing.Point
0xd3dc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0xd3e1  ldarg.0
0xd3e2  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd3e7  ldstr    aPicturebox// "pictureBox"
0xd3ec  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0xd3f1  ldarg.0
0xd3f2  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd3f7  ldloc.0
0xd3f8  ldstr    aPictureboxRigh// "pictureBox.RightToLeft"
0xd3fd  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd402  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0xd407  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0xd40c  ldarg.0
0xd40d  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd412  ldloc.0
0xd413  ldstr    aPictureboxSize// "pictureBox.Size"
0xd418  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd41d  unbox.any [System.Drawing]System.Drawing.Size
0xd422  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0xd427  ldarg.0
0xd428  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd42d  ldloc.0
0xd42e  ldstr    aPictureboxSize_0// "pictureBox.SizeMode"
0xd433  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd438  unbox.any [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode
0xd43d  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_SizeMode(valuetype [System.Windows.Forms]System.Windows.Forms.PictureBoxSizeMode)
0xd442  ldarg.0
0xd443  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd448  ldloc.0
0xd449  ldstr    aPictureboxTabi// "pictureBox.TabIndex"
0xd44e  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd453  unbox.any [mscorlib]System.Int32
0xd458  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabIndex(int32)
0xd45d  ldarg.0
0xd45e  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd463  ldc.i4.0
0xd464  callvirt instance void [System.Windows.Forms]System.Windows.Forms.PictureBox::set_TabStop(bool)
0xd469  ldarg.0
0xd46a  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd46f  ldloc.0
0xd470  ldstr    aPictureboxText// "pictureBox.Text"
0xd475  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xd47a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xd47f  ldarg.0
0xd480  ldfld    class [System.Windows.Forms]System.Windows.Forms.PictureBox Microsoft.Crm.Setup.Common.UI.WaitMessage::pictureBox
0xd485  ldloc.0
0xd486  ldstr    aPictureboxVisi// "pictureBox.Visible"
0xd48b  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd490  unbox.any [mscorlib]System.Boolean
0xd495  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Visible(bool)
0xd49a  ldarg.0
0xd49b  ldloc.0
0xd49c  ldstr    aThisAccessible// "$this.AccessibleDescription"
0xd4a1  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xd4a6  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0xd4ab  ldarg.0
0xd4ac  ldloc.0
0xd4ad  ldstr    aThisAccessible_0// "$this.AccessibleName"
0xd4b2  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0xd4b7  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0xd4bc  ldarg.0
0xd4bd  ldloc.0
0xd4be  ldstr    aThisAutoscaleb// "$this.AutoScaleBaseSize"
0xd4c3  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd4c8  unbox.any [System.Drawing]System.Drawing.Size
0xd4cd  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Form::set_AutoScaleBaseSize(valuetype [System.Drawing]System.Drawing.Size)
0xd4d2  ldarg.0
0xd4d3  ldloc.0
0xd4d4  ldstr    aThisAutoscroll// "$this.AutoScroll"
0xd4d9  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd4de  unbox.any [mscorlib]System.Boolean
0xd4e3  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScroll(bool)
0xd4e8  ldarg.0
0xd4e9  ldloc.0
0xd4ea  ldstr    aThisAutoscroll_0// "$this.AutoScrollMargin"
0xd4ef  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd4f4  unbox.any [System.Drawing]System.Drawing.Size
0xd4f9  call     instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMargin(valuetype [System.Drawing]System.Drawing.Size)
0xd4fe  ldarg.0
0xd4ff  ldloc.0
0xd500  ldstr    aThisAutoscroll_1// "$this.AutoScrollMinSize"
0xd505  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0xd50a  unbox.any [System.Drawing]System.Drawing.Size
0xd50f  call     instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMinSize(valuetype [System.Drawing]System.Drawing.Size)
0xd514  ldarg.0
0xd515  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.SystemColors::get_Window()
0xd51a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackColor(valuetype [System.Drawing]System.Drawing.Color)
0xd51f  ldarg.0
  ... truncated ...
```
