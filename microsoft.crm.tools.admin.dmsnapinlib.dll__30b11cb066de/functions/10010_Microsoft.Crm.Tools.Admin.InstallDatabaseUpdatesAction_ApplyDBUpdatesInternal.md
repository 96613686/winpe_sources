# Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::ApplyDBUpdatesInternal

- ea: `0x10010`
- end: `0x10092`
- name: `Microsoft.Crm.Tools.Admin.InstallDatabaseUpdatesAction::ApplyDBUpdatesInternal`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xfee0`

## callees

- `0x22e0`
- `0x10010`

## string_xrefs

- `0x1004d`: `OrganizationUtility.ApplyDbUpdate.Failed.Log`

## pseudocode

```c

```

## disassembly

```asm
0x10010  ldarg.2
0x10011  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10016  brtrue.s loc_10029
0x10018  ldarg.0
0x10019  ldarg.2
0x1001a  ldarg.3
0x1001b  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType>::.ctor(var<u1>)
0x10020  ldarg.s  5
0x10022  call     void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyDBUpdatesForSpecificRelease(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType>, int32)
0x10027  br.s     loc_1004A
0x10029  ldarg.s  4
0x1002b  brtrue.s loc_10034
0x1002d  ldsfld   string [mscorlib]System.String::Empty
0x10032  br.s     loc_10039
0x10034  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.DBUpdateFileInfo::GetXrmOrgReleaseFilePath()
0x10039  stloc.0
0x1003a  ldarg.0
0x1003b  ldarg.3
0x1003c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType>::.ctor(var<u1>)
0x10041  ldarg.s  5
0x10043  ldloc.0
0x10044  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::ApplyDBUpdates(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType>, int32, string)
0x10049  pop
0x1004a  leave.s  loc_10091
0x1004c  stloc.1
0x1004d  ldstr    aOrganizationut// "OrganizationUtility.ApplyDbUpdate.Faile"...
0x10052  ldc.i4.3
0x10053  newarr   [mscorlib]System.Object
0x10058  dup
0x10059  ldc.i4.0
0x1005a  ldarg.1
0x1005b  stelem.ref
0x1005c  dup
0x1005d  ldc.i4.1
0x1005e  ldarg.0
0x1005f  box      [mscorlib]System.Guid
0x10064  stelem.ref
0x10065  dup
0x10066  ldc.i4.2
0x10067  ldloc.1
0x10068  stelem.ref
0x10069  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x1006e  stloc.2
0x1006f  ldloc.1
0x10070  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x10075  ldc.i4.s 0xA
0x10077  ldloc.2
0x10078  ldc.i4.0
0x10079  newarr   [mscorlib]System.Object
0x1007e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10083  ldloc.2
0x10084  ldc.i4.0
0x10085  newarr   [mscorlib]System.Object
0x1008a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x1008f  rethrow
0x10091  ret
```
