# _LUAIsTokenAdmin(void *)

- ea: `0x1800bca54`
- end: `0x1800bcaef`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `155`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bcbe0`
- `0x1800bccf0`

## callees

- `0x180003470`
- `0x1800bca54`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bcacd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bcacd`
- `ADVAPI32!DuplicateToken` at `0x1800bca88`
- `ADVAPI32!DuplicateToken` at `0x1800bca88`
- `ADVAPI32!CreateWellKnownSid` at `0x1800bcaa9`
- `ADVAPI32!CreateWellKnownSid` at `0x1800bcaa9`
- `ADVAPI32!CheckTokenMembership` at `0x1800bcac2`
- `ADVAPI32!CheckTokenMembership` at `0x1800bcac2`

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
      CheckTokenMembership(DuplicateTokenHandle, pSid, &IsMember);
    CloseHandle(DuplicateTokenHandle);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x1800bca54  sub     rsp, 98h
0x1800bca5b  mov     rax, cs:__security_cookie
0x1800bca62  xor     rax, rsp
0x1800bca65  mov     [rsp+98h+var_18], rax
0x1800bca6d  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800bca72  mov     [rsp+98h+IsMember], 0
0x1800bca7a  mov     edx, 1; ImpersonationLevel
0x1800bca7f  mov     [rsp+98h+DuplicateTokenHandle], 0
0x1800bca88  call    cs:__imp_DuplicateToken
0x1800bca8e  test    eax, eax
0x1800bca90  jz      short loc_1800BCAD3
0x1800bca92  xor     edx, edx; DomainSid
0x1800bca94  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800bca9c  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800bcaa1  lea     r8, [rsp+98h+pSid]; pSid
0x1800bcaa6  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800bcaa9  call    cs:__imp_CreateWellKnownSid
0x1800bcaaf  test    eax, eax
0x1800bcab1  jz      short loc_1800BCAC8
0x1800bcab3  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x1800bcab8  lea     r8, [rsp+98h+IsMember]; IsMember
0x1800bcabd  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x1800bcac2  call    cs:__imp_CheckTokenMembership
0x1800bcac8  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x1800bcacd  call    cs:__imp_CloseHandle
0x1800bcad3  mov     eax, [rsp+98h+IsMember]
0x1800bcad7  mov     rcx, [rsp+98h+var_18]
0x1800bcadf  xor     rcx, rsp; StackCookie
0x1800bcae2  call    __security_check_cookie
0x1800bcae7  add     rsp, 98h
0x1800bcaee  retn
```
