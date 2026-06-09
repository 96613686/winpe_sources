# Microsoft.Crm.Sdk.CrmServiceInternal::Update

- ea: `0x760`
- end: `0x7c8`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::Update`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xac10`

## callees

- `0x70`
- `0x110`
- `0x990`
- `0x9d0`
- `0xc40`

## string_xrefs

- `0x761`: `Update`
- `0x766`: `Update`
- `0x7ae`: `Update`
- `0x7b3`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0x760  ldarg.0
0x761  ldstr    aUpdate// "Update"
0x766  ldstr    aUpdate// "Update"
0x76b  ldarg.1
0x76c  ldarg.2
0x76d  callvirt instance string Microsoft.Crm.Sdk.BusinessEntityBase::get_LogicalName()
0x772  call     instance int32 Microsoft.Crm.Sdk.CrmServiceInternal::VerifyAndRetrieveEntityForCategoryMessage(string messageName, string categoryName, string namespaceName, string entityName)
0x777  stloc.0
0x778  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x77d  stloc.1
0x77e  ldloc.1
0x77f  ldstr    aTarget// "Target"
0x784  ldarg.0
0x785  ldarg.2
0x786  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity Microsoft.Crm.Sdk.BusinessEntityBase::get_InternalEntity()
0x78b  ldarg.s  5
0x78d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x792  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Sdk.CrmServiceInternal::ConvertToSdkEntity(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity de, valuetype [mscorlib]System.Guid organizationId)
0x797  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x79c  ldloc.1
0x79d  ldstr    aOptionalparame// "OptionalParameters"
0x7a2  ldc.i4.0
0x7a3  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x7a8  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x7ad  ldarg.0
0x7ae  ldstr    aUpdate// "Update"
0x7b3  ldstr    aUpdate// "Update"
0x7b8  ldloc.0
0x7b9  ldloc.1
0x7ba  ldarg.3
0x7bb  ldarg.s  4
0x7bd  ldarg.s  5
0x7bf  ldarg.s  6
0x7c1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sdk.CrmServiceInternal::ExecuteRequest(string messageName, string requestName, int32 primaryObjectTypeCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection fields, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0x7c6  pop
0x7c7  ret
```
