# CflApiNew::GetUserSid

- ea: `0x18002a7cc`
- end: `0x18002aa2e`
- name: `CflApiNew::GetUserSid`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ad54`

## callees

- `0x180002490`
- `0x18000375c`
- `0x1800067a4`
- `0x1800067c4`
- `0x180008ad0`
- `0x180010700`
- `0x1800158b8`
- `0x18001b874`
- `0x1800285b8`
- `0x18002a7cc`
- `0x18002aa34`
- `0x18002e008`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x18002a853`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x18002a853`

## string_xrefs

- `0x18002a814`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002a861`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002a8e2`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002a9c8`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CflApiNew::GetUserSid(int a1, _QWORD *a2)
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
      (void *)0x25C,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
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
             (void *)0x263,
             (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
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
      wil::details::ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8___::operator()(v27);
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
  UserSid_0 = CflApiNew::GetUserSid_0(p_Src, &hMem);
  v4 = UserSid_0;
  if ( UserSid_0 >= 0 )
  {
    std::wstring::~wstring(&Src, v16, v17);
    v20 = hMem;
    if ( hMem )
    {
      wil::details::ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8___::operator()(v27);
      *a2 = v20;
      return 0;
    }
LABEL_14:
    v4 = -2147023728;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x287,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)0x80070490LL,
      pCounta);
    wil::details::ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8___::operator()(v27);
    return v4;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x281,
    (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
    (const char *)(unsigned int)UserSid_0,
    pCounta);
  std::wstring::~wstring(&Src, v18, v19);
  wil::details::ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8___::operator()(v27);
  if ( hMem )
    CflFreeBuffer(hMem);
  return v4;
}

