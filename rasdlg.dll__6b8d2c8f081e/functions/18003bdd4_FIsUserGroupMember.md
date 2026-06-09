# FIsUserGroupMember

- ea: `0x18003bdd4`
- end: `0x18003be98`
- name: `FIsUserGroupMember`
- size: `196`
- prototype: `__int64 __fastcall(DWORD nSubAuthority1)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003bcf4`
- `0x18003bda0`

## callees

- `0x18003bdd4`
- `0x18004d110`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003be46`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003be46`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003be32`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003be32`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003be72`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003be72`
- `rtutils!TracePrintfExA` at `0x18003be65`
- `rtutils!TracePrintfExA` at `0x18003be65`

## string_xrefs

- `0x18003be5b`: `CheckTokenMemberShip for admins failed.`

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
0x18003bdd4  mov     [rsp-8+arg_8], rbx
0x18003bdd9  push    rbp
0x18003bdda  mov     rbp, rsp
0x18003bddd  sub     rsp, 80h
0x18003bde4  mov     rax, cs:__security_cookie
0x18003bdeb  xor     rax, rsp
0x18003bdee  mov     [rbp+var_8], rax
0x18003bdf2  xor     ebx, ebx
0x18003bdf4  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18003bdfa  lea     rax, [rbp+SidToCheck]
0x18003bdfe  mov     [rbp+SidToCheck], rbx
0x18003be02  mov     [rsp+80h+pSid], rax; pSid
0x18003be07  mov     r9d, ecx; nSubAuthority1
0x18003be0a  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x18003be0e  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18003be12  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x18003be16  lea     r8d, [rbx+20h]; nSubAuthority0
0x18003be1a  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x18003be1e  mov     dl, 2; nSubAuthorityCount
0x18003be20  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x18003be24  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x18003be28  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x18003be2c  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x18003be2f  mov     [rbp+IsMember], ebx
0x18003be32  call    cs:__imp_AllocateAndInitializeSid
0x18003be38  test    eax, eax
0x18003be3a  jz      short loc_18003BE78
0x18003be3c  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18003be40  lea     r8, [rbp+IsMember]; IsMember
0x18003be44  xor     ecx, ecx; TokenHandle
0x18003be46  call    cs:__imp_CheckTokenMembership
0x18003be4c  test    eax, eax
0x18003be4e  jnz     short loc_18003BE6E
0x18003be50  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18003be56  cmp     ecx, 0FFFFFFFFh
0x18003be59  jz      short loc_18003BE6B
0x18003be5b  lea     r8, aChecktokenmemb_0; "CheckTokenMemberShip for admins failed."
0x18003be62  lea     edx, [rbx+0Ch]; dwFlags
0x18003be65  call    cs:__imp_TracePrintfExA
0x18003be6b  mov     [rbp+IsMember], ebx
0x18003be6e  mov     rcx, [rbp+SidToCheck]; pSid
0x18003be72  call    cs:__imp_FreeSid
0x18003be78  mov     eax, [rbp+IsMember]
0x18003be7b  mov     rcx, [rbp+var_8]
0x18003be7f  xor     rcx, rsp; StackCookie
0x18003be82  call    __security_check_cookie
0x18003be87  mov     rbx, [rsp+80h+arg_8]
0x18003be8f  add     rsp, 80h
0x18003be96  pop     rbp
0x18003be97  retn
```
