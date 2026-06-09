# CWinHttpRequest::SetProxy(PROXY_SETTINGS_CONTAINER *)

- ea: `0x180012180`
- end: `0x180012495`
- name: `?SetProxy@CWinHttpRequest@@UEAAJPEAVPROXY_SETTINGS_CONTAINER@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CWinHttpRequest *__hidden this, struct PROXY_SETTINGS_CONTAINER *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800113c0`
- `0x180011490`
- `0x180011760`
- `0x180012180`
- `0x180073b34`
- `0x180086674`
- `0x1800959c0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a1114`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800121b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800121b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800121cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800121cb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012209`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180012209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800121d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012405`
- `WINHTTP!WinHttpSetOption` at `0x1800123fb`
- `WINHTTP!WinHttpSetOption` at `0x1800123fb`

## string_xrefs

- `0x1800121e7`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinHttpRequest::SetProxy(CWinHttpRequest *this, struct PROXY_SETTINGS_CONTAINER *a2)
{
  __int64 v4; // rbx
  void *v5; // rdi
  HANDLE CurrentThread; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  int LastError; // edi
  unsigned int v10; // r8d
  const wchar_t *v11; // r10
  wchar_t *v12; // rdx
  EVENT_LOG *v13; // rcx
  const wchar_t *v14; // rdi
  const wchar_t *v15; // r9
  signed int v16; // ebx
  DWORD v17; // eax
  __int64 Buffer; // [rsp+20h] [rbp-59h] BYREF
  const wchar_t *v20; // [rsp+28h] [rbp-51h]
  wchar_t *v21; // [rsp+30h] [rbp-49h]
  _BYTE v22[24]; // [rsp+38h] [rbp-41h] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-29h] BYREF
  __int128 v24; // [rsp+58h] [rbp-21h]
  int v25; // [rsp+68h] [rbp-11h]
  int v26; // [rsp+6Ch] [rbp-Dh]
  int v27; // [rsp+70h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  void *TokenHandle; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v30; // [rsp+F0h] [rbp+77h] BYREF

  v4 = -1;
  v30 = -1;
  v5 = (void *)**((_QWORD **)this + 1);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) && GetLastError() != 1008 )
  {
    v8 = 450;
LABEL_4:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                  v7);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    goto LABEL_8;
  }
  if ( !SetThreadToken(0, v5) )
  {
    v8 = 454;
    goto LABEL_4;
  }
  v4 = (__int64)TokenHandle;
  v30 = (__int64)TokenHandle;
  LastError = 0;
