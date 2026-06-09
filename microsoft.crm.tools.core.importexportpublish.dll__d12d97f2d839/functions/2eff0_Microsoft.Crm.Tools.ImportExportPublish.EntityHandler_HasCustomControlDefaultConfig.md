# Microsoft.Crm.Tools.ImportExportPublish.EntityHandler::HasCustomControlDefaultConfig

- ea: `0x2eff0`
- end: `0x2f051`
- name: `Microsoft.Crm.Tools.ImportExportPublish.EntityHandler::HasCustomControlDefaultConfig`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x2e9c0`

## callees

- `0x2eff0`

## string_xrefs

- `0x2eff0`: `CustomControlDefaultConfig`
- `0x2effc`: `CustomControlDefaultConfig`
- `0x2f016`: `customcontroldefaultconfigid`

## pseudocode

```c

```

## disassembly

```asm
0x2eff0  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x2eff5  ldarg.1
0x2eff6  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2effb  stloc.0
0x2effc  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x2f001  ldarg.1
0x2f002  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2f007  stloc.1
0x2f008  ldloc.1
0x2f009  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2f00e  ldc.i4.1
0x2f00f  newarr   [mscorlib]System.String
0x2f014  dup
0x2f015  ldc.i4.0
0x2f016  ldstr    aCustomcontrold_1// "customcontroldefaultconfigid"
0x2f01b  stelem.ref
0x2f01c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2f021  ldloc.1
0x2f022  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2f027  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x2f02c  ldc.i4.0
0x2f02d  ldarg.0
0x2f02e  box      [mscorlib]System.Int32
0x2f033  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2f038  pop
0x2f039  ldloc.0
0x2f03a  ldloc.1
0x2f03b  ldarg.1
0x2f03c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2f041  stloc.2
0x2f042  ldloc.2
0x2f043  brfalse.s loc_2F04F
0x2f045  ldloc.2
0x2f046  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x2f04b  ldc.i4.0
0x2f04c  cgt
0x2f04e  ret
0x2f04f  ldc.i4.0
0x2f050  ret
```
