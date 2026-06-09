# DxgMonitor::MonitorPnpState::RegisterPnPTargetDeviceNotification(_UNICODE_STRING const *,long (*)(void *,void *))

- ea: `0x1402f8f30`
- end: `0x1402f9279`
- name: `?RegisterPnPTargetDeviceNotification@MonitorPnpState@DxgMonitor@@QEAAJPEBU_UNICODE_STRING@@P6AJPEAX1@Z@Z`
- size: `841`
- prototype: `__int64 __fastcall(DxgMonitor::MonitorPnpState *__hidden this, PCUNICODE_STRING SourceString, int (*)(void *, void *))`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140189718`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x140054a70`
- `0x140058fc8`
- `0x14005e890`
- `0x14005ea8c`
- `0x140061c94`
- `0x140093260`
- `0x1400a01e0`
- `0x1402f8f30`
- `0x1403fbdac`

## import_xrefs

- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1402f90ed`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1402f90ed`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402f8fd9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1402f8fd9`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1402f919e`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x1402f919e`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402f9227`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1402f9227`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1402f9134`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1402f9134`
- `watchdog!WdLogSingleEntry2` at `0x1402f9082`
- `watchdog!WdLogSingleEntry2` at `0x1402f915e`
- `watchdog!WdLogSingleEntry2` at `0x1402f91c8`
- `watchdog!WdLogSingleEntry2` at `0x1402f9209`
- `watchdog!WdLogSingleEntry2` at `0x1402f9251`
- `watchdog!WdLogSingleEntry2` at `0x1402f9082`
- `watchdog!WdLogSingleEntry2` at `0x1402f915e`
- `watchdog!WdLogSingleEntry2` at `0x1402f91c8`
- `watchdog!WdLogSingleEntry2` at `0x1402f9209`
- `watchdog!WdLogSingleEntry2` at `0x1402f9251`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402f8f47`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402f8f47`
- `watchdog!WdLogSingleEntry0` at `0x1402f8fb3`
- `watchdog!WdLogSingleEntry0` at `0x1402f90ae`
- `watchdog!WdLogSingleEntry0` at `0x1402f90d4`
- `watchdog!WdLogSingleEntry0` at `0x1402f8fb3`
- `watchdog!WdLogSingleEntry0` at `0x1402f90ae`
- `watchdog!WdLogSingleEntry0` at `0x1402f90d4`
- `watchdog!WdLogSingleEntry1` at `0x1402f8ffd`
- `watchdog!WdLogSingleEntry1` at `0x1402f905a`
- `watchdog!WdLogSingleEntry1` at `0x1402f8ffd`
- `watchdog!WdLogSingleEntry1` at `0x1402f905a`

## pseudocode

```c

```
