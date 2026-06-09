# ThreadIsAdmin(void)

- ea: `0x1801ad010`
- end: `0x1801ad251`
- name: `?ThreadIsAdmin@@YA_NXZ`
- size: `577`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801acff0`

## callees

- `0x180006290`
- `0x18000b764`
- `0x18000b804`
- `0x18000b964`
- `0x18000bb68`
- `0x18000cd44`
- `0x18000cd6c`
- `0x180143528`
- `0x1801ad010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad17a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad1a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad0ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad17a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ad1a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801ad076`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801ad076`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801ad08c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801ad08c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ad1ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801ad1ed`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801ad117`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801ad19f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801ad117`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801ad19f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801ad1d4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801ad1e3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801ad1d4`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801ad1e3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801ad0e5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801ad170`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801ad0e5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801ad170`

## string_xrefs

- `0x1801ad041`: `ThreadIsAdmin`

## pseudocode

```c
char ThreadIsAdmin(void)
{
  HANDLE CurrentThread; // rax
  char v1; // bl
  signed int LastError; // eax
  __int64 v3; // rdx
  WINBOOL IsMember; // [rsp+60h] [rbp-19h] BYREF
  WINBOOL v6; // [rsp+64h] [rbp-15h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-11h] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp-9h] BYREF
  PSID pSid; // [rsp+78h] [rbp-1h] BYREF
  _QWORD v10[4]; // [rsp+80h] [rbp+7h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+27h] BYREF

  CSmTimer::CSmTimer((CSmTimer *)v10);
  CSmTimer::Start((CSmTimer *)v10);
  TraceEnterFunction<5,0,0>(L"ThreadIsAdmin", 11);
  TokenHandle = (void *)-1LL;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  pSid = 0;
  IsMember = 0;
  v6 = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  CurrentThread = GetCurrentThread();
  v1 = 1;
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
      {
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x227u, 0, 0, 0, 0, 0, 0, &pSid) )
        {
          if ( CheckTokenMembership(TokenHandle, pSid, &v6) )
            goto LABEL_22;
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v3 = 47;
        }
        else
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v3 = 45;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v3 = 36;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v3 = 34;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v3 = 25;
  }
  TraceHRError<2,0,0>(L"ThreadIsAdmin", v3, (unsigned int)LastError);
LABEL_22:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( pSid )
    FreeSid(pSid);
  CloseHandle(TokenHandle);
  CSmTimer::Stop((CSmTimer *)v10);
  TraceExitFunctionVoid<5,0,0>(L"ThreadIsAdmin", 61, (unsigned __int64)(1000LL * (v10[1] - v10[0])) / v10[2]);
  if ( !IsMember && !v6 )
    v1 = 0;
  CSmTimer::~CSmTimer((CSmTimer *)v10);
  return v1;
}

```

## disassembly

