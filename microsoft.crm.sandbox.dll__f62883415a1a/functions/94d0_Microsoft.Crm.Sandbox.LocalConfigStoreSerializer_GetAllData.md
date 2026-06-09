# Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::GetAllData

- ea: `0x94d0`
- end: `0x94e4`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::GetAllData`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9490`
- `0x9660`

## pseudocode

```c

```

## disassembly

```asm
0x94d0  ldarg.0
0x94d1  ldfld    class Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::_internalConfigStore
0x94d6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> Microsoft.Crm.Sandbox.IInternalConfigStore::GetAllData()
0x94db  stloc.0
0x94dc  ldarg.0
0x94dd  ldloc.0
0x94de  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ConvertDictionaryByteToObject(class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> input)
0x94e3  ret
```
