# TmPrepareComplete

- ea: `0x14053b060`
- end: `0x14053b067`
- name: `TmPrepareComplete`
- size: `7`
- prototype: `NTSTATUS __stdcall(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1408b1150`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!TmPrepareComplete` at `0x14053b060`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall TmPrepareComplete(PKENLISTMENT Enlistment, PLARGE_INTEGER TmVirtualClock)
{
  return TmPrepareComplete_0(Enlistment, TmVirtualClock);
}

```

## disassembly

```asm
0x14053b060  jmp     cs:TmPrepareComplete_0
```
