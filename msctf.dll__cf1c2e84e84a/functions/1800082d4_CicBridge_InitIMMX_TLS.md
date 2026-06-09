# CicBridge::InitIMMX(TLS *)

- ea: `0x1800082d4`
- end: `0x180008581`
- name: `?InitIMMX@CicBridge@@QEAAJPEAVTLS@@@Z`
- size: `685`
- prototype: `__int64 __fastcall(CicBridge *__hidden this, struct TLS *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180016b24`

## callees

- `0x1800082d4`
- `0x180008588`
- `0x18000865c`
- `0x1800087b0`
- `0x180009c60`
- `0x18001cc80`
- `0x1800831b8`
- `0x18008a980`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000832d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000832d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800083b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800084f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800083b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800084f3`
- `IMM32!CtfImmGetTMAEFlags` at `0x1800084d2`
- `IMM32!CtfImmGetTMAEFlags` at `0x1800084d2`

## string_xrefs

- `0x1800084a6`: `CicBridge::InitIMMX. CThreadMgrEventSink_DIMCallBack==NULL`
- `0x180008547`: `CicBridge::InitIMMX. TF_CreateThreadMgr==NULL`
- `0x180008569`: `CicBridge::InitIMMX. IID_ITfThreadMgr_P==NULL`

## pseudocode

```c

```
