# CEnrollHttpClient::p_Transmit(ushort const *,bool,ushort const *,ushort const *,int,int,int,int,bool,ushort const *,uchar const *,ulong,long *,ushort * *,ushort * *,uchar * *,ulong *)

- ea: `0x18002c180`
- end: `0x18002c89f`
- name: `?p_Transmit@CEnrollHttpClient@@CAJPEBG_N00HHHH10PEBEKPEAJPEAPEAG4PEAPEAEPEAK@Z`
- size: `1823`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8, unsigned __int16 *, unsigned __int16 *, int nResolveTimeout, int nConnectTimeout, int nSendTimeout, int nReceiveTimeout, bool, LPCWSTR lpszHeaders, unsigned __int8 *, DWORD, _DWORD *Size, unsigned __int16 **dwNumberOfBytesRead, unsigned __int16 **, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18002bbd8`

## callees

- `0x180001514`
- `0x180002306`
- `0x18001db00`
- `0x1800213f0`
- `0x180021438`
- `0x18002bf04`
- `0x18002bfd4`
- `0x18002c180`
- `0x18002c8f4`
- `0x18002ca00`
- `0x18002cf3c`
- `0x18002d184`
- `0x1800396f2`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002c79c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002c79c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c6b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c6b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c6ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c6ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c7f4`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c22f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c2b6`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c35f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c3a6`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c686`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c76c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c781`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c22f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c2b6`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c35f`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c3a6`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c686`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c76c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002c781`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002c255`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002c26b`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002c27d`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002c255`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002c26b`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002c27d`
- `WINHTTP!WinHttpSetTimeouts` at `0x18002c313`
- `WINHTTP!WinHttpSetTimeouts` at `0x18002c313`
- `WINHTTP!WinHttpConnect` at `0x18002c415`
- `WINHTTP!WinHttpConnect` at `0x18002c415`
- `WINHTTP!WinHttpOpenRequest` at `0x18002c46c`
- `WINHTTP!WinHttpOpenRequest` at `0x18002c46c`
- `WINHTTP!WinHttpReceiveResponse` at `0x18002c5db`
- `WINHTTP!WinHttpReceiveResponse` at `0x18002c5db`
- `WINHTTP!WinHttpOpen` at `0x18002c296`
- `WINHTTP!WinHttpOpen` at `0x18002c342`
- `WINHTTP!WinHttpOpen` at `0x18002c296`
- `WINHTTP!WinHttpOpen` at `0x18002c342`
- `WINHTTP!WinHttpReadData` at `0x18002c72a`
- `WINHTTP!WinHttpReadData` at `0x18002c72a`
- `WINHTTP!WinHttpCloseHandle` at `0x18002c802`
- `WINHTTP!WinHttpCloseHandle` at `0x18002c810`
- `WINHTTP!WinHttpCloseHandle` at `0x18002c81e`
- `WINHTTP!WinHttpCloseHandle` at `0x18002c82c`
- `WINHTTP!WinHttpCloseHandle` at `0x18002c802`
- `WINHTTP!WinHttpCloseHandle` at `0x18002c810`
- `WINHTTP!WinHttpCloseHandle` at `0x18002c81e`
- `WINHTTP!WinHttpCloseHandle` at `0x18002c82c`
- `WINHTTP!WinHttpQueryHeaders` at `0x18002c61e`
- `WINHTTP!WinHttpQueryHeaders` at `0x18002c61e`
- `WINHTTP!WinHttpSetOption` at `0x18002c2e8`
- `WINHTTP!WinHttpSetOption` at `0x18002c49b`
- `WINHTTP!WinHttpSetOption` at `0x18002c4ea`
- `WINHTTP!WinHttpSetOption` at `0x18002c51f`
- `WINHTTP!WinHttpSetOption` at `0x18002c558`
- `WINHTTP!WinHttpSetOption` at `0x18002c2e8`
- `WINHTTP!WinHttpSetOption` at `0x18002c49b`
- `WINHTTP!WinHttpSetOption` at `0x18002c4ea`
- `WINHTTP!WinHttpSetOption` at `0x18002c51f`
- `WINHTTP!WinHttpSetOption` at `0x18002c558`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18002c750`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x18002c750`

## string_xrefs

- `0x18002c28f`: `Mozilla/4.0 (compatible; Win32; NDES client 10.0.29599.1000/rs_prerelease)`
- `0x18002c33b`: `Mozilla/4.0 (compatible; Win32; NDES client 10.0.29599.1000/rs_prerelease)`

## pseudocode

```c
__int64 __fastcall CEnrollHttpClient::p_Transmit(
        const unsigned __int16 *a1,
        unsigned __int8 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int nResolveTimeout,
        int nConnectTimeout,
        int nSendTimeout,
        int nReceiveTimeout,
        bool a9,
        LPCWSTR lpszHeaders,
        unsigned __int8 *a11,
        DWORD a12,
        _DWORD *Size,
        unsigned __int16 **dwNumberOfBytesRead,
        unsigned __int16 **a15,
        unsigned __int8 **a16,
        unsigned int *a17)
{
  void *v17; // r13
  void *v18; // rsi
  void *v19; // r15
  void *v20; // rdi
  void *v21; // r14
  unsigned int v22; // r12d
  int v23; // eax
  unsigned int v24; // ebx
  INTERNET_PORT v25; // r13
  bool v26; // r15
  void *v27; // rax
  void *v28; // rbx
  unsigned int v29; // eax
  unsigned int v30; // ecx
  ProxyResolver *v31; // rax
  ProxyResolver *v32; // rax
  int v33; // edx
  unsigned int v34; // ecx
  int v35; // eax
  int v36; // eax
  int v37; // eax
  INTERNET_PORT v38; // r8
  void *v39; // rax
  int StringHeaderProperty; // eax
  unsigned int v41; // ecx
  const WCHAR *v42; // rdx
  unsigned __int8 v43; // bl
  void *v44; // rax
  unsigned int v45; // r8d
  unsigned __int16 *v46; // rax
  unsigned int v47; // ebx
  __int64 v48; // r9
  DWORD v49; // edx
  __int64 v50; // r9
  DWORD v51; // r9d
  DWORD v52; // edx
  _DWORD *v53; // rsi
  char *v54; // rax
  char *v55; // rsi
  __int64 v56; // rbx
  _BYTE *v57; // rdx
  int v58; // edx
  __int64 v59; // rcx
  _BYTE *v60; // rax
  unsigned __int64 v62; // [rsp+38h] [rbp-69h]
  HINTERNET v63; // [rsp+58h] [rbp-49h]
  void *v64; // [rsp+60h] [rbp-41h]
  void *hSession; // [rsp+68h] [rbp-39h]
  ProxyResolver *Buffer; // [rsp+70h] [rbp-31h] BYREF
  ProxyResolver *v67; // [rsp+78h] [rbp-29h]
  LPCWSTR pswzServerName; // [rsp+80h] [rbp-21h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-19h] BYREF
  LPCWSTR pwszObjectName; // [rsp+90h] [rbp-11h] BYREF
  DWORD dwBufferLength; // [rsp+98h] [rbp-9h] BYREF
  HLOCAL v72; // [rsp+A0h] [rbp-1h] BYREF

  v17 = 0;
  v18 = 0;
  v19 = 0;
  v64 = 0;
  v20 = 0;
  v67 = 0;
  hMem = 0;
  pswzServerName = 0;
  pwszObjectName = 0;
  LODWORD(Buffer) = 0;
  v72 = 0;
  v21 = 0;
  v22 = 0;
  *Size = 0;
  *dwNumberOfBytesRead = 0;
  *a15 = 0;
  *a16 = 0;
  *a17 = 0;
  v23 = CEnrollHttpClient::p_ParseUrl(
          a1,
          (unsigned __int16 **)&hMem,
          (unsigned __int16 **)&pswzServerName,
          (unsigned __int16 **)&pwszObjectName,
          (unsigned int *)&Buffer);
  v24 = v23;
  if ( v23 < 0 )
  {
    CSPrintErrorLineFile(0x1E701D7u, v23);
    goto LABEL_78;
  }
  v25 = (unsigned __int16)Buffer;
  v26 = (_DWORD)Buffer == 443;
  CSPrintErrorLineFileData((const unsigned __int16 *)hMem, 0x1EA01D7u, (_DWORD)Buffer);
  CSPrintErrorLineFileData(pswzServerName, 0x1EB01D7u, v26);
  CSPrintErrorLineFileData(pwszObjectName, 0x1EC01D7u, 0);
  v27 = WinHttpOpen(L"Mozilla/4.0 (compatible; Win32; NDES client 10.0.29599.1000/rs_prerelease)", 0, 0, 0, 0);
  v28 = v27;
  hSession = v27;
  if ( !v27 )
  {
    v29 = myHLastError();
    v30 = 33096151;
LABEL_5:
    v24 = v29;
    CSPrintErrorLineFile(v30, v29);
    v17 = hSession;
    v18 = 0;
    v19 = 0;
    goto LABEL_78;
  }
  if ( v26 )
  {
    LODWORD(Buffer) = 2720;
    if ( !WinHttpSetOption(v27, 0x54u, &Buffer, 4u) )
    {
      v29 = myHLastError();
      v30 = 33948119;
      goto LABEL_5;
    }
  }
  if ( !WinHttpSetTimeouts(v28, nResolveTimeout, nConnectTimeout, nSendTimeout, nReceiveTimeout) )
  {
    v29 = myHLastError();
    v30 = 34734551;
    goto LABEL_5;
  }
  v63 = WinHttpOpen(L"Mozilla/4.0 (compatible; Win32; NDES client 10.0.29599.1000/rs_prerelease)", 0, 0, 0, 0x10000000u);
  if ( v63 )
  {
    v31 = (ProxyResolver *)operator new(0x60u);
    Buffer = v31;
    if ( v31 )
      v32 = ProxyResolver::ProxyResolver(v31);
    else
      v32 = 0;
    v67 = v32;
    if ( !v32 )
    {
      v33 = -2147024882;
      v24 = -2147024882;
      v34 = 36110807;
LABEL_18:
      CSPrintErrorLineFile(v34, v33);
      v17 = hSession;
LABEL_76:
      v19 = v64;
      goto LABEL_77;
    }
    v35 = myCombineStrings((const unsigned __int16 *)hMem, L"://", pswzServerName, (unsigned __int16 **)&v72);
    v24 = v35;
    if ( v35 < 0 )
    {
      v33 = v35;
      v34 = 36504023;
      goto LABEL_18;
    }
    v36 = ProxyResolver::ResolveProxy(v67, v63, (const unsigned __int16 *)v72);
    v37 = myHError(v36);
    v24 = v37;
    if ( v37 < 0 )
    {
      v33 = v37;
      v34 = 36766167;
      goto LABEL_18;
    }
    v38 = v25;
    v17 = hSession;
    v39 = WinHttpConnect(hSession, pswzServerName, v38, 0);
    v64 = v39;
    if ( v39 )
    {
      v42 = L"POST";
      v43 = a2;
      if ( !a2 )
        v42 = L"GET";
      v44 = WinHttpOpenRequest(v39, v42, pwszObjectName, 0, 0, 0, (v26 << 23) | 0x100u);
      v20 = v44;
      if ( v44 )
      {
        if ( !v26 || WinHttpSetOption(v44, 0x2Fu, 0, 0) )
        {
          v46 = a3;
          if ( a3 )
          {
            v47 = 0;
            while ( 1 )
            {
              v48 = -1;
              do
                ++v48;
              while ( v46[v48] );
              v49 = 4096;
              if ( v47 )
                v49 = 4098;
              if ( !WinHttpSetOption(v20, v49, v46, v48) )
                break;
              v50 = -1;
              do
                ++v50;
              while ( a4[v50] );
              v51 = v50 + 1;
              v52 = 4097;
              if ( v47 )
                v52 = 4099;
              if ( !WinHttpSetOption(v20, v52, a4, v51) )
              {
                StringHeaderProperty = myHLastError();
                v41 = 41091543;
                goto LABEL_73;
              }
              ++v47;
              v46 = a3;
              if ( v47 >= 2 )
              {
                v43 = a2;
                goto LABEL_46;
              }
            }
            StringHeaderProperty = myHLastError();
            v41 = 40370647;
          }
          else
          {
LABEL_46:
            if ( !a9 || (LODWORD(Buffer) = 1, WinHttpSetOption(v20, 0x4Du, &Buffer, 4u)) )
            {
              StringHeaderProperty = SendRequestWithProxyFailover(
                                       v20,
                                       lpszHeaders,
                                       v45,
                                       a11,
                                       a12,
                                       a12,
                                       v62,
                                       v67,
                                       v43 ^ 1u);
              v24 = StringHeaderProperty;
              if ( StringHeaderProperty < 0 )
              {
                v41 = 43123159;
                goto LABEL_74;
              }
              if ( WinHttpReceiveResponse(v20, 0) )
              {
                dwBufferLength = 4;
                v53 = Size;
                if ( WinHttpQueryHeaders(v20, 0x20000013u, 0, Size, &dwBufferLength, 0) )
                {
                  StringHeaderProperty = CEnrollHttpClient::p_GetStringHeaderProperty(v20, 0x16u, dwNumberOfBytesRead);
                  v24 = StringHeaderProperty;
                  if ( StringHeaderProperty )
                  {
                    v41 = 44958167;
                  }
                  else
                  {
                    StringHeaderProperty = CEnrollHttpClient::p_GetStringHeaderProperty(v20, 0x14u, a15);
                    v24 = StringHeaderProperty;
                    if ( !StringHeaderProperty )
                    {
                      CSPrintErrorLineFile(0x2B601D7u, *v53);
                      while ( 1 )
                      {
                        LODWORD(Size) = 0;
                        if ( !WinHttpQueryDataAvailable(v20, (LPDWORD)&Size) )
                        {
                          StringHeaderProperty = myHLastError();
                          v41 = 46531031;
                          goto LABEL_73;
                        }
                        if ( !(_DWORD)Size )
                          break;
                        if ( (unsigned int)Size + v22 < v22 )
                        {
                          v24 = -2147024362;
                          v58 = -2147024362;
                          v41 = 47317463;
                          goto LABEL_75;
                        }
                        v54 = (char *)LocalAlloc(0, (unsigned int)Size + v22);
                        v55 = v54;
                        if ( !v54 )
                        {
                          v58 = -2147024882;
                          v24 = -2147024882;
                          v41 = 47710679;
                          goto LABEL_75;
                        }
                        if ( v21 )
                        {
                          v56 = v22;
                          memcpy_0(v54, v21, v22);
                          v57 = v21;
                          if ( v22 )
                          {
                            do
                            {
                              *v57++ = 0;
                              --v56;
                            }
                            while ( v56 );
                          }
                          LocalFree(v21);
                        }
                        v21 = v55;
                        memset_0(&v55[v22], 0, (unsigned int)Size);
                        LODWORD(dwNumberOfBytesRead) = 0;
                        if ( !WinHttpReadData(v20, &v55[v22], (DWORD)Size, (LPDWORD)&dwNumberOfBytesRead) )
                        {
                          StringHeaderProperty = myHLastError();
                          v41 = 49414615;
                          goto LABEL_73;
                        }
                        v22 += (unsigned int)dwNumberOfBytesRead;
                      }
                      *a16 = (unsigned __int8 *)v21;
                      *a17 = v22;
                      v21 = 0;
                      v24 = 0;
                      goto LABEL_76;
                    }
                    v41 = 45351383;
                  }
                  goto LABEL_74;
                }
                StringHeaderProperty = myHLastError();
                v41 = 44499415;
              }
              else
              {
                StringHeaderProperty = myHLastError();
                v41 = 43581911;
              }
            }
            else
            {
              StringHeaderProperty = myHLastError();
              v41 = 42074583;
            }
          }
        }
        else
        {
          StringHeaderProperty = myHLastError();
          v41 = 39190999;
        }
      }
      else
      {
        StringHeaderProperty = myHLastError();
        v41 = 38404567;
      }
    }
    else
    {
      StringHeaderProperty = myHLastError();
      v41 = 37421527;
    }
LABEL_73:
    v24 = StringHeaderProperty;
LABEL_74:
    v58 = StringHeaderProperty;
LABEL_75:
    CSPrintErrorLineFile(v41, v58);
    goto LABEL_76;
  }
  v24 = myHLastError();
  CSPrintErrorLineFile(0x22001D7u, v24);
  v17 = hSession;
  v19 = 0;
LABEL_77:
  v18 = v63;
LABEL_78:
  CSPrintErrorLineFile(0x2FC01D7u, v24);
  if ( v67 )
  {
    ProxyResolver::~ProxyResolver(v67);
    operator delete(v67);
  }
  LocalFree(hMem);
  LocalFree((HLOCAL)pswzServerName);
  LocalFree((HLOCAL)pwszObjectName);
  LocalFree(v72);
  LocalFree(0);
  if ( v21 )
  {
    v59 = v22;
    v60 = v21;
    if ( v22 )
    {
      do
      {
        *v60++ = 0;
        --v59;
      }
      while ( v59 );
    }
    LocalFree(v21);
  }
  if ( v20 )
    WinHttpCloseHandle(v20);
  if ( v19 )
    WinHttpCloseHandle(v19);
  if ( v18 )
    WinHttpCloseHandle(v18);
  if ( v17 )
    WinHttpCloseHandle(v17);
  return v24;
}

