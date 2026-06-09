# Microsoft.Crm.Setup.Common.RemoveSqmRegistryAction::Do

- ea: `0x2ac0`
- end: `0x2b1e`
- name: `Microsoft.Crm.Setup.Common.RemoveSqmRegistryAction::Do`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x27d0`
- `0x27e0`
- `0x2810`
- `0x2970`
- `0x2ac0`

## pseudocode

```c

```

## disassembly

```asm
0x2ac0  ldarg.0
0x2ac1  call     instance class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument Microsoft.Crm.Setup.Common.SqmAction::get_Argument()
0x2ac6  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.Crm.Setup.Common.SqmConfiguratorArgument::get_MscrmRegistryHive()
0x2acb  ldarg.0
0x2acc  call     instance class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument Microsoft.Crm.Setup.Common.SqmAction::get_Argument()
0x2ad1  callvirt instance string Microsoft.Crm.Setup.Common.SqmConfiguratorArgument::get_MscrmRegistryKey()
0x2ad6  ldc.i4.1
0x2ad7  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x2adc  stloc.0
0x2add  ldloc.0
0x2ade  brfalse.s loc_2B11
0x2ae0  ldarg.0
0x2ae1  call     instance class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument Microsoft.Crm.Setup.Common.SqmAction::get_Argument()
0x2ae6  callvirt instance bool Microsoft.Crm.Setup.Common.SqmConfiguratorArgument::get_IsServerSetup()
0x2aeb  brtrue.s loc_2B05
0x2aed  ldloc.0
0x2aee  ldstr    aSqmenabled// "SQMEnabled"
0x2af3  ldc.i4.0
0x2af4  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string, bool)
0x2af9  ldloc.0
0x2afa  ldstr    aSqmmaxqueuesiz// "SQMMaxQueueSize"
0x2aff  ldc.i4.0
0x2b00  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string, bool)
0x2b05  ldloc.0
0x2b06  ldstr    aSqmqueuelocati// "SQMQueueLocation"
0x2b0b  ldc.i4.0
0x2b0c  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string, bool)
0x2b11  leave.s  loc_2B1D
0x2b13  ldloc.0
0x2b14  brfalse.s loc_2B1C
0x2b16  ldloc.0
0x2b17  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b1c  endfinally
0x2b1d  ret
```
