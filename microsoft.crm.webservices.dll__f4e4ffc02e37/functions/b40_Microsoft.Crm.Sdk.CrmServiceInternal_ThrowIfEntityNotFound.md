# Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfEntityNotFound

- ea: `0xb40`
- end: `0xb6c`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfEntityNotFound`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a0`
- `0x9d0`

## callees

- `0xb40`

## pseudocode

```c

```

## disassembly

```asm
0xb40  ldarg.0
0xb41  brtrue.s loc_B6B
0xb43  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb48  ldstr    aThe0MethodDoes_0// "The '{0}' method does not support entit"...
0xb4d  ldc.i4.2
0xb4e  newarr   [mscorlib]System.Object
0xb53  dup
0xb54  ldc.i4.0
0xb55  ldarg.1
0xb56  stelem.ref
0xb57  dup
0xb58  ldc.i4.1
0xb59  ldarg.2
0xb5a  stelem.ref
0xb5b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb60  ldc.i4   0x80040800
0xb65  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xb6a  throw
0xb6b  ret
```