```

## disassembly

```asm
0x18002c180  mov     rax, rsp
0x18002c183  mov     [rax+8], rbx
0x18002c187  mov     [rax+20h], r9
0x18002c18b  mov     [rax+18h], r8
0x18002c18f  mov     [rax+10h], dl
0x18002c192  push    rbp
0x18002c193  push    rsi
0x18002c194  push    rdi
0x18002c195  push    r12
0x18002c197  push    r13
0x18002c199  push    r14
0x18002c19b  push    r15
0x18002c19d  lea     rbp, [rax-3Fh]
0x18002c1a1  sub     rsp, 0A0h
0x18002c1a8  xor     r13d, r13d
0x18002c1ab  mov     esi, r13d
0x18002c1ae  mov     r15d, r13d
0x18002c1b1  mov     [rbp+37h+var_78], r13
0x18002c1b5  mov     edi, r13d
0x18002c1b8  mov     [rbp+37h+var_60], r13
0x18002c1bc  mov     [rbp+37h+hMem], r13
0x18002c1c0  mov     [rbp+37h+pswzServerName], r13
0x18002c1c4  mov     [rbp+37h+pwszObjectName], r13
0x18002c1c8  mov     dword ptr [rbp+37h+Buffer], r13d
0x18002c1cc  mov     [rbp+37h+var_38], r13
0x18002c1d0  mov     r14d, r13d
0x18002c1d3  mov     r12d, r13d
0x18002c1d6  mov     rax, [rbp+37h+Size]
0x18002c1dd  mov     [rax], r13d
0x18002c1e0  mov     rax, [rbp+37h+dwNumberOfBytesRead]
0x18002c1e7  mov     [rax], r13
0x18002c1ea  mov     rax, [rbp+37h+arg_70]
0x18002c1f1  mov     [rax], r13
0x18002c1f4  mov     rax, [rbp+37h+arg_78]
0x18002c1fb  mov     [rax], r13
0x18002c1fe  mov     rax, [rbp+37h+arg_80]
0x18002c205  mov     [rax], r13d
0x18002c208  lea     rax, [rbp+37h+Buffer]
0x18002c20c  mov     qword ptr [rsp+0D0h+dwFlags], rax; unsigned int *
0x18002c211  lea     r9, [rbp+37h+pwszObjectName]; unsigned __int16 **
0x18002c215  lea     r8, [rbp+37h+pswzServerName]; unsigned __int16 **
0x18002c219  lea     rdx, [rbp+37h+hMem]; unsigned __int16 **
0x18002c21d  call    ?p_ParseUrl@CEnrollHttpClient@@CAJPEBGPEAPEAG11PEAK@Z; CEnrollHttpClient::p_ParseUrl(ushort const *,ushort * *,ushort * *,ushort * *,ulong *)
0x18002c222  mov     ebx, eax
0x18002c224  test    eax, eax
0x18002c226  jns     short loc_18002C23A
0x18002c228  mov     edx, eax
0x18002c22a  mov     ecx, 1E701D7h
0x18002c22f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c235  jmp     loc_18002C77A
0x18002c23a  mov     r13d, dword ptr [rbp+37h+Buffer]
0x18002c23e  cmp     r13d, 1BBh
0x18002c245  setz    r15b
0x18002c249  mov     r8d, r13d
0x18002c24c  mov     edx, 1EA01D7h
0x18002c251  mov     rcx, [rbp+37h+hMem]
0x18002c255  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18002c25b  movzx   esi, r15b
0x18002c25f  mov     r8d, esi
0x18002c262  mov     edx, 1EB01D7h
0x18002c267  mov     rcx, [rbp+37h+pswzServerName]
0x18002c26b  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18002c271  xor     r8d, r8d
0x18002c274  mov     edx, 1EC01D7h
0x18002c279  mov     rcx, [rbp+37h+pwszObjectName]
0x18002c27d  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18002c283  mov     [rsp+0D0h+dwFlags], edi; dwFlags
0x18002c287  xor     r9d, r9d; pszProxyBypassW
0x18002c28a  xor     r8d, r8d; pszProxyW
0x18002c28d  xor     edx, edx; dwAccessType
0x18002c28f  lea     rcx, pszAgentW; "Mozilla/4.0 (compatible; Win32; NDES cl"...
0x18002c296  call    cs:__imp_WinHttpOpen
0x18002c29c  mov     rbx, rax
0x18002c29f  mov     [rbp+37h+hSession], rax
0x18002c2a3  test    rax, rax
0x18002c2a6  jnz     short loc_18002C2CB
0x18002c2a8  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c2ad  mov     ecx, 1F901D7h
0x18002c2b2  mov     ebx, eax
0x18002c2b4  mov     edx, eax
0x18002c2b6  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c2bc  mov     r13, [rbp+37h+hSession]
0x18002c2c0  mov     rsi, rdi
0x18002c2c3  mov     r15, rdi
0x18002c2c6  jmp     loc_18002C77A
0x18002c2cb  test    r15b, r15b
0x18002c2ce  jz      short loc_18002C2FE
0x18002c2d0  mov     dword ptr [rbp+37h+Buffer], 0AA0h
0x18002c2d7  mov     r9d, 4; dwBufferLength
0x18002c2dd  lea     r8, [rbp+37h+Buffer]; lpBuffer
0x18002c2e1  lea     edx, [r9+50h]; dwOption
0x18002c2e5  mov     rcx, rbx; hInternet
0x18002c2e8  call    cs:__imp_WinHttpSetOption
0x18002c2ee  test    eax, eax
0x18002c2f0  jnz     short loc_18002C2FE
0x18002c2f2  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c2f7  mov     ecx, 20601D7h
0x18002c2fc  jmp     short loc_18002C2B2
0x18002c2fe  mov     eax, [rbp+37h+nReceiveTimeout]
0x18002c301  mov     [rsp+0D0h+dwFlags], eax; nReceiveTimeout
0x18002c305  mov     r9d, [rbp+37h+nSendTimeout]; nSendTimeout
0x18002c309  mov     r8d, [rbp+37h+nConnectTimeout]; nConnectTimeout
0x18002c30d  mov     edx, [rbp+37h+nResolveTimeout]; nResolveTimeout
0x18002c310  mov     rcx, rbx; hInternet
0x18002c313  call    cs:__imp_WinHttpSetTimeouts
0x18002c319  xor     ebx, ebx
0x18002c31b  test    eax, eax
0x18002c31d  jnz     short loc_18002C32B
0x18002c31f  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c324  mov     ecx, 21201D7h
0x18002c329  jmp     short loc_18002C2B2
0x18002c32b  mov     [rsp+0D0h+dwFlags], 10000000h; dwFlags
0x18002c333  xor     r9d, r9d; pszProxyBypassW
0x18002c336  xor     r8d, r8d; pszProxyW
0x18002c339  xor     edx, edx; dwAccessType
0x18002c33b  lea     rcx, pszAgentW; "Mozilla/4.0 (compatible; Win32; NDES cl"...
0x18002c342  call    cs:__imp_WinHttpOpen
0x18002c348  mov     [rbp+37h+var_80], rax
0x18002c34c  test    rax, rax
0x18002c34f  jnz     short loc_18002C371
0x18002c351  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c356  mov     ebx, eax
0x18002c358  mov     edx, eax
0x18002c35a  mov     ecx, 22001D7h
0x18002c35f  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c365  mov     r13, [rbp+37h+hSession]
0x18002c369  mov     r15, rdi
0x18002c36c  jmp     loc_18002C776
0x18002c371  mov     ecx, 60h ; '`'; Size
0x18002c376  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c37b  mov     [rbp+37h+Buffer], rax
0x18002c37f  test    rax, rax
0x18002c382  jz      short loc_18002C38E
0x18002c384  mov     rcx, rax; this
0x18002c387  call    ??0ProxyResolver@@QEAA@XZ; ProxyResolver::ProxyResolver(void)
0x18002c38c  jmp     short loc_18002C391
0x18002c38e  mov     rax, rbx
0x18002c391  mov     [rbp+37h+var_60], rax
0x18002c395  test    rax, rax
0x18002c398  jnz     short loc_18002C3B5
0x18002c39a  mov     edx, 8007000Eh
0x18002c39f  mov     ebx, edx
0x18002c3a1  mov     ecx, 22701D7h
0x18002c3a6  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002c3ac  mov     r13, [rbp+37h+hSession]
0x18002c3b0  jmp     loc_18002C772
0x18002c3b5  lea     r9, [rbp+37h+var_38]; unsigned __int16 **
0x18002c3b9  mov     r8, [rbp+37h+pswzServerName]; unsigned __int16 *
0x18002c3bd  lea     rdx, asc_180054ED8; "://"
0x18002c3c4  mov     rcx, [rbp+37h+hMem]; unsigned __int16 *
0x18002c3c8  call    ?myCombineStrings@@YAJPEBG00PEAPEAG@Z; myCombineStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x18002c3cd  mov     ebx, eax
0x18002c3cf  test    eax, eax
0x18002c3d1  jns     short loc_18002C3DC
0x18002c3d3  mov     edx, eax
0x18002c3d5  mov     ecx, 22D01D7h
0x18002c3da  jmp     short loc_18002C3A6
0x18002c3dc  mov     r8, [rbp+37h+var_38]; unsigned __int16 *
0x18002c3e0  mov     rdx, [rbp+37h+var_80]; void *
0x18002c3e4  mov     rcx, [rbp+37h+var_60]; this
0x18002c3e8  call    ?ResolveProxy@ProxyResolver@@QEAAKPEAXPEBG@Z; ProxyResolver::ResolveProxy(void *,ushort const *)
0x18002c3ed  mov     ecx, eax; int
0x18002c3ef  call    ?myHError@@YAJJ@Z; myHError(long)
0x18002c3f4  mov     ebx, eax
0x18002c3f6  test    eax, eax
0x18002c3f8  jns     short loc_18002C403
0x18002c3fa  mov     edx, eax
0x18002c3fc  mov     ecx, 23101D7h
0x18002c401  jmp     short loc_18002C3A6
0x18002c403  xor     r9d, r9d; dwReserved
0x18002c406  movzx   r8d, r13w; nServerPort
0x18002c40a  mov     rdx, [rbp+37h+pswzServerName]; pswzServerName
0x18002c40e  mov     r13, [rbp+37h+hSession]
0x18002c412  mov     rcx, r13; hSession
0x18002c415  call    cs:__imp_WinHttpConnect
0x18002c41b  mov     [rbp+37h+var_78], rax
0x18002c41f  xor     r8d, r8d
0x18002c422  test    rax, rax
0x18002c425  jnz     short loc_18002C436
0x18002c427  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c42c  mov     ecx, 23B01D7h
0x18002c431  jmp     loc_18002C768
0x18002c436  shl     esi, 17h
0x18002c439  bts     esi, 8
0x18002c43d  lea     rcx, pwszVerb; "GET"
0x18002c444  lea     rdx, aPost; "POST"
0x18002c44b  mov     bl, [rbp+37h+arg_8]
0x18002c44e  test    bl, bl
0x18002c450  cmovz   rdx, rcx; pwszVerb
0x18002c454  mov     [rsp+0D0h+var_A0], esi; unsigned __int64
0x18002c458  mov     [rsp+0D0h+ppwszAcceptTypes], r8; ppwszAcceptTypes
0x18002c45d  mov     qword ptr [rsp+0D0h+dwFlags], r8; pwszReferrer
0x18002c462  xor     r9d, r9d; pwszVersion
0x18002c465  mov     r8, [rbp+37h+pwszObjectName]; pwszObjectName
0x18002c469  mov     rcx, rax; hConnect
0x18002c46c  call    cs:__imp_WinHttpOpenRequest
0x18002c472  mov     rdi, rax
0x18002c475  test    rax, rax
0x18002c478  jnz     short loc_18002C489
0x18002c47a  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c47f  mov     ecx, 24A01D7h
0x18002c484  jmp     loc_18002C768
0x18002c489  test    r15b, r15b
0x18002c48c  jz      short loc_18002C4B7
0x18002c48e  xor     r9d, r9d; dwBufferLength
0x18002c491  xor     r8d, r8d; lpBuffer
0x18002c494  lea     edx, [r9+2Fh]; dwOption
0x18002c498  mov     rcx, rdi; hInternet
0x18002c49b  call    cs:__imp_WinHttpSetOption
0x18002c4a1  xor     r15d, r15d
0x18002c4a4  test    eax, eax
0x18002c4a6  jnz     short loc_18002C4BA
0x18002c4a8  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c4ad  mov     ecx, 25601D7h
0x18002c4b2  jmp     loc_18002C768
0x18002c4b7  xor     r15d, r15d
0x18002c4ba  mov     rax, [rbp+37h+lpBuffer]
0x18002c4be  test    rax, rax
0x18002c4c1  jz      short loc_18002C537
0x18002c4c3  mov     ebx, r15d
0x18002c4c6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002c4ca  mov     r9, rsi
0x18002c4cd  inc     r9; dwBufferLength
0x18002c4d0  cmp     [rax+r9*2], r15w
0x18002c4d5  jnz     short loc_18002C4CD
0x18002c4d7  mov     edx, 1000h
0x18002c4dc  lea     ecx, [rdx+2]
0x18002c4df  test    ebx, ebx
0x18002c4e1  cmovnz  edx, ecx; dwOption
0x18002c4e4  mov     r8, rax; lpBuffer
0x18002c4e7  mov     rcx, rdi; hInternet
0x18002c4ea  call    cs:__imp_WinHttpSetOption
0x18002c4f0  test    eax, eax
0x18002c4f2  jz      loc_18002C580
0x18002c4f8  mov     r9, rsi
0x18002c4fb  mov     rax, [rbp+37h+arg_18]
0x18002c4ff  inc     r9
0x18002c502  cmp     [rax+r9*2], r15w
0x18002c507  jnz     short loc_18002C4FF
0x18002c509  inc     r9d; dwBufferLength
0x18002c50c  mov     edx, 1001h
0x18002c511  lea     ecx, [rdx+2]
0x18002c514  test    ebx, ebx
0x18002c516  cmovnz  edx, ecx; dwOption
0x18002c519  mov     r8, rax; lpBuffer
0x18002c51c  mov     rcx, rdi; hInternet
0x18002c51f  call    cs:__imp_WinHttpSetOption
0x18002c525  test    eax, eax
0x18002c527  jz      short loc_18002C571
0x18002c529  inc     ebx
0x18002c52b  cmp     ebx, 2
0x18002c52e  mov     rax, [rbp+37h+lpBuffer]
0x18002c532  jb      short loc_18002C4CA
0x18002c534  mov     bl, [rbp+37h+arg_8]
0x18002c537  cmp     [rbp+37h+arg_40], r15b
0x18002c53e  jz      short loc_18002C58F
0x18002c540  mov     dword ptr [rbp+37h+Buffer], 1
0x18002c547  mov     r9d, 4; dwBufferLength
0x18002c54d  lea     r8, [rbp+37h+Buffer]; lpBuffer
0x18002c551  lea     edx, [r9+49h]; dwOption
0x18002c555  mov     rcx, rdi; hInternet
0x18002c558  call    cs:__imp_WinHttpSetOption
0x18002c55e  test    eax, eax
0x18002c560  jnz     short loc_18002C58F
0x18002c562  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c567  mov     ecx, 28201D7h
0x18002c56c  jmp     loc_18002C768
0x18002c571  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c576  mov     ecx, 27301D7h
0x18002c57b  jmp     loc_18002C768
0x18002c580  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c585  mov     ecx, 26801D7h
0x18002c58a  jmp     loc_18002C768
0x18002c58f  movzx   eax, bl
0x18002c592  xor     eax, 1
0x18002c595  mov     [rsp+40h], eax; int
0x18002c599  mov     rax, [rbp+37h+var_60]
0x18002c59d  mov     [rsp+0D0h+var_98], rax; struct ProxyResolver *
0x18002c5a2  mov     eax, [rbp+37h+arg_58]
0x18002c5a8  mov     dword ptr [rsp+0D0h+ppwszAcceptTypes], eax; DWORD
0x18002c5ac  mov     [rsp+0D0h+dwFlags], eax; DWORD
0x18002c5b0  mov     r9, [rbp+37h+arg_50]; void *
0x18002c5b7  mov     rdx, [rbp+37h+lpszHeaders]; lpszHeaders
0x18002c5be  mov     rcx, rdi; void *
0x18002c5c1  call    ?SendRequestWithProxyFailover@@YAJPEAXPEBGK0KK_KPEAVProxyResolver@@H@Z; SendRequestWithProxyFailover(void *,ushort const *,ulong,void *,ulong,ulong,unsigned __int64,ProxyResolver *,int)
0x18002c5c6  mov     ebx, eax
0x18002c5c8  test    eax, eax
0x18002c5ca  jns     short loc_18002C5D6
0x18002c5cc  mov     ecx, 29201D7h
0x18002c5d1  jmp     loc_18002C76A
0x18002c5d6  xor     edx, edx; lpReserved
0x18002c5d8  mov     rcx, rdi; hRequest
0x18002c5db  call    cs:__imp_WinHttpReceiveResponse
0x18002c5e1  test    eax, eax
0x18002c5e3  jnz     short loc_18002C5F4
0x18002c5e5  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18002c5ea  mov     ecx, 29901D7h
0x18002c5ef  jmp     loc_18002C768
0x18002c5f4  mov     [rbp+37h+dwBufferLength], 4
0x18002c5fb  mov     [rsp+0D0h+ppwszAcceptTypes], r15; lpdwIndex
  ... truncated ...
```
