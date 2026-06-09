# SecLookupAccountSid

- ea: `0x180003660`
- end: `0x180003683`
- name: `SecLookupAccountSid`
- size: `35`
- prototype: `NTSTATUS __stdcall(PSID Sid, PULONG NameSize, PUNICODE_STRING NameBuffer, PULONG DomainSize, PUNICODE_STRING DomainBuffer, PSID_NAME_USE NameUse)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180003e20`

## pseudocode

```c
NTSTATUS __stdcall SecLookupAccountSid(
        PSID Sid,
        PULONG NameSize,
        PUNICODE_STRING NameBuffer,
        PULONG DomainSize,
        PUNICODE_STRING DomainBuffer,
        PSID_NAME_USE NameUse)
{
  return SspipLookupAccountSid((__int64)Sid, NameSize, NameBuffer, DomainSize, DomainBuffer, (__int64)NameUse);
}

```

## disassembly

```asm
0x180003660  sub     rsp, 38h
0x180003664  mov     rax, [rsp+38h+NameUse]
0x180003669  mov     [rsp+38h+var_10], rax
0x18000366e  mov     rax, [rsp+38h+DomainBuffer]
0x180003673  mov     [rsp+38h+var_18], rax
0x180003678  call    SspipLookupAccountSid
0x18000367d  add     rsp, 38h
0x180003681  retn
```
