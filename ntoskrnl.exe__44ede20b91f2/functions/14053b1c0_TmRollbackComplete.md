# TmRollbackComplete

- ea: `0x14053b1c0`
- end: `0x14053b1c7`
- name: `TmRollbackComplete`
- size: `7`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1408b1150`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!TmRollbackComplete` at `0x14053b1c0`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall TmRollbackComplete(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  return TmRollbackComplete_0(Enlistment, TmVirtualClock);
}

```

## disassembly

```asm
0x14053b1c0  jmp     cs:TmRollbackComplete_0
```
