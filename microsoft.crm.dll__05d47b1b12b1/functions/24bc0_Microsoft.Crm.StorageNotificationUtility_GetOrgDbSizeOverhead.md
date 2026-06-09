# Microsoft.Crm.StorageNotificationUtility::GetOrgDbSizeOverhead

- ea: `0x24bc0`
- end: `0x24c9b`
- name: `Microsoft.Crm.StorageNotificationUtility::GetOrgDbSizeOverhead`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x24df0`

## callees

- `0x24bc0`

## string_xrefs

- `0x24bfd`: `Org not found in organization table, assuming deleted.`

## pseudocode

```c

```

## disassembly

```asm
0x24bc0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x24bc5  stloc.3
0x24bc6  ldloc.3
0x24bc7  ldstr    aOrganization// "Organization"
0x24bcc  ldarg.0
0x24bcd  box      [mscorlib]System.Guid
0x24bd2  ldc.i4.1
0x24bd3  newarr   [mscorlib]System.String
0x24bd8  dup
0x24bd9  ldc.i4.0
0x24bda  ldstr    aScalegroupid_0// "ScaleGroupId"
0x24bdf  stelem.ref
0x24be0  ldc.i4   0x190
0x24be5  ldstr    aGetorgdbsizeov// "GetOrgDbSizeOverhead"
0x24bea  ldstr    aDA1SSrcSharedS_4// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x24bef  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x24bf4  stloc.s  4
0x24bf6  ldloc.s  4
0x24bf8  brtrue.s loc_24C15
0x24bfa  ldarg.0
0x24bfb  ldc.i4.s 0x14
0x24bfd  ldstr    aOrgNotFoundInO// "Org not found in organization table, as"...
0x24c02  ldc.i4.0
0x24c03  newarr   [mscorlib]System.Object
0x24c08  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24c0d  ldc.i4.0
0x24c0e  stloc.s  5
0x24c10  leave    loc_24C98
0x24c15  ldloc.s  4
0x24c17  ldstr    aScalegroupid_0// "ScaleGroupId"
0x24c1c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x24c21  unbox.any [mscorlib]System.Guid
0x24c26  stloc.0
0x24c27  leave.s  loc_24C33
0x24c29  ldloc.3
0x24c2a  brfalse.s loc_24C32
0x24c2c  ldloc.3
0x24c2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24c32  endfinally
0x24c33  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x24c38  stloc.1
0x24c39  ldloc.1
0x24c3a  ldstr    aId// "Id"
0x24c3f  ldloc.0
0x24c40  box      [mscorlib]System.Guid
0x24c45  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x24c4a  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x24c4f  ldstr    aScalegroup// "ScaleGroup"
0x24c54  ldc.i4.1
0x24c55  newarr   [mscorlib]System.String
0x24c5a  dup
0x24c5b  ldc.i4.0
0x24c5c  ldstr    aOrgdbsizeoverh// "OrgDbSizeOverhead"
0x24c61  stelem.ref
0x24c62  ldloc.1
0x24c63  ldc.i4   0x1A1
0x24c68  ldstr    aGetorgdbsizeov// "GetOrgDbSizeOverhead"
0x24c6d  ldstr    aDA1SSrcSharedS_4// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x24c72  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x24c77  stloc.2
0x24c78  ldloc.2
0x24c79  ldstr    aOrgdbsizeoverh// "OrgDbSizeOverhead"
0x24c7e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x24c83  brtrue.s loc_24C87
0x24c85  ldc.i4.0
0x24c86  ret
0x24c87  ldloc.2
0x24c88  ldstr    aOrgdbsizeoverh// "OrgDbSizeOverhead"
0x24c8d  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x24c92  unbox.any [mscorlib]System.Int32
0x24c97  ret
0x24c98  ldloc.s  5
0x24c9a  ret
```
