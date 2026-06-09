# Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfFilterNotSet

- ea: `0xa40`
- end: `0xa9b`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfFilterNotSet`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a0`
- `0xaa0`

## callees

- `0xa40`
- `0xc10`

## pseudocode

```c

```

## disassembly

```asm
0xa40  ldarg.2
0xa41  brtrue.s loc_A9A
0xa43  call     bool Microsoft.Crm.Sdk.CrmServiceInternal::get_IsInClientWebServer()
0xa48  brfalse.s loc_A72
0xa4a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4f  ldstr    aThe0MethodDoes// "The '{0}' method does not support entit"...
0xa54  ldc.i4.2
0xa55  newarr   [mscorlib]System.Object
0xa5a  dup
0xa5b  ldc.i4.0
0xa5c  ldarg.0
0xa5d  stelem.ref
0xa5e  dup
0xa5f  ldc.i4.1
0xa60  ldarg.1
0xa61  stelem.ref
0xa62  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa67  ldc.i4   0x80044181
0xa6c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa71  throw
0xa72  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa77  ldstr    aThe0MethodDoes_0// "The '{0}' method does not support entit"...
0xa7c  ldc.i4.2
0xa7d  newarr   [mscorlib]System.Object
0xa82  dup
0xa83  ldc.i4.0
0xa84  ldarg.0
0xa85  stelem.ref
0xa86  dup
0xa87  ldc.i4.1
0xa88  ldarg.1
0xa89  stelem.ref
0xa8a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa8f  ldc.i4   0x80040800
0xa94  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa99  throw
0xa9a  ret
```
