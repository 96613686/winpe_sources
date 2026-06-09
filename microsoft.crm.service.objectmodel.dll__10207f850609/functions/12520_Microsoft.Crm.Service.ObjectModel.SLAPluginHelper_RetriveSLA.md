# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::RetriveSLA

- ea: `0x12520`
- end: `0x1258a`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::RetriveSLA`
- size: `106`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x121a0`
- `0x12b30`
- `0x12fe0`

## callees

- `0x11470`
- `0x12520`

## string_xrefs

- `0x12578`: `businesshoursid`

## pseudocode

```c

```

## disassembly

```asm
0x12520  ldarga.s 0
0x12522  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12527  brtrue.s loc_1252B
0x12529  ldnull
0x1252a  ret
0x1252b  ldarga.s 0
0x1252d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x12532  ldstr    aSla_0// "SLA"
0x12537  ldnull
0x12538  ldc.i4.8
0x12539  newarr   [mscorlib]System.String
0x1253e  dup
0x1253f  ldc.i4.0
0x12540  ldstr    aSlaid// "slaid"
0x12545  stelem.ref
0x12546  dup
0x12547  ldc.i4.1
0x12548  ldstr    aStatecode// "statecode"
0x1254d  stelem.ref
0x1254e  dup
0x1254f  ldc.i4.2
0x12550  ldstr    aChangedattribu// "changedattributelist"
0x12555  stelem.ref
0x12556  dup
0x12557  ldc.i4.3
0x12558  ldstr    aWorkflowid// "workflowid"
0x1255d  stelem.ref
0x1255e  dup
0x1255f  ldc.i4.4
0x12560  ldstr    aOwnerid// "ownerid"
0x12565  stelem.ref
0x12566  dup
0x12567  ldc.i4.5
0x12568  ldstr    aApplicablefrom// "applicablefrom"
0x1256d  stelem.ref
0x1256e  dup
0x1256f  ldc.i4.6
0x12570  ldstr    aAllowpauseresu// "allowpauseresume"
0x12575  stelem.ref
0x12576  dup
0x12577  ldc.i4.7
0x12578  ldstr    aBusinesshoursi// "businesshoursid"
0x1257d  stelem.ref
0x1257e  ldarg.1
0x1257f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(valuetype [mscorlib]System.Guid id, string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x12584  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0x12589  ret
```
