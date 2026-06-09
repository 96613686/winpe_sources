# Microsoft.Crm.Tools.Admin.ImportAppsSolution::Execute

- ea: `0x5be0`
- end: `0x5c58`
- name: `Microsoft.Crm.Tools.Admin.ImportAppsSolution::Execute`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5be0`
- `0x5c60`
- `0x5c90`

## string_xrefs

- `0x5c0e`: `ReadSolution`
- `0x5c2d`: `UpdateSolution`

## pseudocode

```c

```

## disassembly

```asm
0x5be0  ldarg.1
0x5be1  ldstr    aSolutionunique// "solutionUniqueName"
0x5be6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5beb  ldarg.2
0x5bec  ldstr    aSolutionfilena// "solutionFileName"
0x5bf1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5bf6  ldstr    aImportappssolu// "ImportAppsSolution"
0x5bfb  ldc.r8   3600000.0
0x5c04  ldc.i4.1
0x5c05  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::CreateAndStart(string, float64, bool)
0x5c0a  stloc.0
0x5c0b  ldnull
0x5c0c  stloc.1
0x5c0d  ldloc.0
0x5c0e  ldstr    aReadsolution// "ReadSolution"
0x5c13  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x5c18  stloc.2
0x5c19  ldarg.2
0x5c1a  call     unsigned int8[] Microsoft.Crm.Tools.Admin.ImportAppsSolution::ReadSolutionBytes(string solutionFileName)
0x5c1f  stloc.1
0x5c20  leave.s  loc_5C2C
0x5c22  ldloc.2
0x5c23  brfalse.s loc_5C2B
0x5c25  ldloc.2
0x5c26  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5c2b  endfinally
0x5c2c  ldloc.0
0x5c2d  ldstr    aUpdatesolution// "UpdateSolution"
0x5c32  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x5c37  stloc.2
0x5c38  ldarg.0
0x5c39  ldarg.1
0x5c3a  ldarg.2
0x5c3b  ldloc.1
0x5c3c  call     instance void Microsoft.Crm.Tools.Admin.ImportAppsSolution::InstallSolution(string solutionUniqueName, string solutionFileName, unsigned int8[] solutionBytes)
0x5c41  leave.s  loc_5C57
0x5c43  ldloc.2
0x5c44  brfalse.s loc_5C4C
0x5c46  ldloc.2
0x5c47  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5c4c  endfinally
0x5c4d  ldloc.0
0x5c4e  brfalse.s loc_5C56
0x5c50  ldloc.0
0x5c51  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5c56  endfinally
0x5c57  ret
```
