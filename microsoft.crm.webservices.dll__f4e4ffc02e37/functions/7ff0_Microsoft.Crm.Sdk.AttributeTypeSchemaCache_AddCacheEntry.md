# Microsoft.Crm.Sdk.AttributeTypeSchemaCache::AddCacheEntry

- ea: `0x7ff0`
- end: `0x8021`
- name: `Microsoft.Crm.Sdk.AttributeTypeSchemaCache::AddCacheEntry`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7f80`

## callees

- `0x7ff0`

## pseudocode

```c

```

## disassembly

```asm
0x7ff0  ldarg.1
0x7ff1  brfalse.s loc_800A
0x7ff3  ldarg.0
0x7ff4  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Sdk.AttributeTypeSchemaCache::_attributeTypeToEntry
0x7ff9  ldarg.1
0x7ffa  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType
0x7fff  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType
0x8004  ldarg.3
0x8005  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x800a  ldarg.2
0x800b  ldnull
0x800c  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8011  brfalse.s loc_8020
0x8013  ldarg.0
0x8014  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Sdk.AttributeTypeSchemaCache::_clrTypeToEntry
0x8019  ldarg.2
0x801a  ldarg.3
0x801b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x8020  ret
```
