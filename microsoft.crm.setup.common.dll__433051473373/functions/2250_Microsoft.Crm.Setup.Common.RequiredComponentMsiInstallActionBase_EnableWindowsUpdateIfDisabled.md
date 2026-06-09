# Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::EnableWindowsUpdateIfDisabled

- ea: `0x2250`
- end: `0x22b5`
- name: `Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::EnableWindowsUpdateIfDisabled`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2250`
- `0x122e0`

## string_xrefs

- `0x2250`: `Component installation requires windows update service`
- `0x2271`: `Windows Update Service is currently disabled -- enabling the service`
- `0x2299`: `Windows Update Service is not disabled`

## pseudocode

```c

```

## disassembly

```asm
0x2250  ldstr    aComponentInsta// "Component installation requires windows"...
0x2255  ldc.i4.0
0x2256  newarr   [mscorlib]System.Object
0x225b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x2260  ldstr    aWuauserv// "wuauserv"
0x2265  call     string [mscorlib]System.Environment::get_MachineName()
0x226a  call     bool [Microsoft.Crm.Setup.Shared.Interop]Microsoft.Crm.Setup.Common.Utility.ServiceUtility::IsServiceDisabled(string, string)
0x226f  brfalse.s loc_2299
0x2271  ldstr    aWindowsUpdateS// "Windows Update Service is currently dis"...
0x2276  ldc.i4.0
0x2277  newarr   [mscorlib]System.Object
0x227c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x2281  ldstr    aWuauserv// "wuauserv"
0x2286  call     string [mscorlib]System.Environment::get_MachineName()
0x228b  call     void [Microsoft.Crm.Setup.Shared.Interop]Microsoft.Crm.Setup.Common.Utility.ServiceUtility::SetServiceToAutoStart(string, string)
0x2290  ldarg.0
0x2291  ldc.i4.1
0x2292  stfld    bool Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::_forciblyEnabledWindowsUpdate
0x2297  br.s     loc_22A9
0x2299  ldstr    aWindowsUpdateS_0// "Windows Update Service is not disabled"
0x229e  ldc.i4.0
0x229f  newarr   [mscorlib]System.Object
0x22a4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x22a9  ldarg.0
0x22aa  call     bool Microsoft.Crm.Setup.Common.Utility.WindowsUpdateUtility::PauseAutomaticUpdates()
0x22af  stfld    bool Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::_automaticUpdatesPaused
0x22b4  ret
```
