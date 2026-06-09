# MapSecurityError

- ea: `0x1800046e0`
- end: `0x1800046f6`
- name: `MapSecurityError`
- size: `22`
- prototype: `NTSTATUS __stdcall(SECURITY_STATUS SecStatus)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!RtlMapSecurityErrorToNtStatus` at `0x1800046e4`
- `ntoskrnl!RtlMapSecurityErrorToNtStatus` at `0x1800046e4`

## pseudocode

```c
NTSTATUS __stdcall MapSecurityError(SECURITY_STATUS SecStatus)
{
  return RtlMapSecurityErrorToNtStatus(SecStatus);
}

```

## disassembly

```asm
0x1800046e0  sub     rsp, 28h
0x1800046e4  call    cs:__imp_RtlMapSecurityErrorToNtStatus
0x1800046eb  nop     dword ptr [rax+rax+00h]
0x1800046f0  add     rsp, 28h
0x1800046f4  retn
```
