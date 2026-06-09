# NtPrePrepareComplete

- ea: `0x14053abc0`
- end: `0x14053abc7`
- name: `NtPrePrepareComplete`
- size: `7`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtPrePrepareComplete` at `0x14053abc0`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtPrePrepareComplete(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  return NtPrePrepareComplete_0(EnlistmentHandle, TmVirtualClock);
}

```

## disassembly

```asm
0x14053abc0  jmp     cs:NtPrePrepareComplete_0
```
