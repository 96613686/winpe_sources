# RDVIsInWellKnownGroup

- ea: `0x18001ce90`
- end: `0x18001cfe0`
- name: `RDVIsInWellKnownGroup`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b9d0`

## callees

- `0x18001ce90`
- `0x18004e850`
- `0x180097f64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf93`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001cf0e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001cf0e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cef1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001cef1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001cf22`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001cf22`

## pseudocode

```c
bool RDVIsInWellKnownGroup()
{
  DWORD v1; // eax
  __int64 v2; // r8
  DWORD LastError; // eax
  __int64 v4; // r8
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x241u, 0, 0, 0, 0, 0, 0, &SidToCheck);
  if ( IsMember )
  {
    if ( !CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      IsMember = 0;
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v4, LastError);
      }
    }
    FreeSid(SidToCheck);
  }
  else
  {
    v1 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v2, v1);
    }
  }
  return IsMember != 0;
}

```

## disassembly

```asm
0x18001ce90  mov     [rsp-8+arg_0], rbx
0x18001ce95  push    rbp
0x18001ce96  mov     rbp, rsp
0x18001ce99  sub     rsp, 80h
0x18001cea0  mov     rax, cs:__security_cookie
0x18001cea7  xor     rax, rsp
0x18001ceaa  mov     [rbp+var_8], rax
0x18001ceae  xor     ebx, ebx
0x18001ceb0  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18001ceb6  lea     rax, [rbp+SidToCheck]
0x18001ceba  mov     [rbp+IsMember], ebx
0x18001cebd  mov     [rsp+80h+pSid], rax; pSid
0x18001cec2  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18001cec6  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x18001ceca  mov     r9d, 241h; nSubAuthority1
0x18001ced0  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x18001ced4  lea     r8d, [rbx+20h]; nSubAuthority0
0x18001ced8  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x18001cedc  mov     dl, 2; nSubAuthorityCount
0x18001cede  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x18001cee2  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x18001cee6  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x18001ceea  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x18001ceed  mov     [rbp+SidToCheck], rbx
0x18001cef1  call    cs:__imp_AllocateAndInitializeSid
0x18001cef8  nop     dword ptr [rax+rax+00h]
0x18001cefd  mov     [rbp+IsMember], eax
0x18001cf00  test    eax, eax
0x18001cf02  jz      short loc_18001CF52
0x18001cf04  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18001cf08  lea     r8, [rbp+IsMember]; IsMember
0x18001cf0c  xor     ecx, ecx; TokenHandle
0x18001cf0e  call    cs:__imp_CheckTokenMembership
0x18001cf15  nop     dword ptr [rax+rax+00h]
0x18001cf1a  test    eax, eax
0x18001cf1c  jz      short loc_18001CF90
0x18001cf1e  mov     rcx, [rbp+SidToCheck]; pSid
0x18001cf22  call    cs:__imp_FreeSid
0x18001cf29  nop     dword ptr [rax+rax+00h]
0x18001cf2e  cmp     [rbp+IsMember], ebx
0x18001cf31  setnz   al
0x18001cf34  mov     rcx, [rbp+var_8]
0x18001cf38  xor     rcx, rsp; StackCookie
0x18001cf3b  call    __security_check_cookie
0x18001cf40  mov     rbx, [rsp+80h+arg_0]
0x18001cf48  add     rsp, 80h
0x18001cf4f  pop     rbp
0x18001cf50  retn
0x18001cf52  call    cs:__imp_GetLastError
0x18001cf59  nop     dword ptr [rax+rax+00h]
0x18001cf5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf65  lea     rdx, WPP_GLOBAL_Control
0x18001cf6c  cmp     rcx, rdx
0x18001cf6f  jz      short loc_18001CF2E
0x18001cf71  test    byte ptr [rcx+1Ch], 1
0x18001cf75  jz      short loc_18001CF2E
0x18001cf77  cmp     byte ptr [rcx+19h], 2
0x18001cf7b  jb      short loc_18001CF2E
0x18001cf7d  mov     rcx, [rcx+10h]
0x18001cf81  mov     edx, 0Bh
0x18001cf86  mov     r9d, eax
0x18001cf89  call    WPP_SF_Dd
0x18001cf8e  jmp     short loc_18001CF2E
0x18001cf90  mov     [rbp+IsMember], ebx
0x18001cf93  call    cs:__imp_GetLastError
0x18001cf9a  nop     dword ptr [rax+rax+00h]
0x18001cf9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfa6  lea     rdx, WPP_GLOBAL_Control
0x18001cfad  cmp     rcx, rdx
0x18001cfb0  jz      loc_18001CF1E
0x18001cfb6  test    byte ptr [rcx+1Ch], 1
0x18001cfba  jz      loc_18001CF1E
0x18001cfc0  cmp     byte ptr [rcx+19h], 2
0x18001cfc4  jb      loc_18001CF1E
0x18001cfca  mov     rcx, [rcx+10h]
0x18001cfce  mov     edx, 0Ah
0x18001cfd3  mov     r9d, eax
0x18001cfd6  call    WPP_SF_Dd
0x18001cfdb  jmp     loc_18001CF1E
```
