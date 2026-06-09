# Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::Execute

- ea: `0x18a00`
- end: `0x18a7f`
- name: `Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::Execute`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x19440`

## callees

- `0x18a00`
- `0x18a80`
- `0x18ab0`

## string_xrefs

- `0x18a35`: `ReadSolution`
- `0x18a54`: `UpdateSolution`

## pseudocode

```c

```

## disassembly

```asm
0x18a00  ldarg.1
0x18a01  ldstr    aSolutionunique// "solutionUniqueName"
0x18a06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x18a0b  ldarg.2
0x18a0c  ldstr    aSolutionfilena// "solutionFileName"
0x18a11  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x18a16  ldstr    aImportcustomso// "ImportCustomSolution"
0x18a1b  ldc.r8   100000.0
0x18a24  ldc.i4.1
0x18a25  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::CreateAndStart(string, float64, bool)
0x18a2a  stloc.0
0x18a2b  ldloc.0
0x18a2c  ldc.i4.2
0x18a2d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CounterList::set_LevelOfTrace(valuetype [System]System.Diagnostics.TraceLevel)
0x18a32  ldnull
0x18a33  stloc.1
0x18a34  ldloc.0
0x18a35  ldstr    aReadsolution// "ReadSolution"
0x18a3a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x18a3f  stloc.2
0x18a40  ldarg.2
0x18a41  call     unsigned int8[] Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::ReadSolutionBytes(string solutionFileName)
0x18a46  stloc.1
0x18a47  leave.s  loc_18A53
0x18a49  ldloc.2
0x18a4a  brfalse.s loc_18A52
0x18a4c  ldloc.2
0x18a4d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18a52  endfinally
0x18a53  ldloc.0
0x18a54  ldstr    aUpdatesolution// "UpdateSolution"
0x18a59  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x18a5e  stloc.2
0x18a5f  ldarg.0
0x18a60  ldarg.1
0x18a61  ldarg.2
0x18a62  ldloc.1
0x18a63  call     instance void Microsoft.Crm.SE.DllMethodActions.ImportCustomSolution::InstallSolution(string solutionUniqueName, string solutionFileName, unsigned int8[] solutionBytes)
0x18a68  leave.s  loc_18A7E
0x18a6a  ldloc.2
0x18a6b  brfalse.s loc_18A73
0x18a6d  ldloc.2
0x18a6e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18a73  endfinally
0x18a74  ldloc.0
0x18a75  brfalse.s loc_18A7D
0x18a77  ldloc.0
0x18a78  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18a7d  endfinally
0x18a7e  ret
```
