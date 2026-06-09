# APPLICATION_MANAGER::WaitForMultipleObjectsThread(void *)

- ea: `0x180008f30`
- end: `0x180008f47`
- name: `?WaitForMultipleObjectsThread@APPLICATION_MANAGER@@CAKPEAX@Z`
- size: `23`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180008f40`

## pseudocode

```c
ULONG __fastcall APPLICATION_MANAGER::WaitForMultipleObjectsThread(PVOID Parameter)
{
  return WaitForMultipleObjects(*(_DWORD *)Parameter, *((const HANDLE **)Parameter + 1), 1, *((_DWORD *)Parameter + 4));
}

```

## disassembly

```asm
0x180008f30  mov     r9d, [rcx+10h]
0x180008f34  mov     r8d, 1
0x180008f3a  mov     rdx, [rcx+8]
0x180008f3e  mov     ecx, [rcx]
0x180008f40  jmp     cs:__imp_WaitForMultipleObjects
```
