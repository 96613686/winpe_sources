# <>c__DisplayClass5_0::<AddJob>b__0

- ea: `0xb80`
- end: `0xb9d`
- name: `<>c__DisplayClass5_0::<AddJob>b__0`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0xb80  ldarg.0
0xb81  ldstr    aSocketexceptio// "SocketException.ErrorCode = {0}"
0xb86  ldarg.1
0xb87  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0xb8c  box      [mscorlib]System.Int32
0xb91  call     string [mscorlib]System.String::Format(string, object)
0xb96  stfld    string class <>c__DisplayClass5_0<var<u1>, !!T0>::extra
0xb9b  ldc.i4.1
0xb9c  ret
```
