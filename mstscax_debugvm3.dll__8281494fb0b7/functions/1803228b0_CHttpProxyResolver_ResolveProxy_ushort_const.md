# CHttpProxyResolver::ResolveProxy(ushort const *)

- ea: `0x1803228b0`
- end: `0x180322f34`
- name: `?ResolveProxy@CHttpProxyResolver@@UEAAJPEBG@Z`
- size: `1668`
- prototype: `int(CHttpProxyResolver *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800011f4`
- `0x180001e8c`
- `0x1800031a8`
- `0x180005ccc`
- `0x18000608c`
- `0x1800829d4`
- `0x180082ad8`
- `0x180322314`
- `0x1803228b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180322984`
- `KERNEL32!GetLastError` at `0x180322b47`
- `KERNEL32!GetLastError` at `0x180322984`
- `KERNEL32!GetLastError` at `0x180322b47`
- `KERNEL32!GlobalFree` at `0x180322e09`
- `KERNEL32!GlobalFree` at `0x180322ecb`
- `KERNEL32!GlobalFree` at `0x180322ede`
- `KERNEL32!GlobalFree` at `0x180322ef1`
- `KERNEL32!GlobalFree` at `0x180322e09`
- `KERNEL32!GlobalFree` at `0x180322ecb`
- `KERNEL32!GlobalFree` at `0x180322ede`
- `KERNEL32!GlobalFree` at `0x180322ef1`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180322976`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180322976`
- `WINHTTP!WinHttpCloseHandle` at `0x180322f03`
- `WINHTTP!WinHttpCloseHandle` at `0x180322f03`
- `WINHTTP!WinHttpOpen` at `0x180322b31`
- `WINHTTP!WinHttpOpen` at `0x180322b31`

## string_xrefs

- `0x180322ad0`: `Autodetect:%d, Autoconfig URL: %s, Proxy: %s, Proxy bypass: %s`
- `0x180322b95`: `WinHttpOpen in ResolveProxy failed`
- `0x1803229de`: `WinHttpGetIEProxyConfigForCurrentUser returned error %d; bailing`
- `0x180322a77`: `WinHttpGetIEProxyConfigForCurrentUser returned info:`
- `0x180322c9a`: `Failed in autodetect; falling back to autoconfig URL or static settings`
- `0x180322ce7`: `Trying autoconfig URL %s`
- `0x180322d40`: `Retrieved proxy info via autoconfig URL, proxy: %s proxybypass: %s`

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
  __int16 *v21; // rdx
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
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      LODWORD(v31) = 459;
      hMem = "ResolveProxy";
      LODWORD(v32) = -2147020579;
      v25 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttpproxyresolver\\proxyresolver.cpp";
      lpszProxy = "ResolveProxy being called a second time?";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)qword_18086B2F8,
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
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v31 = "WinHttpGetIEProxyConfigForCurrentUser returned info:";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)qword_18086B430,
        0,
        v12,
        (__int64)&v31);
    }
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      lpszProxyBypass = pProxyConfig.lpszProxyBypass;
      lpszProxy = (const char *)pProxyConfig.lpszProxy;
      lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
      LODWORD(v31) = pProxyConfig.fAutoDetect;
      v29 = "Autodetect:%d, Autoconfig URL: %s, Proxy: %s, Proxy bypass: %s";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v10,
        (unsigned int)byte_18086B3A3,
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
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v31 = "No IE proxy settings found, trying autodetect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)byte_18086B289,
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
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        LODWORD(v31) = 512;
        hMem = "ResolveProxy";
        v29 = "onecore\\termsrv\\rdp\\win\\httpio\\winhttpproxyresolver\\proxyresolver.cpp";
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        LODWORD(v32) = v17;
        lpszAutoConfigUrl = (LPWSTR)"WinHttpOpen in ResolveProxy failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_1808B5850,
          (unsigned int)&word_18086B35E,
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
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v31 = "Trying autodetect";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&dword_1808B5850,
          (unsigned int)byte_18086B33D,
          0,
          v12,
          (__int64)&v31);
      }
      LastError = CHttpProxyResolver::GetProxyForAutoSettings(v10, v25, a2, 0, &v32, (unsigned __int16 **)&hMem);
      if ( !LastError )
      {
        v4 = 1;
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v20 = "Retrieved proxy info via autodetect process, proxy: %s proxybypass: %s";
          v21 = word_18086B14A;
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
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              v31 = (const char *)*((_QWORD *)this + 5);
              v32 = (unsigned __int16 *)*((_QWORD *)this + 4);
              hMem = "Retrieved proxy information, proxy %s proxybypass %s";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                (_DWORD)v10,
                (unsigned int)qword_18086B1B8,
                v11,
                v12,
                (__int64)&hMem,
                (__int64)&v32,
                (__int64)&v31);
            }
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              LODWORD(v31) = v4;
              v32 = (unsigned __int16 *)"Proxy failover valid? %d";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                (unsigned int)&dword_1808B5850,
                (unsigned int)&byte_18086B187,
                v11,
                v12,
                (__int64)&v32,
                (__int64)&v31);
            }
          }
          else
          {
            *((_DWORD *)this + 6) = 1;
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              v31 = "No forward proxy will be used";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                (unsigned int)&dword_1808B5850,
                (unsigned int)byte_18086B213,
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
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v31 = "Failed in autodetect; falling back to autoconfig URL or static settings";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&dword_1808B5850,
          (unsigned int)byte_18086B129,
          0,
          v12,
          (__int64)&v31);
      }
    }
    if ( pProxyConfig.lpszAutoConfigUrl )
    {
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v31 = (const char *)pProxyConfig.lpszAutoConfigUrl;
        v29 = "Trying autoconfig URL %s";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v10,
          (unsigned int)byte_18086B0E9,
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
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v20 = "Retrieved proxy info via autoconfig URL, proxy: %s proxybypass: %s";
          v21 = (__int16 *)&dword_18086B0AC;
          goto LABEL_31;
        }
