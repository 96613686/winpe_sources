# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::SlaForCase_0

- ea: `0x121a0`
- end: `0x12347`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::SlaForCase_0`
- size: `423`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x10900`
- `0x12180`
- `0x12ca0`

## callees

- `0x11470`
- `0x12110`
- `0x12130`
- `0x121a0`
- `0x12520`
- `0x12590`

## string_xrefs

- `0x12306`: `businesshoursid`

## pseudocode

```c

```

## disassembly

```asm
0x121a0  ldarg.s  4
0x121a2  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::IsSlaSupressed(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x121a7  brfalse.s loc_121AB
0x121a9  ldnull
0x121aa  ret
0x121ab  ldarga.s 1
0x121ad  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x121b2  brfalse.s loc_1221A
0x121b4  ldarg.1
0x121b5  stloc.0
0x121b6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x121bb  stloc.1
0x121bc  ldloca.s 0
0x121be  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x121c3  brtrue.s loc_121C8
0x121c5  ldc.i4.1
0x121c6  br.s     loc_121E1
0x121c8  ldloca.s 0
0x121ca  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x121cf  brtrue.s loc_121D4
0x121d1  ldc.i4.0
0x121d2  br.s     loc_121E1
0x121d4  ldloca.s 0
0x121d6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x121db  ldloc.1
0x121dc  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x121e1  brfalse.s loc_1221A
0x121e3  ldarg.1
0x121e4  ldarg.s  4
0x121e6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::RetriveSLA(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> SLAId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x121eb  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0x121f0  stloc.2
0x121f1  ldloc.2
0x121f2  brfalse.s loc_12209
0x121f4  ldloc.2
0x121f5  ldstr    aStatecode// "statecode"
0x121fa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x121ff  unbox.any [mscorlib]System.Int32
0x12204  ldc.i4.1
0x12205  bne.un.s loc_12209
0x12207  ldloc.2
0x12208  ret
0x12209  ldc.i4   0x80055001
0x1220e  ldc.i4.0
0x1220f  newarr   [mscorlib]System.Object
0x12214  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x12219  throw
0x1221a  ldarga.s 2
0x1221c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12221  brfalse.s loc_12295
0x12223  ldarg.2
0x12224  stloc.0
0x12225  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1222a  stloc.1
0x1222b  ldloca.s 0
0x1222d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12232  brtrue.s loc_12237
0x12234  ldc.i4.1
0x12235  br.s     loc_12250
0x12237  ldloca.s 0
0x12239  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x1223e  brtrue.s loc_12243
0x12240  ldc.i4.0
0x12241  br.s     loc_12250
0x12243  ldloca.s 0
0x12245  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x1224a  ldloc.1
0x1224b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12250  brfalse.s loc_12295
0x12252  ldarga.s 1
0x12254  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12259  brfalse.s loc_1228A
0x1225b  ldarg.1
0x1225c  stloc.0
0x1225d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12262  stloc.1
0x12263  ldloca.s 0
0x12265  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x1226a  brtrue.s loc_1226F
0x1226c  ldc.i4.0
0x1226d  br.s     loc_12288
0x1226f  ldloca.s 0
0x12271  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x12276  brtrue.s loc_1227B
0x12278  ldc.i4.1
0x12279  br.s     loc_12288
0x1227b  ldloca.s 0
0x1227d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x12282  ldloc.1
0x12283  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12288  brfalse.s loc_12295
0x1228a  ldarg.s  4
0x1228c  call     bool Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::CanAutoApplySLA(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x12291  brtrue.s loc_12295
0x12293  ldnull
0x12294  ret
0x12295  ldarg.0
0x12296  brfalse  loc_1233C
0x1229b  ldarg.0
0x1229c  ldstr    aSlaid// "slaid"
0x122a1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x122a6  brfalse  loc_1233C
0x122ab  ldarg.0
0x122ac  ldstr    aSlaid// "slaid"
0x122b1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x122b6  callvirt instance string [mscorlib]System.Object::ToString()
0x122bb  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x122c0  ldstr    aSla_0// "SLA"
0x122c5  ldnull
0x122c6  ldc.i4.8
0x122c7  newarr   [mscorlib]System.String
0x122cc  dup
0x122cd  ldc.i4.0
0x122ce  ldstr    aStatecode// "statecode"
0x122d3  stelem.ref
0x122d4  dup
0x122d5  ldc.i4.1
0x122d6  ldstr    aSlaid// "slaid"
0x122db  stelem.ref
0x122dc  dup
0x122dd  ldc.i4.2
0x122de  ldstr    aChangedattribu// "changedattributelist"
0x122e3  stelem.ref
0x122e4  dup
0x122e5  ldc.i4.3
0x122e6  ldstr    aWorkflowid// "workflowid"
0x122eb  stelem.ref
0x122ec  dup
0x122ed  ldc.i4.4
0x122ee  ldstr    aOwnerid// "ownerid"
0x122f3  stelem.ref
0x122f4  dup
0x122f5  ldc.i4.5
0x122f6  ldstr    aApplicablefrom// "applicablefrom"
0x122fb  stelem.ref
0x122fc  dup
0x122fd  ldc.i4.6
0x122fe  ldstr    aAllowpauseresu// "allowpauseresume"
0x12303  stelem.ref
0x12304  dup
0x12305  ldc.i4.7
0x12306  ldstr    aBusinesshoursi// "businesshoursid"
0x1230b  stelem.ref
0x1230c  ldarg.s  4
0x1230e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(valuetype [mscorlib]System.Guid id, string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x12313  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0x12318  stloc.3
0x12319  ldarg.3
0x1231a  ldc.i4.1
0x1231b  stind.i1
0x1231c  ldloc.3
0x1231d  brfalse.s loc_12334
0x1231f  ldloc.3
0x12320  ldstr    aStatecode// "statecode"
0x12325  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1232a  unbox.any [mscorlib]System.Int32
0x1232f  ldc.i4.1
0x12330  bne.un.s loc_12334
0x12332  ldloc.3
0x12333  ret
0x12334  ldarg.s  4
0x12336  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetDefaultSla(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x1233b  ret
0x1233c  ldarg.3
0x1233d  ldc.i4.1
0x1233e  stind.i1
0x1233f  ldarg.s  4
0x12341  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetDefaultSla(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x12346  ret
```
