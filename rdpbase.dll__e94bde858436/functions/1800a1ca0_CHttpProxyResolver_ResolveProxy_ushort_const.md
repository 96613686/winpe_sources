# CHttpProxyResolver::ResolveProxy(ushort const *)

- ea: `0x1800a1ca0`
- end: `0x1800a231d`
- name: `?ResolveProxy@CHttpProxyResolver@@UEAAJPEBG@Z`
- size: `1661`
- prototype: `int(CHttpProxyResolver *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800018a4`
- `0x180002550`
- `0x1800025dc`
- `0x180004970`
- `0x180004a94`
- `0x180004f70`
- `0x180005820`
- `0x1800a1704`
- `0x1800a1ca0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1f37`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a21f9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a22b4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a22c7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a22da`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a21f9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a22b4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a22c7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a22da`
- `WINHTTP!WinHttpOpen` at `0x1800a1f21`
- `WINHTTP!WinHttpOpen` at `0x1800a1f21`
- `WINHTTP!WinHttpCloseHandle` at `0x1800a22ec`
- `WINHTTP!WinHttpCloseHandle` at `0x1800a22ec`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800a1d66`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800a1d66`

## string_xrefs

- `0x1800a1dce`: `WinHttpGetIEProxyConfigForCurrentUser returned error %d; bailing`
- `0x1800a1e67`: `WinHttpGetIEProxyConfigForCurrentUser returned info:`
- `0x1800a1ec0`: `Autodetect:%d, Autoconfig URL: %s, Proxy: %s, Proxy bypass: %s`
- `0x1800a1f85`: `WinHttpOpen in ResolveProxy failed`
- `0x1800a208a`: `Failed in autodetect; falling back to autoconfig URL or static settings`
- `0x1800a20d7`: `Trying autoconfig URL %s`
- `0x1800a2130`: `Retrieved proxy info via autoconfig URL, proxy: %s proxybypass: %s`

## pseudocode

