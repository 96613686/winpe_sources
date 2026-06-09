# CACHED_AUTOPROXY::LookupProxy(LockableHINTERNET &,ushort const *,TokenHandle const &,bool,_WINHTTP_PROXY_INFO &)

- ea: `0x1800084a0`
- end: `0x180008b63`
- name: `?LookupProxy@CACHED_AUTOPROXY@@SAXAEAVLockableHINTERNET@@PEBGAEBVTokenHandle@@_NAEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `1731`
- prototype: `void __fastcall(struct LockableHINTERNET *, const unsigned __int16 *, const struct TokenHandle *, char, struct _WINHTTP_PROXY_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e315c`

## callees

- `0x1800084a0`
- `0x180008b70`
- `0x18000db20`
- `0x18000f5f0`
- `0x180032db0`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a1114`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800085a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800085a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000864d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000876f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000864d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000876f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008643`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008643`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000894b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008974`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008a08`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008a85`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008b3d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000894b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008974`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008a08`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008a85`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180008b3d`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180008699`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180008699`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CACHED_AUTOPROXY::LookupProxy(
        struct LockableHINTERNET *a1,
        const unsigned __int16 *a2,
        const struct TokenHandle *a3,
        char a4,
        struct _WINHTTP_PROXY_INFO *a5)
{
  LPWSTR v9; // r14
  EVENT_LOG *v10; // rcx
  int v11; // ebx
  _DWORD *v12; // rax
  signed int LastError; // eax
  EVENT_LOG *v14; // rcx
  LPWSTR lpszAutoConfigUrl; // rax
  DWORD v16; // eax
  unsigned int ProxyForUrl; // eax
  int v18; // ebx
  EVENT_LOG *v19; // rcx
  LPWSTR lpszProxyBypass; // rax
  LPWSTR lpszProxy; // rcx
  EVENT_LOG *v22; // r10
  __int64 v23; // r9
  unsigned __int16 *v24; // rax
  int v25; // edx
  int v26; // ecx
  unsigned __int16 *v27; // rax
  int v28; // edx
  int v29; // ecx
  __int64 v30; // r9
  unsigned __int16 *v31; // rax
  int v32; // edx
  int v33; // ecx
  unsigned __int16 *v34; // rax
  int v35; // edx
  int v36; // ecx
  const wchar_t *v37; // rbx
  const wchar_t *v38; // r9
  __int128 v39; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v40; // [rsp+30h] [rbp-D0h]
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+40h] [rbp-C0h] BYREF
  void **v42; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+68h] [rbp-98h]
  __int64 v44; // [rsp+78h] [rbp-88h]
  _DWORD *v45; // [rsp+80h] [rbp-80h]
  __int64 v46; // [rsp+88h] [rbp-78h]
  __int64 *v47; // [rsp+90h] [rbp-70h]
  void **pExceptionObject; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v49; // [rsp+C8h] [rbp-38h]
  int v50; // [rsp+D8h] [rbp-28h]
  int v51; // [rsp+DCh] [rbp-24h]
  int v52; // [rsp+E0h] [rbp-20h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_12cba19daead377fec43f4905df69b93_Traceguids, a2);
  v9 = 0;
  *(_OWORD *)a5 = 0;
  *((_QWORD *)a5 + 2) = 0;
  v39 = 0;
  v40 = 0;
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  if ( a4 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_12cba19daead377fec43f4905df69b93_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    *(_QWORD *)&v39 = 0x300000001LL;
    HIDWORD(v40) = 1;
    goto LABEL_41;
  }
  CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&v42);
  LOBYTE(v43) = 0;
  *((_QWORD *)&v43 + 1) = *(_QWORD *)a3;
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL));
  v11 = 0;
  v44 = 0;
  v12 = HeapAlloc(hBitsHeap, 8u, 4u);
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
    v49 = 0;
    pExceptionObject = &ComError::`vftable';
    v50 = -2147024882;
    v51 = 0;
    v52 = 1;
    throw (ComError *)&pExceptionObject;
  }
  *v12 = 1;
  v45 = v12;
  v46 = 0;
  _InterlockedIncrement(&dword_180145058);
  v47 = &GenericStringHandle<unsigned short>::s_EmptyString;
  if ( !(_BYTE)v43 )
  {
    if ( !ImpersonateLoggedOnUser(**((HANDLE **)&v43 + 1)) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v49 = 0;
      pExceptionObject = &ComError::`vftable';
      v50 = LastError;
      v51 = 0;
      v52 = 1;
      throw (ComError *)&pExceptionObject;
    }
    LOBYTE(v43) = 1;
  }
  if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_12cba19daead377fec43f4905df69b93_Traceguids);
      v14 = WPP_GLOBAL_Control;
    }
    if ( pProxyConfig.fAutoDetect )
    {
      if ( v14 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)v14 + 2), 13, WPP_12cba19daead377fec43f4905df69b93_Traceguids);
        v14 = WPP_GLOBAL_Control;
      }
      *(_QWORD *)&v39 = 0x300000001LL;
      v11 = 1;
    }
    lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
    if ( !pProxyConfig.lpszAutoConfigUrl )
      goto LABEL_39;
    if ( v14 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
    {
      WPP_SF_S(
        *((_QWORD *)v14 + 2),
        14,
        WPP_12cba19daead377fec43f4905df69b93_Traceguids,
        pProxyConfig.lpszAutoConfigUrl);
      lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
    }
    LODWORD(v39) = v39 | 2;
    *((_QWORD *)&v39 + 1) = lpszAutoConfigUrl;
    v9 = lpszAutoConfigUrl;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_12cba19daead377fec43f4905df69b93_Traceguids, v16);
    }
    *(_QWORD *)&v39 = 0x300000001LL;
  }
  v11 = 1;
LABEL_39:
  CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&v42);
  HIDWORD(v40) = 1;
  if ( !v11 )
    goto LABEL_54;
  v10 = WPP_GLOBAL_Control;
LABEL_41:
  if ( v10 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)v10 + 2), 16, WPP_12cba19daead377fec43f4905df69b93_Traceguids);
  CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)&pExceptionObject, a3);
  LODWORD(v39) = v39 | 0x400000;
  ProxyForUrl = CACHED_AUTOPROXY::GetProxyForUrlEx(a1, a2, (struct _WINHTTP_AUTOPROXY_OPTIONS *)&v39, a5);
  v18 = ProxyForUrl;
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_12cba19daead377fec43f4905df69b93_Traceguids, ProxyForUrl);
    v19 = WPP_GLOBAL_Control;
  }
  if ( v18 == -2147012879 )
  {
    if ( v19 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v19 + 2), 18, WPP_12cba19daead377fec43f4905df69b93_Traceguids);
    v43 = 0;
    v42 = &ComError::`vftable';
    v44 = 0x8B80004004LL;
    LODWORD(v45) = 1;
    throw (ComError *)&v42;
  }
  CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&pExceptionObject);
  if ( v18 >= 0 )
  {
    lpszProxyBypass = pProxyConfig.lpszProxyBypass;
    lpszProxy = pProxyConfig.lpszProxy;
    goto LABEL_62;
  }
