# NtCommitComplete

- ea: `0x14053aa00`
- end: `0x14053aa07`
- name: `NtCommitComplete`
- size: `7`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCommitComplete` at `0x14053aa00`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtCommitComplete(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  return NtCommitComplete_0(EnlistmentHandle, TmVirtualClock);
}

```

## disassembly

```asm
0x14053aa00  jmp     cs:NtCommitComplete_0
```
