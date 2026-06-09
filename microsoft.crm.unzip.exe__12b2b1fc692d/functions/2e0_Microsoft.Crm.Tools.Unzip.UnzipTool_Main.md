# Microsoft.Crm.Tools.Unzip.UnzipTool::Main

- ea: `0x2e0`
- end: `0x3b7`
- name: `Microsoft.Crm.Tools.Unzip.UnzipTool::Main`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x2c0`
- `0x2e0`
- `0x3c0`
- `0x400`
- `0xb10`
- `0xb30`
- `0xb50`

## pseudocode

```c

```

## disassembly

```asm
0x2e0  .entrypoint// "ZIN41-TE1EG-WXE84-8HBA"
0x2e5  call     void [Xceed.Zip]Xceed.Zip.Licenser::set_LicenseKey(string)
0x2ea  ldarg.0
0x2eb  ldlen
0x2ec  conv.i4
0x2ed  ldc.i4.1
0x2ee  bne.un.s loc_307
0x2f0  ldarg.0
0x2f1  ldc.i4.0
0x2f2  ldelem.ref
0x2f3  ldstr    asc_102E// "/?"
0x2f8  ldc.i4.5
0x2f9  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2fe  brtrue.s loc_307
0x300  call     void Microsoft.Crm.Tools.Unzip.UnzipTool::ShowUsage()
0x305  ldc.i4.0
0x306  ret
0x307  ldarg.0
0x308  ldlen
0x309  conv.i4
0x30a  ldc.i4.3
0x30b  beq.s    loc_314
0x30d  call     void Microsoft.Crm.Tools.Unzip.UnzipTool::ShowUsage()
0x312  ldc.i4.1
0x313  ret
0x314  newobj   instance void Microsoft.Crm.Tools.Unzip.UnzipTool::.ctor()
0x319  stloc.0
0x31a  ldloc.0
0x31b  ldarg.0
0x31c  callvirt instance void Microsoft.Crm.Tools.Unzip.UnzipTool::ParseArguments(string[] args)
0x321  ldloc.0
0x322  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.Unzip.UnzipTool::RunUnzip()
0x327  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x32c  stloc.1
0x32d  br.s     loc_34D
0x32f  ldloca.s 1
0x331  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x336  stloc.2
0x337  ldloc.0
0x338  ldc.i4.3
0x339  ldstr    aExtracted0// "Extracted {0}"
0x33e  ldc.i4.1
0x33f  newarr   [mscorlib]System.Object
0x344  dup
0x345  ldc.i4.0
0x346  ldloc.2
0x347  stelem.ref
0x348  callvirt instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x34d  ldloca.s 1
0x34f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x354  brtrue.s loc_32F
0x356  leave.s  loc_366
0x358  ldloca.s 1
0x35a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x360  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x365  endfinally
0x366  ldc.i4.0
0x367  stloc.3
0x368  leave.s  loc_3B5
0x36a  stloc.s  4
0x36c  ldloc.0
0x36d  ldc.i4.1
0x36e  ldstr    aExitingWithErr// "Exiting with error code {0}"
0x373  ldc.i4.1
0x374  newarr   [mscorlib]System.Object
0x379  dup
0x37a  ldc.i4.0
0x37b  ldloc.s  4
0x37d  callvirt instance int32 Microsoft.Crm.Tools.Unzip.UnzipToolException::get_ErrorCode()
0x382  box      [mscorlib]System.Int32
0x387  stelem.ref
0x388  callvirt instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x38d  ldloc.s  4
0x38f  callvirt instance int32 Microsoft.Crm.Tools.Unzip.UnzipToolException::get_ErrorCode()
0x394  stloc.3
0x395  leave.s  loc_3B5
0x397  stloc.s  5
0x399  ldloc.0
0x39a  ldc.i4.1
0x39b  ldstr    aUnexpectedExce// "Unexpected exception {0}"
0x3a0  ldc.i4.1
0x3a1  newarr   [mscorlib]System.Object
0x3a6  dup
0x3a7  ldc.i4.0
0x3a8  ldloc.s  5
0x3aa  stelem.ref
0x3ab  callvirt instance void Microsoft.Crm.Tools.Unzip.UnzipTool::LogTrace(valuetype [System]System.Diagnostics.TraceLevel level, string format, object[] args)
0x3b0  ldc.i4.s 0x14
0x3b2  stloc.3
0x3b3  leave.s  loc_3B5
0x3b5  ldloc.3
0x3b6  ret
```
