# SearchPathA

- ea: `0x1800e96b0`
- end: `0x1800e99ad`
- name: `SearchPathA`
- size: `765`
- prototype: `DWORD __stdcall(LPCSTR lpPath, LPCSTR lpFileName, LPCSTR lpExtension, DWORD nBufferLength, LPSTR lpBuffer, LPSTR *lpFilePart)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180148ad0`

## callees

- `0x18004b9d0`
- `0x180073120`
- `0x1800e96b0`
- `0x1800e9ac0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800e974b`
- `ntdll!RtlFreeUnicodeString` at `0x1800e975b`
- `ntdll!RtlFreeUnicodeString` at `0x1800e9967`
- `ntdll!RtlFreeUnicodeString` at `0x1800e997c`
- `ntdll!RtlFreeUnicodeString` at `0x1800e998c`
- `ntdll!RtlFreeUnicodeString` at `0x1800e974b`
- `ntdll!RtlFreeUnicodeString` at `0x1800e975b`
- `ntdll!RtlFreeUnicodeString` at `0x1800e9967`
- `ntdll!RtlFreeUnicodeString` at `0x1800e997c`
- `ntdll!RtlFreeUnicodeString` at `0x1800e998c`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800e98d6`
- `ntdll!RtlUnicodeToMultiByteN` at `0x1800e98d6`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e9866`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e9895`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e991b`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e9866`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e9895`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x1800e991b`
- `ntdll!RtlFreeHeap` at `0x1800e97e8`
- `ntdll!RtlFreeHeap` at `0x1800e9952`
- `ntdll!RtlFreeHeap` at `0x1800e97e8`
- `ntdll!RtlFreeHeap` at `0x1800e9952`
- `ntdll!RtlAllocateHeap` at `0x1800e9786`
- `ntdll!RtlAllocateHeap` at `0x1800e980e`
- `ntdll!RtlAllocateHeap` at `0x1800e9786`
- `ntdll!RtlAllocateHeap` at `0x1800e980e`

## pseudocode

```c

```
