# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetDefaultSla

- ea: `0x12590`
- end: `0x126d0`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetDefaultSla`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x121a0`

## callees

- `0x11510`
- `0x12590`

## string_xrefs

- `0x12611`: `businesshoursid`
- `0x126bc`: `businesshoursid`

## pseudocode

```c

```

## disassembly

```asm
0x12590  ldnull
0x12591  stloc.0
0x12592  ldarg.0
0x12593  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ObjectServiceUtility::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12598  brtrue   loc_12628
0x1259d  ldstr    aSla_0// "SLA"
0x125a2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x125a7  dup
0x125a8  ldstr    aIsdefault// "isdefault"
0x125ad  ldstr    a1// "1"
0x125b2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x125b7  dup
0x125b8  ldstr    aStatecode// "statecode"
0x125bd  ldc.i4.1
0x125be  stloc.1
0x125bf  ldloca.s 1
0x125c1  constrained. [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLAState
0x125c7  callvirt instance string [mscorlib]System.Object::ToString()
0x125cc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x125d1  ldc.i4.8
0x125d2  newarr   [mscorlib]System.String
0x125d7  dup
0x125d8  ldc.i4.0
0x125d9  ldstr    aSlaid// "slaid"
0x125de  stelem.ref
0x125df  dup
0x125e0  ldc.i4.1
0x125e1  ldstr    aStatecode// "statecode"
0x125e6  stelem.ref
0x125e7  dup
0x125e8  ldc.i4.2
0x125e9  ldstr    aChangedattribu// "changedattributelist"
0x125ee  stelem.ref
0x125ef  dup
0x125f0  ldc.i4.3
0x125f1  ldstr    aWorkflowid// "workflowid"
0x125f6  stelem.ref
0x125f7  dup
0x125f8  ldc.i4.4
0x125f9  ldstr    aOwnerid// "ownerid"
0x125fe  stelem.ref
0x125ff  dup
0x12600  ldc.i4.5
0x12601  ldstr    aApplicablefrom// "applicablefrom"
0x12606  stelem.ref
0x12607  dup
0x12608  ldc.i4.6
0x12609  ldstr    aAllowpauseresu// "allowpauseresume"
0x1260e  stelem.ref
0x1260f  dup
0x12610  ldc.i4.7
0x12611  ldstr    aBusinesshoursi// "businesshoursid"
0x12616  stelem.ref
0x12617  ldarg.0
0x12618  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x1261d  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0x12622  stloc.0
0x12623  br       loc_126CE
0x12628  ldstr    aSla_0// "SLA"
0x1262d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x12632  dup
0x12633  ldstr    aIsdefault// "isdefault"
0x12638  ldstr    a1// "1"
0x1263d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12642  dup
0x12643  ldstr    aObjecttypecode// "objecttypecode"
0x12648  ldc.i4.s 0x70
0x1264a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1264f  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x12654  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12659  dup
0x1265a  ldstr    aStatecode// "statecode"
0x1265f  ldc.i4.1
0x12660  stloc.1
0x12661  ldloca.s 1
0x12663  constrained. [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLAState
0x12669  callvirt instance string [mscorlib]System.Object::ToString()
0x1266e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12673  ldc.i4.s 9
0x12675  newarr   [mscorlib]System.String
0x1267a  dup
0x1267b  ldc.i4.0
0x1267c  ldstr    aSlaid// "slaid"
0x12681  stelem.ref
0x12682  dup
0x12683  ldc.i4.1
0x12684  ldstr    aStatecode// "statecode"
0x12689  stelem.ref
0x1268a  dup
0x1268b  ldc.i4.2
0x1268c  ldstr    aChangedattribu// "changedattributelist"
0x12691  stelem.ref
0x12692  dup
0x12693  ldc.i4.3
0x12694  ldstr    aObjecttypecode// "objecttypecode"
0x12699  stelem.ref
0x1269a  dup
0x1269b  ldc.i4.4
0x1269c  ldstr    aWorkflowid// "workflowid"
0x126a1  stelem.ref
0x126a2  dup
0x126a3  ldc.i4.5
0x126a4  ldstr    aOwnerid// "ownerid"
0x126a9  stelem.ref
0x126aa  dup
0x126ab  ldc.i4.6
0x126ac  ldstr    aApplicablefrom// "applicablefrom"
0x126b1  stelem.ref
0x126b2  dup
0x126b3  ldc.i4.7
0x126b4  ldstr    aAllowpauseresu// "allowpauseresume"
0x126b9  stelem.ref
0x126ba  dup
0x126bb  ldc.i4.8
0x126bc  ldstr    aBusinesshoursi// "businesshoursid"
0x126c1  stelem.ref
0x126c2  ldarg.0
0x126c3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity(string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x126c8  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SLA
0x126cd  stloc.0
0x126ce  ldloc.0
0x126cf  ret
```
