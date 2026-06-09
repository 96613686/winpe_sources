# CQueueMgr::UpdateMachineProperties(ulong,ulong * const,tagPROPVARIANT * const)

- ea: `0x1800193e8`
- end: `0x1800195a2`
- name: `?UpdateMachineProperties@CQueueMgr@@QEAAXKQEAKQEAUtagPROPVARIANT@@@Z`
- size: `442`
- prototype: `void __fastcall(CQueueMgr *__hidden this, unsigned int, unsigned int *const, struct tagPROPVARIANT *const)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800197e4`
- `0x18003a310`
- `0x18003aa14`

## callees

- `0x180009924`
- `0x18001358c`
- `0x1800193e8`
- `0x18002c61c`
- `0x180048980`
- `0x180060944`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180019582`
- `KERNEL32!LeaveCriticalSection` at `0x180019582`
- `mqsec!GetFalconKeyValue` at `0x18001949e`
- `mqsec!GetFalconKeyValue` at `0x18001949e`
- `mqsec!SetFalconKeyValue` at `0x180019567`
- `mqsec!SetFalconKeyValue` at `0x180019567`

## string_xrefs

- `0x180019508`: `MachineCache\MachineJournalQuota`
- `0x18001953e`: `MachineCache\MachineQuota`
- `0x180019497`: `MachineCache\MachineDeadletterQuota`

## pseudocode

```c

```
