# Microsoft.Crm.Controls.CommandBarControlCollection::OnValidate

- ea: `0xfd80`
- end: `0xfdae`
- name: `Microsoft.Crm.Controls.CommandBarControlCollection::OnValidate`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xfd80`

## string_xrefs

- `0xfd86`: `ICrmCommandBarControl`
- `0xfda2`: `value must be of type ICrmCommandBarControl.`

## pseudocode

```c

```

## disassembly

```asm
0xfd80  ldarg.1
0xfd81  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xfd86  ldstr    aIcrmcommandbar// "ICrmCommandBarControl"
0xfd8b  ldc.i4.0
0xfd8c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetInterface(string, bool)
0xfd91  ldtoken  Microsoft.Crm.Controls.ICrmCommandBarControl
0xfd96  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfd9b  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xfda0  brfalse.s loc_FDAD
0xfda2  ldstr    aValueMustBeOfT// "value must be of type ICrmCommandBarCon"...
0xfda7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xfdac  throw
0xfdad  ret
```
