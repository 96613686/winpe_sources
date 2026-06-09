# web::http::client::details::winhttp_client::open(void)

- ea: `0x180053dc0`
- end: `0x1800547c7`
- name: `?open@winhttp_client@details@client@http@web@@IEAAKXZ`
- size: `2567`
- prototype: `unsigned int __fastcall(web::http::client::details::winhttp_client *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180055670`

## callees

- `0x18000c9a8`
- `0x18000df90`
- `0x18000e430`
- `0x18000ebdc`
- `0x180014300`
- `0x1800143d0`
- `0x180037dd0`
- `0x180043c90`
- `0x18004d610`
- `0x180053dc0`
- `0x180057cdc`
- `0x180063668`
- `0x180065130`
- `0x1800716a8`
- `0x180071714`
- `0x180074724`
- `0x1800747a0`
- `0x180074e4c`
- `0x18008121c`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800544ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800544ae`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180054001`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180054017`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180054764`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180054774`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180054784`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180054001`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180054017`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180054764`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180054774`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180054784`
- `WINHTTP!WinHttpSetTimeouts` at `0x18005438f`
- `WINHTTP!WinHttpSetTimeouts` at `0x18005438f`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180053f8f`
- `WINHTTP!WinHttpGetIEProxyConfigForCurrentUser` at `0x180053f8f`
- `WINHTTP!WinHttpConnect` at `0x18005449c`
- `WINHTTP!WinHttpConnect` at `0x18005449c`
- `WINHTTP!WinHttpSetOption` at `0x1800543c3`
- `WINHTTP!WinHttpSetOption` at `0x1800543f0`
- `WINHTTP!WinHttpSetOption` at `0x1800543c3`
- `WINHTTP!WinHttpSetOption` at `0x1800543f0`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18005444c`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18005444c`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180053f77`
- `WINHTTP!WinHttpGetDefaultProxyConfiguration` at `0x180053f77`
- `WINHTTP!WinHttpOpen` at `0x180054346`
- `WINHTTP!WinHttpOpen` at `0x180054346`

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
  const struct std::nothrow_t *v31; // rdx
  _BYTE *v32; // rcx
  WINHTTP_PROXY_INFO *p_pProxyInfo; // rdx
  void *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  int v37; // r8d
  const WCHAR *v38; // rdx
  HINTERNET v39; // rax
  const struct std::nothrow_t *v40; // rdx
  void *v41; // rcx
  const struct std::nothrow_t *v42; // rdx
  void *v43; // rcx
  const struct std::nothrow_t *v44; // rdx
  void *v45; // rcx
  const struct std::nothrow_t *v46; // rdx
  void *v47; // rcx
  const struct std::nothrow_t *v48; // rdx
  void *v49; // rcx
  const struct std::nothrow_t *v50; // rdx
  void *v51; // rcx
  const struct std::nothrow_t *v52; // rdx
  wchar_t *v53; // rcx
  const struct std::nothrow_t *v54; // rdx
  void *v55; // rcx
  const struct web::http::client::http_client_config *Buffer; // [rsp+30h] [rbp-D0h] BYREF
  const WCHAR *v57; // [rsp+38h] [rbp-C8h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+40h] [rbp-C0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-A0h]
  void *Src[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v61; // [rsp+78h] [rbp-88h]
  unsigned __int64 v62; // [rsp+80h] [rbp-80h]
  wchar_t *S1[2]; // [rsp+90h] [rbp-70h] BYREF
  size_t N; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v65; // [rsp+A8h] [rbp-58h]
  void *v66[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v68; // [rsp+C8h] [rbp-38h]
  void *v69[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v70; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v71; // [rsp+E8h] [rbp-18h]
  void *v72[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v73; // [rsp+100h] [rbp+0h]
  unsigned __int64 v74; // [rsp+108h] [rbp+8h]
  void *v75[3]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v76; // [rsp+128h] [rbp+28h]
  void *v77[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v78; // [rsp+140h] [rbp+40h]
  unsigned __int64 v79; // [rsp+148h] [rbp+48h]
  void *v80[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v81; // [rsp+160h] [rbp+60h]
  unsigned __int64 v82; // [rsp+168h] [rbp+68h]
  int v83; // [rsp+170h] [rbp+70h]
  WINHTTP_PROXY_INFO pProxyInfo; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v85; // [rsp+198h] [rbp+98h]

  if ( *((_BYTE *)this + 1008) )
    return 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 272);
  pplx::details::critical_section_impl::lock((LPCRITICAL_SECTION)((char *)this + 272));
  if ( !*((_BYTE *)this + 1008) )
  {
    memset(&pProxyConfig, 0, sizeof(pProxyConfig));
    lpszProxy = 0;
    lpszProxyBypass = 0;
    v57 = 0;
    *((_BYTE *)this + 1033) = 0;
    *(_OWORD *)Src = 0;
    v61 = 0;
    v62 = 7;
    LOWORD(Src[0]) = 0;
    std::wstring::wstring(S1, L"/");
    *(_OWORD *)v66 = 0;
    v67 = 0;
    v68 = 7;
    LOWORD(v66[0]) = 0;
    *(_OWORD *)v69 = 0;
    v70 = 0;
    v71 = 7;
    LOWORD(v69[0]) = 0;
    *(_OWORD *)v72 = 0;
    v73 = 0;
    v74 = 7;
    LOWORD(v72[0]) = 0;
    std::wstring::wstring(v75, L"/");
    *(_OWORD *)v77 = 0;
    v78 = 0;
    v79 = 7;
    LOWORD(v77[0]) = 0;
    *(_OWORD *)v80 = 0;
    v81 = 0;
    v82 = 7;
    LOWORD(v80[0]) = 0;
    v83 = -1;
    v6 = web::http::client::details::_http_client_communicator::client_config(this);
    Buffer = v6;
    v7 = (wchar_t **)((char *)v6 + 40);
    v8 = *((_DWORD *)v6 + 68);
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
          *((_BYTE *)this + 1033) = 1;
          memset(&pProxyInfo, 0, sizeof(pProxyInfo));
          if ( (!WinHttpGetDefaultProxyConfiguration(&pProxyInfo) || pProxyInfo.dwAccessType == 1)
            && WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig) )
          {
            if ( pProxyConfig.fAutoDetect )
            {
              *((_BYTE *)this + 1033) = 1;
            }
            else
            {
              lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
              if ( pProxyConfig.lpszAutoConfigUrl )
              {
                *((_BYTE *)this + 1033) = 1;
                v11 = wcslen_0(lpszAutoConfigUrl);
                std::wstring::_Assign<unsigned short>((char *)this + 1040, lpszAutoConfigUrl, v11);
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
      if ( *((_QWORD *)v6 + 8) <= 7u )
        v12 = (wchar_t *)((char *)v6 + 40);
      else
        v12 = *v7;
      std::wstring::_Assign<unsigned short>(S1, v12, *((_QWORD *)v6 + 7));
    }
    if ( v66 != (void **)((char *)v6 + 72) )
    {
      if ( *((_QWORD *)v6 + 12) <= 7u )
        v13 = (char *)v6 + 72;
      else
        v13 = (char *)*((_QWORD *)v6 + 9);
      std::wstring::_Assign<unsigned short>(v66, v13, *((_QWORD *)v6 + 11));
    }
    if ( v69 != (void **)((char *)v6 + 104) )
    {
      if ( *((_QWORD *)v6 + 16) <= 7u )
        v14 = (char *)v6 + 104;
      else
        v14 = (char *)*((_QWORD *)v6 + 13);
      std::wstring::_Assign<unsigned short>(v69, v14, *((_QWORD *)v6 + 15));
    }
    if ( v72 != (void **)((char *)v6 + 136) )
    {
      if ( *((_QWORD *)v6 + 20) <= 7u )
        v15 = (char *)v6 + 136;
      else
        v15 = (char *)*((_QWORD *)v6 + 17);
      std::wstring::_Assign<unsigned short>(v72, v15, *((_QWORD *)v6 + 19));
    }
    if ( v75 != (void **)((char *)v6 + 168) )
    {
      if ( *((_QWORD *)v6 + 24) <= 7u )
        v16 = (char *)v6 + 168;
      else
        v16 = (char *)*((_QWORD *)v6 + 21);
      std::wstring::_Assign<unsigned short>(v75, v16, *((_QWORD *)v6 + 23));
    }
    if ( v77 != (void **)((char *)v6 + 200) )
    {
      if ( *((_QWORD *)v6 + 28) <= 7u )
        v17 = (char *)v6 + 200;
      else
        v17 = (char *)*((_QWORD *)v6 + 25);
      std::wstring::_Assign<unsigned short>(v77, v17, *((_QWORD *)v6 + 27));
    }
    if ( v80 != (void **)((char *)v6 + 232) )
    {
      if ( *((_QWORD *)v6 + 32) <= 7u )
        v18 = (char *)v6 + 232;
      else
        v18 = (char *)*((_QWORD *)v6 + 29);
      std::wstring::_Assign<unsigned short>(v80, v18, *((_QWORD *)v6 + 31));
    }
    v19 = *((_DWORD *)v6 + 66);
    v83 = v19;
    if ( N )
    {
      v20 = (const wchar_t *)S1;
      if ( v65 > 7 )
        v20 = S1[0];
      if ( N != 1 )
      {
LABEL_66:
        if ( !v19 )
        {
          lpszProxy = (const WCHAR *)v69;
          if ( v71 > 7 )
            lpszProxy = (const WCHAR *)v69[0];
          goto LABEL_95;
        }
        goto LABEL_70;
      }
      if ( wmemcmp(v20, L"/", 1u) )
      {
        v19 = v83;
        goto LABEL_66;
      }
    }
LABEL_70:
    v21 = v69;
    if ( v71 > 7 )
      v21 = (void **)v69[0];
    std::wstring::_Assign<unsigned short>(Src, v21, v70);
    if ( v83 > 0 )
    {
      v22 = v61;
      v23 = v62;
      if ( v61 >= v62 )
      {
        v25 = 0x7FFFFFFFFFFFFFFELL;
        if ( 0x7FFFFFFFFFFFFFFELL == v61 )
          goto LABEL_174;
        v26 = (v61 + 1) | 7;
        if ( v26 <= 0x7FFFFFFFFFFFFFFELL )
        {
          v27 = v62 >> 1;
          if ( v62 <= 0x7FFFFFFFFFFFFFFELL - (v62 >> 1) )
          {
            v25 = (v61 + 1) | 7;
            if ( v26 < v62 + v27 )
              v25 = v62 + v27;
          }
        }
        v28 = (char *)std::allocator<unsigned short>::allocate(Src, v25 + 1);
        v61 = v22 + 1;
        v62 = v25;
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
          v31 = (const struct std::nothrow_t *)(2 * v23 + 2);
          if ( (unsigned __int64)v31 < 0x1000 )
          {
            operator delete(v30, v31);
          }
          else
          {
            v32 = (_BYTE *)*((_QWORD *)v30 - 1);
            if ( (unsigned __int64)((_BYTE *)v30 - v32 - 8) > 0x1F )
              __fastfail(5u);
            operator delete(v32, (const struct std::nothrow_t *)(2 * v23 + 41));
          }
        }
        Src[0] = v28;
        v6 = Buffer;
      }
      else
      {
        ++v61;
        v24 = Src;
        if ( v62 > 7 )
          v24 = (void **)Src[0];
        *(_DWORD *)((char *)v24 + 2 * v22) = 58;
      }
      std::_Integral_to_string<unsigned short,int>(&pProxyInfo, (unsigned int)v83);
      p_pProxyInfo = &pProxyInfo;
      if ( v85 > 7 )
        p_pProxyInfo = *(WINHTTP_PROXY_INFO **)&pProxyInfo.dwAccessType;
      std::wstring::_Append<unsigned short>(Src, p_pProxyInfo, pProxyInfo.lpszProxyBypass);
      std::destroy_at<std::pair<std::wstring const,_GUID>>(&pProxyInfo);
      lpszProxyBypass = v57;
    }
    lpszProxy = (const WCHAR *)Src;
    if ( v62 > 7 )
      lpszProxy = (const WCHAR *)Src[0];
LABEL_95:
    v34 = WinHttpOpen(0, v9, lpszProxy, lpszProxyBypass, 0x10000000u);
    *((_QWORD *)this + 127) = v34;
    if ( !v34 )
      goto LABEL_114;
    v35 = *((_QWORD *)v6 + 52) / 1000LL;
    if ( (int)v35 < 1 )
      LODWORD(v35) = 1;
    if ( !WinHttpSetTimeouts(v34, v35, v35, v35, v35) )
      goto LABEL_114;
    if ( *((_BYTE *)v6 + 408) )
    {
      LODWORD(Buffer) = 1;
      if ( !WinHttpSetOption(*((HINTERNET *)this + 127), 0x49u, &Buffer, 4u) )
        goto LABEL_114;
    }
    LODWORD(Buffer) = 2720;
    if ( !WinHttpSetOption(*((HINTERNET *)this + 127), 0x54u, &Buffer, 4u) )
      goto LABEL_114;
    if ( !*((_QWORD *)v6 + 70) )
    {
LABEL_105:
      if ( WinHttpSetStatusCallback(
             *((HINTERNET *)this + 127),
             web::http::client::details::winhttp_client::completion_callback,
             0x97F4C30u,
             0) != (WINHTTP_STATUS_CALLBACK)-1LL )
      {
        if ( web::uri::is_port_default((web::http::client::details::winhttp_client *)((char *)this + 40)) )
        {
          LOWORD(v37) = 80;
          if ( *((_BYTE *)this + 1032) )
            LOWORD(v37) = 443;
        }
        else
        {
          v37 = *((_DWORD *)this + 66);
        }
        v38 = (const WCHAR *)((char *)this + 104);
        if ( *((_QWORD *)this + 16) > 7u )
          v38 = *(const WCHAR **)v38;
        v39 = WinHttpConnect(*((HINTERNET *)this + 127), v38, v37, 0);
        *((_QWORD *)this + 128) = v39;
        if ( v39 )
        {
          *((_BYTE *)this + 1008) = 1;
          LastError = 0;
LABEL_116:
          if ( v82 > 7 )
          {
            v40 = (const struct std::nothrow_t *)(2 * v82 + 2);
            if ( (unsigned __int64)v40 < 0x1000 )
            {
              v41 = v80[0];
            }
            else
            {
              v41 = (void *)*((_QWORD *)v80[0] - 1);
              if ( (unsigned __int64)((char *)v80[0] - (char *)v41 - 8) > 0x1F )
                goto LABEL_156;
              v40 = (const struct std::nothrow_t *)(2 * v82 + 41);
            }
            operator delete(v41, v40);
          }
          v81 = 0;
          v82 = 7;
          LOWORD(v80[0]) = 0;
          if ( v79 > 7 )
          {
            v42 = (const struct std::nothrow_t *)(2 * v79 + 2);
            if ( (unsigned __int64)v42 < 0x1000 )
            {
              v43 = v77[0];
            }
            else
            {
              v43 = (void *)*((_QWORD *)v77[0] - 1);
              if ( (unsigned __int64)((char *)v77[0] - (char *)v43 - 8) > 0x1F )
                goto LABEL_156;
              v42 = (const struct std::nothrow_t *)(2 * v79 + 41);
            }
            operator delete(v43, v42);
          }
          v78 = 0;
          v79 = 7;
          LOWORD(v77[0]) = 0;
          if ( v76 > 7 )
          {
            v44 = (const struct std::nothrow_t *)(2 * v76 + 2);
            if ( (unsigned __int64)v44 < 0x1000 )
            {
              v45 = v75[0];
            }
            else
            {
              v45 = (void *)*((_QWORD *)v75[0] - 1);
              if ( (unsigned __int64)((char *)v75[0] - (char *)v45 - 8) > 0x1F )
                goto LABEL_156;
              v44 = (const struct std::nothrow_t *)(2 * v76 + 41);
            }
            operator delete(v45, v44);
          }
          v75[2] = 0;
          v76 = 7;
          LOWORD(v75[0]) = 0;
          if ( v74 > 7 )
          {
            v46 = (const struct std::nothrow_t *)(2 * v74 + 2);
            if ( (unsigned __int64)v46 < 0x1000 )
            {
              v47 = v72[0];
            }
            else
            {
              v47 = (void *)*((_QWORD *)v72[0] - 1);
              if ( (unsigned __int64)((char *)v72[0] - (char *)v47 - 8) > 0x1F )
                goto LABEL_156;
              v46 = (const struct std::nothrow_t *)(2 * v74 + 41);
            }
            operator delete(v47, v46);
          }
          v73 = 0;
          v74 = 7;
          LOWORD(v72[0]) = 0;
          if ( v71 > 7 )
          {
            v48 = (const struct std::nothrow_t *)(2 * v71 + 2);
            if ( (unsigned __int64)v48 < 0x1000 )
            {
              v49 = v69[0];
            }
            else
            {
              v49 = (void *)*((_QWORD *)v69[0] - 1);
              if ( (unsigned __int64)((char *)v69[0] - (char *)v49 - 8) > 0x1F )
                goto LABEL_156;
              v48 = (const struct std::nothrow_t *)(2 * v71 + 41);
            }
            operator delete(v49, v48);
          }
          v70 = 0;
          v71 = 7;
          LOWORD(v69[0]) = 0;
          if ( v68 > 7 )
          {
            v50 = (const struct std::nothrow_t *)(2 * v68 + 2);
            if ( (unsigned __int64)v50 < 0x1000 )
            {
              v51 = v66[0];
            }
            else
            {
              v51 = (void *)*((_QWORD *)v66[0] - 1);
              if ( (unsigned __int64)((char *)v66[0] - (char *)v51 - 8) > 0x1F )
                goto LABEL_156;
              v50 = (const struct std::nothrow_t *)(2 * v68 + 41);
            }
            operator delete(v51, v50);
          }
          v67 = 0;
          v68 = 7;
          LOWORD(v66[0]) = 0;
          if ( v65 <= 7 )
          {
LABEL_159:
            N = 0;
            v65 = 7;
            LOWORD(S1[0]) = 0;
            if ( v62 > 7 )
            {
              v54 = (const struct std::nothrow_t *)(2 * v62 + 2);
              if ( (unsigned __int64)v54 < 0x1000 )
              {
                v55 = Src[0];
              }
              else
              {
                v55 = (void *)*((_QWORD *)Src[0] - 1);
                if ( (unsigned __int64)((char *)Src[0] - (char *)v55 - 8) > 0x1F )
                  __fastfail(5u);
                v54 = (const struct std::nothrow_t *)(2 * v62 + 41);
              }
              operator delete(v55, v54);
            }
            v61 = 0;
            v62 = 7;
            LOWORD(Src[0]) = 0;
            if ( pProxyConfig.lpszAutoConfigUrl )
              GlobalFree(pProxyConfig.lpszAutoConfigUrl);
            if ( pProxyConfig.lpszProxy )
              GlobalFree(pProxyConfig.lpszProxy);
            if ( pProxyConfig.lpszProxyBypass )
              GlobalFree(pProxyConfig.lpszProxyBypass);
            goto LABEL_172;
          }
          v52 = (const struct std::nothrow_t *)(2 * v65 + 2);
          if ( (unsigned __int64)v52 < 0x1000 )
          {
            v53 = S1[0];
            goto LABEL_158;
          }
          v53 = (wchar_t *)*((_QWORD *)S1[0] - 1);
          if ( (unsigned __int64)((char *)S1[0] - (char *)v53 - 8) <= 0x1F )
          {
            v52 = (const struct std::nothrow_t *)(2 * v65 + 41);
LABEL_158:
            operator delete(v53, v52);
            goto LABEL_159;
          }
LABEL_156:
          __fastfail(5u);
        }
      }
LABEL_114:
      LastError = GetLastError();
      goto LABEL_116;
    }
    v57 = (const WCHAR *)*((_QWORD *)this + 127);
    v36 = *((_QWORD *)v6 + 70);
    if ( v36 )
    {
      (*(void (__fastcall **)(__int64, const WCHAR **))(*(_QWORD *)v36 + 16LL))(v36, &v57);
      goto LABEL_105;
    }
    std::_Xbad_function_call();
LABEL_174:
    std::_Xlen_string();
  }
  LastError = 0;
LABEL_172:
  pplx::details::critical_section_impl::unlock(lpCriticalSection);
  return LastError;
}

```

