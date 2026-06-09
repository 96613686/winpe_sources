# Microsoft.Crm.Controls.CommandBarControlCollection::OnInsert

- ea: `0xfcc0`
- end: `0xfcf3`
- name: `Microsoft.Crm.Controls.CommandBarControlCollection::OnInsert`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xfcc0`

## string_xrefs

- `0xfcc6`: `ICrmCommandBarControl`
- `0xfce2`: `value must be of type ICrmCommandBarControl.`

## pseudocode

```c

```

## disassembly

```asm
0xfcc0  ldarg.2
0xfcc1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xfcc6  ldstr    aIcrmcommandbar// "ICrmCommandBarControl"
0xfccb  ldc.i4.0
0xfccc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetInterface(string, bool)
0xfcd1  ldtoken  Microsoft.Crm.Controls.ICrmCommandBarControl
0xfcd6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfcdb  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xfce0  brfalse.s loc_FCF2
0xfce2  ldstr    aValueMustBeOfT// "value must be of type ICrmCommandBarCon"...
0xfce7  ldstr    aValue_0// "value"
0xfcec  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xfcf1  throw
0xfcf2  ret
```
