# Microsoft.Crm.Sdk.RequestBuilderFactory::Create

- ea: `0x4b80`
- end: `0x4b98`
- name: `Microsoft.Crm.Sdk.RequestBuilderFactory::Create`
- size: `24`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x920`
- `0x9d0`
- `0x45a0`
- `0x4790`

## callees

- `0x55a0`

## pseudocode

```c

```

## disassembly

```asm
0x4b80  ldsfld   class Microsoft.Crm.Sdk.RequestBuilderProxyCache Microsoft.Crm.Sdk.RequestBuilderFactory::_proxyCache
0x4b85  ldarg.1
0x4b86  ldarg.0
0x4b87  newobj   instance void Microsoft.Crm.Sdk.RequestBuilderKey::.ctor(string namespaceName, string requestName)
0x4b8c  ldarg.2
0x4b8d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x4b92  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<class Microsoft.Crm.Sdk.RequestBuilderKey, class Microsoft.Crm.Sdk.RequestBuilderProxy>::LookupEntry(void, var<u1>)
0x4b97  ret
```
