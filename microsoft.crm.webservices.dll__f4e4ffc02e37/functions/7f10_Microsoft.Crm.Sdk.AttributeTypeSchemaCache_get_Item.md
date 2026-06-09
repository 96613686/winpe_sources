# Microsoft.Crm.Sdk.AttributeTypeSchemaCache::get_Item

- ea: `0x7f10`
- end: `0x7f47`
- name: `Microsoft.Crm.Sdk.AttributeTypeSchemaCache::get_Item`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x78f0`
- `0x7c90`

## callees

- `0x7f10`

## pseudocode

```c

```

## disassembly

```asm
0x7f10  ldarg.0
0x7f11  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Sdk.AttributeTypeSchemaCache::_attributeTypeToEntry
0x7f16  ldarg.1
0x7f17  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType
0x7f1c  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x7f21  isinst   AttributeTypeSchemaCacheEntry
0x7f26  dup
0x7f27  brtrue.s loc_7F46
0x7f29  ldstr    aUnknownAttribu// "Unknown attribute type: "
0x7f2e  ldarga.s 1
0x7f30  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType
0x7f36  callvirt instance string [mscorlib]System.Object::ToString()
0x7f3b  call     string [mscorlib]System.String::Concat(string, string)
0x7f40  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x7f45  throw
0x7f46  ret
```
