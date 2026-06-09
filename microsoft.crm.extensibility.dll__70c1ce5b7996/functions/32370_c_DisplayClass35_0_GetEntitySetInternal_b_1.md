# <>c__DisplayClass35_0::<GetEntitySetInternal>b__1

- ea: `0x32370`
- end: `0x323ce`
- name: `<>c__DisplayClass35_0::<GetEntitySetInternal>b__1`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1d750`

## string_xrefs

- `0x32387`: `CrmODataServiceDataProvider`

## pseudocode

```c

```

## disassembly

```asm
0x32370  ldstr    aMethodname// "methodName"
0x32375  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3237a  ldstr    a01_0// "{0}.{1}"
0x3237f  ldc.i4.2
0x32380  newarr   [mscorlib]System.Object
0x32385  dup
0x32386  ldc.i4.0
0x32387  ldstr    aCrmodataservic// "CrmODataServiceDataProvider"
0x3238c  stelem.ref
0x3238d  dup
0x3238e  ldc.i4.1
0x3238f  ldstr    aRetrieveedment// "RetrieveEdmEntityCollection"
0x32394  stelem.ref
0x32395  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3239a  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x3239f  ldarg.0
0x323a0  ldarg.0
0x323a1  ldfld    class Microsoft.Crm.Extensibility.OData.EntityController <>c__DisplayClass35_0::<>4__this
0x323a6  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x323ab  ldarg.0
0x323ac  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext <>c__DisplayClass35_0::context
0x323b1  ldarg.0
0x323b2  ldfld    string <>c__DisplayClass35_0::entitySetName
0x323b7  ldarg.0
0x323b8  ldfld    string <>c__DisplayClass35_0::castedEntityName
0x323bd  ldarg.0
0x323be  ldfld    class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions <>c__DisplayClass35_0::queryOptions
0x323c3  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityCollection(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityCollectionName, string castedEntityName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x323c8  stfld    class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection <>c__DisplayClass35_0::crmEdmEntityObjectCollection
0x323cd  ret
```
