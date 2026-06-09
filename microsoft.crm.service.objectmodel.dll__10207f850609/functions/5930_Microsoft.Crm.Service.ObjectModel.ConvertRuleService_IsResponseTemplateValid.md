# Microsoft.Crm.Service.ObjectModel.ConvertRuleService::IsResponseTemplateValid

- ea: `0x5930`
- end: `0x59e3`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleService::IsResponseTemplateValid`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x5930`

## string_xrefs

- `0x5931`: `responsetemplateid`
- `0x5979`: `responsetemplateid`
- `0x598a`: `responsetemplateid`
- `0x5962`: `templatetypecode`
- `0x59b7`: `templatetypecode`
- `0x59cb`: `templatetypecode`
- `0x5972`: `templateid`
- `0x599e`: `Template`

## pseudocode

```c

```

## disassembly

```asm
0x5930  ldarg.1
0x5931  ldstr    aResponsetempla// "responsetemplateid"
0x5936  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x593b  brfalse  loc_59E1
0x5940  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.TemplateService::.ctor()
0x5945  ldarg.2
0x5946  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x594b  newobj   instance void [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.Template::.ctor(valuetype [mscorlib]System.Guid)
0x5950  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5955  ldarg.2
0x5956  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x595b  stloc.0
0x595c  ldloc.0
0x595d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5962  ldstr    aTemplatetypeco// "templatetypecode"
0x5967  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x596c  ldloc.0
0x596d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5972  ldstr    aTemplateid// "templateid"
0x5977  ldc.i4.0
0x5978  ldarg.1
0x5979  ldstr    aResponsetempla// "responsetemplateid"
0x597e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5983  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5988  pop
0x5989  ldarg.1
0x598a  ldstr    aResponsetempla// "responsetemplateid"
0x598f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5994  callvirt instance string [mscorlib]System.Object::ToString()
0x5999  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x599e  ldstr    aTemplate// "Template"
0x59a3  ldarg.2
0x59a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x59a9  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x59ae  ldloc.0
0x59af  ldarg.2
0x59b0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x59b5  stloc.1
0x59b6  ldloc.1
0x59b7  ldstr    aTemplatetypeco// "templatetypecode"
0x59bc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x59c1  unbox.any [mscorlib]System.Int32
0x59c6  ldc.i4.s 0x70
0x59c8  beq.s    loc_59DD
0x59ca  ldloc.1
0x59cb  ldstr    aTemplatetypeco// "templatetypecode"
0x59d0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x59d5  unbox.any [mscorlib]System.Int32
0x59da  ldc.i4.8
0x59db  bne.un.s loc_59DF
0x59dd  ldc.i4.1
0x59de  ret
0x59df  ldc.i4.0
0x59e0  ret
0x59e1  ldc.i4.1
0x59e2  ret
```
