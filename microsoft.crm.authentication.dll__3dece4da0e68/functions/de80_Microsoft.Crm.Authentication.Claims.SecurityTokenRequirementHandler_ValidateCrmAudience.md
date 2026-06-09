# Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateCrmAudience

- ea: `0xde80`
- end: `0xdff5`
- name: `Microsoft.Crm.Authentication.Claims.SecurityTokenRequirementHandler::ValidateCrmAudience`
- size: `373`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xde30`
- `0xe000`

## callees

- `0xcb0`
- `0x1980`
- `0xc080`
- `0xde80`
- `0x150e0`

## pseudocode

```c

```

## disassembly

```asm
0xde80  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::.ctor()
0xde85  stloc.0
0xde86  ldarg.0
0xde87  brfalse  loc_DFF3
0xde8c  ldarg.1
0xde8d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xde92  ldc.i4.2
0xde93  callvirt instance class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::GetDiscoveryServiceUrl(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.WebServices.EndpointVersion)
0xde98  newobj   instance void [System]System.UriBuilder::.ctor(class [System]System.Uri)
0xde9d  stloc.1
0xde9e  ldnull
0xde9f  stloc.2
0xdea0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xdea5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xdeaa  ldc.i4.2
0xdeab  bne.un.s loc_DECF
0xdead  ldarg.1
0xdeae  callvirt instance class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::GetOSDPDiscoveryServiceUrl()
0xdeb3  newobj   instance void [System]System.UriBuilder::.ctor(class [System]System.Uri)
0xdeb8  stloc.2
0xdeb9  ldloc.2
0xdeba  ldsfld   string [mscorlib]System.String::Empty
0xdebf  callvirt instance void [System]System.UriBuilder::set_Path(string)
0xdec4  ldloc.2
0xdec5  ldsfld   string [mscorlib]System.String::Empty
0xdeca  callvirt instance void [System]System.UriBuilder::set_Query(string)
0xdecf  ldloc.1
0xded0  ldsfld   string [mscorlib]System.String::Empty
0xded5  callvirt instance void [System]System.UriBuilder::set_Path(string)
0xdeda  ldloc.1
0xdedb  ldsfld   string [mscorlib]System.String::Empty
0xdee0  callvirt instance void [System]System.UriBuilder::set_Query(string)
0xdee5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xdeea  pop
0xdeeb  ldarg.2
0xdeec  ldnull
0xdeed  cgt.un
0xdeef  stloc.3
0xdef0  ldarg.0
0xdef1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Uri>::GetEnumerator()
0xdef6  stloc.s  4
0xdef8  br       loc_DFD9
0xdefd  newobj   instance void <>c__DisplayClass5_0::.ctor()
0xdf02  stloc.s  5
0xdf04  ldloc.s  5
0xdf06  ldloc.s  4
0xdf08  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Uri>::get_Current()
0xdf0d  stfld    class [System]System.Uri <>c__DisplayClass5_0::uri
0xdf12  ldloc.3
0xdf13  brfalse.s loc_DF2D
0xdf15  ldarg.2
0xdf16  ldloc.s  5
0xdf18  ldftn    instance bool <>c__DisplayClass5_0::<ValidateCrmAudience>b__0(class [System]System.Uri u)
0xdf1e  newobj   instance void class [mscorlib]System.Func`2<class [System]System.Uri, bool>::.ctor(object, native int)
0xdf23  call     T0x2B000021
0xdf28  brtrue   loc_DFD9
0xdf2d  ldloc.s  5
0xdf2f  ldfld    class [System]System.Uri <>c__DisplayClass5_0::uri
0xdf34  call     class [System]System.Uri Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_ExternalRelyingPartyUrl()
0xdf39  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0xdf3e  brtrue   loc_DFD9
0xdf43  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xdf48  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xdf4d  ldc.i4.2
0xdf4e  bne.un.s loc_DF5E
0xdf50  ldloc.s  5
0xdf52  ldfld    class [System]System.Uri <>c__DisplayClass5_0::uri
0xdf57  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::IsOnlinePortalHomePageRequest(class [System]System.Uri uri)
0xdf5c  brtrue.s loc_DFD9
0xdf5e  ldloc.1
0xdf5f  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0xdf64  ldloc.s  5
0xdf66  ldfld    class [System]System.Uri <>c__DisplayClass5_0::uri
0xdf6b  callvirt instance bool [System]System.Uri::IsBaseOf(class [System]System.Uri)
0xdf70  brtrue.s loc_DFD9
0xdf72  ldloc.2
0xdf73  brfalse.s loc_DF89
0xdf75  ldloc.2
0xdf76  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0xdf7b  ldloc.s  5
0xdf7d  ldfld    class [System]System.Uri <>c__DisplayClass5_0::uri
0xdf82  callvirt instance bool [System]System.Uri::IsBaseOf(class [System]System.Uri)
0xdf87  brtrue.s loc_DFD9
0xdf89  ldloc.s  5
0xdf8b  ldfld    class [System]System.Uri <>c__DisplayClass5_0::uri
0xdf90  ldloc.1
0xdf91  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0xdf96  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xdf9b  brtrue.s loc_DFD9
0xdf9d  ldloc.2
0xdf9e  brfalse.s loc_DFB4
0xdfa0  ldloc.s  5
0xdfa2  ldfld    class [System]System.Uri <>c__DisplayClass5_0::uri
0xdfa7  ldloc.2
0xdfa8  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0xdfad  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xdfb2  brtrue.s loc_DFD9
0xdfb4  ldloc.s  5
0xdfb6  ldfld    class [System]System.Uri <>c__DisplayClass5_0::uri
0xdfbb  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetOrganizationId(class [System]System.Uri uri)
0xdfc0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xdfc5  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xdfca  brfalse.s loc_DFD9
0xdfcc  ldloc.0
0xdfcd  ldloc.s  5
0xdfcf  ldfld    class [System]System.Uri <>c__DisplayClass5_0::uri
0xdfd4  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System]System.Uri>::Add(var<u1>)
0xdfd9  ldloc.s  4
0xdfdb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xdfe0  brtrue   loc_DEFD
0xdfe5  leave.s  loc_DFF3
0xdfe7  ldloc.s  4
0xdfe9  brfalse.s loc_DFF2
0xdfeb  ldloc.s  4
0xdfed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdff2  endfinally
0xdff3  ldloc.0
0xdff4  ret
```
