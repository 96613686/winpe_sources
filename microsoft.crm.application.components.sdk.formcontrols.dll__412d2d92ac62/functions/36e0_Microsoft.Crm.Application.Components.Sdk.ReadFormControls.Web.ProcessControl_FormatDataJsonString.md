# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::FormatDataJsonString

- ea: `0x36e0`
- end: `0x3721`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::FormatDataJsonString`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x3620`
- `0x37a0`

## string_xrefs

- `0x36e5`: `{{"_processStages":{0},"_processControlStrings":{1}, "_globalNavigationData":{2}, "_processId":"{3}", "_warning":{4}, "_warningCode":{5}}}`

## pseudocode

```c

```

## disassembly

```asm
0x36e0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36e5  ldstr    aProcessstages0// "{{\"_processStages\":{0},\"_processCont"...
0x36ea  ldc.i4.6
0x36eb  newarr   [mscorlib]System.Object
0x36f0  dup
0x36f1  ldc.i4.0
0x36f2  ldarg.1
0x36f3  stelem.ref
0x36f4  dup
0x36f5  ldc.i4.1
0x36f6  ldarg.2
0x36f7  stelem.ref
0x36f8  dup
0x36f9  ldc.i4.2
0x36fa  ldarg.3
0x36fb  stelem.ref
0x36fc  dup
0x36fd  ldc.i4.3
0x36fe  ldarg.s  4
0x3700  stelem.ref
0x3701  dup
0x3702  ldc.i4.4
0x3703  ldarg.0
0x3704  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3709  ldarg.s  5
0x370b  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x3710  stelem.ref
0x3711  dup
0x3712  ldc.i4.5
0x3713  ldarg.s  6
0x3715  box      [mscorlib]System.Int32
0x371a  stelem.ref
0x371b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3720  ret
```
