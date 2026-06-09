# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TryAddTrackingFieldToNextLink

- ea: `0x21270`
- end: `0x2128c`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TryAddTrackingFieldToNextLink`
- size: `28`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1d660`
- `0x1d750`
- `0x1e010`
- `0x1eb40`
- `0x1f4d0`
- `0x21100`

## callees

- `0x19ba0`
- `0x212a0`
- `0x24e10`
- `0x24e60`
- `0x28fe0`

## pseudocode

```c

```

## disassembly

```asm
0x21270  ldarg.0
0x21271  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x21276  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x2127b  ldarg.0
0x2127c  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x21281  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferTrackChangesHeaderSpecified()
0x21286  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TryReturnTrackingFieldFromNextLink(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParameters, bool defaultValueToReturn)
0x2128b  ret
```
