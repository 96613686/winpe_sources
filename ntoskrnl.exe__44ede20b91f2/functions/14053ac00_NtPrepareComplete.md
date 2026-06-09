# NtPrepareComplete

- ea: `0x14053ac00`
- end: `0x14053ac07`
- name: `NtPrepareComplete`
- size: `7`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtPrepareComplete` at `0x14053ac00`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtPrepareComplete(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  return NtPrepareComplete_0(EnlistmentHandle, TmVirtualClock);
}

```

## disassembly

```asm
0x14053ac00  jmp     cs:NtPrepareComplete_0
```
