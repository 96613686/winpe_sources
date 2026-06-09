# Microsoft.Crm.Sandbox.SandboxStatisticsHelper::WriteWorkerExecutionRecords

- ea: `0x6060`
- end: `0x60a2`
- name: `Microsoft.Crm.Sandbox.SandboxStatisticsHelper::WriteWorkerExecutionRecords`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6060`
- `0x60b0`

## string_xrefs

- `0x607f`: `SandboxStatisticsHelper.WriteWorkerExecutionRecords: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6060  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_writeWorkerExecutionRecords
0x6065  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x606a  ldc.i4.1
0x606b  beq.s    loc_606F
0x606d  leave.s  loc_60A1
0x606f  call     void Microsoft.Crm.Sandbox.SandboxStatisticsHelper::InternalWriteWorkerExecutionRecords()
0x6074  leave.s  loc_60A1
0x6076  stloc.0
0x6077  ldloc.0
0x6078  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x607d  ldc.i4.s 0x28
0x607f  ldstr    aSandboxstatist_6// "SandboxStatisticsHelper.WriteWorkerExec"...
0x6084  ldc.i4.1
0x6085  newarr   [mscorlib]System.Object
0x608a  dup
0x608b  ldc.i4.0
0x608c  ldloc.0
0x608d  stelem.ref
0x608e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6093  leave.s  loc_60A1
0x6095  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxStatisticsHelper::_writeWorkerExecutionRecords
0x609a  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x609f  pop
0x60a0  endfinally
0x60a1  ret
```
