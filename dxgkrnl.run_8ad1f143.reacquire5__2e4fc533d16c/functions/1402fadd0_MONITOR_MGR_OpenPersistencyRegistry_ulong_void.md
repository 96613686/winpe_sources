# MONITOR_MGR::_OpenPersistencyRegistry(ulong,void * *)

- ea: `0x1402fadd0`
- end: `0x1402fb0ad`
- name: `?_OpenPersistencyRegistry@MONITOR_MGR@@AEBAJKPEAPEAX@Z`
- size: `733`
- prototype: `int(MONITOR_MGR *__hidden this, unsigned int, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14018cb44`
- `0x1402f940c`
- `0x1402f9d40`

## callees

- `0x140045b34`
- `0x1400936a8`
- `0x1400a0bd0`
- `0x1402fadd0`

## import_xrefs

- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1402faeb3`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1402faeb3`
- `ntoskrnl!ObfDereferenceObject` at `0x1402faeff`
- `ntoskrnl!ObfDereferenceObject` at `0x1402faeff`
- `ntoskrnl!ZwClose` at `0x1402fb05b`
- `ntoskrnl!ZwClose` at `0x1402fb05b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1402faeed`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1402faeed`
- `watchdog!WdLogSingleEntry2` at `0x1402faff4`
- `watchdog!WdLogSingleEntry2` at `0x1402fb020`
- `watchdog!WdLogSingleEntry2` at `0x1402fb079`
- `watchdog!WdLogSingleEntry2` at `0x1402faff4`
- `watchdog!WdLogSingleEntry2` at `0x1402fb020`
- `watchdog!WdLogSingleEntry2` at `0x1402fb079`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402fafa0`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402fafa0`
- `watchdog!WdLogSingleEntry0` at `0x1402fae19`
- `watchdog!WdLogSingleEntry0` at `0x1402fae37`
- `watchdog!WdLogSingleEntry0` at `0x1402fae63`
- `watchdog!WdLogSingleEntry0` at `0x1402fae8e`
- `watchdog!WdLogSingleEntry0` at `0x1402faeca`
- `watchdog!WdLogSingleEntry0` at `0x1402faf1f`
- `watchdog!WdLogSingleEntry0` at `0x1402fb041`
- `watchdog!WdLogSingleEntry0` at `0x1402fae19`
- `watchdog!WdLogSingleEntry0` at `0x1402fae37`
- `watchdog!WdLogSingleEntry0` at `0x1402fae63`
- `watchdog!WdLogSingleEntry0` at `0x1402fae8e`
- `watchdog!WdLogSingleEntry0` at `0x1402faeca`
- `watchdog!WdLogSingleEntry0` at `0x1402faf1f`
- `watchdog!WdLogSingleEntry0` at `0x1402fb041`

## pseudocode

```c

```
