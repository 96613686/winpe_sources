# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteEndUserNotifications

- ea: `0x280e0`
- end: `0x2818e`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteEndUserNotifications`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x25e50`

## callees

- `0x280e0`

## string_xrefs

- `0x28124`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x28160`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x280e3`: `DeleteOrganizationEndUserNotification`
- `0x2811f`: `DeleteEndUserNotifications`
- `0x2815b`: `DeleteEndUserNotifications`
- `0x28172`: `Exception in DeleteOrganizationEndUserNotification {0}`

## pseudocode

```c

```

## disassembly

```asm
0x280e0  ldarg.0
0x280e1  ldc.i4.s 0x14
0x280e3  ldstr    aDeleteorganiza_0// "DeleteOrganizationEndUserNotification"
0x280e8  ldc.i4.0
0x280e9  newarr   [mscorlib]System.Object
0x280ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x280f3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x280f8  stloc.0
0x280f9  ldloc.0
0x280fa  ldstr    aOrganizationid_0// "OrganizationId"
0x280ff  ldarg.0
0x28100  box      [mscorlib]System.Guid
0x28105  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x2810a  ldarg.1
0x2810b  ldstr    aEndusernotific_7// "EndUserNotification"
0x28110  ldc.i4.1
0x28111  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x28116  dup
0x28117  ldc.i4.0
0x28118  ldloc.0
0x28119  stelem.ref
0x2811a  ldc.i4   0x6AC
0x2811f  ldstr    aDeleteendusern// "DeleteEndUserNotifications"
0x28124  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x28129  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x2812e  pop
0x2812f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x28134  stloc.1
0x28135  ldloc.1
0x28136  ldstr    aOrganizationid_0// "OrganizationId"
0x2813b  ldarg.0
0x2813c  box      [mscorlib]System.Guid
0x28141  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x28146  ldarg.1
0x28147  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x2814c  ldc.i4.1
0x2814d  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x28152  dup
0x28153  ldc.i4.0
0x28154  ldloc.1
0x28155  stelem.ref
0x28156  ldc.i4   0x6B0
0x2815b  ldstr    aDeleteendusern// "DeleteEndUserNotifications"
0x28160  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x28165  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x2816a  pop
0x2816b  leave.s  loc_2818D
0x2816d  stloc.2
0x2816e  ldloc.2
0x2816f  ldarg.0
0x28170  ldc.i4.s 0x14
0x28172  ldstr    aExceptionInDel// "Exception in DeleteOrganizationEndUserN"...
0x28177  ldc.i4.1
0x28178  newarr   [mscorlib]System.Object
0x2817d  dup
0x2817e  ldc.i4.0
0x2817f  ldloc.2
0x28180  callvirt instance string [mscorlib]System.Exception::get_Message()
0x28185  stelem.ref
0x28186  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2818b  rethrow
0x2818d  ret
```
