# FIsUserGroupMember

- ea: `0x18001601c`
- end: `0x1800160e6`
- name: `FIsUserGroupMember`
- size: `202`
- prototype: `__int64 __fastcall(DWORD nSubAuthority1)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800160ec`
- `0x180016120`

## callees

- `0x18001601c`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001609c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001609c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001608e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001608e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001607a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001607a`
- `rtutils!TracePrintfExA` at `0x1800160de`
- `rtutils!TracePrintfExA` at `0x1800160de`

## string_xrefs

- `0x1800160d2`: `CheckTokenMemberShip for admins failed.`

## pseudocode

```c
__int64 __fastcall FIsUserGroupMember(DWORD nSubAuthority1)
{
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

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
0x18001601c  mov     [rsp-8+arg_8], rbx
0x180016021  push    rbp
0x180016022  mov     rbp, rsp
0x180016025  sub     rsp, 80h
0x18001602c  mov     rax, cs:__security_cookie
0x180016033  xor     rax, rsp
0x180016036  mov     [rbp+var_8], rax
0x18001603a  xor     ebx, ebx
0x18001603c  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180016042  lea     rax, [rbp+SidToCheck]
0x180016046  mov     [rbp+SidToCheck], rbx
0x18001604a  mov     [rsp+80h+pSid], rax; pSid
0x18001604f  mov     r9d, ecx; nSubAuthority1
0x180016052  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x180016056  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18001605a  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x18001605e  lea     r8d, [rbx+20h]; nSubAuthority0
0x180016062  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x180016066  mov     dl, 2; nSubAuthorityCount
0x180016068  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x18001606c  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x180016070  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x180016074  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x180016077  mov     [rbp+IsMember], ebx
0x18001607a  call    cs:__imp_AllocateAndInitializeSid
0x180016080  test    eax, eax
0x180016082  jz      short loc_1800160A2
0x180016084  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x180016088  lea     r8, [rbp+IsMember]; IsMember
0x18001608c  xor     ecx, ecx; TokenHandle
0x18001608e  call    cs:__imp_CheckTokenMembership
0x180016094  test    eax, eax
0x180016096  jz      short loc_1800160C2
0x180016098  mov     rcx, [rbp+SidToCheck]; pSid
0x18001609c  call    cs:__imp_FreeSid
0x1800160a2  mov     eax, [rbp+IsMember]
0x1800160a5  mov     rcx, [rbp+var_8]
0x1800160a9  xor     rcx, rsp; StackCookie
0x1800160ac  call    __security_check_cookie
0x1800160b1  mov     rbx, [rsp+80h+arg_8]
0x1800160b9  add     rsp, 80h
0x1800160c0  pop     rbp
0x1800160c1  retn
0x1800160c2  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800160c8  cmp     ecx, 0FFFFFFFFh
0x1800160cb  jnz     short loc_1800160D2
0x1800160cd  mov     [rbp+IsMember], ebx
0x1800160d0  jmp     short loc_180016098
0x1800160d2  lea     r8, aChecktokenmemb_0; "CheckTokenMemberShip for admins failed."
0x1800160d9  mov     edx, 0Ch; dwFlags
0x1800160de  call    cs:__imp_TracePrintfExA
0x1800160e4  jmp     short loc_1800160CD
```
