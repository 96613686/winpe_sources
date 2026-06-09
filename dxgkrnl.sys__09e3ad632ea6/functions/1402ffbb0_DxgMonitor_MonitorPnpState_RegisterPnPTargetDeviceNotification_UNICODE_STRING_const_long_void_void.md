# DxgMonitor::MonitorPnpState::RegisterPnPTargetDeviceNotification(_UNICODE_STRING const *,long (*)(void *,void *))

- ea: `0x1402ffbb0`
- end: `0x1402ffef9`
- name: `?RegisterPnPTargetDeviceNotification@MonitorPnpState@DxgMonitor@@QEAAJPEBU_UNICODE_STRING@@P6AJPEAX1@Z@Z`
- size: `841`
- prototype: `__int64 __fastcall(DxgMonitor::MonitorPnpState *__hidden this, PCUNICODE_STRING SourceString, int (*)(void *, void *))`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14018d718`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x140054c50`
- `0x140059238`
- `0x14005ec44`
- `0x14005ee40`
- `0x140062044`
- `0x140093d30`
- `0x1400a0cb0`
- `0x1402ffbb0`
- `0x1403f980c`

## import_xrefs

- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1402ffd6d`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1402ffd6d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402ffc59`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402ffc59`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1402ffe1e`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1402ffe1e`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402ffea7`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402ffea7`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1402ffdb4`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1402ffdb4`
- `watchdog!WdLogSingleEntry2` at `0x1402ffd02`
- `watchdog!WdLogSingleEntry2` at `0x1402ffdde`
- `watchdog!WdLogSingleEntry2` at `0x1402ffe48`
- `watchdog!WdLogSingleEntry2` at `0x1402ffe89`
- `watchdog!WdLogSingleEntry2` at `0x1402ffed1`
- `watchdog!WdLogSingleEntry2` at `0x1402ffd02`
- `watchdog!WdLogSingleEntry2` at `0x1402ffdde`
- `watchdog!WdLogSingleEntry2` at `0x1402ffe48`
- `watchdog!WdLogSingleEntry2` at `0x1402ffe89`
- `watchdog!WdLogSingleEntry2` at `0x1402ffed1`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402ffbc7`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402ffbc7`
- `watchdog!WdLogSingleEntry0` at `0x1402ffc33`
- `watchdog!WdLogSingleEntry0` at `0x1402ffd2e`
- `watchdog!WdLogSingleEntry0` at `0x1402ffd54`
- `watchdog!WdLogSingleEntry0` at `0x1402ffc33`
- `watchdog!WdLogSingleEntry0` at `0x1402ffd2e`
- `watchdog!WdLogSingleEntry0` at `0x1402ffd54`
- `watchdog!WdLogSingleEntry1` at `0x1402ffc7d`
- `watchdog!WdLogSingleEntry1` at `0x1402ffcda`
- `watchdog!WdLogSingleEntry1` at `0x1402ffc7d`
- `watchdog!WdLogSingleEntry1` at `0x1402ffcda`

## pseudocode

```c

```
