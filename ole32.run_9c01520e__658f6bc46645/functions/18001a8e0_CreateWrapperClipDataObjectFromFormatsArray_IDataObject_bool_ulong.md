# CreateWrapperClipDataObjectFromFormatsArray(IDataObject * *,bool,ulong *)

- ea: `0x18001a8e0`
- end: `0x18001aa6e`
- name: `?CreateWrapperClipDataObjectFromFormatsArray@@YAJPEAPEAUIDataObject@@_NPEAK@Z`
- size: `398`
- prototype: `HRESULT __fastcall(IDataObject **ppDataObj, bool isBrokeredCall, unsigned int *pdwClipSequenceNumber)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180009c20`
- `0x18001dfb0`

## callees

- `0x18000a574`
- `0x18001a8e0`
- `0x18001aa74`
- `0x18001ac98`
- `0x18001b084`
- `0x18001c838`
- `0x18001c8c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aa60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001aa60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a9bc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001a9bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa32`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001a9e9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001a9e9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001a967`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18001a967`
- `USER32!IsClipboardFormatAvailable` at `0x18001a931`
- `USER32!IsClipboardFormatAvailable` at `0x18001a931`
- `USER32!GetClipboardData` at `0x18001a94c`
- `USER32!GetClipboardData` at `0x18001a94c`
- `USER32!GetClipboardSequenceNumber` at `0x18001a8fa`
- `USER32!GetClipboardSequenceNumber` at `0x18001a8fa`

## pseudocode

```c

```
