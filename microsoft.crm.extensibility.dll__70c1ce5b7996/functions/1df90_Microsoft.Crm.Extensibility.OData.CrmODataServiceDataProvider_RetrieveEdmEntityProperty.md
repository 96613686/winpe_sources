# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityProperty

- ea: `0x1df90`
- end: `0x1e00a`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityProperty`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x11600`

## callees

- `0xf740`
- `0xfab0`
- `0xfb80`
- `0x13460`
- `0x1d4d0`
- `0x1df90`
- `0x21370`
- `0x24cb0`
- `0x24e10`
- `0x28fe0`

## pseudocode

```c

```

## disassembly

```asm
0x1df90  ldnull
0x1df91  stloc.0
0x1df92  ldarg.2
0x1df93  ldarg.0
0x1df94  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1df99  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1df9e  ldarg.s  4
0x1dfa0  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType::FindProperty(string)
0x1dfa5  stloc.1
0x1dfa6  ldc.i4.1
0x1dfa7  newarr   [mscorlib]System.String
0x1dfac  dup
0x1dfad  ldc.i4.0
0x1dfae  ldloc.1
0x1dfaf  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetCrmAttributeNameFromEdmAttributeName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x1dfb4  stelem.ref
0x1dfb5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x1dfba  stloc.0
0x1dfbb  ldarg.2
0x1dfbc  ldarg.3
0x1dfbd  ldarg.0
0x1dfbe  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1dfc3  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetXrmEntityReferenceForKeys(string edmEntityName, string key, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1dfc8  stloc.2
0x1dfc9  ldarg.1
0x1dfca  ldloc.2
0x1dfcb  ldloc.0
0x1dfcc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Retrieve(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet columnSet)
0x1dfd1  ldarg.1
0x1dfd2  call     void Microsoft.Crm.Extensibility.OData.CrmODataOptimisticConcurrencyHelper::ThrowIfMatchHeadersAreSentWithProperty(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1dfd7  ldarg.1
0x1dfd8  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x1dfdd  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1dfe2  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::ValidateAndReturnNoLock(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParams)
0x1dfe7  stloc.3
0x1dfe8  ldarg.2
0x1dfe9  ldarg.0
0x1dfea  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1dfef  ldc.i4.0
0x1dff0  ldc.i4.0
0x1dff1  ldloc.3
0x1dff2  call     class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToEdmEntityObject(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool isDeltaEntity, [opt] bool fillAllProperties, [opt] bool noLock)
0x1dff7  ldnull
0x1dff8  stloc.s  4
0x1dffa  ldarg.s  4
0x1dffc  ldloca.s 4
0x1dffe  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x1e003  brfalse.s loc_1E008
0x1e005  ldloc.s  4
0x1e007  ret
0x1e008  ldnull
0x1e009  ret
```
