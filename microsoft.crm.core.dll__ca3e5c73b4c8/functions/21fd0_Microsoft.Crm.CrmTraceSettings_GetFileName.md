# Microsoft.Crm.CrmTraceSettings::GetFileName

- ea: `0x21fd0`
- end: `0x22031`
- name: `Microsoft.Crm.CrmTraceSettings::GetFileName`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x20e10`
- `0x21d70`

## callees

- `0x1f600`
- `0x20090`
- `0x21fd0`

## string_xrefs

- `0x21fde`: `Trace Directory not defined`
- `0x22007`: `Error accessing file `

## pseudocode

```c

```

## disassembly

```asm
0x21fd0  ldc.i4.1
0x21fd1  ldarg.1
0x21fd2  ldind.i4
0x21fd3  ldarg.2
0x21fd4  ldarg.3
0x21fd5  call     string Microsoft.Crm.CrmTrace::GetFileName(bool returnPath, int32 fileCountSuffix, string traceDirectory, string extension)
0x21fda  stloc.0
0x21fdb  ldloc.0
0x21fdc  brtrue.s loc_21FE9
0x21fde  ldstr    aTraceDirectory// "Trace Directory not defined"
0x21fe3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x21fe8  throw
0x21fe9  ldc.i4.0
0x21fea  stloc.1
0x21feb  br.s     loc_2202B
0x21fed  ldc.i4.1
0x21fee  ldarg.1
0x21fef  ldind.i4
0x21ff0  ldarg.2
0x21ff1  ldarg.3
0x21ff2  call     string Microsoft.Crm.CrmTrace::GetFileName(bool returnPath, int32 fileCountSuffix, string traceDirectory, string extension)
0x21ff7  stloc.0
0x21ff8  ldloc.0
0x21ff9  ldarg.0
0x21ffa  ldarg.1
0x21ffb  ldind.i4
0x21ffc  ldarg.2
0x21ffd  call     valuetype FileChange Microsoft.Crm.CrmTrace::GetFileChange(string fileName, int32 traceFileSize, int32 fileCountSuffix, string traceDirectory)
0x22002  stloc.1
0x22003  ldloc.1
0x22004  ldc.i4.1
0x22005  bne.un.s loc_22018
0x22007  ldstr    aErrorAccessing// "Error accessing file "
0x2200c  ldloc.0
0x2200d  call     string [mscorlib]System.String::Concat(string, string)
0x22012  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x22017  throw
0x22018  ldloc.1
0x22019  ldc.i4.3
0x2201a  bne.un.s loc_22024
0x2201c  ldarg.1
0x2201d  ldarg.1
0x2201e  ldind.i4
0x2201f  ldc.i4.1
0x22020  add
0x22021  stind.i4
0x22022  br.s     loc_2202B
0x22024  ldloc.1
0x22025  ldc.i4.4
0x22026  bne.un.s loc_2202B
0x22028  ldarg.1
0x22029  ldc.i4.0
0x2202a  stind.i4
0x2202b  ldloc.1
0x2202c  ldc.i4.2
0x2202d  bne.un.s loc_21FED
0x2202f  ldloc.0
0x22030  ret
```
