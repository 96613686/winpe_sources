# MergeSdbpGetHashOfFileAlloc(uchar * *,ulong *,void * *,ushort const *)

- ea: `0x180097498`
- end: `0x1800976be`
- name: `?MergeSdbpGetHashOfFileAlloc@@YAKPEAPEAEPEAKPEAPEAXPEBG@Z`
- size: `550`
- prototype: `unsigned int(unsigned __int8 **, unsigned int *, void **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180097a30`

## callees

- `0x180012920`
- `0x180019c84`
- `0x18004ed20`
- `0x180097498`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800975f3`
- `ntdll!RtlAllocateHeap` at `0x1800975f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009767f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009767f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180097519`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180097519`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18009766c`
- `WINTRUST!CryptCATAdminReleaseContext` at `0x18009766c`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x1800975b3`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x180097619`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x1800975b3`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle2` at `0x180097619`
- `WINTRUST!CryptCATAdminAcquireContext2` at `0x180097575`
- `WINTRUST!CryptCATAdminAcquireContext2` at `0x180097575`

## string_xrefs

- `0x180097536`: `Error opening file: [%d].`

## pseudocode

```c

```
