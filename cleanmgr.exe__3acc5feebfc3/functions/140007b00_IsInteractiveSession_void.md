# IsInteractiveSession(void)

- ea: `0x140007b00`
- end: `0x140007ba9`
- name: `?IsInteractiveSession@@YAHXZ`
- size: `169`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400080a8`
- `0x140009d34`

## callees

- `0x1400029a0`
- `0x140006574`
- `0x140007b00`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140007b6b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140007b6b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140007b38`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140007b38`

## pseudocode

```c
__int64 IsInteractiveSession(void)
{
  const char *v0; // r9
  const char *v1; // r9
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  IsMember = 0;
  cbSid[0] = 68;
  if ( !CreateWellKnownSid(WinInteractiveSid, 0, pSid, cbSid) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x55,
      (unsigned int)"shell\\applets\\cleanup\\cleanmgr\\cleanmgr.cpp",
      v0);
  if ( !CheckTokenMembership((HANDLE)0xFFFFFFFFFFFFFFFCLL, pSid, &IsMember) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x56,
      (unsigned int)"shell\\applets\\cleanup\\cleanmgr\\cleanmgr.cpp",
      v1);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x140007b00  sub     rsp, 98h
0x140007b07  mov     rax, cs:__security_cookie
0x140007b0e  xor     rax, rsp
0x140007b11  mov     [rsp+98h+var_18], rax
0x140007b19  xor     edx, edx; DomainSid
0x140007b1b  mov     [rsp+98h+IsMember], 0
0x140007b23  lea     r9, [rsp+98h+cbSid]; cbSid
0x140007b28  mov     [rsp+98h+cbSid], 44h ; 'D'
0x140007b30  lea     r8, [rsp+98h+pSid]; pSid
0x140007b35  lea     ecx, [rdx+0Bh]; WellKnownSidType
0x140007b38  call    cs:__imp_CreateWellKnownSid
0x140007b3e  test    eax, eax
0x140007b40  jnz     short loc_140007B5A
0x140007b42  mov     rcx, [rsp+98h]; this
0x140007b4a  lea     r8, aShellAppletsCl; "shell\\applets\\cleanup\\cleanmgr\\clea"...
0x140007b51  lea     edx, [rax+55h]; void *
0x140007b54  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007b5a  lea     r8, [rsp+98h+IsMember]; IsMember
0x140007b5f  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x140007b66  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x140007b6b  call    cs:__imp_CheckTokenMembership
0x140007b71  test    eax, eax
0x140007b73  jnz     short loc_140007B8D
0x140007b75  mov     rcx, [rsp+98h]; this
0x140007b7d  lea     r8, aShellAppletsCl; "shell\\applets\\cleanup\\cleanmgr\\clea"...
0x140007b84  lea     edx, [rax+56h]; void *
0x140007b87  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140007b8d  mov     eax, [rsp+98h+IsMember]
0x140007b91  mov     rcx, [rsp+98h+var_18]
0x140007b99  xor     rcx, rsp; StackCookie
0x140007b9c  call    __security_check_cookie
0x140007ba1  add     rsp, 98h
0x140007ba8  retn
```