LABEL_54:
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_12cba19daead377fec43f4905df69b93_Traceguids);
    v22 = WPP_GLOBAL_Control;
  }
  lpszProxy = pProxyConfig.lpszProxy;
  if ( !pProxyConfig.lpszProxy )
    goto LABEL_65;
  if ( v22 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 1) != 0 )
  {
    WPP_SF_S(*((_QWORD *)v22 + 2), 20, WPP_12cba19daead377fec43f4905df69b93_Traceguids, pProxyConfig.lpszProxy);
    lpszProxy = pProxyConfig.lpszProxy;
  }
  *(_DWORD *)a5 = 3;
  *((_QWORD *)a5 + 1) = lpszProxy;
  lpszProxyBypass = pProxyConfig.lpszProxyBypass;
  *((_QWORD *)a5 + 2) = pProxyConfig.lpszProxyBypass;
LABEL_62:
  if ( !lpszProxy || *((LPWSTR *)a5 + 1) == lpszProxy )
  {
    v22 = WPP_GLOBAL_Control;
    goto LABEL_66;
  }
  GlobalFree(lpszProxy);
  pProxyConfig.lpszProxy = 0;
  v22 = WPP_GLOBAL_Control;
LABEL_65:
  lpszProxyBypass = pProxyConfig.lpszProxyBypass;
