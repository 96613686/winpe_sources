# Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GetCustomControlConfig

- ea: `0x64a40`
- end: `0x64aa3`
- name: `Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GetCustomControlConfig`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x64790`

## callees

- `0x64a40`

## string_xrefs

- `0x64a6c`: `controldescriptionxml`
- `0x64a40`: `CustomControlDefaultConfig`

## pseudocode

```c

```

## disassembly

```asm
0x64a40  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x64a45  ldarg.2
0x64a46  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x64a4b  stloc.0
0x64a4c  ldloc.0
0x64a4d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x64a52  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x64a57  ldc.i4.0
0x64a58  ldarg.1
0x64a59  box      [mscorlib]System.Int32
0x64a5e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x64a63  pop
0x64a64  ldc.i4.1
0x64a65  newarr   [mscorlib]System.String
0x64a6a  dup
0x64a6b  ldc.i4.0
0x64a6c  ldstr    aControldescrip// "controldescriptionxml"
0x64a71  stelem.ref
0x64a72  stloc.1
0x64a73  ldloc.0
0x64a74  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x64a79  ldloc.1
0x64a7a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x64a7f  ldarg.0
0x64a80  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService Microsoft.Crm.Metadata.Dependency.DependencyProcessor::_customControlConfigService
0x64a85  ldloc.0
0x64a86  ldarg.2
0x64a87  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x64a8c  stloc.2
0x64a8d  ldloc.2
0x64a8e  brfalse.s loc_64A99
0x64a90  ldloc.2
0x64a91  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x64a96  ldc.i4.0
0x64a97  bgt.s    loc_64A9B
0x64a99  ldnull
0x64a9a  ret
0x64a9b  ldloc.2
0x64a9c  ldc.i4.0
0x64a9d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x64aa2  ret
```
