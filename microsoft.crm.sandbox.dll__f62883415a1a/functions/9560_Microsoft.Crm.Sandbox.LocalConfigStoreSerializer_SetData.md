# Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::SetData

- ea: `0x9560`
- end: `0x957f`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::SetData`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9470`
- `0x96b0`
- `0x9700`

## pseudocode

```c

```

## disassembly

```asm
0x9560  ldarg.0
0x9561  ldarg.1
0x9562  ldstr    aKeydata// "keyData"
0x9567  call     instance void Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ThrowIfNull(object data, string Message)
0x956c  ldarg.0
0x956d  ldfld    class Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::_internalConfigStore
0x9572  ldarg.0
0x9573  ldarg.1
0x9574  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ConvertDictionaryObjectToByte(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> input)
0x9579  callvirt instance void Microsoft.Crm.Sandbox.IInternalConfigStore::SetData(class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> keyData)
0x957e  ret
```
