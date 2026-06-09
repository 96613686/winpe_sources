# Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileImportExportHelper::RetrieveProfileEntityAccessLevel

- ea: `0x2c4d0`
- end: `0x2c53d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileImportExportHelper::RetrieveProfileEntityAccessLevel`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x2c508`: `channelaccessprofileid`
- `0x2c4d6`: `ChannelAccessProfileEntityAccessLevel`
- `0x2c4fb`: `ChannelAccessProfileEntityAccessLevel`
- `0x2c51b`: `entityaccesslevelid`
- `0x2c4f0`: `entityaccessleveldepthmask`

## pseudocode

```c

```

## disassembly

```asm
0x2c4d0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ChannelAccessProfileEntityAccessLevelService::.ctor()
0x2c4d5  stloc.0
0x2c4d6  ldstr    aChannelaccessp_7// "ChannelAccessProfileEntityAccessLevel"
0x2c4db  ldarg.2
0x2c4dc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2c4e1  stloc.1
0x2c4e2  ldloc.1
0x2c4e3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2c4e8  ldc.i4.1
0x2c4e9  newarr   [mscorlib]System.String
0x2c4ee  dup
0x2c4ef  ldc.i4.0
0x2c4f0  ldstr    aEntityaccessle_0// "entityaccessleveldepthmask"
0x2c4f5  stelem.ref
0x2c4f6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2c4fb  ldstr    aChannelaccessp_7// "ChannelAccessProfileEntityAccessLevel"
0x2c500  ldarg.2
0x2c501  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2c506  stloc.2
0x2c507  ldloc.2
0x2c508  ldstr    aChannelaccessp_1// "channelaccessprofileid"
0x2c50d  ldc.i4.0
0x2c50e  ldarg.1
0x2c50f  box      [mscorlib]System.Guid
0x2c514  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2c519  pop
0x2c51a  ldloc.2
0x2c51b  ldstr    aEntityaccessle// "entityaccesslevelid"
0x2c520  ldc.i4.0
0x2c521  ldarg.0
0x2c522  box      [mscorlib]System.Guid
0x2c527  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x2c52c  pop
0x2c52d  ldloc.1
0x2c52e  ldloc.2
0x2c52f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x2c534  ldloc.0
0x2c535  ldloc.1
0x2c536  ldarg.2
0x2c537  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2c53c  ret
```
