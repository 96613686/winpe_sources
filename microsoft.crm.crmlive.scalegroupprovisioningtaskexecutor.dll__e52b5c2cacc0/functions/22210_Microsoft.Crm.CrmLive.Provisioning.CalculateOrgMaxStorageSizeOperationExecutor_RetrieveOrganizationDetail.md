# Microsoft.Crm.CrmLive.Provisioning.CalculateOrgMaxStorageSizeOperationExecutor::RetrieveOrganizationDetail

- ea: `0x22210`
- end: `0x22280`
- name: `Microsoft.Crm.CrmLive.Provisioning.CalculateOrgMaxStorageSizeOperationExecutor::RetrieveOrganizationDetail`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x22050`

## callees

- `0x22210`

## string_xrefs

- `0x22235`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\CalculateOrgMaxStorageSizeOperation.cs`
- `0x22246`: `Org not found in organization table, assuming deleted.`

## pseudocode

```c

```

## disassembly

```asm
0x22210  ldc.i4.0
0x22211  stloc.0
0x22212  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x22217  stloc.1
0x22218  ldloc.1
0x22219  ldstr    aOrganization// "Organization"
0x2221e  ldarg.0
0x2221f  box      [mscorlib]System.Guid
0x22224  ldc.i4.1
0x22225  newarr   [mscorlib]System.String
0x2222a  dup
0x2222b  ldc.i4.0
0x2222c  ldarg.1
0x2222d  stelem.ref
0x2222e  ldc.i4.s 0x7D
0x22230  ldstr    aRetrieveorgani// "RetrieveOrganizationDetail"
0x22235  ldstr    aDDbsShDccm2110_34// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2223a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x2223f  stloc.2
0x22240  ldloc.2
0x22241  brtrue.s loc_2225A
0x22243  ldarg.0
0x22244  ldc.i4.s 0xA
0x22246  ldstr    aOrgNotFoundInO// "Org not found in organization table, as"...
0x2224b  ldc.i4.0
0x2224c  newarr   [mscorlib]System.Object
0x22251  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22256  ldc.i4.m1
0x22257  stloc.3
0x22258  leave.s  loc_2227E
0x2225a  ldloc.2
0x2225b  ldarg.1
0x2225c  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x22261  brfalse.s loc_22270
0x22263  ldloc.2
0x22264  ldarg.1
0x22265  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2226a  unbox.any [mscorlib]System.Int32
0x2226f  stloc.0
0x22270  leave.s  loc_2227C
0x22272  ldloc.1
0x22273  brfalse.s loc_2227B
0x22275  ldloc.1
0x22276  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2227b  endfinally
0x2227c  ldloc.0
0x2227d  ret
0x2227e  ldloc.3
0x2227f  ret
```
