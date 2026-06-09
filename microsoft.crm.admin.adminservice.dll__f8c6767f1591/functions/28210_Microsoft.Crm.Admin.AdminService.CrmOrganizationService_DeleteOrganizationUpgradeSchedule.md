# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationUpgradeSchedule

- ea: `0x28210`
- end: `0x282a5`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationUpgradeSchedule`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x25e50`

## callees

- `0x28210`

## string_xrefs

- `0x2826e`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x28213`: `DeleteOrganizationUpgradeSchedule for org {0}`
- `0x28269`: `DeleteOrganizationUpgradeSchedule`
- `0x28280`: `Exception in DeleteOrganizationUpgradeSchedule  for org {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x28210  ldarg.0
0x28211  ldc.i4.s 0x14
0x28213  ldstr    aDeleteorganiza_2// "DeleteOrganizationUpgradeSchedule for o"...
0x28218  ldc.i4.1
0x28219  newarr   [mscorlib]System.Object
0x2821e  dup
0x2821f  ldc.i4.0
0x28220  ldarg.0
0x28221  box      [mscorlib]System.Guid
0x28226  stelem.ref
0x28227  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2822c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x28231  stloc.0
0x28232  ldloc.0
0x28233  ldstr    aOrganizationid_0// "OrganizationId"
0x28238  ldarg.0
0x28239  box      [mscorlib]System.Guid
0x2823e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x28243  ldloc.0
0x28244  ldstr    aStatus_0// "Status"
0x28249  ldc.i4.0
0x2824a  box      [mscorlib]System.Int32
0x2824f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x28254  ldarg.1
0x28255  ldstr    aOrganizationup// "OrganizationUpgradeSchedule"
0x2825a  ldc.i4.1
0x2825b  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x28260  dup
0x28261  ldc.i4.0
0x28262  ldloc.0
0x28263  stelem.ref
0x28264  ldc.i4   0x6DC
0x28269  ldstr    aDeleteorganiza_3// "DeleteOrganizationUpgradeSchedule"
0x2826e  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x28273  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x28278  pop
0x28279  leave.s  loc_282A4
0x2827b  stloc.1
0x2827c  ldloc.1
0x2827d  ldarg.0
0x2827e  ldc.i4.s 0x14
0x28280  ldstr    aExceptionInDel_1// "Exception in DeleteOrganizationUpgradeS"...
0x28285  ldc.i4.2
0x28286  newarr   [mscorlib]System.Object
0x2828b  dup
0x2828c  ldc.i4.0
0x2828d  ldarg.0
0x2828e  box      [mscorlib]System.Guid
0x28293  stelem.ref
0x28294  dup
0x28295  ldc.i4.1
0x28296  ldloc.1
0x28297  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2829c  stelem.ref
0x2829d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x282a2  rethrow
0x282a4  ret
```
