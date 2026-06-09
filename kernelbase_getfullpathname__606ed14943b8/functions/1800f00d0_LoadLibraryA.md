# LoadLibraryA

- ea: `0x1800f00d0`
- end: `0x1800f01a9`
- name: `LoadLibraryA`
- size: `217`
- prototype: `HMODULE __stdcall(LPCSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800f00d0`

## callees

- `0x18004b9d0`
- `0x18004cc30`
- `0x1800f00d0`
- `0x18010acd0`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800f015e`
- `ntdll!RtlFreeUnicodeString` at `0x1800f015e`
- `ntdll!RtlSetLastWin32Error` at `0x1800f0197`
- `ntdll!RtlSetLastWin32Error` at `0x1800f0197`
- `ntdll!RtlInitAnsiStringEx` at `0x1800f011a`
- `ntdll!RtlInitAnsiStringEx` at `0x1800f011a`
- `ntdll!RtlFreeHeap` at `0x1801a16a1`
- `ntdll!RtlFreeHeap` at `0x1801a16c7`
- `ntdll!RtlFreeHeap` at `0x1801a16a1`
- `ntdll!RtlFreeHeap` at `0x1801a16c7`
- `ntdll!_stricmp` at `0x1800f00ee`
- `ntdll!_stricmp` at `0x1800f00ee`
- `ntdll!strncat_s` at `0x1801a1673`
- `ntdll!strncat_s` at `0x1801a1673`
- `ntdll!RtlAllocateHeap` at `0x1801a1635`
- `ntdll!RtlAllocateHeap` at `0x1801a1635`

## string_xrefs

- `0x1800f00e7`: `twain_32.dll`
- `0x1801a1667`: `\twain_32.dll`

## pseudocode

```c

```
