# Microsoft.Crm.Sdk.CrmServiceInternal::Create

- ea: `0x680`
- end: `0x6f6`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::Create`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xaaf0`

## callees

- `0x70`
- `0x110`
- `0x990`
- `0x9d0`
- `0xc40`

## string_xrefs

- `0x681`: `Create`
- `0x686`: `Create`
- `0x6ce`: `Create`
- `0x6d3`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x680  ldarg.0
0x681  ldstr    aCreate// "Create"
0x686  ldstr    aCreate// "Create"
0x68b  ldarg.1
0x68c  ldarg.2
0x68d  callvirt instance string Microsoft.Crm.Sdk.BusinessEntityBase::get_LogicalName()
0x692  call     instance int32 Microsoft.Crm.Sdk.CrmServiceInternal::VerifyAndRetrieveEntityForCategoryMessage(string messageName, string categoryName, string namespaceName, string entityName)
0x697  stloc.0
0x698  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x69d  stloc.1
0x69e  ldloc.1
0x69f  ldstr    aTarget// "Target"
0x6a4  ldarg.0
0x6a5  ldarg.2
0x6a6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.BusinessEntityBase::get_InternalEntity()
0x6ab  ldarg.s  5
0x6ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x6b2  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Sdk.CrmServiceInternal::ConvertToSdkEntity(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity de, valuetype [mscorlib]System.Guid organizationId)
0x6b7  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x6bc  ldloc.1
0x6bd  ldstr    aOptionalparame// "OptionalParameters"
0x6c2  ldc.i4.0
0x6c3  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x6c8  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x6cd  ldarg.0
0x6ce  ldstr    aCreate// "Create"
0x6d3  ldstr    aCreate// "Create"
0x6d8  ldloc.0
0x6d9  ldloc.1
0x6da  ldarg.3
0x6db  ldarg.s  4
0x6dd  ldarg.s  5
0x6df  ldarg.s  6
0x6e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sdk.CrmServiceInternal::ExecuteRequest(string messageName, string requestName, int32 primaryObjectTypeCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection fields, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0x6e6  ldstr    aId// "id"
0x6eb  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x6f0  unbox.any [mscorlib]System.Guid
0x6f5  ret
```
