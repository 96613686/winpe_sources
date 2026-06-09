# Microsoft.Xrm.Sdk.Entity::CheckIsReadOnly

- ea: `0x42a0`
- end: `0x42c8`
- name: `Microsoft.Xrm.Sdk.Entity::CheckIsReadOnly`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3ba0`
- `0x3bd0`
- `0x3c40`
- `0x3cc0`

## callees

- `0x4240`
- `0x42a0`

## string_xrefs

- `0x42ad`: `The entity is read-only and the '{0}' property cannot be modified. Use the context to update the entity instead.`

## pseudocode

```c

```

## disassembly

```asm
0x42a0  ldarg.0
0x42a1  call     instance bool Microsoft.Xrm.Sdk.Entity::get_IsReadOnly()
0x42a6  brfalse.s loc_42C7
0x42a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42ad  ldstr    aTheEntityIsRea// "The entity is read-only and the '{0}' p"...
0x42b2  ldc.i4.1
0x42b3  newarr   [mscorlib]System.Object
0x42b8  dup
0x42b9  ldc.i4.0
0x42ba  ldarg.1
0x42bb  stelem.ref
0x42bc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42c1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x42c6  throw
0x42c7  ret
```
