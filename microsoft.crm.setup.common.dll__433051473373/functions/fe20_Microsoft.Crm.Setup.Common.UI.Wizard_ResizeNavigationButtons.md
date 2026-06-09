# Microsoft.Crm.Setup.Common.UI.Wizard::ResizeNavigationButtons

- ea: `0xfe20`
- end: `0xffe0`
- name: `Microsoft.Crm.Setup.Common.UI.Wizard::ResizeNavigationButtons`
- size: `448`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd730`
- `0xd7a0`

## callees

- `0xff0`
- `0xfcc0`
- `0xfe20`

## string_xrefs

- `0xfe6c`: `RepairButtonText`
- `0xfe9a`: `UninstallButtonText`
- `0xfe55`: `InstallButtonText`

## pseudocode

```c

```

## disassembly

```asm
0xfe20  newobj   instance void [System]System.Collections.Specialized.StringCollection::.ctor()
0xfe25  stloc.0
0xfe26  ldloc.0
0xfe27  ldstr    aNextbuttontext// "NextButtonText"
0xfe2c  ldc.i4.0
0xfe2d  newarr   [mscorlib]System.Object
0xfe32  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xfe37  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xfe3c  pop
0xfe3d  ldloc.0
0xfe3e  ldstr    aCancelbuttonte// "CancelButtonText"
0xfe43  ldc.i4.0
0xfe44  newarr   [mscorlib]System.Object
0xfe49  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xfe4e  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xfe53  pop
0xfe54  ldloc.0
0xfe55  ldstr    aInstallbuttont// "InstallButtonText"
0xfe5a  ldc.i4.0
0xfe5b  newarr   [mscorlib]System.Object
0xfe60  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xfe65  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xfe6a  pop
0xfe6b  ldloc.0
0xfe6c  ldstr    aRepairbuttonte// "RepairButtonText"
0xfe71  ldc.i4.0
0xfe72  newarr   [mscorlib]System.Object
0xfe77  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xfe7c  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xfe81  pop
0xfe82  ldloc.0
0xfe83  ldstr    aUpgradebuttont// "UpgradeButtonText"
0xfe88  ldc.i4.0
0xfe89  newarr   [mscorlib]System.Object
0xfe8e  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xfe93  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xfe98  pop
0xfe99  ldloc.0
0xfe9a  ldstr    aUninstallbutto// "UninstallButtonText"
0xfe9f  ldc.i4.0
0xfea0  newarr   [mscorlib]System.Object
0xfea5  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xfeaa  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xfeaf  pop
0xfeb0  ldloc.0
0xfeb1  ldarg.0
0xfeb2  call     instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_FinishButton()
0xfeb7  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0xfebc  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xfec1  pop
0xfec2  ldloc.0
0xfec3  ldarg.0
0xfec4  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::backButton
0xfec9  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0xfece  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0xfed3  pop
0xfed4  ldarg.0
0xfed5  ldfld    class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::finishButton
0xfeda  stloc.1
0xfedb  ldloc.1
0xfedc  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Width()
0xfee1  stloc.2
0xfee2  ldloc.1
0xfee3  callvirt instance class [System.Drawing]System.Drawing.Graphics [System.Windows.Forms]System.Windows.Forms.Control::CreateGraphics()
0xfee8  stloc.3
0xfee9  ldloc.0
0xfeea  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0xfeef  stloc.s  6
0xfef1  br.s     loc_FF29
0xfef3  ldloc.s  6
0xfef5  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0xfefa  stloc.s  7
0xfefc  ldloc.3
0xfefd  ldloc.s  7
0xfeff  ldloc.1
0xff00  callvirt instance class [System.Drawing]System.Drawing.Font [System.Windows.Forms]System.Windows.Forms.Control::get_Font()
0xff05  callvirt instance valuetype [System.Drawing]System.Drawing.SizeF [System.Drawing]System.Drawing.Graphics::MeasureString(string, class [System.Drawing]System.Drawing.Font)
0xff0a  stloc.s  4
0xff0c  ldloca.s 4
0xff0e  call     instance float32 [System.Drawing]System.Drawing.SizeF::get_Width()
0xff13  ldc.r4   6.0
0xff18  add
0xff19  call     int32 [mscorlib]System.Convert::ToInt32(float32)
0xff1e  stloc.s  8
0xff20  ldloc.2
0xff21  ldloc.s  8
0xff23  call     int32 [mscorlib]System.Math::Max(int32, int32)
0xff28  stloc.2
0xff29  ldloc.s  6
0xff2b  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0xff30  brtrue.s loc_FEF3
0xff32  leave.s  loc_FF49
0xff34  ldloc.s  6
0xff36  isinst   [mscorlib]System.IDisposable
0xff3b  stloc.s  9
0xff3d  ldloc.s  9
0xff3f  brfalse.s loc_FF48
0xff41  ldloc.s  9
0xff43  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xff48  endfinally
0xff49  ldarg.0
0xff4a  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xff4f  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Right()
0xff54  ldarg.0
0xff55  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xff5a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0xff5f  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::get_Right()
0xff64  ldarg.0
0xff65  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xff6a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges [System.Windows.Forms]System.Windows.Forms.ScrollableControl::get_DockPadding()
0xff6f  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.ScrollableControl/DockPaddingEdges::get_Left()
0xff74  add
0xff75  sub
0xff76  stloc.s  5
0xff78  ldloc.2
0xff79  ldloc.s  5
0xff7b  ldc.i4.3
0xff7c  div
0xff7d  call     int32 [mscorlib]System.Math::Min(int32, int32)
0xff82  stloc.2
0xff83  ldloc.2
0xff84  ldloc.1
0xff85  callvirt instance int32 [System.Windows.Forms]System.Windows.Forms.Control::get_Width()
0xff8a  ble.s    loc_FFDF
0xff8c  ldarg.0
0xff8d  ldfld    class [System.Windows.Forms]System.Windows.Forms.FlowLayoutPanel Microsoft.Crm.Setup.Common.UI.Wizard::buttonPanel
0xff92  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Control/ControlCollection [System.Windows.Forms]System.Windows.Forms.Control::get_Controls()
0xff97  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Windows.Forms]System.Windows.Forms.Layout.ArrangedElementCollection::GetEnumerator()
0xff9c  stloc.s  0xA
0xff9e  br.s     loc_FFBF
0xffa0  ldloc.s  0xA
0xffa2  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xffa7  castclass [System.Windows.Forms]System.Windows.Forms.Control
0xffac  stloc.s  0xB
0xffae  ldloc.s  0xB
0xffb0  isinst   [System.Windows.Forms]System.Windows.Forms.Button
0xffb5  brfalse.s loc_FFBF
0xffb7  ldloc.s  0xB
0xffb9  ldloc.2
0xffba  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Width(int32)
0xffbf  ldloc.s  0xA
0xffc1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xffc6  brtrue.s loc_FFA0
0xffc8  leave.s  loc_FFDF
0xffca  ldloc.s  0xA
0xffcc  isinst   [mscorlib]System.IDisposable
0xffd1  stloc.s  9
0xffd3  ldloc.s  9
0xffd5  brfalse.s loc_FFDE
0xffd7  ldloc.s  9
0xffd9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xffde  endfinally
0xffdf  ret
```
