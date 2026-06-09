# web::http::client::details::winhttp_client::open(void)

- ea: `0x1800dbc90`
- end: `0x1800dc697`
- name: `?open@winhttp_client@details@client@http@web@@IEAAKXZ`
- size: `2567`
- prototype: `unsigned int __fastcall(web::http::client::details::winhttp_client *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800dd4f0`

## callees

- `0x180018c3c`
- `0x180019080`
- `0x180019588`
- `0x18001a03c`
- `0x18001b180`
- `0x18001b2b0`
- `0x1800aa020`
- `0x1800bd3d0`
- `0x1800cd4b0`
- `0x1800d6520`
- `0x1800dbc90`
- `0x1800e5314`
- `0x1800e53ec`
- `0x1800e68b0`
- `0x1800e7ba0`
- `0x1800effac`
- `0x1800f008c`
- `0x1800f7a78`
- `0x180107298`
- `0x180193010`

## import_xrefs

- `WINHTTP!WinHttpSetTimeouts` at `0x1800dc25f`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800dc25f`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800dc31c`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800dc31c`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800dbe47`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x1800dbe47`
- `WINHTTP!WinHttpSetOption` at `0x1800dc293`
- `WINHTTP!WinHttpSetOption` at `0x1800dc2c0`
- `WINHTTP!WinHttpSetOption` at `0x1800dc293`
- `WINHTTP!WinHttpSetOption` at `0x1800dc2c0`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800dbe5f`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x1800dbe5f`
- `WINHTTP!WinHttpConnect` at `0x1800dc36c`
- `WINHTTP!WinHttpConnect` at `0x1800dc36c`
- `WINHTTP!WinHttpOpen` at `0x1800dc216`
- `WINHTTP!WinHttpOpen` at `0x1800dc216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc37e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc37e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dbed1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dbee7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc634`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc644`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc654`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dbed1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dbee7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc634`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc644`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800dc654`

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
0x1800dbc90  push    rbp
0x1800dbc92  push    rbx
0x1800dbc93  push    rsi
0x1800dbc94  push    rdi
0x1800dbc95  push    r12
0x1800dbc97  push    r13
0x1800dbc99  push    r14
0x1800dbc9b  push    r15
0x1800dbc9d  lea     rbp, [rsp-0B8h]
0x1800dbca5  sub     rsp, 1B8h
0x1800dbcac  mov     rax, cs:__security_cookie
0x1800dbcb3  xor     rax, rsp
0x1800dbcb6  mov     [rbp+0F0h+var_50], rax
0x1800dbcbd  mov     rbx, rcx
0x1800dbcc0  xor     esi, esi
0x1800dbcc2  movzx   eax, byte ptr [rcx+3C8h]
0x1800dbcc9  nop
0x1800dbcca  test    al, al
0x1800dbccc  jz      short loc_1800DBCD5
0x1800dbcce  xor     eax, eax
0x1800dbcd0  jmp     loc_1800DC668
0x1800dbcd5  lea     rax, [rcx+110h]
0x1800dbcdc  mov     [rsp+1F0h+lpCriticalSection], rax
0x1800dbce1  mov     rcx, rax; lpCriticalSection
0x1800dbce4  call    ?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x1800dbce9  nop
0x1800dbcea  movzx   eax, byte ptr [rbx+3C8h]
0x1800dbcf1  nop
0x1800dbcf2  test    al, al
0x1800dbcf4  jz      short loc_1800DBCFD
0x1800dbcf6  mov     ebx, esi
0x1800dbcf8  jmp     loc_1800DC65B
0x1800dbcfd  xorps   xmm0, xmm0
0x1800dbd00  movups  xmmword ptr [rsp+1F0h+pProxyConfig.fAutoDetect], xmm0
0x1800dbd05  movups  xmmword ptr [rsp+1F0h+pProxyConfig.lpszProxy], xmm0
0x1800dbd0a  mov     rdi, rsi
0x1800dbd0d  mov     r14, rsi
0x1800dbd10  mov     [rsp+1F0h+var_1B8], rsi
0x1800dbd15  mov     [rbx+3E1h], dil
0x1800dbd1c  movups  xmmword ptr [rsp+1F0h+Src], xmm0
0x1800dbd21  mov     [rsp+1F0h+var_178], rsi
0x1800dbd26  mov     [rbp+0F0h+var_170], 7
0x1800dbd2e  mov     word ptr [rsp+1F0h+Src], si
0x1800dbd33  lea     rdx, asc_1801D2C90; "/"
0x1800dbd3a  lea     rcx, [rbp+0F0h+S1]
0x1800dbd3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dbd43  nop
0x1800dbd44  lea     rax, [rbp+0F0h+var_140]
0x1800dbd48  mov     [rsp+1F0h+Buffer], rax
0x1800dbd4d  xorps   xmm0, xmm0
0x1800dbd50  movups  xmmword ptr [rbp+0F0h+var_140], xmm0
0x1800dbd54  mov     [rbp+0F0h+var_130], rsi
0x1800dbd58  mov     [rbp+0F0h+var_128], 7
0x1800dbd60  mov     word ptr [rbp+0F0h+var_140], si
0x1800dbd64  movups  xmmword ptr [rbp+0F0h+var_120], xmm0
0x1800dbd68  mov     [rbp+0F0h+var_110], rsi
0x1800dbd6c  mov     [rbp+0F0h+var_108], 7
0x1800dbd74  mov     word ptr [rbp+0F0h+var_120], si
0x1800dbd78  movups  xmmword ptr [rbp+0F0h+var_100], xmm0
0x1800dbd7c  mov     [rbp+0F0h+var_F0], rsi
0x1800dbd80  mov     [rbp+0F0h+var_E8], 7
0x1800dbd88  mov     word ptr [rbp+0F0h+var_100], si
0x1800dbd8c  lea     rdx, asc_1801D2C90; "/"
0x1800dbd93  lea     rcx, [rbp+0F0h+var_E0]
0x1800dbd97  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800dbd9c  xorps   xmm0, xmm0
0x1800dbd9f  movups  xmmword ptr [rbp+0F0h+var_C0], xmm0
0x1800dbda3  mov     [rbp+0F0h+var_B0], rsi
0x1800dbda7  mov     [rbp+0F0h+var_A8], 7
0x1800dbdaf  mov     word ptr [rbp+0F0h+var_C0], si
0x1800dbdb3  movups  xmmword ptr [rbp+0F0h+Block], xmm0
0x1800dbdb7  mov     [rbp+0F0h+var_90], rsi
0x1800dbdbb  mov     [rbp+0F0h+var_88], 7
0x1800dbdc3  mov     word ptr [rbp+0F0h+Block], si
0x1800dbdc7  mov     [rbp+0F0h+var_80], 0FFFFFFFFh
0x1800dbdce  mov     rcx, rbx; this
0x1800dbdd1  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x1800dbdd6  mov     r13, rax
0x1800dbdd9  mov     [rsp+1F0h+Buffer], rax
0x1800dbdde  lea     rsi, [rax+20h]
0x1800dbde2  mov     eax, [rsi+0E8h]
0x1800dbde8  mov     r15d, 1
0x1800dbdee  test    eax, eax
0x1800dbdf0  jnz     short loc_1800DBDFF
0x1800dbdf2  call    web__http__client__details__WinHttpDefaultProxyConstant
0x1800dbdf7  mov     r12d, eax
0x1800dbdfa  jmp     loc_1800DC203
0x1800dbdff  cmp     eax, 2
0x1800dbe02  jnz     short loc_1800DBE0C
0x1800dbe04  mov     r12d, r15d
0x1800dbe07  jmp     loc_1800DC203
0x1800dbe0c  cmp     eax, r15d
0x1800dbe0f  jnz     loc_1800DBEF2
0x1800dbe15  call    web__http__client__details__WinHttpDefaultProxyConstant
0x1800dbe1a  mov     r12d, eax
0x1800dbe1d  cmp     eax, 4
0x1800dbe20  jz      loc_1800DC203
0x1800dbe26  mov     [rbx+3E1h], r15b
0x1800dbe2d  xorps   xmm0, xmm0
0x1800dbe30  xor     eax, eax
0x1800dbe32  movups  xmmword ptr [rbp+0F0h+pProxyInfo.dwAccessType], xmm0
0x1800dbe39  mov     [rbp+0F0h+pProxyInfo.lpszProxyBypass], rax
0x1800dbe40  lea     rcx, [rbp+0F0h+pProxyInfo]; pProxyInfo
0x1800dbe47  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x1800dbe4d  test    eax, eax
0x1800dbe4f  jz      short loc_1800DBE5A
0x1800dbe51  cmp     [rbp+0F0h+pProxyInfo.dwAccessType], 1
0x1800dbe58  jnz     short loc_1800DBEC5
0x1800dbe5a  lea     rcx, [rsp+1F0h+pProxyConfig]; pProxyConfig
0x1800dbe5f  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x1800dbe65  test    eax, eax
0x1800dbe67  jz      short loc_1800DBEC5
0x1800dbe69  cmp     [rsp+1F0h+pProxyConfig.fAutoDetect], 0
0x1800dbe6e  jz      short loc_1800DBE79
0x1800dbe70  mov     byte ptr [rbx+3E1h], 1
0x1800dbe77  jmp     short loc_1800DBEC5
0x1800dbe79  mov     rsi, [rsp+1F0h+pProxyConfig.lpszAutoConfigUrl]
0x1800dbe7e  test    rsi, rsi
0x1800dbe81  jz      short loc_1800DBEA6
0x1800dbe83  mov     byte ptr [rbx+3E1h], 1
0x1800dbe8a  mov     rcx, rsi; String
0x1800dbe8d  call    wcslen_0
0x1800dbe92  lea     rcx, [rbx+3E8h]
0x1800dbe99  mov     r8, rax
0x1800dbe9c  mov     rdx, rsi
0x1800dbe9f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbea4  jmp     short loc_1800DBEC5
0x1800dbea6  mov     rax, [rsp+1F0h+pProxyConfig.lpszProxy]
0x1800dbeab  test    rax, rax
0x1800dbeae  jz      short loc_1800DBEC5
0x1800dbeb0  mov     r12d, 3
0x1800dbeb6  mov     rdi, rax
0x1800dbeb9  mov     rax, [rsp+1F0h+pProxyConfig.lpszProxyBypass]
0x1800dbebe  test    rax, rax
0x1800dbec1  cmovnz  r14, rax
0x1800dbec5  mov     rcx, [rbp+0F0h+pProxyInfo.lpszProxy]; hMem
0x1800dbecc  test    rcx, rcx
0x1800dbecf  jz      short loc_1800DBED7
0x1800dbed1  call    cs:__imp_GlobalFree
0x1800dbed7  mov     rcx, [rbp+0F0h+pProxyInfo.lpszProxyBypass]; hMem
0x1800dbede  test    rcx, rcx
0x1800dbee1  jz      loc_1800DC203
0x1800dbee7  call    cs:__imp_GlobalFree
0x1800dbeed  jmp     loc_1800DC203
0x1800dbef2  mov     r12d, 3
0x1800dbef8  lea     rax, [rbp+0F0h+S1]
0x1800dbefc  cmp     rax, rsi
0x1800dbeff  jz      short loc_1800DBF1D
0x1800dbf01  cmp     qword ptr [rsi+18h], 7
0x1800dbf06  jbe     short loc_1800DBF0D
0x1800dbf08  mov     rdx, [rsi]
0x1800dbf0b  jmp     short loc_1800DBF10
0x1800dbf0d  mov     rdx, rsi
0x1800dbf10  mov     r8, [rsi+10h]
0x1800dbf14  lea     rcx, [rbp+0F0h+S1]
0x1800dbf18  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbf1d  lea     rdi, [rsi+20h]
0x1800dbf21  lea     rax, [rbp+0F0h+var_140]
0x1800dbf25  cmp     rax, rdi
0x1800dbf28  jz      short loc_1800DBF46
0x1800dbf2a  cmp     qword ptr [rdi+18h], 7
0x1800dbf2f  jbe     short loc_1800DBF36
0x1800dbf31  mov     rdx, [rdi]
0x1800dbf34  jmp     short loc_1800DBF39
0x1800dbf36  mov     rdx, rdi
0x1800dbf39  mov     r8, [rdi+10h]
0x1800dbf3d  lea     rcx, [rbp+0F0h+var_140]
0x1800dbf41  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbf46  lea     r8, [rdi+20h]
0x1800dbf4a  lea     rax, [rbp+0F0h+var_120]
0x1800dbf4e  cmp     rax, r8
0x1800dbf51  jz      short loc_1800DBF6F
0x1800dbf53  cmp     qword ptr [r8+18h], 7
0x1800dbf58  jbe     short loc_1800DBF5F
0x1800dbf5a  mov     rdx, [r8]
0x1800dbf5d  jmp     short loc_1800DBF62
0x1800dbf5f  mov     rdx, r8
0x1800dbf62  mov     r8, [r8+10h]
0x1800dbf66  lea     rcx, [rbp+0F0h+var_120]
0x1800dbf6a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbf6f  lea     r8, [rdi+40h]
0x1800dbf73  lea     rax, [rbp+0F0h+var_100]
0x1800dbf77  cmp     rax, r8
0x1800dbf7a  jz      short loc_1800DBF98
0x1800dbf7c  cmp     qword ptr [r8+18h], 7
0x1800dbf81  jbe     short loc_1800DBF88
0x1800dbf83  mov     rdx, [r8]
0x1800dbf86  jmp     short loc_1800DBF8B
0x1800dbf88  mov     rdx, r8
0x1800dbf8b  mov     r8, [r8+10h]
0x1800dbf8f  lea     rcx, [rbp+0F0h+var_100]
0x1800dbf93  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbf98  lea     r8, [rdi+60h]
0x1800dbf9c  lea     rax, [rbp+0F0h+var_E0]
0x1800dbfa0  cmp     rax, r8
0x1800dbfa3  jz      short loc_1800DBFC1
0x1800dbfa5  cmp     qword ptr [r8+18h], 7
0x1800dbfaa  jbe     short loc_1800DBFB1
0x1800dbfac  mov     rdx, [r8]
0x1800dbfaf  jmp     short loc_1800DBFB4
0x1800dbfb1  mov     rdx, r8
0x1800dbfb4  mov     r8, [r8+10h]
0x1800dbfb8  lea     rcx, [rbp+0F0h+var_E0]
0x1800dbfbc  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbfc1  lea     r8, [rdi+80h]
0x1800dbfc8  lea     rax, [rbp+0F0h+var_C0]
0x1800dbfcc  cmp     rax, r8
0x1800dbfcf  jz      short loc_1800DBFED
0x1800dbfd1  cmp     qword ptr [r8+18h], 7
0x1800dbfd6  jbe     short loc_1800DBFDD
0x1800dbfd8  mov     rdx, [r8]
0x1800dbfdb  jmp     short loc_1800DBFE0
0x1800dbfdd  mov     rdx, r8
0x1800dbfe0  mov     r8, [r8+10h]
0x1800dbfe4  lea     rcx, [rbp+0F0h+var_C0]
0x1800dbfe8  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dbfed  lea     r8, [rdi+0A0h]
0x1800dbff4  lea     rax, [rbp+0F0h+Block]
0x1800dbff8  cmp     rax, r8
0x1800dbffb  jz      short loc_1800DC019
0x1800dbffd  cmp     qword ptr [r8+18h], 7
0x1800dc002  jbe     short loc_1800DC009
0x1800dc004  mov     rdx, [r8]
0x1800dc007  jmp     short loc_1800DC00C
0x1800dc009  mov     rdx, r8
0x1800dc00c  mov     r8, [r8+10h]
0x1800dc010  lea     rcx, [rbp+0F0h+Block]
0x1800dc014  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dc019  mov     eax, [rdi+0C0h]
0x1800dc01f  mov     [rbp+0F0h+var_80], eax
0x1800dc022  mov     r8, [rbp+0F0h+N]; N
0x1800dc026  test    r8, r8
0x1800dc029  jz      short loc_1800DC068
0x1800dc02b  lea     rcx, [rbp+0F0h+S1]
0x1800dc02f  cmp     [rbp+0F0h+var_148], 7
0x1800dc034  cmova   rcx, [rbp+0F0h+S1]; S1
0x1800dc039  cmp     r8, r15
0x1800dc03c  jnz     short loc_1800DC051
0x1800dc03e  lea     rdx, asc_1801D2C90; "/"
0x1800dc045  call    wmemcmp
0x1800dc04a  test    eax, eax
0x1800dc04c  jz      short loc_1800DC068
0x1800dc04e  mov     eax, [rbp+0F0h+var_80]
0x1800dc051  test    eax, eax
0x1800dc053  jnz     short loc_1800DC068
0x1800dc055  lea     rdi, [rbp+0F0h+var_120]
0x1800dc059  cmp     [rbp+0F0h+var_108], 7
0x1800dc05e  cmova   rdi, [rbp+0F0h+var_120]
0x1800dc063  jmp     loc_1800DC203
0x1800dc068  lea     rdx, [rbp+0F0h+var_120]
0x1800dc06c  cmp     [rbp+0F0h+var_108], 7
0x1800dc071  cmova   rdx, [rbp+0F0h+var_120]
0x1800dc076  mov     r8, [rbp+0F0h+var_110]
0x1800dc07a  lea     rcx, [rsp+1F0h+Src]
0x1800dc07f  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800dc084  cmp     [rbp+0F0h+var_80], 0
0x1800dc088  jle     loc_1800DC1F3
0x1800dc08e  mov     r14, [rsp+1F0h+var_178]
0x1800dc093  mov     rsi, [rbp+0F0h+var_170]
0x1800dc097  cmp     r14, rsi
0x1800dc09a  jnb     short loc_1800DC0C3
0x1800dc09c  lea     rax, [r14+1]
0x1800dc0a0  mov     [rsp+1F0h+var_178], rax
0x1800dc0a5  lea     rax, [rsp+1F0h+Src]
0x1800dc0aa  cmp     rsi, 7
0x1800dc0ae  cmova   rax, [rsp+1F0h+Src]
0x1800dc0b4  lea     rcx, [rax+r14*2]
0x1800dc0b8  mov     dword ptr [rcx], 3Ah ; ':'
0x1800dc0be  jmp     loc_1800DC1A9
0x1800dc0c3  mov     rdi, 7FFFFFFFFFFFFFFEh
0x1800dc0cd  mov     rax, rdi
0x1800dc0d0  sub     rax, r14
0x1800dc0d3  cmp     rax, r15
0x1800dc0d6  jb      loc_1800DC691
0x1800dc0dc  lea     r13, [r14+1]
0x1800dc0e0  mov     rcx, r13
0x1800dc0e3  or      rcx, 7
0x1800dc0e7  cmp     rcx, rdi
0x1800dc0ea  ja      short loc_1800DC10B
0x1800dc0ec  mov     rdx, rsi
0x1800dc0ef  shr     rdx, 1
0x1800dc0f2  mov     rax, rdi
0x1800dc0f5  sub     rax, rdx
0x1800dc0f8  cmp     rsi, rax
0x1800dc0fb  ja      short loc_1800DC10B
0x1800dc0fd  lea     rax, [rsi+rdx]
0x1800dc101  mov     rdi, rcx
0x1800dc104  cmp     rcx, rax
0x1800dc107  cmovb   rdi, rax
0x1800dc10b  lea     rdx, [rdi+1]
0x1800dc10f  lea     rcx, [rsp+1F0h+Src]
0x1800dc114  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x1800dc119  mov     r15, rax
0x1800dc11c  mov     [rsp+1F0h+var_178], r13
0x1800dc121  mov     [rbp+0F0h+var_170], rdi
0x1800dc125  add     r14, r14
0x1800dc128  mov     r8, r14; Size
0x1800dc12b  mov     rcx, rax; void *
0x1800dc12e  cmp     rsi, 7
0x1800dc132  jbe     short loc_1800DC187
  ... truncated ...
```
