# _LUAIsTokenAdmin(void *)

- ea: `0x14001cdbc`
- end: `0x14001ce57`
- name: `?_LUAIsTokenAdmin@@YAHPEAX@Z`
- size: `155`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001cf8c`

## callees

- `0x14001cdbc`
- `0x14001e050`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ce35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001ce35`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14001cdf0`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x14001cdf0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14001ce2a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14001ce2a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14001ce11`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x14001ce11`

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
0x14001cdbc  sub     rsp, 98h
0x14001cdc3  mov     rax, cs:__security_cookie
0x14001cdca  xor     rax, rsp
0x14001cdcd  mov     [rsp+98h+var_18], rax
0x14001cdd5  lea     r8, [rsp+98h+DuplicateTokenHandle]; DuplicateTokenHandle
0x14001cdda  mov     [rsp+98h+IsMember], 0
0x14001cde2  mov     edx, 1; ImpersonationLevel
0x14001cde7  mov     [rsp+98h+DuplicateTokenHandle], 0
0x14001cdf0  call    cs:__imp_DuplicateToken
0x14001cdf6  test    eax, eax
0x14001cdf8  jz      short loc_14001CE3B
0x14001cdfa  xor     edx, edx; DomainSid
0x14001cdfc  mov     [rsp+98h+cbSid], 44h ; 'D'
0x14001ce04  lea     r9, [rsp+98h+cbSid]; cbSid
0x14001ce09  lea     r8, [rsp+98h+pSid]; pSid
0x14001ce0e  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x14001ce11  call    cs:__imp_CreateWellKnownSid
0x14001ce17  test    eax, eax
0x14001ce19  jz      short loc_14001CE30
0x14001ce1b  mov     rcx, [rsp+98h+DuplicateTokenHandle]; TokenHandle
0x14001ce20  lea     r8, [rsp+98h+IsMember]; IsMember
0x14001ce25  lea     rdx, [rsp+98h+pSid]; SidToCheck
0x14001ce2a  call    cs:__imp_CheckTokenMembership
0x14001ce30  mov     rcx, [rsp+98h+DuplicateTokenHandle]; hObject
0x14001ce35  call    cs:__imp_CloseHandle
0x14001ce3b  mov     eax, [rsp+98h+IsMember]
0x14001ce3f  mov     rcx, [rsp+98h+var_18]
0x14001ce47  xor     rcx, rsp; StackCookie
0x14001ce4a  call    __security_check_cookie
0x14001ce4f  add     rsp, 98h
0x14001ce56  retn
```
