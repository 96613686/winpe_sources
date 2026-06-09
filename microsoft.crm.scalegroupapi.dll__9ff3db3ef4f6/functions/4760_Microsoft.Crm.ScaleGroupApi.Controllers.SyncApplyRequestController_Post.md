# Microsoft.Crm.ScaleGroupApi.Controllers.SyncApplyRequestController::Post

- ea: `0x4760`
- end: `0x480f`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.SyncApplyRequestController::Post`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1a10`
- `0x1a30`
- `0x1a50`
- `0x4760`
- `0x4810`
- `0x4870`

## string_xrefs

- `0x47ab`: `DirectoryObject not found {0} for organization {1}`

## pseudocode

```c

```

## disassembly

```asm
0x4760  ldarg.2
0x4761  stloc.0
0x4762  call     T0x2B000026
0x4767  ldarg.1
0x4768  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProviderFactory::GetProvider(valuetype [mscorlib]System.Guid)
0x476d  ldarg.3
0x476e  brtrue.s loc_4773
0x4770  ldnull
0x4771  br.s     loc_4779
0x4773  ldarg.3
0x4774  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSyncApplyRequest::get_ObjectUrl()
0x4779  stloc.1
0x477a  ldarg.3
0x477b  brtrue.s loc_4784
0x477d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4782  br.s     loc_478A
0x4784  ldarg.3
0x4785  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGSyncApplyRequest::get_GroupId()
0x478a  stloc.2
0x478b  ldarg.3
0x478c  brtrue.s loc_4791
0x478e  ldc.i4.0
0x478f  br.s     loc_4797
0x4791  ldarg.3
0x4792  callvirt instance bool Microsoft.Crm.ScaleGroupApi.Models.SGSyncApplyRequest::get_IgnoreLicenseChecks()
0x4797  stloc.3
0x4798  ldarg.1
0x4799  ldloc.0
0x479a  ldloc.1
0x479b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveObject(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string)
0x47a0  stloc.s  4
0x47a2  ldloc.s  4
0x47a4  brtrue.s loc_47D3
0x47a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x47ab  ldstr    aDirectoryobjec// "DirectoryObject not found {0} for organ"...
0x47b0  ldc.i4.2
0x47b1  newarr   [mscorlib]System.Object
0x47b6  dup
0x47b7  ldc.i4.0
0x47b8  ldloc.0
0x47b9  box      [mscorlib]System.Guid
0x47be  stelem.ref
0x47bf  dup
0x47c0  ldc.i4.1
0x47c1  ldarg.1
0x47c2  box      [mscorlib]System.Guid
0x47c7  stelem.ref
0x47c8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x47cd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x47d2  throw
0x47d3  ldloc.s  4
0x47d5  ldstr    aType// "Type"
0x47da  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x47df  castclass [mscorlib]System.String
0x47e4  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0x47e9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x47ee  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0x47f3  ldc.i4.5
0x47f4  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x47f9  brfalse.s loc_4807
0x47fb  ldarg.1
0x47fc  ldloc.s  4
0x47fe  ldloc.1
0x47ff  ldloc.2
0x4800  ldloc.3
0x4801  call     string Microsoft.Crm.ScaleGroupApi.Controllers.SyncApplyRequestController::ExecuteSyncUsersDataExecutor(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag user, string objectUrl, valuetype [mscorlib]System.Guid groupId, bool ignoreLicenseChecks)
0x4806  ret
0x4807  ldarg.1
0x4808  ldloc.0
0x4809  call     string Microsoft.Crm.ScaleGroupApi.Controllers.SyncApplyRequestController::ExecuteSyncDataExecutor(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid directoryObjectId)
0x480e  ret
```
