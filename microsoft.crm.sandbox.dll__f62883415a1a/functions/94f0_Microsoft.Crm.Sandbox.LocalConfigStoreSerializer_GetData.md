# Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::GetData

- ea: `0x94f0`
- end: `0x953f`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::GetData`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9480`
- `0x94f0`
- `0x9600`
- `0x9700`

## pseudocode

```c

```

## disassembly

```asm
0x94f0  ldarg.0
0x94f1  ldarg.1
0x94f2  ldstr    aKeyname// "keyName"
0x94f7  call     instance void Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ThrowIfNull(object data, string Message)
0x94fc  ldarg.0
0x94fd  ldfld    class Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::_internalConfigStore
0x9502  ldarg.1
0x9503  callvirt instance unsigned int8[] Microsoft.Crm.Sandbox.IInternalConfigStore::GetData(string keyName)
0x9508  stloc.0
0x9509  ldloc.0
0x950a  brfalse.s loc_9535
0x950c  ldarg.0
0x950d  ldloc.0
0x950e  call     instance object Microsoft.Crm.Sandbox.LocalConfigStoreSerializer::ByteArrayToObject(unsigned int8[] arrBytes)
0x9513  stloc.1
0x9514  ldloc.1
0x9515  brfalse.s loc_9535
0x9517  ldloc.1
0x9518  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x951d  ldtoken  mvar<u1>
0x9522  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9527  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x952c  brfalse.s loc_9535
0x952e  ldloc.1
0x952f  unbox.any mvar<u1>
0x9534  ret
0x9535  ldloca.s 2
0x9537  initobj  mvar<u1>
0x953d  ldloc.2
0x953e  ret
```
