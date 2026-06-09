# Microsoft.Crm.Sdk.BusinessEntityFactory::Create

- ea: `0x480`
- end: `0x491`
- name: `Microsoft.Crm.Sdk.BusinessEntityFactory::Create`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1460`

## callees

- `0x420`

## pseudocode

```c

```

## disassembly

```asm
0x480  ldarg.0
0x481  call     class [mscorlib]System.Type Microsoft.Crm.Sdk.BusinessEntityFactory::GetBusinessEntityType(string typeNamespace)
0x486  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x48b  castclass Microsoft.Crm.Sdk.BusinessEntityBase
0x490  ret
```
