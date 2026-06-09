# Microsoft.Crm.Setup.Common.UI.WizardPage::InitializeComponent

- ea: `0x10d80`
- end: `0x10eb5`
- name: `Microsoft.Crm.Setup.Common.UI.WizardPage::InitializeComponent`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10d20`

## string_xrefs

- `0x10d9c`: `$this.AccessibleDescription`
- `0x10db2`: `$this.AccessibleName`
- `0x10d80`: `Microsoft.Crm.Setup.Common.WizardPage`

## pseudocode

```c

```

## disassembly

```asm
0x10d80  ldstr    aMicrosoftCrmSe_9// "Microsoft.Crm.Setup.Common.WizardPage"
0x10d85  ldtoken  Microsoft.Crm.Setup.Common.UI.WizardPage
0x10d8a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10d8f  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x10d94  newobj   instance void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x10d99  stloc.0
0x10d9a  ldarg.0
0x10d9b  ldloc.0
0x10d9c  ldstr    aThisAccessible// "$this.AccessibleDescription"
0x10da1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x10da6  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x10dab  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleDescription(string)
0x10db0  ldarg.0
0x10db1  ldloc.0
0x10db2  ldstr    aThisAccessible_0// "$this.AccessibleName"
0x10db7  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::get_InternalCultureInfo()
0x10dbc  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x10dc1  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_AccessibleName(string)
0x10dc6  ldarg.0
0x10dc7  ldloc.0
0x10dc8  ldstr    aThisAutoscroll// "$this.AutoScroll"
0x10dcd  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x10dd2  unbox.any [mscorlib]System.Boolean
0x10dd7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScroll(bool)
0x10ddc  ldarg.0
0x10ddd  ldloc.0
0x10dde  ldstr    aThisAutoscroll_0// "$this.AutoScrollMargin"
0x10de3  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x10de8  unbox.any [System.Drawing]System.Drawing.Size
0x10ded  call     instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMargin(valuetype [System.Drawing]System.Drawing.Size)
0x10df2  ldarg.0
0x10df3  ldloc.0
0x10df4  ldstr    aThisAutoscroll_1// "$this.AutoScrollMinSize"
0x10df9  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x10dfe  unbox.any [System.Drawing]System.Drawing.Size
0x10e03  call     instance void [System.Windows.Forms]System.Windows.Forms.ScrollableControl::set_AutoScrollMinSize(valuetype [System.Drawing]System.Drawing.Size)
0x10e08  ldarg.0
0x10e09  ldloc.0
0x10e0a  ldstr    aThisBackground// "$this.BackgroundImage"
0x10e0f  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x10e14  castclass [System.Drawing]System.Drawing.Image
0x10e19  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_BackgroundImage(class [System.Drawing]System.Drawing.Image)
0x10e1e  ldarg.0
0x10e1f  ldloc.0
0x10e20  ldstr    aThisEnabled// "$this.Enabled"
0x10e25  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x10e2a  unbox.any [mscorlib]System.Boolean
0x10e2f  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x10e34  ldarg.0
0x10e35  ldloc.0
0x10e36  ldstr    aThisFont// "$this.Font"
0x10e3b  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x10e40  castclass [System.Drawing]System.Drawing.Font
0x10e45  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Font(class [System.Drawing]System.Drawing.Font)
0x10e4a  ldarg.0
0x10e4b  ldloc.0
0x10e4c  ldstr    aThisImemode// "$this.ImeMode"
0x10e51  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x10e56  unbox.any [System.Windows.Forms]System.Windows.Forms.ImeMode
0x10e5b  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_ImeMode(valuetype [System.Windows.Forms]System.Windows.Forms.ImeMode)
0x10e60  ldarg.0
0x10e61  ldloc.0
0x10e62  ldstr    aThisLocation// "$this.Location"
0x10e67  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x10e6c  unbox.any [System.Drawing]System.Drawing.Point
0x10e71  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Location(valuetype [System.Drawing]System.Drawing.Point)
0x10e76  ldarg.0
0x10e77  ldstr    aWizardpage// "WizardPage"
0x10e7c  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Name(string)
0x10e81  ldarg.0
0x10e82  ldloc.0
0x10e83  ldstr    aThisRighttolef// "$this.RightToLeft"
0x10e88  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x10e8d  unbox.any [System.Windows.Forms]System.Windows.Forms.RightToLeft
0x10e92  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_RightToLeft(valuetype [System.Windows.Forms]System.Windows.Forms.RightToLeft)
0x10e97  ldarg.0
0x10e98  ldloc.0
0x10e99  ldstr    aThisSize// "$this.Size"
0x10e9e  callvirt instance object [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetObject(string)
0x10ea3  unbox.any [System.Drawing]System.Drawing.Size
0x10ea8  call     instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Size(valuetype [System.Drawing]System.Drawing.Size)
0x10ead  ldarg.0
0x10eae  ldc.i4.2
0x10eaf  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::set_AutoScaleMode(valuetype [System.Windows.Forms]System.Windows.Forms.AutoScaleMode)
0x10eb4  ret
```