LABEL_40:
        v23 = v32;
        v22 = (char *)hMem;
        goto LABEL_44;
      }
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v31 = (const char *)pProxyConfig.lpszProxyBypass;
        v32 = pProxyConfig.lpszProxy;
        hMem = "Falling back to static settings: proxy: %s, proxy bypass: %s";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v10,
          (unsigned int)&dword_18086B234,
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
  if ( (unsigned int)dword_1808B5850 > 2 )
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
      (unsigned int)word_18086B2AA,
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
0x1803228b0  push    rbp
0x1803228b2  push    rbx
0x1803228b3  push    rsi
0x1803228b4  push    rdi
0x1803228b5  push    r12
0x1803228b7  push    r14
0x1803228b9  push    r15
0x1803228bb  lea     rbp, [rsp-27h]
0x1803228c0  sub     rsp, 0A0h
0x1803228c7  xor     r12d, r12d
0x1803228ca  xorps   xmm0, xmm0
0x1803228cd  mov     r14, rdx
0x1803228d0  mov     r15, rcx
0x1803228d3  mov     esi, r12d
0x1803228d6  mov     [rbp+57h+arg_10], r12
0x1803228da  mov     edi, 800710DDh
0x1803228df  mov     [rbp+57h+hMem], r12
0x1803228e3  movups  xmmword ptr [rbp+57h+pProxyConfig.fAutoDetect], xmm0
0x1803228e7  mov     [rbp+57h+var_80], r12
0x1803228eb  movups  xmmword ptr [rbp+57h+pProxyConfig.lpszProxy], xmm0
0x1803228ef  cmp     [rcx+0Ch], r12d
0x1803228f3  jz      short loc_180322972
0x1803228f5  mov     eax, cs:dword_1808B5850
0x1803228fb  mov     ebx, 10DDh
0x180322900  cmp     eax, 2
0x180322903  jbe     loc_180322EC2
0x180322909  lea     rax, aResolveproxy; "ResolveProxy"
0x180322910  mov     dword ptr [rbp+57h+arg_0], 1CBh
0x180322917  mov     [rbp+57h+hMem], rax
0x18032291b  lea     rdx, qword_18086B2F8
0x180322922  lea     rax, aOnecoreTermsrv_72; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x180322929  mov     dword ptr [rbp+57h+arg_10], edi
0x18032292c  mov     [rbp+57h+var_80], rax
0x180322930  lea     rax, aResolveproxyBe; "ResolveProxy being called a second time"...
0x180322937  mov     [rbp+57h+var_78], rax
0x18032293b  lea     rax, [rbp+57h+hMem]
0x18032293f  mov     [rsp+0D0h+var_90], rax
0x180322944  lea     rax, [rbp+57h+arg_0]
0x180322948  mov     [rsp+0D0h+var_98], rax
0x18032294d  lea     rax, [rbp+57h+var_80]
0x180322951  mov     [rsp+0D0h+var_A0], rax
0x180322956  lea     rax, [rbp+57h+arg_10]
0x18032295a  mov     [rsp+0D0h+var_A8], rax
0x18032295f  lea     rax, [rbp+57h+var_78]
0x180322963  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322968  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18032296d  jmp     loc_180322EC2
0x180322972  lea     rcx, [rbp+57h+pProxyConfig]; pProxyConfig
0x180322976  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x18032297c  test    eax, eax
0x18032297e  jnz     loc_180322A68
0x180322984  call    cs:__imp_GetLastError
0x18032298a  mov     ebx, eax
0x18032298c  cmp     eax, 2
0x18032298f  mov     eax, cs:dword_1808B5850
0x180322995  jz      loc_180322A29
0x18032299b  cmp     eax, 2
0x18032299e  jbe     loc_180322EC2
0x1803229a4  mov     dword ptr [rbp+57h+arg_0], ebx
0x1803229a7  lea     rax, aResolveproxy; "ResolveProxy"
0x1803229ae  mov     [rbp+57h+var_78], rax
0x1803229b2  lea     rax, aOnecoreTermsrv_72; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x1803229b9  mov     [rbp+57h+var_80], rax
0x1803229bd  mov     dword ptr [rbp+57h+arg_10], 1D4h
0x1803229c4  test    ebx, ebx
0x1803229c6  jg      short loc_1803229CC
0x1803229c8  mov     eax, ebx
0x1803229ca  jmp     short loc_1803229D4
0x1803229cc  movzx   eax, bx
0x1803229cf  or      eax, 80070000h
0x1803229d4  mov     dword ptr [rbp+57h+hMem], eax
0x1803229d7  lea     rdx, word_18086B2AA
0x1803229de  lea     rax, aWinhttpgetiepr_1; "WinHttpGetIEProxyConfigForCurrentUser r"...
0x1803229e5  mov     [rbp+57h+var_70], rax
0x1803229e9  lea     rax, [rbp+57h+arg_0]
0x1803229ed  mov     [rsp+0D0h+var_88], rax
0x1803229f2  lea     rax, [rbp+57h+var_78]
0x1803229f6  mov     [rsp+0D0h+var_90], rax
0x1803229fb  lea     rax, [rbp+57h+arg_10]
0x1803229ff  mov     [rsp+0D0h+var_98], rax
0x180322a04  lea     rax, [rbp+57h+var_80]
0x180322a08  mov     [rsp+0D0h+var_A0], rax
0x180322a0d  lea     rax, [rbp+57h+hMem]
0x180322a11  mov     [rsp+0D0h+var_A8], rax
0x180322a16  lea     rax, [rbp+57h+var_70]
0x180322a1a  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322a1f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180322a24  jmp     loc_180322EC2
0x180322a29  mov     edi, 4
0x180322a2e  cmp     eax, edi
0x180322a30  jbe     short loc_180322A5C
0x180322a32  lea     rax, aNoIeProxySetti; "No IE proxy settings found, trying auto"...
0x180322a39  xor     r8d, r8d
0x180322a3c  mov     [rbp+57h+arg_0], rax
0x180322a40  lea     rdx, byte_18086B289
0x180322a47  lea     rax, [rbp+57h+arg_0]
0x180322a4b  lea     rcx, dword_1808B5850
0x180322a52  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322a57  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180322a5c  mov     [rbp+57h+pProxyConfig.fAutoDetect], 1
0x180322a63  jmp     loc_180322B1D
0x180322a68  mov     eax, cs:dword_1808B5850
0x180322a6e  mov     edi, 4
0x180322a73  cmp     eax, edi
0x180322a75  jbe     short loc_180322AA1
0x180322a77  lea     rax, aWinhttpgetiepr_0; "WinHttpGetIEProxyConfigForCurrentUser r"...
0x180322a7e  xor     r8d, r8d
0x180322a81  mov     [rbp+57h+arg_0], rax
0x180322a85  lea     rdx, qword_18086B430
0x180322a8c  lea     rax, [rbp+57h+arg_0]
0x180322a90  lea     rcx, dword_1808B5850
0x180322a97  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322a9c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180322aa1  mov     eax, cs:dword_1808B5850
0x180322aa7  cmp     eax, edi
0x180322aa9  jbe     short loc_180322B0D
0x180322aab  mov     rax, [rbp+57h+pProxyConfig.lpszProxyBypass]
0x180322aaf  lea     rdx, byte_18086B3A3
0x180322ab6  mov     [rbp+57h+var_70], rax
0x180322aba  mov     rax, [rbp+57h+pProxyConfig.lpszProxy]
0x180322abe  mov     [rbp+57h+var_78], rax
0x180322ac2  mov     rax, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x180322ac6  mov     [rbp+57h+var_68], rax
0x180322aca  mov     eax, [rbp+57h+pProxyConfig.fAutoDetect]
0x180322acd  mov     dword ptr [rbp+57h+arg_0], eax
0x180322ad0  lea     rax, aAutodetectDAut; "Autodetect:%d, Autoconfig URL: %s, Prox"...
0x180322ad7  mov     [rbp+57h+var_60], rax
0x180322adb  lea     rax, [rbp+57h+var_70]
0x180322adf  mov     [rsp+0D0h+var_90], rax
0x180322ae4  lea     rax, [rbp+57h+var_78]
0x180322ae8  mov     [rsp+0D0h+var_98], rax
0x180322aed  lea     rax, [rbp+57h+var_68]
0x180322af1  mov     [rsp+0D0h+var_A0], rax
0x180322af6  lea     rax, [rbp+57h+arg_0]
0x180322afa  mov     [rsp+0D0h+var_A8], rax
0x180322aff  lea     rax, [rbp+57h+var_60]
0x180322b03  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322b08  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180322b0d  cmp     [rbp+57h+pProxyConfig.fAutoDetect], r12d
0x180322b11  jnz     short loc_180322B1D
0x180322b13  cmp     [rbp+57h+pProxyConfig.lpszAutoConfigUrl], r12
0x180322b17  jz      loc_180322DA3
0x180322b1d  xor     r9d, r9d; pszProxyBypassW
0x180322b20  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x180322b25  xor     r8d, r8d; pszProxyW
0x180322b28  lea     rcx, pszAgentW; "ProxyResolver/1.0"
0x180322b2f  xor     edx, edx; dwAccessType
0x180322b31  call    cs:__imp_WinHttpOpen
0x180322b37  mov     [rbp+57h+var_80], rax
0x180322b3b  mov     rsi, rax
0x180322b3e  test    rax, rax
0x180322b41  jnz     loc_180322BD7
0x180322b47  call    cs:__imp_GetLastError
0x180322b4d  mov     ecx, cs:dword_1808B5850
0x180322b53  mov     ebx, eax
0x180322b55  cmp     ecx, 2
0x180322b58  jbe     loc_180322EBD
0x180322b5e  mov     dword ptr [rbp+57h+arg_0], 200h
0x180322b65  lea     rax, aResolveproxy; "ResolveProxy"
0x180322b6c  mov     [rbp+57h+hMem], rax
0x180322b70  lea     rax, aOnecoreTermsrv_72; "onecore\\termsrv\\rdp\\win\\httpio\\win"...
0x180322b77  mov     [rbp+57h+var_60], rax
0x180322b7b  test    ebx, ebx
0x180322b7d  jg      short loc_180322B83
0x180322b7f  mov     eax, ebx
0x180322b81  jmp     short loc_180322B8B
0x180322b83  movzx   eax, bx
0x180322b86  or      eax, 80070000h
0x180322b8b  mov     dword ptr [rbp+57h+arg_10], eax
0x180322b8e  lea     rdx, word_18086B35E
0x180322b95  lea     rax, aWinhttpopenInR; "WinHttpOpen in ResolveProxy failed"
0x180322b9c  mov     [rbp+57h+var_68], rax
0x180322ba0  lea     rax, [rbp+57h+hMem]
0x180322ba4  mov     [rsp+0D0h+var_90], rax
0x180322ba9  lea     rax, [rbp+57h+arg_0]
0x180322bad  mov     [rsp+0D0h+var_98], rax
0x180322bb2  lea     rax, [rbp+57h+var_60]
0x180322bb6  mov     [rsp+0D0h+var_A0], rax
0x180322bbb  lea     rax, [rbp+57h+arg_10]
0x180322bbf  mov     [rsp+0D0h+var_A8], rax
0x180322bc4  lea     rax, [rbp+57h+var_68]
0x180322bc8  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322bcd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180322bd2  jmp     loc_180322EBD
0x180322bd7  cmp     [rbp+57h+pProxyConfig.fAutoDetect], r12d
0x180322bdb  jz      loc_180322CC4
0x180322be1  mov     eax, cs:dword_1808B5850
0x180322be7  cmp     eax, edi
0x180322be9  jbe     short loc_180322C15
0x180322beb  lea     rax, aTryingAutodete; "Trying autodetect"
0x180322bf2  xor     r8d, r8d
0x180322bf5  mov     [rbp+57h+arg_0], rax
0x180322bf9  lea     rdx, byte_18086B33D
0x180322c00  lea     rax, [rbp+57h+arg_0]
0x180322c04  lea     rcx, dword_1808B5850
0x180322c0b  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322c10  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180322c15  lea     rax, [rbp+57h+hMem]
0x180322c19  xor     r9d, r9d; unsigned __int16 *
0x180322c1c  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x180322c21  mov     r8, r14; unsigned __int16 *
0x180322c24  lea     rax, [rbp+57h+arg_10]
0x180322c28  mov     rdx, rsi; void *
0x180322c2b  mov     qword ptr [rsp+0D0h+dwFlags], rax; unsigned __int16 **
0x180322c30  call    ?GetProxyForAutoSettings@CHttpProxyResolver@@AEAAKPEAXPEBG1PEAPEAG2@Z; CHttpProxyResolver::GetProxyForAutoSettings(void *,ushort const *,ushort const *,ushort * *,ushort * *)
0x180322c35  mov     ebx, eax
0x180322c37  test    eax, eax
0x180322c39  mov     eax, cs:dword_1808B5850
0x180322c3f  jnz     short loc_180322C96
0x180322c41  mov     r12d, 1
0x180322c47  cmp     eax, edi
0x180322c49  jbe     loc_180322D53
0x180322c4f  lea     rax, aRetrievedProxy_0; "Retrieved proxy info via autodetect pro"...
0x180322c56  lea     rdx, word_18086B14A
0x180322c5d  mov     rsi, [rbp+57h+hMem]
0x180322c61  mov     r14, [rbp+57h+arg_10]
0x180322c65  mov     [rbp+57h+hMem], rax
0x180322c69  lea     rax, [rbp+57h+arg_0]
0x180322c6d  mov     [rsp+0D0h+var_A0], rax
0x180322c72  lea     rax, [rbp+57h+arg_10]
0x180322c76  mov     [rsp+0D0h+var_A8], rax
0x180322c7b  lea     rax, [rbp+57h+hMem]
0x180322c7f  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322c84  mov     [rbp+57h+arg_10], r14
0x180322c88  mov     [rbp+57h+arg_0], rsi
0x180322c8c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180322c91  jmp     loc_180322DB5
0x180322c96  cmp     eax, edi
0x180322c98  jbe     short loc_180322CC4
0x180322c9a  lea     rax, aFailedInAutode; "Failed in autodetect; falling back to a"...
0x180322ca1  xor     r8d, r8d
0x180322ca4  mov     [rbp+57h+arg_0], rax
0x180322ca8  lea     rdx, byte_18086B129
0x180322caf  lea     rax, [rbp+57h+arg_0]
0x180322cb3  lea     rcx, dword_1808B5850
0x180322cba  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322cbf  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180322cc4  cmp     [rbp+57h+pProxyConfig.lpszAutoConfigUrl], r12
0x180322cc8  jz      loc_180322DA3
0x180322cce  mov     eax, cs:dword_1808B5850
0x180322cd4  cmp     eax, edi
0x180322cd6  jbe     short loc_180322D09
0x180322cd8  mov     rax, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]
0x180322cdc  lea     rdx, byte_18086B0E9
0x180322ce3  mov     [rbp+57h+arg_0], rax
0x180322ce7  lea     rax, aTryingAutoconf; "Trying autoconfig URL %s"
0x180322cee  mov     [rbp+57h+var_60], rax
0x180322cf2  lea     rax, [rbp+57h+arg_0]
0x180322cf6  mov     [rsp+0D0h+var_A8], rax
0x180322cfb  lea     rax, [rbp+57h+var_60]
0x180322cff  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322d04  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180322d09  mov     r9, [rbp+57h+pProxyConfig.lpszAutoConfigUrl]; unsigned __int16 *
0x180322d0d  lea     rax, [rbp+57h+hMem]
0x180322d11  mov     [rsp+0D0h+var_A8], rax; unsigned __int16 **
0x180322d16  mov     r8, r14; unsigned __int16 *
0x180322d19  lea     rax, [rbp+57h+arg_10]
0x180322d1d  mov     rdx, rsi; void *
0x180322d20  mov     qword ptr [rsp+0D0h+dwFlags], rax; unsigned __int16 **
0x180322d25  call    ?GetProxyForAutoSettings@CHttpProxyResolver@@AEAAKPEAXPEBG1PEAPEAG2@Z; CHttpProxyResolver::GetProxyForAutoSettings(void *,ushort const *,ushort const *,ushort * *,ushort * *)
0x180322d2a  mov     ebx, eax
0x180322d2c  test    eax, eax
0x180322d2e  mov     eax, cs:dword_1808B5850
0x180322d34  jnz     short loc_180322D5D
0x180322d36  mov     r12d, 1
0x180322d3c  cmp     eax, edi
0x180322d3e  jbe     short loc_180322D53
0x180322d40  lea     rax, aRetrievedProxy_1; "Retrieved proxy info via autoconfig URL"...
0x180322d47  lea     rdx, dword_18086B0AC
0x180322d4e  jmp     loc_180322C5D
0x180322d53  mov     r14, [rbp+57h+arg_10]
0x180322d57  mov     rsi, [rbp+57h+hMem]
0x180322d5b  jmp     short loc_180322DB5
0x180322d5d  cmp     eax, edi
0x180322d5f  jbe     short loc_180322DA3
0x180322d61  mov     rax, [rbp+57h+pProxyConfig.lpszProxyBypass]
0x180322d65  lea     rdx, dword_18086B234
0x180322d6c  mov     [rbp+57h+arg_0], rax
0x180322d70  mov     rax, [rbp+57h+pProxyConfig.lpszProxy]
0x180322d74  mov     [rbp+57h+arg_10], rax
0x180322d78  lea     rax, aFallingBackToS; "Falling back to static settings: proxy:"...
0x180322d7f  mov     [rbp+57h+hMem], rax
0x180322d83  lea     rax, [rbp+57h+arg_0]
0x180322d87  mov     [rsp+0D0h+var_A0], rax
0x180322d8c  lea     rax, [rbp+57h+arg_10]
0x180322d90  mov     [rsp+0D0h+var_A8], rax
0x180322d95  lea     rax, [rbp+57h+hMem]
0x180322d99  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x180322d9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180322da3  mov     r14, [rbp+57h+pProxyConfig.lpszProxy]
0x180322da7  xor     ebx, ebx
0x180322da9  mov     rsi, [rbp+57h+pProxyConfig.lpszProxyBypass]
0x180322dad  mov     [rbp+57h+pProxyConfig.lpszProxy], r12
0x180322db1  mov     [rbp+57h+pProxyConfig.lpszProxyBypass], r12
0x180322db5  mov     [r15+30h], r12d
0x180322db9  test    r14, r14
0x180322dbc  jnz     short loc_180322E14
0x180322dbe  mov     dword ptr [r15+18h], 1
0x180322dc6  mov     eax, cs:dword_1808B5850
0x180322dcc  cmp     eax, edi
  ... truncated ...
```
