# Pku2uCheckTokenMembership(void *,ulong,int *)

- ea: `0x180015fa0`
- end: `0x18001609e`
- name: `?Pku2uCheckTokenMembership@@YAJPEAXKPEAH@Z`
- size: `254`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, DWORD nSubAuthority0, PBOOL IsMember)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020238`

## callees

- `0x180015fa0`
- `0x1800210f0`
- `0x180023ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001600e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001602d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001600e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001602d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016070`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180016070`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180016004`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180016004`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016023`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180016023`

## pseudocode

```c
__int64 __fastcall Pku2uCheckTokenMembership(HANDLE TokenHandle, DWORD nSubAuthority0, PBOOL IsMember)
{
  DWORD LastError; // ebx
  PSID SidToCheck; // [rsp+60h] [rbp-38h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-30h] BYREF

  LastError = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *IsMember = 0;
  SidToCheck = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, nSubAuthority0, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership(TokenHandle, SidToCheck, IsMember) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_145765ada38d35d83bd68130d412160b_Traceguids, LastError);
    }
  }
  else
  {
    LastError = GetLastError();
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( (int)LastError > 0 )
    return (unsigned __int16)LastError | 0xC0070000;
  else
    return LastError;
}

```

## disassembly

```asm
0x180015fa0  push    rbx
0x180015fa2  push    rsi
0x180015fa3  push    rdi
0x180015fa4  sub     rsp, 80h
0x180015fab  mov     rax, cs:__security_cookie
0x180015fb2  xor     rax, rsp
0x180015fb5  mov     [rsp+98h+var_28], rax
0x180015fba  xor     ebx, ebx
0x180015fbc  mov     word ptr [rsp+98h+pIdentifierAuthority.Value+4], 500h
0x180015fc3  lea     rax, [rsp+98h+SidToCheck]
0x180015fc8  mov     [r8], ebx
0x180015fcb  mov     [rsp+98h+pSid], rax; pSid
0x180015fd0  mov     rdi, r8
0x180015fd3  mov     [rsp+98h+nSubAuthority7], ebx; nSubAuthority7
0x180015fd7  mov     rsi, rcx
0x180015fda  mov     [rsp+98h+nSubAuthority6], ebx; nSubAuthority6
0x180015fde  lea     rcx, [rsp+98h+pIdentifierAuthority]; pIdentifierAuthority
0x180015fe3  mov     [rsp+98h+nSubAuthority5], ebx; nSubAuthority5
0x180015fe7  mov     r8d, edx; nSubAuthority0
0x180015fea  mov     [rsp+98h+nSubAuthority4], ebx; nSubAuthority4
0x180015fee  xor     r9d, r9d; nSubAuthority1
0x180015ff1  mov     [rsp+98h+nSubAuthority3], ebx; nSubAuthority3
0x180015ff5  mov     dl, 1; nSubAuthorityCount
0x180015ff7  mov     [rsp+98h+nSubAuthority2], ebx; nSubAuthority2
0x180015ffb  mov     [rsp+98h+SidToCheck], rbx
0x180016000  mov     dword ptr [rsp+98h+pIdentifierAuthority.Value], ebx
0x180016004  call    cs:__imp_AllocateAndInitializeSid
0x18001600a  test    eax, eax
0x18001600c  jnz     short loc_180016018
0x18001600e  call    cs:__imp_GetLastError
0x180016014  mov     ebx, eax
0x180016016  jmp     short loc_180016066
0x180016018  mov     rdx, [rsp+98h+SidToCheck]; SidToCheck
0x18001601d  mov     r8, rdi; IsMember
0x180016020  mov     rcx, rsi; TokenHandle
0x180016023  call    cs:__imp_CheckTokenMembership
0x180016029  test    eax, eax
0x18001602b  jnz     short loc_180016066
0x18001602d  call    cs:__imp_GetLastError
0x180016033  mov     ebx, eax
0x180016035  mov     rcx, cs:WPP_GLOBAL_Control
0x18001603c  lea     rax, WPP_GLOBAL_Control
0x180016043  cmp     rcx, rax
0x180016046  jz      short loc_180016066
0x180016048  test    byte ptr [rcx+1Ch], 1
0x18001604c  jz      short loc_180016066
0x18001604e  mov     rcx, [rcx+10h]
0x180016052  lea     r8, WPP_145765ada38d35d83bd68130d412160b_Traceguids
0x180016059  mov     edx, 0Eh
0x18001605e  mov     r9d, ebx
0x180016061  call    WPP_SF_d
0x180016066  mov     rcx, [rsp+98h+SidToCheck]; pSid
0x18001606b  test    rcx, rcx
0x18001606e  jz      short loc_180016076
0x180016070  call    cs:__imp_FreeSid
0x180016076  test    ebx, ebx
0x180016078  jg      short loc_18001607E
0x18001607a  mov     eax, ebx
0x18001607c  jmp     short loc_180016086
0x18001607e  movzx   eax, bx
0x180016081  or      eax, 0C0070000h
0x180016086  mov     rcx, [rsp+98h+var_28]
0x18001608b  xor     rcx, rsp; StackCookie
0x18001608e  call    __security_check_cookie
0x180016093  add     rsp, 80h
0x18001609a  pop     rdi
0x18001609b  pop     rsi
0x18001609c  pop     rbx
0x18001609d  retn
```
