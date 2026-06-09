# Microsoft.Crm.Sdk.AttributeTypeSchemaCache::get_Item_0

- ea: `0x7f50`
- end: `0x7f7b`
- name: `Microsoft.Crm.Sdk.AttributeTypeSchemaCache::get_Item_0`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7c90`

## callees

- `0x7f50`

## pseudocode

```c

```

## disassembly

```asm
0x7f50  ldarg.0
0x7f51  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Sdk.AttributeTypeSchemaCache::_clrTypeToEntry
0x7f56  ldarg.1
0x7f57  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x7f5c  isinst   AttributeTypeSchemaCacheEntry
0x7f61  dup
0x7f62  brtrue.s loc_7F7A
0x7f64  ldstr    aUnknownAttribu// "Unknown attribute type: "
0x7f69  ldarg.1
0x7f6a  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7f6f  call     string [mscorlib]System.String::Concat(string, string)
0x7f74  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x7f79  throw
0x7f7a  ret
```
