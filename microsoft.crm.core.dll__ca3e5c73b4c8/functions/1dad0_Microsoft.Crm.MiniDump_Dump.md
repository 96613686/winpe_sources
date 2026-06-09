# Microsoft.Crm.MiniDump::Dump

- ea: `0x1dad0`
- end: `0x1db44`
- name: `Microsoft.Crm.MiniDump::Dump`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1d9f0`

## callees

- `0x1dad0`
- `0x1db50`
- `0x1dca0`
- `0x1eaa0`
- `0x1f4b0`
- `0x1f4d0`
- `0x1f510`

## string_xrefs

- `0x1dad7`: `Attempting to create a mini-dump in response to {0} event. `
- `0x1db0b`: `Successfully created mini-dump at '{0}'.`
- `0x1db2c`: `Failed to create mini-dump due to exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1dad0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1dad5  ldc.i4.s 0x14
0x1dad7  ldstr    aAttemptingToCr// "Attempting to create a mini-dump in res"...
0x1dadc  ldc.i4.1
0x1dadd  newarr   [mscorlib]System.Object
0x1dae2  dup
0x1dae3  ldc.i4.0
0x1dae4  ldarg.1
0x1dae5  box      Microsoft.Crm.MiniDumpReasons
0x1daea  stelem.ref
0x1daeb  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x1daf0  ldarg.0
0x1daf1  call     instance string Microsoft.Crm.MiniDump::CreateDump()
0x1daf6  stloc.0
0x1daf7  ldarg.1
0x1daf8  ldc.i4.8
0x1daf9  or
0x1dafa  ldc.i4.8
0x1dafb  beq.s    loc_1DB04
0x1dafd  ldloc.0
0x1dafe  ldarg.2
0x1daff  call     void Microsoft.Crm.MiniDump::CreateExceptionFile(string dumpFileName, class [mscorlib]System.Exception e)
0x1db04  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1db09  ldc.i4.s 0x14
0x1db0b  ldstr    aSuccessfullyCr// "Successfully created mini-dump at '{0}'"...
0x1db10  ldc.i4.1
0x1db11  newarr   [mscorlib]System.Object
0x1db16  dup
0x1db17  ldc.i4.0
0x1db18  ldloc.0
0x1db19  stelem.ref
0x1db1a  call     void Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x1db1f  ldloc.0
0x1db20  stloc.1
0x1db21  leave.s  loc_1DB42
0x1db23  stloc.2
0x1db24  ldloc.2
0x1db25  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1db2a  ldc.i4.s 0x14
0x1db2c  ldstr    aFailedToCreate// "Failed to create mini-dump due to excep"...
0x1db31  ldc.i4.1
0x1db32  newarr   [mscorlib]System.Object
0x1db37  dup
0x1db38  ldc.i4.0
0x1db39  ldloc.2
0x1db3a  stelem.ref
0x1db3b  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x1db40  rethrow
0x1db42  ldloc.1
0x1db43  ret
```