LABEL_8:
  if ( LastError < 0 )
  {
    v24 = 0;
    pExceptionObject = &ComError::`vftable';
    v25 = LastError;
    v26 = 611;
    v27 = 1;
    throw (ComError *)&pExceptionObject;
  }
  Buffer = 0;
  v21 = 0;
  v10 = *(_DWORD *)a2;
  LODWORD(Buffer) = *(_DWORD *)a2;
  v11 = (const wchar_t *)*((_QWORD *)a2 + 5);
  v20 = v11;
  v12 = (wchar_t *)((*((_QWORD *)a2 + 1) + 12LL) & -(__int64)(*(_WORD *)(*((_QWORD *)a2 + 1) + 12LL) != 0));
  v21 = v12;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_655a24a015db31ef984e42af7ef631c4_Traceguids, v10);
      v12 = v21;
      v11 = v20;
      v10 = Buffer;
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (EVENT_LOG *)&WPP_GLOBAL_Control )
    {
      v14 = L"(null)";
      if ( (*((_BYTE *)v13 + 28) & 1) != 0 )
      {
        v15 = L"(null)";
        if ( v11 )
          v15 = v11;
        WPP_SF_S(*((_QWORD *)v13 + 2), 33, &WPP_655a24a015db31ef984e42af7ef631c4_Traceguids, v15);
        v12 = v21;
        v11 = v20;
        v10 = Buffer;
        v13 = WPP_GLOBAL_Control;
      }
      if ( v13 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      {
        if ( v12 )
          v14 = v12;
        WPP_SF_S(*((_QWORD *)v13 + 2), 34, &WPP_655a24a015db31ef984e42af7ef631c4_Traceguids, v14);
        v11 = v20;
        v10 = Buffer;
        v13 = WPP_GLOBAL_Control;
      }
    }
  }
  if ( v10 == 1 )
  {
    if ( v13 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v13 + 2), 35, &WPP_655a24a015db31ef984e42af7ef631c4_Traceguids);
    if ( v4 != -1 )
      wil::details::RevertImpersonateToken((HANDLE)v4, v12);
    return 0;
  }
  if ( !v11 )
  {
    if ( v13 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v13 + 2), 36, &WPP_655a24a015db31ef984e42af7ef631c4_Traceguids);
    v16 = 0;
LABEL_48:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v30);
    return (unsigned int)v16;
  }
  if ( !v10 )
  {
    if ( v13 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v13 + 2), 37, &WPP_655a24a015db31ef984e42af7ef631c4_Traceguids);
    LODWORD(Buffer) = 3;
  }
  ScopedIoOriginThreadMarker::ScopedIoOriginThreadMarker(
    (ScopedIoOriginThreadMarker *)v22,
    *((struct IoOriginThreadTracker **)this + 4));
  if ( !WinHttpSetOption(*((HINTERNET *)this + 2), 0x26u, &Buffer, 0x18u) )
  {
    v17 = GetLastError();
    v16 = v17;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_655a24a015db31ef984e42af7ef631c4_Traceguids, v17);
    if ( v16 == 87 )
    {
      ScopedIoOriginThreadMarker::~ScopedIoOriginThreadMarker((ScopedIoOriginThreadMarker *)v22);
      v16 = -2145386433;
    }
    else
    {
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      ScopedIoOriginThreadMarker::~ScopedIoOriginThreadMarker((ScopedIoOriginThreadMarker *)v22);
    }
    goto LABEL_48;
  }
  ScopedIoOriginThreadMarker::~ScopedIoOriginThreadMarker((ScopedIoOriginThreadMarker *)v22);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v30);
  return 0;
}

```

## disassembly

```asm
0x180012180  mov     [rsp-8+arg_8], rbx
0x180012185  push    rbp
0x180012186  push    rsi
0x180012187  push    rdi
0x180012188  push    r13
0x18001218a  push    r14
0x18001218c  lea     rbp, [rsp-37h]
0x180012191  sub     rsp, 0B0h
0x180012198  mov     rsi, rdx
0x18001219b  mov     r14, rcx
0x18001219e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800121a2  mov     [rbp+57h+arg_10], rbx
0x1800121a6  mov     rax, [rcx+8]
0x1800121aa  mov     rdi, [rax]
0x1800121ad  mov     [rbp+57h+TokenHandle], 0
0x1800121b5  call    cs:__imp_GetCurrentThread
0x1800121bb  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800121bf  mov     edx, 0F01FFh; DesiredAccess
0x1800121c4  lea     r8d, [rbx+2]; OpenAsSelf
0x1800121c8  mov     rcx, rax; ThreadHandle
0x1800121cb  call    cs:__imp_OpenThreadToken
0x1800121d1  test    eax, eax
0x1800121d3  jnz     short loc_180012204
0x1800121d5  call    cs:__imp_GetLastError
0x1800121db  cmp     eax, 3F0h
0x1800121e0  jz      short loc_180012204
0x1800121e2  mov     edx, 1C2h; void *
0x1800121e7  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800121ee  mov     rcx, [rbp+5Fh]; this
0x1800121f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800121f7  mov     edi, eax
0x1800121f9  lea     rcx, [rbp+57h+TokenHandle]
0x1800121fd  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180012202  jmp     short loc_180012224
0x180012204  mov     rdx, rdi; Token
0x180012207  xor     ecx, ecx; Thread
0x180012209  call    cs:__imp_SetThreadToken
0x18001220f  test    eax, eax
0x180012211  jnz     short loc_18001221A
0x180012213  mov     edx, 1C6h
0x180012218  jmp     short loc_1800121E7
0x18001221a  mov     rbx, [rbp+57h+TokenHandle]
0x18001221e  mov     [rbp+57h+arg_10], rbx
0x180012222  xor     edi, edi
0x180012224  test    edi, edi
0x180012226  jns     short loc_18001225C
0x180012228  xorps   xmm0, xmm0
0x18001222b  movups  [rbp+57h+var_78], xmm0
0x18001222f  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180012236  mov     [rbp+57h+pExceptionObject], rax
0x18001223a  mov     [rbp+57h+var_68], edi
0x18001223d  mov     [rbp+57h+var_64], 263h
0x180012244  mov     [rbp+57h+var_60], 1
0x18001224b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180012252  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180012256  call    _CxxThrowException_0
0x18001225c  mov     [rbp+57h+Buffer], 0
0x180012264  mov     [rbp+57h+var_A0], 0
0x18001226c  mov     r8d, [rsi]
0x18001226f  mov     dword ptr [rbp+57h+Buffer], r8d
0x180012273  mov     r10, [rsi+28h]
0x180012277  mov     [rbp+57h+var_A8], r10
0x18001227b  mov     rcx, [rsi+8]
0x18001227f  add     rcx, 0Ch
0x180012283  movzx   eax, word ptr [rcx]
0x180012286  neg     ax
0x180012289  sbb     rdx, rdx
0x18001228c  and     rdx, rcx
0x18001228f  mov     [rbp+57h+var_A0], rdx
0x180012293  lea     rsi, WPP_GLOBAL_Control
0x18001229a  lea     r13, WPP_655a24a015db31ef984e42af7ef631c4_Traceguids
0x1800122a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122a8  cmp     rcx, rsi
0x1800122ab  jz      loc_180012353
0x1800122b1  test    byte ptr [rcx+1Ch], 1
0x1800122b5  jz      short loc_1800122DE
0x1800122b7  mov     edx, 20h ; ' '
0x1800122bc  mov     r9d, r8d
0x1800122bf  mov     r8, r13
0x1800122c2  mov     rcx, [rcx+10h]
0x1800122c6  call    WPP_SF_d
0x1800122cb  mov     rdx, [rbp+57h+var_A0]
0x1800122cf  mov     r10, [rbp+57h+var_A8]
0x1800122d3  mov     r8d, dword ptr [rbp+57h+Buffer]
0x1800122d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122de  cmp     rcx, rsi
0x1800122e1  jz      short loc_180012353
0x1800122e3  lea     rdi, aNull_3; "(null)"
0x1800122ea  test    byte ptr [rcx+1Ch], 1
0x1800122ee  jz      short loc_18001231E
0x1800122f0  mov     r9, rdi
0x1800122f3  test    r10, r10
0x1800122f6  cmovnz  r9, r10
0x1800122fa  mov     edx, 21h ; '!'
0x1800122ff  mov     r8, r13
0x180012302  mov     rcx, [rcx+10h]
0x180012306  call    WPP_SF_S
0x18001230b  mov     rdx, [rbp+57h+var_A0]
0x18001230f  mov     r10, [rbp+57h+var_A8]
0x180012313  mov     r8d, dword ptr [rbp+57h+Buffer]
0x180012317  mov     rcx, cs:WPP_GLOBAL_Control
0x18001231e  cmp     rcx, rsi
0x180012321  jz      short loc_180012353
0x180012323  test    byte ptr [rcx+1Ch], 1
0x180012327  jz      short loc_180012353
0x180012329  test    rdx, rdx
0x18001232c  cmovnz  rdi, rdx
0x180012330  mov     edx, 22h ; '"'
0x180012335  mov     r9, rdi
0x180012338  mov     r8, r13
0x18001233b  mov     rcx, [rcx+10h]
0x18001233f  call    WPP_SF_S
0x180012344  mov     r10, [rbp+57h+var_A8]
0x180012348  mov     r8d, dword ptr [rbp+57h+Buffer]
0x18001234c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012353  cmp     r8d, 1
0x180012357  jnz     short loc_18001238C
0x180012359  cmp     rcx, rsi
0x18001235c  jz      short loc_180012375
0x18001235e  test    [rcx+1Ch], r8b
0x180012362  jz      short loc_180012375
0x180012364  lea     edx, [r8+22h]
0x180012368  mov     r8, r13
0x18001236b  mov     rcx, [rcx+10h]
0x18001236f  call    WPP_SF_
0x180012374  nop
0x180012375  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180012379  jz      loc_18001247C
0x18001237f  mov     rcx, rbx; Token
0x180012382  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x180012387  jmp     loc_18001247C
0x18001238c  test    r10, r10
0x18001238f  jnz     short loc_1800123B3
0x180012391  cmp     rcx, rsi
0x180012394  jz      short loc_1800123AC
0x180012396  test    byte ptr [rcx+1Ch], 1
0x18001239a  jz      short loc_1800123AC
0x18001239c  lea     edx, [r10+24h]
0x1800123a0  mov     r8, r13
0x1800123a3  mov     rcx, [rcx+10h]
0x1800123a7  call    WPP_SF_
0x1800123ac  xor     ebx, ebx
0x1800123ae  jmp     loc_18001245C
0x1800123b3  test    r8d, r8d
0x1800123b6  jnz     short loc_1800123DA
0x1800123b8  cmp     rcx, rsi
0x1800123bb  jz      short loc_1800123D3
0x1800123bd  test    byte ptr [rcx+1Ch], 1
0x1800123c1  jz      short loc_1800123D3
0x1800123c3  lea     edx, [r8+25h]
0x1800123c7  mov     r8, r13
0x1800123ca  mov     rcx, [rcx+10h]
0x1800123ce  call    WPP_SF_
0x1800123d3  mov     dword ptr [rbp+57h+Buffer], 3
0x1800123da  mov     rdx, [r14+20h]; struct IoOriginThreadTracker *
0x1800123de  lea     rcx, [rbp+57h+var_98]; this
0x1800123e2  call    ??0ScopedIoOriginThreadMarker@@QEAA@PEAVIoOriginThreadTracker@@@Z; ScopedIoOriginThreadMarker::ScopedIoOriginThreadMarker(IoOriginThreadTracker *)
0x1800123e7  mov     r9d, 18h; dwBufferLength
0x1800123ed  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800123f1  lea     edi, [r9+0Eh]
0x1800123f5  mov     edx, edi; dwOption
0x1800123f7  mov     rcx, [r14+10h]; hInternet
0x1800123fb  call    cs:__imp_WinHttpSetOption
0x180012401  test    eax, eax
0x180012403  jnz     short loc_180012469
0x180012405  call    cs:__imp_GetLastError
0x18001240b  mov     ebx, eax
0x18001240d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012414  cmp     rcx, rsi
0x180012417  jz      short loc_180012430
0x180012419  test    byte ptr [rcx+1Ch], 2
0x18001241d  jz      short loc_180012430
0x18001241f  mov     edx, edi
0x180012421  mov     r9d, eax
0x180012424  mov     r8, r13
0x180012427  mov     rcx, [rcx+10h]
0x18001242b  call    WPP_SF_d
0x180012430  cmp     ebx, 57h ; 'W'
0x180012433  jnz     short loc_180012445
0x180012435  lea     rcx, [rbp+57h+var_98]; this
0x180012439  call    ??1ScopedIoOriginThreadMarker@@UEAA@XZ; ScopedIoOriginThreadMarker::~ScopedIoOriginThreadMarker(void)
0x18001243e  mov     ebx, 8020003Fh
0x180012443  jmp     short loc_18001245C
0x180012445  test    ebx, ebx
0x180012447  jle     short loc_180012452
0x180012449  movzx   ebx, bx
0x18001244c  or      ebx, 80070000h
0x180012452  lea     rcx, [rbp+57h+var_98]; this
0x180012456  call    ??1ScopedIoOriginThreadMarker@@UEAA@XZ; ScopedIoOriginThreadMarker::~ScopedIoOriginThreadMarker(void)
0x18001245b  nop
0x18001245c  lea     rcx, [rbp+57h+arg_10]
0x180012460  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180012465  mov     eax, ebx
0x180012467  jmp     short loc_18001247E
0x180012469  lea     rcx, [rbp+57h+var_98]; this
0x18001246d  call    ??1ScopedIoOriginThreadMarker@@UEAA@XZ; ScopedIoOriginThreadMarker::~ScopedIoOriginThreadMarker(void)
0x180012472  nop
0x180012473  lea     rcx, [rbp+57h+arg_10]
0x180012477  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001247c  xor     eax, eax
0x18001247e  mov     rbx, [rsp+0D0h+arg_8]
0x180012486  add     rsp, 0B0h
0x18001248d  pop     r14
0x18001248f  pop     r13
0x180012491  pop     rdi
0x180012492  pop     rsi
0x180012493  pop     rbp
0x180012494  retn
```
