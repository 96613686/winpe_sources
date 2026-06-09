# Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext

- ea: `0x28b60`
- end: `0x28b8b`
- name: `Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext`
- size: `43`
- prototype: ``
- caller_count: `31`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x2e80`
- `0x30a0`
- `0x10630`
- `0x11490`
- `0x11bf0`
- `0x11c90`
- `0x11e10`
- `0x11eb0`
- `0x11f10`
- `0x12150`
- `0x12280`
- `0x123d0`
- `0x12490`
- `0x12570`
- `0x12610`
- `0x127d0`
- `0x128a0`
- `0x12940`
- `0x12a60`
- `0x12c70`
- `0x12d50`
- `0x12df0`
- `0x12e90`
- `0x12f30`
- `0x12fe0`
- `0x130f0`
- `0x131b0`
- `0x132a0`
- `0x203a0`
- `0x292b0`
- `0x339d0`

## callees

- `0x24a70`
- `0x28b60`
- `0x28b90`

## pseudocode

```c

```

## disassembly

```asm
0x28b60  ldarg.0
0x28b61  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x28b66  ldstr    aCrmodatacontex// "CrmODataContext"
0x28b6b  ldloca.s 0
0x28b6d  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x28b72  brfalse.s loc_28B7B
0x28b74  ldloc.0
0x28b75  castclass Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext
0x28b7a  ret
0x28b7b  ldarg.0
0x28b7c  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::.ctor(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x28b81  stloc.1
0x28b82  ldarg.0
0x28b83  ldloc.1
0x28b84  call     void Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::SetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x28b89  ldloc.1
0x28b8a  ret
```
