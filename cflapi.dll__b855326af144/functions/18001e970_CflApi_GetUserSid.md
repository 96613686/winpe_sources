# CflApi::GetUserSid

- ea: `0x18001e970`
- end: `0x18001ebd2`
- name: `CflApi::GetUserSid`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f2d8`

## callees

- `0x180002490`
- `0x18000375c`
- `0x1800067a4`
- `0x1800067c4`
- `0x180008ad0`
- `0x180010700`
- `0x1800158b8`
- `0x18001b79c`
- `0x18001b874`
- `0x18001e970`
- `0x18001ebd8`
- `0x18002e008`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x18001e9f7`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x18001e9f7`

## string_xrefs

- `0x18001e9b8`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001ea05`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001ea86`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001eb6c`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CflApi::GetUserSid(int a1, _QWORD *a2)
{
  unsigned int v4; // ebx
  const char *v5; // r9
  unsigned int v7; // ecx
  PWTS_SESSION_INFO_1W v8; // rdx
  __int64 v9; // rdi
  WTS_CONNECTSTATE_CLASS State; // eax
  LPWSTR pDomainName; // r9
  unsigned __int64 v12; // rdx
  __int64 v13; // rbx
  const WCHAR *p_Src; // rcx
  int UserSid_0; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  HLOCAL v20; // rbx
  int pCount; // [rsp+20h] [rbp-29h]
  int pCounta; // [rsp+20h] [rbp-29h]
  DWORD v23; // [rsp+30h] [rbp-19h] BYREF
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+38h] [rbp-11h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-9h] BYREF
  DWORD pLevel; // [rsp+48h] [rbp-1h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp+7h] BYREF
  __int16 v28; // [rsp+60h] [rbp+17h]
  __int128 Src; // [rsp+68h] [rbp+1Fh] BYREF
  unsigned __int64 v30; // [rsp+78h] [rbp+2Fh]
  unsigned __int64 v31; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *a2 = 0;
  if ( !(unsigned __int8)IsWTSEnumerateSessionsExWPresent() )
  {
    v4 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D8,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x80004001LL,
      pCount);
    return v4;
  }
  hMem = 0;
  pLevel = 1;
  ppSessionInfo = 0;
  v23 = 0;
  if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &v23) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x4DF,
             (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
             v5);
  v27[0] = &ppSessionInfo;
  v27[1] = &v23;
  v28 = 256;
  v7 = 0;
  if ( !v23 )
    goto LABEL_14;
  v8 = ppSessionInfo;
  while ( 1 )
  {
    v9 = v7;
    if ( ppSessionInfo[v9].SessionId != a1 )
      goto LABEL_13;
    State = ppSessionInfo[v9].State;
    if ( State != WTSConnected )
      break;
    if ( !ppSessionInfo[v9].pUserName )
    {
      wil::details::ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f___::operator()(v27);
      return 0;
    }
LABEL_13:
    if ( ++v7 >= v23 )
      goto LABEL_14;
  }
  if ( State || !ppSessionInfo[v9].pUserName )
    goto LABEL_13;
  Src = 0;
  v30 = 0;
  v31 = 7;
  LOWORD(Src) = 0;
  pDomainName = ppSessionInfo[v9].pDomainName;
  if ( pDomainName )
  {
    v12 = -1;
    do
      ++v12;
    while ( pDomainName[v12] );
    if ( v12 > 7 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(&Src);
    }
    else
    {
      v30 = v12;
      v13 = 2 * v12;
      memmove_0(&Src, pDomainName, 2 * v12);
      *(_WORD *)((char *)&Src + v13) = 0;
    }
    std::wstring::operator+=(&Src, L"\\");
    v8 = ppSessionInfo;
  }
  std::wstring::operator+=(&Src, v8[v9].pUserName);
  hMem = 0;
  p_Src = (const WCHAR *)&Src;
  if ( v31 > 7 )
    p_Src = (const WCHAR *)Src;
  UserSid_0 = CflApi::GetUserSid_0(p_Src, &hMem);
  v4 = UserSid_0;
  if ( UserSid_0 >= 0 )
  {
    std::wstring::~wstring(&Src, v16, v17);
    v20 = hMem;
    if ( hMem )
    {
      wil::details::ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f___::operator()(v27);
      *a2 = v20;
      return 0;
    }
LABEL_14:
    v4 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x503,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x80070490LL,
      pCounta);
    wil::details::ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f___::operator()(v27);
    return v4;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4FD,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
    (const char *)(unsigned int)UserSid_0,
    pCounta);
  std::wstring::~wstring(&Src, v18, v19);
  wil::details::ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f___::operator()(v27);
  if ( hMem )
    CflFreeBuffer(hMem);
  return v4;
}

