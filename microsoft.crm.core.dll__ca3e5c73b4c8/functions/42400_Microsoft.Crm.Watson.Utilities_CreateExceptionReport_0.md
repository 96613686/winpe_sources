# Microsoft.Crm.Watson.Utilities::CreateExceptionReport_0

- ea: `0x42400`
- end: `0x42439`
- name: `Microsoft.Crm.Watson.Utilities::CreateExceptionReport_0`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x423f0`

## callees

- `0x42400`
- `0x42440`

## string_xrefs

- `0x42408`: `CreateExceptionReport - The exception object cannot be null`
- `0x4241b`: `CreateExceptionReport - The file path cannot be null`

## pseudocode

```c

```

## disassembly

```asm
0x42400  ldarg.0
0x42401  brtrue.s loc_42413
0x42403  ldstr    aE// "e"
0x42408  ldstr    aCreateexceptio// "CreateExceptionReport - The exception o"...
0x4240d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x42412  throw
0x42413  ldarg.1
0x42414  brtrue.s loc_42426
0x42416  ldstr    aFile// "file"
0x4241b  ldstr    aCreateexceptio_0// "CreateExceptionReport - The file path c"...
0x42420  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x42425  throw
0x42426  ldarg.1
0x42427  ldarg.0
0x42428  callvirt instance string [mscorlib]System.Object::ToString()
0x4242d  ldarg.2
0x4242e  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x42433  call     void Microsoft.Crm.Watson.Utilities::WriteFile(string path, string text, bool append, class [mscorlib]System.Text.Encoding encoding)
0x42438  ret
```
