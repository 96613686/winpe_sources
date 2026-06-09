# NtCommitEnlistment

- ea: `0x14053aa20`
- end: `0x14053aa27`
- name: `NtCommitEnlistment`
- size: `7`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCommitEnlistment` at `0x14053aa20`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtCommitEnlistment(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  return NtCommitEnlistment_0(EnlistmentHandle, TmVirtualClock);
}

```

## disassembly

```asm
0x14053aa20  jmp     cs:NtCommitEnlistment_0
```
