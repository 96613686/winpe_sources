# Microsoft.Crm.Watson.Utilities::WriteFile

- ea: `0x42440`
- end: `0x4249d`
- name: `Microsoft.Crm.Watson.Utilities::WriteFile`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x42300`
- `0x42400`

## callees

- `0x42440`

## string_xrefs

- `0x42448`: `WriteFile - The file path cannot be null`
- `0x4245b`: `WriteFile - The encoding cannot be null`

## pseudocode

```c

```

## disassembly

```asm
0x42440  ldarg.0
0x42441  brtrue.s loc_42453
0x42443  ldstr    aPath// "path"
0x42448  ldstr    aWritefileTheFi// "WriteFile - The file path cannot be nul"...
0x4244d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x42452  throw
0x42453  ldarg.3
0x42454  brtrue.s loc_42466
0x42456  ldstr    aEncoding// "encoding"
0x4245b  ldstr    aWritefileTheEn// "WriteFile - The encoding cannot be null"
0x42460  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x42465  throw
0x42466  ldarg.1
0x42467  brfalse.s loc_42477
0x42469  ldarg.1
0x4246a  callvirt instance string [mscorlib]System.String::Trim()
0x4246f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x42474  ldc.i4.0
0x42475  bgt.s    loc_42478
0x42477  ret
0x42478  ldnull
0x42479  stloc.0
0x4247a  ldarg.0
0x4247b  ldarg.2
0x4247c  ldarg.3
0x4247d  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(string, bool, class [mscorlib]System.Text.Encoding)
0x42482  stloc.0
0x42483  ldloc.0
0x42484  ldarg.1
0x42485  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x4248a  ldloc.0
0x4248b  callvirt instance void [mscorlib]System.IO.TextWriter::Flush()
0x42490  leave.s  loc_4249C
0x42492  ldloc.0
0x42493  brfalse.s loc_4249B
0x42495  ldloc.0
0x42496  callvirt instance void [mscorlib]System.IO.TextWriter::Close()
0x4249b  endfinally
0x4249c  ret
```
