# Microsoft.Crm.Controls.CommandBarControlCollection::OnSet

- ea: `0xfd40`
- end: `0xfd73`
- name: `Microsoft.Crm.Controls.CommandBarControlCollection::OnSet`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xfd40`

## string_xrefs

- `0xfd46`: `ICrmCommandBarControl`
- `0xfd62`: `newValue must be of type ICrmCommandBarControl.`

## pseudocode

```c

```

## disassembly

```asm
0xfd40  ldarg.3
0xfd41  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xfd46  ldstr    aIcrmcommandbar// "ICrmCommandBarControl"
0xfd4b  ldc.i4.0
0xfd4c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetInterface(string, bool)
0xfd51  ldtoken  Microsoft.Crm.Controls.ICrmCommandBarControl
0xfd56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfd5b  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xfd60  brfalse.s loc_FD72
0xfd62  ldstr    aNewvalueMustBe// "newValue must be of type ICrmCommandBar"...
0xfd67  ldstr    aNewvalue// "newValue"
0xfd6c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xfd71  throw
0xfd72  ret
```