LABEL_66:
  if ( lpszProxyBypass && *((LPWSTR *)a5 + 2) != lpszProxyBypass )
  {
    GlobalFree(lpszProxyBypass);
    pProxyConfig.lpszProxyBypass = 0;
    v22 = WPP_GLOBAL_Control;
  }
  v23 = *((_QWORD *)a5 + 1);
  if ( v23 )
  {
    v24 = (unsigned __int16 *)*((_QWORD *)a5 + 1);
    do
    {
      v25 = *(unsigned __int16 *)((char *)asc_180145038 + (_QWORD)v24 - v23);
      v26 = *v24 - v25;
      if ( v26 )
        break;
      ++v24;
    }
    while ( v25 );
    if ( !v26 )
      goto LABEL_79;
    v27 = (unsigned __int16 *)*((_QWORD *)a5 + 1);
    do
    {
      v28 = *(unsigned __int16 *)((char *)asc_180145030 + (_QWORD)v27 - v23);
      v29 = *v27 - v28;
      if ( v29 )
        break;
      ++v27;
    }
    while ( v28 );
    if ( !v29 )
    {
LABEL_79:
      if ( v22 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)v22 + 2), 21, WPP_12cba19daead377fec43f4905df69b93_Traceguids, v23);
      GlobalFree(*((HGLOBAL *)a5 + 1));
      *((_QWORD *)a5 + 1) = 0;
      v22 = WPP_GLOBAL_Control;
    }
  }
  v30 = *((_QWORD *)a5 + 2);
  if ( v30 )
  {
    v31 = (unsigned __int16 *)*((_QWORD *)a5 + 2);
    do
    {
      v32 = *(unsigned __int16 *)((char *)asc_180145038 + (_QWORD)v31 - v30);
      v33 = *v31 - v32;
      if ( v33 )
        break;
      ++v31;
    }
    while ( v32 );
    if ( !v33 )
      goto LABEL_92;
    v34 = (unsigned __int16 *)*((_QWORD *)a5 + 2);
    do
    {
      v35 = *(unsigned __int16 *)((char *)asc_180145030 + (_QWORD)v34 - v30);
      v36 = *v34 - v35;
      if ( v36 )
        break;
      ++v34;
    }
    while ( v35 );
    if ( !v36 )
    {
LABEL_92:
      if ( v22 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)v22 + 2), 22, WPP_12cba19daead377fec43f4905df69b93_Traceguids, v30);
      GlobalFree(*((HGLOBAL *)a5 + 2));
      *((_QWORD *)a5 + 2) = 0;
      v22 = WPP_GLOBAL_Control;
    }
  }
  if ( v22 != (EVENT_LOG *)&WPP_GLOBAL_Control )
  {
    v37 = L"(null)";
    if ( (*((_BYTE *)v22 + 28) & 1) != 0 )
    {
      v38 = L"(null)";
      if ( *((_QWORD *)a5 + 1) )
        v38 = (const wchar_t *)*((_QWORD *)a5 + 1);
      WPP_SF_S(*((_QWORD *)v22 + 2), 23, WPP_12cba19daead377fec43f4905df69b93_Traceguids, v38);
      v22 = WPP_GLOBAL_Control;
    }
    if ( v22 != (EVENT_LOG *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v22 + 28) & 1) != 0 )
      {
        if ( *((_QWORD *)a5 + 2) )
          v37 = (const wchar_t *)*((_QWORD *)a5 + 2);
        WPP_SF_S(*((_QWORD *)v22 + 2), 24, WPP_12cba19daead377fec43f4905df69b93_Traceguids, v37);
        v22 = WPP_GLOBAL_Control;
      }
      if ( v22 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v22 + 2), 25, WPP_12cba19daead377fec43f4905df69b93_Traceguids, *(unsigned int *)a5);
    }
  }
  if ( v9 )
    GlobalFree(v9);
}

