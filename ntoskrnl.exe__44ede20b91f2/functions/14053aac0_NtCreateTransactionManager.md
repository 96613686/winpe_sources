# NtCreateTransactionManager

- ea: `0x14053aac0`
- end: `0x14053aac7`
- name: `NtCreateTransactionManager`
- size: `7`
- prototype: `NTSTATUS __stdcall(PHANDLE TmHandle, ACCESS_MASK DesiredAccess, POBJECT_ATTRIBUTES ObjectAttributes, PUNICODE_STRING LogFileName, ULONG CreateOptions, ULONG CommitStrength)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCreateTransactionManager` at `0x14053aac0`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtCreateTransactionManager(
        PHANDLE TmHandle,
        ACCESS_MASK DesiredAccess,
        POBJECT_ATTRIBUTES ObjectAttributes,
        PUNICODE_STRING LogFileName,
        ULONG CreateOptions,
        ULONG CommitStrength)
{
  return NtCreateTransactionManager_0(
           TmHandle,
           DesiredAccess,
           ObjectAttributes,
           LogFileName,
           CreateOptions,
           CommitStrength);
}

```

## disassembly

```asm
0x14053aac0  jmp     cs:NtCreateTransactionManager_0
```
