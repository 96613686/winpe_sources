# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetSecondaryDatacenterId

- ea: `0x26660`
- end: `0x268ad`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetSecondaryDatacenterId`
- size: `589`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x26580`
- `0x26660`

## string_xrefs

- `0x26695`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x2670d`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x267ae`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x2680c`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x26660  ldarg.1
0x26661  ldstr    aOrganizationid// "organizationId"
0x26666  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2666b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x26670  stloc.0
0x26671  ldloc.0
0x26672  ldstr    aOrganization// "Organization"
0x26677  ldarg.1
0x26678  box      [mscorlib]System.Guid
0x2667d  ldc.i4.1
0x2667e  newarr   [mscorlib]System.String
0x26683  dup
0x26684  ldc.i4.0
0x26685  ldstr    aAvailabilitygr_1// "AvailabilityGroup"
0x2668a  stelem.ref
0x2668b  ldc.i4   0x1FD
0x26690  ldstr    aGetsecondaryda// "GetSecondaryDatacenterId"
0x26695  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2669a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x2669f  stloc.1
0x266a0  ldloc.1
0x266a1  brtrue.s loc_266AF
0x266a3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x266a8  stloc.s  0xB
0x266aa  leave    loc_268AA
0x266af  ldloc.1
0x266b0  ldstr    aAvailabilitygr_1// "AvailabilityGroup"
0x266b5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x266ba  castclass [mscorlib]System.String
0x266bf  stloc.2
0x266c0  ldloc.2
0x266c1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x266c6  brfalse.s loc_266D4
0x266c8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x266cd  stloc.s  0xB
0x266cf  leave    loc_268AA
0x266d4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x266d9  stloc.3
0x266da  ldloc.3
0x266db  ldstr    aName// "Name"
0x266e0  ldloc.2
0x266e1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x266e6  ldloc.0
0x266e7  ldstr    aAvailabilitygr_4// "AvailabilityGroups"
0x266ec  ldc.i4.2
0x266ed  newarr   [mscorlib]System.String
0x266f2  dup
0x266f3  ldc.i4.0
0x266f4  ldstr    aPrimaryserver_0// "PrimaryServer"
0x266f9  stelem.ref
0x266fa  dup
0x266fb  ldc.i4.1
0x266fc  ldstr    aAsyncreplica1// "AsyncReplica1"
0x26701  stelem.ref
0x26702  ldloc.3
0x26703  ldc.i4   0x20C
0x26708  ldstr    aGetsecondaryda// "GetSecondaryDatacenterId"
0x2670d  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x26712  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x26717  stloc.s  4
0x26719  ldloc.s  4
0x2671b  brtrue.s loc_26729
0x2671d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x26722  stloc.s  0xB
0x26724  leave    loc_268AA
0x26729  ldloc.s  4
0x2672b  ldstr    aPrimaryserver_0// "PrimaryServer"
0x26730  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x26735  castclass [mscorlib]System.String
0x2673a  stloc.s  5
0x2673c  ldloc.s  5
0x2673e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x26743  brfalse.s loc_26751
0x26745  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2674a  stloc.s  0xB
0x2674c  leave    loc_268AA
0x26751  ldloc.s  4
0x26753  ldstr    aAsyncreplica1// "AsyncReplica1"
0x26758  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2675d  castclass [mscorlib]System.String
0x26762  stloc.s  6
0x26764  ldloc.s  6
0x26766  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2676b  brfalse.s loc_26779
0x2676d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x26772  stloc.s  0xB
0x26774  leave    loc_268AA
0x26779  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2677e  stloc.s  7
0x26780  ldloc.s  7
0x26782  ldstr    aName// "Name"
0x26787  ldloc.s  5
0x26789  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2678e  ldloc.0
0x2678f  ldstr    aServer_1// "Server"
0x26794  ldc.i4.1
0x26795  newarr   [mscorlib]System.String
0x2679a  dup
0x2679b  ldc.i4.0
0x2679c  ldstr    aDatacenterid_1// "DatacenterId"
0x267a1  stelem.ref
0x267a2  ldloc.s  7
0x267a4  ldc.i4   0x221
0x267a9  ldstr    aGetsecondaryda// "GetSecondaryDatacenterId"
0x267ae  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x267b3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x267b8  dup
0x267b9  brtrue.s loc_267CD
0x267bb  ldstr    aCouldNotFindPr// "Could not find PrimaryServer : "
0x267c0  ldloc.s  5
0x267c2  call     string [mscorlib]System.String::Concat(string, string)
0x267c7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x267cc  throw
0x267cd  ldstr    aDatacenterid_1// "DatacenterId"
0x267d2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x267d7  unbox.any [mscorlib]System.Guid
0x267dc  stloc.s  8
0x267de  ldloc.s  7
0x267e0  ldstr    aName// "Name"
0x267e5  ldloc.s  6
0x267e7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x267ec  ldloc.0
0x267ed  ldstr    aServer_1// "Server"
0x267f2  ldc.i4.1
0x267f3  newarr   [mscorlib]System.String
0x267f8  dup
0x267f9  ldc.i4.0
0x267fa  ldstr    aDatacenterid_1// "DatacenterId"
0x267ff  stelem.ref
0x26800  ldloc.s  7
0x26802  ldc.i4   0x22A
0x26807  ldstr    aGetsecondaryda// "GetSecondaryDatacenterId"
0x2680c  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x26811  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x26816  dup
0x26817  brtrue.s loc_2682B
0x26819  ldstr    aCouldNotFindAs// "Could not find AsyncReplica1 : "
0x2681e  ldloc.s  6
0x26820  call     string [mscorlib]System.String::Concat(string, string)
0x26825  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2682a  throw
0x2682b  ldstr    aDatacenterid_1// "DatacenterId"
0x26830  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x26835  unbox.any [mscorlib]System.Guid
0x2683a  stloc.s  9
0x2683c  ldarg.0
0x2683d  ldarg.1
0x2683e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetDatacenterId(valuetype [mscorlib]System.Guid organizationId)
0x26843  stloc.s  0xA
0x26845  ldloc.s  8
0x26847  ldloc.s  0xA
0x26849  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2684e  brfalse.s loc_26856
0x26850  ldloc.s  9
0x26852  stloc.s  0xB
0x26854  leave.s  loc_268AA
0x26856  ldloc.s  9
0x26858  ldloc.s  0xA
0x2685a  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2685f  brfalse.s loc_26867
0x26861  ldloc.s  8
0x26863  stloc.s  0xB
0x26865  leave.s  loc_268AA
0x26867  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2686c  ldstr    aDatacentersDid// "Datacenters did not match. DC1 : {0}, D"...
0x26871  ldc.i4.3
0x26872  newarr   [mscorlib]System.Object
0x26877  dup
0x26878  ldc.i4.0
0x26879  ldloc.s  8
0x2687b  box      [mscorlib]System.Guid
0x26880  stelem.ref
0x26881  dup
0x26882  ldc.i4.1
0x26883  ldloc.s  9
0x26885  box      [mscorlib]System.Guid
0x2688a  stelem.ref
0x2688b  dup
0x2688c  ldc.i4.2
0x2688d  ldloc.s  0xA
0x2688f  box      [mscorlib]System.Guid
0x26894  stelem.ref
0x26895  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2689a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2689f  throw
0x268a0  ldloc.0
0x268a1  brfalse.s loc_268A9
0x268a3  ldloc.0
0x268a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x268a9  endfinally
0x268aa  ldloc.s  0xB
0x268ac  ret
```
