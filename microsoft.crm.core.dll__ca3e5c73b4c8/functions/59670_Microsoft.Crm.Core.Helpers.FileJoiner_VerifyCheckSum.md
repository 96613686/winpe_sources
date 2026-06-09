# Microsoft.Crm.Core.Helpers.FileJoiner::VerifyCheckSum

- ea: `0x59670`
- end: `0x596e0`
- name: `Microsoft.Crm.Core.Helpers.FileJoiner::VerifyCheckSum`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x59410`

## callees

- `0x1b360`
- `0x1c070`
- `0x1eaa0`
- `0x1f510`
- `0x4f0f0`
- `0x50c70`
- `0x50cb0`
- `0x59670`

## string_xrefs

- `0x59671`: `filePath`
- `0x59698`: `filePath`
- `0x59693`: `File path is invalid`

## pseudocode

```c

```

## disassembly

```asm
0x59670  ldarg.0
0x59671  ldstr    aFilepath// "filePath"
0x59676  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrWhiteSpace(string parameter, string name)
0x5967b  ldarg.1
0x5967c  callvirt instance string Microsoft.Crm.Core.Models.BlobInfo::get_BlobChecksum()
0x59681  ldstr    aChecksum// "checkSum"
0x59686  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrWhiteSpace(string parameter, string name)
0x5968b  ldarg.0
0x5968c  call     bool [mscorlib]System.IO.File::Exists(string)
0x59691  brtrue.s loc_596A3
0x59693  ldstr    aFilePathIsInva// "File path is invalid"
0x59698  ldstr    aFilepath// "filePath"
0x5969d  newobj   instance void Microsoft.Crm.CrmArgumentException::.ctor(string message, string parameterName)
0x596a2  throw
0x596a3  ldarg.1
0x596a4  callvirt instance string Microsoft.Crm.Core.Models.BlobInfo::get_BlobChecksum()
0x596a9  ldarg.0
0x596aa  call     unsigned int8[] Microsoft.Crm.Core.FileChecksumUtility::CalculateChecksum(string filePath)
0x596af  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x596b4  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x596b9  brfalse.s loc_596DE
0x596bb  ldnull
0x596bc  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x596c1  ldc.i4.s 0x12
0x596c3  ldstr    aChecksumVerifi// "Checksum verification failed for the bl"...
0x596c8  ldc.i4.1
0x596c9  newarr   [mscorlib]System.Object
0x596ce  dup
0x596cf  ldc.i4.0
0x596d0  ldarg.1
0x596d1  callvirt instance string Microsoft.Crm.Core.Models.BlobInfo::get_BlobName()
0x596d6  stelem.ref
0x596d7  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x596dc  ldc.i4.0
0x596dd  ret
0x596de  ldc.i4.1
0x596df  ret
```
