# TmRollbackEnlistment

- ea: `0x14053b1e0`
- end: `0x14053b1e7`
- name: `TmRollbackEnlistment`
- size: `7`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1408961d0`
- `0x140a88814`
- `0x140ae4910`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!TmRollbackEnlistment` at `0x14053b1e0`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall TmRollbackEnlistment(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  return TmRollbackEnlistment_0(Enlistment, TmVirtualClock);
}

```

## disassembly

```asm
0x14053b1e0  jmp     cs:TmRollbackEnlistment_0
```
