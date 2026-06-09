# Microsoft.Crm.ParameterFilterBase::ShouldValidateParameters

- ea: `0x11d0`
- end: `0x11f7`
- name: `Microsoft.Crm.ParameterFilterBase::ShouldValidateParameters`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1370`

## callees

- `0x11d0`

## pseudocode

```c

```

## disassembly

```asm
0x11d0  ldarg.1
0x11d1  isinst   [mscorlib]System.Reflection.ICustomAttributeProvider
0x11d6  stloc.0
0x11d7  ldloc.0
0x11d8  brtrue.s loc_11E1
0x11da  ldarg.1
0x11db  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x11e0  stloc.0
0x11e1  ldloc.0
0x11e2  ldtoken  Microsoft.Crm.IgnoreParameterValidationAttribute
0x11e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11ec  ldc.i4.1
0x11ed  callvirt instance object[] [mscorlib]System.Reflection.ICustomAttributeProvider::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x11f2  ldlen
0x11f3  ldc.i4.0
0x11f4  ceq
0x11f6  ret
```
