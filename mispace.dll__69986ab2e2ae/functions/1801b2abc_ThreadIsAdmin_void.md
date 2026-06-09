# ThreadIsAdmin(void)

- ea: `0x1801b2abc`
- end: `0x1801b2d52`
- name: `?ThreadIsAdmin@@YA_NXZ`
- size: `662`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801b2a9c`

## callees

- `0x180006350`
- `0x18000b63c`
- `0x18000b6dc`
- `0x18000b840`
- `0x18000ba50`
- `0x18000cca4`
- `0x18000ccd4`
- `0x180147a54`
- `0x1801b2abc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2b4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2bb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2b4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2bb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b2c91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b2b22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801b2b22`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801b2b3e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801b2b3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b2ce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b2ce7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801b2be1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801b2c81`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801b2be1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801b2c81`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801b2cc2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801b2cd7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801b2cc2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801b2cd7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801b2ba3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801b2c46`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801b2ba3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1801b2c46`

## string_xrefs

- `0x1801b2aed`: `ThreadIsAdmin`

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
0x1801b2abc  push    rbp
0x1801b2abe  push    rbx
0x1801b2abf  push    rsi
0x1801b2ac0  push    rdi
0x1801b2ac1  lea     rbp, [rsp-3Fh]
0x1801b2ac6  sub     rsp, 0B8h
0x1801b2acd  mov     rax, cs:__security_cookie
0x1801b2ad4  xor     rax, rsp
0x1801b2ad7  mov     [rbp+57h+var_28], rax
0x1801b2adb  lea     rcx, [rbp+57h+var_50]; this
0x1801b2adf  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1801b2ae4  lea     rcx, [rbp+57h+var_50]; this
0x1801b2ae8  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1801b2aed  lea     rsi, aThreadisadmin; "ThreadIsAdmin"
0x1801b2af4  mov     edx, 0Bh
0x1801b2af9  mov     rcx, rsi
0x1801b2afc  call    ??$TraceEnterFunction@$04$0A@$0A@@@YAXPEBGI@Z; TraceEnterFunction<5,0,0>(ushort const *,uint)
0x1801b2b01  xor     edi, edi
0x1801b2b03  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1801b2b0b  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x1801b2b0e  mov     [rbp+57h+SidToCheck], rdi
0x1801b2b12  mov     [rbp+57h+var_58], rdi
0x1801b2b16  mov     [rbp+57h+IsMember], edi
0x1801b2b19  mov     [rbp+57h+var_6C], edi
0x1801b2b1c  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1801b2b22  call    cs:__imp_GetCurrentThread
0x1801b2b29  nop     dword ptr [rax+rax+00h]
0x1801b2b2e  lea     ebx, [rdi+1]
0x1801b2b31  mov     rcx, rax; ThreadHandle
0x1801b2b34  mov     r8d, ebx; OpenAsSelf
0x1801b2b37  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1801b2b3b  lea     edx, [rdi+8]; DesiredAccess
0x1801b2b3e  call    cs:__imp_OpenThreadToken
0x1801b2b45  nop     dword ptr [rax+rax+00h]
0x1801b2b4a  test    eax, eax
0x1801b2b4c  jnz     short loc_1801B2B70
0x1801b2b4e  call    cs:__imp_GetLastError
0x1801b2b55  nop     dword ptr [rax+rax+00h]
0x1801b2b5a  test    eax, eax
0x1801b2b5c  jle     short loc_1801B2B66
0x1801b2b5e  movzx   eax, ax
0x1801b2b61  or      eax, 80070000h
0x1801b2b66  mov     edx, 19h
0x1801b2b6b  jmp     loc_1801B2CAE
0x1801b2b70  lea     rax, [rbp+57h+SidToCheck]
0x1801b2b74  mov     r9d, 220h; nSubAuthority1
0x1801b2b7a  mov     [rsp+0D0h+pSid], rax; pSid
0x1801b2b7f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1801b2b83  mov     [rsp+0D0h+nSubAuthority7], edi; nSubAuthority7
0x1801b2b87  mov     r8d, 20h ; ' '; nSubAuthority0
0x1801b2b8d  mov     [rsp+0D0h+nSubAuthority6], edi; nSubAuthority6
0x1801b2b91  mov     dl, 2; nSubAuthorityCount
0x1801b2b93  mov     [rsp+0D0h+nSubAuthority5], edi; nSubAuthority5
0x1801b2b97  mov     [rsp+0D0h+nSubAuthority4], edi; nSubAuthority4
0x1801b2b9b  mov     [rsp+0D0h+nSubAuthority3], edi; nSubAuthority3
0x1801b2b9f  mov     [rsp+0D0h+nSubAuthority2], edi; nSubAuthority2
0x1801b2ba3  call    cs:__imp_AllocateAndInitializeSid
0x1801b2baa  nop     dword ptr [rax+rax+00h]
0x1801b2baf  test    eax, eax
0x1801b2bb1  jnz     short loc_1801B2BD5
0x1801b2bb3  call    cs:__imp_GetLastError
0x1801b2bba  nop     dword ptr [rax+rax+00h]
0x1801b2bbf  test    eax, eax
0x1801b2bc1  jle     short loc_1801B2BCB
0x1801b2bc3  movzx   eax, ax
0x1801b2bc6  or      eax, 80070000h
0x1801b2bcb  mov     edx, 22h ; '"'
0x1801b2bd0  jmp     loc_1801B2CAE
0x1801b2bd5  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1801b2bd9  lea     r8, [rbp+57h+IsMember]; IsMember
0x1801b2bdd  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1801b2be1  call    cs:__imp_CheckTokenMembership
0x1801b2be8  nop     dword ptr [rax+rax+00h]
0x1801b2bed  test    eax, eax
0x1801b2bef  jnz     short loc_1801B2C13
0x1801b2bf1  call    cs:__imp_GetLastError
0x1801b2bf8  nop     dword ptr [rax+rax+00h]
0x1801b2bfd  test    eax, eax
0x1801b2bff  jle     short loc_1801B2C09
0x1801b2c01  movzx   eax, ax
0x1801b2c04  or      eax, 80070000h
0x1801b2c09  mov     edx, 24h ; '$'
0x1801b2c0e  jmp     loc_1801B2CAE
0x1801b2c13  lea     rax, [rbp+57h+var_58]
0x1801b2c17  mov     r9d, 227h; nSubAuthority1
0x1801b2c1d  mov     [rsp+0D0h+pSid], rax; pSid
0x1801b2c22  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1801b2c26  mov     [rsp+0D0h+nSubAuthority7], edi; nSubAuthority7
0x1801b2c2a  mov     r8d, 20h ; ' '; nSubAuthority0
0x1801b2c30  mov     [rsp+0D0h+nSubAuthority6], edi; nSubAuthority6
0x1801b2c34  mov     dl, 2; nSubAuthorityCount
0x1801b2c36  mov     [rsp+0D0h+nSubAuthority5], edi; nSubAuthority5
0x1801b2c3a  mov     [rsp+0D0h+nSubAuthority4], edi; nSubAuthority4
0x1801b2c3e  mov     [rsp+0D0h+nSubAuthority3], edi; nSubAuthority3
0x1801b2c42  mov     [rsp+0D0h+nSubAuthority2], edi; nSubAuthority2
0x1801b2c46  call    cs:__imp_AllocateAndInitializeSid
0x1801b2c4d  nop     dword ptr [rax+rax+00h]
0x1801b2c52  test    eax, eax
0x1801b2c54  jnz     short loc_1801B2C75
0x1801b2c56  call    cs:__imp_GetLastError
0x1801b2c5d  nop     dword ptr [rax+rax+00h]
0x1801b2c62  test    eax, eax
0x1801b2c64  jle     short loc_1801B2C6E
0x1801b2c66  movzx   eax, ax
0x1801b2c69  or      eax, 80070000h
0x1801b2c6e  mov     edx, 2Dh ; '-'
0x1801b2c73  jmp     short loc_1801B2CAE
0x1801b2c75  mov     rdx, [rbp+57h+var_58]; SidToCheck
0x1801b2c79  lea     r8, [rbp+57h+var_6C]; IsMember
0x1801b2c7d  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1801b2c81  call    cs:__imp_CheckTokenMembership
0x1801b2c88  nop     dword ptr [rax+rax+00h]
0x1801b2c8d  test    eax, eax
0x1801b2c8f  jnz     short loc_1801B2CB9
0x1801b2c91  call    cs:__imp_GetLastError
0x1801b2c98  nop     dword ptr [rax+rax+00h]
0x1801b2c9d  test    eax, eax
0x1801b2c9f  jle     short loc_1801B2CA9
0x1801b2ca1  movzx   eax, ax
0x1801b2ca4  or      eax, 80070000h
0x1801b2ca9  mov     edx, 2Fh ; '/'
0x1801b2cae  mov     r8d, eax
0x1801b2cb1  mov     rcx, rsi
0x1801b2cb4  call    ??$TraceHRError@$01$0A@$0A@@@YAXPEBGII@Z; TraceHRError<2,0,0>(ushort const *,uint,uint)
0x1801b2cb9  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x1801b2cbd  test    rcx, rcx
0x1801b2cc0  jz      short loc_1801B2CCE
0x1801b2cc2  call    cs:__imp_FreeSid
0x1801b2cc9  nop     dword ptr [rax+rax+00h]
0x1801b2cce  mov     rcx, [rbp+57h+var_58]; pSid
0x1801b2cd2  test    rcx, rcx
0x1801b2cd5  jz      short loc_1801B2CE3
0x1801b2cd7  call    cs:__imp_FreeSid
0x1801b2cde  nop     dword ptr [rax+rax+00h]
0x1801b2ce3  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1801b2ce7  call    cs:__imp_CloseHandle
0x1801b2cee  nop     dword ptr [rax+rax+00h]
0x1801b2cf3  lea     rcx, [rbp+57h+var_50]; this
0x1801b2cf7  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1801b2cfc  mov     rax, [rbp+57h+var_48]
0x1801b2d00  xor     edx, edx
0x1801b2d02  sub     rax, [rbp+57h+var_50]
0x1801b2d06  mov     rcx, rsi
0x1801b2d09  imul    rax, 3E8h
0x1801b2d10  div     [rbp+57h+var_40]
0x1801b2d14  mov     edx, 3Dh ; '='
0x1801b2d19  mov     r8, rax
0x1801b2d1c  call    ??$TraceExitFunctionVoid@$04$0A@$0A@@@YAXPEBGI_K@Z; TraceExitFunctionVoid<5,0,0>(ushort const *,uint,unsigned __int64)
0x1801b2d21  cmp     [rbp+57h+IsMember], edi
0x1801b2d24  jnz     short loc_1801B2D2E
0x1801b2d26  cmp     [rbp+57h+var_6C], edi
0x1801b2d29  jnz     short loc_1801B2D2E
0x1801b2d2b  mov     bl, dil
0x1801b2d2e  lea     rcx, [rbp+57h+var_50]; this
0x1801b2d32  call    ??1CSmTimer@@QEAA@XZ; CSmTimer::~CSmTimer(void)
0x1801b2d37  mov     al, bl
0x1801b2d39  mov     rcx, [rbp+57h+var_28]
0x1801b2d3d  xor     rcx, rsp; StackCookie
0x1801b2d40  call    __security_check_cookie
0x1801b2d45  add     rsp, 0B8h
0x1801b2d4c  pop     rdi
0x1801b2d4d  pop     rsi
0x1801b2d4e  pop     rbx
0x1801b2d4f  pop     rbp
0x1801b2d50  retn
```
