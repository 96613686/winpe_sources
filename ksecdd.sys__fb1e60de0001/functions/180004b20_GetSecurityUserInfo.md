# GetSecurityUserInfo

- ea: `0x180004b20`
- end: `0x180004b2f`
- name: `GetSecurityUserInfo`
- size: `15`
- prototype: `NTSTATUS __stdcall(PLUID LogonId, ULONG Flags, PSecurityUserData *UserInformation)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001f0c4`

## pseudocode

```c
NTSTATUS __stdcall GetSecurityUserInfo(PLUID LogonId, ULONG Flags, PSecurityUserData *UserInformation)
{
  return SecpGetUserInfo(LogonId, Flags, UserInformation);
}

```

## disassembly

```asm
0x180004b20  sub     rsp, 28h
0x180004b24  call    SecpGetUserInfo
0x180004b29  add     rsp, 28h
0x180004b2d  retn
```
