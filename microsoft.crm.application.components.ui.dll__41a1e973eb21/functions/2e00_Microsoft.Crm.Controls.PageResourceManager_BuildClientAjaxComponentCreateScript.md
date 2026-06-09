# Microsoft.Crm.Controls.PageResourceManager::BuildClientAjaxComponentCreateScript

- ea: `0x2e00`
- end: `0x2eed`
- name: `Microsoft.Crm.Controls.PageResourceManager::BuildClientAjaxComponentCreateScript`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2d80`

## callees

- `0x2e00`

## string_xrefs

- `0x2e09`: `Argument componentTypeName cannot be null or empty.`
- `0x2e19`: `Argument componentTypeName is not a valid JavaScript id.`
- `0x2e87`: `crmCreate({0},{1},{2},{3},{4});`

## pseudocode

```c

```

## disassembly

```asm
0x2e00  ldarg.1
0x2e01  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e06  ldc.i4.0
0x2e07  ceq
0x2e09  ldstr    aArgumentCompon// "Argument componentTypeName cannot be nu"...
0x2e0e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x2e13  ldarg.1
0x2e14  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::IsValidJavaScriptIdentifierWithNamespaces(string)
0x2e19  ldstr    aArgumentCompon_0// "Argument componentTypeName is not a val"...
0x2e1e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x2e23  ldarg.2
0x2e24  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e29  brfalse.s loc_2E32
0x2e2b  ldstr    aNull// "null"
0x2e30  starg.s  2
0x2e32  ldarg.3
0x2e33  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e38  brfalse.s loc_2E41
0x2e3a  ldstr    aNull// "null"
0x2e3f  starg.s  3
0x2e41  ldarg.s  4
0x2e43  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e48  brfalse.s loc_2E51
0x2e4a  ldstr    aNull// "null"
0x2e4f  starg.s  4
0x2e51  ldarg.s  5
0x2e53  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e58  brfalse.s loc_2E62
0x2e5a  ldstr    aNull// "null"
0x2e5f  stloc.0
0x2e60  br.s     loc_2E82
0x2e62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e67  ldstr    aGet0// "$get({0})"
0x2e6c  ldc.i4.1
0x2e6d  newarr   [mscorlib]System.Object
0x2e72  dup
0x2e73  ldc.i4.0
0x2e74  ldarg.s  5
0x2e76  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2e7b  stelem.ref
0x2e7c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e81  stloc.0
0x2e82  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e87  ldstr    aCrmcreate01234// "crmCreate({0},{1},{2},{3},{4});"
0x2e8c  ldc.i4.5
0x2e8d  newarr   [mscorlib]System.Object
0x2e92  dup
0x2e93  ldc.i4.0
0x2e94  ldarg.1
0x2e95  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x2e9a  stelem.ref
0x2e9b  dup
0x2e9c  ldc.i4.1
0x2e9d  ldarg.2
0x2e9e  stelem.ref
0x2e9f  dup
0x2ea0  ldc.i4.2
0x2ea1  ldarg.3
0x2ea2  stelem.ref
0x2ea3  dup
0x2ea4  ldc.i4.3
0x2ea5  ldarg.s  4
0x2ea7  stelem.ref
0x2ea8  dup
0x2ea9  ldc.i4.4
0x2eaa  ldloc.0
0x2eab  stelem.ref
0x2eac  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2eb1  stloc.1
0x2eb2  ldarg.1
0x2eb3  ldstr    aMscrmFormnavco// "Mscrm.FormNavControl"
0x2eb8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ebd  brfalse.s loc_2EEB
0x2ebf  ldarg.s  5
0x2ec1  ldstr    aCrmnavbar// "crmNavBar"
0x2ec6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ecb  brfalse.s loc_2EEB
0x2ecd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ed2  ldstr    aIf0Null1ElseWi// "if ({0} != null) {{ {1} }} else {{ wind"...
0x2ed7  ldc.i4.2
0x2ed8  newarr   [mscorlib]System.Object
0x2edd  dup
0x2ede  ldc.i4.0
0x2edf  ldloc.0
0x2ee0  stelem.ref
0x2ee1  dup
0x2ee2  ldc.i4.1
0x2ee3  ldloc.1
0x2ee4  stelem.ref
0x2ee5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2eea  ret
0x2eeb  ldloc.1
0x2eec  ret
```
