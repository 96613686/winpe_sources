# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::CreateEdmEntity

- ea: `0x1e3b0`
- end: `0x1e47b`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::CreateEdmEntity`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x116c0`

## callees

- `0xf880`
- `0xfb60`
- `0x133e0`
- `0x179c0`
- `0x17a10`
- `0x18f80`
- `0x192a0`
- `0x19ca0`
- `0x1d220`
- `0x1e3b0`
- `0x1e560`
- `0x1f180`
- `0x24b60`
- `0x24e60`

## pseudocode

```c

```

## disassembly

```asm
0x1e3b0  ldarg.2
0x1e3b1  ldarg.0
0x1e3b2  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e3b7  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityCollectionName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e3bc  stloc.0
0x1e3bd  ldarg.2
0x1e3be  ldarg.0
0x1e3bf  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e3c4  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetXrmEntityLogicalNameFromEdmEntityName(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e3c9  stloc.1
0x1e3ca  ldarg.1
0x1e3cb  ldloc.1
0x1e3cc  call     void Microsoft.Crm.Extensibility.OData.CrmODataOptimisticConcurrencyHelper::HandlePostMatchETags(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityLogicalName)
0x1e3d1  ldloc.1
0x1e3d2  ldsfld   string [mscorlib]System.String::Empty
0x1e3d7  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetXrmEntityReference(string xrmEntityName, string entityIdValue)
0x1e3dc  stloc.2
0x1e3dd  ldarg.3
0x1e3de  ldloc.2
0x1e3df  ldarg.0
0x1e3e0  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e3e5  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToCrmEntity(class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e3ea  stloc.3
0x1e3eb  ldarg.1
0x1e3ec  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1e3f1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ReturnRowVersion()
0x1e3f6  stloc.s  6
0x1e3f8  ldloca.s 6
0x1e3fa  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1e3ff  brfalse.s loc_1E426
0x1e401  ldarg.1
0x1e402  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1e407  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataOptionalParameters()
0x1e40c  ldstr    aReturnrowversi// "ReturnRowVersion"
0x1e411  ldarg.1
0x1e412  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1e417  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ReturnRowVersion()
0x1e41c  box      valuetype [mscorlib]System.Nullable`1<bool>
0x1e421  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x1e426  ldarg.1
0x1e427  ldloc.3
0x1e428  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::CreateOrganizationResponse(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x1e42d  stloc.s  4
0x1e42f  ldloc.s  4
0x1e431  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse::get_Results()
0x1e436  ldstr    aId// "id"
0x1e43b  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1e440  unbox.any [mscorlib]System.Guid
0x1e445  stloc.s  5
0x1e447  ldarg.1
0x1e448  ldloc.s  4
0x1e44a  ldstr    aEntityreferenc_0// "EntityReference"
0x1e44f  call     void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::SetReturnRowVersionHeader(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse orgResponse, string fieldName)
0x1e454  ldarg.1
0x1e455  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1e45a  ldloc.0
0x1e45b  ldloca.s 5
0x1e45d  constrained. [mscorlib]System.Guid
0x1e463  callvirt instance string [mscorlib]System.Object::ToString()
0x1e468  ldarg.1
0x1e469  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::CreateCrmEdmEntityReference(string edmEntityName, string edmEntityKey, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1e46e  callvirt instance class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::get_Link()
0x1e473  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataHeaders::SetODataEntityIdInResponse(class [System]System.Uri oDataEntityId)
0x1e478  ldloc.s  5
0x1e47a  ret
```
