# Pku2uImpersonateToken(void *,void * *,int *)

- ea: `0x180014fe0`
- end: `0x180015181`
- name: `?Pku2uImpersonateToken@@YAJPEAXPEAPEAXPEAH@Z`
- size: `417`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **, int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020238`
- `0x18002a320`
- `0x180035dc0`

## callees

- `0x180014fe0`
- `0x1800210f0`
- `0x180023ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001505e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001505e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001512e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001512e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800150c4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800150c4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180015054`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180015054`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180015077`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180015077`
- `ntdll!NtSetInformationThread` at `0x180015154`
- `ntdll!NtSetInformationThread` at `0x180015154`
- `ntdll!NtOpenThreadToken` at `0x180015109`
- `ntdll!NtOpenThreadToken` at `0x180015109`

## pseudocode

```c
__int64 __fastcall Pku2uImpersonateToken(HANDLE TokenHandle, void **a2, int *a3)
{
  int LastError; // ebx
  bool v7; // sf
  PSID SidToCheck; // [rsp+60h] [rbp-48h] BYREF
  WINBOOL IsMember; // [rsp+68h] [rbp-40h] BYREF
  HANDLE pIdentifierAuthority; // [rsp+70h] [rbp-38h] BYREF

  WORD2(pIdentifierAuthority) = 1280;
  *a3 = 0;
  *a2 = 0;
  SidToCheck = 0;
  LODWORD(pIdentifierAuthority) = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(
         (PSID_IDENTIFIER_AUTHORITY)&pIdentifierAuthority,
         1u,
         0x14u,
         0,
         0,
         0,
         0,
         0,
         0,
         0,
         &SidToCheck) )
  {
    LastError = 0;
    if ( !CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_145765ada38d35d83bd68130d412160b_Traceguids,
          (unsigned int)LastError);
    }
  }
  else
  {
    LastError = GetLastError();
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  v7 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0xC0070000;
    v7 = LastError < 0;
  }
  if ( !v7 && !IsMember )
  {
    *a3 = 0;
    *a2 = 0;
    pIdentifierAuthority = TokenHandle;
    SidToCheck = 0;
    LastError = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &SidToCheck);
    if ( (int)(LastError + 0x80000000) < 0 || LastError == -1073741700 )
    {
      *a3 = 1;
      LastError = NtSetInformationThread(
                    (HANDLE)0xFFFFFFFFFFFFFFFELL,
                    ThreadImpersonationToken,
                    &pIdentifierAuthority,
                    8u);
      *a2 = SidToCheck;
    }
    else if ( SidToCheck )
    {
      CloseHandle(SidToCheck);
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180014fe0  push    rbx
0x180014fe2  push    rbp
0x180014fe3  push    rsi
0x180014fe4  push    rdi
0x180014fe5  push    r14
0x180014fe7  sub     rsp, 80h
0x180014fee  mov     rax, cs:__security_cookie
0x180014ff5  xor     rax, rsp
0x180014ff8  mov     [rsp+0A8h+var_30], rax
0x180014ffd  xor     ebp, ebp
0x180014fff  mov     word ptr [rsp+0A8h+pIdentifierAuthority+4], 500h
0x180015006  mov     [r8], ebp
0x180015009  lea     rax, [rsp+0A8h+SidToCheck]
0x18001500e  mov     [rsp+0A8h+pSid], rax; pSid
0x180015013  mov     r14, r8
0x180015016  mov     [rsp+0A8h+nSubAuthority7], ebp; nSubAuthority7
0x18001501a  mov     rsi, rdx
0x18001501d  mov     [rsp+0A8h+nSubAuthority6], ebp; nSubAuthority6
0x180015021  mov     rdi, rcx
0x180015024  mov     [rsp+0A8h+nSubAuthority5], ebp; nSubAuthority5
0x180015028  lea     rcx, [rsp+0A8h+pIdentifierAuthority]; pIdentifierAuthority
0x18001502d  mov     [rsp+0A8h+nSubAuthority4], ebp; nSubAuthority4
0x180015031  xor     r9d, r9d; nSubAuthority1
0x180015034  mov     [rdx], rbp
0x180015037  mov     r8d, 14h; nSubAuthority0
0x18001503d  mov     [rsp+0A8h+nSubAuthority3], ebp; nSubAuthority3
0x180015041  mov     dl, 1; nSubAuthorityCount
0x180015043  mov     [rsp+0A8h+nSubAuthority2], ebp; nSubAuthority2
0x180015047  mov     [rsp+0A8h+SidToCheck], rbp
0x18001504c  mov     dword ptr [rsp+0A8h+pIdentifierAuthority], ebp
0x180015050  mov     [rsp+0A8h+IsMember], ebp
0x180015054  call    cs:__imp_AllocateAndInitializeSid
0x18001505a  test    eax, eax
0x18001505c  jnz     short loc_180015068
0x18001505e  call    cs:__imp_GetLastError
0x180015064  mov     ebx, eax
0x180015066  jmp     short loc_1800150BA
0x180015068  mov     rdx, [rsp+0A8h+SidToCheck]; SidToCheck
0x18001506d  lea     r8, [rsp+0A8h+IsMember]; IsMember
0x180015072  mov     rcx, rdi; TokenHandle
0x180015075  mov     ebx, ebp
0x180015077  call    cs:__imp_CheckTokenMembership
0x18001507d  test    eax, eax
0x18001507f  jnz     short loc_1800150BA
0x180015081  call    cs:__imp_GetLastError
0x180015087  mov     ebx, eax
0x180015089  mov     rcx, cs:WPP_GLOBAL_Control
0x180015090  lea     rax, WPP_GLOBAL_Control
0x180015097  cmp     rcx, rax
0x18001509a  jz      short loc_1800150BA
0x18001509c  test    byte ptr [rcx+1Ch], 1
0x1800150a0  jz      short loc_1800150BA
0x1800150a2  mov     rcx, [rcx+10h]
0x1800150a6  lea     r8, WPP_145765ada38d35d83bd68130d412160b_Traceguids
0x1800150ad  mov     edx, 0Eh
0x1800150b2  mov     r9d, ebx
0x1800150b5  call    WPP_SF_d
0x1800150ba  mov     rcx, [rsp+0A8h+SidToCheck]; pSid
0x1800150bf  test    rcx, rcx
0x1800150c2  jz      short loc_1800150CA
0x1800150c4  call    cs:__imp_FreeSid
0x1800150ca  test    ebx, ebx
0x1800150cc  jle     short loc_1800150D9
0x1800150ce  movzx   ebx, bx
0x1800150d1  or      ebx, 0C0070000h
0x1800150d7  test    ebx, ebx
0x1800150d9  js      loc_180015164
0x1800150df  cmp     [rsp+0A8h+IsMember], ebp
0x1800150e3  jnz     short loc_180015164
0x1800150e5  mov     [r14], ebp
0x1800150e8  lea     r9, [rsp+0A8h+SidToCheck]; TokenHandle
0x1800150ed  mov     r8b, 1; OpenAsSelf
0x1800150f0  mov     [rsi], rbp
0x1800150f3  mov     edx, 0Ch; DesiredAccess
0x1800150f8  mov     [rsp+0A8h+pIdentifierAuthority], rdi
0x1800150fd  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180015104  mov     [rsp+0A8h+SidToCheck], rbp
0x180015109  call    cs:__imp_NtOpenThreadToken
0x18001510f  mov     ecx, 80000000h
0x180015114  mov     ebx, eax
0x180015116  add     eax, ecx
0x180015118  test    ecx, eax
0x18001511a  jnz     short loc_180015136
0x18001511c  cmp     ebx, 0C000007Ch
0x180015122  jz      short loc_180015136
0x180015124  mov     rcx, [rsp+0A8h+SidToCheck]; hObject
0x180015129  test    rcx, rcx
0x18001512c  jz      short loc_180015164
0x18001512e  call    cs:__imp_CloseHandle
0x180015134  jmp     short loc_180015164
0x180015136  mov     r9d, 8; ThreadInformationLength
0x18001513c  mov     dword ptr [r14], 1
0x180015143  lea     r8, [rsp+0A8h+pIdentifierAuthority]; ThreadInformation
0x180015148  mov     edx, 5; ThreadInformationClass
0x18001514d  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180015154  call    cs:__imp_NtSetInformationThread
0x18001515a  mov     rcx, [rsp+0A8h+SidToCheck]
0x18001515f  mov     ebx, eax
0x180015161  mov     [rsi], rcx
0x180015164  mov     eax, ebx
0x180015166  mov     rcx, [rsp+0A8h+var_30]
0x18001516b  xor     rcx, rsp; StackCookie
0x18001516e  call    __security_check_cookie
0x180015173  add     rsp, 80h
0x18001517a  pop     r14
0x18001517c  pop     rdi
0x18001517d  pop     rsi
0x18001517e  pop     rbp
0x18001517f  pop     rbx
0x180015180  retn
```
