# TmCommitComplete

- ea: `0x14053ae80`
- end: `0x14053ae87`
- name: `TmCommitComplete`
- size: `7`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1408b1150`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!TmCommitComplete` at `0x14053ae80`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall TmCommitComplete(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  return TmCommitComplete_0(Enlistment, TmVirtualClock);
}

```

## disassembly

```asm
0x14053ae80  jmp     cs:TmCommitComplete_0
```
