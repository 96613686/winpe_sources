# AddDllToList(_DLL_LIST_ENTRY * *,ushort const *,ushort const *)

- ea: `0x180089c5c`
- end: `0x180089e13`
- name: `?AddDllToList@@YAHPEAPEAU_DLL_LIST_ENTRY@@PEBG1@Z`
- size: `439`
- prototype: `__int64 __fastcall(struct _DLL_LIST_ENTRY **, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180089f80`
- `0x18008b784`
- `0x18008bad8`
- `0x18008c120`

## callees

- `0x180012920`
- `0x180089c5c`
- `0x18008c408`
- `0x1800f1f10`
- `0x1800f1fd0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180089c9e`
- `msvcrt!wcscpy_s` at `0x180089cae`
- `msvcrt!wcscpy_s` at `0x180089dc4`
- `msvcrt!wcscpy_s` at `0x180089dd5`
- `msvcrt!wcscpy_s` at `0x180089c9e`
- `msvcrt!wcscpy_s` at `0x180089cae`
- `msvcrt!wcscpy_s` at `0x180089dc4`
- `msvcrt!wcscpy_s` at `0x180089dd5`
- `msvcrt!_wcsicmp` at `0x180089cd7`
- `msvcrt!_wcsicmp` at `0x180089ceb`
- `msvcrt!_wcsicmp` at `0x180089d06`
- `msvcrt!_wcsicmp` at `0x180089cd7`
- `msvcrt!_wcsicmp` at `0x180089ceb`
- `msvcrt!_wcsicmp` at `0x180089d06`
- `ntdll!RtlAllocateHeap` at `0x180089d7d`
- `ntdll!RtlAllocateHeap` at `0x180089d7d`

## string_xrefs

- `0x180089d8b`: `Failed to allocate memory for DLL list entry`
- `0x180089d98`: `AddDllToList`

## pseudocode

```c

```
