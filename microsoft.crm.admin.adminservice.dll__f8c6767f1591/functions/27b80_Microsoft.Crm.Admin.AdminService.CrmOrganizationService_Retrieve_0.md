# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Retrieve_0

- ea: `0x27b80`
- end: `0x27d96`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Retrieve_0`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x27750`

## callees

- `0x27b80`
- `0x28580`
- `0x29870`
- `0x29890`
- `0x298b0`
- `0x298d0`
- `0x298f0`
- `0x29910`
- `0x29930`

## string_xrefs

- `0x27cdb`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x27cfa`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x27b80  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x27b85  ldc.i4.s 0x14
0x27b87  ldstr    aRetrieveMultip_7// "Retrieve multiple organizations"
0x27b8c  ldc.i4.0
0x27b8d  newarr   [mscorlib]System.Object
0x27b92  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x27b97  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x27b9c  stloc.0
0x27b9d  ldnull
0x27b9e  stloc.1
0x27b9f  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x27ba4  stloc.2
0x27ba5  ldnull
0x27ba6  stloc.3
0x27ba7  ldarg.1
0x27ba8  brfalse  loc_27CE8
0x27bad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x27bb2  stloc.1
0x27bb3  ldarg.1
0x27bb4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_ScaleGroupId()
0x27bb9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x27bbe  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x27bc3  brfalse.s loc_27BDB
0x27bc5  ldloc.1
0x27bc6  ldstr    aScalegroupid_0// "ScaleGroupId"
0x27bcb  ldarg.1
0x27bcc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_ScaleGroupId()
0x27bd1  box      [mscorlib]System.Guid
0x27bd6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x27bdb  ldarg.1
0x27bdc  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState> Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_State()
0x27be1  stloc.s  5
0x27be3  ldloca.s 5
0x27be5  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>::get_HasValue()
0x27bea  brfalse.s loc_27C02
0x27bec  ldloc.1
0x27bed  ldstr    aState// "State"
0x27bf2  ldarg.1
0x27bf3  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState> Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_State()
0x27bf8  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState>
0x27bfd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x27c02  ldarg.1
0x27c03  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_SqlServerName()
0x27c08  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x27c0d  brtrue.s loc_27C20
0x27c0f  ldloc.1
0x27c10  ldstr    aSqlservername// "SqlServerName"
0x27c15  ldarg.1
0x27c16  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_SqlServerName()
0x27c1b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x27c20  ldarg.1
0x27c21  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_AvailabilityGroupName()
0x27c26  brfalse.s loc_27C39
0x27c28  ldloc.1
0x27c29  ldstr    aAvailabilitygr_1// "AvailabilityGroup"
0x27c2e  ldarg.1
0x27c2f  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_AvailabilityGroupName()
0x27c34  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x27c39  ldarg.1
0x27c3a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_DatacenterId()
0x27c3f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x27c44  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x27c49  brfalse.s loc_27C61
0x27c4b  ldloc.1
0x27c4c  ldstr    aDatacenterid_1// "DatacenterId"
0x27c51  ldarg.1
0x27c52  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_DatacenterId()
0x27c57  box      [mscorlib]System.Guid
0x27c5c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x27c61  ldarg.1
0x27c62  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_StorageGroupId()
0x27c67  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x27c6c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x27c71  brfalse.s loc_27C89
0x27c73  ldloc.1
0x27c74  ldstr    aStoragegroupid_0// "StorageGroupId"
0x27c79  ldarg.1
0x27c7a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_StorageGroupId()
0x27c7f  box      [mscorlib]System.Guid
0x27c84  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x27c89  ldarg.1
0x27c8a  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType> Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_OrganizationType()
0x27c8f  stloc.s  6
0x27c91  ldloca.s 6
0x27c93  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType>::get_HasValue()
0x27c98  brfalse.s loc_27CB0
0x27c9a  ldloc.1
0x27c9b  ldstr    aType// "Type"
0x27ca0  ldarg.1
0x27ca1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType> Microsoft.Crm.Admin.AdminService.OrganizationFilter::get_OrganizationType()
0x27ca6  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType>
0x27cab  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x27cb0  ldloc.1
0x27cb1  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Count()
0x27cb6  ldc.i4.0
0x27cb7  bgt.s    loc_27CBC
0x27cb9  ldnull
0x27cba  br.s     loc_27CC6
0x27cbc  ldc.i4.1
0x27cbd  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x27cc2  dup
0x27cc3  ldc.i4.0
0x27cc4  ldloc.1
0x27cc5  stelem.ref
0x27cc6  stloc.s  4
0x27cc8  ldloc.2
0x27cc9  ldstr    aOrganization// "Organization"
0x27cce  ldarg.0
0x27ccf  ldloc.s  4
0x27cd1  ldc.i4   0x5BA
0x27cd6  ldstr    aRetrieve// "Retrieve"
0x27cdb  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x27ce0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x27ce5  stloc.3
0x27ce6  br.s     loc_27D05
0x27ce8  ldloc.2
0x27ce9  ldstr    aOrganization// "Organization"
0x27cee  ldarg.0
0x27cef  ldnull
0x27cf0  ldc.i4   0x5BE
0x27cf5  ldstr    aRetrieve// "Retrieve"
0x27cfa  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x27cff  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x27d04  stloc.3
0x27d05  ldloc.3
0x27d06  brfalse.s loc_27D4B
0x27d08  ldloc.3
0x27d09  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x27d0e  stloc.s  7
0x27d10  br.s     loc_27D32
0x27d12  ldloca.s 7
0x27d14  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x27d19  stloc.s  9
0x27d1b  ldloca.s 9
0x27d1d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x27d22  newobj   instance void Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0x27d27  stloc.s  8
0x27d29  ldloc.0
0x27d2a  ldloc.s  8
0x27d2c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x27d31  pop
0x27d32  ldloca.s 7
0x27d34  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x27d39  brtrue.s loc_27D12
0x27d3b  leave.s  loc_27D4B
0x27d3d  ldloca.s 7
0x27d3f  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x27d45  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27d4a  endfinally
0x27d4b  ldloc.0
0x27d4c  ldtoken  Microsoft.Crm.Admin.AdminService.OrganizationData
0x27d51  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27d56  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x27d5b  castclass class Microsoft.Crm.Admin.AdminService.OrganizationData[]
0x27d60  stloc.s  0xA
0x27d62  leave.s  loc_27D93
0x27d64  ldloc.2
0x27d65  brfalse.s loc_27D6D
0x27d67  ldloc.2
0x27d68  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27d6d  endfinally
0x27d6e  stloc.s  0xB
0x27d70  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x27d75  ldc.i4.s 0x14
0x27d77  ldstr    aExceptionInRet_16// "Exception in retrieve multiple organiza"...
0x27d7c  ldc.i4.1
0x27d7d  newarr   [mscorlib]System.Object
0x27d82  dup
0x27d83  ldc.i4.0
0x27d84  ldloc.s  0xB
0x27d86  callvirt instance string [mscorlib]System.Exception::get_Message()
0x27d8b  stelem.ref
0x27d8c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x27d91  rethrow
0x27d93  ldloc.s  0xA
0x27d95  ret
```
