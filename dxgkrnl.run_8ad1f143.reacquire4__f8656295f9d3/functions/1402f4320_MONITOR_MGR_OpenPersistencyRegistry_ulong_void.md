# MONITOR_MGR::_OpenPersistencyRegistry(ulong,void * *)

- ea: `0x1402f4320`
- end: `0x1402f45fd`
- name: `?_OpenPersistencyRegistry@MONITOR_MGR@@AEBAJKPEAPEAX@Z`
- size: `733`
- prototype: `int(MONITOR_MGR *__hidden this, unsigned int, void **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140188b44`
- `0x1402f295c`
- `0x1402f3290`

## callees

- `0x1400458d4`
- `0x140092bd8`
- `0x1400a0100`
- `0x1402f4320`

## import_xrefs

- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1402f4403`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1402f4403`
- `ntoskrnl!ObfDereferenceObject` at `0x1402f444f`
- `ntoskrnl!ObfDereferenceObject` at `0x1402f444f`
- `ntoskrnl!ZwClose` at `0x1402f45ab`
- `ntoskrnl!ZwClose` at `0x1402f45ab`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1402f443d`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1402f443d`
- `watchdog!WdLogSingleEntry2` at `0x1402f4544`
- `watchdog!WdLogSingleEntry2` at `0x1402f4570`
- `watchdog!WdLogSingleEntry2` at `0x1402f45c9`
- `watchdog!WdLogSingleEntry2` at `0x1402f4544`
- `watchdog!WdLogSingleEntry2` at `0x1402f4570`
- `watchdog!WdLogSingleEntry2` at `0x1402f45c9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402f44f0`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1402f44f0`
- `watchdog!WdLogSingleEntry0` at `0x1402f4369`
- `watchdog!WdLogSingleEntry0` at `0x1402f4387`
- `watchdog!WdLogSingleEntry0` at `0x1402f43b3`
- `watchdog!WdLogSingleEntry0` at `0x1402f43de`
- `watchdog!WdLogSingleEntry0` at `0x1402f441a`
- `watchdog!WdLogSingleEntry0` at `0x1402f446f`
- `watchdog!WdLogSingleEntry0` at `0x1402f4591`
- `watchdog!WdLogSingleEntry0` at `0x1402f4369`
- `watchdog!WdLogSingleEntry0` at `0x1402f4387`
- `watchdog!WdLogSingleEntry0` at `0x1402f43b3`
- `watchdog!WdLogSingleEntry0` at `0x1402f43de`
- `watchdog!WdLogSingleEntry0` at `0x1402f441a`
- `watchdog!WdLogSingleEntry0` at `0x1402f446f`
- `watchdog!WdLogSingleEntry0` at `0x1402f4591`

## pseudocode

```c

```
