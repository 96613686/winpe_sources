# NtCommitTransaction

- ea: `0x14053aa40`
- end: `0x14053aa47`
- name: `NtCommitTransaction`
- size: `7`
- prototype: `NTSTATUS __stdcall(HANDLE TransactionHandle, BOOLEAN Wait)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ext-ms-win-ntos-tm-l1-1-0!NtCommitTransaction` at `0x14053aa40`

## pseudocode

```c
// attributes: thunk
NTSTATUS __stdcall NtCommitTransaction(HANDLE TransactionHandle, BOOLEAN Wait)
{
  return NtCommitTransaction_0(TransactionHandle, Wait);
}

```

## disassembly

```asm
0x14053aa40  jmp     cs:NtCommitTransaction_0
```
