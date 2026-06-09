# WideCharToMultiByte

- ea: `0x18004e490`
- end: `0x18004fce9`
- name: `WideCharToMultiByte`
- size: `6233`
- prototype: `int __stdcall(UINT CodePage, DWORD dwFlags, LPCWCH lpWideCharStr, int cchWideChar, LPSTR lpMultiByteStr, int cbMultiByte, LPCCH lpDefaultChar, LPBOOL lpUsedDefaultChar)`
- caller_count: `18`
- callee_count: `22`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d820`
- `0x1800300b4`
- `0x180032500`
- `0x1800354e0`
- `0x180036ce0`
- `0x18004101c`
- `0x180078a90`
- `0x18007a3f0`
- `0x180080394`
- `0x1800b7160`
- `0x1800b74a0`
- `0x1800ebcb0`
- `0x1800fbb20`
- `0x180141960`
- `0x180147d10`
- `0x18014ad90`
- `0x18014b160`
- `0x18017e628`

## callees

- `0x18001cd34`
- `0x180020244`
- `0x180020ad0`
- `0x180021e08`
- `0x180024ed0`
- `0x1800285f0`
- `0x180028630`
- `0x1800393f0`
- `0x180048f20`
- `0x18004cc30`
- `0x18004ce20`
- `0x18004e3d0`
- `0x18004e490`
- `0x18004fcf0`
- `0x180050040`
- `0x180050730`
- `0x180050a50`
- `0x18012dfb4`
- `0x180130d10`
- `0x1801369c9`
- `0x180194f10`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004e831`
- `ntdll!RtlInitUnicodeString` at `0x18004f072`
- `ntdll!RtlInitUnicodeString` at `0x18004f114`
- `ntdll!RtlInitUnicodeString` at `0x18004e831`
- `ntdll!RtlInitUnicodeString` at `0x18004f072`
- `ntdll!RtlInitUnicodeString` at `0x18004f114`
- `ntdll!NtOpenKey` at `0x18004e86d`
- `ntdll!NtOpenKey` at `0x18004e86d`
- `ntdll!NtQueryValueKey` at `0x18004f0b2`
- `ntdll!NtQueryValueKey` at `0x18004f0b2`
- `ntdll!RtlUnicodeStringToInteger` at `0x18004f12e`
- `ntdll!RtlUnicodeStringToInteger` at `0x18004f12e`
- `ntdll!NtGetNlsSectionPtr` at `0x18004f34c`
- `ntdll!NtGetNlsSectionPtr` at `0x18004f4ea`
- `ntdll!NtGetNlsSectionPtr` at `0x18004f34c`
- `ntdll!NtGetNlsSectionPtr` at `0x18004f4ea`
- `ntdll!RtlUnicodeToUTF8N` at `0x18004e6e4`
- `ntdll!RtlUnicodeToUTF8N` at `0x18004e6e4`
- `ntdll!NtClose` at `0x18004f043`
- `ntdll!NtClose` at `0x18004f043`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004efd8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004f1dd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004f391`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004f450`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004f694`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004efd8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004f1dd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004f391`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004f450`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18004f694`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f009`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f20d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f369`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f3be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f49d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f507`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f6bf`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f009`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f20d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f369`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f3be`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f49d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f507`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18004f6bf`
- `ntdll!RtlFreeHeap` at `0x18004ea7b`
- `ntdll!RtlFreeHeap` at `0x18004ea7b`
- `ntdll!RtlAllocateHeap` at `0x18004e8b9`
- `ntdll!RtlAllocateHeap` at `0x18004f480`
- `ntdll!RtlAllocateHeap` at `0x18004f5d0`
- `ntdll!RtlAllocateHeap` at `0x18004f708`
- `ntdll!RtlAllocateHeap` at `0x18004e8b9`
- `ntdll!RtlAllocateHeap` at `0x18004f480`
- `ntdll!RtlAllocateHeap` at `0x18004f5d0`
- `ntdll!RtlAllocateHeap` at `0x18004f708`

## string_xrefs

- `0x18004eed7`: `\Registry\Machine\System\CurrentControlSet\Control`
- `0x18004fac1`: `NlsDllCodePageTranslation`
- `0x18004fbd7`: `NlsDllCodePageTranslation`

## pseudocode

```c

```
