# Microsoft.Crm.Application.Security.WrpcContext::.ctor

- ea: `0x13540`
- end: `0x137a7`
- name: `Microsoft.Crm.Application.Security.WrpcContext::.ctor`
- size: `615`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x2c70`
- `0x3f80`
- `0x4050`

## callees

- `0x134a0`
- `0x134d0`
- `0x13500`
- `0x13540`
- `0x2a940`

## string_xrefs

- `0x136ac`: `Invalid WRPC token key.`
- `0x136d2`: `Invalid WRPC token expiry duration.`
- `0x13742`: `WRPC Token Reset: TOKEN_EXPIRY={0}, IGNORE_TOKEN={1}, TOKEN_KEY={2}`

## pseudocode

```c

```

## disassembly

```asm
0x13540  ldarg.0
0x13541  call     instance void [mscorlib]System.Object::.ctor()
0x13546  ldarg.0
0x13547  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1354c  stfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13551  ldarg.0
0x13552  ldarg.0
0x13553  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13558  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x1355d  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenKey()
0x13562  callvirt instance object [System.Web]System.Web.HttpApplicationState::get_Item(string)
0x13567  castclass unsigned int8[]
0x1356c  stfld    unsigned int8[] Microsoft.Crm.Application.Security.WrpcContext::_tokenKey
0x13571  ldarg.0
0x13572  ldfld    unsigned int8[] Microsoft.Crm.Application.Security.WrpcContext::_tokenKey
0x13577  brfalse.s loc_135C3
0x13579  ldarg.0
0x1357a  ldfld    unsigned int8[] Microsoft.Crm.Application.Security.WrpcContext::_tokenKey
0x1357f  ldlen
0x13580  brfalse.s loc_135C3
0x13582  ldarg.0
0x13583  ldarg.0
0x13584  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13589  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x1358e  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenExpiry()
0x13593  callvirt instance object [System.Web]System.Web.HttpApplicationState::get_Item(string)
0x13598  unbox.any [mscorlib]System.Int32
0x1359d  stfld    int32 Microsoft.Crm.Application.Security.WrpcContext::_tokenExpiry
0x135a2  ldarg.0
0x135a3  ldarg.0
0x135a4  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x135a9  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x135ae  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheIgnoreToken()
0x135b3  callvirt instance object [System.Web]System.Web.HttpApplicationState::get_Item(string)
0x135b8  unbox.any [mscorlib]System.Boolean
0x135bd  stfld    bool Microsoft.Crm.Application.Security.WrpcContext::_isTokenCheckIgnored
0x135c2  ret
0x135c3  ldarg.0
0x135c4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x135c9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0x135ce  call     bool [Microsoft.Crm]Microsoft.Crm.ApplicationConfig::IsTokenCheckIgnored(valuetype [mscorlib]System.Guid)
0x135d3  stfld    bool Microsoft.Crm.Application.Security.WrpcContext::_isTokenCheckIgnored
0x135d8  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x135dd  brfalse.s loc_1363E
0x135df  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookFatClient()
0x135e4  brfalse.s loc_1363E
0x135e6  ldc.i4   0x400
0x135eb  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x135f0  stloc.0
0x135f1  ldloc.0
0x135f2  ldloc.0
0x135f3  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Capacity()
0x135f8  call     int32 NativeMethods::GetWRPCToken(class [mscorlib]System.Text.StringBuilder token, int32 size)
0x135fd  stloc.1
0x135fe  ldloc.1
0x135ff  ldloc.0
0x13600  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Capacity()
0x13605  ble.s    loc_1361B
0x13607  ldloc.0
0x13608  ldloc.1
0x13609  callvirt instance void [mscorlib]System.Text.StringBuilder::set_Capacity(int32)
0x1360e  ldloc.0
0x1360f  ldloc.0
0x13610  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Capacity()
0x13615  call     int32 NativeMethods::GetWRPCToken(class [mscorlib]System.Text.StringBuilder token, int32 size)
0x1361a  pop
0x1361b  ldarg.0
0x1361c  ldloc.0
0x1361d  callvirt instance string [mscorlib]System.Object::ToString()
0x13622  call     unsigned int8[] [Microsoft.Crm]Microsoft.Crm.CryptoRandom::ConvertKeyToBytes(string)
0x13627  stfld    unsigned int8[] Microsoft.Crm.Application.Security.WrpcContext::_tokenKey
0x1362c  ldarg.0
0x1362d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x13632  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_TokenExpiry()
0x13637  stfld    int32 Microsoft.Crm.Application.Security.WrpcContext::_tokenExpiry
0x1363c  br.s     loc_1369B
0x1363e  ldarg.0
0x1363f  ldc.i4.2
0x13640  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x13645  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x1364a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0x1364f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0x13654  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmKey [Microsoft.Crm.Core]Microsoft.Crm.CrmKey::GetActiveKey(valuetype [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyType, valuetype [mscorlib]System.Guid)
0x13659  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmKey Microsoft.Crm.Application.Security.WrpcContext::_wrpcCrmKey
0x1365e  ldarg.0
0x1365f  ldarg.0
0x13660  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmKey Microsoft.Crm.Application.Security.WrpcContext::_wrpcCrmKey
0x13665  ldc.i4.1
0x13666  newarr   [Microsoft.Crm.Core]Microsoft.Crm.HashParameterBase
0x1366b  dup
0x1366c  ldc.i4.0
0x1366d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x13672  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0x13677  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.GuidHashParameter::.ctor(valuetype [mscorlib]System.Guid)
0x1367c  stelem.ref
0x1367d  call     unsigned int8[] [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyService::ComputeHash(class [Microsoft.Crm.Core]Microsoft.Crm.CrmKey, class [Microsoft.Crm.Core]Microsoft.Crm.HashParameterBase[])
0x13682  stfld    unsigned int8[] Microsoft.Crm.Application.Security.WrpcContext::_tokenKey
0x13687  ldarg.0
0x13688  ldc.i4.2
0x13689  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmKeySetting [Microsoft.Crm.Core]Microsoft.Crm.CrmKeySetting::LoadKeySetting(valuetype [Microsoft.Crm.Core]Microsoft.Crm.CrmKeyType)
0x1368e  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmKeySetting::get_CryptoTimeToLive()
0x13693  ldc.i4.s 0x3C
0x13695  mul
0x13696  stfld    int32 Microsoft.Crm.Application.Security.WrpcContext::_tokenExpiry
0x1369b  ldarg.0
0x1369c  ldfld    unsigned int8[] Microsoft.Crm.Application.Security.WrpcContext::_tokenKey
0x136a1  brfalse.s loc_136AC
0x136a3  ldarg.0
0x136a4  ldfld    unsigned int8[] Microsoft.Crm.Application.Security.WrpcContext::_tokenKey
0x136a9  ldlen
0x136aa  brtrue.s loc_136BC
0x136ac  ldstr    aInvalidWrpcTok// "Invalid WRPC token key."
0x136b1  ldc.i4   0x80631109
0x136b6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x136bb  throw
0x136bc  ldarg.0
0x136bd  ldfld    int32 Microsoft.Crm.Application.Security.WrpcContext::_tokenExpiry
0x136c2  ldc.i4.5
0x136c3  blt.s    loc_136D2
0x136c5  ldarg.0
0x136c6  ldfld    int32 Microsoft.Crm.Application.Security.WrpcContext::_tokenExpiry
0x136cb  ldc.i4   0x2760
0x136d0  ble.s    loc_136E2
0x136d2  ldstr    aInvalidWrpcTok_0// "Invalid WRPC token expiry duration."
0x136d7  ldc.i4   0x80631108
0x136dc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x136e1  throw
0x136e2  ldarg.0
0x136e3  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x136e8  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x136ed  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenKey()
0x136f2  ldarg.0
0x136f3  ldfld    unsigned int8[] Microsoft.Crm.Application.Security.WrpcContext::_tokenKey
0x136f8  callvirt instance void [System.Web]System.Web.HttpApplicationState::set_Item(string, object)
0x136fd  ldarg.0
0x136fe  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13703  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x13708  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenExpiry()
0x1370d  ldarg.0
0x1370e  ldfld    int32 Microsoft.Crm.Application.Security.WrpcContext::_tokenExpiry
0x13713  box      [mscorlib]System.Int32
0x13718  callvirt instance void [System.Web]System.Web.HttpApplicationState::set_Item(string, object)
0x1371d  ldarg.0
0x1371e  ldfld    class [System.Web]System.Web.HttpContext Microsoft.Crm.Application.Security.WrpcContext::_context
0x13723  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x13728  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheIgnoreToken()
0x1372d  ldarg.0
0x1372e  ldfld    bool Microsoft.Crm.Application.Security.WrpcContext::_isTokenCheckIgnored
0x13733  box      [mscorlib]System.Boolean
0x13738  callvirt instance void [System.Web]System.Web.HttpApplicationState::set_Item(string, object)
0x1373d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13742  ldstr    aWrpcTokenReset// "WRPC Token Reset: TOKEN_EXPIRY={0}, IGN"...
0x13747  ldc.i4.3
0x13748  newarr   [mscorlib]System.Object
0x1374d  dup
0x1374e  ldc.i4.0
0x1374f  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x13754  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x13759  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenExpiry()
0x1375e  callvirt instance object [System.Web]System.Web.HttpApplicationState::get_Item(string)
0x13763  stelem.ref
0x13764  dup
0x13765  ldc.i4.1
0x13766  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1376b  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x13770  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheIgnoreToken()
0x13775  callvirt instance object [System.Web]System.Web.HttpApplicationState::get_Item(string)
0x1377a  stelem.ref
0x1377b  dup
0x1377c  ldc.i4.2
0x1377d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x13782  callvirt instance class [System.Web]System.Web.HttpApplicationState [System.Web]System.Web.HttpContext::get_Application()
0x13787  call     string Microsoft.Crm.Application.Security.WrpcContext::get_CacheTokenKey()
0x1378c  callvirt instance object [System.Web]System.Web.HttpApplicationState::get_Item(string)
0x13791  castclass unsigned int8[]
0x13796  call     string [Microsoft.Crm]Microsoft.Crm.CryptoRandom::ConvertKeyToString(unsigned int8[])
0x1379b  stelem.ref
0x1379c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x137a1  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Util::TraceInfo(string)
0x137a6  ret
```
