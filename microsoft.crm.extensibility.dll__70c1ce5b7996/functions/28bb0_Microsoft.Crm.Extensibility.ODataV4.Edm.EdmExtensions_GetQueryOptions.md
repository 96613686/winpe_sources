# Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions

- ea: `0x28bb0`
- end: `0x28bb9`
- name: `Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions`
- size: `9`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10630`
- `0x117a0`
- `0x11a80`
- `0x11bf0`
- `0x11c90`
- `0x11f10`
- `0x12150`
- `0x12280`
- `0x12610`
- `0x12940`
- `0x12a60`
- `0x12f30`
- `0x12fe0`
- `0x130f0`
- `0x131b0`
- `0x132a0`
- `0x203a0`
- `0x20a70`
- `0x29760`

## callees

- `0x28bc0`

## pseudocode

```c

```

## disassembly

```asm
0x28bb0  ldarg.0
0x28bb1  ldnull
0x28bb2  ldarg.1
0x28bb3  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x28bb8  ret
```
