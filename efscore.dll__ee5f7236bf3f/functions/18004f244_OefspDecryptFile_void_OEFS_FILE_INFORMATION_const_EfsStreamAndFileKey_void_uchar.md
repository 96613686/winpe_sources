# OefspDecryptFile(void *,OEFS_FILE_INFORMATION const &,EfsStreamAndFileKey &,void *,uchar *)

- ea: `0x18004f244`
- end: `0x18004f4ef`
- name: `?OefspDecryptFile@@YAJPEAXAEBUOEFS_FILE_INFORMATION@@AEAVEfsStreamAndFileKey@@0PEAE@Z`
- size: `683`
- prototype: `__int64 __fastcall(void *, const struct OEFS_FILE_INFORMATION *, struct EfsStreamAndFileKey *, void *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004e17c`
- `0x18004e9e8`

## callees

- `0x18000b12c`
- `0x18000ef20`
- `0x18001b1d0`
- `0x18001dd98`
- `0x18004c054`
- `0x18004cf18`
- `0x18004f244`
- `0x18004fec8`
- `0x1800505ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f3b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f48e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f4c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f3b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f48e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004f4c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f3be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f49c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f4cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f3be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f49c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004f4cf`

## string_xrefs

- `0x18004f2c1`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004f392`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`
- `0x18004f471`: `onecoreuap\ds\security\efs\dll\efsonline.cxx`

## pseudocode

```c

```
