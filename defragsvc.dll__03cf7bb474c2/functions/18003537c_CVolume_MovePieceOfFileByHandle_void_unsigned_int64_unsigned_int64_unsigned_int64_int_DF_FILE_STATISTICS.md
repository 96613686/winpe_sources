# CVolume::_MovePieceOfFileByHandle(void *,unsigned __int64,unsigned __int64,unsigned __int64,int,_DF_FILE_STATISTICS *)

- ea: `0x18003537c`
- end: `0x180035803`
- name: `?_MovePieceOfFileByHandle@CVolume@@IEAAJPEAX_K11HPEAU_DF_FILE_STATISTICS@@@Z`
- size: `1159`
- prototype: `__int64 __fastcall(CVolume *this, void *, __int64, __int64, unsigned __int64, int, struct _DF_FILE_STATISTICS *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180035210`
- `0x180064250`

## callees

- `0x180002b9c`
- `0x180006400`
- `0x18000ad50`
- `0x18003537c`
- `0x180038c3c`
- `0x180056768`
- `0x180064fbc`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x1800354a0`
- `ntdll!NtFsControlFile` at `0x1800354a0`
- `ntdll!NtWaitForSingleObject` at `0x1800354c3`
- `ntdll!NtWaitForSingleObject` at `0x1800354c3`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003545b`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800354ac`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18003545b`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800354ac`

## string_xrefs

- `0x1800353ac`: `CVolume::_MovePieceOfFileByHandle`

## pseudocode

```c

```
