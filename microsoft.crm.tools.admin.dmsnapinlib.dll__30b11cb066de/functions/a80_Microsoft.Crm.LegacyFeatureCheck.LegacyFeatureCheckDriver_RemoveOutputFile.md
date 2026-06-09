# Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::RemoveOutputFile

- ea: `0xa80`
- end: `0xaaf`
- name: `Microsoft.Crm.LegacyFeatureCheck.LegacyFeatureCheckDriver::RemoveOutputFile`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x590`

## callees

- `0xa80`

## string_xrefs

- `0xa9d`: `Cannot write to output file.`

## pseudocode

```c

```

## disassembly

```asm
0xa80  ldarg.1
0xa81  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xa86  brtrue.s loc_AAE
0xa88  ldarg.1
0xa89  call     bool [mscorlib]System.IO.File::Exists(string)
0xa8e  brfalse.s loc_AAE
0xa90  ldc.i4.s 0x57
0xa92  stloc.0
0xa93  ldarg.1
0xa94  call     valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.File::GetAttributes(string)
0xa99  ldloc.0
0xa9a  and
0xa9b  brfalse.s loc_AA8
0xa9d  ldstr    aCannotWriteToO// "Cannot write to output file."
0xaa2  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xaa7  throw
0xaa8  ldarg.1
0xaa9  call     void [mscorlib]System.IO.File::Delete(string)
0xaae  ret
```
