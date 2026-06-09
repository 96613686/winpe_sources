# Microsoft.Crm.Extensibility.OData.EntityController::UpdateNavigationRefInternal

- ea: `0x12c70`
- end: `0x12d42`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::UpdateNavigationRefInternal`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x12bb0`
- `0x12c10`

## callees

- `0xf740`
- `0x11500`
- `0x11a80`
- `0x12c70`
- `0x17870`
- `0x17a00`
- `0x1e600`
- `0x20d50`
- `0x28b60`
- `0x32420`

## pseudocode

```c

```

## disassembly

```asm
0x12c70  newobj   instance void <>c__DisplayClass65_0::.ctor()
0x12c75  stloc.0
0x12c76  ldloc.0
0x12c77  ldarg.3
0x12c78  stfld    string <>c__DisplayClass65_0::navigation
0x12c7d  ldarg.0
0x12c7e  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12c83  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x12c88  ldarg.0
0x12c89  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12c8e  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12c93  stloc.1
0x12c94  ldarg.s  4
0x12c96  ldarg.0
0x12c97  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12c9c  ldloc.1
0x12c9d  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::CreateCrmEdmEntityReference(class [System]System.Uri link, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x12ca2  stloc.2
0x12ca3  ldarg.0
0x12ca4  ldarg.1
0x12ca5  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x12caa  starg.s  1
0x12cac  ldarg.0
0x12cad  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x12cb2  ldloc.1
0x12cb3  ldarg.1
0x12cb4  ldarg.2
0x12cb5  ldloc.0
0x12cb6  ldfld    string <>c__DisplayClass65_0::navigation
0x12cbb  ldloc.2
0x12cbc  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateResourceNavigationPropertyReference(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, string navigationPropertyName, class Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference edmPropertyReference)
0x12cc1  ldarg.1
0x12cc2  ldarg.0
0x12cc3  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12cc8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12ccd  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty> [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::DeclaredNavigationProperties(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType)
0x12cd2  ldloc.0
0x12cd3  ldftn    instance bool <>c__DisplayClass65_0::<UpdateNavigationRefInternal>b__0(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty x)
0x12cd9  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty, bool>::.ctor(object, native int)
0x12cde  call     T0x2B00007C
0x12ce3  call     T0x2B00007D
0x12ce8  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::ToEntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty)
0x12ced  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x12cf2  stloc.3
0x12cf3  ldarg.0
0x12cf4  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12cf9  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x12cfe  ldnull
0x12cff  call     bool [System.Net.Http]System.Net.Http.HttpMethod::op_Inequality(class [System.Net.Http]System.Net.Http.HttpMethod, class [System.Net.Http]System.Net.Http.HttpMethod)
0x12d04  brfalse.s loc_12D37
0x12d06  ldarg.0
0x12d07  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12d0c  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x12d11  callvirt instance string [System.Net.Http]System.Net.Http.HttpMethod::get_Method()
0x12d16  callvirt instance string [mscorlib]System.String::ToLower()
0x12d1b  ldstr    aPost// "post"
0x12d20  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12d25  brfalse.s loc_12D37
0x12d27  ldarg.0
0x12d28  ldloc.3
0x12d29  ldloc.2
0x12d2a  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmEdmEntityReference::get_EdmEntityKey()
0x12d2f  ldc.i4.0
0x12d30  ldloc.1
0x12d31  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::HandlePatchAndPutActionExecuteTransactionResponse(string entityName, object key, bool isMetadataEntity, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x12d36  ret
0x12d37  ldarg.0
0x12d38  ldarg.1
0x12d39  ldarg.2
0x12d3a  ldc.i4.0
0x12d3b  ldloc.1
0x12d3c  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::HandlePatchAndPutActionExecuteTransactionResponse(string entityName, object key, bool isMetadataEntity, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x12d41  ret
```
