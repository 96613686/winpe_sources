# CheckAndCreateSubFolders(ushort const *)

- ea: `0x18001fdd0`
- end: `0x180020051`
- name: `?CheckAndCreateSubFolders@@YAKPEBG@Z`
- size: `641`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f580`
- `0x1800b3bd0`

## callees

- `0x18000a504`
- `0x18001fdd0`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff1c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fe44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fe44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fede`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ff11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ff3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fede`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ff11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ff3b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001fef0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18001fef0`

## string_xrefs

- `0x18001ff8a`: `CheckAndCreateSubFolders: failed to CopySubString for path %s with error: %d.`
- `0x180020023`: `CheckAndCreateSubFolders: failed to CopySubString for path %s with error: %d.`
- `0x18001ffd2`: `CheckAndCreateSubFolders: failed to CreateDirectory for path %s with error: %d.`
- `0x18001fffc`: `CheckAndCreateSubFolders: failed to CreateDirectory for path %s with error: %d.`

## pseudocode

```c

```
