# Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::RetrieveRuleItems

- ea: `0x72b40`
- end: `0x72bc9`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleHandler::RetrieveRuleItems`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x72860`

## string_xrefs

- `0x72b7a`: `conditionxml`
- `0x72b6a`: `channelaccessprofileruleid`
- `0x72b96`: `channelaccessprofileruleid`
- `0x72b82`: `associatedchannelaccessprofile`
- `0x72b40`: `ChannelAccessProfileRuleItem`
- `0x72b62`: `channelaccessprofileruleitemid`

## pseudocode

```c

```

## disassembly

```asm
0x72b40  ldstr    aChannelaccessp_18// "ChannelAccessProfileRuleItem"
0x72b45  ldarg.3
0x72b46  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x72b4b  stloc.0
0x72b4c  ldarg.1
0x72b4d  ldarg.3
0x72b4e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x72b53  stloc.1
0x72b54  ldloc.1
0x72b55  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x72b5a  ldc.i4.5
0x72b5b  newarr   [mscorlib]System.String
0x72b60  dup
0x72b61  ldc.i4.0
0x72b62  ldstr    aChannelaccessp_20// "channelaccessprofileruleitemid"
0x72b67  stelem.ref
0x72b68  dup
0x72b69  ldc.i4.1
0x72b6a  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x72b6f  stelem.ref
0x72b70  dup
0x72b71  ldc.i4.2
0x72b72  ldstr    aName// "name"
0x72b77  stelem.ref
0x72b78  dup
0x72b79  ldc.i4.3
0x72b7a  ldstr    aConditionxml_0// "conditionxml"
0x72b7f  stelem.ref
0x72b80  dup
0x72b81  ldc.i4.4
0x72b82  ldstr    aAssociatedchan_0// "associatedchannelaccessprofile"
0x72b87  stelem.ref
0x72b88  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x72b8d  ldarg.1
0x72b8e  ldarg.3
0x72b8f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x72b94  stloc.2
0x72b95  ldloc.2
0x72b96  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x72b9b  ldc.i4.0
0x72b9c  ldarg.2
0x72b9d  box      [mscorlib]System.Guid
0x72ba2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x72ba7  pop
0x72ba8  ldloc.1
0x72ba9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0x72bae  ldstr    aSequencenumber_0// "sequencenumber"
0x72bb3  ldc.i4.0
0x72bb4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x72bb9  ldloc.1
0x72bba  ldloc.2
0x72bbb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x72bc0  ldloc.0
0x72bc1  ldloc.1
0x72bc2  ldarg.3
0x72bc3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x72bc8  ret
```
