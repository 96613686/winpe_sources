# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::SetOrganizationResources

- ea: `0x12a20`
- end: `0x12dc1`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::SetOrganizationResources`
- size: `929`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x12dd0`

## callees

- `0x12a20`
- `0x13190`
- `0x131c0`

## string_xrefs

- `0x12a5d`: `ServiceComponentId`
- `0x12ae5`: `ServiceComponentId`
- `0x12b4a`: `ServiceComponentId`
- `0x12b51`: `ServiceComponentId`
- `0x12b9c`: `ServiceComponentId`
- `0x12c01`: `ServiceComponentId`
- `0x12c70`: `ServiceComponentId`
- `0x12d02`: `ServiceComponentId`
- `0x12ad0`: `ServiceComponentSku`
- `0x12aa9`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x12af5`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x12b89`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x12c97`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x12d1f`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x12d93`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x12a20  ldstr    aSetorganizatio// "SetOrganizationResources_"
0x12a25  ldarga.s 0
0x12a27  constrained. [mscorlib]System.Guid
0x12a2d  callvirt instance string [mscorlib]System.Object::ToString()
0x12a32  call     string [mscorlib]System.String::Concat(string, string)
0x12a37  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLock(string)
0x12a3c  stloc.0
0x12a3d  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x12a42  stloc.1
0x12a43  ldc.i4.0
0x12a44  stloc.2
0x12a45  ldarga.s 4
0x12a47  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x12a4c  brtrue.s loc_12A56
0x12a4e  ldarg.2
0x12a4f  ldarg.3
0x12a50  call     int32 Microsoft.Crm.CrmLive.Services.ServiceInstanceService::DetermineChangeValue(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus statusCode, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus oldStatusCode)
0x12a55  stloc.2
0x12a56  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12a5b  stloc.3
0x12a5c  ldloc.3
0x12a5d  ldstr    aServicecompone// "ServiceComponentId"
0x12a62  ldarg.1
0x12a63  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12a68  ldloc.3
0x12a69  ldstr    aOrganizationid_0// "OrganizationId"
0x12a6e  ldarg.0
0x12a6f  box      [mscorlib]System.Guid
0x12a74  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12a79  ldloc.1
0x12a7a  ldstr    aOrganizationre// "OrganizationResources"
0x12a7f  ldc.i4.2
0x12a80  newarr   [mscorlib]System.String
0x12a85  dup
0x12a86  ldc.i4.0
0x12a87  ldstr    aId// "Id"
0x12a8c  stelem.ref
0x12a8d  dup
0x12a8e  ldc.i4.1
0x12a8f  ldstr    aCount// "Count"
0x12a94  stelem.ref
0x12a95  ldc.i4.1
0x12a96  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x12a9b  dup
0x12a9c  ldc.i4.0
0x12a9d  ldloc.3
0x12a9e  stelem.ref
0x12a9f  ldc.i4   0x90
0x12aa4  ldstr    aSetorganizatio_0// "SetOrganizationResources"
0x12aa9  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12aae  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x12ab3  stloc.s  4
0x12ab5  ldnull
0x12ab6  stloc.s  5
0x12ab8  ldloc.s  4
0x12aba  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x12abf  brtrue.s loc_12ACF
0x12ac1  ldloc.s  4
0x12ac3  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x12ac8  call     T0x2B00005D
0x12acd  stloc.s  5
0x12acf  ldloc.1
0x12ad0  ldstr    aServicecompone_4// "ServiceComponentSku"
0x12ad5  ldc.i4.2
0x12ad6  newarr   [mscorlib]System.String
0x12adb  dup
0x12adc  ldc.i4.0
0x12add  ldstr    aName// "Name"
0x12ae2  stelem.ref
0x12ae3  dup
0x12ae4  ldc.i4.1
0x12ae5  ldstr    aServicecompone// "ServiceComponentId"
0x12aea  stelem.ref
0x12aeb  ldc.i4   0x9A
0x12af0  ldstr    aSetorganizatio_0// "SetOrganizationResources"
0x12af5  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12afa  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], int32, string, string)
0x12aff  stloc.s  6
0x12b01  ldnull
0x12b02  stloc.s  7
0x12b04  ldnull
0x12b05  stloc.s  8
0x12b07  ldloc.s  6
0x12b09  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x12b0e  brtrue   loc_12BDE
0x12b13  ldloc.s  6
0x12b15  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x12b1a  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x12b1f  stloc.s  0xA
0x12b21  br       loc_12BC2
0x12b26  ldloca.s 0xA
0x12b28  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x12b2d  stloc.s  0xB
0x12b2f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12b34  stloc.s  0xC
0x12b36  ldloc.s  0xC
0x12b38  ldstr    aOrganizationid_0// "OrganizationId"
0x12b3d  ldarg.0
0x12b3e  box      [mscorlib]System.Guid
0x12b43  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12b48  ldloc.s  0xC
0x12b4a  ldstr    aServicecompone// "ServiceComponentId"
0x12b4f  ldloc.s  0xB
0x12b51  ldstr    aServicecompone// "ServiceComponentId"
0x12b56  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12b5b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12b60  ldloc.1
0x12b61  ldstr    aOrganizationre// "OrganizationResources"
0x12b66  ldc.i4.1
0x12b67  newarr   [mscorlib]System.String
0x12b6c  dup
0x12b6d  ldc.i4.0
0x12b6e  ldstr    aId// "Id"
0x12b73  stelem.ref
0x12b74  ldc.i4.1
0x12b75  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x12b7a  dup
0x12b7b  ldc.i4.0
0x12b7c  ldloc.s  0xC
0x12b7e  stelem.ref
0x12b7f  ldc.i4   0xA7
0x12b84  ldstr    aSetorganizatio_0// "SetOrganizationResources"
0x12b89  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12b8e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x12b93  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x12b98  brtrue.s loc_12BC2
0x12b9a  ldloc.s  0xB
0x12b9c  ldstr    aServicecompone// "ServiceComponentId"
0x12ba1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12ba6  castclass [mscorlib]System.String
0x12bab  stloc.s  8
0x12bad  ldloc.s  0xB
0x12baf  ldstr    aName// "Name"
0x12bb4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12bb9  castclass [mscorlib]System.String
0x12bbe  stloc.s  7
0x12bc0  leave.s  loc_12BDE
0x12bc2  ldloca.s 0xA
0x12bc4  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x12bc9  brtrue   loc_12B26
0x12bce  leave.s  loc_12BDE
0x12bd0  ldloca.s 0xA
0x12bd2  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x12bd8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12bdd  endfinally
0x12bde  ldc.i4.0
0x12bdf  stloc.s  9
0x12be1  ldloc.s  6
0x12be3  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x12be8  brtrue.s loc_12C37
0x12bea  ldloc.s  6
0x12bec  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x12bf1  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x12bf6  stloc.s  0xA
0x12bf8  br.s     loc_12C1E
0x12bfa  ldloca.s 0xA
0x12bfc  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x12c01  ldstr    aServicecompone// "ServiceComponentId"
0x12c06  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12c0b  castclass [mscorlib]System.String
0x12c10  ldarg.1
0x12c11  ldc.i4.5
0x12c12  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x12c17  brfalse.s loc_12C1E
0x12c19  ldc.i4.1
0x12c1a  stloc.s  9
0x12c1c  leave.s  loc_12C37
0x12c1e  ldloca.s 0xA
0x12c20  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x12c25  brtrue.s loc_12BFA
0x12c27  leave.s  loc_12C37
0x12c29  ldloca.s 0xA
0x12c2b  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x12c31  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12c36  endfinally
0x12c37  ldloc.s  7
0x12c39  ldnull
0x12c3a  cgt.un
0x12c3c  ldloc.s  9
0x12c3e  and
0x12c3f  brfalse.s loc_12CA2
0x12c41  ldloc.s  8
0x12c43  ldarg.1
0x12c44  ldc.i4.5
0x12c45  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x12c4a  brtrue.s loc_12CA2
0x12c4c  ldarg.2
0x12c4d  ldc.i4.1
0x12c4e  beq.s    loc_12C55
0x12c50  leave    loc_12DC0
0x12c55  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12c5a  stloc.s  0xD
0x12c5c  ldloc.s  0xD
0x12c5e  ldstr    aOrganizationid_0// "OrganizationId"
0x12c63  ldarg.0
0x12c64  box      [mscorlib]System.Guid
0x12c69  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12c6e  ldloc.s  0xD
0x12c70  ldstr    aServicecompone// "ServiceComponentId"
0x12c75  ldloc.s  8
0x12c77  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12c7c  ldloc.1
0x12c7d  ldstr    aOrganizationre// "OrganizationResources"
0x12c82  ldc.i4.1
0x12c83  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x12c88  dup
0x12c89  ldc.i4.0
0x12c8a  ldloc.s  0xD
0x12c8c  stelem.ref
0x12c8d  ldc.i4   0xCF
0x12c92  ldstr    aSetorganizatio_0// "SetOrganizationResources"
0x12c97  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12c9c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x12ca1  pop
0x12ca2  ldloc.s  5
0x12ca4  brtrue   loc_12D2F
0x12ca9  ldarg.2
0x12caa  ldc.i4.1
0x12cab  beq.s    loc_12CB8
0x12cad  ldstr    a15001CannotIns// "15001 - Cannot insert record with a lic"...
0x12cb2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x12cb7  throw
0x12cb8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12cbd  stloc.s  0xE
0x12cbf  ldloc.s  0xE
0x12cc1  ldstr    aCount// "Count"
0x12cc6  ldarga.s 4
0x12cc8  ldloc.2
0x12cc9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault(!!T0)
0x12cce  box      [mscorlib]System.Int32
0x12cd3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12cd8  ldloc.s  0xE
0x12cda  ldstr    aId// "Id"
0x12cdf  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x12ce4  box      [mscorlib]System.Guid
0x12ce9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12cee  ldloc.s  0xE
0x12cf0  ldstr    aOrganizationid_0// "OrganizationId"
0x12cf5  ldarg.0
0x12cf6  box      [mscorlib]System.Guid
0x12cfb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12d00  ldloc.s  0xE
0x12d02  ldstr    aServicecompone// "ServiceComponentId"
0x12d07  ldarg.1
0x12d08  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12d0d  ldloc.1
0x12d0e  ldstr    aOrganizationre// "OrganizationResources"
0x12d13  ldloc.s  0xE
0x12d15  ldc.i4   0xE1
0x12d1a  ldstr    aSetorganizatio_0// "SetOrganizationResources"
0x12d1f  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12d24  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x12d29  pop
0x12d2a  leave    loc_12DC0
0x12d2f  ldarga.s 4
0x12d31  ldloc.s  5
0x12d33  ldstr    aCount// "Count"
0x12d38  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12d3d  unbox.any [mscorlib]System.Int32
0x12d42  ldloc.2
0x12d43  add
0x12d44  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault(!!T0)
0x12d49  stloc.s  0xF
0x12d4b  ldloc.s  0xF
0x12d4d  ldc.i4.0
0x12d4e  bge.s    loc_12D5B
0x12d50  ldstr    a15001CannotRed// "15001 - Cannot reduce count below 0"
0x12d55  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x12d5a  throw
0x12d5b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12d60  stloc.s  0x10
0x12d62  ldloc.s  0x10
0x12d64  ldstr    aCount// "Count"
0x12d69  ldloc.s  0xF
0x12d6b  box      [mscorlib]System.Int32
0x12d70  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12d75  ldloc.1
0x12d76  ldstr    aOrganizationre// "OrganizationResources"
0x12d7b  ldloc.s  5
0x12d7d  ldstr    aId// "Id"
0x12d82  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12d87  ldloc.s  0x10
0x12d89  ldc.i4   0xEF
0x12d8e  ldstr    aSetorganizatio_0// "SetOrganizationResources"
0x12d93  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12d98  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x12d9d  pop
0x12d9e  ldloc.2
0x12d9f  ldloc.s  0xF
0x12da1  ldarg.1
0x12da2  ldarg.0
0x12da3  ldloc.s  7
0x12da5  call     void Microsoft.Crm.CrmLive.Services.ServiceInstanceService::UpdateUserPurchaseCount(int32 change, int32 newCount, string serviceComponentId, valuetype [mscorlib]System.Guid orgId, string skuName)
0x12daa  leave.s  loc_12DC0
0x12dac  ldloc.1
0x12dad  brfalse.s loc_12DB5
0x12daf  ldloc.1
0x12db0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12db5  endfinally
0x12db6  ldloc.0
  ... truncated ...
```
