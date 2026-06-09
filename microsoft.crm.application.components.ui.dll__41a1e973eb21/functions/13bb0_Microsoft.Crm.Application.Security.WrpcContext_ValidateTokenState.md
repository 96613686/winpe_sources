# Microsoft.Crm.Application.Security.WrpcContext::ValidateTokenState

- ea: `0x13bb0`
- end: `0x13cba`
- name: `Microsoft.Crm.Application.Security.WrpcContext::ValidateTokenState`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x137b0`

## callees

- `0x134a0`
- `0x134d0`
- `0x13500`
- `0x13bb0`

## string_xrefs

- `0x13bc4`: `WRPCTokenState`
- `0x13bdd`: `WRPCTokenState`
- `0x13c3f`: `WRPCTokenState`
- `0x13c28`: `Validate WRPC Token: WRPCTokenState={0}, TOKEN_EXPIRY={1}, IGNORE_TOKEN={2}, TOKEN_KEY={3}`
- `0x13c8a`: `EXPIRED_WRPC_TOKEN`
- `0x13c9a`: `INVALID_WRPC_TOKEN`
- `0x13caa`: `INVALID_WRPC_TOKEN: Invalid HttpContext`

## pseudocode

```c

```

## disassembly

```asm
0x13bb0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x13bb5  brfalse  loc_13CAA
0x13bba  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x13bbf  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x13bc4  ldstr    aWrpctokenstate// "WRPCTokenState"
0x13bc9  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x13bce  brfalse  loc_13CAA
0x13bd3  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x13bd8  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x13bdd  ldstr    aWrpctokenstate// "WRPCTokenState"
0x13be2  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x13be7  unbox.any [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.WrpcTokenState
0x13bec  stloc.0
0x13bed  ldloc.0
0x13bee  brfalse.s loc_13BF4
0x13bf0  ldloc.0
0x13bf1  ldc.i4.3
0x13bf2  bne.un.s loc_13BF5
0x13bf4  ret
0x13bf5  ldsfld   string [mscorlib]System.String::Empty
0x13bfa  stloc.1
0x13bfb  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x13c00  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x13c05  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenKey()
0x13c0a  callvirt instance object [System.Web]System.Web.HttpApplicationState::get_Item(string)
0x13c0f  castclass unsigned int8[]
0x13c14  stloc.2
0x13c15  ldloc.2
0x13c16  brfalse.s loc_13C23
0x13c18  ldloc.2
0x13c19  ldlen
0x13c1a  brfalse.s loc_13C23
0x13c1c  ldloc.2
0x13c1d  call     string [Microsoft.Crm]Microsoft.Crm.CryptoRandom::ConvertKeyToString(unsigned int8[])
0x13c22  stloc.1
0x13c23  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13c28  ldstr    aValidateWrpcTo// "Validate WRPC Token: WRPCTokenState={0}"...
0x13c2d  ldc.i4.4
0x13c2e  newarr   [mscorlib]System.Object
0x13c33  dup
0x13c34  ldc.i4.0
0x13c35  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x13c3a  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x13c3f  ldstr    aWrpctokenstate// "WRPCTokenState"
0x13c44  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x13c49  stelem.ref
0x13c4a  dup
0x13c4b  ldc.i4.1
0x13c4c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x13c51  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x13c56  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenExpiry()
0x13c5b  callvirt instance object [System.Web]System.Web.HttpApplicationState::get_Item(string)
0x13c60  stelem.ref
0x13c61  dup
0x13c62  ldc.i4.2
0x13c63  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x13c68  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x13c6d  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheIgnoreToken()
0x13c72  callvirt instance object [System.Web]System.Web.HttpApplicationState::get_Item(string)
0x13c77  stelem.ref
0x13c78  dup
0x13c79  ldc.i4.3
0x13c7a  ldloc.1
0x13c7b  stelem.ref
0x13c7c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13c81  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::TraceInfo(string)
0x13c86  ldloc.0
0x13c87  ldc.i4.2
0x13c88  bne.un.s loc_13C9A
0x13c8a  ldstr    aExpiredWrpcTok// "EXPIRED_WRPC_TOKEN"
0x13c8f  ldc.i4   0x8063110A
0x13c94  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x13c99  throw
0x13c9a  ldstr    aInvalidWrpcTok_1// "INVALID_WRPC_TOKEN"
0x13c9f  ldc.i4   0x8063110B
0x13ca4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x13ca9  throw
0x13caa  ldstr    aInvalidWrpcTok_2// "INVALID_WRPC_TOKEN: Invalid HttpContext"
0x13caf  ldc.i4   0x8063110B
0x13cb4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x13cb9  throw
```
