# Microsoft.Crm.Application.Script::BuildCloseWindow_1

- ea: `0x16c80`
- end: `0x16d3b`
- name: `Microsoft.Crm.Application.Script::BuildCloseWindow_1`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x16c70`

## callees

- `0x16c80`
- `0x16e30`
- `0x16ef0`
- `0x16f20`
- `0x47280`

## string_xrefs

- `0x16c88`: `/_static/_common/scripts/MicrosoftAjax.js`
- `0x16c90`: `/_static/_common/scripts/EncodeDecode.js`
- `0x16c98`: `/_static/_common/scripts/Microsoft.Crm.Client.Core.js`
- `0x16ca0`: `/_static/_common/scripts/CrmServiceProxy.js`
- `0x16ca8`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0x16cb0`: `/_common/global.ashx`

## pseudocode

```c

```

## disassembly

```asm
0x16c80  ldc.i4.6
0x16c81  newarr   [mscorlib]System.String
0x16c86  dup
0x16c87  ldc.i4.0
0x16c88  ldstr    aStaticCommonSc// "/_static/_common/scripts/MicrosoftAjax."...
0x16c8d  stelem.ref
0x16c8e  dup
0x16c8f  ldc.i4.1
0x16c90  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/EncodeDecode.j"...
0x16c95  stelem.ref
0x16c96  dup
0x16c97  ldc.i4.2
0x16c98  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/Microsoft.Crm."...
0x16c9d  stelem.ref
0x16c9e  dup
0x16c9f  ldc.i4.3
0x16ca0  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/CrmServiceProx"...
0x16ca5  stelem.ref
0x16ca6  dup
0x16ca7  ldc.i4.4
0x16ca8  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/CrmServiceProx"...
0x16cad  stelem.ref
0x16cae  dup
0x16caf  ldc.i4.5
0x16cb0  ldstr    aCommonGlobalAs// "/_common/global.ashx"
0x16cb5  stelem.ref
0x16cb6  ldnull
0x16cb7  ldftn    string Microsoft.Crm.Application.Script::BuildScriptTag(string scriptPath)
0x16cbd  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x16cc2  call     T0x2B00003B
0x16cc7  call     T0x2B00003C
0x16ccc  stloc.0
0x16ccd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16cd2  ldstr    aDoctypeHtmlHtm// "<!DOCTYPE html>\r\n\t\t\t\t\t <html>\r"...
0x16cd7  ldc.i4.5
0x16cd8  newarr   [mscorlib]System.Object
0x16cdd  dup
0x16cde  ldc.i4.0
0x16cdf  ldarg.0
0x16ce0  ldarg.1
0x16ce1  ldarg.2
0x16ce2  ldarg.3
0x16ce3  ldarg.s  4
0x16ce5  call     string Microsoft.Crm.Application.Script::BuildGridRefreshCallback(class Microsoft.Crm.Application.Platform.EntityType entityType, string searchText, valuetype [mscorlib]System.Guid entityId, bool renderScriptBlock, bool useTopWindow)
0x16cea  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x16cef  stelem.ref
0x16cf0  dup
0x16cf1  ldc.i4.1
0x16cf2  ldstr    asc_B59BA// "\n\t\t"
0x16cf7  ldloc.0
0x16cf8  call     string [mscorlib]System.String::Join(string, string[])
0x16cfd  stelem.ref
0x16cfe  dup
0x16cff  ldc.i4.2
0x16d00  call     bool Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x16d05  brtrue.s loc_16D0E
0x16d07  ldstr    aFalse// "false"
0x16d0c  br.s     loc_16D13
0x16d0e  ldstr    aTrue// "true"
0x16d13  stelem.ref
0x16d14  dup
0x16d15  ldc.i4.3
0x16d16  ldarg.0
0x16d17  ldarg.s  4
0x16d19  call     string Microsoft.Crm.Application.Script::BuildNotifyParentScriptBlock(class Microsoft.Crm.Application.Platform.EntityType entityType, bool useTopWindow)
0x16d1e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x16d23  stelem.ref
0x16d24  dup
0x16d25  ldc.i4.4
0x16d26  ldarg.0
0x16d27  ldarg.1
0x16d28  ldarg.2
0x16d29  ldarg.3
0x16d2a  call     string Microsoft.Crm.Application.Script::BuildRefreshParentLookupScriptBlock(class Microsoft.Crm.Application.Platform.EntityType entityType, string searchText, valuetype [mscorlib]System.Guid entityId, bool renderScriptBlock)
0x16d2f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x16d34  stelem.ref
0x16d35  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x16d3a  ret
```
