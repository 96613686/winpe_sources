# Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::SetData_0

- ea: `0x9580`
- end: `0x95ac`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::SetData_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9460`
- `0x95b0`
- `0x9700`

## pseudocode

```c

```

## disassembly

```asm
0x9580  ldarg.0
0x9581  ldarg.1
0x9582  ldstr    aKeyname// "keyName"
0x9587  call     instance void Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ThrowIfNull(object data, string Message)
0x958c  ldarg.0
0x958d  ldarg.2
0x958e  ldstr    aData// "data"
0x9593  call     instance void Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ThrowIfNull(object data, string Message)
0x9598  ldarg.0
0x9599  ldfld    class Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::_internalConfigStore
0x959e  ldarg.1
0x959f  ldarg.0
0x95a0  ldarg.2
0x95a1  call     instance unsigned int8[] Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ObjectToByteArray(object obj)
0x95a6  callvirt instance void Microsoft.Crm.Sandbox.IInternalConfigStore::SetData(string keyName, unsigned int8[] data)
0x95ab  ret
```
