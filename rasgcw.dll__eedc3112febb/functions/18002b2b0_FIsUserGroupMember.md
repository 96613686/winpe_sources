# FIsUserGroupMember

- ea: `0x18002b2b0`
- end: `0x18002b374`
- name: `FIsUserGroupMember`
- size: `196`
- prototype: `__int64 __fastcall(DWORD nSubAuthority1)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011bc0`
- `0x18002b204`

## callees

- `0x18002b2b0`
- `0x18002f3b0`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x18002b341`
- `rtutils!TracePrintfExA` at `0x18002b341`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b34e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002b34e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b30e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002b30e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002b322`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002b322`

## string_xrefs

- `0x18002b337`: `CheckTokenMemberShip for admins failed.`

## pseudocode

```c
__int64 __fastcall FIsUserGroupMember(DWORD nSubAuthority1)
{
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, nSubAuthority1, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "CheckTokenMemberShip for admins failed.");
      IsMember = 0;
    }
    FreeSid(SidToCheck);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x18002b2b0  mov     [rsp-8+arg_8], rbx
0x18002b2b5  push    rbp
0x18002b2b6  mov     rbp, rsp
0x18002b2b9  sub     rsp, 80h
0x18002b2c0  mov     rax, cs:__security_cookie
0x18002b2c7  xor     rax, rsp
0x18002b2ca  mov     [rbp+var_8], rax
0x18002b2ce  xor     ebx, ebx
0x18002b2d0  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18002b2d6  lea     rax, [rbp+SidToCheck]
0x18002b2da  mov     [rbp+SidToCheck], rbx
0x18002b2de  mov     [rsp+80h+pSid], rax; pSid
0x18002b2e3  mov     r9d, ecx; nSubAuthority1
0x18002b2e6  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x18002b2ea  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18002b2ee  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x18002b2f2  lea     r8d, [rbx+20h]; nSubAuthority0
0x18002b2f6  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x18002b2fa  mov     dl, 2; nSubAuthorityCount
0x18002b2fc  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x18002b300  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x18002b304  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x18002b308  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x18002b30b  mov     [rbp+IsMember], ebx
0x18002b30e  call    cs:__imp_AllocateAndInitializeSid
0x18002b314  test    eax, eax
0x18002b316  jz      short loc_18002B354
0x18002b318  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18002b31c  lea     r8, [rbp+IsMember]; IsMember
0x18002b320  xor     ecx, ecx; TokenHandle
0x18002b322  call    cs:__imp_CheckTokenMembership
0x18002b328  test    eax, eax
0x18002b32a  jnz     short loc_18002B34A
0x18002b32c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18002b332  cmp     ecx, 0FFFFFFFFh
0x18002b335  jz      short loc_18002B347
0x18002b337  lea     r8, aChecktokenmemb_1; "CheckTokenMemberShip for admins failed."
0x18002b33e  lea     edx, [rbx+0Ch]; dwFlags
0x18002b341  call    cs:__imp_TracePrintfExA
0x18002b347  mov     [rbp+IsMember], ebx
0x18002b34a  mov     rcx, [rbp+SidToCheck]; pSid
0x18002b34e  call    cs:__imp_FreeSid
0x18002b354  mov     eax, [rbp+IsMember]
0x18002b357  mov     rcx, [rbp+var_8]
0x18002b35b  xor     rcx, rsp; StackCookie
0x18002b35e  call    __security_check_cookie
0x18002b363  mov     rbx, [rsp+80h+arg_8]
0x18002b36b  add     rsp, 80h
0x18002b372  pop     rbp
0x18002b373  retn
```
