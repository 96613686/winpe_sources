# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlIcons::GetCompletedLabelIcon

- ea: `0x5d80`
- end: `0x5dd9`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlIcons::GetCompletedLabelIcon`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5b60`

## string_xrefs

- `0x5dc3`: `ProcessControl.CompletedStage`
- `0x5d80`: `/_imgs/processcontrol/process_control_completed.png`
- `0x5d90`: `<img class="{0} completedStep" src="{1}" alt="{2}" title="{2}"/>`

## pseudocode

```c

```

## disassembly

```asm
0x5d80  ldstr    aImgsProcesscon_8// "/_imgs/processcontrol/process_control_c"...
0x5d85  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControlIcons::GetStripImage(string path)
0x5d8a  stloc.0
0x5d8b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5d90  ldstr    aImgClass0Compl// "<img class=\"{0} completedStep\" src=\""...
0x5d95  ldc.i4.3
0x5d96  newarr   [mscorlib]System.Object
0x5d9b  dup
0x5d9c  ldc.i4.0
0x5d9d  ldloc.0
0x5d9e  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x5da3  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5da8  stelem.ref
0x5da9  dup
0x5daa  ldc.i4.1
0x5dab  ldloc.0
0x5dac  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x5db1  callvirt instance string [mscorlib]System.Object::ToString()
0x5db6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5dbb  stelem.ref
0x5dbc  dup
0x5dbd  ldc.i4.2
0x5dbe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5dc3  ldstr    aProcesscontrol_2// "ProcessControl.CompletedStage"
0x5dc8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5dcd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5dd2  stelem.ref
0x5dd3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5dd8  ret
```
