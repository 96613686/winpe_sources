# SocketBrokerTable::HandleWnsNotifications(_WNS_CONNECTIVITY_STATUS *)

- ea: `0x180001f38`
- end: `0x180001fd9`
- name: `?HandleWnsNotifications@SocketBrokerTable@@QEAAXPEAU_WNS_CONNECTIVITY_STATUS@@@Z`
- size: `161`
- prototype: `void __fastcall(SocketBrokerTable *__hidden this, struct _WNS_CONNECTIVITY_STATUS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f00`

## callees

- `0x180001f38`
- `0x180001fe0`
- `0x180002050`

## import_xrefs

- `ntdll!RtlInitEnumerationHashTable` at `0x180001f99`
- `ntdll!RtlInitEnumerationHashTable` at `0x180001f99`
- `ntdll!RtlEndEnumerationHashTable` at `0x180001fba`
- `ntdll!RtlEndEnumerationHashTable` at `0x180001fba`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180001fa7`
- `ntdll!RtlEnumerateEntryHashTable` at `0x180001fa7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001f68`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001f77`

## pseudocode

```c

```
