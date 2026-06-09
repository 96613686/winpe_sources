# Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::TimeSpentOnIncident

- ea: `0x11e20`
- end: `0x11e7a`
- name: `Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::TimeSpentOnIncident`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10bc0`

## callees

- `0x11510`
- `0x11e20`

## string_xrefs

- `0x11e52`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x11e20  ldstr    aIncidentresolu// "IncidentResolution"
0x11e25  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x11e2a  dup
0x11e2b  ldstr    aIncidentid// "incidentid"
0x11e30  ldarga.s 0
0x11e32  constrained. [mscorlib]System.Guid
0x11e38  callvirt instance string [mscorlib]System.Object::ToString()
0x11e3d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x11e42  ldc.i4.2
0x11e43  newarr   [mscorlib]System.String
0x11e48  dup
0x11e49  ldc.i4.0
0x11e4a  ldstr    aTimespent// "timespent"
0x11e4f  stelem.ref
0x11e50  dup
0x11e51  ldc.i4.1
0x11e52  ldstr    aCreatedon// "createdon"
0x11e57  stelem.ref
0x11e58  ldarg.1
0x11e59  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x11e5e  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.IncidentResolution
0x11e63  stloc.0
0x11e64  ldloc.0
0x11e65  brtrue.s loc_11E69
0x11e67  ldc.i4.0
0x11e68  ret
0x11e69  ldloc.0
0x11e6a  ldstr    aTimespent// "timespent"
0x11e6f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11e74  unbox.any [mscorlib]System.Int32
0x11e79  ret
```
