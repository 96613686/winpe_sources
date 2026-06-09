# Microsoft.Crm.Sdk.BusinessEntityCollectionFactory::Create

- ea: `0x510`
- end: `0x521`
- name: `Microsoft.Crm.Sdk.BusinessEntityCollectionFactory::Create`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1770`

## callees

- `0x4b0`

## pseudocode

```c

```

## disassembly

```asm
0x510  ldarg.0
0x511  call     class [mscorlib]System.Type Microsoft.Crm.Sdk.BusinessEntityCollectionFactory::GetBusinessEntityCollectionType(string typeNamespace)
0x516  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x51b  castclass Microsoft.Crm.Sdk.BusinessEntityCollectionBase
0x520  ret
```