## disassembly

```asm
0x180053dc0  push    rbp
0x180053dc2  push    rbx
0x180053dc3  push    rsi
0x180053dc4  push    rdi
0x180053dc5  push    r12
0x180053dc7  push    r13
0x180053dc9  push    r14
0x180053dcb  push    r15
0x180053dcd  lea     rbp, [rsp-0B8h]
0x180053dd5  sub     rsp, 1B8h
0x180053ddc  mov     rax, cs:__security_cookie
0x180053de3  xor     rax, rsp
0x180053de6  mov     [rbp+0F0h+var_50], rax
0x180053ded  mov     rbx, rcx
0x180053df0  xor     esi, esi
0x180053df2  movzx   eax, byte ptr [rcx+3F0h]
0x180053df9  nop
0x180053dfa  test    al, al
0x180053dfc  jz      short loc_180053E05
0x180053dfe  xor     eax, eax
0x180053e00  jmp     loc_180054798
0x180053e05  lea     rax, [rcx+110h]
0x180053e0c  mov     [rsp+1F0h+lpCriticalSection], rax
0x180053e11  mov     rcx, rax; lpCriticalSection
0x180053e14  call    ?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x180053e19  nop
0x180053e1a  movzx   eax, byte ptr [rbx+3F0h]
0x180053e21  nop
0x180053e22  test    al, al
0x180053e24  jz      short loc_180053E2D
0x180053e26  mov     ebx, esi
0x180053e28  jmp     loc_18005478B
0x180053e2d  xorps   xmm0, xmm0
0x180053e30  movups  xmmword ptr [rsp+1F0h+pProxyConfig.fAutoDetect], xmm0
0x180053e35  movups  xmmword ptr [rsp+1F0h+pProxyConfig.lpszProxy], xmm0
0x180053e3a  mov     rdi, rsi
0x180053e3d  mov     r14, rsi
0x180053e40  mov     [rsp+1F0h+var_1B8], rsi
0x180053e45  mov     [rbx+409h], dil
0x180053e4c  movups  xmmword ptr [rsp+1F0h+Src], xmm0
0x180053e51  mov     [rsp+1F0h+var_178], rsi
0x180053e56  mov     [rbp+0F0h+var_170], 7
0x180053e5e  mov     word ptr [rsp+1F0h+Src], si
0x180053e63  lea     rdx, asc_1801118E8; "/"
0x180053e6a  lea     rcx, [rbp+0F0h+S1]
0x180053e6e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180053e73  nop
0x180053e74  lea     rax, [rbp+0F0h+var_140]
0x180053e78  mov     [rsp+1F0h+Buffer], rax
0x180053e7d  xorps   xmm0, xmm0
0x180053e80  movups  xmmword ptr [rbp+0F0h+var_140], xmm0
0x180053e84  mov     [rbp+0F0h+var_130], rsi
0x180053e88  mov     [rbp+0F0h+var_128], 7
0x180053e90  mov     word ptr [rbp+0F0h+var_140], si
0x180053e94  movups  xmmword ptr [rbp+0F0h+var_120], xmm0
0x180053e98  mov     [rbp+0F0h+var_110], rsi
0x180053e9c  mov     [rbp+0F0h+var_108], 7
0x180053ea4  mov     word ptr [rbp+0F0h+var_120], si
0x180053ea8  movups  xmmword ptr [rbp+0F0h+var_100], xmm0
0x180053eac  mov     [rbp+0F0h+var_F0], rsi
0x180053eb0  mov     [rbp+0F0h+var_E8], 7
0x180053eb8  mov     word ptr [rbp+0F0h+var_100], si
0x180053ebc  lea     rdx, asc_1801118E8; "/"
0x180053ec3  lea     rcx, [rbp+0F0h+var_E0]
0x180053ec7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180053ecc  xorps   xmm0, xmm0
0x180053ecf  movups  xmmword ptr [rbp+0F0h+var_C0], xmm0
0x180053ed3  mov     [rbp+0F0h+var_B0], rsi
0x180053ed7  mov     [rbp+0F0h+var_A8], 7
0x180053edf  mov     word ptr [rbp+0F0h+var_C0], si
0x180053ee3  movups  xmmword ptr [rbp+0F0h+var_A0], xmm0
0x180053ee7  mov     [rbp+0F0h+var_90], rsi
0x180053eeb  mov     [rbp+0F0h+var_88], 7
0x180053ef3  mov     word ptr [rbp+0F0h+var_A0], si
0x180053ef7  mov     [rbp+0F0h+var_80], 0FFFFFFFFh
0x180053efe  mov     rcx, rbx; this
0x180053f01  call    ?client_config@_http_client_communicator@details@client@http@web@@QEBAAEBVhttp_client_config@345@XZ; web::http::client::details::_http_client_communicator::client_config(void)
0x180053f06  mov     r13, rax
0x180053f09  mov     [rsp+1F0h+Buffer], rax
0x180053f0e  lea     rsi, [rax+28h]
0x180053f12  mov     eax, [rsi+0E8h]
0x180053f18  mov     r15d, 1
0x180053f1e  test    eax, eax
0x180053f20  jnz     short loc_180053F2F
0x180053f22  call    web__http__client__details__WinHttpDefaultProxyConstant
0x180053f27  mov     r12d, eax
0x180053f2a  jmp     loc_180054333
0x180053f2f  cmp     eax, 2
0x180053f32  jnz     short loc_180053F3C
0x180053f34  mov     r12d, r15d
0x180053f37  jmp     loc_180054333
0x180053f3c  cmp     eax, r15d
0x180053f3f  jnz     loc_180054022
0x180053f45  call    web__http__client__details__WinHttpDefaultProxyConstant
0x180053f4a  mov     r12d, eax
0x180053f4d  cmp     eax, 4
0x180053f50  jz      loc_180054333
0x180053f56  mov     [rbx+409h], r15b
0x180053f5d  xorps   xmm0, xmm0
0x180053f60  xor     eax, eax
0x180053f62  movups  xmmword ptr [rbp+0F0h+pProxyInfo.dwAccessType], xmm0
0x180053f69  mov     [rbp+0F0h+pProxyInfo.lpszProxyBypass], rax
0x180053f70  lea     rcx, [rbp+0F0h+pProxyInfo]; pProxyInfo
0x180053f77  call    cs:__imp_WinHttpGetDefaultProxyConfiguration
0x180053f7d  test    eax, eax
0x180053f7f  jz      short loc_180053F8A
0x180053f81  cmp     [rbp+0F0h+pProxyInfo.dwAccessType], 1
0x180053f88  jnz     short loc_180053FF5
0x180053f8a  lea     rcx, [rsp+1F0h+pProxyConfig]; pProxyConfig
0x180053f8f  call    cs:__imp_WinHttpGetIEProxyConfigForCurrentUser
0x180053f95  test    eax, eax
0x180053f97  jz      short loc_180053FF5
0x180053f99  cmp     [rsp+1F0h+pProxyConfig.fAutoDetect], 0
0x180053f9e  jz      short loc_180053FA9
0x180053fa0  mov     byte ptr [rbx+409h], 1
0x180053fa7  jmp     short loc_180053FF5
0x180053fa9  mov     rsi, [rsp+1F0h+pProxyConfig.lpszAutoConfigUrl]
0x180053fae  test    rsi, rsi
0x180053fb1  jz      short loc_180053FD6
0x180053fb3  mov     byte ptr [rbx+409h], 1
0x180053fba  mov     rcx, rsi; String
0x180053fbd  call    wcslen_0
0x180053fc2  lea     rcx, [rbx+410h]
0x180053fc9  mov     r8, rax
0x180053fcc  mov     rdx, rsi
0x180053fcf  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180053fd4  jmp     short loc_180053FF5
0x180053fd6  mov     rax, [rsp+1F0h+pProxyConfig.lpszProxy]
0x180053fdb  test    rax, rax
0x180053fde  jz      short loc_180053FF5
0x180053fe0  mov     r12d, 3
0x180053fe6  mov     rdi, rax
0x180053fe9  mov     rax, [rsp+1F0h+pProxyConfig.lpszProxyBypass]
0x180053fee  test    rax, rax
0x180053ff1  cmovnz  r14, rax
0x180053ff5  mov     rcx, [rbp+0F0h+pProxyInfo.lpszProxy]; hMem
0x180053ffc  test    rcx, rcx
0x180053fff  jz      short loc_180054007
0x180054001  call    cs:__imp_GlobalFree
0x180054007  mov     rcx, [rbp+0F0h+pProxyInfo.lpszProxyBypass]; hMem
0x18005400e  test    rcx, rcx
0x180054011  jz      loc_180054333
0x180054017  call    cs:__imp_GlobalFree
0x18005401d  jmp     loc_180054333
0x180054022  mov     r12d, 3
0x180054028  lea     rax, [rbp+0F0h+S1]
0x18005402c  cmp     rax, rsi
0x18005402f  jz      short loc_18005404D
0x180054031  cmp     qword ptr [rsi+18h], 7
0x180054036  jbe     short loc_18005403D
0x180054038  mov     rdx, [rsi]
0x18005403b  jmp     short loc_180054040
0x18005403d  mov     rdx, rsi
0x180054040  mov     r8, [rsi+10h]
0x180054044  lea     rcx, [rbp+0F0h+S1]
0x180054048  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005404d  lea     rdi, [rsi+20h]
0x180054051  lea     rax, [rbp+0F0h+var_140]
0x180054055  cmp     rax, rdi
0x180054058  jz      short loc_180054076
0x18005405a  cmp     qword ptr [rdi+18h], 7
0x18005405f  jbe     short loc_180054066
0x180054061  mov     rdx, [rdi]
0x180054064  jmp     short loc_180054069
0x180054066  mov     rdx, rdi
0x180054069  mov     r8, [rdi+10h]
0x18005406d  lea     rcx, [rbp+0F0h+var_140]
0x180054071  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180054076  lea     r8, [rdi+20h]
0x18005407a  lea     rax, [rbp+0F0h+var_120]
0x18005407e  cmp     rax, r8
0x180054081  jz      short loc_18005409F
0x180054083  cmp     qword ptr [r8+18h], 7
0x180054088  jbe     short loc_18005408F
0x18005408a  mov     rdx, [r8]
0x18005408d  jmp     short loc_180054092
0x18005408f  mov     rdx, r8
0x180054092  mov     r8, [r8+10h]
0x180054096  lea     rcx, [rbp+0F0h+var_120]
0x18005409a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005409f  lea     r8, [rdi+40h]
0x1800540a3  lea     rax, [rbp+0F0h+var_100]
0x1800540a7  cmp     rax, r8
0x1800540aa  jz      short loc_1800540C8
0x1800540ac  cmp     qword ptr [r8+18h], 7
0x1800540b1  jbe     short loc_1800540B8
0x1800540b3  mov     rdx, [r8]
0x1800540b6  jmp     short loc_1800540BB
0x1800540b8  mov     rdx, r8
0x1800540bb  mov     r8, [r8+10h]
0x1800540bf  lea     rcx, [rbp+0F0h+var_100]
0x1800540c3  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800540c8  lea     r8, [rdi+60h]
0x1800540cc  lea     rax, [rbp+0F0h+var_E0]
0x1800540d0  cmp     rax, r8
0x1800540d3  jz      short loc_1800540F1
0x1800540d5  cmp     qword ptr [r8+18h], 7
0x1800540da  jbe     short loc_1800540E1
0x1800540dc  mov     rdx, [r8]
0x1800540df  jmp     short loc_1800540E4
0x1800540e1  mov     rdx, r8
0x1800540e4  mov     r8, [r8+10h]
0x1800540e8  lea     rcx, [rbp+0F0h+var_E0]
0x1800540ec  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800540f1  lea     r8, [rdi+80h]
0x1800540f8  lea     rax, [rbp+0F0h+var_C0]
0x1800540fc  cmp     rax, r8
0x1800540ff  jz      short loc_18005411D
0x180054101  cmp     qword ptr [r8+18h], 7
0x180054106  jbe     short loc_18005410D
0x180054108  mov     rdx, [r8]
0x18005410b  jmp     short loc_180054110
0x18005410d  mov     rdx, r8
0x180054110  mov     r8, [r8+10h]
0x180054114  lea     rcx, [rbp+0F0h+var_C0]
0x180054118  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18005411d  lea     r8, [rdi+0A0h]
0x180054124  lea     rax, [rbp+0F0h+var_A0]
0x180054128  cmp     rax, r8
0x18005412b  jz      short loc_180054149
0x18005412d  cmp     qword ptr [r8+18h], 7
0x180054132  jbe     short loc_180054139
0x180054134  mov     rdx, [r8]
0x180054137  jmp     short loc_18005413C
0x180054139  mov     rdx, r8
0x18005413c  mov     r8, [r8+10h]
0x180054140  lea     rcx, [rbp+0F0h+var_A0]
0x180054144  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180054149  mov     eax, [rdi+0C0h]
0x18005414f  mov     [rbp+0F0h+var_80], eax
0x180054152  mov     r8, [rbp+0F0h+N]; N
0x180054156  test    r8, r8
0x180054159  jz      short loc_180054198
0x18005415b  lea     rcx, [rbp+0F0h+S1]
0x18005415f  cmp     [rbp+0F0h+var_148], 7
0x180054164  cmova   rcx, [rbp+0F0h+S1]; S1
0x180054169  cmp     r8, r15
0x18005416c  jnz     short loc_180054181
0x18005416e  lea     rdx, asc_1801118E8; "/"
0x180054175  call    wmemcmp
0x18005417a  test    eax, eax
0x18005417c  jz      short loc_180054198
0x18005417e  mov     eax, [rbp+0F0h+var_80]
0x180054181  test    eax, eax
0x180054183  jnz     short loc_180054198
0x180054185  lea     rdi, [rbp+0F0h+var_120]
0x180054189  cmp     [rbp+0F0h+var_108], 7
0x18005418e  cmova   rdi, [rbp+0F0h+var_120]
0x180054193  jmp     loc_180054333
0x180054198  lea     rdx, [rbp+0F0h+var_120]
0x18005419c  cmp     [rbp+0F0h+var_108], 7
0x1800541a1  cmova   rdx, [rbp+0F0h+var_120]
0x1800541a6  mov     r8, [rbp+0F0h+var_110]
0x1800541aa  lea     rcx, [rsp+1F0h+Src]
0x1800541af  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800541b4  cmp     [rbp+0F0h+var_80], 0
0x1800541b8  jle     loc_180054323
0x1800541be  mov     r14, [rsp+1F0h+var_178]
0x1800541c3  mov     rsi, [rbp+0F0h+var_170]
0x1800541c7  cmp     r14, rsi
0x1800541ca  jnb     short loc_1800541F3
0x1800541cc  lea     rax, [r14+1]
0x1800541d0  mov     [rsp+1F0h+var_178], rax
0x1800541d5  lea     rax, [rsp+1F0h+Src]
0x1800541da  cmp     rsi, 7
0x1800541de  cmova   rax, [rsp+1F0h+Src]
0x1800541e4  lea     rcx, [rax+r14*2]
0x1800541e8  mov     dword ptr [rcx], 3Ah ; ':'
0x1800541ee  jmp     loc_1800542D9
0x1800541f3  mov     rdi, 7FFFFFFFFFFFFFFEh
0x1800541fd  mov     rax, rdi
0x180054200  sub     rax, r14
0x180054203  cmp     rax, r15
0x180054206  jb      loc_1800547C1
0x18005420c  lea     r13, [r14+1]
0x180054210  mov     rcx, r13
0x180054213  or      rcx, 7
0x180054217  cmp     rcx, rdi
0x18005421a  ja      short loc_18005423B
0x18005421c  mov     rdx, rsi
0x18005421f  shr     rdx, 1
0x180054222  mov     rax, rdi
0x180054225  sub     rax, rdx
0x180054228  cmp     rsi, rax
0x18005422b  ja      short loc_18005423B
0x18005422d  lea     rax, [rsi+rdx]
0x180054231  mov     rdi, rcx
0x180054234  cmp     rcx, rax
0x180054237  cmovb   rdi, rax
0x18005423b  lea     rdx, [rdi+1]
0x18005423f  lea     rcx, [rsp+1F0h+Src]
0x180054244  call    ?allocate@?$allocator@G@std@@QEAAPEAG_K@Z; std::allocator<ushort>::allocate(unsigned __int64)
0x180054249  mov     r15, rax
0x18005424c  mov     [rsp+1F0h+var_178], r13
0x180054251  mov     [rbp+0F0h+var_170], rdi
0x180054255  add     r14, r14
0x180054258  mov     r8, r14; Size
0x18005425b  mov     rcx, rax; void *
0x18005425e  cmp     rsi, 7
0x180054262  jbe     short loc_1800542B7
  ... truncated ...
```
