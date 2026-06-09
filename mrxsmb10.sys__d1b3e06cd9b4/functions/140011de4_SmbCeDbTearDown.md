# SmbCeDbTearDown

- ea: `0x140011de4`
- end: `0x140011e14`
- name: `SmbCeDbTearDown`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140031b98`
- `0x140032a30`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140011def`
- `ntoskrnl!ExDeleteResourceLite` at `0x140011e02`
- `ntoskrnl!ExDeleteResourceLite` at `0x140011def`
- `ntoskrnl!ExDeleteResourceLite` at `0x140011e02`

## pseudocode

```c
NTSTATUS SmbCeDbTearDown()
{
  ExDeleteResourceLite(&s_SmbSecuritySignatureResource);
  return ExDeleteResourceLite(&s_SmbCeDbResource);
}

```

## disassembly

```asm
0x140011de4  sub     rsp, 28h
0x140011de8  lea     rcx, s_SmbSecuritySignatureResource; Resource
0x140011def  call    cs:__imp_ExDeleteResourceLite
0x140011df6  nop     dword ptr [rax+rax+00h]
0x140011dfb  lea     rcx, s_SmbCeDbResource; Resource
0x140011e02  call    cs:__imp_ExDeleteResourceLite
0x140011e09  nop     dword ptr [rax+rax+00h]
0x140011e0e  add     rsp, 28h
0x140011e12  retn
```
