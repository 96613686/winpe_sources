# Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4::IsSkipTokenPresent

- ea: `0x13e80`
- end: `0x13e9b`
- name: `Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4::IsSkipTokenPresent`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x13e80`
- `0x24e10`
- `0x28fe0`

## string_xrefs

- `0x13e8b`: `$skiptoken`

## pseudocode

```c

```

## disassembly

```asm
0x13e80  ldarg.0
0x13e81  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Request()
0x13e86  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x13e8b  ldstr    aSkiptoken// "$skiptoken"
0x13e90  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x13e95  brfalse.s loc_13E99
0x13e97  ldc.i4.1
0x13e98  ret
0x13e99  ldc.i4.0
0x13e9a  ret
```
