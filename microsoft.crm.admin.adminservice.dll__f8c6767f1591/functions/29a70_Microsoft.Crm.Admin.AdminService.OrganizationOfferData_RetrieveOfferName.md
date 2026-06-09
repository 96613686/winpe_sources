# Microsoft.Crm.Admin.AdminService.OrganizationOfferData::RetrieveOfferName

- ea: `0x29a70`
- end: `0x29b7b`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationOfferData::RetrieveOfferName`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x29a30`

## callees

- `0x29a70`

## string_xrefs

- `0x29a84`: `ServiceComponentId`
- `0x29aec`: `ServiceComponentId`
- `0x29af3`: `ServiceComponentId`
- `0x29a77`: `ServiceComponentSku`
- `0x29b03`: `ServiceInstance`

## pseudocode

```c

```

## disassembly

```asm
0x29a70  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x29a75  stloc.0
0x29a76  ldloc.0
0x29a77  ldstr    aServicecompone_4// "ServiceComponentSku"
0x29a7c  ldc.i4.2
0x29a7d  newarr   [mscorlib]System.String
0x29a82  dup
0x29a83  ldc.i4.0
0x29a84  ldstr    aServicecompone// "ServiceComponentId"
0x29a89  stelem.ref
0x29a8a  dup
0x29a8b  ldc.i4.1
0x29a8c  ldstr    aName// "Name"
0x29a91  stelem.ref
0x29a92  ldc.i4.s 0x43
0x29a94  ldstr    aRetrieveoffern// "RetrieveOfferName"
0x29a99  ldstr    aDA1SSrcCrmlive_51// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x29a9e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], int32, string, string)
0x29aa3  stloc.1
0x29aa4  ldloc.1
0x29aa5  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x29aaa  brfalse.s loc_29AB7
0x29aac  ldsfld   string [mscorlib]System.String::Empty
0x29ab1  stloc.2
0x29ab2  leave    loc_29B79
0x29ab7  ldloc.1
0x29ab8  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x29abd  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x29ac2  stloc.3
0x29ac3  br       loc_29B4D
0x29ac8  ldloca.s 3
0x29aca  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x29acf  stloc.s  4
0x29ad1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x29ad6  stloc.s  5
0x29ad8  ldloc.s  5
0x29ada  ldstr    aOrganizationid_0// "OrganizationId"
0x29adf  ldarg.0
0x29ae0  box      [mscorlib]System.Guid
0x29ae5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x29aea  ldloc.s  5
0x29aec  ldstr    aServicecompone// "ServiceComponentId"
0x29af1  ldloc.s  4
0x29af3  ldstr    aServicecompone// "ServiceComponentId"
0x29af8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x29afd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x29b02  ldloc.0
0x29b03  ldstr    aServiceinstanc// "ServiceInstance"
0x29b08  ldc.i4.1
0x29b09  newarr   [mscorlib]System.String
0x29b0e  dup
0x29b0f  ldc.i4.0
0x29b10  ldstr    aId// "Id"
0x29b15  stelem.ref
0x29b16  ldc.i4.1
0x29b17  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x29b1c  dup
0x29b1d  ldc.i4.0
0x29b1e  ldloc.s  5
0x29b20  stelem.ref
0x29b21  ldc.i4.s 0x50
0x29b23  ldstr    aRetrieveoffern// "RetrieveOfferName"
0x29b28  ldstr    aDA1SSrcCrmlive_51// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x29b2d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x29b32  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x29b37  brtrue.s loc_29B4D
0x29b39  ldloc.s  4
0x29b3b  ldstr    aName// "Name"
0x29b40  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x29b45  castclass [mscorlib]System.String
0x29b4a  stloc.2
0x29b4b  leave.s  loc_29B79
0x29b4d  ldloca.s 3
0x29b4f  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x29b54  brtrue   loc_29AC8
0x29b59  leave.s  loc_29B73
0x29b5b  ldloca.s 3
0x29b5d  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x29b63  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29b68  endfinally
0x29b69  ldloc.0
0x29b6a  brfalse.s loc_29B72
0x29b6c  ldloc.0
0x29b6d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29b72  endfinally
0x29b73  ldsfld   string [mscorlib]System.String::Empty
0x29b78  ret
0x29b79  ldloc.2
0x29b7a  ret
```
