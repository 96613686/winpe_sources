# CACHED_AUTOPROXY::GetProxyForUrlEx(LockableHINTERNET &,ushort const *,_WINHTTP_AUTOPROXY_OPTIONS *,_WINHTTP_PROXY_INFO *)

- ea: `0x180032db0`
- end: `0x180033416`
- name: `?GetProxyForUrlEx@CACHED_AUTOPROXY@@CAJAEAVLockableHINTERNET@@PEBGPEAU_WINHTTP_AUTOPROXY_OPTIONS@@PEAU_WINHTTP_PROXY_INFO@@@Z`
- size: `1638`
- prototype: `__int64 __fastcall(HINTERNET *this, const unsigned __int16 *, WINHTTP_AUTOPROXY_OPTIONS *, struct _WINHTTP_PROXY_INFO *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800084a0`

## callees

- `0x180006640`
- `0x18000c520`
- `0x1800327f0`
- `0x180032db0`
- `0x180033420`
- `0x180033480`
- `0x1800334ec`
- `0x180080430`
- `0x180089184`
- `0x180092664`
- `0x1800952bc`
- `0x18009a7a0`
- `0x18009b668`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a1114`
- `0x1800a3444`
- `0x1800f9948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033009`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003320a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003321c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800330c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003320a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033214`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003321c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180032e35`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180032e35`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180033200`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180033200`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800333ba`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800333ba`
- `WINHTTP!WinHttpFreeProxyResult` at `0x180032f9e`
- `WINHTTP!WinHttpFreeProxyResult` at `0x1800333c5`
- `WINHTTP!WinHttpFreeProxyResult` at `0x180032f9e`
- `WINHTTP!WinHttpFreeProxyResult` at `0x1800333c5`
- `WINHTTP!WinHttpGetProxyForUrlEx` at `0x180033135`
- `WINHTTP!WinHttpGetProxyForUrlEx` at `0x180033135`
- `WINHTTP!WinHttpCreateProxyResolver` at `0x18003303a`
- `WINHTTP!WinHttpCreateProxyResolver` at `0x18003303a`
- `WINHTTP!WinHttpCloseHandle` at `0x180032fca`
- `WINHTTP!WinHttpCloseHandle` at `0x180032ff4`
- `WINHTTP!WinHttpCloseHandle` at `0x1800333f1`
- `WINHTTP!WinHttpCloseHandle` at `0x180032fca`
- `WINHTTP!WinHttpCloseHandle` at `0x180032ff4`
- `WINHTTP!WinHttpCloseHandle` at `0x1800333f1`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800330aa`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800330aa`

## string_xrefs

- `0x18003301f`: `onecore\admin\services\drizzle\service\src\proxy.h`

## pseudocode

