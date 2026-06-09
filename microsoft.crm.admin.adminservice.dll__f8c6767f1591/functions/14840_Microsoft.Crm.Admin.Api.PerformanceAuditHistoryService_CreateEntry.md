# Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateEntry

- ea: `0x14840`
- end: `0x148eb`
- name: `Microsoft.Crm.Admin.Api.PerformanceAuditHistoryService::CreateEntry`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14820`
- `0x14830`

## callees

- `0x14840`

## string_xrefs

- `0x1489c`: `CreatedOn`
- `0x148ce`: `CreateEntry`
- `0x148d3`: `D:\a\1\s\src\CrmLive\Admin\PerformanceAudit\PerformanceAuditHistoryService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x14840  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x14845  ldstr    aPerformanceaud// "PerformanceAuditEnabled"
0x1484a  ldc.i4.0
0x1484b  callvirt T0x2B000068
0x14850  brfalse  loc_148EA
0x14855  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1485a  stloc.0
0x1485b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x14860  stloc.1
0x14861  ldloc.1
0x14862  ldstr    aObjectid_0// "ObjectId"
0x14867  ldarg.0
0x14868  box      [mscorlib]System.Guid
0x1486d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x14872  ldloc.1
0x14873  ldstr    aObjecttype// "ObjectType"
0x14878  ldarg.1
0x14879  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1487e  ldloc.1
0x1487f  ldstr    aOperation// "Operation"
0x14884  ldarg.2
0x14885  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1488a  ldloc.1
0x1488b  ldstr    aOperationsubty// "OperationSubType"
0x14890  ldarg.3
0x14891  box      OperationSubType
0x14896  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1489b  ldloc.1
0x1489c  ldstr    aCreatedon// "CreatedOn"
0x148a1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x148a6  box      [mscorlib]System.DateTime
0x148ab  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x148b0  ldloc.1
0x148b1  ldstr    aAuditentryid// "AuditEntryId"
0x148b6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x148bb  box      [mscorlib]System.Guid
0x148c0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x148c5  ldloc.0
0x148c6  ldstr    aPerformanceaud_0// "PerformanceAuditHistory"
0x148cb  ldloc.1
0x148cc  ldc.i4.s 0x3B
0x148ce  ldstr    aCreateentry// "CreateEntry"
0x148d3  ldstr    aDA1SSrcCrmlive_28// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Perfo"...
0x148d8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x148dd  pop
0x148de  leave.s  loc_148EA
0x148e0  ldloc.0
0x148e1  brfalse.s loc_148E9
0x148e3  ldloc.0
0x148e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x148e9  endfinally
0x148ea  ret
```
