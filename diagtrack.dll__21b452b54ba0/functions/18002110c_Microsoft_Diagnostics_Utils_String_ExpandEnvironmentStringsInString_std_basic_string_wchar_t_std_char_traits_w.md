# Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,bool,void *)

- ea: `0x18002110c`
- end: `0x18002141b`
- name: `?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z`
- size: `783`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `101`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001dc38`
- `0x180020db8`
- `0x1800331bc`
- `0x180048cac`
- `0x1800629d0`
- `0x18006995c`
- `0x18006b654`
- `0x180086d00`
- `0x180093f24`
- `0x18009a250`
- `0x1800bad40`
- `0x1800c33e0`
- `0x1800c4b14`
- `0x1800c53b4`
- `0x1800c5d5c`
- `0x1800c5ee4`
- `0x1800c6ef4`
- `0x1800c708c`
- `0x1800c7468`
- `0x1800df720`
- `0x1800e02f8`
- `0x18010711c`
- `0x180124444`
- `0x18013ddf8`
- `0x18013f76c`
- `0x18013fa24`
- `0x180140a5c`
- `0x1801418d8`
- `0x18014e0b4`
- `0x18014e81c`
- `0x180150580`
- `0x180156958`
- `0x18015e224`
- `0x18015f3f0`
- `0x1801606ac`
- `0x1801618f4`
- `0x180169c48`
- `0x18018b898`
- `0x18018bba4`
- `0x18018c9e4`
- `0x18018cce4`
- `0x18019a6a0`
- `0x1801aa710`
- `0x1801ad074`
- `0x1801aee34`
- `0x1801b0e68`
- `0x1801b0f48`
- `0x1801b15cc`
- `0x1801b5e6c`
- `0x1801b6884`

## callees

- `0x1800202a4`
- `0x180020e6c`
- `0x18002110c`
- `0x18002abec`
- `0x18002b770`
- `0x18002b9c0`
- `0x18002cb04`
- `0x18002df00`
- `0x180064e34`
- `0x18008a4ec`
- `0x1800bc658`
- `0x180107fc4`
- `0x1801b2084`
- `0x1801cd84c`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800211f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800211e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800211e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800211cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800211cc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021350`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021394`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021350`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180021394`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x180021275`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x180021275`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800211b7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800211b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(
        _QWORD *lpSrc,
        char a2,
        void *a3)
{
  int v5; // eax
  BOOL v6; // eax
  const char *v7; // r9
  wil::details::in1diag3 *v8; // rcx
  __int64 v9; // rdx
  HANDLE CurrentThread; // rax
  unsigned int i; // edi
  WCHAR *v12; // r8
  const WCHAR *v13; // rdx
  const wchar_t *v14; // rcx
  _QWORD *v15; // rcx
  const char *v16; // r9
  WCHAR *v17; // rdx
  const WCHAR *v18; // rcx
  DWORD v19; // eax
  const char *v20; // r9
  WCHAR *v21; // rdx
  const WCHAR *v22; // rcx
  const char *v23; // r9
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-60h]
  void *TokenHandle[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v27[2]; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR lpDest[2]; // [rsp+50h] [rbp-30h] BYREF
  DWORD dwSize[2]; // [rsp+60h] [rbp-20h]
  unsigned __int64 v30; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( a2 )
  {
    *(_OWORD *)v27 = *(_OWORD *)&off_180383870;
    *(_OWORD *)lpDest = *(_OWORD *)&off_180383880;
    v5 = Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(lpSrc);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x343,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
        (const char *)(unsigned int)v5,
        TokenType);
  }
  TokenHandle[0] = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    TokenHandle,
    0);
  if ( a3 )
  {
    v6 = DuplicateTokenEx(a3, 0xEu, 0, SecurityIdentification, TokenImpersonation, TokenHandle);
    v8 = retaddr;
    if ( v6 )
      goto LABEL_11;
    v9 = 848;
    goto LABEL_10;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, TokenHandle) && GetLastError() != 1008 )
  {
    v9 = 857;
    v8 = retaddr;
LABEL_10:
    wil::details::in1diag3::_Log_GetLastError(
      v8,
      (void *)v9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
      v7);
  }
LABEL_11:
  if ( (unsigned __int64)TokenHandle[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    std::wstring::wstring(lpDest, 260, 0);
    for ( i = 260; ; std::wstring::resize(lpDest, i) )
    {
      v12 = (WCHAR *)lpDest;
      if ( v30 > 7 )
        v12 = lpDest[0];
      v13 = lpSrc[3] <= 7u ? (const WCHAR *)lpSrc : (const WCHAR *)*lpSrc;
      if ( ExpandEnvironmentStringsForUserW(TokenHandle[0], v13, v12, dwSize[0]) )
        break;
      if ( i >= 0x410 )
        goto LABEL_27;
      i *= 2;
    }
    v27[0] = 0;
    v14 = (const wchar_t *)lpDest;
    if ( v30 > 7 )
      v14 = lpDest[0];
    if ( (int)StringCchLengthW(v14, i, v27) >= 0 )
    {
      std::wstring::resize(lpDest, LODWORD(v27[0]));
      std::wstring::operator=(lpSrc, lpDest);
      std::wstring::_Tidy_deallocate(lpDest);
      goto LABEL_25;
    }
LABEL_27:
    std::wstring::assign(lpSrc, &Src);
    goto LABEL_46;
  }
  if ( GetLastError() != 1008 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x384,
      (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
      v16);
LABEL_25:
  if ( lpSrc[3] <= 7u )
    v15 = lpSrc;
  else
    v15 = (_QWORD *)*lpSrc;
  if ( std::_Traits_find_ch<std::char_traits<wchar_t>>(v15, lpSrc[2], 0, 37) != -1 )
  {
    std::wstring::wstring(lpDest, 260, 0);
    v17 = (WCHAR *)lpDest;
    if ( v30 > 7 )
      v17 = lpDest[0];
    if ( lpSrc[3] <= 7u )
      v18 = (const WCHAR *)lpSrc;
    else
      v18 = (const WCHAR *)*lpSrc;
    v19 = ExpandEnvironmentStringsW(v18, v17, dwSize[0]);
    if ( !v19 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x390,
        (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
        v20);
    if ( (unsigned __int64)v19 >= *(_QWORD *)dwSize )
    {
      std::wstring::resize(lpDest, v19);
      v21 = (WCHAR *)lpDest;
      if ( v30 > 7 )
        v21 = lpDest[0];
      if ( lpSrc[3] <= 7u )
        v22 = (const WCHAR *)lpSrc;
      else
        v22 = (const WCHAR *)*lpSrc;
      v19 = ExpandEnvironmentStringsW(v22, v21, dwSize[0]);
      if ( !v19 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x397,
          (unsigned int)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
          v23);
    }
    std::wstring::resize(lpDest, v19 - 1);
    std::wstring::operator=(lpSrc, lpDest);
LABEL_46:
    std::wstring::_Tidy_deallocate(lpDest);
  }
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
}

```