```c
__int64 __fastcall CACHED_AUTOPROXY::GetProxyForUrlEx(
        HINTERNET *this,
        const unsigned __int16 *a2,
        WINHTTP_AUTOPROXY_OPTIONS *a3,
        struct _WINHTTP_PROXY_INFO *a4)
{
  HANDLE v6; // rdi
  wil::details *v7; // rcx
  HANDLE Event; // rbx
  int LastErrorFailHr; // eax
  _DWORD *v10; // rax
  DWORD_PTR v11; // r14
  const ComError *v12; // rax
  const ComError *v13; // rbx
  HoldCritSec *v14; // rax
  void *v15; // rdx
  HoldCritSec *v16; // r15
  HINTERNET v17; // r12
  __int64 result; // rax
  const char *v19; // r9
  signed int v20; // eax
  unsigned int LastError; // eax
  signed int ProxyForUrl; // eax
  void (*v23)(void); // r9
  unsigned int v24; // eax
  signed int v25; // eax
  int v26; // eax
  HGLOBAL v27; // rbx
  HGLOBAL v28; // rax
  void *v29; // rdx
  const ComError *v30; // rbx
  HINTERNET hInternet; // [rsp+30h] [rbp-348h] BYREF
  HGLOBAL hMem; // [rsp+38h] [rbp-340h] BYREF
  HANDLE hHandle; // [rsp+40h] [rbp-338h] BYREF
  const ComError *v34[3]; // [rsp+48h] [rbp-330h] BYREF
  void **pExceptionObject; // [rsp+60h] [rbp-318h] BYREF
  __int128 v36; // [rsp+68h] [rbp-310h]
  int v37; // [rsp+78h] [rbp-300h]
  int v38; // [rsp+7Ch] [rbp-2FCh]
  int v39; // [rsp+80h] [rbp-2F8h]
  void **v40; // [rsp+C0h] [rbp-2B8h] BYREF
  __int128 v41; // [rsp+C8h] [rbp-2B0h]
  signed int v42; // [rsp+D8h] [rbp-2A0h]
  int v43; // [rsp+DCh] [rbp-29Ch]
  int v44; // [rsp+E0h] [rbp-298h]
  void **v45; // [rsp+120h] [rbp-258h] BYREF
  __int128 v46; // [rsp+128h] [rbp-250h]
  unsigned int v47; // [rsp+138h] [rbp-240h]
  int v48; // [rsp+13Ch] [rbp-23Ch]
  int v49; // [rsp+140h] [rbp-238h]
  void **v50; // [rsp+180h] [rbp-1F8h] BYREF
  __int128 v51; // [rsp+188h] [rbp-1F0h]
  signed int v52; // [rsp+198h] [rbp-1E0h]
  int v53; // [rsp+19Ch] [rbp-1DCh]
  int v54; // [rsp+1A0h] [rbp-1D8h]
  void **v55; // [rsp+1E0h] [rbp-198h] BYREF
  __int128 v56; // [rsp+1E8h] [rbp-190h]
  unsigned int v57; // [rsp+1F8h] [rbp-180h]
  int v58; // [rsp+1FCh] [rbp-17Ch]
  int v59; // [rsp+200h] [rbp-178h]
  void **v60; // [rsp+240h] [rbp-138h] BYREF
  __int128 v61; // [rsp+248h] [rbp-130h]
  signed int v62; // [rsp+258h] [rbp-120h]
  int v63; // [rsp+25Ch] [rbp-11Ch]
  int v64; // [rsp+260h] [rbp-118h]
  void **v65; // [rsp+2A0h] [rbp-D8h] BYREF
  __int128 v66; // [rsp+2A8h] [rbp-D0h]
  int v67; // [rsp+2B8h] [rbp-C0h]
  int v68; // [rsp+2BCh] [rbp-BCh]
  int v69; // [rsp+2C0h] [rbp-B8h]
  _BYTE Context[120]; // [rsp+300h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_12cba19daead377fec43f4905df69b93_Traceguids, a2);
  *(_DWORD *)a4 = 1;
  *((_QWORD *)a4 + 1) = 0;
  *((_QWORD *)a4 + 2) = 0;
  hInternet = 0;
  v6 = 0;
  hHandle = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &hHandle,
      Event);
    LastErrorFailHr = 0;
    v6 = hHandle;
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v7);
  }
  try
  {
    if ( LastErrorFailHr < 0 )
    {
      v36 = 0;
      pExceptionObject = &ComError::`vftable';
      v37 = LastErrorFailHr;
      v38 = 333;
      v39 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v10 = operator new(0x20u);
    v11 = (DWORD_PTR)v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = v6;
      v10[2] = 0;
      *((_OWORD *)v10 + 1) = 0;
    }
    else
    {
      v11 = 0;
    }
    v34[1] = (const ComError *)v11;
    v12 = (const ComError *)operator new(0x10u);
    v13 = v12;
    if ( v12 )
    {
      *(_BYTE *)v12 = 0;
      *((_QWORD *)v12 + 1) = this;
      CCritSec2::enter((CCritSec2 *)this);
      *(_BYTE *)v13 = 1;
    }
    else
    {
      v13 = 0;
    }
    v34[2] = v13;
    v14 = (HoldCritSec *)operator new(0x10u);
    v16 = v14;
    if ( v14 )
    {
      *(_BYTE *)v14 = 0;
      *((_QWORD *)v14 + 1) = this;
      CCritSec2::enter((CCritSec2 *)this);
      *(_BYTE *)v16 = 1;
    }
    else
    {
      v16 = 0;
    }
    v17 = this[6];
    if ( v16 )
    {
      HoldCritSec::~HoldCritSec(v16);
      operator delete(v16, 0x10u);
    }
    if ( v17 )
    {
      if ( hInternet )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&hMem);
        WinHttpCloseHandle(hInternet);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&hMem);
      }
      hInternet = 0;
      if ( this[2] != (HINTERNET)GetCurrentThreadId() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x6F,
          (unsigned int)"onecore\\admin\\services\\drizzle\\service\\src\\proxy.h",
          v19);
      v20 = WinHttpCreateProxyResolver(this[6], &hInternet);
      if ( v20 )
      {
        if ( v20 > 0 )
          v20 = (unsigned __int16)v20 | 0x80070000;
        v41 = 0;
        v40 = &ComError::`vftable';
        v42 = v20;
        v43 = 352;
        v44 = 1;
        throw (ComError *)&v40;
      }
      if ( WinHttpSetStatusCallback(hInternet, CACHED_AUTOPROXY::GetProxyCallback, 0x1200000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0x80070000;
        else
          LastError = GetLastError();
        v46 = 0;
        v45 = &ComError::`vftable';
        v47 = LastError;
        v48 = 362;
        v49 = 1;
        throw (ComError *)&v45;
      }
      ProxyForUrl = WinHttpGetProxyForUrlEx(hInternet, a2, a3, v11);
      if ( ProxyForUrl != 997 )
      {
        if ( ProxyForUrl > 0 )
          ProxyForUrl = (unsigned __int16)ProxyForUrl | 0x80070000;
        v51 = 0;
        v50 = &ComError::`vftable';
        v52 = ProxyForUrl;
        v53 = 374;
        v54 = 1;
        throw (ComError *)&v50;
      }
      if ( v13 )
      {
        HoldCritSec::~HoldCritSec(v13);
        operator delete(v13, 0x10u);
      }
      ScopedWatchdogTimer::ScopedWatchdogTimer(Context, 0x1D4C0u, -2147012716, v23);
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_12cba19daead377fec43f4905df69b93_Traceguids);
      if ( WaitForSingleObjectEx(v6, 0xFFFFFFFF, 0) )
      {
        if ( (int)GetLastError() > 0 )
          v24 = (unsigned __int16)GetLastError() | 0x80070000;
        else
          v24 = GetLastError();
        v56 = 0;
        v55 = &ComError::`vftable';
        v57 = v24;
        v58 = 387;
        v59 = 1;
        throw (ComError *)&v55;
      }
      ScopedWatchdogTimer::~ScopedWatchdogTimer((ScopedWatchdogTimer *)Context);
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_12cba19daead377fec43f4905df69b93_Traceguids,
          *(unsigned int *)(v11 + 8));
      v25 = *(_DWORD *)(v11 + 8);
      if ( v25 )
      {
        if ( v25 > 0 )
          v25 = (unsigned __int16)v25 | 0x80070000;
        v61 = 0;
        v60 = &ComError::`vftable';
        v62 = v25;
        v63 = 394;
        v64 = 1;
        throw (ComError *)&v60;
      }
      hMem = 0;
      v26 = CACHED_AUTOPROXY::ConvertProxyResultToProxyList(
              (const struct _WINHTTP_PROXY_RESULT *)(v11 + 16),
              (unsigned __int16 **)&hMem);
      if ( v26 < 0 )
      {
        v66 = 0;
        v65 = &ComError::`vftable';
        v67 = v26;
        v68 = 398;
        v69 = 1;
        throw (ComError *)&v65;
      }
      v27 = hMem;
      if ( *(_WORD *)hMem )
      {
        *(_DWORD *)a4 = 3;
        v28 = v27;
        v27 = 0;
        *((_QWORD *)a4 + 1) = v28;
      }
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          WPP_12cba19daead377fec43f4905df69b93_Traceguids,
          *((_QWORD *)a4 + 1));
      if ( v27 )
        GlobalFree(v27);
      WinHttpFreeProxyResult((WINHTTP_PROXY_RESULT *)(v11 + 16));
      operator delete((void *)v11, 0x20u);
      if ( v6 )
        wil::details::CloseHandle((wil::details *)v6, v29);
      if ( hInternet )
        WinHttpCloseHandle(hInternet);
      result = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_12cba19daead377fec43f4905df69b93_Traceguids);
      if ( v13 )
      {
        HoldCritSec::~HoldCritSec(v13);
        operator delete(v13, 0x10u);
      }
      if ( v11 )
      {
        WinHttpFreeProxyResult((WINHTTP_PROXY_RESULT *)(v11 + 16));
        operator delete((void *)v11, 0x20u);
      }
      if ( v6 )
        wil::details::CloseHandle((wil::details *)v6, v15);
      if ( hInternet )
        WinHttpCloseHandle(hInternet);
      result = 2147954417LL;
    }
  }
  catch ( const ComError *v34 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      v30 = v34[0];
    }
    else
    {
      v30 = v34[0];
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_12cba19daead377fec43f4905df69b93_Traceguids,
        *((unsigned int *)v30 + 6),
        *((_DWORD *)v30 + 7));
    }
    return *((unsigned int *)v30 + 6);
  }
  if ( LastErrorFailHr < 0 )
  {
    v36 = 0;
    pExceptionObject = &ComError::`vftable';
    v37 = LastErrorFailHr;
    v38 = 333;
    v39 = 1;
    throw (ComError *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180032db0  mov     [rsp+arg_18], r9
0x180032db5  mov     [rsp+pAutoProxyOptions], r8
0x180032dba  mov     [rsp+pcwszUrl], rdx
0x180032dbf  push    rbx
0x180032dc0  push    rsi
0x180032dc1  push    rdi
0x180032dc2  push    r12
0x180032dc4  push    r13
0x180032dc6  push    r14
0x180032dc8  push    r15
0x180032dca  sub     rsp, 340h
0x180032dd1  mov     rbx, r9
0x180032dd4  mov     rax, rdx
0x180032dd7  mov     r13, rcx
0x180032dda  xor     r12d, r12d
0x180032ddd  lea     rdx, WPP_GLOBAL_Control
0x180032de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180032deb  lea     esi, [r12+1]
0x180032df0  cmp     rcx, rdx
0x180032df3  jz      short loc_180032E11
0x180032df5  test    [rcx+1Ch], sil
0x180032df9  jz      short loc_180032E11
0x180032dfb  lea     edx, [rsi+1Bh]
0x180032dfe  mov     r9, rax
0x180032e01  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x180032e08  mov     rcx, [rcx+10h]
0x180032e0c  call    WPP_SF_S
0x180032e11  mov     [rbx], esi
0x180032e13  mov     [rbx+8], r12
0x180032e17  mov     [rbx+10h], r12
0x180032e1b  mov     [rsp+378h+hInternet], r12
0x180032e20  mov     rdi, r12
0x180032e23  mov     [rsp+378h+hHandle], r12
0x180032e28  mov     r9d, 1F0003h; dwDesiredAccess
0x180032e2e  mov     r8d, esi; dwFlags
0x180032e31  xor     edx, edx; lpName
0x180032e33  xor     ecx, ecx; lpEventAttributes
0x180032e35  call    cs:__imp_CreateEventExW
0x180032e3b  mov     rbx, rax
0x180032e3e  test    rax, rax
0x180032e41  jz      short loc_180032E60
0x180032e43  call    cs:__imp_GetLastError
0x180032e49  mov     rdx, rbx
0x180032e4c  lea     rcx, [rsp+378h+hHandle]
0x180032e51  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180032e56  mov     eax, r12d
0x180032e59  mov     rdi, [rsp+378h+hHandle]
0x180032e5e  jmp     short loc_180032E65
0x180032e60  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180032e65  test    eax, eax
0x180032e67  jns     short loc_180032EA1
0x180032e69  xorps   xmm0, xmm0
0x180032e6c  movups  [rsp+378h+var_310], xmm0
0x180032e71  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180032e78  mov     [rsp+378h+pExceptionObject], rcx
0x180032e7d  mov     [rsp+378h+var_300], eax
0x180032e81  mov     [rsp+378h+var_2FC], 14Dh
0x180032e89  mov     [rsp+378h+var_2F8], esi
0x180032e90  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180032e97  lea     rcx, [rsp+378h+pExceptionObject]; pExceptionObject
0x180032e9c  call    _CxxThrowException_0
0x180032ea1  mov     ecx, 20h ; ' '; dwBytes
0x180032ea6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032eab  mov     r14, rax
0x180032eae  test    rax, rax
0x180032eb1  jz      short loc_180032EC3
0x180032eb3  mov     [rax], rdi
0x180032eb6  mov     [rax+8], r12d
0x180032eba  xorps   xmm0, xmm0
0x180032ebd  movups  xmmword ptr [rax+10h], xmm0
0x180032ec1  jmp     short loc_180032EC6
0x180032ec3  mov     r14, r12
0x180032ec6  mov     [rsp+378h+var_328], r14
0x180032ecb  mov     r15d, 10h
0x180032ed1  mov     ecx, r15d; dwBytes
0x180032ed4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032ed9  mov     rbx, rax
0x180032edc  test    rax, rax
0x180032edf  jz      short loc_180032EF5
0x180032ee1  mov     [rax], r12b
0x180032ee4  mov     [rax+8], r13
0x180032ee8  mov     rcx, r13; this
0x180032eeb  call    ?enter@CCritSec2@@QEAAXXZ; CCritSec2::enter(void)
0x180032ef0  mov     [rbx], sil
0x180032ef3  jmp     short loc_180032EF8
0x180032ef5  mov     rbx, r12
0x180032ef8  mov     [rsp+378h+var_320], rbx
0x180032efd  mov     rcx, r15; dwBytes
0x180032f00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032f05  mov     r15, rax
0x180032f08  test    rax, rax
0x180032f0b  jz      short loc_180032F21
0x180032f0d  mov     [rax], r12b
0x180032f10  mov     [rax+8], r13
0x180032f14  mov     rcx, r13; this
0x180032f17  call    ?enter@CCritSec2@@QEAAXXZ; CCritSec2::enter(void)
0x180032f1c  mov     [r15], sil
0x180032f1f  jmp     short loc_180032F24
0x180032f21  mov     r15, r12
0x180032f24  mov     r12, [r13+30h]
0x180032f28  test    r15, r15
0x180032f2b  jz      short loc_180032F42
0x180032f2d  mov     rcx, r15; this
0x180032f30  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x180032f35  mov     edx, 10h; unsigned __int64
0x180032f3a  mov     rcx, r15; void *
0x180032f3d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180032f42  test    r12, r12
0x180032f45  jnz     loc_180032FDA
0x180032f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032f52  lea     r13, WPP_GLOBAL_Control
0x180032f59  cmp     rcx, r13
0x180032f5c  jz      short loc_180032F7A
0x180032f5e  test    byte ptr [rcx+1Ch], 2
0x180032f62  jz      short loc_180032F7A
0x180032f64  lea     edx, [r12+1Dh]
0x180032f69  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x180032f70  mov     rcx, [rcx+10h]
0x180032f74  call    WPP_SF_
0x180032f79  nop
0x180032f7a  test    rbx, rbx
0x180032f7d  jz      short loc_180032F95
0x180032f7f  mov     rcx, rbx; this
0x180032f82  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x180032f87  mov     edx, 10h; unsigned __int64
0x180032f8c  mov     rcx, rbx; void *
0x180032f8f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180032f94  nop
0x180032f95  test    r14, r14
0x180032f98  jz      short loc_180032FB2
0x180032f9a  lea     rcx, [r14+10h]; pProxyResult
0x180032f9e  call    cs:__imp_WinHttpFreeProxyResult
0x180032fa4  mov     edx, 20h ; ' '; unsigned __int64
0x180032fa9  mov     rcx, r14; void *
0x180032fac  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180032fb1  nop
0x180032fb2  test    rdi, rdi
0x180032fb5  jz      short loc_180032FC0
0x180032fb7  mov     rcx, rdi; this
0x180032fba  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180032fbf  nop
0x180032fc0  mov     rcx, [rsp+378h+hInternet]; hInternet
0x180032fc5  test    rcx, rcx
0x180032fc8  jz      short loc_180032FD0
0x180032fca  call    cs:__imp_WinHttpCloseHandle
0x180032fd0  mov     eax, 80072EF1h
0x180032fd5  jmp     loc_180033402
0x180032fda  mov     r15, [rsp+378h+hInternet]
0x180032fdf  xor     r12d, r12d
0x180032fe2  test    r15, r15
0x180032fe5  jz      short loc_180033004
0x180032fe7  lea     rcx, [rsp+378h+hMem]; this
0x180032fec  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180032ff1  mov     rcx, r15; hInternet
0x180032ff4  call    cs:__imp_WinHttpCloseHandle
0x180032ffa  lea     rcx, [rsp+378h+hMem]; this
0x180032fff  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180033004  mov     [rsp+378h+hInternet], r12
0x180033009  call    cs:__imp_GetCurrentThreadId
0x18003300f  mov     eax, eax
0x180033011  mov     rcx, [rsp+378h]; this
0x180033019  cmp     [r13+10h], rax
0x18003301d  jz      short loc_180033031
0x18003301f  lea     r8, aOnecoreAdminSe; "onecore\\admin\\services\\drizzle\\serv"...
0x180033026  mov     edx, 6Fh ; 'o'; void *
0x18003302b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180033031  lea     rdx, [rsp+378h+hInternet]; phResolver
0x180033036  mov     rcx, [r13+30h]; hSession
0x18003303a  call    cs:__imp_WinHttpCreateProxyResolver
0x180033040  test    eax, eax
0x180033042  jz      short loc_180033095
0x180033044  jle     short loc_18003304E
0x180033046  movzx   eax, ax
0x180033049  or      eax, 80070000h
0x18003304e  xorps   xmm0, xmm0
0x180033051  movups  [rsp+378h+var_2B0], xmm0
0x180033059  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180033060  mov     [rsp+378h+var_2B8], rcx
0x180033068  mov     [rsp+378h+var_2A0], eax
0x18003306f  mov     [rsp+378h+var_29C], 160h
0x18003307a  mov     [rsp+378h+var_298], esi
0x180033081  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180033088  lea     rcx, [rsp+378h+var_2B8]; pExceptionObject
0x180033090  call    _CxxThrowException_0
0x180033095  xor     r9d, r9d; dwReserved
0x180033098  mov     r8d, 1200000h; dwNotificationFlags
0x18003309e  lea     rdx, ?GetProxyCallback@CACHED_AUTOPROXY@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x1800330a5  mov     rcx, [rsp+378h+hInternet]; hInternet
0x1800330aa  call    cs:__imp_WinHttpSetStatusCallback
0x1800330b0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800330b4  jnz     short loc_18003311D
0x1800330b6  call    cs:__imp_GetLastError
0x1800330bc  test    eax, eax
0x1800330be  jg      short loc_1800330C8
0x1800330c0  call    cs:__imp_GetLastError
0x1800330c6  jmp     short loc_1800330D6
0x1800330c8  call    cs:__imp_GetLastError
0x1800330ce  movzx   eax, ax
0x1800330d1  or      eax, 80070000h
0x1800330d6  xorps   xmm0, xmm0
0x1800330d9  movups  [rsp+378h+var_250], xmm0
0x1800330e1  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800330e8  mov     [rsp+378h+var_258], rcx
0x1800330f0  mov     [rsp+378h+var_240], eax
0x1800330f7  mov     [rsp+378h+var_23C], 16Ah
0x180033102  mov     [rsp+378h+var_238], esi
0x180033109  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180033110  lea     rcx, [rsp+378h+var_258]; pExceptionObject
0x180033118  call    _CxxThrowException_0
0x18003311d  mov     r9, r14; pContext
0x180033120  mov     r8, [rsp+378h+pAutoProxyOptions]; pAutoProxyOptions
0x180033128  mov     rdx, [rsp+378h+pcwszUrl]; pcwszUrl
0x180033130  mov     rcx, [rsp+378h+hInternet]; hResolver
0x180033135  call    cs:__imp_WinHttpGetProxyForUrlEx
0x18003313b  cmp     eax, 3E5h
0x180033140  jz      short loc_180033196
0x180033142  test    eax, eax
0x180033144  jle     short loc_18003314E
0x180033146  movzx   eax, ax
0x180033149  or      eax, 80070000h
0x18003314e  xorps   xmm0, xmm0
0x180033151  movups  [rsp+378h+var_1F0], xmm0
0x180033159  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180033160  mov     [rsp+378h+var_1F8], rcx
0x180033168  mov     [rsp+378h+var_1E0], eax
0x18003316f  mov     [rsp+378h+var_1DC], 176h
0x18003317a  mov     [rsp+378h+var_1D8], esi
0x180033181  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180033188  lea     rcx, [rsp+378h+var_1F8]; pExceptionObject
0x180033190  call    _CxxThrowException_0
0x180033196  test    rbx, rbx
0x180033199  jz      short loc_1800331B0
0x18003319b  mov     rcx, rbx; this
0x18003319e  call    ??1HoldCritSec@@QEAA@XZ; HoldCritSec::~HoldCritSec(void)
0x1800331a3  mov     edx, 10h; unsigned __int64
0x1800331a8  mov     rcx, rbx; void *
0x1800331ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800331b0  mov     edx, 1D4C0h; dwMilliseconds
0x1800331b5  mov     r8d, 80072F94h; int
0x1800331bb  lea     rcx, [rsp+378h+Context]; Context
0x1800331c3  call    ??0ScopedWatchdogTimer@@QEAA@KJP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,long,void (*)(void))
0x1800331c8  nop
0x1800331c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331d0  lea     r13, WPP_GLOBAL_Control
0x1800331d7  cmp     rcx, r13
0x1800331da  jz      short loc_1800331F7
0x1800331dc  test    [rcx+1Ch], sil
0x1800331e0  jz      short loc_1800331F7
0x1800331e2  mov     edx, 1Eh
0x1800331e7  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x1800331ee  mov     rcx, [rcx+10h]
0x1800331f2  call    WPP_SF_
0x1800331f7  xor     r8d, r8d; bAlertable
0x1800331fa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800331fd  mov     rcx, rdi; hHandle
0x180033200  call    cs:__imp_WaitForSingleObjectEx
0x180033206  test    eax, eax
0x180033208  jz      short loc_180033272
0x18003320a  call    cs:__imp_GetLastError
0x180033210  test    eax, eax
0x180033212  jg      short loc_18003321C
0x180033214  call    cs:__imp_GetLastError
0x18003321a  jmp     short loc_18003322A
0x18003321c  call    cs:__imp_GetLastError
0x180033222  movzx   eax, ax
0x180033225  or      eax, 80070000h
0x18003322a  xorps   xmm0, xmm0
0x18003322d  movups  [rsp+378h+var_190], xmm0
0x180033235  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18003323c  mov     [rsp+378h+var_198], rcx
0x180033244  mov     [rsp+378h+var_180], eax
0x18003324b  mov     [rsp+378h+var_17C], 183h
0x180033256  mov     [rsp+378h+var_178], esi
0x18003325d  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180033264  lea     rcx, [rsp+378h+var_198]; pExceptionObject
0x18003326c  call    _CxxThrowException_0
0x180033272  lea     rcx, [rsp+378h+Context]; this
0x18003327a  call    ??1ScopedWatchdogTimer@@QEAA@XZ; ScopedWatchdogTimer::~ScopedWatchdogTimer(void)
0x18003327f  mov     rcx, cs:WPP_GLOBAL_Control
0x180033286  cmp     rcx, r13
0x180033289  jz      short loc_1800332AA
0x18003328b  test    [rcx+1Ch], sil
0x18003328f  jz      short loc_1800332AA
0x180033291  mov     edx, 1Fh
0x180033296  mov     r9d, [r14+8]
0x18003329a  lea     r8, WPP_12cba19daead377fec43f4905df69b93_Traceguids
0x1800332a1  mov     rcx, [rcx+10h]
0x1800332a5  call    WPP_SF_d
0x1800332aa  mov     eax, [r14+8]
0x1800332ae  test    eax, eax
0x1800332b0  jz      short loc_180033304
0x1800332b2  jle     short loc_1800332BC
0x1800332b4  movzx   eax, ax
0x1800332b7  or      eax, 80070000h
0x1800332bc  xorps   xmm0, xmm0
0x1800332bf  movups  [rsp+378h+var_130], xmm0
0x1800332c7  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800332ce  mov     [rsp+378h+var_138], rcx
0x1800332d6  mov     [rsp+378h+var_120], eax
0x1800332dd  mov     [rsp+378h+var_11C], 18Ah
  ... truncated ...
```
