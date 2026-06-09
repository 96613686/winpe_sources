# Microsoft.Crm.Setup.Common.CreateSqmRegistryAction::Do

- ea: `0x29a0`
- end: `0x2a34`
- name: `Microsoft.Crm.Setup.Common.CreateSqmRegistryAction::Do`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x27d0`
- `0x27e0`
- `0x27f0`
- `0x2810`
- `0x2970`
- `0x29a0`

## pseudocode

```c

```

## disassembly

```asm
0x29a0  ldarg.1
0x29a1  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x29a6  stloc.0
0x29a7  ldarg.0
0x29a8  call     instance class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument Microsoft.Crm.Setup.Common.SqmAction::get_Argument()
0x29ad  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.Crm.Setup.Common.SqmConfiguratorArgument::get_MscrmRegistryHive()
0x29b2  ldarg.0
0x29b3  call     instance class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument Microsoft.Crm.Setup.Common.SqmAction::get_Argument()
0x29b8  callvirt instance string Microsoft.Crm.Setup.Common.SqmConfiguratorArgument::get_MscrmRegistryKey()
0x29bd  ldc.i4.1
0x29be  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x29c3  stloc.1
0x29c4  ldarg.0
0x29c5  call     instance class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument Microsoft.Crm.Setup.Common.SqmAction::get_Argument()
0x29ca  callvirt instance bool Microsoft.Crm.Setup.Common.SqmConfiguratorArgument::get_IsServerSetup()
0x29cf  brtrue.s loc_2A0F
0x29d1  ldloc.0
0x29d2  callvirt instance bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_SqmOptIn()
0x29d7  brfalse.s loc_29EC
0x29d9  ldloc.1
0x29da  ldstr    aSqmenabled// "SQMEnabled"
0x29df  ldc.i4.1
0x29e0  box      [mscorlib]System.Int32
0x29e5  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x29ea  br.s     loc_29FD
0x29ec  ldloc.1
0x29ed  ldstr    aSqmenabled// "SQMEnabled"
0x29f2  ldc.i4.0
0x29f3  box      [mscorlib]System.Int32
0x29f8  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x29fd  ldloc.1
0x29fe  ldstr    aSqmmaxqueuesiz// "SQMMaxQueueSize"
0x2a03  ldc.i4.s 0x1E
0x2a05  box      [mscorlib]System.Int32
0x2a0a  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x2a0f  ldarg.0
0x2a10  call     instance class Microsoft.Crm.Setup.Common.SqmConfiguratorArgument Microsoft.Crm.Setup.Common.SqmAction::get_Argument()
0x2a15  callvirt instance string Microsoft.Crm.Setup.Common.SqmConfiguratorArgument::get_SqmQueueLocationFolder()
0x2a1a  stloc.2
0x2a1b  ldloc.1
0x2a1c  ldstr    aSqmqueuelocati// "SQMQueueLocation"
0x2a21  ldloc.2
0x2a22  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x2a27  leave.s  loc_2A33
0x2a29  ldloc.1
0x2a2a  brfalse.s loc_2A32
0x2a2c  ldloc.1
0x2a2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a32  endfinally
0x2a33  ret
```
