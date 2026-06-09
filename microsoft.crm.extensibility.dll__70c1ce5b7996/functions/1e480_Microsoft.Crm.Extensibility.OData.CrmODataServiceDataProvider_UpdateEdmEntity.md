# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateEdmEntity

- ea: `0x1e480`
- end: `0x1e55d`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateEdmEntity`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x11c90`

## callees

- `0xf880`
- `0x133e0`
- `0x179c0`
- `0x17a10`
- `0x18f80`
- `0x192a0`
- `0x19ca0`
- `0x1d2a0`
- `0x1e480`
- `0x1e560`
- `0x21370`
- `0x24d00`
- `0x24e60`

## string_xrefs

- `0x1e4b2`: `Deep update of navigation properties is not allowed.`

## pseudocode

```c

```

## disassembly

```asm
0x1e480  ldarg.2
0x1e481  ldarg.3
0x1e482  ldarg.0
0x1e483  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e488  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetXrmEntityReferenceForKeys(string edmEntityName, string key, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e48d  stloc.0
0x1e48e  ldarg.s  4
0x1e490  ldloc.0
0x1e491  ldarg.0
0x1e492  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e497  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToCrmEntity(class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e49c  stloc.1
0x1e49d  ldloc.1
0x1e49e  brfalse.s loc_1E4C3
0x1e4a0  ldloc.1
0x1e4a1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x1e4a6  call     T0x2B0000BC
0x1e4ab  brfalse.s loc_1E4C3
0x1e4ad  ldc.i4   0x190
0x1e4b2  ldstr    aDeepUpdateOfNa// "Deep update of navigation properties is"...
0x1e4b7  ldc.i4.0
0x1e4b8  newarr   [mscorlib]System.Object
0x1e4bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1e4c2  throw
0x1e4c3  ldarg.1
0x1e4c4  ldloc.1
0x1e4c5  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x1e4ca  call     valuetype UpdateOption Microsoft.Crm.Extensibility.OData.CrmODataOptimisticConcurrencyHelper::HandleUpdateMatchETags(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityLogicalName)
0x1e4cf  stloc.2
0x1e4d0  ldarg.1
0x1e4d1  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1e4d6  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ReturnRowVersion()
0x1e4db  stloc.s  5
0x1e4dd  ldloca.s 5
0x1e4df  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1e4e4  brfalse.s loc_1E50B
0x1e4e6  ldarg.1
0x1e4e7  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1e4ec  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataOptionalParameters()
0x1e4f1  ldstr    aReturnrowversi// "ReturnRowVersion"
0x1e4f6  ldarg.1
0x1e4f7  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1e4fc  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ReturnRowVersion()
0x1e501  box      valuetype [mscorlib]System.Nullable`1<bool>
0x1e506  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1e50b  ldarg.1
0x1e50c  ldloc.1
0x1e50d  ldloc.2
0x1e50e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, valuetype UpdateOption updateOption)
0x1e513  stloc.3
0x1e514  ldarg.1
0x1e515  ldloc.3
0x1e516  ldloc.3
0x1e517  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.UpdateResponse
0x1e51c  brtrue.s loc_1E525
0x1e51e  ldstr    aTarget// "Target"
0x1e523  br.s     loc_1E52A
0x1e525  ldstr    aEntityreferenc_0// "EntityReference"
0x1e52a  call     void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::SetReturnRowVersionHeader(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse orgResponse, string fieldName)
0x1e52f  ldarg.2
0x1e530  ldarg.0
0x1e531  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e536  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityCollectionName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e53b  stloc.s  4
0x1e53d  ldarg.1
0x1e53e  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1e543  ldloc.s  4
0x1e545  ldarg.3
0x1e546  ldarg.1
0x1e547  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::CreateCrmEdmEntityReference(string edmEntityName, string edmEntityKey, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1e54c  callvirt instance class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::get_Link()
0x1e551  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataHeaders::SetODataEntityIdInResponse(class [System]System.Uri oDataEntityId)
0x1e556  ldloc.1
0x1e557  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1e55c  ret
```
