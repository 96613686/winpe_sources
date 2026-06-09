# Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::ResetWindowsUpdate

- ea: `0x22c0`
- end: `0x2303`
- name: `Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::ResetWindowsUpdate`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x22c0`
- `0x12360`

## string_xrefs

- `0x22c8`: `Restoring orginal Windows Update service state.`

## pseudocode

```c

```

## disassembly

```asm
0x22c0  ldarg.0
0x22c1  ldfld    bool Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::_forciblyEnabledWindowsUpdate
0x22c6  brfalse.s loc_2302
0x22c8  ldstr    aRestoringOrgin// "Restoring orginal Windows Update servic"...
0x22cd  ldc.i4.0
0x22ce  newarr   [mscorlib]System.Object
0x22d3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x22d8  ldarg.0
0x22d9  ldfld    bool Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::_automaticUpdatesPaused
0x22de  brfalse.s loc_22EC
0x22e0  call     void Microsoft.Crm.Setup.Common.Utility.WindowsUpdateUtility::ResumeAutomaticUpdates()
0x22e5  ldarg.0
0x22e6  ldc.i4.0
0x22e7  stfld    bool Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::_automaticUpdatesPaused
0x22ec  ldstr    aWuauserv// "wuauserv"
0x22f1  call     string [mscorlib]System.Environment::get_MachineName()
0x22f6  call     void [Microsoft.Crm.Setup.Shared.Interop]Microsoft.Crm.Setup.Common.Utility.ServiceUtility::SetServiceToDisabled(string, string)
0x22fb  ldarg.0
0x22fc  ldc.i4.0
0x22fd  stfld    bool Microsoft.Crm.Setup.Common.RequiredComponentMsiInstallActionBase::_forciblyEnabledWindowsUpdate
0x2302  ret
```