```

## disassembly

```asm
0x18001e970  mov     [rsp-8+arg_0], rbx
0x18001e975  mov     [rsp-8+arg_10], rsi
0x18001e97a  push    rbp
0x18001e97b  push    rdi
0x18001e97c  push    r14
0x18001e97e  lea     rbp, [rsp-47h]
0x18001e983  sub     rsp, 90h
0x18001e98a  mov     rax, cs:__security_cookie
0x18001e991  xor     rax, rsp
0x18001e994  mov     [rbp+57h+var_18], rax
0x18001e998  mov     rsi, rdx
0x18001e99b  mov     ebx, ecx
0x18001e99d  xor     r14d, r14d
0x18001e9a0  mov     [rdx], r14
0x18001e9a3  call    IsWTSEnumerateSessionsExWPresent
0x18001e9a8  test    al, al
0x18001e9aa  jnz     short loc_18001E9CE
0x18001e9ac  mov     rcx, [rbp+5Fh]; this
0x18001e9b0  mov     ebx, 80004001h
0x18001e9b5  mov     r9d, ebx; char *
0x18001e9b8  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001e9bf  mov     edx, 4D8h; void *
0x18001e9c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9c9  jmp     loc_18001EAA2
0x18001e9ce  mov     [rbp+57h+hMem], r14
0x18001e9d2  mov     [rbp+57h+pLevel], 1
0x18001e9d9  mov     [rbp+57h+ppSessionInfo], r14
0x18001e9dd  mov     [rbp+57h+var_70], r14d
0x18001e9e1  lea     rax, [rbp+57h+var_70]
0x18001e9e5  mov     qword ptr [rsp+0A0h+pCount], rax; int
0x18001e9ea  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x18001e9ee  xor     r8d, r8d; Filter
0x18001e9f1  lea     rdx, [rbp+57h+pLevel]; pLevel
0x18001e9f5  xor     ecx, ecx; hServer
0x18001e9f7  call    cs:__imp_WTSEnumerateSessionsExW
0x18001e9fd  test    eax, eax
0x18001e9ff  jnz     short loc_18001EA18
0x18001ea01  mov     rcx, [rbp+5Fh]; this
0x18001ea05  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ea0c  mov     edx, 4DFh; void *
0x18001ea11  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ea16  jmp     short loc_18001EA66
0x18001ea18  lea     rax, [rbp+57h+ppSessionInfo]
0x18001ea1c  mov     [rbp+57h+var_50], rax
0x18001ea20  lea     rax, [rbp+57h+var_70]
0x18001ea24  mov     [rbp+57h+var_48], rax
0x18001ea28  mov     [rbp+57h+var_40], 100h
0x18001ea2e  mov     ecx, r14d
0x18001ea31  mov     r8d, [rbp+57h+var_70]
0x18001ea35  test    r8d, r8d
0x18001ea38  jz      short loc_18001EA7A
0x18001ea3a  mov     rdx, [rbp+57h+ppSessionInfo]
0x18001ea3e  mov     eax, ecx
0x18001ea40  imul    rdi, rax, 38h ; '8'
0x18001ea44  cmp     [rdi+rdx+8], ebx
0x18001ea48  jnz     short loc_18001EA73
0x18001ea4a  mov     eax, [rdi+rdx+4]
0x18001ea4e  cmp     eax, 1
0x18001ea51  jnz     short loc_18001EA68
0x18001ea53  cmp     [rdi+rdx+20h], r14
0x18001ea58  jnz     short loc_18001EA73
0x18001ea5a  lea     rcx, [rbp+57h+var_50]
0x18001ea5e  call    wil__details__ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f_____operator__
0x18001ea63  mov     eax, r14d
0x18001ea66  jmp     short loc_18001EAA4
0x18001ea68  test    eax, eax
0x18001ea6a  jnz     short loc_18001EA73
0x18001ea6c  cmp     [rdi+rdx+20h], r14
0x18001ea71  jnz     short loc_18001EAC8
0x18001ea73  inc     ecx
0x18001ea75  cmp     ecx, r8d
0x18001ea78  jb      short loc_18001EA3E
0x18001ea7a  mov     rcx, [rbp+5Fh]; this
0x18001ea7e  mov     ebx, 80070490h
0x18001ea83  mov     r9d, ebx; char *
0x18001ea86  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ea8d  mov     edx, 503h; void *
0x18001ea92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ea97  nop
0x18001ea98  lea     rcx, [rbp+57h+var_50]
0x18001ea9c  call    wil__details__ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f_____operator__
0x18001eaa1  nop
0x18001eaa2  mov     eax, ebx
0x18001eaa4  mov     rcx, [rbp+57h+var_18]
0x18001eaa8  xor     rcx, rsp; StackCookie
0x18001eaab  call    __security_check_cookie
0x18001eab0  lea     r11, [rsp+0A0h+var_10]
0x18001eab8  mov     rbx, [r11+20h]
0x18001eabc  mov     rsi, [r11+30h]
0x18001eac0  mov     rsp, r11
0x18001eac3  pop     r14
0x18001eac5  pop     rdi
0x18001eac6  pop     rbp
0x18001eac7  retn
0x18001eac8  xorps   xmm0, xmm0
0x18001eacb  movups  [rbp+57h+Src], xmm0
0x18001eacf  mov     [rbp+57h+var_28], r14
0x18001ead3  mov     [rbp+57h+var_20], 7
0x18001eadb  mov     word ptr [rbp+57h+Src], r14w
0x18001eae0  mov     r9, [rdi+rdx+28h]
0x18001eae5  test    r9, r9
0x18001eae8  jz      short loc_18001EB36
0x18001eaea  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001eaee  inc     rdx
0x18001eaf1  cmp     [r9+rdx*2], r14w
0x18001eaf6  jnz     short loc_18001EAEE
0x18001eaf8  lea     rcx, [rbp+57h+Src]; void *
0x18001eafc  cmp     rdx, 7
0x18001eb00  ja      short loc_18001EB1D
0x18001eb02  mov     [rbp+57h+var_28], rdx
0x18001eb06  lea     rbx, [rdx+rdx]
0x18001eb0a  mov     r8, rbx; Size
0x18001eb0d  mov     rdx, r9; Src
0x18001eb10  call    memmove_0
0x18001eb15  mov     word ptr [rbp+rbx+57h+Src], r14w
0x18001eb1b  jmp     short loc_18001EB22
0x18001eb1d  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001eb22  lea     rdx, asc_1800321DC; "\\"
0x18001eb29  lea     rcx, [rbp+57h+Src]; Src
0x18001eb2d  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18001eb32  mov     rdx, [rbp+57h+ppSessionInfo]
0x18001eb36  mov     rdx, [rdi+rdx+20h]; void *
0x18001eb3b  lea     rcx, [rbp+57h+Src]; Src
0x18001eb3f  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18001eb44  mov     [rbp+57h+hMem], r14
0x18001eb48  lea     rcx, [rbp+57h+Src]
0x18001eb4c  cmp     [rbp+57h+var_20], 7
0x18001eb51  cmova   rcx, qword ptr [rbp+57h+Src]; SourceString
0x18001eb56  lea     rdx, [rbp+57h+hMem]
0x18001eb5a  call    CflApi__GetUserSid_0
0x18001eb5f  mov     ebx, eax
0x18001eb61  test    eax, eax
0x18001eb63  jns     short loc_18001EBA9
0x18001eb65  mov     rcx, [rbp+5Fh]; this
0x18001eb69  mov     r9d, eax; char *
0x18001eb6c  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001eb73  mov     edx, 4FDh; void *
0x18001eb78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb7d  nop
0x18001eb7e  lea     rcx, [rbp+57h+Src]
0x18001eb82  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eb87  nop
0x18001eb88  lea     rcx, [rbp+57h+var_50]
0x18001eb8c  call    wil__details__ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f_____operator__
0x18001eb91  nop
0x18001eb92  mov     rcx, [rbp+57h+hMem]; hMem
0x18001eb96  test    rcx, rcx
0x18001eb99  jz      loc_18001EAA2
0x18001eb9f  call    CflFreeBuffer
0x18001eba4  jmp     loc_18001EAA2
0x18001eba9  lea     rcx, [rbp+57h+Src]
0x18001ebad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ebb2  mov     rbx, [rbp+57h+hMem]
0x18001ebb6  test    rbx, rbx
0x18001ebb9  jz      loc_18001EA7A
0x18001ebbf  lea     rcx, [rbp+57h+var_50]
0x18001ebc3  call    wil__details__ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f_____operator__
0x18001ebc8  mov     [rsi], rbx
0x18001ebcb  xor     eax, eax
0x18001ebcd  jmp     loc_18001EAA4
```
