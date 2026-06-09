# GetIStreamFromData(void const *,ulong,IStream * *)

- ea: `0x18020c124`
- end: `0x18020c2cb`
- name: `?GetIStreamFromData@@YAJPEBXKPEAPEAUIStream@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(const void *Src, size_t Size, struct IStream **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18020c504`

## callees

- `0x180010cc0`
- `0x18009cf78`
- `0x1800a9014`
- `0x1800e7a70`
- `0x1800eb920`
- `0x18020c124`
- `0x1802cf7cc`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18020c24a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18020c24a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18020c278`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18020c278`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalAlloc` at `0x18020c1a8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalAlloc` at `0x18020c1a8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18020c1d9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18020c1d9`

## string_xrefs

- `0x18020c162`: `onecore\base\cbs\sandbox\lib\sandboxcommunication.cpp`
- `0x18020c1c1`: `onecore\base\cbs\sandbox\lib\sandboxcommunication.cpp`
- `0x18020c1ef`: `onecore\base\cbs\sandbox\lib\sandboxcommunication.cpp`
- `0x18020c261`: `onecore\base\cbs\sandbox\lib\sandboxcommunication.cpp`

## pseudocode

```c

```
