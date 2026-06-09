# NtPropagationComplete

- ea: `0x14053ac40`
- end: `0x14053ac47`
- name: `NtPropagationComplete`
- size: `7`
- prototype: `NTSTATUS __stdcall(HANDLE ResourceManagerHandle, ULONG RequestCookie, ULONG BufferLength, PVOID Buffer)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtPropagationComplete` at `0x14053ac40`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtPropagationComplete(
        HANDLE ResourceManagerHandle,
        ULONG RequestCookie,
        ULONG BufferLength,
        PVOID Buffer)
{
  return NtPropagationComplete_0(ResourceManagerHandle, RequestCookie, BufferLength, Buffer);
}

```

## disassembly

```asm
0x14053ac40  jmp     cs:NtPropagationComplete_0
```
