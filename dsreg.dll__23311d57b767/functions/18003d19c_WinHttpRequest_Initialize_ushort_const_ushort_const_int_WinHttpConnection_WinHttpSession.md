# WinHttpRequest::Initialize(ushort const *,ushort const *,int,WinHttpConnection &,WinHttpSession &)

- ea: `0x18003d19c`
- end: `0x18003d519`
- name: `?Initialize@WinHttpRequest@@QEAAJPEBG0HAEAVWinHttpConnection@@AEAVWinHttpSession@@@Z`
- size: `893`
- prototype: `int(WinHttpRequest *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int, struct WinHttpConnection *, struct WinHttpSession *)`
- caller_count: `9`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180064b9c`
- `0x180066f68`
- `0x180079b64`
- `0x180083dc8`
- `0x180088bac`
- `0x1800b447c`
- `0x1800b60a4`
- `0x1800b885c`
- `0x1800ba1ac`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x1800307c4`
- `0x18003334c`
- `0x18003d19c`
- `0x18003ed28`
- `0x180043ef8`
- `0x18004651c`
- `0x1800772b0`
- `0x180078098`
- `0x180079da0`
- `0x180091184`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d4b7`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18003d318`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18003d46b`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18003d318`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18003d46b`
- `WINHTTP!WinHttpSetTimeouts` at `0x18003d4ad`
- `WINHTTP!WinHttpSetTimeouts` at `0x18003d4ad`
- `WINHTTP!WinHttpOpenRequest` at `0x18003d2ea`
- `WINHTTP!WinHttpOpenRequest` at `0x18003d2ea`

## string_xrefs

- `0x18003d36e`: `EventWriteWinhttpOpenRequestFailureEvent`
- `0x18003d375`: `Logger::WriteWinhttpOpenRequestFailureEvent`
- `0x18003d1c5`: `pcszPath`
- `0x18003d1e0`: `pcszPath`
- `0x18003d2ab`: `WinHttpConnection::CreateUrl`
- `0x18003d390`: `WinHttpOpenRequest`
- `0x18003d250`: `%s: Path: "%s". Verb: %s. bIsSecure: %s. UseAutoProxy: %s.`

## pseudocode

```c
__int64 __fastcall WinHttpRequest::Initialize(
        WinHttpRequest *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        HINTERNET *a5,
        struct WinHttpSession *a6)
{
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // rdx
  const wchar_t *v12; // rdx
  int v13; // eax
  const wchar_t *v14; // rcx
  void *v15; // rcx
  DWORD dwFlags; // r12d
  int Url; // eax
  HINTERNET v18; // rax
  int v19; // r15d
  DWORD v20; // edi
  const wchar_t *v21; // r8
  DWORD LastError; // eax
  int v23; // edx
  int v24; // ecx
  unsigned int v25; // eax
  _QWORD *v26; // rax
  __int64 (__fastcall ***v27)(_QWORD, __int64); // rdx
  int v28; // eax
  signed int v29; // eax

