# NtTerminateProcess_0

- ea: `0x180002b10`
- end: `0x180002b16`
- name: `NtTerminateProcess_0`
- size: `6`
- prototype: `NTSTATUS __stdcall(HANDLE ProcessHandle, NTSTATUS ExitStatus)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800028e0`

## import_xrefs

- `ntdll!NtTerminateProcess` at `0x180002b10`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtTerminateProcess_0(HANDLE ProcessHandle, NTSTATUS ExitStatus)
{
  return NtTerminateProcess(ProcessHandle, ExitStatus);
}

```

## disassembly

```asm
0x180002b10  jmp     cs:__imp_NtTerminateProcess
```
