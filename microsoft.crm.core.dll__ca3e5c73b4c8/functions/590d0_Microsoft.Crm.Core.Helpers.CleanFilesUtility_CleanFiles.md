# Microsoft.Crm.Core.Helpers.CleanFilesUtility::CleanFiles

- ea: `0x590d0`
- end: `0x591ea`
- name: `Microsoft.Crm.Core.Helpers.CleanFilesUtility::CleanFiles`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x59410`

## callees

- `0x1be80`
- `0x1c070`
- `0x1eaa0`
- `0x1f510`
- `0x590d0`

## string_xrefs

- `0x590dc`: `downloadPath`
- `0x590fe`: `Invalid directory data.`
- `0x5915d`: `Error occurred while deleting the directory {0} : {1}`
- `0x59187`: `Error occurred while deleting the directory {0} : {1}`
- `0x591b2`: `Error occurred while deleting the directory {0} : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x590d0  ldarg.1
0x590d1  ldstr    aDirectories// "directories"
0x590d6  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x590db  ldarg.0
0x590dc  ldstr    aDownloadpath// "downloadPath"
0x590e1  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrWhiteSpace(string parameter, string name)
0x590e6  ldarg.0
0x590e7  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x590ec  brfalse.s loc_590F6
0x590ee  ldarg.1
0x590ef  call     T0x2B00004B
0x590f4  brtrue.s loc_5910F
0x590f6  ldnull
0x590f7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x590fc  ldc.i4.s 0x12
0x590fe  ldstr    aInvalidDirecto// "Invalid directory data."
0x59103  ldc.i4.0
0x59104  newarr   [mscorlib]System.Object
0x59109  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5910e  ret
0x5910f  ldarg.1
0x59110  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x59115  stloc.0
0x59116  br       loc_591D2
0x5911b  ldloc.0
0x5911c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x59121  stloc.1
0x59122  ldloc.1
0x59123  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x59128  brtrue   loc_591D2
0x5912d  ldarg.0
0x5912e  ldloc.1
0x5912f  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x59134  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x59139  brfalse  loc_591D2
0x5913e  ldarg.0
0x5913f  ldloc.1
0x59140  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x59145  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x5914a  stloc.2
0x5914b  ldloc.2
0x5914c  ldc.i4.1
0x5914d  callvirt instance void [mscorlib]System.IO.DirectoryInfo::Delete(bool)
0x59152  leave.s  loc_591D2
0x59154  stloc.3
0x59155  ldloc.3
0x59156  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5915b  ldc.i4.s 0x12
0x5915d  ldstr    aErrorOccurredW_0// "Error occurred while deleting the direc"...
0x59162  ldc.i4.2
0x59163  newarr   [mscorlib]System.Object
0x59168  dup
0x59169  ldc.i4.0
0x5916a  ldloc.2
0x5916b  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x59170  stelem.ref
0x59171  dup
0x59172  ldc.i4.1
0x59173  ldloc.3
0x59174  stelem.ref
0x59175  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5917a  leave.s  loc_591D2
0x5917c  stloc.s  4
0x5917e  ldloc.s  4
0x59180  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x59185  ldc.i4.s 0x12
0x59187  ldstr    aErrorOccurredW_0// "Error occurred while deleting the direc"...
0x5918c  ldc.i4.2
0x5918d  newarr   [mscorlib]System.Object
0x59192  dup
0x59193  ldc.i4.0
0x59194  ldloc.2
0x59195  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x5919a  stelem.ref
0x5919b  dup
0x5919c  ldc.i4.1
0x5919d  ldloc.s  4
0x5919f  stelem.ref
0x591a0  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x591a5  leave.s  loc_591D2
0x591a7  stloc.s  5
0x591a9  ldloc.s  5
0x591ab  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x591b0  ldc.i4.s 0x12
0x591b2  ldstr    aErrorOccurredW_0// "Error occurred while deleting the direc"...
0x591b7  ldc.i4.2
0x591b8  newarr   [mscorlib]System.Object
0x591bd  dup
0x591be  ldc.i4.0
0x591bf  ldloc.2
0x591c0  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x591c5  stelem.ref
0x591c6  dup
0x591c7  ldc.i4.1
0x591c8  ldloc.s  5
0x591ca  stelem.ref
0x591cb  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x591d0  leave.s  loc_591D2
0x591d2  ldloc.0
0x591d3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x591d8  brtrue   loc_5911B
0x591dd  leave.s  loc_591E9
0x591df  ldloc.0
0x591e0  brfalse.s loc_591E8
0x591e2  ldloc.0
0x591e3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x591e8  endfinally
0x591e9  ret
```
