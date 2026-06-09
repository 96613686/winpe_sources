# web::http::client::details::winhttp_client::open(void)

- ea: `0x1800dbaf0`
- end: `0x1800dc4f7`
- name: `?open@winhttp_client@details@client@http@web@@IEAAKXZ`
- size: `2567`
- prototype: `unsigned int __fastcall(web::http::client::details::winhttp_client *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800dd350`

## callees

- `0x180018bbc`
- `0x180019000`
- `0x180019508`
- `0x180019fac`
- `0x18001b0a0`
- `0x18001b1d0`
- `0x1800a9e80`
- `0x1800bd230`
- `0x1800cd310`
- `0x1800d6380`
- `0x1800dbaf0`
- `0x1800e5174`
- `0x1800e5248`
- `0x1800e66dc`
- `0x1800e79e0`
- `0x1800ef7e8`
- `0x1800ef8a8`
- `0x1800f6c44`
- `0x180105fec`
- `0x180191010`

## import_xrefs

- `WINHTTP!WinHttpSetTimeouts` at `0x1800dc0bf`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800dc0bf`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800dc17c`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800dc17c`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800dbca7`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800dbca7`
- `WINHTTP!WinHttpSetOption` at `0x1800dc0f3`
- `WINHTTP!WinHttpSetOption` at `0x1800dc120`
- `WINHTTP!WinHttpSetOption` at `0x1800dc0f3`
- `WINHTTP!WinHttpSetOption` at `0x1800dc120`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800dbcbf`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800dbcbf`
- `WINHTTP!WinHttpConnect` at `0x1800dc1cc`
- `WINHTTP!WinHttpConnect` at `0x1800dc1cc`
- `WINHTTP!WinHttpOpen` at `0x1800dc076`
- `WINHTTP!WinHttpOpen` at `0x1800dc076`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc1de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc1de`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dbd31`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dbd47`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc494`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc4a4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc4b4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dbd31`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dbd47`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc494`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc4a4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc4b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall web::http::client::details::winhttp_client::open(web::http::client::details::winhttp_client *this)
{
  DWORD LastError; // ebx
  const WCHAR *lpszProxy; // rdi
  const WCHAR *lpszProxyBypass; // r14
  const struct web::http::client::http_client_config *v6; // r13
  wchar_t **v7; // rsi
  int v8; // eax
  DWORD v9; // r12d
  const wchar_t *lpszAutoConfigUrl; // rsi
  size_t v11; // rax
  wchar_t *v12; // rdx
  char *v13; // rdx
  char *v14; // rdx
  char *v15; // rdx
  char *v16; // rdx
  char *v17; // rdx
  char *v18; // rdx
  int v19; // eax
  const wchar_t *v20; // rcx
  void **v21; // rdx
  unsigned __int64 v22; // r14
  unsigned __int64 v23; // rsi
  void **v24; // rax
  __int64 v25; // rdi
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  char *v28; // r15
  size_t v29; // r14
  void *v30; // rdi
  _BYTE *v31; // rcx
  WINHTTP_PROXY_INFO *p_pProxyInfo; // rdx
  void *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  int v36; // r8d
  const WCHAR *v37; // rdx
  HINTERNET v38; // rax
  void *v39; // rcx
  void *v40; // rcx
  void *v41; // rcx
  void *v42; // rcx
  void *v43; // rcx
  void *v44; // rcx
  wchar_t *v45; // rcx
  void *v46; // rcx
  const struct web::http::client::http_client_config *Buffer; // [rsp+30h] [rbp-D0h] BYREF
  const WCHAR *v48; // [rsp+38h] [rbp-C8h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+40h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-A0h]
  void *Src[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v52; // [rsp+78h] [rbp-88h]
  unsigned __int64 v53; // [rsp+80h] [rbp-80h]
  wchar_t *S1[2]; // [rsp+90h] [rbp-70h] BYREF
  size_t N; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v56; // [rsp+A8h] [rbp-58h]
  void *v57[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v58; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v59; // [rsp+C8h] [rbp-38h]
  void *v60[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v61; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v62; // [rsp+E8h] [rbp-18h]
  void *v63[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v64; // [rsp+100h] [rbp+0h]
  unsigned __int64 v65; // [rsp+108h] [rbp+8h]
  void *v66[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v67; // [rsp+128h] [rbp+28h]
  void *v68[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v69; // [rsp+140h] [rbp+40h]
  unsigned __int64 v70; // [rsp+148h] [rbp+48h]
  void *Block[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v72; // [rsp+160h] [rbp+60h]
  unsigned __int64 v73; // [rsp+168h] [rbp+68h]
  int v74; // [rsp+170h] [rbp+70h]
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v76; // [rsp+198h] [rbp+98h]

  if ( *((_BYTE *)this + 968) )
    return 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 272);
  pplx::details::critical_section_impl::lock((LPCRITICAL_SECTION)((char *)this + 272));
  if ( !*((_BYTE *)this + 968) )
  {
    memset(&pProxyConfig, 0, sizeof(pProxyConfig));
    lpszProxy = 0;
    lpszProxyBypass = 0;
    v48 = 0;
    *((_BYTE *)this + 993) = 0;
    *(_OWORD *)Src = 0;
    v52 = 0;
    v53 = 7;
    LOWORD(Src[0]) = 0;
    std::wstring::wstring(S1, L"/");
    *(_OWORD *)v57 = 0;
    v58 = 0;
    v59 = 7;
    LOWORD(v57[0]) = 0;
    *(_OWORD *)v60 = 0;
    v61 = 0;
    v62 = 7;
    LOWORD(v60[0]) = 0;
    *(_OWORD *)v63 = 0;
    v64 = 0;
    v65 = 7;
    LOWORD(v63[0]) = 0;
    std::wstring::wstring(v66, L"/");
    *(_OWORD *)v68 = 0;
    v69 = 0;
    v70 = 7;
    LOWORD(v68[0]) = 0;
    *(_OWORD *)Block = 0;
    v72 = 0;
    v73 = 7;
    LOWORD(Block[0]) = 0;
    v74 = -1;
    v6 = web::http::client::details::_http_client_communicator::client_config(this);
    Buffer = v6;
    v7 = (wchar_t **)((char *)v6 + 32);
    v8 = *((_DWORD *)v6 + 66);
    switch ( v8 )
    {
      case 0:
        v9 = web::http::client::details::WinHttpDefaultProxyConstant();
        goto LABEL_95;
      case 2:
        v9 = 1;
        goto LABEL_95;
      case 1:
        v9 = web::http::client::details::WinHttpDefaultProxyConstant();
        if ( v9 != 4 )
        {
          *((_BYTE *)this + 993) = 1;
          memset(&pProxyInfo, 0, sizeof(pProxyInfo));
          if ( (!WinHttpGetDefaultProxyConfiguration(&pProxyInfo) || pProxyInfo.dwAccessType == 1)
            && WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
          {
            if ( pProxyConfig.fAutoDetect )
            {
              *((_BYTE *)this + 993) = 1;
            }
            else
            {
              lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
              if ( pProxyConfig.lpszAutoConfigUrl )
              {
                *((_BYTE *)this + 993) = 1;
                v11 = wcslen_0(lpszAutoConfigUrl);
                std::wstring::_Assign<unsigned short>((char *)this + 1000, lpszAutoConfigUrl, v11);
              }
              else if ( pProxyConfig.lpszProxy )
              {
                v9 = 3;
                lpszProxy = pProxyConfig.lpszProxy;
                if ( pProxyConfig.lpszProxyBypass )
                  lpszProxyBypass = pProxyConfig.lpszProxyBypass;
              }
            }
          }
          if ( pProxyInfo.lpszProxy )
            GlobalFree(pProxyInfo.lpszProxy);
          if ( pProxyInfo.lpszProxyBypass )
            GlobalFree(pProxyInfo.lpszProxyBypass);
        }
        goto LABEL_95;
    }
    v9 = 3;
    if ( S1 != v7 )
    {
      if ( *((_QWORD *)v6 + 7) <= 7u )
        v12 = (wchar_t *)((char *)v6 + 32);
      else
        v12 = *v7;
      std::wstring::_Assign<unsigned short>(S1, v12, *((_QWORD *)v6 + 6));
    }
    if ( v57 != (void **)((char *)v6 + 64) )
    {
      if ( *((_QWORD *)v6 + 11) <= 7u )
        v13 = (char *)v6 + 64;
      else
        v13 = (char *)*((_QWORD *)v6 + 8);
      std::wstring::_Assign<unsigned short>(v57, v13, *((_QWORD *)v6 + 10));
    }
    if ( v60 != (void **)((char *)v6 + 96) )
    {
      if ( *((_QWORD *)v6 + 15) <= 7u )
        v14 = (char *)v6 + 96;
      else
        v14 = (char *)*((_QWORD *)v6 + 12);
      std::wstring::_Assign<unsigned short>(v60, v14, *((_QWORD *)v6 + 14));
    }
    if ( v63 != (void **)((char *)v6 + 128) )
    {
      if ( *((_QWORD *)v6 + 19) <= 7u )
        v15 = (char *)v6 + 128;
      else
        v15 = (char *)*((_QWORD *)v6 + 16);
      std::wstring::_Assign<unsigned short>(v63, v15, *((_QWORD *)v6 + 18));
    }
    if ( v66 != (void **)((char *)v6 + 160) )
    {
      if ( *((_QWORD *)v6 + 23) <= 7u )
        v16 = (char *)v6 + 160;
      else
        v16 = (char *)*((_QWORD *)v6 + 20);
      std::wstring::_Assign<unsigned short>(v66, v16, *((_QWORD *)v6 + 22));
    }
    if ( v68 != (void **)((char *)v6 + 192) )
    {
      if ( *((_QWORD *)v6 + 27) <= 7u )
        v17 = (char *)v6 + 192;
      else
        v17 = (char *)*((_QWORD *)v6 + 24);
      std::wstring::_Assign<unsigned short>(v68, v17, *((_QWORD *)v6 + 26));
    }
    if ( Block != (void **)((char *)v6 + 224) )
    {
      if ( *((_QWORD *)v6 + 31) <= 7u )
        v18 = (char *)v6 + 224;
      else
        v18 = (char *)*((_QWORD *)v6 + 28);
      std::wstring::_Assign<unsigned short>(Block, v18, *((_QWORD *)v6 + 30));
    }
    v19 = *((_DWORD *)v6 + 64);
    v74 = v19;
    if ( N )
    {
      v20 = (const wchar_t *)S1;
      if ( v56 > 7 )
        v20 = S1[0];
      if ( N != 1 )
      {
LABEL_66:
        if ( !v19 )
        {
          lpszProxy = (const WCHAR *)v60;
          if ( v62 > 7 )
            lpszProxy = (const WCHAR *)v60[0];
          goto LABEL_95;
        }
        goto LABEL_70;
      }
      if ( wmemcmp(v20, L"/", 1u) )
      {
        v19 = v74;
        goto LABEL_66;
      }
    }
LABEL_70:
    v21 = v60;
    if ( v62 > 7 )
      v21 = (void **)v60[0];
    std::wstring::_Assign<unsigned short>(Src, v21, v61);
    if ( v74 > 0 )
    {
      v22 = v52;
      v23 = v53;
      if ( v52 >= v53 )
      {
        v25 = 0x7FFFFFFFFFFFFFFELL;
        if ( 0x7FFFFFFFFFFFFFFELL == v52 )
          goto LABEL_172;
        v26 = (v52 + 1) | 7;
        if ( v26 <= 0x7FFFFFFFFFFFFFFELL )
        {
          v27 = v53 >> 1;
          if ( v53 <= 0x7FFFFFFFFFFFFFFELL - (v53 >> 1) )
          {
            v25 = (v52 + 1) | 7;
            if ( v26 < v53 + v27 )
              v25 = v53 + v27;
          }
        }
        v28 = (char *)std::allocator<unsigned short>::allocate(Src, v25 + 1);
        v52 = v22 + 1;
        v53 = v25;
        v29 = 2 * v22;
        if ( v23 <= 7 )
        {
          memcpy_0(v28, Src, v29);
          *(_DWORD *)&v28[v29] = 58;
        }
        else
        {
          v30 = Src[0];
          memcpy_0(v28, Src[0], v29);
          *(_DWORD *)&v28[v29] = 58;
          if ( 2 * v23 + 2 < 0x1000 )
          {
            operator delete(v30);
          }
          else
          {
            v31 = (_BYTE *)*((_QWORD *)v30 - 1);
            if ( (unsigned __int64)((_BYTE *)v30 - v31 - 8) > 0x1F )
              __fastfail(5u);
            operator delete(v31);
          }
        }
        Src[0] = v28;
        v6 = Buffer;
      }
      else
      {
        ++v52;
        v24 = Src;
        if ( v53 > 7 )
          v24 = (void **)Src[0];
        *(_DWORD *)((char *)v24 + 2 * v22) = 58;
      }
      std::to_wstring(&pProxyInfo, (unsigned int)v74);
      p_pProxyInfo = &pProxyInfo;
      if ( v76 > 7 )
        p_pProxyInfo = *(WINHTTP_PROXY_INFO **)&pProxyInfo.dwAccessType;
      std::wstring::_Append<unsigned short>(Src, p_pProxyInfo, pProxyInfo.lpszProxyBypass);
      Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId::~DeviceOrUserTargetId((Microsoft::Windows::Mdm::MdmDiagnosticSource::DeviceOrUserTargetId *)&pProxyInfo);
      lpszProxyBypass = v48;
    }
    lpszProxy = (const WCHAR *)Src;
    if ( v53 > 7 )
      lpszProxy = (const WCHAR *)Src[0];
LABEL_95:
    v33 = WinHttpOpen(0, v9, lpszProxy, lpszProxyBypass, 0x10000000u);
    *((_QWORD *)this + 122) = v33;
    if ( !v33 )
      goto LABEL_114;
    v34 = *((_QWORD *)v6 + 51) / 1000LL;
    if ( (int)v34 < 1 )
      LODWORD(v34) = 1;
    if ( !WinHttpSetTimeouts(v33, v34, v34, v34, v34) )
      goto LABEL_114;
    if ( *((_BYTE *)v6 + 400) )
    {
      LODWORD(Buffer) = 1;
      if ( !WinHttpSetOption(*((HINTERNET *)this + 122), 0x49u, &Buffer, 4u) )
        goto LABEL_114;
    }
    LODWORD(Buffer) = 2720;
    if ( !WinHttpSetOption(*((HINTERNET *)this + 122), 0x54u, &Buffer, 4u) )
      goto LABEL_114;
    if ( !*((_QWORD *)v6 + 69) )
    {
LABEL_105:
      if ( WinHttpSetStatusCallback(
             *((HINTERNET *)this + 122),
             web::http::client::details::winhttp_client::completion_callback,
             0x97F4C30u,
             0) != (WINHTTP_STATUS_CALLBACK)-1LL )
      {
        if ( web::uri::is_port_default((web::http::client::details::winhttp_client *)((char *)this + 40)) )
        {
          LOWORD(v36) = 80;
          if ( *((_BYTE *)this + 992) )
            LOWORD(v36) = 443;
        }
        else
        {
          v36 = *((_DWORD *)this + 66);
        }
        v37 = (const WCHAR *)((char *)this + 104);
        if ( *((_QWORD *)this + 16) > 7u )
          v37 = *(const WCHAR **)v37;
        v38 = WinHttpConnect(*((HINTERNET *)this + 122), v37, v36, 0);
        *((_QWORD *)this + 123) = v38;
        if ( v38 )
        {
          *((_BYTE *)this + 968) = 1;
          LastError = 0;
LABEL_116:
          if ( v73 > 7 )
          {
            if ( 2 * v73 + 2 < 0x1000 )
            {
              v39 = Block[0];
            }
            else
            {
              v39 = (void *)*((_QWORD *)Block[0] - 1);
              if ( (unsigned __int64)((char *)Block[0] - (char *)v39 - 8) > 0x1F )
                goto LABEL_155;
            }
            operator delete(v39);
          }
          v72 = 0;
          v73 = 7;
          LOWORD(Block[0]) = 0;
          if ( v70 > 7 )
          {
            if ( 2 * v70 + 2 < 0x1000 )
            {
              v40 = v68[0];
            }
            else
            {
              v40 = (void *)*((_QWORD *)v68[0] - 1);
              if ( (unsigned __int64)((char *)v68[0] - (char *)v40 - 8) > 0x1F )
                goto LABEL_155;
            }
            operator delete(v40);
          }
          v69 = 0;
          v70 = 7;
          LOWORD(v68[0]) = 0;
          if ( v67 > 7 )
          {
            if ( 2 * v67 + 2 < 0x1000 )
            {
              v41 = v66[0];
            }
            else
            {
              v41 = (void *)*((_QWORD *)v66[0] - 1);
              if ( (unsigned __int64)((char *)v66[0] - (char *)v41 - 8) > 0x1F )
                goto LABEL_155;
            }
            operator delete(v41);
          }
          v66[2] = 0;
          v67 = 7;
          LOWORD(v66[0]) = 0;
          if ( v65 > 7 )
          {
            if ( 2 * v65 + 2 < 0x1000 )
            {
              v42 = v63[0];
            }
            else
            {
              v42 = (void *)*((_QWORD *)v63[0] - 1);
              if ( (unsigned __int64)((char *)v63[0] - (char *)v42 - 8) > 0x1F )
                goto LABEL_155;
            }
            operator delete(v42);
          }
          v64 = 0;
          v65 = 7;
          LOWORD(v63[0]) = 0;
          if ( v62 > 7 )
          {
            if ( 2 * v62 + 2 < 0x1000 )
            {
              v43 = v60[0];
            }
            else
            {
              v43 = (void *)*((_QWORD *)v60[0] - 1);
              if ( (unsigned __int64)((char *)v60[0] - (char *)v43 - 8) > 0x1F )
                goto LABEL_155;
            }
            operator delete(v43);
          }
          v61 = 0;
          v62 = 7;
          LOWORD(v60[0]) = 0;
          if ( v59 > 7 )
          {
            if ( 2 * v59 + 2 < 0x1000 )
            {
              v44 = v57[0];
            }
            else
            {
              v44 = (void *)*((_QWORD *)v57[0] - 1);
              if ( (unsigned __int64)((char *)v57[0] - (char *)v44 - 8) > 0x1F )
                goto LABEL_155;
            }
            operator delete(v44);
          }
          v58 = 0;
          v59 = 7;
          LOWORD(v57[0]) = 0;
          if ( v56 > 7 )
          {
            if ( 2 * v56 + 2 < 0x1000 )
            {
              v45 = S1[0];
            }
            else
            {
              v45 = (wchar_t *)*((_QWORD *)S1[0] - 1);
              if ( (unsigned __int64)((char *)S1[0] - (char *)v45 - 8) > 0x1F )
LABEL_155:
                __fastfail(5u);
            }
            operator delete(v45);
          }
          N = 0;
          v56 = 7;
          LOWORD(S1[0]) = 0;
          if ( v53 > 7 )
          {
            if ( 2 * v53 + 2 < 0x1000 )
            {
              v46 = Src[0];
            }
            else
            {
              v46 = (void *)*((_QWORD *)Src[0] - 1);
              if ( (unsigned __int64)((char *)Src[0] - (char *)v46 - 8) > 0x1F )
                __fastfail(5u);
            }
            operator delete(v46);
          }
          v52 = 0;
          v53 = 7;
          LOWORD(Src[0]) = 0;
          if ( pProxyConfig.lpszAutoConfigUrl )
            GlobalFree(pProxyConfig.lpszAutoConfigUrl);
          if ( pProxyConfig.lpszProxy )
            GlobalFree(pProxyConfig.lpszProxy);
          if ( pProxyConfig.lpszProxyBypass )
            GlobalFree(pProxyConfig.lpszProxyBypass);
          goto LABEL_170;
        }
      }
LABEL_114:
      LastError = GetLastError();
      goto LABEL_116;
    }
    v48 = (const WCHAR *)*((_QWORD *)this + 122);
    v35 = *((_QWORD *)v6 + 69);
    if ( v35 )
    {
      (*(void (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v35 + 16LL))(v35, &v48);
      goto LABEL_105;
    }
    std::_Xbad_function_call();
LABEL_172:
    std::_Xlen_string();
  }
  LastError = 0;
LABEL_170:
  pplx::details::critical_section_impl::unlock(lpCriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x1800dbaf0  push    rbp
0x1800dbaf2  push    rbx
0x1800dbaf3  push    rsi
0x1800dbaf4  push    rdi
0x1800dbaf5  push    r12
0x1800dbaf7  push    r13
0x1800dbaf9  push    r14
0x1800dbafb  push    r15
0x1800dbafd  lea     rbp, [rsp-0B8h]
0x1800dbb05  sub     rsp, 1B8h
0x1800dbb0c  mov     rax, cs:__security_cookie
0x1800dbb13  xor     rax, rsp
0x1800dbb16  mov     [rbp+0F0h+var_50], rax
0x1800dbb1d  mov     rbx, rcx
0x1800dbb20  xor     esi, esi
0x1800dbb22  movzx   eax, byte ptr [rcx+3C8h]
0x1800dbb29  nop
0x1800dbb2a  test    al, al
0x1800dbb2c  jz      short loc_1800DBB35
0x1800dbb2e  xor     eax, eax
0x1800dbb30  jmp     loc_1800DC4C8
0x1800dbb35  lea     rax, [rcx+110h]
0x1800dbb3c  mov     [rsp+1F0h+lpCriticalSection], rax
0x1800dbb41  mov     rcx, rax; lpCriticalSection
0x1800dbb44  call    ?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x1800dbb49  nop
0x1800dbb4a  movzx   eax, byte ptr [rbx+3C8h]
0x1800dbb51  nop
0x1800dbb52  test    al, al
0x1800dbb54  jz      short loc_1800DBB5D
0x1800dbb56  mov     ebx, esi
0x1800dbb58  jmp     loc_1800DC4BB
0x1800dbb5d  xorps   xmm0, xmm0
0x1800dbb60  movups  xmmword ptr [rsp+1F0h+pProxyConfig.fAutoDetect], xmm0
0x1800dbb65  movups  xmmword ptr [rsp+1F0h+pProxyConfig.lpszProxy], xmm0
0x1800dbb6a  mov     rdi, rsi
0x1800dbb6d  mov     r14, rsi
0x1800dbb70  mov     [rsp+1F0h+var_1B8], rsi
0x1800dbb75  mov     [rbx+3E1h], dil
0x1800dbb7c  movups  xmmword ptr [rsp+1F0h+Src], xmm0
0x1800dbb81  mov     [rsp+1F0h+var_178], rsi
0x1800dbb86  mov     [rbp+0F0h+var_170], 7
0x1800dbb8e  mov     word ptr [rsp+1F0h+Src], si
0x1800dbb93  lea     rdx, asc_1801D0CA8; "/"
0x1800dbb9a  lea     rcx, [rbp+0F0h+S1]
0x1800dbb9e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dbba3  nop
0x1800dbba4  lea     rax, [rbp+0F0h+var_140]
0x1800dbba8  mov     [rsp+1F0h+Buffer], rax
0x1800dbbad  xorps   xmm0, xmm0
0x1800dbbb0  movups  xmmword ptr [rbp+0F0h+var_140], xmm0
0x1800dbbb4  mov     [rbp+0F0h+var_130], rsi
0x1800dbbb8  mov     [rbp+0F0h+var_128], 7
0x1800dbbc0  mov     word ptr [rbp+0F0h+var_140], si
0x1800dbbc4  movups  xmmword ptr [rbp+0F0h+var_120], xmm0
0x1800dbbc8  mov     [rbp+0F0h+var_110], rsi
0x1800dbbcc  mov     [rbp+0F0h+var_108], 7
0x1800dbbd4  mov     word ptr [rbp+0F0h+var_120], si
0x1800dbbd8  movups  xmmword ptr [rbp+0F0h+var_100], xmm0
0x1800dbbdc  mov     [rbp+0F0h+var_F0], rsi
0x1800dbbe0  mov     [rbp+0F0h+var_E8], 7
0x1800dbbe8  mov     word ptr [rbp+0F0h+var_100], si
0x1800dbbec  lea     rdx, asc_1801D0CA8; "/"
0x1800dbbf3  lea     rcx, [rbp+0F0h+var_E0]
0x1800dbbf7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dbbfc  xorps   xmm0, xmm0
0x1800dbbff  movups  xmmword ptr [rbp+0F0h+var_C0], xmm0
0x1800dbc03  mov     [rbp+0F0h+var_B0], rsi
0x1800dbc07  mov     [rbp+0F0h+var_A8], 7
0x1800dbc0f  mov     word ptr [rbp+0F0h+var_C0], si
0x1800dbc13  movups  xmmword ptr [rbp+0F0h+Block], xmm0
0x1800dbc17  mov     [rbp+0F0h+var_90], rsi
0x1800dbc1b  mov     [rbp+0F0h+var_88], 7
0x1800dbc23  mov     word ptr [rbp+0F0h+Block], si
0x1800dbc27  mov     [rbp+0F0h+var_80], 0FFFFFFFFh
0x1800dbc2e  mov     rcx, rbx; this
0x1800dbc31  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800dbc36  mov     r13, rax
0x1800dbc39  mov     [rsp+1F0h+Buffer], rax
0x1800dbc3e  lea     rsi, [rax+20h]
0x1800dbc42  mov     eax, [rsi+0E8h]
0x1800dbc48  mov     r15d, 1
0x1800dbc4e  test    eax, eax
0x1800dbc50  jnz     short loc_1800DBC5F
0x1800dbc52  call    web__http__client__details__WinHttpDefaultProxyConstant
0x1800dbc57  mov     r12d, eax
0x1800dbc5a  jmp     loc_1800DC063
0x1800dbc5f  cmp     eax, 2
0x1800dbc62  jnz     short loc_1800DBC6C
0x1800dbc64  mov     r12d, r15d
0x1800dbc67  jmp     loc_1800DC063
0x1800dbc6c  cmp     eax, r15d
0x1800dbc6f  jnz     loc_1800DBD52
0x1800dbc75  call    web__http__client__details__WinHttpDefaultProxyConstant
0x1800dbc7a  mov     r12d, eax
0x1800dbc7d  cmp     eax, 4
0x1800dbc80  jz      loc_1800DC063
0x1800dbc86  mov     [rbx+3E1h], r15b
0x1800dbc8d  xorps   xmm0, xmm0
0x1800dbc90  xor     eax, eax
0x1800dbc92  movups  xmmword ptr [rbp+0F0h+pProxyInfo.dwAccessType], xmm0
0x1800dbc99  mov     [rbp+0F0h+pProxyInfo.lpszProxyBypass], rax
0x1800dbca0  lea     rcx, [rbp+0F0h+pProxyInfo]; pProxyInfo
0x1800dbca7  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x1800dbcad  test    eax, eax
0x1800dbcaf  jz      short loc_1800DBCBA
0x1800dbcb1  cmp     [rbp+0F0h+pProxyInfo.dwAccessType], 1
0x1800dbcb8  jnz     short loc_1800DBD25
0x1800dbcba  lea     rcx, [rsp+1F0h+pProxyConfig]; pProxyConfig
0x1800dbcbf  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800dbcc5  test    eax, eax
0x1800dbcc7  jz      short loc_1800DBD25
0x1800dbcc9  cmp     [rsp+1F0h+pProxyConfig.fAutoDetect], 0
0x1800dbcce  jz      short loc_1800DBCD9
0x1800dbcd0  mov     byte ptr [rbx+3E1h], 1
0x1800dbcd7  jmp     short loc_1800DBD25
0x1800dbcd9  mov     rsi, [rsp+1F0h+pProxyConfig.lpszAutoConfigUrl]
0x1800dbcde  test    rsi, rsi
0x1800dbce1  jz      short loc_1800DBD06
0x1800dbce3  mov     byte ptr [rbx+3E1h], 1
0x1800dbcea  mov     rcx, rsi; String
0x1800dbced  call    wcslen_0
0x1800dbcf2  lea     rcx, [rbx+3E8h]
0x1800dbcf9  mov     r8, rax
0x1800dbcfc  mov     rdx, rsi
0x1800dbcff  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbd04  jmp     short loc_1800DBD25
0x1800dbd06  mov     rax, [rsp+1F0h+pProxyConfig.lpszProxy]
0x1800dbd0b  test    rax, rax
0x1800dbd0e  jz      short loc_1800DBD25
0x1800dbd10  mov     r12d, 3
0x1800dbd16  mov     rdi, rax
0x1800dbd19  mov     rax, [rsp+1F0h+pProxyConfig.lpszProxyBypass]
0x1800dbd1e  test    rax, rax
0x1800dbd21  cmovnz  r14, rax
0x1800dbd25  mov     rcx, [rbp+0F0h+pProxyInfo.lpszProxy]; hMem
0x1800dbd2c  test    rcx, rcx
0x1800dbd2f  jz      short loc_1800DBD37
0x1800dbd31  call    cs:__imp_GlobalFree
0x1800dbd37  mov     rcx, [rbp+0F0h+pProxyInfo.lpszProxyBypass]; hMem
0x1800dbd3e  test    rcx, rcx
0x1800dbd41  jz      loc_1800DC063
0x1800dbd47  call    cs:__imp_GlobalFree
0x1800dbd4d  jmp     loc_1800DC063
0x1800dbd52  mov     r12d, 3
0x1800dbd58  lea     rax, [rbp+0F0h+S1]
0x1800dbd5c  cmp     rax, rsi
0x1800dbd5f  jz      short loc_1800DBD7D
0x1800dbd61  cmp     qword ptr [rsi+18h], 7
0x1800dbd66  jbe     short loc_1800DBD6D
0x1800dbd68  mov     rdx, [rsi]
0x1800dbd6b  jmp     short loc_1800DBD70
0x1800dbd6d  mov     rdx, rsi
0x1800dbd70  mov     r8, [rsi+10h]
0x1800dbd74  lea     rcx, [rbp+0F0h+S1]
0x1800dbd78  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbd7d  lea     rdi, [rsi+20h]
0x1800dbd81  lea     rax, [rbp+0F0h+var_140]
0x1800dbd85  cmp     rax, rdi
0x1800dbd88  jz      short loc_1800DBDA6
0x1800dbd8a  cmp     qword ptr [rdi+18h], 7
0x1800dbd8f  jbe     short loc_1800DBD96
0x1800dbd91  mov     rdx, [rdi]
0x1800dbd94  jmp     short loc_1800DBD99
0x1800dbd96  mov     rdx, rdi
0x1800dbd99  mov     r8, [rdi+10h]
0x1800dbd9d  lea     rcx, [rbp+0F0h+var_140]
0x1800dbda1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbda6  lea     r8, [rdi+20h]
0x1800dbdaa  lea     rax, [rbp+0F0h+var_120]
0x1800dbdae  cmp     rax, r8
0x1800dbdb1  jz      short loc_1800DBDCF
0x1800dbdb3  cmp     qword ptr [r8+18h], 7
0x1800dbdb8  jbe     short loc_1800DBDBF
0x1800dbdba  mov     rdx, [r8]
0x1800dbdbd  jmp     short loc_1800DBDC2
0x1800dbdbf  mov     rdx, r8
0x1800dbdc2  mov     r8, [r8+10h]
0x1800dbdc6  lea     rcx, [rbp+0F0h+var_120]
0x1800dbdca  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbdcf  lea     r8, [rdi+40h]
0x1800dbdd3  lea     rax, [rbp+0F0h+var_100]
0x1800dbdd7  cmp     rax, r8
0x1800dbdda  jz      short loc_1800DBDF8
0x1800dbddc  cmp     qword ptr [r8+18h], 7
0x1800dbde1  jbe     short loc_1800DBDE8
0x1800dbde3  mov     rdx, [r8]
0x1800dbde6  jmp     short loc_1800DBDEB
0x1800dbde8  mov     rdx, r8
0x1800dbdeb  mov     r8, [r8+10h]
0x1800dbdef  lea     rcx, [rbp+0F0h+var_100]
0x1800dbdf3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbdf8  lea     r8, [rdi+60h]
0x1800dbdfc  lea     rax, [rbp+0F0h+var_E0]
0x1800dbe00  cmp     rax, r8
0x1800dbe03  jz      short loc_1800DBE21
0x1800dbe05  cmp     qword ptr [r8+18h], 7
0x1800dbe0a  jbe     short loc_1800DBE11
0x1800dbe0c  mov     rdx, [r8]
0x1800dbe0f  jmp     short loc_1800DBE14
0x1800dbe11  mov     rdx, r8
0x1800dbe14  mov     r8, [r8+10h]
0x1800dbe18  lea     rcx, [rbp+0F0h+var_E0]
0x1800dbe1c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbe21  lea     r8, [rdi+80h]
0x1800dbe28  lea     rax, [rbp+0F0h+var_C0]
0x1800dbe2c  cmp     rax, r8
0x1800dbe2f  jz      short loc_1800DBE4D
0x1800dbe31  cmp     qword ptr [r8+18h], 7
0x1800dbe36  jbe     short loc_1800DBE3D
0x1800dbe38  mov     rdx, [r8]
0x1800dbe3b  jmp     short loc_1800DBE40
0x1800dbe3d  mov     rdx, r8
0x1800dbe40  mov     r8, [r8+10h]
0x1800dbe44  lea     rcx, [rbp+0F0h+var_C0]
0x1800dbe48  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbe4d  lea     r8, [rdi+0A0h]
0x1800dbe54  lea     rax, [rbp+0F0h+Block]
0x1800dbe58  cmp     rax, r8
0x1800dbe5b  jz      short loc_1800DBE79
0x1800dbe5d  cmp     qword ptr [r8+18h], 7
0x1800dbe62  jbe     short loc_1800DBE69
0x1800dbe64  mov     rdx, [r8]
0x1800dbe67  jmp     short loc_1800DBE6C
0x1800dbe69  mov     rdx, r8
0x1800dbe6c  mov     r8, [r8+10h]
0x1800dbe70  lea     rcx, [rbp+0F0h+Block]
0x1800dbe74  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbe79  mov     eax, [rdi+0C0h]
0x1800dbe7f  mov     [rbp+0F0h+var_80], eax
0x1800dbe82  mov     r8, [rbp+0F0h+N]; N
0x1800dbe86  test    r8, r8
0x1800dbe89  jz      short loc_1800DBEC8
0x1800dbe8b  lea     rcx, [rbp+0F0h+S1]
0x1800dbe8f  cmp     [rbp+0F0h+var_148], 7
0x1800dbe94  cmova   rcx, [rbp+0F0h+S1]; S1
0x1800dbe99  cmp     r8, r15
0x1800dbe9c  jnz     short loc_1800DBEB1
0x1800dbe9e  lea     rdx, asc_1801D0CA8; "/"
0x1800dbea5  call    wmemcmp
0x1800dbeaa  test    eax, eax
0x1800dbeac  jz      short loc_1800DBEC8
0x1800dbeae  mov     eax, [rbp+0F0h+var_80]
0x1800dbeb1  test    eax, eax
0x1800dbeb3  jnz     short loc_1800DBEC8
0x1800dbeb5  lea     rdi, [rbp+0F0h+var_120]
0x1800dbeb9  cmp     [rbp+0F0h+var_108], 7
0x1800dbebe  cmova   rdi, [rbp+0F0h+var_120]
0x1800dbec3  jmp     loc_1800DC063
0x1800dbec8  lea     rdx, [rbp+0F0h+var_120]
0x1800dbecc  cmp     [rbp+0F0h+var_108], 7
0x1800dbed1  cmova   rdx, [rbp+0F0h+var_120]
0x1800dbed6  mov     r8, [rbp+0F0h+var_110]
0x1800dbeda  lea     rcx, [rsp+1F0h+Src]
0x1800dbedf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbee4  cmp     [rbp+0F0h+var_80], 0
0x1800dbee8  jle     loc_1800DC053
0x1800dbeee  mov     r14, [rsp+1F0h+var_178]
0x1800dbef3  mov     rsi, [rbp+0F0h+var_170]
0x1800dbef7  cmp     r14, rsi
0x1800dbefa  jnb     short loc_1800DBF23
0x1800dbefc  lea     rax, [r14+1]
0x1800dbf00  mov     [rsp+1F0h+var_178], rax
0x1800dbf05  lea     rax, [rsp+1F0h+Src]
0x1800dbf0a  cmp     rsi, 7
0x1800dbf0e  cmova   rax, [rsp+1F0h+Src]
0x1800dbf14  lea     rcx, [rax+r14*2]
0x1800dbf18  mov     dword ptr [rcx], 3Ah ; ':'
0x1800dbf1e  jmp     loc_1800DC009
0x1800dbf23  mov     rdi, 7FFFFFFFFFFFFFFEh
0x1800dbf2d  mov     rax, rdi
0x1800dbf30  sub     rax, r14
0x1800dbf33  cmp     rax, r15
0x1800dbf36  jb      loc_1800DC4F1
0x1800dbf3c  lea     r13, [r14+1]
0x1800dbf40  mov     rcx, r13
0x1800dbf43  or      rcx, 7
0x1800dbf47  cmp     rcx, rdi
0x1800dbf4a  ja      short loc_1800DBF6B
0x1800dbf4c  mov     rdx, rsi
0x1800dbf4f  shr     rdx, 1
0x1800dbf52  mov     rax, rdi
0x1800dbf55  sub     rax, rdx
0x1800dbf58  cmp     rsi, rax
0x1800dbf5b  ja      short loc_1800DBF6B
0x1800dbf5d  lea     rax, [rsi+rdx]
0x1800dbf61  mov     rdi, rcx
0x1800dbf64  cmp     rcx, rax
0x1800dbf67  cmovb   rdi, rax
0x1800dbf6b  lea     rdx, [rdi+1]
0x1800dbf6f  lea     rcx, [rsp+1F0h+Src]
0x1800dbf74  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x1800dbf79  mov     r15, rax
0x1800dbf7c  mov     [rsp+1F0h+var_178], r13
0x1800dbf81  mov     [rbp+0F0h+var_170], rdi
0x1800dbf85  add     r14, r14
0x1800dbf88  mov     r8, r14; Size
0x1800dbf8b  mov     rcx, rax; void *
0x1800dbf8e  cmp     rsi, 7
0x1800dbf92  jbe     short loc_1800DBFE7
  ... truncated ...
```
