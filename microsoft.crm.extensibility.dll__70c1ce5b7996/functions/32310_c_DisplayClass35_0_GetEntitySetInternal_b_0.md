# <>c__DisplayClass35_0::<GetEntitySetInternal>b__0

- ea: `0x32310`
- end: `0x3236e`
- name: `<>c__DisplayClass35_0::<GetEntitySetInternal>b__0`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x218d0`

## string_xrefs

- `0x32327`: `CrmODataMetadataServiceDataProvider`

## pseudocode

```c

```

## disassembly

```asm
0x32310  ldstr    aMethodname// "methodName"
0x32315  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3231a  ldstr    a01_0// "{0}.{1}"
0x3231f  ldc.i4.2
0x32320  newarr   [mscorlib]System.Object
0x32325  dup
0x32326  ldc.i4.0
0x32327  ldstr    aCrmodatametada// "CrmODataMetadataServiceDataProvider"
0x3232c  stelem.ref
0x3232d  dup
0x3232e  ldc.i4.1
0x3232f  ldstr    aRetrieveedment// "RetrieveEdmEntityCollection"
0x32334  stelem.ref
0x32335  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3233a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x3233f  ldarg.0
0x32340  ldarg.0
0x32341  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass35_0::<>4__this
0x32346  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataMetadataServiceDataProvider
0x3234b  ldarg.0
0x3234c  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext <>c__DisplayClass35_0::context
0x32351  ldarg.0
0x32352  ldfld    string <>c__DisplayClass35_0::entitySetName
0x32357  ldarg.0
0x32358  ldfld    string <>c__DisplayClass35_0::castedEntityName
0x3235d  ldarg.0
0x3235e  ldfld    class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions <>c__DisplayClass35_0::queryOptions
0x32363  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEdmEntityCollection(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entitySetName, string castedEntityName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x32368  stfld    class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection <>c__DisplayClass35_0::crmEdmEntityObjectCollection
0x3236d  ret
```
