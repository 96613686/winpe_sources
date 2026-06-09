# Microsoft.Crm.Core.Helpers.FileJoiner::CleanFileDirectory

- ea: `0x597b0`
- end: `0x5984f`
- name: `Microsoft.Crm.Core.Helpers.FileJoiner::CleanFileDirectory`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x59410`

## callees

- `0x1eaa0`
- `0x1f510`
- `0x597b0`

## string_xrefs

- `0x597df`: `Error occurred while deleting the directory {0} : {1}`
- `0x59807`: `Error occurred while deleting the directory {0} : {1}`
- `0x5982f`: `Error occurred while deleting the directory {0} : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x597b0  ldarg.0
0x597b1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x597b6  brtrue   loc_5984E
0x597bb  ldarg.0
0x597bc  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x597c1  brfalse  loc_5984E
0x597c6  ldarg.0
0x597c7  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x597cc  stloc.0
0x597cd  ldloc.0
0x597ce  ldc.i4.1
0x597cf  callvirt instance void [mscorlib]System.IO.DirectoryInfo::Delete(bool)
0x597d4  leave.s  loc_5984E
0x597d6  stloc.1
0x597d7  ldloc.1
0x597d8  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x597dd  ldc.i4.s 0x12
0x597df  ldstr    aErrorOccurredW_0// "Error occurred while deleting the direc"...
0x597e4  ldc.i4.2
0x597e5  newarr   [mscorlib]System.Object
0x597ea  dup
0x597eb  ldc.i4.0
0x597ec  ldloc.0
0x597ed  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x597f2  stelem.ref
0x597f3  dup
0x597f4  ldc.i4.1
0x597f5  ldloc.1
0x597f6  stelem.ref
0x597f7  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x597fc  leave.s  loc_5984E
0x597fe  stloc.2
0x597ff  ldloc.2
0x59800  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x59805  ldc.i4.s 0x12
0x59807  ldstr    aErrorOccurredW_0// "Error occurred while deleting the direc"...
0x5980c  ldc.i4.2
0x5980d  newarr   [mscorlib]System.Object
0x59812  dup
0x59813  ldc.i4.0
0x59814  ldloc.0
0x59815  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x5981a  stelem.ref
0x5981b  dup
0x5981c  ldc.i4.1
0x5981d  ldloc.2
0x5981e  stelem.ref
0x5981f  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x59824  leave.s  loc_5984E
0x59826  stloc.3
0x59827  ldloc.3
0x59828  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5982d  ldc.i4.s 0x12
0x5982f  ldstr    aErrorOccurredW_0// "Error occurred while deleting the direc"...
0x59834  ldc.i4.2
0x59835  newarr   [mscorlib]System.Object
0x5983a  dup
0x5983b  ldc.i4.0
0x5983c  ldloc.0
0x5983d  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x59842  stelem.ref
0x59843  dup
0x59844  ldc.i4.1
0x59845  ldloc.3
0x59846  stelem.ref
0x59847  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5984c  leave.s  loc_5984E
0x5984e  ret
```
