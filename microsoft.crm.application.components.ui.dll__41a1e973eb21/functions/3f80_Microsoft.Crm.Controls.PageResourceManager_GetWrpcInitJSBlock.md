# Microsoft.Crm.Controls.PageResourceManager::GetWrpcInitJSBlock

- ea: `0x3f80`
- end: `0x4046`
- name: `Microsoft.Crm.Controls.PageResourceManager::GetWrpcInitJSBlock`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x7ae0`

## callees

- `0x3f80`
- `0x13540`
- `0x13cc0`

## string_xrefs

- `0x3fad`: `_aWrpcTokens[`
- `0x3fd6`: `]={Token: `

## pseudocode

```c

```

## disassembly

```asm
0x3f80  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3f85  stloc.0
0x3f86  ldc.i4   0x1F4
0x3f8b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x3f90  stloc.1
0x3f91  newobj   instance void Microsoft.Crm.Application.Security.WrpcContext::.ctor()
0x3f96  stloc.2
0x3f97  ldc.i4.0
0x3f98  stloc.3
0x3f99  br       loc_402E
0x3f9e  ldarg.0
0x3f9f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_wrpcTokenUrls
0x3fa4  ldloc.3
0x3fa5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Item(!!T0)
0x3faa  stloc.s  4
0x3fac  ldloc.1
0x3fad  ldstr    aAwrpctokens// "_aWrpcTokens["
0x3fb2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3fb7  pop
0x3fb8  ldloc.1
0x3fb9  ldloc.s  4
0x3fbb  callvirt instance string [mscorlib]System.Object::ToString()
0x3fc0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3fc5  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x3fca  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x3fcf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3fd4  pop
0x3fd5  ldloc.1
0x3fd6  ldstr    aToken// "]={Token: "
0x3fdb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3fe0  pop
0x3fe1  ldloc.1
0x3fe2  ldloc.2
0x3fe3  ldloc.s  4
0x3fe5  ldloc.0
0x3fe6  callvirt instance string Microsoft.Crm.Application.Security.WrpcContext::GenerateToken(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri actionPageUrl, valuetype [mscorlib]System.DateTime timestamp)
0x3feb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x3ff0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3ff5  pop
0x3ff6  ldloc.1
0x3ff7  ldstr    aTimestamp// ", Timestamp: \""
0x3ffc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4001  pop
0x4002  ldloc.1
0x4003  ldloca.s 0
0x4005  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x400a  stloc.s  5
0x400c  ldloca.s 5
0x400e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4013  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x4018  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x401d  pop
0x401e  ldloc.1
0x401f  ldstr    asc_343AA// "\"};\n"
0x4024  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4029  pop
0x402a  ldloc.3
0x402b  ldc.i4.1
0x402c  add
0x402d  stloc.3
0x402e  ldloc.3
0x402f  ldarg.0
0x4030  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_wrpcTokenUrls
0x4035  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Count()
0x403a  blt      loc_3F9E
0x403f  ldloc.1
0x4040  callvirt instance string [mscorlib]System.Object::ToString()
0x4045  ret
```