  if ( !a2 )
  {
    v10 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpRequest::Initialize", L"pcszPath");
    v11 = L"pcszPath";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"WinHttpRequest::Initialize", v11);
    return v10;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpRequest::Initialize", L"pcszVerb");
    v11 = L"pcszVerb";
    goto LABEL_3;
  }
  v12 = L"TRUE";
  v13 = *((_DWORD *)a6 + 4);
  *((_DWORD *)this + 41) = v13;
  v14 = L"TRUE";
  if ( !v13 )
    v14 = L"FALSE";
  if ( !a4 )
    v12 = L"FALSE";
  Logger::TraceVerbose(
    (wchar_t *)L"%s: Path: \"%s\". Verb: %s. bIsSecure: %s. UseAutoProxy: %s.",
    L"WinHttpRequest::Initialize",
    a2,
    a3,
    v12,
    v14);
  v15 = (void *)*((_QWORD *)this + 7);
  dwFlags = a4 != 0 ? 0x800000 : 0;
  if ( v15 )
  {
    operator delete(v15);
    *((_QWORD *)this + 7) = 0;
  }
  Url = WinHttpConnection::CreateUrl((WinHttpConnection *)a5, (unsigned __int16 **)this + 7);
  v10 = Url;
  if ( Url < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"WinHttpRequest::Initialize",
      L"WinHttpConnection::CreateUrl",
      (unsigned int)Url);
    return v10;
  }
  v18 = WinHttpOpenRequest(a5[1], a3, a2, 0, 0, 0, dwFlags);
  *((_QWORD *)this + 1) = v18;
  v19 = 2;
  if ( !v18 )
  {
    LastError = GetLastError();
    v20 = LastError;
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v25 = McTemplateU0zqq_EventWriteTransfer(v24, v23, (_DWORD)a3, dwFlags, LastError);
      if ( v25 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteWinhttpOpenRequestFailureEvent",
          L"EventWriteWinhttpOpenRequestFailureEvent",
          v25);
    }
    if ( v20 )
    {
      v21 = L"WinHttpOpenRequest";
LABEL_23:
      Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"WinHttpRequest::Initialize", v21, v20);
      if ( (int)v20 > 0 )
        return (unsigned __int16)v20 | 0x80070000;
      else
        return v20;
    }
  }
  if ( WinHttpSetStatusCallback(*((HINTERNET *)this + 1), WinHttpRequest::AsyncCallback, 0x6F4800u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
  {
    v20 = GetLastError();
    Logger::WriteWinhttpSetCallbackFailureEvent(0x6F4800u, v20);
    if ( v20 )
      goto LABEL_17;
  }
  if ( !*((_DWORD *)this + 41) )
  {
    v26 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    if ( !v26 )
    {
      v10 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"WinHttpRequest::Initialize");
      return v10;
    }
    *(_OWORD *)v26 = 0;
    *v26 = &WinHttpHandle::`vftable';
    do
    {
      v26[1] = 0;
      --v19;
    }
    while ( v19 );
    *v26 = &WinHttpHandle::`vftable';
    v27 = (__int64 (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 15);
    *((_QWORD *)this + 15) = v26;
    if ( v27 )
      std::default_delete<WinHttpProxyResolver>::operator()((__int64)&WinHttpHandle::`vftable', v27);
    v28 = WinHttpProxyResolver::Initialize(*((WinHttpProxyResolver **)this + 15), a6);
    v10 = v28;
    if ( v28 < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"WinHttpRequest::Initialize",
        L"WinHttpProxyResolver::Intialize",
        (unsigned int)v28);
      return v10;
    }
    if ( WinHttpSetStatusCallback(
           *(HINTERNET *)(*((_QWORD *)this + 15) + 8LL),
           WinHttpRequest::AsyncCallback,
           0x1200000u,
           0) == (WINHTTP_STATUS_CALLBACK)-1LL )
    {
      v20 = GetLastError();
      Logger::WriteWinhttpSetCallbackFailureEvent(0x1200000u, v20);
      if ( v20 )
      {
LABEL_17:
        v21 = L"WinHttpSetStatusCallback";
        goto LABEL_23;
      }
    }
  }
  if ( !WinHttpSetTimeouts(*((HINTERNET *)this + 1), 0, 60000, 30000, *((_DWORD *)this + 42)) )
  {
    v29 = GetLastError();
    if ( v29 > 0 )
      v29 = (unsigned __int16)v29 | 0x80070000;
    Logger::TraceWarning(
      (wchar_t *)L"%s: WinHttpSetTimeouts failed with error code 0x%08X. Continuing with default timeouts.",
      L"WinHttpRequest::Initialize",
      (unsigned int)v29);
  }
  return v10;
}

```

## disassembly

```asm
0x18003d19c  push    rbx
0x18003d19e  push    rbp
0x18003d19f  push    rsi
0x18003d1a0  push    rdi
0x18003d1a1  push    r12
0x18003d1a3  push    r13
0x18003d1a5  push    r14
0x18003d1a7  push    r15
0x18003d1a9  sub     rsp, 48h
0x18003d1ad  lea     rsi, aWinhttprequest_0; "WinHttpRequest::Initialize"
0x18003d1b4  mov     ebx, r9d
0x18003d1b7  mov     r14, r8
0x18003d1ba  mov     rdi, rdx
0x18003d1bd  mov     rbp, rcx
0x18003d1c0  test    rdx, rdx
0x18003d1c3  jnz     short loc_18003D1F4
0x18003d1c5  lea     r8, aPcszpath; "pcszPath"
0x18003d1cc  mov     rdx, rsi
0x18003d1cf  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18003d1d6  mov     ebx, 80070057h
0x18003d1db  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003d1e0  lea     rdx, aPcszpath; "pcszPath"
0x18003d1e7  mov     rcx, rsi; unsigned __int16 *
0x18003d1ea  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18003d1ef  jmp     loc_18003D506
0x18003d1f4  test    r14, r14
0x18003d1f7  jnz     short loc_18003D21D
0x18003d1f9  lea     r8, aPcszverb; "pcszVerb"
0x18003d200  mov     rdx, rsi
0x18003d203  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18003d20a  mov     ebx, 80070057h
0x18003d20f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003d214  lea     rdx, aPcszverb; "pcszVerb"
0x18003d21b  jmp     short loc_18003D1E7
0x18003d21d  mov     r13, [rsp+88h+arg_28]
0x18003d225  lea     r8, aFalse_0; "FALSE"
0x18003d22c  lea     rdx, aTrue_0; "TRUE"
0x18003d233  mov     r9, r14
0x18003d236  mov     eax, [r13+10h]
0x18003d23a  test    eax, eax
0x18003d23c  mov     [rcx+0A4h], eax
0x18003d242  mov     rcx, rdx
0x18003d245  cmovz   rcx, r8
0x18003d249  test    ebx, ebx
0x18003d24b  mov     [rsp+88h+ppwszAcceptTypes], rcx
0x18003d250  lea     rcx, aSPathSVerbSBis; "%s: Path: \"%s\". Verb: %s. bIsSecure: "...
0x18003d257  cmovz   rdx, r8
0x18003d25b  mov     r8, rdi
0x18003d25e  mov     [rsp+88h+pwszReferrer], rdx
0x18003d263  mov     rdx, rsi
0x18003d266  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003d26b  neg     ebx
0x18003d26d  lea     rbx, [rbp+38h]
0x18003d271  mov     rcx, [rbx]; Block
0x18003d274  sbb     r12d, r12d
0x18003d277  and     r12d, 800000h
0x18003d27e  test    rcx, rcx
0x18003d281  jz      short loc_18003D28F
0x18003d283  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d288  mov     qword ptr [rbx], 0
0x18003d28f  mov     r15, [rsp+88h+arg_20]
0x18003d297  mov     rdx, rbx; unsigned __int16 **
0x18003d29a  mov     rcx, r15; this
0x18003d29d  call    ?CreateUrl@WinHttpConnection@@QEAAJPEAPEAG@Z; WinHttpConnection::CreateUrl(ushort * *)
0x18003d2a2  mov     ebx, eax
0x18003d2a4  test    eax, eax
0x18003d2a6  jns     short loc_18003D2C6
0x18003d2a8  mov     r9d, eax
0x18003d2ab  lea     r8, aWinhttpconnect_1; "WinHttpConnection::CreateUrl"
0x18003d2b2  mov     rdx, rsi
0x18003d2b5  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18003d2bc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003d2c1  jmp     loc_18003D506
0x18003d2c6  mov     rcx, [r15+8]; hConnect
0x18003d2ca  xor     r9d, r9d; pwszVersion
0x18003d2cd  mov     [rsp+88h+dwFlags], r12d; dwFlags
0x18003d2d2  mov     r8, rdi; pwszObjectName
0x18003d2d5  mov     [rsp+88h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x18003d2de  mov     rdx, r14; pwszVerb
0x18003d2e1  mov     [rsp+88h+pwszReferrer], 0; pwszReferrer
0x18003d2ea  call    cs:__imp_WinHttpOpenRequest
0x18003d2f0  mov     [rbp+8], rax
0x18003d2f4  mov     r15d, 2
0x18003d2fa  test    rax, rax
0x18003d2fd  jz      short loc_18003D347
0x18003d2ff  xor     edi, edi
0x18003d301  mov     rcx, [rbp+8]; hInternet
0x18003d305  lea     rdx, ?AsyncCallback@WinHttpRequest@@KAXPEAX_KK0K@Z; lpfnInternetCallback
0x18003d30c  mov     r14d, 6F4800h
0x18003d312  xor     r9d, r9d; dwReserved
0x18003d315  mov     r8d, r14d; dwNotificationFlags
0x18003d318  call    cs:__imp_WinHttpSetStatusCallback
0x18003d31e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003d322  jnz     loc_18003D3AE
0x18003d328  call    cs:__imp_GetLastError
0x18003d32e  mov     edx, eax; unsigned int
0x18003d330  mov     ecx, r14d; unsigned int
0x18003d333  mov     edi, eax
0x18003d335  call    ?WriteWinhttpSetCallbackFailureEvent@Logger@@SAJKK@Z; Logger::WriteWinhttpSetCallbackFailureEvent(ulong,ulong)
0x18003d33a  test    edi, edi
0x18003d33c  jz      short loc_18003D3AE
0x18003d33e  lea     r8, aWinhttpsetstat_0; "WinHttpSetStatusCallback"
0x18003d345  jmp     short loc_18003D397
0x18003d347  call    cs:__imp_GetLastError
0x18003d34d  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, r15b
0x18003d354  mov     edi, eax
0x18003d356  jz      short loc_18003D388
0x18003d358  mov     r9d, r12d
0x18003d35b  mov     dword ptr [rsp+88h+pwszReferrer], eax
0x18003d35f  mov     r8, r14
0x18003d362  call    McTemplateU0zqq_EventWriteTransfer
0x18003d367  test    eax, eax
0x18003d369  jz      short loc_18003D388
0x18003d36b  mov     r9d, eax
0x18003d36e  lea     r8, aEventwritewinh_13; "EventWriteWinhttpOpenRequestFailureEven"...
0x18003d375  lea     rdx, aLoggerWritewin_7; "Logger::WriteWinhttpOpenRequestFailureE"...
0x18003d37c  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18003d383  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003d388  test    edi, edi
0x18003d38a  jz      loc_18003D301
0x18003d390  lea     r8, aWinhttpopenreq_0; "WinHttpOpenRequest"
0x18003d397  mov     r9d, edi
0x18003d39a  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18003d3a1  mov     rdx, rsi
0x18003d3a4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003d3a9  jmp     loc_18003D4DF
0x18003d3ae  cmp     dword ptr [rbp+0A4h], 0
0x18003d3b5  jnz     loc_18003D491
0x18003d3bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d3c2  mov     ecx, 10h; unsigned __int64
0x18003d3c7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003d3cc  mov     [rsp+88h+arg_8], rax
0x18003d3d4  test    rax, rax
0x18003d3d7  jz      loc_18003D4E7
0x18003d3dd  xorps   xmm0, xmm0
0x18003d3e0  lea     rcx, ??_7WinHttpHandle@@6B@; const WinHttpHandle::`vftable'
0x18003d3e7  movups  xmmword ptr [rax], xmm0
0x18003d3ea  mov     [rax], rcx
0x18003d3ed  mov     qword ptr [rax+8], 0
0x18003d3f5  sub     r15d, 1
0x18003d3f9  jnz     short loc_18003D3ED
0x18003d3fb  lea     rcx, ??_7WinHttpHandle@@6B@; const WinHttpHandle::`vftable'
0x18003d402  mov     [rax], rcx
0x18003d405  test    rax, rax
0x18003d408  jz      loc_18003D4E7
0x18003d40e  mov     rdx, [rbp+78h]
0x18003d412  mov     [rbp+78h], rax
0x18003d416  test    rdx, rdx
0x18003d419  jz      short loc_18003D420
0x18003d41b  call    ??R?$default_delete@VWinHttpProxyResolver@@@std@@QEBAXPEAVWinHttpProxyResolver@@@Z; std::default_delete<WinHttpProxyResolver>::operator()(WinHttpProxyResolver *)
0x18003d420  mov     rcx, [rbp+78h]; this
0x18003d424  mov     rdx, r13; struct WinHttpSession *
0x18003d427  call    ?Initialize@WinHttpProxyResolver@@QEAAJAEAVWinHttpSession@@@Z; WinHttpProxyResolver::Initialize(WinHttpSession &)
0x18003d42c  mov     ebx, eax
0x18003d42e  test    eax, eax
0x18003d430  jns     short loc_18003D450
0x18003d432  mov     r9d, eax
0x18003d435  lea     r8, aWinhttpproxyre_0; "WinHttpProxyResolver::Intialize"
0x18003d43c  mov     rdx, rsi
0x18003d43f  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x18003d446  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003d44b  jmp     loc_18003D4DB
0x18003d450  mov     rcx, [rbp+78h]
0x18003d454  lea     rdx, ?AsyncCallback@WinHttpRequest@@KAXPEAX_KK0K@Z; lpfnInternetCallback
0x18003d45b  mov     r14d, 1200000h
0x18003d461  xor     r9d, r9d; dwReserved
0x18003d464  mov     r8d, r14d; dwNotificationFlags
0x18003d467  mov     rcx, [rcx+8]; hInternet
0x18003d46b  call    cs:__imp_WinHttpSetStatusCallback
0x18003d471  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003d475  jnz     short loc_18003D491
0x18003d477  call    cs:__imp_GetLastError
0x18003d47d  mov     edx, eax; unsigned int
0x18003d47f  mov     ecx, r14d; unsigned int
0x18003d482  mov     edi, eax
0x18003d484  call    ?WriteWinhttpSetCallbackFailureEvent@Logger@@SAJKK@Z; Logger::WriteWinhttpSetCallbackFailureEvent(ulong,ulong)
0x18003d489  test    edi, edi
0x18003d48b  jnz     loc_18003D33E
0x18003d491  mov     eax, [rbp+0A8h]
0x18003d497  xor     edx, edx; nResolveTimeout
0x18003d499  mov     rcx, [rbp+8]; hInternet
0x18003d49d  mov     r9d, 7530h; nSendTimeout
0x18003d4a3  mov     r8d, 0EA60h; nConnectTimeout
0x18003d4a9  mov     dword ptr [rsp+88h+pwszReferrer], eax; nReceiveTimeout
0x18003d4ad  call    cs:__imp_WinHttpSetTimeouts
0x18003d4b3  test    eax, eax
0x18003d4b5  jnz     short loc_18003D4DB
0x18003d4b7  call    cs:__imp_GetLastError
0x18003d4bd  test    eax, eax
0x18003d4bf  jle     short loc_18003D4C9
0x18003d4c1  movzx   eax, ax
0x18003d4c4  or      eax, 80070000h
0x18003d4c9  mov     r8d, eax
0x18003d4cc  lea     rcx, aSWinhttpsettim; "%s: WinHttpSetTimeouts failed with erro"...
0x18003d4d3  mov     rdx, rsi
0x18003d4d6  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18003d4db  test    edi, edi
0x18003d4dd  jz      short loc_18003D506
0x18003d4df  test    edi, edi
0x18003d4e1  jg      short loc_18003D4FD
0x18003d4e3  mov     ebx, edi
0x18003d4e5  jmp     short loc_18003D506
0x18003d4e7  mov     rdx, rsi
0x18003d4ea  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18003d4f1  mov     ebx, 8007000Eh
0x18003d4f6  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18003d4fb  jmp     short loc_18003D4DB
0x18003d4fd  movzx   ebx, di
0x18003d500  or      ebx, 80070000h
0x18003d506  mov     eax, ebx
0x18003d508  add     rsp, 48h
0x18003d50c  pop     r15
0x18003d50e  pop     r14
0x18003d510  pop     r13
0x18003d512  pop     r12
0x18003d514  pop     rdi
0x18003d515  pop     rsi
0x18003d516  pop     rbp
0x18003d517  pop     rbx
0x18003d518  retn
```
