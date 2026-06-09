# FTP_DATA_CHANNEL::SetupPassiveListener(ushort,sockaddr_storage *)

- ea: `0x180040e48`
- end: `0x180041157`
- name: `?SetupPassiveListener@FTP_DATA_CHANNEL@@QEAAJGPEAUsockaddr_storage@@@Z`
- size: `783`
- prototype: `int(FTP_DATA_CHANNEL *__hidden this, unsigned __int16, struct sockaddr_storage *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18003a8f8`

## callees

- `0x180006fc0`
- `0x1800070f8`
- `0x180007578`
- `0x1800076b8`
- `0x180040e48`
- `0x180046ff7`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `WS2_32!GetNameInfoW` at `0x180041038`
- `WS2_32!GetNameInfoW` at `0x180041038`
- `WS2_32!__imp_htons` at `0x180040f5d`
- `WS2_32!__imp_htons` at `0x180040f5d`
- `WS2_32!__imp_ntohs` at `0x180041045`
- `WS2_32!__imp_ntohs` at `0x180041045`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x180040f33`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x180040f33`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800410f2`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x1800410f2`

## pseudocode

```c

```
