# FIsUserGroupMember

- ea: `0x180004564`
- end: `0x180004628`
- name: `FIsUserGroupMember`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800044c8`

## callees

- `0x180004564`
- `0x180004e1c`
- `0x1800054b0`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x1800045c5`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800045c5`
- `ADVAPI32!FreeSid` at `0x180004602`
- `ADVAPI32!FreeSid` at `0x180004602`
- `ADVAPI32!CheckTokenMembership` at `0x1800045d9`
- `ADVAPI32!CheckTokenMembership` at `0x1800045d9`
- `KERNEL32!GetLastError` at `0x1800045e3`
- `KERNEL32!GetLastError` at `0x1800045e3`

## string_xrefs

- `0x1800045e9`: `CheckTokenMemberShip for admins failed. Error = %#x`

## pseudocode

```c
_BOOL8 FIsUserGroupMember()
{
  DWORD LastError; // eax
  __int64 v1; // r9
  BOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      LastError = GetLastError();
      MyDbgPrintfW(0xFFFFFFFFLL, L"CheckTokenMemberShip for admins failed. Error = %#x", LastError, v1);
      IsMember = 0;
    }
    FreeSid(SidToCheck);
  }
  return IsMember;
}

```

## disassembly

```asm
0x180004564  mov     [rsp-8+arg_0], rbx
0x180004569  push    rbp
0x18000456a  mov     rbp, rsp
0x18000456d  sub     rsp, 80h
0x180004574  mov     rax, cs:__security_cookie
0x18000457b  xor     rax, rsp
0x18000457e  mov     [rbp+var_8], rax
0x180004582  xor     ebx, ebx
0x180004584  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18000458a  lea     rax, [rbp+SidToCheck]
0x18000458e  mov     [rbp+SidToCheck], rbx
0x180004592  mov     [rsp+80h+pSid], rax; pSid
0x180004597  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18000459b  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x18000459f  mov     r9d, 220h; nSubAuthority1
0x1800045a5  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x1800045a9  lea     r8d, [rbx+20h]; nSubAuthority0
0x1800045ad  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x1800045b1  mov     dl, 2; nSubAuthorityCount
0x1800045b3  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x1800045b7  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x1800045bb  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x1800045bf  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x1800045c2  mov     [rbp+IsMember], ebx
0x1800045c5  call    cs:__imp_AllocateAndInitializeSid
0x1800045cb  test    eax, eax
0x1800045cd  jz      short loc_180004608
0x1800045cf  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800045d3  lea     r8, [rbp+IsMember]; IsMember
0x1800045d7  xor     ecx, ecx; TokenHandle
0x1800045d9  call    cs:__imp_CheckTokenMembership
0x1800045df  test    eax, eax
0x1800045e1  jnz     short loc_1800045FE
0x1800045e3  call    cs:__imp_GetLastError
0x1800045e9  lea     rdx, aChecktokenmemb_0; "CheckTokenMemberShip for admins failed."...
0x1800045f0  or      ecx, 0FFFFFFFFh
0x1800045f3  mov     r8d, eax
0x1800045f6  call    MyDbgPrintfW
0x1800045fb  mov     [rbp+IsMember], ebx
0x1800045fe  mov     rcx, [rbp+SidToCheck]; pSid
0x180004602  call    cs:__imp_FreeSid
0x180004608  mov     eax, [rbp+IsMember]
0x18000460b  mov     rcx, [rbp+var_8]
0x18000460f  xor     rcx, rsp; StackCookie
0x180004612  call    __security_check_cookie
0x180004617  mov     rbx, [rsp+80h+arg_0]
0x18000461f  add     rsp, 80h
0x180004626  pop     rbp
0x180004627  retn
```
