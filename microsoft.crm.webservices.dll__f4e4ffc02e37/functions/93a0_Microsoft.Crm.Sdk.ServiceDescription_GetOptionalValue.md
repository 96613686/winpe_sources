# Microsoft.Crm.Sdk.ServiceDescription::GetOptionalValue

- ea: `0x93a0`
- end: `0x93cd`
- name: `Microsoft.Crm.Sdk.ServiceDescription::GetOptionalValue`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x90a0`
- `0x91c0`

## callees

- `0x93a0`

## pseudocode

```c

```

## disassembly

```asm
0x93a0  ldarg.1
0x93a1  brtrue.s loc_93A5
0x93a3  ldarg.2
0x93a4  ret
0x93a5  ldarg.1
0x93a6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x93ab  ldtoken  [mscorlib]System.String
0x93b0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93b5  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x93ba  brfalse.s loc_93CB
0x93bc  ldarg.1
0x93bd  callvirt instance string [mscorlib]System.Object::ToString()
0x93c2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x93c7  brtrue.s loc_93CB
0x93c9  ldarg.2
0x93ca  ret
0x93cb  ldarg.1
0x93cc  ret
```