## disassembly

```asm
0x18002110c  mov     [rsp-18h+arg_8], rbx
0x180021111  push    rbp
0x180021112  push    rdi
0x180021113  push    r14
0x180021115  mov     rbp, rsp
0x180021118  sub     rsp, 80h
0x18002111f  mov     rax, cs:__security_cookie
0x180021126  xor     rax, rsp
0x180021129  mov     [rbp+var_10], rax
0x18002112d  mov     rdi, r8
0x180021130  mov     rbx, rcx
0x180021133  lea     r14, aOnecoreBaseTel_72; "onecore\\base\\telemetry\\utc\\include"...
0x18002113a  test    dl, dl
0x18002113c  jz      short loc_18002117E
0x18002113e  movups  xmm0, xmmword ptr cs:off_180383870; "%DiagtrackStorageRoot%"
0x180021145  movdqu  xmmword ptr [rbp+var_40], xmm0
0x18002114a  movups  xmm1, xmmword ptr cs:off_180383880; "%ProgramData%\\Microsoft\\Diagnosis"
0x180021151  movdqu  xmmword ptr [rbp+lpDest], xmm1
0x180021156  xor     r9d, r9d
0x180021159  lea     r8, [rbp+var_40]
0x18002115d  lea     rdx, [rbp+lpDest]
0x180021161  call    ??$ReplaceAllImpl@_W@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1_N@Z; Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(std::wstring &,std::wstring_view,std::wstring_view,bool)
0x180021166  mov     rcx, [rbp+18h]; this
0x18002116a  test    eax, eax
0x18002116c  jns     short loc_18002117E
0x18002116e  mov     r9d, eax; char *
0x180021171  mov     r8, r14; unsigned int
0x180021174  mov     edx, 343h; void *
0x180021179  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002117e  mov     [rbp+TokenHandle], 0
0x180021186  xor     edx, edx
0x180021188  lea     rcx, [rbp+TokenHandle]
0x18002118c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180021191  test    rdi, rdi
0x180021194  jz      short loc_1800211CC
0x180021196  lea     rax, [rbp+TokenHandle]
0x18002119a  mov     [rsp+80h+phNewToken], rax; phNewToken
0x18002119f  mov     [rsp+80h+TokenType], 2; TokenType
0x1800211a7  mov     r9d, 1; ImpersonationLevel
0x1800211ad  xor     r8d, r8d; lpTokenAttributes
0x1800211b0  lea     edx, [r9+0Dh]; dwDesiredAccess
0x1800211b4  mov     rcx, rdi; hExistingToken
0x1800211b7  call    cs:__imp_DuplicateTokenEx
0x1800211bd  mov     rcx, [rbp+18h]
0x1800211c1  test    eax, eax
0x1800211c3  jnz     short loc_18002120D
0x1800211c5  mov     edx, 350h
0x1800211ca  jmp     short loc_180021205
0x1800211cc  call    cs:__imp_GetCurrentThread
0x1800211d2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800211d6  mov     edx, 0Eh; DesiredAccess
0x1800211db  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800211df  mov     rcx, rax; ThreadHandle
0x1800211e2  call    cs:__imp_OpenThreadToken
0x1800211e8  test    eax, eax
0x1800211ea  jnz     short loc_18002120D
0x1800211ec  mov     rdi, [rbp+18h]
0x1800211f0  call    cs:__imp_GetLastError
0x1800211f6  cmp     eax, 3F0h
0x1800211fb  jz      short loc_18002120D
0x1800211fd  mov     edx, 359h; void *
0x180021202  mov     rcx, rdi; this
0x180021205  mov     r8, r14; unsigned int
0x180021208  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002120d  mov     rax, [rbp+TokenHandle]
0x180021211  dec     rax
0x180021214  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021218  ja      loc_1800212E7
0x18002121e  xor     r8d, r8d
0x180021221  mov     edx, 104h
0x180021226  lea     rcx, [rbp+lpDest]
0x18002122a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18002122f  nop
0x180021230  mov     edi, 104h
0x180021235  jmp     short loc_180021250
0x180021237  cmp     edi, 410h
0x18002123d  jnb     loc_1800212D2
0x180021243  add     edi, edi
0x180021245  mov     edx, edi
0x180021247  lea     rcx, [rbp+lpDest]
0x18002124b  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180021250  lea     r8, [rbp+lpDest]
0x180021254  cmp     [rbp+var_18], 7
0x180021259  cmova   r8, [rbp+lpDest]; lpDest
0x18002125e  cmp     qword ptr [rbx+18h], 7
0x180021263  jbe     short loc_18002126A
0x180021265  mov     rdx, [rbx]
0x180021268  jmp     short loc_18002126D
0x18002126a  mov     rdx, rbx; lpSrc
0x18002126d  mov     r9d, [rbp+dwSize]; dwSize
0x180021271  mov     rcx, [rbp+TokenHandle]; hToken
0x180021275  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x18002127b  test    eax, eax
0x18002127d  jz      short loc_180021237
0x18002127f  mov     [rbp+var_40], 0
0x180021287  lea     rcx, [rbp+lpDest]
0x18002128b  cmp     [rbp+var_18], 7
0x180021290  cmova   rcx, [rbp+lpDest]; wchar_t *
0x180021295  mov     edx, edi; unsigned __int64
0x180021297  lea     r8, [rbp+var_40]; unsigned __int64 *
0x18002129b  call    ?StringCchLengthW@@YAJPEB_W_KPEA_K@Z; StringCchLengthW(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x1800212a0  test    eax, eax
0x1800212a2  js      short loc_1800212D2
0x1800212a4  mov     edx, dword ptr [rbp+var_40]
0x1800212a7  lea     rcx, [rbp+lpDest]
0x1800212ab  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800212b0  lea     rdx, [rbp+lpDest]
0x1800212b4  mov     rcx, rbx
0x1800212b7  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800212bc  nop
0x1800212bd  lea     rcx, [rbp+lpDest]
0x1800212c1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800212c6  cmp     qword ptr [rbx+18h], 7
0x1800212cb  jbe     short loc_1800212FE
0x1800212cd  mov     rcx, [rbx]
0x1800212d0  jmp     short loc_180021301
0x1800212d2  lea     rdx, Src
0x1800212d9  mov     rcx, rbx
0x1800212dc  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800212e1  nop
0x1800212e2  jmp     loc_1800213BB
0x1800212e7  mov     rdi, [rbp+18h]
0x1800212eb  call    cs:__imp_GetLastError
0x1800212f1  cmp     eax, 3F0h
0x1800212f6  jnz     loc_1800213FC
0x1800212fc  jmp     short loc_1800212C6
0x1800212fe  mov     rcx, rbx
0x180021301  mov     r9d, 25h ; '%'
0x180021307  xor     r8d, r8d
0x18002130a  mov     rdx, [rbx+10h]
0x18002130e  call    ??$_Traits_find_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_find_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x180021313  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021317  jz      loc_1800213C5
0x18002131d  xor     r8d, r8d
0x180021320  mov     edx, 104h
0x180021325  lea     rcx, [rbp+lpDest]
0x180021329  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18002132e  nop
0x18002132f  lea     rdx, [rbp+lpDest]
0x180021333  cmp     [rbp+var_18], 7
0x180021338  cmova   rdx, [rbp+lpDest]; lpDst
0x18002133d  cmp     qword ptr [rbx+18h], 7
0x180021342  jbe     short loc_180021349
0x180021344  mov     rcx, [rbx]
0x180021347  jmp     short loc_18002134C
0x180021349  mov     rcx, rbx; lpSrc
0x18002134c  mov     r8d, [rbp+dwSize]; nSize
0x180021350  call    cs:__imp_ExpandEnvironmentStringsW
0x180021356  mov     rcx, [rbp+18h]; this
0x18002135a  test    eax, eax
0x18002135c  jz      loc_18002140D
0x180021362  mov     edx, eax
0x180021364  cmp     rdx, qword ptr [rbp+dwSize]
0x180021368  jb      short loc_1800213A2
0x18002136a  lea     rcx, [rbp+lpDest]
0x18002136e  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180021373  lea     rdx, [rbp+lpDest]
0x180021377  cmp     [rbp+var_18], 7
0x18002137c  cmova   rdx, [rbp+lpDest]; lpDst
0x180021381  cmp     qword ptr [rbx+18h], 7
0x180021386  jbe     short loc_18002138D
0x180021388  mov     rcx, [rbx]
0x18002138b  jmp     short loc_180021390
0x18002138d  mov     rcx, rbx; lpSrc
0x180021390  mov     r8d, [rbp+dwSize]; nSize
0x180021394  call    cs:__imp_ExpandEnvironmentStringsW
0x18002139a  mov     rcx, [rbp+18h]; this
0x18002139e  test    eax, eax
0x1800213a0  jz      short loc_1800213EE
0x1800213a2  lea     edx, [rax-1]
0x1800213a5  lea     rcx, [rbp+lpDest]
0x1800213a9  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800213ae  lea     rdx, [rbp+lpDest]
0x1800213b2  mov     rcx, rbx
0x1800213b5  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800213ba  nop
0x1800213bb  lea     rcx, [rbp+lpDest]
0x1800213bf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800213c4  nop
0x1800213c5  lea     rcx, [rbp+TokenHandle]
0x1800213c9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800213ce  mov     rcx, [rbp+var_10]
0x1800213d2  xor     rcx, rsp; StackCookie
0x1800213d5  call    __security_check_cookie
0x1800213da  mov     rbx, [rsp+80h+arg_8]
0x1800213e2  add     rsp, 80h
0x1800213e9  pop     r14
0x1800213eb  pop     rdi
0x1800213ec  pop     rbp
0x1800213ed  retn
0x1800213ee  mov     r8, r14; unsigned int
0x1800213f1  mov     edx, 397h; void *
0x1800213f6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800213fc  mov     r8, r14; unsigned int
0x1800213ff  mov     edx, 384h; void *
0x180021404  mov     rcx, rdi; this
0x180021407  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002140d  mov     r8, r14; unsigned int
0x180021410  mov     edx, 390h; void *
0x180021415  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
