# NtRollbackComplete

- ea: `0x14053ad80`
- end: `0x14053ad87`
- name: `NtRollbackComplete`
- size: `7`
- prototype: `NTSTATUS __stdcall(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtRollbackComplete` at `0x14053ad80`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtRollbackComplete(HANDLE EnlistmentHandle, PLARGE_INTEGER TmVirtualClock)
{
  return NtRollbackComplete_0(EnlistmentHandle, TmVirtualClock);
}

```

## disassembly

```asm
0x14053ad80  jmp     cs:NtRollbackComplete_0
```