```

## disassembly

```asm
0x1800084a0  push    rbp
0x1800084a2  push    rbx
0x1800084a3  push    rsi
0x1800084a4  push    rdi
0x1800084a5  push    r12
0x1800084a7  push    r13
0x1800084a9  push    r14
0x1800084ab  push    r15
0x1800084ad  lea     rbp, [rsp-28h]
0x1800084b2  sub     rsp, 128h
0x1800084b9  movzx   ebx, r9b
0x1800084bd  mov     rsi, r8
0x1800084c0  mov     r15, rdx
0x1800084c3  mov     r12, rcx
0x1800084c6  lea     r13, WPP_GLOBAL_Control
0x1800084cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084d4  cmp     rcx, r13
0x1800084d7  jz      short loc_1800084F7
0x1800084d9  test    byte ptr [rcx+1Ch], 1
0x1800084dd  jz      short loc_1800084F7
0x1800084df  mov     edx, 0Ah
0x1800084e4  mov     r9, r15
0x1800084e7  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x1800084ee  mov     rcx, [rcx+10h]
0x1800084f2  call    WPP_SF_S
0x1800084f7  xor     r14d, r14d
0x1800084fa  xorps   xmm0, xmm0
0x1800084fd  xor     eax, eax
0x1800084ff  mov     rdi, [rbp+60h+arg_20]
0x180008506  movups  xmmword ptr [rdi], xmm0
0x180008509  mov     [rdi+10h], rax
0x18000850d  movups  [rsp+160h+var_140], xmm0
0x180008512  movups  [rsp+160h+var_130], xmm0
0x180008517  xorps   xmm1, xmm1
0x18000851a  movups  xmmword ptr [rsp+160h+pProxyConfig.fAutoDetect], xmm1
0x18000851f  movups  xmmword ptr [rsp+160h+pProxyConfig.lpszProxy], xmm1
0x180008524  test    bl, bl
0x180008526  jz      short loc_180008573
0x180008528  mov     rcx, cs:WPP_GLOBAL_Control
0x18000852f  cmp     rcx, r13
0x180008532  jz      short loc_180008556
0x180008534  test    byte ptr [rcx+1Ch], 1
0x180008538  jz      short loc_180008556
0x18000853a  mov     edx, 0Bh
0x18000853f  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x180008546  mov     rcx, [rcx+10h]
0x18000854a  call    WPP_SF_
0x18000854f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008556  mov     dword ptr [rsp+160h+var_140], 1
0x18000855e  mov     dword ptr [rsp+160h+var_140+4], 3
0x180008566  mov     dword ptr [rsp+160h+var_130+0Ch], 1
0x18000856e  jmp     loc_1800087CA
0x180008573  lea     rcx, [rsp+160h+var_100]; this
0x180008578  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x18000857d  nop
0x18000857e  mov     byte ptr [rsp+160h+var_F8], 0
0x180008583  mov     rax, [rsi]
0x180008586  mov     qword ptr [rsp+160h+var_F8+8], rax
0x18000858b  lock inc dword ptr [rax+8]
0x18000858f  xor     ebx, ebx
0x180008591  mov     [rsp+160h+var_E8], rbx
0x180008596  mov     edx, 8; dwFlags
0x18000859b  mov     r8d, 4; dwBytes
0x1800085a1  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800085a8  call    cs:__imp_HeapAlloc
0x1800085ae  test    rax, rax
0x1800085b1  jnz     short loc_180008614
0x1800085b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085ba  cmp     rcx, r13
0x1800085bd  jz      short loc_1800085E0
0x1800085bf  test    byte ptr [rcx+1Ch], 4
0x1800085c3  jz      short loc_1800085E0
0x1800085c5  mov     edx, 0Ah
0x1800085ca  mov     r9d, 4
0x1800085d0  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800085d7  mov     rcx, [rcx+10h]
0x1800085db  call    WPP_SF_d
0x1800085e0  xorps   xmm0, xmm0
0x1800085e3  movups  [rbp+60h+var_98], xmm0
0x1800085e7  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800085ee  mov     [rbp+60h+pExceptionObject], rcx
0x1800085f2  mov     [rbp+60h+var_88], 8007000Eh
0x1800085f9  mov     [rbp+60h+var_84], ebx
0x1800085fc  mov     [rbp+60h+var_80], 1
0x180008603  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000860a  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x18000860e  call    _CxxThrowException_0
0x180008614  mov     dword ptr [rax], 1
0x18000861a  mov     [rbp+60h+var_E0], rax
0x18000861e  mov     [rbp+60h+var_D8], rbx
0x180008622  lock inc cs:dword_180145058
0x180008629  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x180008630  mov     [rbp+60h+var_D0], rax
0x180008634  cmp     byte ptr [rsp+160h+var_F8], 0
0x180008639  jnz     short loc_180008694
0x18000863b  mov     rcx, qword ptr [rsp+160h+var_F8+8]
0x180008640  mov     rcx, [rcx]; hToken
0x180008643  call    cs:__imp_ImpersonateLoggedOnUser
0x180008649  test    eax, eax
0x18000864b  jnz     short loc_18000868F
0x18000864d  call    cs:__imp_GetLastError
0x180008653  test    eax, eax
0x180008655  jle     short loc_18000865F
0x180008657  movzx   eax, ax
0x18000865a  or      eax, 80070000h
0x18000865f  xorps   xmm0, xmm0
0x180008662  movups  [rbp+60h+var_98], xmm0
0x180008666  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000866d  mov     [rbp+60h+pExceptionObject], rcx
0x180008671  mov     [rbp+60h+var_88], eax
0x180008674  mov     [rbp+60h+var_84], ebx
0x180008677  mov     [rbp+60h+var_80], 1
0x18000867e  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180008685  lea     rcx, [rbp+60h+pExceptionObject]; pExceptionObject
0x180008689  call    _CxxThrowException_0
0x18000868f  mov     byte ptr [rsp+160h+var_F8], 1
0x180008694  lea     rcx, [rsp+160h+pProxyConfig]; pProxyConfig
0x180008699  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18000869f  test    eax, eax
0x1800086a1  jz      loc_18000875D
0x1800086a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086ae  cmp     rcx, r13
0x1800086b1  jz      short loc_1800086D5
0x1800086b3  test    byte ptr [rcx+1Ch], 1
0x1800086b7  jz      short loc_1800086D5
0x1800086b9  mov     edx, 0Ch
0x1800086be  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x1800086c5  mov     rcx, [rcx+10h]
0x1800086c9  call    WPP_SF_
0x1800086ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086d5  cmp     [rsp+160h+pProxyConfig.fAutoDetect], 0
0x1800086da  jz      short loc_180008718
0x1800086dc  cmp     rcx, r13
0x1800086df  jz      short loc_180008703
0x1800086e1  test    byte ptr [rcx+1Ch], 1
0x1800086e5  jz      short loc_180008703
0x1800086e7  mov     edx, 0Dh
0x1800086ec  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x1800086f3  mov     rcx, [rcx+10h]
0x1800086f7  call    WPP_SF_
0x1800086fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180008703  mov     dword ptr [rsp+160h+var_140], 1
0x18000870b  mov     dword ptr [rsp+160h+var_140+4], 3
0x180008713  mov     ebx, 1
0x180008718  mov     rax, [rsp+160h+pProxyConfig.lpszAutoConfigUrl]
0x18000871d  test    rax, rax
0x180008720  jz      loc_1800087A9
0x180008726  cmp     rcx, r13
0x180008729  jz      short loc_18000874E
0x18000872b  test    byte ptr [rcx+1Ch], 1
0x18000872f  jz      short loc_18000874E
0x180008731  mov     edx, 0Eh
0x180008736  mov     r9, rax
0x180008739  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x180008740  mov     rcx, [rcx+10h]
0x180008744  call    WPP_SF_S
0x180008749  mov     rax, [rsp+160h+pProxyConfig.lpszAutoConfigUrl]
0x18000874e  or      dword ptr [rsp+160h+var_140], 2
0x180008753  mov     qword ptr [rsp+160h+var_140+8], rax
0x180008758  mov     r14, rax
0x18000875b  jmp     short loc_1800087A4
0x18000875d  mov     rax, cs:WPP_GLOBAL_Control
0x180008764  cmp     rax, r13
0x180008767  jz      short loc_180008794
0x180008769  test    byte ptr [rax+1Ch], 1
0x18000876d  jz      short loc_180008794
0x18000876f  call    cs:__imp_GetLastError
0x180008775  mov     edx, 0Fh
0x18000877a  mov     r9d, eax
0x18000877d  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x180008784  mov     rcx, cs:WPP_GLOBAL_Control
0x18000878b  mov     rcx, [rcx+10h]
0x18000878f  call    WPP_SF_d
0x180008794  mov     dword ptr [rsp+160h+var_140], 1
0x18000879c  mov     dword ptr [rsp+160h+var_140+4], 3
0x1800087a4  mov     ebx, 1
0x1800087a9  lea     rcx, [rsp+160h+var_100]; this
0x1800087ae  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800087b3  mov     dword ptr [rsp+160h+var_130+0Ch], 1
0x1800087bb  test    ebx, ebx
0x1800087bd  jz      loc_1800088C3
0x1800087c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087ca  cmp     rcx, r13
0x1800087cd  jz      short loc_1800087EA
0x1800087cf  test    byte ptr [rcx+1Ch], 1
0x1800087d3  jz      short loc_1800087EA
0x1800087d5  mov     edx, 10h
0x1800087da  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x1800087e1  mov     rcx, [rcx+10h]
0x1800087e5  call    WPP_SF_
0x1800087ea  mov     rdx, rsi; struct TokenHandle *
0x1800087ed  lea     rcx, [rbp+60h+pExceptionObject]; this
0x1800087f1  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x1800087f6  nop
0x1800087f7  or      dword ptr [rsp+160h+var_140], 400000h
0x1800087ff  mov     r9, rdi; struct _WINHTTP_PROXY_INFO *
0x180008802  lea     r8, [rsp+160h+var_140]; struct _WINHTTP_AUTOPROXY_OPTIONS *
0x180008807  mov     rdx, r15; unsigned __int16 *
0x18000880a  mov     rcx, r12; this
0x18000880d  call    ?GetProxyForUrlEx@CACHED_AUTOPROXY@@CAJAEAVLockableHINTERNET@@PEBGPEAU_WINHTTP_AUTOPROXY_OPTIONS@@PEAU_WINHTTP_PROXY_INFO@@@Z; CACHED_AUTOPROXY::GetProxyForUrlEx(LockableHINTERNET &,ushort const *,_WINHTTP_AUTOPROXY_OPTIONS *,_WINHTTP_PROXY_INFO *)
0x180008812  mov     ebx, eax
0x180008814  mov     rcx, cs:WPP_GLOBAL_Control
0x18000881b  cmp     rcx, r13
0x18000881e  jz      short loc_180008845
0x180008820  test    byte ptr [rcx+1Ch], 1
0x180008824  jz      short loc_180008845
0x180008826  mov     edx, 11h
0x18000882b  mov     r9d, eax
0x18000882e  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x180008835  mov     rcx, [rcx+10h]
0x180008839  call    WPP_SF_d
0x18000883e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008845  cmp     ebx, 80072EF1h
0x18000884b  jnz     short loc_1800088AA
0x18000884d  cmp     rcx, r13
0x180008850  jz      short loc_18000886D
0x180008852  test    byte ptr [rcx+1Ch], 1
0x180008856  jz      short loc_18000886D
0x180008858  mov     edx, 12h
0x18000885d  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x180008864  mov     rcx, [rcx+10h]
0x180008868  call    WPP_SF_
0x18000886d  xorps   xmm0, xmm0
0x180008870  movups  [rsp+160h+var_F8], xmm0
0x180008875  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18000887c  mov     [rsp+160h+var_100], rcx
0x180008881  mov     dword ptr [rsp+160h+var_E8], 80004004h
0x180008889  mov     dword ptr [rsp+160h+var_E8+4], 8Bh
0x180008891  mov     dword ptr [rbp+60h+var_E0], 1
0x180008898  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000889f  lea     rcx, [rsp+160h+var_100]; pExceptionObject
0x1800088a4  call    _CxxThrowException_0
0x1800088aa  lea     rcx, [rbp+60h+pExceptionObject]; this
0x1800088ae  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x1800088b3  test    ebx, ebx
0x1800088b5  js      short loc_1800088C3
0x1800088b7  mov     rax, [rsp+160h+pProxyConfig.lpszProxyBypass]
0x1800088bc  mov     rcx, [rsp+160h+pProxyConfig.lpszProxy]
0x1800088c1  jmp     short loc_180008938
0x1800088c3  mov     r10, cs:WPP_GLOBAL_Control
0x1800088ca  cmp     r10, r13
0x1800088cd  jz      short loc_1800088F2
0x1800088cf  test    byte ptr [r10+1Ch], 1
0x1800088d4  jz      short loc_1800088F2
0x1800088d6  mov     edx, 13h
0x1800088db  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x1800088e2  mov     rcx, [r10+10h]
0x1800088e6  call    WPP_SF_
0x1800088eb  mov     r10, cs:WPP_GLOBAL_Control
0x1800088f2  mov     rcx, [rsp+160h+pProxyConfig.lpszProxy]
0x1800088f7  test    rcx, rcx
0x1800088fa  jz      short loc_180008961
0x1800088fc  cmp     r10, r13
0x1800088ff  jz      short loc_180008925
0x180008901  test    byte ptr [r10+1Ch], 1
0x180008906  jz      short loc_180008925
0x180008908  mov     edx, 14h
0x18000890d  mov     r9, rcx
0x180008910  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x180008917  mov     rcx, [r10+10h]
0x18000891b  call    WPP_SF_S
0x180008920  mov     rcx, [rsp+160h+pProxyConfig.lpszProxy]; hMem
0x180008925  mov     dword ptr [rdi], 3
0x18000892b  mov     [rdi+8], rcx
0x18000892f  mov     rax, [rsp+160h+pProxyConfig.lpszProxyBypass]
0x180008934  mov     [rdi+10h], rax
0x180008938  test    rcx, rcx
0x18000893b  jz      loc_180008B57
0x180008941  cmp     [rdi+8], rcx
0x180008945  jz      loc_180008B57
0x18000894b  call    cs:__imp_GlobalFree
0x180008951  mov     [rsp+160h+pProxyConfig.lpszProxy], 0
0x18000895a  mov     r10, cs:WPP_GLOBAL_Control
0x180008961  mov     rax, [rsp+160h+pProxyConfig.lpszProxyBypass]
0x180008966  test    rax, rax
0x180008969  jz      short loc_18000898A
0x18000896b  cmp     [rdi+10h], rax
0x18000896f  jz      short loc_18000898A
0x180008971  mov     rcx, rax; hMem
0x180008974  call    cs:__imp_GlobalFree
0x18000897a  mov     [rsp+160h+pProxyConfig.lpszProxyBypass], 0
0x180008983  mov     r10, cs:WPP_GLOBAL_Control
0x18000898a  mov     r9, [rdi+8]
0x18000898e  lea     rbx, asc_180145038; ":"
0x180008995  lea     rsi, asc_180145030; "::"
0x18000899c  test    r9, r9
0x18000899f  jz      short loc_180008A1D
0x1800089a1  mov     rax, r9
0x1800089a4  mov     r8, rbx
0x1800089a7  sub     r8, r9
0x1800089aa  movzx   ecx, word ptr [rax]
0x1800089ad  movzx   edx, word ptr [rax+r8]
0x1800089b2  sub     ecx, edx
0x1800089b4  jnz     short loc_1800089BE
0x1800089b6  add     rax, 2
0x1800089ba  test    edx, edx
0x1800089bc  jnz     short loc_1800089AA
0x1800089be  test    ecx, ecx
0x1800089c0  jz      short loc_1800089E3
0x1800089c2  mov     rax, r9
  ... truncated ...
```
