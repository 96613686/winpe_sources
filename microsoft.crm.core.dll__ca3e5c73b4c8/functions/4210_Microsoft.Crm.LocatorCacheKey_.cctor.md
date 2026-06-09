# Microsoft.Crm.LocatorCacheKey::.cctor

- ea: `0x4210`
- end: `0x43fe`
- name: `Microsoft.Crm.LocatorCacheKey::.cctor`
- size: `494`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x4410`

## string_xrefs

- `0x427c`: `CrmSiteSettingId`
- `0x432b`: `CrmServiceApplicationId`
- `0x433a`: `IsRedisCacheEnabledForScaleGroup`

## pseudocode

```c

```

## disassembly

```asm
0x4210  ldc.i4.s 0x14
0x4212  newarr   Microsoft.Crm.FixedCacheKey
0x4217  dup
0x4218  ldc.i4.0
0x4219  ldstr    aCrmuserorganiz_1// "CrmUserOrganizations"
0x421e  ldc.i4.3
0x421f  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4224  stelem.ref
0x4225  dup
0x4226  ldc.i4.1
0x4227  ldstr    aCrmuserauthent// "CrmUserAuthentication"
0x422c  ldc.i4.4
0x422d  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4232  stelem.ref
0x4233  dup
0x4234  ldc.i4.2
0x4235  ldstr    aCrmuserid// "CrmUserId"
0x423a  ldc.i4.5
0x423b  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4240  stelem.ref
0x4241  dup
0x4242  ldc.i4.3
0x4243  ldstr    aCrmdeploymento// "CrmDeploymentOrganizations"
0x4248  ldc.i4.6
0x4249  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x424e  stelem.ref
0x424f  dup
0x4250  ldc.i4.4
0x4251  ldstr    aCrmallorganiza// "CrmAllOrganizations"
0x4256  ldc.i4.7
0x4257  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x425c  stelem.ref
0x425d  dup
0x425e  ldc.i4.5
0x425f  ldstr    aCrmdeploymenti// "CrmDeploymentId"
0x4264  ldc.i4.8
0x4265  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x426a  stelem.ref
0x426b  dup
0x426c  ldc.i4.6
0x426d  ldstr    aCrmscalegroupi// "CrmScaleGroupId"
0x4272  ldc.i4.s 9
0x4274  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4279  stelem.ref
0x427a  dup
0x427b  ldc.i4.7
0x427c  ldstr    aCrmsitesetting// "CrmSiteSettingId"
0x4281  ldc.i4.s 0xA
0x4283  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4288  stelem.ref
0x4289  dup
0x428a  ldc.i4.8
0x428b  ldstr    aCrmuseridorgan// "CrmUserIdOrganizations"
0x4290  ldc.i4.s 0xB
0x4292  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4297  stelem.ref
0x4298  dup
0x4299  ldc.i4.s 9
0x429b  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x42a0  ldc.i4.s 0xC
0x42a2  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x42a7  stelem.ref
0x42a8  dup
0x42a9  ldc.i4.s 0xA
0x42ab  ldstr    aFullyloadedorg// "FullyLoadedOrganizationDomainNameToIdKe"...
0x42b0  ldc.i4.s 0x10
0x42b2  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x42b7  stelem.ref
0x42b8  dup
0x42b9  ldc.i4.s 0xB
0x42bb  ldstr    aCrmorganizatio_0// "CrmOrganizationIdAll"
0x42c0  ldc.i4.s 0xD
0x42c2  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x42c7  stelem.ref
0x42c8  dup
0x42c9  ldc.i4.s 0xC
0x42cb  ldstr    aOrganizationid// "OrganizationIdToUniqueNamesKey"
0x42d0  ldc.i4.s 0x17
0x42d2  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x42d7  stelem.ref
0x42d8  dup
0x42d9  ldc.i4.s 0xD
0x42db  ldstr    aCrmserverid// "CrmServerId"
0x42e0  ldc.i4.s 0xE
0x42e2  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x42e7  stelem.ref
0x42e8  dup
0x42e9  ldc.i4.s 0xE
0x42eb  ldstr    aFederationprov_0// "FederationProviderId"
0x42f0  ldc.i4.s 0x11
0x42f2  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x42f7  stelem.ref
0x42f8  dup
0x42f9  ldc.i4.s 0xF
0x42fb  ldstr    aCrmuserinvitat// "CrmUserInvitation"
0x4300  ldc.i4.s 0xF
0x4302  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4307  stelem.ref
0x4308  dup
0x4309  ldc.i4.s 0x10
0x430b  ldstr    aCrmpodid// "CrmPodId"
0x4310  ldc.i4.s 0x12
0x4312  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4317  stelem.ref
0x4318  dup
0x4319  ldc.i4.s 0x11
0x431b  ldstr    aCrmdatacenteri// "CrmDatacenterId"
0x4320  ldc.i4.s 0x13
0x4322  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4327  stelem.ref
0x4328  dup
0x4329  ldc.i4.s 0x12
0x432b  ldstr    aCrmserviceappl// "CrmServiceApplicationId"
0x4330  ldc.i4.5
0x4331  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4336  stelem.ref
0x4337  dup
0x4338  ldc.i4.s 0x13
0x433a  ldstr    aIsrediscacheen// "IsRedisCacheEnabledForScaleGroup"
0x433f  ldc.i4.s 0x15
0x4341  newobj   instance void Microsoft.Crm.FixedCacheKey::.ctor(string keyName, valuetype Microsoft.Crm.LocatorKeyType keyType)
0x4346  stelem.ref
0x4347  stsfld   class Microsoft.Crm.FixedCacheKey[] Microsoft.Crm.LocatorCacheKey::FixedCacheKeys
0x434c  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.Crm.LocatorKeyType>::.ctor()
0x4351  dup
0x4352  ldc.i4.8
0x4353  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.Crm.LocatorKeyType>::Add(var<u1>)
0x4358  pop
0x4359  dup
0x435a  ldc.i4.s 0x13
0x435c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.Crm.LocatorKeyType>::Add(var<u1>)
0x4361  pop
0x4362  dup
0x4363  ldc.i4.s 9
0x4365  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.Crm.LocatorKeyType>::Add(var<u1>)
0x436a  pop
0x436b  dup
0x436c  ldc.i4.s 0xA
0x436e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.Crm.LocatorKeyType>::Add(var<u1>)
0x4373  pop
0x4374  dup
0x4375  ldc.i4.s 0xE
0x4377  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.Crm.LocatorKeyType>::Add(var<u1>)
0x437c  pop
0x437d  stsfld   class [System]System.Collections.Generic.ISet`1<valuetype Microsoft.Crm.LocatorKeyType> Microsoft.Crm.LocatorCacheKey::SyncKeyTypes
0x4382  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x4387  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x438c  dup
0x438d  ldstr    aScalegroupdepl// "ScaleGroupDeployment"
0x4392  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x4397  pop
0x4398  dup
0x4399  ldstr    aServersettings// "ServerSettings"
0x439e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x43a3  pop
0x43a4  dup
0x43a5  ldstr    aDeployment// "Deployment"
0x43aa  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x43af  pop
0x43b0  dup
0x43b1  ldstr    aServer// "Server"
0x43b6  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x43bb  pop
0x43bc  dup
0x43bd  ldstr    aScalegroup// "ScaleGroup"
0x43c2  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x43c7  pop
0x43c8  dup
0x43c9  ldstr    aFeaturecontrol// "FeatureControl"
0x43ce  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x43d3  pop
0x43d4  dup
0x43d5  ldstr    aFeaturecontrol_0// "FeatureControlDefinition"
0x43da  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x43df  pop
0x43e0  dup
0x43e1  ldstr    aFeaturecontrol_1// "FeatureControlVersionsMapping"
0x43e6  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x43eb  pop
0x43ec  dup
0x43ed  ldstr    aDatacenter// "Datacenter"
0x43f2  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x43f7  pop
0x43f8  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.Crm.LocatorCacheKey::SyncTables
0x43fd  ret
```
