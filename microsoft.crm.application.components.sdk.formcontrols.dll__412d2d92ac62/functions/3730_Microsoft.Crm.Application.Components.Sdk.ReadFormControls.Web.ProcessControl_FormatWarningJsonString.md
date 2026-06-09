# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::FormatWarningJsonString

- ea: `0x3730`
- end: `0x377a`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::FormatWarningJsonString`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x3620`
- `0x37a0`

## string_xrefs

- `0x3735`: `{{"_processStages":{0},"_processControlStrings":{1}, "_globalNavigationData":{2}, "_processId":{3}, "_warning":{4}, "_warningCode":{5}}}`

## pseudocode

```c

```

## disassembly

```asm
0x3730  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3735  ldstr    aProcessstages0_0// "{{\"_processStages\":{0},\"_processCont"...
0x373a  ldc.i4.6
0x373b  newarr   [mscorlib]System.Object
0x3740  dup
0x3741  ldc.i4.0
0x3742  ldstr    aNull// "null"
0x3747  stelem.ref
0x3748  dup
0x3749  ldc.i4.1
0x374a  ldarg.1
0x374b  stelem.ref
0x374c  dup
0x374d  ldc.i4.2
0x374e  ldstr    aNull// "null"
0x3753  stelem.ref
0x3754  dup
0x3755  ldc.i4.3
0x3756  ldstr    aNull// "null"
0x375b  stelem.ref
0x375c  dup
0x375d  ldc.i4.4
0x375e  ldarg.0
0x375f  ldfld    class [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_serializer
0x3764  ldarg.2
0x3765  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x376a  stelem.ref
0x376b  dup
0x376c  ldc.i4.5
0x376d  ldarg.3
0x376e  box      [mscorlib]System.Int32
0x3773  stelem.ref
0x3774  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3779  ret
```
