# TlsExternalAlgorithmLock_Delete

- ea: `0x14000c824`
- end: `0x14000c841`
- name: `TlsExternalAlgorithmLock_Delete`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140021cfc`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14000c82f`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000c82f`

## pseudocode

```c
NTSTATUS TlsExternalAlgorithmLock_Delete()
{
  return ExDeleteResourceLite(&Resource);
}

```

## disassembly

```asm
0x14000c824  sub     rsp, 28h
0x14000c828  lea     rcx, Resource; Resource
0x14000c82f  call    cs:__imp_ExDeleteResourceLite
0x14000c836  nop     dword ptr [rax+rax+00h]
0x14000c83b  add     rsp, 28h
0x14000c83f  retn
```
