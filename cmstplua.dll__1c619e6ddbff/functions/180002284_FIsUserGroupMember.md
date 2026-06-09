# FIsUserGroupMember

- ea: `0x180002284`
- end: `0x180002348`
- name: `FIsUserGroupMember`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800021e8`

## callees

- `0x180002284`
- `0x180002444`
- `0x1800026e0`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x180002322`
- `ADVAPI32!FreeSid` at `0x180002322`
- `ADVAPI32!CheckTokenMembership` at `0x1800022f9`
- `ADVAPI32!CheckTokenMembership` at `0x1800022f9`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800022e5`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800022e5`
- `KERNEL32!GetLastError` at `0x180002303`
- `KERNEL32!GetLastError` at `0x180002303`

## string_xrefs

- `0x180002309`: `CheckTokenMemberShip for admins failed. Error = %#x`

## pseudocode

```c
_BOOL8 FIsUserGroupMember()
{
  DWORD LastError; // eax
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
      MyDbgPrintfW(0xFFFFFFFFLL, L"CheckTokenMemberShip for admins failed. Error = %#x", LastError);
      IsMember = 0;
    }
    FreeSid(SidToCheck);
  }
  return IsMember;
}

```

## disassembly

```asm
0x180002284  mov     [rsp-8+arg_0], rbx
0x180002289  push    rbp
0x18000228a  mov     rbp, rsp
0x18000228d  sub     rsp, 80h
0x180002294  mov     rax, cs:__security_cookie
0x18000229b  xor     rax, rsp
0x18000229e  mov     [rbp+var_8], rax
0x1800022a2  xor     ebx, ebx
0x1800022a4  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800022aa  lea     rax, [rbp+SidToCheck]
0x1800022ae  mov     [rbp+SidToCheck], rbx
0x1800022b2  mov     [rsp+80h+pSid], rax; pSid
0x1800022b7  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800022bb  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x1800022bf  mov     r9d, 220h; nSubAuthority1
0x1800022c5  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x1800022c9  lea     r8d, [rbx+20h]; nSubAuthority0
0x1800022cd  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x1800022d1  mov     dl, 2; nSubAuthorityCount
0x1800022d3  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x1800022d7  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x1800022db  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x1800022df  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x1800022e2  mov     [rbp+IsMember], ebx
0x1800022e5  call    cs:__imp_AllocateAndInitializeSid
0x1800022eb  test    eax, eax
0x1800022ed  jz      short loc_180002328
0x1800022ef  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800022f3  lea     r8, [rbp+IsMember]; IsMember
0x1800022f7  xor     ecx, ecx; TokenHandle
0x1800022f9  call    cs:__imp_CheckTokenMembership
0x1800022ff  test    eax, eax
0x180002301  jnz     short loc_18000231E
0x180002303  call    cs:__imp_GetLastError
0x180002309  lea     rdx, aChecktokenmemb_0; "CheckTokenMemberShip for admins failed."...
0x180002310  or      ecx, 0FFFFFFFFh
0x180002313  mov     r8d, eax
0x180002316  call    MyDbgPrintfW
0x18000231b  mov     [rbp+IsMember], ebx
0x18000231e  mov     rcx, [rbp+SidToCheck]; pSid
0x180002322  call    cs:__imp_FreeSid
0x180002328  mov     eax, [rbp+IsMember]
0x18000232b  mov     rcx, [rbp+var_8]
0x18000232f  xor     rcx, rsp; StackCookie
0x180002332  call    __security_check_cookie
0x180002337  mov     rbx, [rsp+80h+arg_0]
0x18000233f  add     rsp, 80h
0x180002346  pop     rbp
0x180002347  retn
```
