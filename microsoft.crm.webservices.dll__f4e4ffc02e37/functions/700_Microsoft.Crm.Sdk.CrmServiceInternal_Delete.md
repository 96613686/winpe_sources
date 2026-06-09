# Microsoft.Crm.Sdk.CrmServiceInternal::Delete

- ea: `0x700`
- end: `0x758`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::Delete`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0xab30`

## callees

- `0x990`
- `0x9d0`

## string_xrefs

- `0x701`: `Delete`
- `0x706`: `Delete`
- `0x73d`: `Delete`
- `0x742`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x700  ldarg.0
0x701  ldstr    aDelete// "Delete"
0x706  ldstr    aDelete// "Delete"
0x70b  ldarg.1
0x70c  ldarg.2
0x70d  call     instance int32 Microsoft.Crm.Sdk.CrmServiceInternal::VerifyAndRetrieveEntityForCategoryMessage(string messageName, string categoryName, string namespaceName, string entityName)
0x712  stloc.0
0x713  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x718  stloc.1
0x719  ldloc.1
0x71a  ldstr    aTarget// "Target"
0x71f  ldarg.2
0x720  ldarg.3
0x721  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x726  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x72b  ldloc.1
0x72c  ldstr    aOptionalparame// "OptionalParameters"
0x731  ldc.i4.0
0x732  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x737  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x73c  ldarg.0
0x73d  ldstr    aDelete// "Delete"
0x742  ldstr    aDelete// "Delete"
0x747  ldloc.0
0x748  ldloc.1
0x749  ldarg.s  4
0x74b  ldarg.s  5
0x74d  ldarg.s  6
0x74f  ldarg.s  7
0x751  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sdk.CrmServiceInternal::ExecuteRequest(string messageName, string requestName, int32 primaryObjectTypeCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection fields, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0x756  pop
0x757  ret
```
