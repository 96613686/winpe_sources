# Microsoft.Crm.Setup.Common.Utility.PowershellSystemComponentManager::ProcessExitCode

- ea: `0x11ce0`
- end: `0x11e0f`
- name: `Microsoft.Crm.Setup.Common.Utility.PowershellSystemComponentManager::ProcessExitCode`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11c70`

## callees

- `0xff0`
- `0x116c0`
- `0x11ce0`

## string_xrefs

- `0x11d48`: `Components successfully enabled, but reboot is required for completion`
- `0x11d1e`: `Components successfully enabled`
- `0x11d33`: `No additional components need to be enabled.`
- `0x11d69`: `Component installation with PowerShell failed.`
- `0x11d88`: `Component installation failed and a restart is required.`
- `0x11da7`: `Invalid arguments were passed to powershell while enabling components.`
- `0x11dc6`: `Unknown failure while enabling components with powershell. Exit code: {0}`
- `0x11df4`: `SystemComponentManager.Powershell.ErrorEnablingSystemComponents`

## pseudocode

```c

```

## disassembly

```asm
0x11ce0  ldnull
0x11ce1  stloc.0
0x11ce2  ldarg.1
0x11ce3  ldc.i4.4
0x11ce4  bgt.s    loc_11CF5
0x11ce6  ldarg.1
0x11ce7  brfalse.s loc_11D1E
0x11ce9  ldarg.1
0x11cea  ldc.i4.4
0x11ceb  beq      loc_11DA7
0x11cf0  br       loc_11DC6
0x11cf5  ldarg.1
0x11cf6  ldc.i4   0x3E8
0x11cfb  sub
0x11cfc  switch   loc_11D69, loc_11D88, loc_11DC6, loc_11D33
0x11d11  ldarg.1
0x11d12  ldc.i4   0xBC2
0x11d17  beq.s    loc_11D48
0x11d19  br       loc_11DC6
0x11d1e  ldstr    aComponentsSucc_0// "Components successfully enabled"
0x11d23  ldc.i4.0
0x11d24  newarr   [mscorlib]System.Object
0x11d29  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x11d2e  br       loc_11DEC
0x11d33  ldstr    aNoAdditionalCo// "No additional components need to be ena"...
0x11d38  ldc.i4.0
0x11d39  newarr   [mscorlib]System.Object
0x11d3e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x11d43  br       loc_11DEC
0x11d48  ldstr    aComponentsSucc// "Components successfully enabled, but re"...
0x11d4d  ldc.i4.0
0x11d4e  newarr   [mscorlib]System.Object
0x11d53  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x11d58  ldarg.0
0x11d59  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_InstallInfo()
0x11d5e  ldc.i4.1
0x11d5f  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::set_RebootRequired(bool)
0x11d64  br       loc_11DEC
0x11d69  ldstr    aComponentInsta_0// "Component installation with PowerShell "...
0x11d6e  ldc.i4.0
0x11d6f  newarr   [mscorlib]System.Object
0x11d74  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x11d79  ldarga.s 1
0x11d7b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11d80  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11d85  stloc.0
0x11d86  br.s     loc_11DEC
0x11d88  ldstr    aComponentInsta_1// "Component installation failed and a res"...
0x11d8d  ldc.i4.0
0x11d8e  newarr   [mscorlib]System.Object
0x11d93  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x11d98  ldarga.s 1
0x11d9a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11d9f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11da4  stloc.0
0x11da5  br.s     loc_11DEC
0x11da7  ldstr    aInvalidArgumen// "Invalid arguments were passed to powers"...
0x11dac  ldc.i4.0
0x11dad  newarr   [mscorlib]System.Object
0x11db2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x11db7  ldarga.s 1
0x11db9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11dbe  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11dc3  stloc.0
0x11dc4  br.s     loc_11DEC
0x11dc6  ldstr    aUnknownFailure// "Unknown failure while enabling componen"...
0x11dcb  ldc.i4.1
0x11dcc  newarr   [mscorlib]System.Object
0x11dd1  dup
0x11dd2  ldc.i4.0
0x11dd3  ldarg.1
0x11dd4  box      [mscorlib]System.Int32
0x11dd9  stelem.ref
0x11dda  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x11ddf  ldarga.s 1
0x11de1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11de6  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11deb  stloc.0
0x11dec  ldloc.0
0x11ded  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11df2  brtrue.s loc_11E0E
0x11df4  ldstr    aSystemcomponen_2// "SystemComponentManager.Powershell.Error"...
0x11df9  ldc.i4.1
0x11dfa  newarr   [mscorlib]System.Object
0x11dff  dup
0x11e00  ldc.i4.0
0x11e01  ldloc.0
0x11e02  stelem.ref
0x11e03  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x11e08  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0x11e0d  throw
0x11e0e  ret
```
