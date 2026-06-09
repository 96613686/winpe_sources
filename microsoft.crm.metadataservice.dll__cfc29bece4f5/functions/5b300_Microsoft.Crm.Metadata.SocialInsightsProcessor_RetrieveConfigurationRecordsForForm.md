# Microsoft.Crm.Metadata.SocialInsightsProcessor::RetrieveConfigurationRecordsForForm

- ea: `0x5b300`
- end: `0x5b34e`
- name: `Microsoft.Crm.Metadata.SocialInsightsProcessor::RetrieveConfigurationRecordsForForm`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5b280`

## string_xrefs

- `0x5b300`: `SocialInsightsConfiguration`
- `0x5b332`: `socialinsightsconfigurationid`

## pseudocode

```c

```

## disassembly

```asm
0x5b300  ldstr    aSocialinsights// "SocialInsightsConfiguration"
0x5b305  ldarg.2
0x5b306  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5b30b  stloc.0
0x5b30c  ldloc.0
0x5b30d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5b312  ldstr    aFormid// "formid"
0x5b317  ldc.i4.0
0x5b318  ldarg.0
0x5b319  box      [mscorlib]System.Guid
0x5b31e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5b323  pop
0x5b324  ldloc.0
0x5b325  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5b32a  ldc.i4.2
0x5b32b  newarr   [mscorlib]System.String
0x5b330  dup
0x5b331  ldc.i4.0
0x5b332  ldstr    aSocialinsights_0// "socialinsightsconfigurationid"
0x5b337  stelem.ref
0x5b338  dup
0x5b339  ldc.i4.1
0x5b33a  ldstr    aControlid// "controlid"
0x5b33f  stelem.ref
0x5b340  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x5b345  ldarg.1
0x5b346  ldloc.0
0x5b347  ldarg.2
0x5b348  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5b34d  ret
```
