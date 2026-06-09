# Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::GetDataByKeyNames

- ea: `0x9540`
- end: `0x955f`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::GetDataByKeyNames`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x94a0`
- `0x9660`
- `0x9700`

## pseudocode

```c

```

## disassembly

```asm
0x9540  ldarg.0
0x9541  ldarg.1
0x9542  ldstr    aKeynames// "keyNames"
0x9547  call     instance void Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ThrowIfNull(object data, string Message)
0x954c  ldarg.0
0x954d  ldarg.0
0x954e  ldfld    class Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::_internalConfigStore
0x9553  ldarg.1
0x9554  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> Microsoft.Crm.Sandbox.IInternalConfigStore::GetDataByKeyNames(class [mscorlib]System.Collections.Generic.List`1<string> keyNames)
0x9559  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ConvertDictionaryByteToObject(class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> input)
0x955e  ret
```