```c
__int64 __fastcall CHttpProxyResolver::ResolveProxy(
        CHttpProxyResolver *this,
        const unsigned __int16 *a2,
        int a3,
        int a4)
{
  int v4; // r12d
  char *v7; // rsi
  unsigned int v8; // edi
  signed int LastError; // ebx
  CHttpProxyResolver *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  unsigned int v16; // eax
  signed int v17; // eax
  int v18; // r8d
  int v19; // r9d
  char *v20; // rax
  char *v21; // rdx
  char *v22; // rsi
  unsigned __int16 *v23; // r14
  char *v25; // [rsp+50h] [rbp-29h] BYREF
  const char *lpszProxy; // [rsp+58h] [rbp-21h] BYREF
  LPWSTR lpszProxyBypass; // [rsp+60h] [rbp-19h] BYREF
  LPWSTR lpszAutoConfigUrl; // [rsp+68h] [rbp-11h] BYREF
  const char *v29; // [rsp+70h] [rbp-9h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+78h] [rbp-1h] BYREF
  const char *v31; // [rsp+E0h] [rbp+67h] BYREF
  unsigned __int16 *v32; // [rsp+F0h] [rbp+77h] BYREF
  HGLOBAL hMem; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = 0;
  v7 = 0;
  v32 = 0;
  v8 = -2147020579;
  hMem = 0;
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  v25 = 0;
  if ( *((_DWORD *)this + 3) )
  {
    LastError = 4317;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v31) = 459;
      hMem = "ResolveProxy";
      LODWORD(v32) = -2147020579;
      v25 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttpproxyresolver\\proxyresolver.cpp";
      lpszProxy = "ResolveProxy being called a second time?";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)byte_1801B3729,
        a3,
        a4,
        (__int64)&lpszProxy,
        (__int64)&v32,
        (__int64)&v25,
        (__int64)&v31,
        (__int64)&hMem);
    }
    goto LABEL_55;
  }
  if ( WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v31 = "WinHttpGetIEProxyConfigForCurrentUser returned info:";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)byte_1801B3699,
        0,
        v12,
        (__int64)&v31);
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      lpszProxyBypass = pProxyConfig.lpszProxyBypass;
      lpszProxy = (const char *)pProxyConfig.lpszProxy;
      lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
      LODWORD(v31) = pProxyConfig.fAutoDetect;
      v29 = "Autodetect:%d, Autoconfig URL: %s, Proxy: %s, Proxy bypass: %s";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v10,
        (unsigned int)&dword_1801B360C,
        v11,
        v12,
        (__int64)&v29,
        (__int64)&v31,
        (__int64)&lpszAutoConfigUrl,
        (__int64)&lpszProxy,
        (__int64)&lpszProxyBypass);
    }
    if ( !pProxyConfig.fAutoDetect && !pProxyConfig.lpszAutoConfigUrl )
      goto LABEL_43;
    goto LABEL_20;
  }
  LastError = GetLastError();
  if ( LastError == 2 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      v31 = "No IE proxy settings found, trying autodetect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)word_1801B36BA,
        0,
        v15,
        (__int64)&v31);
    }
    pProxyConfig.fAutoDetect = 1;
LABEL_20:
    v25 = (char *)WinHttpOpen(L"ProxyResolver/1.0", 0, 0, 0, 0);
    v7 = v25;
    if ( !v25 )
    {
      v17 = GetLastError();
      LastError = v17;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v31) = 512;
        hMem = "ResolveProxy";
        v29 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttpproxyresolver\\proxyresolver.cpp";
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        LODWORD(v32) = v17;
        lpszAutoConfigUrl = (LPWSTR)"WinHttpOpen in ResolveProxy failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&byte_1801B35C7,
          v18,
          v19,
          (__int64)&lpszAutoConfigUrl,
          (__int64)&v32,
          (__int64)&v29,
          (__int64)&v31,
          (__int64)&hMem);
      }
LABEL_54:
      v8 = -2147020579;
      goto LABEL_55;
    }
    if ( pProxyConfig.fAutoDetect )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v31 = "Trying autodetect";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)&word_1801B35A6,
          0,
          v12,
          (__int64)&v31);
      }
      LastError = CHttpProxyResolver::GetProxyForAutoSettings(v10, v25, a2, 0, &v32, (unsigned __int16 **)&hMem);
      if ( !LastError )
      {
        v4 = 1;
        if ( (unsigned int)CallbackContext > 4 )
        {
          v20 = "Retrieved proxy info via autodetect process, proxy: %s proxybypass: %s";
          v21 = byte_1801B3569;
LABEL_31:
          v22 = (char *)hMem;
          v23 = v32;
          hMem = v20;
          v31 = v22;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v10,
            (_DWORD)v21,
            v11,
            v12,
            (__int64)&hMem,
            (__int64)&v32,
            (__int64)&v31);
LABEL_44:
          *((_DWORD *)this + 12) = v4;
          if ( v23 )
          {
            *((_DWORD *)this + 6) = 3;
            *((_DWORD *)this + 3) = 1;
            *((_QWORD *)this + 4) = v23;
            *((_QWORD *)this + 5) = v22;
            if ( (unsigned int)CallbackContext > 4 )
            {
              v31 = (const char *)*((_QWORD *)this + 5);
              v32 = (unsigned __int16 *)*((_QWORD *)this + 4);
              hMem = "Retrieved proxy information, proxy %s proxybypass %s";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                (_DWORD)v10,
                (unsigned int)word_1801B33FA,
                v11,
                v12,
                (__int64)&hMem,
                (__int64)&v32,
                (__int64)&v31);
            }
            if ( (unsigned int)CallbackContext > 4 )
            {
              LODWORD(v31) = v4;
              v32 = (unsigned __int16 *)"Proxy failover valid? %d";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                (_DWORD)v10,
                (unsigned int)byte_1801B33C9,
                v11,
                v12,
                (__int64)&v32,
                (__int64)&v31);
            }
          }
          else
          {
            *((_DWORD *)this + 6) = 1;
            if ( (unsigned int)CallbackContext > 4 )
            {
              v31 = "No forward proxy will be used";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                (unsigned int)&CallbackContext,
                (unsigned int)byte_1801B3455,
                0,
                v12,
                (__int64)&v31);
            }
            if ( v22 )
              GlobalFree(v22);
          }
          v7 = v25;
          goto LABEL_54;
        }
        goto LABEL_40;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v31 = "Failed in autodetect; falling back to autoconfig URL or static settings";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)qword_1801B3548,
          0,
          v12,
          (__int64)&v31);
      }
    }
    if ( pProxyConfig.lpszAutoConfigUrl )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v31 = (const char *)pProxyConfig.lpszAutoConfigUrl;
        v29 = "Trying autoconfig URL %s";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v10,
          (unsigned int)qword_1801B3508,
          v11,
          v12,
          (__int64)&v29,
          (__int64)&v31);
      }
      LastError = CHttpProxyResolver::GetProxyForAutoSettings(
                    v10,
                    v25,
                    a2,
                    pProxyConfig.lpszAutoConfigUrl,
                    &v32,
                    (unsigned __int16 **)&hMem);
      if ( !LastError )
      {
        v4 = 1;
        if ( (unsigned int)CallbackContext > 4 )
        {
          v20 = "Retrieved proxy info via autoconfig URL, proxy: %s proxybypass: %s";
          v21 = byte_1801B34CB;
          goto LABEL_31;
        }
LABEL_40:
        v23 = v32;
        v22 = (char *)hMem;
        goto LABEL_44;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v31 = (const char *)pProxyConfig.lpszProxyBypass;
        v32 = pProxyConfig.lpszProxy;
        hMem = "Falling back to static settings: proxy: %s, proxy bypass: %s";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v10,
          (unsigned int)&word_1801B3476,
          v11,
          v12,
          (__int64)&hMem,
          (__int64)&v32,
          (__int64)&v31);
      }
    }
LABEL_43:
    v23 = pProxyConfig.lpszProxy;
    LastError = 0;
    v22 = (char *)pProxyConfig.lpszProxyBypass;
    pProxyConfig.lpszProxy = 0;
    pProxyConfig.lpszProxyBypass = 0;
    goto LABEL_44;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v31) = LastError;
    lpszProxy = "ResolveProxy";
    v25 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttpproxyresolver\\proxyresolver.cpp";
    LODWORD(v32) = 468;
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    else
      v16 = LastError;
    LODWORD(hMem) = v16;
    lpszProxyBypass = (LPWSTR)"WinHttpGetIEProxyConfigForCurrentUser returned error %d; bailing";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)byte_1801B36DB,
      v14,
      v15,
      (__int64)&lpszProxyBypass,
      (__int64)&hMem,
      (__int64)&v25,
      (__int64)&v32,
      (__int64)&lpszProxy,
      (__int64)&v31);
  }
LABEL_55:
  if ( pProxyConfig.lpszAutoConfigUrl )
  {
    GlobalFree(pProxyConfig.lpszAutoConfigUrl);
    pProxyConfig.lpszAutoConfigUrl = 0;
  }
  if ( pProxyConfig.lpszProxy )
  {
    GlobalFree(pProxyConfig.lpszProxy);
    pProxyConfig.lpszProxy = 0;
  }
  if ( pProxyConfig.lpszProxyBypass )
  {
    GlobalFree(pProxyConfig.lpszProxyBypass);
    pProxyConfig.lpszProxyBypass = 0;
  }
  if ( v7 )
    WinHttpCloseHandle(v7);
  if ( LastError )
  {
    if ( LastError != 4317 )
      return (unsigned int)-2147467259;
  }
  else
  {
    return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x1800a1ca0  push    rbp
0x1800a1ca2  push    rbx
0x1800a1ca3  push    rsi
0x1800a1ca4  push    rdi
0x1800a1ca5  push    r12
0x1800a1ca7  push    r14
0x1800a1ca9  push    r15
0x1800a1cab  lea     rbp, [rsp-27h]
0x1800a1cb0  sub     rsp, 0A0h
0x1800a1cb7  xor     r12d, r12d
0x1800a1cba  xorps   xmm0, xmm0
0x1800a1cbd  mov     r14, rdx
0x1800a1cc0  mov     r15, rcx
0x1800a1cc3  mov     esi, r12d
0x1800a1cc6  mov     [rbp+57h+arg_10], r12
0x1800a1cca  mov     edi, 800710DDh
0x1800a1ccf  mov     [rbp+57h+hMem], r12
0x1800a1cd3  movups  xmmword ptr [rbp+57h+pProxyConfig.fAutoDetect], xmm0
0x1800a1cd7  mov     [rbp+57h+var_80], r12
0x1800a1cdb  movups  xmmword ptr [rbp+57h+pProxyConfig.lpszProxy], xmm0
0x1800a1cdf  cmp     [rcx+0Ch], r12d
0x1800a1ce3  jz      short loc_1800A1D62
0x1800a1ce5  mov     eax, cs:CallbackContext
0x1800a1ceb  mov     ebx, 10DDh
0x1800a1cf0  cmp     eax, 2
0x1800a1cf3  jbe     loc_1800A22AB
0x1800a1cf9  lea     rax, aResolveproxy; "ResolveProxy"
0x1800a1d00  mov     dword ptr [rbp+57h+arg_0], 1CBh
0x1800a1d07  mov     [rbp+57h+hMem], rax
0x1800a1d0b  lea     rdx, byte_1801B3729
0x1800a1d12  lea     rax, aOnecoreTermsrv_80; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x1800a1d19  mov     dword ptr [rbp+57h+arg_10], edi
0x1800a1d1c  mov     [rbp+57h+var_80], rax
0x1800a1d20  lea     rax, aResolveproxyBe; "ResolveProxy being called a second time"...
0x1800a1d27  mov     [rbp+57h+var_78], rax
0x1800a1d2b  lea     rax, [rbp+57h+hMem]
0x1800a1d2f  mov     [rsp+0D0h+var_90], rax
0x1800a1d34  lea     rax, [rbp+57h+arg_0]
0x1800a1d38  mov     [rsp+0D0h+var_98], rax
0x1800a1d3d  lea     rax, [rbp+57h+var_80]
0x1800a1d41  mov     [rsp+0D0h+var_A0], rax
0x1800a1d46  lea     rax, [rbp+57h+arg_10]
0x1800a1d4a  mov     [rsp+0D0h+var_A8], rax
0x1800a1d4f  lea     rax, [rbp+57h+var_78]
0x1800a1d53  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a1d58  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800a1d5d  jmp     loc_1800A22AB
0x1800a1d62  lea     rcx, [rbp+57h+pProxyConfig]; pProxyConfig
0x1800a1d66  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800a1d6c  test    eax, eax
0x1800a1d6e  jnz     loc_1800A1E58
0x1800a1d74  call    cs:__imp_GetLastError
0x1800a1d7a  mov     ebx, eax
0x1800a1d7c  cmp     eax, 2
0x1800a1d7f  mov     eax, cs:CallbackContext
0x1800a1d85  jz      loc_1800A1E19
0x1800a1d8b  cmp     eax, 2
0x1800a1d8e  jbe     loc_1800A22AB
0x1800a1d94  mov     dword ptr [rbp+57h+arg_0], ebx
0x1800a1d97  lea     rax, aResolveproxy; "ResolveProxy"
0x1800a1d9e  mov     [rbp+57h+var_78], rax
0x1800a1da2  lea     rax, aOnecoreTermsrv_80; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x1800a1da9  mov     [rbp+57h+var_80], rax
0x1800a1dad  mov     dword ptr [rbp+57h+arg_10], 1D4h
0x1800a1db4  test    ebx, ebx
0x1800a1db6  jg      short loc_1800A1DBC
0x1800a1db8  mov     eax, ebx
0x1800a1dba  jmp     short loc_1800A1DC4
0x1800a1dbc  movzx   eax, bx
0x1800a1dbf  or      eax, 80070000h
0x1800a1dc4  mov     dword ptr [rbp+57h+hMem], eax
0x1800a1dc7  lea     rdx, byte_1801B36DB
0x1800a1dce  lea     rax, aWinhttpgetiepr_1; "WinHttpGetIEProxyConfigForCurrentUser r"...
0x1800a1dd5  mov     [rbp+57h+var_70], rax
0x1800a1dd9  lea     rax, [rbp+57h+arg_0]
0x1800a1ddd  mov     [rsp+0D0h+var_88], rax
0x1800a1de2  lea     rax, [rbp+57h+var_78]
0x1800a1de6  mov     [rsp+0D0h+var_90], rax
0x1800a1deb  lea     rax, [rbp+57h+arg_10]
0x1800a1def  mov     [rsp+0D0h+var_98], rax
0x1800a1df4  lea     rax, [rbp+57h+var_80]
0x1800a1df8  mov     [rsp+0D0h+var_A0], rax
0x1800a1dfd  lea     rax, [rbp+57h+hMem]
0x1800a1e01  mov     [rsp+0D0h+var_A8], rax
0x1800a1e06  lea     rax, [rbp+57h+var_70]
0x1800a1e0a  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a1e0f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a1e14  jmp     loc_1800A22AB
0x1800a1e19  mov     edi, 4
0x1800a1e1e  cmp     eax, edi
0x1800a1e20  jbe     short loc_1800A1E4C
0x1800a1e22  lea     rax, aNoIeProxySetti; "No IE proxy settings found, trying auto"...
0x1800a1e29  xor     r8d, r8d
0x1800a1e2c  mov     [rbp+57h+arg_0], rax
0x1800a1e30  lea     rdx, word_1801B36BA
0x1800a1e37  lea     rax, [rbp+57h+arg_0]
0x1800a1e3b  lea     rcx, CallbackContext
0x1800a1e42  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a1e47  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800a1e4c  mov     [rbp+57h+pProxyConfig.fAutoDetect], 1
0x1800a1e53  jmp     loc_1800A1F0D
0x1800a1e58  mov     eax, cs:CallbackContext
0x1800a1e5e  mov     edi, 4
0x1800a1e63  cmp     eax, edi
0x1800a1e65  jbe     short loc_1800A1E91
0x1800a1e67  lea     rax, aWinhttpgetiepr_0; "WinHttpGetIEProxyConfigForCurrentUser r"...
0x1800a1e6e  xor     r8d, r8d
0x1800a1e71  mov     [rbp+57h+arg_0], rax
0x1800a1e75  lea     rdx, byte_1801B3699
0x1800a1e7c  lea     rax, [rbp+57h+arg_0]
0x1800a1e80  lea     rcx, CallbackContext
0x1800a1e87  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a1e8c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800a1e91  mov     eax, cs:CallbackContext
0x1800a1e97  cmp     eax, edi
0x1800a1e99  jbe     short loc_1800A1EFD
0x1800a1e9b  mov     rax, [rbp+57h+pProxyConfig.lpszProxyBypass]
0x1800a1e9f  lea     rdx, dword_1801B360C
0x1800a1ea6  mov     [rbp+57h+var_70], rax
0x1800a1eaa  mov     rax, [rbp+57h+pProxyConfig.lpszProxy]
0x1800a1eae  mov     [rbp+57h+var_78], rax
0x1800a1eb2  mov     rax, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x1800a1eb6  mov     [rbp+57h+var_68], rax
0x1800a1eba  mov     eax, [rbp+57h+pProxyConfig.fAutoDetect]
0x1800a1ebd  mov     dword ptr [rbp+57h+arg_0], eax
0x1800a1ec0  lea     rax, aAutodetectDAut; "Autodetect:%d, Autoconfig URL: %s, Prox"...
0x1800a1ec7  mov     [rbp+57h+var_60], rax
0x1800a1ecb  lea     rax, [rbp+57h+var_70]
0x1800a1ecf  mov     [rsp+0D0h+var_90], rax
0x1800a1ed4  lea     rax, [rbp+57h+var_78]
0x1800a1ed8  mov     [rsp+0D0h+var_98], rax
0x1800a1edd  lea     rax, [rbp+57h+var_68]
0x1800a1ee1  mov     [rsp+0D0h+var_A0], rax
0x1800a1ee6  lea     rax, [rbp+57h+arg_0]
0x1800a1eea  mov     [rsp+0D0h+var_A8], rax
0x1800a1eef  lea     rax, [rbp+57h+var_60]
0x1800a1ef3  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a1ef8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800a1efd  cmp     [rbp+57h+pProxyConfig.fAutoDetect], r12d
0x1800a1f01  jnz     short loc_1800A1F0D
0x1800a1f03  cmp     [rbp+57h+pProxyConfig.lpszAutoConfigUrl], r12
0x1800a1f07  jz      loc_1800A2193
0x1800a1f0d  xor     r9d, r9d; pszProxyBypassW
0x1800a1f10  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x1800a1f15  xor     r8d, r8d; pszProxyW
0x1800a1f18  lea     rcx, pszAgentW; "ProxyResolver/1.0"
0x1800a1f1f  xor     edx, edx; dwAccessType
0x1800a1f21  call    cs:__imp_WinHttpOpen
0x1800a1f27  mov     [rbp+57h+var_80], rax
0x1800a1f2b  mov     rsi, rax
0x1800a1f2e  test    rax, rax
0x1800a1f31  jnz     loc_1800A1FC7
0x1800a1f37  call    cs:__imp_GetLastError
0x1800a1f3d  mov     ecx, cs:CallbackContext
0x1800a1f43  mov     ebx, eax
0x1800a1f45  cmp     ecx, 2
0x1800a1f48  jbe     loc_1800A22A6
0x1800a1f4e  mov     dword ptr [rbp+57h+arg_0], 200h
0x1800a1f55  lea     rax, aResolveproxy; "ResolveProxy"
0x1800a1f5c  mov     [rbp+57h+hMem], rax
0x1800a1f60  lea     rax, aOnecoreTermsrv_80; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x1800a1f67  mov     [rbp+57h+var_60], rax
0x1800a1f6b  test    ebx, ebx
0x1800a1f6d  jg      short loc_1800A1F73
0x1800a1f6f  mov     eax, ebx
0x1800a1f71  jmp     short loc_1800A1F7B
0x1800a1f73  movzx   eax, bx
0x1800a1f76  or      eax, 80070000h
0x1800a1f7b  mov     dword ptr [rbp+57h+arg_10], eax
0x1800a1f7e  lea     rdx, byte_1801B35C7
0x1800a1f85  lea     rax, aWinhttpopenInR; "WinHttpOpen in ResolveProxy failed"
0x1800a1f8c  mov     [rbp+57h+var_68], rax
0x1800a1f90  lea     rax, [rbp+57h+hMem]
0x1800a1f94  mov     [rsp+0D0h+var_90], rax
0x1800a1f99  lea     rax, [rbp+57h+arg_0]
0x1800a1f9d  mov     [rsp+0D0h+var_98], rax
0x1800a1fa2  lea     rax, [rbp+57h+var_60]
0x1800a1fa6  mov     [rsp+0D0h+var_A0], rax
0x1800a1fab  lea     rax, [rbp+57h+arg_10]
0x1800a1faf  mov     [rsp+0D0h+var_A8], rax
0x1800a1fb4  lea     rax, [rbp+57h+var_68]
0x1800a1fb8  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a1fbd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800a1fc2  jmp     loc_1800A22A6
0x1800a1fc7  cmp     [rbp+57h+pProxyConfig.fAutoDetect], r12d
0x1800a1fcb  jz      loc_1800A20B4
0x1800a1fd1  mov     eax, cs:CallbackContext
0x1800a1fd7  cmp     eax, edi
0x1800a1fd9  jbe     short loc_1800A2005
0x1800a1fdb  lea     rax, aTryingAutodete; "Trying autodetect"
0x1800a1fe2  xor     r8d, r8d
0x1800a1fe5  mov     [rbp+57h+arg_0], rax
0x1800a1fe9  lea     rdx, word_1801B35A6
0x1800a1ff0  lea     rax, [rbp+57h+arg_0]
0x1800a1ff4  lea     rcx, CallbackContext
0x1800a1ffb  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a2000  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800a2005  lea     rax, [rbp+57h+hMem]
0x1800a2009  xor     r9d, r9d; unsigned __int16 *
0x1800a200c  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x1800a2011  mov     r8, r14; unsigned __int16 *
0x1800a2014  lea     rax, [rbp+57h+arg_10]
0x1800a2018  mov     rdx, rsi; void *
0x1800a201b  mov     qword ptr [rsp+0D0h+dwFlags], rax; unsigned __int16 **
0x1800a2020  call    ?GetProxyForAutoSettings@CHttpProxyResolver@@AEAAKPEAXPEBG1PEAPEAG2@Z; CHttpProxyResolver::GetProxyForAutoSettings(void *,ushort const *,ushort const *,ushort * *,ushort * *)
0x1800a2025  mov     ebx, eax
0x1800a2027  test    eax, eax
0x1800a2029  mov     eax, cs:CallbackContext
0x1800a202f  jnz     short loc_1800A2086
0x1800a2031  mov     r12d, 1
0x1800a2037  cmp     eax, edi
0x1800a2039  jbe     loc_1800A2143
0x1800a203f  lea     rax, aRetrievedProxy_0; "Retrieved proxy info via autodetect pro"...
0x1800a2046  lea     rdx, byte_1801B3569
0x1800a204d  mov     rsi, [rbp+57h+hMem]
0x1800a2051  mov     r14, [rbp+57h+arg_10]
0x1800a2055  mov     [rbp+57h+hMem], rax
0x1800a2059  lea     rax, [rbp+57h+arg_0]
0x1800a205d  mov     [rsp+0D0h+var_A0], rax
0x1800a2062  lea     rax, [rbp+57h+arg_10]
0x1800a2066  mov     [rsp+0D0h+var_A8], rax
0x1800a206b  lea     rax, [rbp+57h+hMem]
0x1800a206f  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a2074  mov     [rbp+57h+arg_10], r14
0x1800a2078  mov     [rbp+57h+arg_0], rsi
0x1800a207c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800a2081  jmp     loc_1800A21A5
0x1800a2086  cmp     eax, edi
0x1800a2088  jbe     short loc_1800A20B4
0x1800a208a  lea     rax, aFailedInAutode; "Failed in autodetect; falling back to a"...
0x1800a2091  xor     r8d, r8d
0x1800a2094  mov     [rbp+57h+arg_0], rax
0x1800a2098  lea     rdx, qword_1801B3548
0x1800a209f  lea     rax, [rbp+57h+arg_0]
0x1800a20a3  lea     rcx, CallbackContext
0x1800a20aa  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a20af  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800a20b4  cmp     [rbp+57h+pProxyConfig.lpszAutoConfigUrl], r12
0x1800a20b8  jz      loc_1800A2193
0x1800a20be  mov     eax, cs:CallbackContext
0x1800a20c4  cmp     eax, edi
0x1800a20c6  jbe     short loc_1800A20F9
0x1800a20c8  mov     rax, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x1800a20cc  lea     rdx, qword_1801B3508
0x1800a20d3  mov     [rbp+57h+arg_0], rax
0x1800a20d7  lea     rax, aTryingAutoconf; "Trying autoconfig URL %s"
0x1800a20de  mov     [rbp+57h+var_60], rax
0x1800a20e2  lea     rax, [rbp+57h+arg_0]
0x1800a20e6  mov     [rsp+0D0h+var_A8], rax
0x1800a20eb  lea     rax, [rbp+57h+var_60]
0x1800a20ef  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a20f4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800a20f9  mov     r9, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]; unsigned __int16 *
0x1800a20fd  lea     rax, [rbp+57h+hMem]
0x1800a2101  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x1800a2106  mov     r8, r14; unsigned __int16 *
0x1800a2109  lea     rax, [rbp+57h+arg_10]
0x1800a210d  mov     rdx, rsi; void *
0x1800a2110  mov     qword ptr [rsp+0D0h+dwFlags], rax; unsigned __int16 **
0x1800a2115  call    ?GetProxyForAutoSettings@CHttpProxyResolver@@AEAAKPEAXPEBG1PEAPEAG2@Z; CHttpProxyResolver::GetProxyForAutoSettings(void *,ushort const *,ushort const *,ushort * *,ushort * *)
0x1800a211a  mov     ebx, eax
0x1800a211c  test    eax, eax
0x1800a211e  mov     eax, cs:CallbackContext
0x1800a2124  jnz     short loc_1800A214D
0x1800a2126  mov     r12d, 1
0x1800a212c  cmp     eax, edi
0x1800a212e  jbe     short loc_1800A2143
0x1800a2130  lea     rax, aRetrievedProxy_1; "Retrieved proxy info via autoconfig URL"...
0x1800a2137  lea     rdx, byte_1801B34CB
0x1800a213e  jmp     loc_1800A204D
0x1800a2143  mov     r14, [rbp+57h+arg_10]
0x1800a2147  mov     rsi, [rbp+57h+hMem]
0x1800a214b  jmp     short loc_1800A21A5
0x1800a214d  cmp     eax, edi
0x1800a214f  jbe     short loc_1800A2193
0x1800a2151  mov     rax, [rbp+57h+pProxyConfig.lpszProxyBypass]
0x1800a2155  lea     rdx, word_1801B3476
0x1800a215c  mov     [rbp+57h+arg_0], rax
0x1800a2160  mov     rax, [rbp+57h+pProxyConfig.lpszProxy]
0x1800a2164  mov     [rbp+57h+arg_10], rax
0x1800a2168  lea     rax, aFallingBackToS; "Falling back to static settings: proxy:"...
0x1800a216f  mov     [rbp+57h+hMem], rax
0x1800a2173  lea     rax, [rbp+57h+arg_0]
0x1800a2177  mov     [rsp+0D0h+var_A0], rax
0x1800a217c  lea     rax, [rbp+57h+arg_10]
0x1800a2180  mov     [rsp+0D0h+var_A8], rax
0x1800a2185  lea     rax, [rbp+57h+hMem]
0x1800a2189  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x1800a218e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800a2193  mov     r14, [rbp+57h+pProxyConfig.lpszProxy]
0x1800a2197  xor     ebx, ebx
0x1800a2199  mov     rsi, [rbp+57h+pProxyConfig.lpszProxyBypass]
0x1800a219d  mov     [rbp+57h+pProxyConfig.lpszProxy], r12
0x1800a21a1  mov     [rbp+57h+pProxyConfig.lpszProxyBypass], r12
0x1800a21a5  mov     [r15+30h], r12d
0x1800a21a9  test    r14, r14
0x1800a21ac  jnz     short loc_1800A2204
0x1800a21ae  mov     dword ptr [r15+18h], 1
0x1800a21b6  mov     eax, cs:CallbackContext
0x1800a21bc  cmp     eax, edi
  ... truncated ...
```
