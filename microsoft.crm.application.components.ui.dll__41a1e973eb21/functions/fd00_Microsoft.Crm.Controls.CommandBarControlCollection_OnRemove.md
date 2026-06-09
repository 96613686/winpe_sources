# Microsoft.Crm.Controls.CommandBarControlCollection::OnRemove

- ea: `0xfd00`
- end: `0xfd33`
- name: `Microsoft.Crm.Controls.CommandBarControlCollection::OnRemove`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xfd00`

## string_xrefs

- `0xfd06`: `ICrmCommandBarControl`
- `0xfd22`: `value must be of type ICrmCommandBarControl.`

## pseudocode

```c

```

## disassembly

```asm
0xfd00  ldarg.2
0xfd01  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xfd06  ldstr    aIcrmcommandbar// "ICrmCommandBarControl"
0xfd0b  ldc.i4.0
0xfd0c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetInterface(string, bool)
0xfd11  ldtoken  Microsoft.Crm.Controls.ICrmCommandBarControl
0xfd16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfd1b  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xfd20  brfalse.s loc_FD32
0xfd22  ldstr    aValueMustBeOfT// "value must be of type ICrmCommandBarCon"...
0xfd27  ldstr    aValue_0// "value"
0xfd2c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xfd31  throw
0xfd32  ret
```
