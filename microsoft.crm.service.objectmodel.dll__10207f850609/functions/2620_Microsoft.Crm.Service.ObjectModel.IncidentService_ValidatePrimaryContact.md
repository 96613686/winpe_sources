# Microsoft.Crm.Service.ObjectModel.IncidentService::ValidatePrimaryContact

- ea: `0x2620`
- end: `0x2829`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::ValidatePrimaryContact`
- size: `521`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x2620`

## string_xrefs

- `0x2818`: `The specified contact doesn't belong to the contact that was specified in the customer field. Remove the value from the contact field, or select a contact associated to the selected customer, and then try again.`

## pseudocode

```c

```

## disassembly

```asm
0x2620  ldc.i4.0
0x2621  stloc.0
0x2622  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2627  stloc.1
0x2628  ldc.i4.0
0x2629  stloc.2
0x262a  ldarg.1
0x262b  ldstr    aPrimarycontact// "primarycontactid"
0x2630  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x2635  brtrue   loc_27FB
0x263a  ldarg.1
0x263b  ldstr    aPrimarycontact// "primarycontactid"
0x2640  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x2645  unbox.any [mscorlib]System.Guid
0x264a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x264f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2654  brfalse  loc_27FB
0x2659  ldarg.3
0x265a  brfalse  loc_2736
0x265f  ldarg.1
0x2660  ldstr    aCustomerid// "customerid"
0x2665  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x266a  brfalse  loc_2736
0x266f  ldstr    aIncident// "Incident"
0x2674  ldarg.2
0x2675  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x267a  stloc.s  5
0x267c  ldloc.s  5
0x267e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2683  ldc.i4.2
0x2684  newarr   [mscorlib]System.String
0x2689  dup
0x268a  ldc.i4.0
0x268b  ldstr    aCustomerid// "customerid"
0x2690  stelem.ref
0x2691  dup
0x2692  ldc.i4.1
0x2693  ldstr    aCustomeridtype// "customeridtype"
0x2698  stelem.ref
0x2699  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x269e  ldloc.s  5
0x26a0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x26a5  ldstr    aIncidentid// "incidentid"
0x26aa  ldc.i4.0
0x26ab  ldarg.1
0x26ac  ldstr    aIncidentid// "incidentid"
0x26b1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x26b6  unbox.any [mscorlib]System.Guid
0x26bb  box      [mscorlib]System.Guid
0x26c0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x26c5  pop
0x26c6  ldnull
0x26c7  stloc.s  6
0x26c9  ldarg.2
0x26ca  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x26cf  stloc.s  7
0x26d1  ldarg.0
0x26d2  ldarg.1
0x26d3  ldstr    aIncidentid// "incidentid"
0x26d8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x26dd  unbox.any [mscorlib]System.Guid
0x26e2  ldarg.1
0x26e3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x26e8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x26ed  ldarg.2
0x26ee  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x26f3  ldloc.s  5
0x26f5  ldarg.2
0x26f6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x26fb  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident
0x2700  stloc.s  6
0x2702  leave.s  loc_2710
0x2704  ldloc.s  7
0x2706  brfalse.s loc_270F
0x2708  ldloc.s  7
0x270a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x270f  endfinally
0x2710  ldloc.s  6
0x2712  ldstr    aCustomerid// "customerid"
0x2717  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x271c  unbox.any [mscorlib]System.Guid
0x2721  stloc.1
0x2722  ldloc.s  6
0x2724  ldstr    aCustomeridtype// "customeridtype"
0x2729  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x272e  unbox.any [mscorlib]System.Int32
0x2733  stloc.2
0x2734  br.s     loc_2758
0x2736  ldarg.1
0x2737  ldstr    aCustomerid// "customerid"
0x273c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x2741  unbox.any [mscorlib]System.Guid
0x2746  stloc.1
0x2747  ldarg.1
0x2748  ldstr    aCustomeridtype// "customeridtype"
0x274d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x2752  unbox.any [mscorlib]System.Int32
0x2757  stloc.2
0x2758  ldstr    aContact// "Contact"
0x275d  ldarg.2
0x275e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2763  stloc.3
0x2764  ldloc.3
0x2765  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x276a  ldstr    aContactid// "contactid"
0x276f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x2774  ldloc.3
0x2775  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x277a  ldstr    aParentcustomer// "parentcustomerid"
0x277f  ldc.i4.0
0x2780  ldloc.1
0x2781  box      [mscorlib]System.Guid
0x2786  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x278b  pop
0x278c  ldarg.0
0x278d  ldloc.3
0x278e  ldarg.2
0x278f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2794  ldarg.1
0x2795  ldstr    aPrimarycontact// "primarycontactid"
0x279a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x279f  unbox.any [mscorlib]System.Guid
0x27a4  stloc.s  4
0x27a6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x27ab  stloc.s  8
0x27ad  br.s     loc_27DB
0x27af  ldloc.s  8
0x27b1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x27b6  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x27bb  stloc.s  9
0x27bd  ldloc.s  4
0x27bf  ldloc.s  9
0x27c1  ldstr    aContactid// "contactid"
0x27c6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x27cb  unbox.any [mscorlib]System.Guid
0x27d0  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x27d5  brfalse.s loc_27DB
0x27d7  ldc.i4.1
0x27d8  stloc.0
0x27d9  leave.s  loc_27FD
0x27db  ldloc.s  8
0x27dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27e2  brtrue.s loc_27AF
0x27e4  leave.s  loc_27FD
0x27e6  ldloc.s  8
0x27e8  isinst   [mscorlib]System.IDisposable
0x27ed  stloc.s  0xA
0x27ef  ldloc.s  0xA
0x27f1  brfalse.s loc_27FA
0x27f3  ldloc.s  0xA
0x27f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27fa  endfinally
0x27fb  ldc.i4.1
0x27fc  stloc.0
0x27fd  ldloc.0
0x27fe  brtrue.s loc_2828
0x2800  ldloc.2
0x2801  ldc.i4.1
0x2802  bne.un.s loc_2814
0x2804  ldstr    aTheSpecifiedCo// "The specified contact doesn't belong to"...
0x2809  ldc.i4   0x8004F864
0x280e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2813  throw
0x2814  ldloc.2
0x2815  ldc.i4.2
0x2816  bne.un.s loc_2828
0x2818  ldstr    aTheSpecifiedCo_0// "The specified contact doesn't belong to"...
0x281d  ldc.i4   0x8004F865
0x2822  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2827  throw
0x2828  ret
```
