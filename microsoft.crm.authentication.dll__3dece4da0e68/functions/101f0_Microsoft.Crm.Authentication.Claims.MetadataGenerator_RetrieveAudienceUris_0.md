# Microsoft.Crm.Authentication.Claims.MetadataGenerator::RetrieveAudienceUris_0

- ea: `0x101f0`
- end: `0x10289`
- name: `Microsoft.Crm.Authentication.Claims.MetadataGenerator::RetrieveAudienceUris_0`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x101d0`

## callees

- `0x101f0`
- `0x10290`

## pseudocode

```c

```

## disassembly

```asm
0x101f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::.ctor()
0x101f5  stloc.0
0x101f6  ldarg.0
0x101f7  brfalse  loc_10282
0x101fc  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationStateInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStateInfoProvider::get_Instance()
0x10201  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationStateInfoProvider::GetEnabledOrganizationsIds()
0x10206  stloc.1
0x10207  ldloc.1
0x10208  brfalse.s loc_10258
0x1020a  ldloc.1
0x1020b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/KeyCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Keys()
0x10210  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/KeyCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x10215  stloc.2
0x10216  br.s     loc_1023F
0x10218  ldloca.s 2
0x1021a  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/KeyCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x1021f  unbox.any [mscorlib]System.Guid
0x10224  stloc.3
0x10225  ldarg.0
0x10226  ldloc.3
0x10227  callvirt instance class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::GetCrmServiceUrl(valuetype [mscorlib]System.Guid)
0x1022c  ldloc.0
0x1022d  call     void Microsoft.Crm.Authentication.Claims.MetadataGenerator::AddServiceUri(class [System]System.Uri serviceUri, class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri> uris)
0x10232  ldarg.0
0x10233  ldloc.3
0x10234  callvirt instance class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::GetWebApplicationUrl(valuetype [mscorlib]System.Guid)
0x10239  ldloc.0
0x1023a  call     void Microsoft.Crm.Authentication.Claims.MetadataGenerator::AddServiceUri(class [System]System.Uri serviceUri, class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri> uris)
0x1023f  ldloca.s 2
0x10241  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/KeyCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x10246  brtrue.s loc_10218
0x10248  leave.s  loc_10258
0x1024a  ldloca.s 2
0x1024c  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/KeyCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x10252  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10257  endfinally
0x10258  ldarg.0
0x10259  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1025e  callvirt instance class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::GetDiscoveryServiceUrl(valuetype [mscorlib]System.Guid)
0x10263  ldloc.0
0x10264  call     void Microsoft.Crm.Authentication.Claims.MetadataGenerator::AddServiceUri(class [System]System.Uri serviceUri, class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri> uris)
0x10269  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x1026e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x10273  ldc.i4.2
0x10274  bne.un.s loc_10282
0x10276  ldarg.0
0x10277  callvirt instance class [System]System.Uri [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider::GetOSDPDiscoveryServiceUrl()
0x1027c  ldloc.0
0x1027d  call     void Microsoft.Crm.Authentication.Claims.MetadataGenerator::AddServiceUri(class [System]System.Uri serviceUri, class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri> uris)
0x10282  ldloc.0
0x10283  newobj   instance void class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System]System.Uri>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x10288  ret
```
