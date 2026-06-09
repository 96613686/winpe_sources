# Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::IsLightClient

- ea: `0x12ec0`
- end: `0x12f1d`
- name: `Microsoft.Crm.Setup.Common.Update.DBUpdateDatabaseInstaller::IsLightClient`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x12f80`

## callees

- `0xff0`
- `0x12ec0`

## string_xrefs

- `0x12ed3`: `OpenSubKey.Failed`

## pseudocode

```c

```

## disassembly

```asm
0x12ec0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x12ec5  ldstr    aSoftwareMicros_2// "SOFTWARE\\Microsoft\\MSCRMClient"
0x12eca  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x12ecf  stloc.0
0x12ed0  ldloc.0
0x12ed1  brtrue.s loc_12EF1
0x12ed3  ldstr    aOpensubkeyFail// "OpenSubKey.Failed"
0x12ed8  ldc.i4.1
0x12ed9  newarr   [mscorlib]System.Object
0x12ede  dup
0x12edf  ldc.i4.0
0x12ee0  ldstr    aSoftwareMicros_2// "SOFTWARE\\Microsoft\\MSCRMClient"
0x12ee5  stelem.ref
0x12ee6  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x12eeb  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0x12ef0  throw
0x12ef1  ldloc.0
0x12ef2  ldstr    aLightclient// "LightClient"
0x12ef7  ldc.i4.1
0x12ef8  box      [mscorlib]System.Int32
0x12efd  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x12f02  unbox.any [mscorlib]System.Int32
0x12f07  brtrue.s loc_12F0D
0x12f09  ldc.i4.0
0x12f0a  stloc.1
0x12f0b  leave.s  loc_12F1B
0x12f0d  leave.s  loc_12F19
0x12f0f  ldloc.0
0x12f10  brfalse.s loc_12F18
0x12f12  ldloc.0
0x12f13  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12f18  endfinally
0x12f19  ldc.i4.1
0x12f1a  ret
0x12f1b  ldloc.1
0x12f1c  ret
```
