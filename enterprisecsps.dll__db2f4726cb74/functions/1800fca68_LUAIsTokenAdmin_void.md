# _LUAIsTokenAdmin(void *)

- ea: `0x1800fca68`
- end: `0x1800fcb15`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800fcc64`

## callees

- `0x180008de0`
- `0x180009fa7`
- `0x1800fca68`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fcaec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800fcaec`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800fca9c`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800fca9c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800fcac3`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800fcac3`

## pseudocode

```c
__int64 __fastcall _LUAIsTokenAdmin(void *a1)
{
  WINBOOL IsMember; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid; // [rsp+24h] [rbp-74h] BYREF
  void *DuplicateTokenHandle; // [rsp+28h] [rbp-70h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  IsMember = 0;
  DuplicateTokenHandle = 0;
  if ( DuplicateToken(a1, SecurityIdentification, &DuplicateTokenHandle) )
  {
    cbSid = 68;
    if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
      CheckTokenMembership_0(DuplicateTokenHandle, pSid, &IsMember);
    CloseHandle(DuplicateTokenHandle);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x1800fca68  sub     rsp, 98h
0x1800fca6f  mov     rax, cs:__security_cookie
0x1800fca76  xor     rax, rsp
0x1800fca79  mov     [rsp+98h+var_18], rax
0x1800fca81  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800fca86  mov     [rsp+98h+IsMember], 0
0x1800fca8e  mov     edx, 1; ImpersonationLevel
0x1800fca93  mov     [rsp+98h+DuplicateTokenHandle], 0
0x1800fca9c  call    cs:__imp_DuplicateToken
0x1800fcaa3  nop     dword ptr [rax+rax+00h]
0x1800fcaa8  test    eax, eax
0x1800fcaaa  jz      short loc_1800FCAF8
0x1800fcaac  xor     edx, edx; DomainSid
0x1800fcaae  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800fcab6  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800fcabb  lea     r8, [rsp+98h+pSid]; pSid
0x1800fcac0  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800fcac3  call    cs:__imp_CreateWellKnownSid
0x1800fcaca  nop     dword ptr [rax+rax+00h]
0x1800fcacf  test    eax, eax
0x1800fcad1  jz      short loc_1800FCAE7
0x1800fcad3  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x1800fcad8  lea     r8, [rsp+98h+IsMember]; IsMember
0x1800fcadd  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x1800fcae2  call    CheckTokenMembership_0
0x1800fcae7  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x1800fcaec  call    cs:__imp_CloseHandle
0x1800fcaf3  nop     dword ptr [rax+rax+00h]
0x1800fcaf8  mov     eax, [rsp+98h+IsMember]
0x1800fcafc  mov     rcx, [rsp+98h+var_18]
0x1800fcb04  xor     rcx, rsp; StackCookie
0x1800fcb07  call    __security_check_cookie
0x1800fcb0c  add     rsp, 98h
0x1800fcb13  retn
```
