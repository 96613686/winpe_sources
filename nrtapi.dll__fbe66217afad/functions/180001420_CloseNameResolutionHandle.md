# CloseNameResolutionHandle

- ea: `0x180001420`
- end: `0x180001427`
- name: `CloseNameResolutionHandle`
- size: `7`
- prototype: `NTSTATUS __stdcall(HANDLE Handle)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `ntdll!NtClose` at `0x180001420`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall CloseNameResolutionHandle(HANDLE Handle)
{
  return NtClose(Handle);
}

```

## disassembly

```asm
0x180001420  jmp     cs:__imp_NtClose
```