```

## disassembly

```asm
0x18002a7cc  mov     [rsp-8+arg_0], rbx
0x18002a7d1  mov     [rsp-8+arg_10], rsi
0x18002a7d6  push    rbp
0x18002a7d7  push    rdi
0x18002a7d8  push    r14
0x18002a7da  lea     rbp, [rsp-47h]
0x18002a7df  sub     rsp, 90h
0x18002a7e6  mov     rax, cs:__security_cookie
0x18002a7ed  xor     rax, rsp
0x18002a7f0  mov     [rbp+57h+var_18], rax
0x18002a7f4  mov     rsi, rdx
0x18002a7f7  mov     ebx, ecx
0x18002a7f9  xor     r14d, r14d
0x18002a7fc  mov     [rdx], r14
0x18002a7ff  call    IsWTSEnumerateSessionsExWPresent
0x18002a804  test    al, al
0x18002a806  jnz     short loc_18002A82A
0x18002a808  mov     rcx, [rbp+5Fh]; this
0x18002a80c  mov     ebx, 80004001h
0x18002a811  mov     r9d, ebx; char *
0x18002a814  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002a81b  mov     edx, 25Ch; void *
0x18002a820  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a825  jmp     loc_18002A8FE
0x18002a82a  mov     [rbp+57h+hMem], r14
0x18002a82e  mov     [rbp+57h+pLevel], 1
0x18002a835  mov     [rbp+57h+ppSessionInfo], r14
0x18002a839  mov     [rbp+57h+var_70], r14d
0x18002a83d  lea     rax, [rbp+57h+var_70]
0x18002a841  mov     qword ptr [rsp+0A0h+pCount], rax; int
0x18002a846  lea     r9, [rbp+57h+ppSessionInfo]; ppSessionInfo
0x18002a84a  xor     r8d, r8d; Filter
0x18002a84d  lea     rdx, [rbp+57h+pLevel]; pLevel
0x18002a851  xor     ecx, ecx; hServer
0x18002a853  call    cs:__imp_WTSEnumerateSessionsExW
0x18002a859  test    eax, eax
0x18002a85b  jnz     short loc_18002A874
0x18002a85d  mov     rcx, [rbp+5Fh]; this
0x18002a861  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002a868  mov     edx, 263h; void *
0x18002a86d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a872  jmp     short loc_18002A8C2
0x18002a874  lea     rax, [rbp+57h+ppSessionInfo]
0x18002a878  mov     [rbp+57h+var_50], rax
0x18002a87c  lea     rax, [rbp+57h+var_70]
0x18002a880  mov     [rbp+57h+var_48], rax
0x18002a884  mov     [rbp+57h+var_40], 100h
0x18002a88a  mov     ecx, r14d
0x18002a88d  mov     r8d, [rbp+57h+var_70]
0x18002a891  test    r8d, r8d
0x18002a894  jz      short loc_18002A8D6
0x18002a896  mov     rdx, [rbp+57h+ppSessionInfo]
0x18002a89a  mov     eax, ecx
0x18002a89c  imul    rdi, rax, 38h ; '8'
0x18002a8a0  cmp     [rdi+rdx+8], ebx
0x18002a8a4  jnz     short loc_18002A8CF
0x18002a8a6  mov     eax, [rdi+rdx+4]
0x18002a8aa  cmp     eax, 1
0x18002a8ad  jnz     short loc_18002A8C4
0x18002a8af  cmp     [rdi+rdx+20h], r14
0x18002a8b4  jnz     short loc_18002A8CF
0x18002a8b6  lea     rcx, [rbp+57h+var_50]
0x18002a8ba  call    wil__details__ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8_____operator__
0x18002a8bf  mov     eax, r14d
0x18002a8c2  jmp     short loc_18002A900
0x18002a8c4  test    eax, eax
0x18002a8c6  jnz     short loc_18002A8CF
0x18002a8c8  cmp     [rdi+rdx+20h], r14
0x18002a8cd  jnz     short loc_18002A924
0x18002a8cf  inc     ecx
0x18002a8d1  cmp     ecx, r8d
0x18002a8d4  jb      short loc_18002A89A
0x18002a8d6  mov     rcx, [rbp+5Fh]; this
0x18002a8da  mov     ebx, 80070490h
0x18002a8df  mov     r9d, ebx; char *
0x18002a8e2  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002a8e9  mov     edx, 287h; void *
0x18002a8ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a8f3  nop
0x18002a8f4  lea     rcx, [rbp+57h+var_50]
0x18002a8f8  call    wil__details__ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8_____operator__
0x18002a8fd  nop
0x18002a8fe  mov     eax, ebx
0x18002a900  mov     rcx, [rbp+57h+var_18]
0x18002a904  xor     rcx, rsp; StackCookie
0x18002a907  call    __security_check_cookie
0x18002a90c  lea     r11, [rsp+0A0h+var_10]
0x18002a914  mov     rbx, [r11+20h]
0x18002a918  mov     rsi, [r11+30h]
0x18002a91c  mov     rsp, r11
0x18002a91f  pop     r14
0x18002a921  pop     rdi
0x18002a922  pop     rbp
0x18002a923  retn
0x18002a924  xorps   xmm0, xmm0
0x18002a927  movups  [rbp+57h+Src], xmm0
0x18002a92b  mov     [rbp+57h+var_28], r14
0x18002a92f  mov     [rbp+57h+var_20], 7
0x18002a937  mov     word ptr [rbp+57h+Src], r14w
0x18002a93c  mov     r9, [rdi+rdx+28h]
0x18002a941  test    r9, r9
0x18002a944  jz      short loc_18002A992
0x18002a946  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002a94a  inc     rdx
0x18002a94d  cmp     [r9+rdx*2], r14w
0x18002a952  jnz     short loc_18002A94A
0x18002a954  lea     rcx, [rbp+57h+Src]; void *
0x18002a958  cmp     rdx, 7
0x18002a95c  ja      short loc_18002A979
0x18002a95e  mov     [rbp+57h+var_28], rdx
0x18002a962  lea     rbx, [rdx+rdx]
0x18002a966  mov     r8, rbx; Size
0x18002a969  mov     rdx, r9; Src
0x18002a96c  call    memmove_0
0x18002a971  mov     word ptr [rbp+rbx+57h+Src], r14w
0x18002a977  jmp     short loc_18002A97E
0x18002a979  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18002a97e  lea     rdx, asc_1800321DC; "\\"
0x18002a985  lea     rcx, [rbp+57h+Src]; Src
0x18002a989  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18002a98e  mov     rdx, [rbp+57h+ppSessionInfo]
0x18002a992  mov     rdx, [rdi+rdx+20h]; void *
0x18002a997  lea     rcx, [rbp+57h+Src]; Src
0x18002a99b  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x18002a9a0  mov     [rbp+57h+hMem], r14
0x18002a9a4  lea     rcx, [rbp+57h+Src]
0x18002a9a8  cmp     [rbp+57h+var_20], 7
0x18002a9ad  cmova   rcx, qword ptr [rbp+57h+Src]; SourceString
0x18002a9b2  lea     rdx, [rbp+57h+hMem]
0x18002a9b6  call    CflApiNew__GetUserSid_0
0x18002a9bb  mov     ebx, eax
0x18002a9bd  test    eax, eax
0x18002a9bf  jns     short loc_18002AA05
0x18002a9c1  mov     rcx, [rbp+5Fh]; this
0x18002a9c5  mov     r9d, eax; char *
0x18002a9c8  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002a9cf  mov     edx, 281h; void *
0x18002a9d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a9d9  nop
0x18002a9da  lea     rcx, [rbp+57h+Src]
0x18002a9de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a9e3  nop
0x18002a9e4  lea     rcx, [rbp+57h+var_50]
0x18002a9e8  call    wil__details__ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8_____operator__
0x18002a9ed  nop
0x18002a9ee  mov     rcx, [rbp+57h+hMem]; hMem
0x18002a9f2  test    rcx, rcx
0x18002a9f5  jz      loc_18002A8FE
0x18002a9fb  call    CflFreeBuffer
0x18002aa00  jmp     loc_18002A8FE
0x18002aa05  lea     rcx, [rbp+57h+Src]
0x18002aa09  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002aa0e  mov     rbx, [rbp+57h+hMem]
0x18002aa12  test    rbx, rbx
0x18002aa15  jz      loc_18002A8D6
0x18002aa1b  lea     rcx, [rbp+57h+var_50]
0x18002aa1f  call    wil__details__ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8_____operator__
0x18002aa24  mov     [rsi], rbx
0x18002aa27  xor     eax, eax
0x18002aa29  jmp     loc_18002A900
```
