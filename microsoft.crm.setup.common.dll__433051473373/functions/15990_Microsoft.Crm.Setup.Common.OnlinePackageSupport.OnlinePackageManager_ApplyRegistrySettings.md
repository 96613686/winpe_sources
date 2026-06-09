# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ApplyRegistrySettings

- ea: `0x15990`
- end: `0x15a08`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ApplyRegistrySettings`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x15500`

## callees

- `0x13210`
- `0x14fe0`
- `0x15990`
- `0x15d30`
- `0x166f0`

## string_xrefs

- `0x15990`: `Applying registry settings from packing list`
- `0x159a6`: `Expected to find at least one registry operation`
- `0x159ee`: `Finished applying registry settings from packing list`

## pseudocode

```c

```

## disassembly

```asm
0x15990  ldstr    aApplyingRegist// "Applying registry settings from packing"...
0x15995  ldc.i4.0
0x15996  newarr   [mscorlib]System.Object
0x1599b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x159a0  ldarg.1
0x159a1  call     T0x2B00001C
0x159a6  ldstr    aExpectedToFind_0// "Expected to find at least one registry "...
0x159ab  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x159b0  ldarg.1
0x159b1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>::GetEnumerator()
0x159b6  stloc.0
0x159b7  br.s     loc_159DA
0x159b9  ldloc.0
0x159ba  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>::get_Current()
0x159bf  callvirt instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation::Execute()
0x159c4  stloc.1
0x159c5  ldloc.1
0x159c6  brfalse.s loc_159DA
0x159c8  ldarg.0
0x159c9  call     instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::get_RollbackDescriptor()
0x159ce  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_RegistryOperations()
0x159d3  ldc.i4.0
0x159d4  ldloc.1
0x159d5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>::Insert(int32, var<u1>)
0x159da  ldloc.0
0x159db  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x159e0  brtrue.s loc_159B9
0x159e2  leave.s  loc_159EE
0x159e4  ldloc.0
0x159e5  brfalse.s loc_159ED
0x159e7  ldloc.0
0x159e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x159ed  endfinally
0x159ee  ldstr    aFinishedApplyi// "Finished applying registry settings fro"...
0x159f3  ldc.i4.0
0x159f4  newarr   [mscorlib]System.Object
0x159f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x159fe  leave.s  loc_15A07
0x15a00  ldarg.0
0x15a01  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::FlushRollbackDescriptor()
0x15a06  endfinally
0x15a07  ret
```
