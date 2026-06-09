# Microsoft.Crm.Application.Security.WrpcContext::GetWrpcTokenAsQueryString

- ea: `0x14020`
- end: `0x140b1`
- name: `Microsoft.Crm.Application.Security.WrpcContext::GetWrpcTokenAsQueryString`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x13cc0`
- `0x14020`

## string_xrefs

- `0x14045`: `CRMWRPCToken`
- `0x14077`: `CRMWRPCTokenTimeStamp`

## pseudocode

```c

```

## disassembly

```asm
0x14020  ldarg.0
0x14021  ldfld    bool Microsoft.Crm.Application.Security.WrpcContext::_isTokenCheckIgnored
0x14026  brfalse.s loc_1402E
0x14028  ldsfld   string [mscorlib]System.String::Empty
0x1402d  ret
0x1402e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x14033  stloc.0
0x14034  ldc.i4.s 0x64
0x14036  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x1403b  dup
0x1403c  ldc.i4.s 0x26
0x1403e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x14043  pop
0x14044  dup
0x14045  ldstr    aCrmwrpctoken// "CRMWRPCToken"
0x1404a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1404f  pop
0x14050  dup
0x14051  ldc.i4.s 0x3D
0x14053  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x14058  pop
0x14059  dup
0x1405a  ldarg.0
0x1405b  ldarg.1
0x1405c  ldloc.0
0x1405d  call     instance string Microsoft.Crm.Application.Security.WrpcContext::GenerateToken(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri actionPageUrl, valuetype [mscorlib]System.DateTime timestamp)
0x14062  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x14067  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1406c  pop
0x1406d  dup
0x1406e  ldc.i4.s 0x26
0x14070  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x14075  pop
0x14076  dup
0x14077  ldstr    aCrmwrpctokenti// "CRMWRPCTokenTimeStamp"
0x1407c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x14081  pop
0x14082  dup
0x14083  ldc.i4.s 0x3D
0x14085  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1408a  pop
0x1408b  dup
0x1408c  ldloca.s 0
0x1408e  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x14093  stloc.1
0x14094  ldloca.s 1
0x14096  ldstr    aD_1// "D"
0x1409b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x140a0  call     instance string [mscorlib]System.Int64::ToString(string, class [mscorlib]System.IFormatProvider)
0x140a5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x140aa  pop
0x140ab  callvirt instance string [mscorlib]System.Object::ToString()
0x140b0  ret
```