```asm
0x1801ad010  push    rbp
0x1801ad012  push    rbx
0x1801ad013  push    rsi
0x1801ad014  push    rdi
0x1801ad015  lea     rbp, [rsp-3Fh]
0x1801ad01a  sub     rsp, 0B8h
0x1801ad021  mov     rax, cs:__security_cookie
0x1801ad028  xor     rax, rsp
0x1801ad02b  mov     [rbp+57h+var_28], rax
0x1801ad02f  lea     rcx, [rbp+57h+var_50]; this
0x1801ad033  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1801ad038  lea     rcx, [rbp+57h+var_50]; this
0x1801ad03c  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801ad041  lea     rsi, aThreadisadmin; "ThreadIsAdmin"
0x1801ad048  mov     edx, 0Bh
0x1801ad04d  mov     rcx, rsi
0x1801ad050  call    ??$TraceEnterFunction@$04$0A@$0A@@@YAXPEBGI@Z; TraceEnterFunction<5,0,0>(ushort const *,uint)
0x1801ad055  xor     edi, edi
0x1801ad057  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1801ad05f  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x1801ad062  mov     [rbp+57h+SidToCheck], rdi
0x1801ad066  mov     [rbp+57h+var_58], rdi
0x1801ad06a  mov     [rbp+57h+IsMember], edi
0x1801ad06d  mov     [rbp+57h+var_6C], edi
0x1801ad070  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1801ad076  call    cs:__imp_GetCurrentThread
0x1801ad07c  lea     ebx, [rdi+1]
0x1801ad07f  mov     rcx, rax; ThreadHandle
0x1801ad082  mov     r8d, ebx; OpenAsSelf
0x1801ad085  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1801ad089  lea     edx, [rdi+8]; DesiredAccess
0x1801ad08c  call    cs:__imp_OpenThreadToken
0x1801ad092  test    eax, eax
0x1801ad094  jnz     short loc_1801AD0B2
0x1801ad096  call    cs:__imp_GetLastError
0x1801ad09c  test    eax, eax
0x1801ad09e  jle     short loc_1801AD0A8
0x1801ad0a0  movzx   eax, ax
0x1801ad0a3  or      eax, 80070000h
0x1801ad0a8  mov     edx, 19h
0x1801ad0ad  jmp     loc_1801AD1C0
0x1801ad0b2  lea     rax, [rbp+57h+SidToCheck]
0x1801ad0b6  mov     r9d, 220h; nSubAuthority1
0x1801ad0bc  mov     [rsp+0D0h+pSid], rax; pSid
0x1801ad0c1  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1801ad0c5  mov     [rsp+0D0h+nSubAuthority7], edi; nSubAuthority7
0x1801ad0c9  mov     r8d, 20h ; ' '; nSubAuthority0
0x1801ad0cf  mov     [rsp+0D0h+nSubAuthority6], edi; nSubAuthority6
0x1801ad0d3  mov     dl, 2; nSubAuthorityCount
0x1801ad0d5  mov     [rsp+0D0h+nSubAuthority5], edi; nSubAuthority5
0x1801ad0d9  mov     [rsp+0D0h+nSubAuthority4], edi; nSubAuthority4
0x1801ad0dd  mov     [rsp+0D0h+nSubAuthority3], edi; nSubAuthority3
0x1801ad0e1  mov     [rsp+0D0h+nSubAuthority2], edi; nSubAuthority2
0x1801ad0e5  call    cs:__imp_AllocateAndInitializeSid
0x1801ad0eb  test    eax, eax
0x1801ad0ed  jnz     short loc_1801AD10B
0x1801ad0ef  call    cs:__imp_GetLastError
0x1801ad0f5  test    eax, eax
0x1801ad0f7  jle     short loc_1801AD101
0x1801ad0f9  movzx   eax, ax
0x1801ad0fc  or      eax, 80070000h
0x1801ad101  mov     edx, 22h ; '"'
0x1801ad106  jmp     loc_1801AD1C0
0x1801ad10b  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1801ad10f  lea     r8, [rbp+57h+IsMember]; IsMember
0x1801ad113  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1801ad117  call    cs:__imp_CheckTokenMembership
0x1801ad11d  test    eax, eax
0x1801ad11f  jnz     short loc_1801AD13D
0x1801ad121  call    cs:__imp_GetLastError
0x1801ad127  test    eax, eax
0x1801ad129  jle     short loc_1801AD133
0x1801ad12b  movzx   eax, ax
0x1801ad12e  or      eax, 80070000h
0x1801ad133  mov     edx, 24h ; '$'
0x1801ad138  jmp     loc_1801AD1C0
0x1801ad13d  lea     rax, [rbp+57h+var_58]
0x1801ad141  mov     r9d, 227h; nSubAuthority1
0x1801ad147  mov     [rsp+0D0h+pSid], rax; pSid
0x1801ad14c  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1801ad150  mov     [rsp+0D0h+nSubAuthority7], edi; nSubAuthority7
0x1801ad154  mov     r8d, 20h ; ' '; nSubAuthority0
0x1801ad15a  mov     [rsp+0D0h+nSubAuthority6], edi; nSubAuthority6
0x1801ad15e  mov     dl, 2; nSubAuthorityCount
0x1801ad160  mov     [rsp+0D0h+nSubAuthority5], edi; nSubAuthority5
0x1801ad164  mov     [rsp+0D0h+nSubAuthority4], edi; nSubAuthority4
0x1801ad168  mov     [rsp+0D0h+nSubAuthority3], edi; nSubAuthority3
0x1801ad16c  mov     [rsp+0D0h+nSubAuthority2], edi; nSubAuthority2
0x1801ad170  call    cs:__imp_AllocateAndInitializeSid
0x1801ad176  test    eax, eax
0x1801ad178  jnz     short loc_1801AD193
0x1801ad17a  call    cs:__imp_GetLastError
0x1801ad180  test    eax, eax
0x1801ad182  jle     short loc_1801AD18C
0x1801ad184  movzx   eax, ax
0x1801ad187  or      eax, 80070000h
0x1801ad18c  mov     edx, 2Dh ; '-'
0x1801ad191  jmp     short loc_1801AD1C0
0x1801ad193  mov     rdx, [rbp+57h+var_58]; SidToCheck
0x1801ad197  lea     r8, [rbp+57h+var_6C]; IsMember
0x1801ad19b  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1801ad19f  call    cs:__imp_CheckTokenMembership
0x1801ad1a5  test    eax, eax
0x1801ad1a7  jnz     short loc_1801AD1CB
0x1801ad1a9  call    cs:__imp_GetLastError
0x1801ad1af  test    eax, eax
0x1801ad1b1  jle     short loc_1801AD1BB
0x1801ad1b3  movzx   eax, ax
0x1801ad1b6  or      eax, 80070000h
0x1801ad1bb  mov     edx, 2Fh ; '/'
0x1801ad1c0  mov     r8d, eax
0x1801ad1c3  mov     rcx, rsi
0x1801ad1c6  call    ??$TraceHRError@$01$0A@$0A@@@YAXPEBGII@Z; TraceHRError<2,0,0>(ushort const *,uint,uint)
0x1801ad1cb  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1801ad1cf  test    rcx, rcx
0x1801ad1d2  jz      short loc_1801AD1DA
0x1801ad1d4  call    cs:__imp_FreeSid
0x1801ad1da  mov     rcx, [rbp+57h+var_58]; pSid
0x1801ad1de  test    rcx, rcx
0x1801ad1e1  jz      short loc_1801AD1E9
0x1801ad1e3  call    cs:__imp_FreeSid
0x1801ad1e9  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1801ad1ed  call    cs:__imp_CloseHandle
0x1801ad1f3  lea     rcx, [rbp+57h+var_50]; this
0x1801ad1f7  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801ad1fc  mov     rax, [rbp+57h+var_48]
0x1801ad200  xor     edx, edx
0x1801ad202  sub     rax, [rbp+57h+var_50]
0x1801ad206  mov     rcx, rsi
0x1801ad209  imul    rax, 3E8h
0x1801ad210  div     [rbp+57h+var_40]
0x1801ad214  mov     edx, 3Dh ; '='
0x1801ad219  mov     r8, rax
0x1801ad21c  call    ??$TraceExitFunctionVoid@$04$0A@$0A@@@YAXPEBGI_K@Z; TraceExitFunctionVoid<5,0,0>(ushort const *,uint,unsigned __int64)
0x1801ad221  cmp     [rbp+57h+IsMember], edi
0x1801ad224  jnz     short loc_1801AD22E
0x1801ad226  cmp     [rbp+57h+var_6C], edi
0x1801ad229  jnz     short loc_1801AD22E
0x1801ad22b  mov     bl, dil
0x1801ad22e  lea     rcx, [rbp+57h+var_50]; this
0x1801ad232  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x1801ad237  mov     al, bl
0x1801ad239  mov     rcx, [rbp+57h+var_28]
0x1801ad23d  xor     rcx, rsp; StackCookie
0x1801ad240  call    __security_check_cookie
0x1801ad245  add     rsp, 0B8h
0x1801ad24c  pop     rdi
0x1801ad24d  pop     rsi
0x1801ad24e  pop     rbx
0x1801ad24f  pop     rbp
0x1801ad250  retn
```
