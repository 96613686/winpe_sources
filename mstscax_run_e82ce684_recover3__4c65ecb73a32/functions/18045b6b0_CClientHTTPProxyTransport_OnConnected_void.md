# CClientHTTPProxyTransport::OnConnected(void)

- ea: `0x18045b6b0`
- end: `0x18045cc90`
- name: `?OnConnected@CClientHTTPProxyTransport@@UEAAJXZ`
- size: `5600`
- prototype: `__int64 __fastcall(CClientHTTPProxyTransport *__hidden this)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180017fb8`
- `0x1800186a0`
- `0x18001cdc0`
- `0x18001e170`
- `0x18001f5d0`
- `0x1800204e8`
- `0x18002311c`
- `0x18002a334`
- `0x18002a374`
- `0x180039c98`
- `0x180085e04`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x18012962c`
- `0x18012966c`
- `0x18012dd50`
- `0x18045b6b0`
- `0x18045ced0`
- `0x180461a90`
- `0x180462e2c`
- `0x180473b9c`
- `0x18068c010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18045ba2f`
- `KERNEL32!LocalAlloc` at `0x18045be84`
- `KERNEL32!LocalAlloc` at `0x18045c295`
- `KERNEL32!LocalAlloc` at `0x18045c69d`
- `KERNEL32!LocalAlloc` at `0x18045ba2f`
- `KERNEL32!LocalAlloc` at `0x18045be84`
- `KERNEL32!LocalAlloc` at `0x18045c295`
- `KERNEL32!LocalAlloc` at `0x18045c69d`
- `KERNEL32!LocalFree` at `0x18045cc00`
- `KERNEL32!LocalFree` at `0x18045cc0e`
- `KERNEL32!LocalFree` at `0x18045cc3d`
- `KERNEL32!LocalFree` at `0x18045cc62`
- `KERNEL32!LocalFree` at `0x18045cc00`
- `KERNEL32!LocalFree` at `0x18045cc0e`
- `KERNEL32!LocalFree` at `0x18045cc3d`
- `KERNEL32!LocalFree` at `0x18045cc62`

## string_xrefs

- `0x18045bd9e`: `GatewayBrokeringType`
- `0x18045bba9`: `Side channel authentication cookie size`
- `0x18045bb3e`: `Side channel authentication cookie`
- `0x18045bcc3`: `Side channel port`
- `0x18045bc8a`: `GetSideTransportProperty for UDP port failed !`
- `0x18045bcb0`: `GetSideTransportProperty for UDP port failed !`
- `0x18045bb70`: `SetUlongPtrProperty for m_upSideChannelAuthCookie failed !`
- `0x18045bb96`: `SetUlongPtrProperty for m_upSideChannelAuthCookie failed !`
- `0x18045bbe0`: `SetProperty for m_dwSideChannelAuthCookieSize failed !`
- `0x18045bc06`: `SetProperty for m_dwSideChannelAuthCookieSize failed !`
- `0x18045ba61`: `TSAlloc failed for sideChannelAuthCookie`
- `0x18045bac1`: `TSAlloc failed for sideChannelAuthCookie`
- `0x18045bb05`: `GetSideTransportProperty for UDP cookie failed !`
- `0x18045bb2b`: `GetSideTransportProperty for UDP cookie failed !`
- `0x18045b9a5`: `GetSideTransportProperty for size of UDP cookie failed !`
- `0x18045ba09`: `GetSideTransportProperty for size of UDP cookie failed !`
- `0x18045c1a3`: `TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERCERT to TS_PROP_REDIRECTION_TARGET_CERTIFICATE failed !`
- `0x18045c1c9`: `TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERCERT to TS_PROP_REDIRECTION_TARGET_CERTIFICATE failed !`
- `0x18045be4a`: `GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !`
- `0x18045be70`: `GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !`
- `0x18045bf2b`: `GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !`
- `0x18045bf84`: `GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !`
- `0x18045bdcd`: `GetProperty TS_PROP_TRANSPORT_PROXYBROKERINGTYPE Failed !`
- `0x18045bdf3`: `GetProperty TS_PROP_TRANSPORT_PROXYBROKERINGTYPE Failed !`
- `0x18045c5c2`: `TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHBLOB to TS_PROP_REDIRECTION_PK_ENCRYPTED_PASSWORD failed !`
- `0x18045c5e0`: `TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHBLOB to TS_PROP_REDIRECTION_PK_ENCRYPTED_PASSWORD failed !`
- `0x18045c36b`: `GetSideTransportProperty for AA_TRANSPORT_PROPERTY_USERNAME failed !`
- `0x18045c391`: `GetSideTransportProperty for AA_TRANSPORT_PROPERTY_USERNAME failed !`
- `0x18045c205`: `TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHGUID to TS_PROP_REDIRECTION_GUID failed !`
- `0x18045c22b`: `TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHGUID to TS_PROP_REDIRECTION_GUID failed !`
- `0x18045ca3d`: `GetSideTransportProperty for AA_TRANSPORT_PROPERTY_LOGONCERTENABLED failed !`
- `0x18045ca63`: `GetSideTransportProperty for AA_TRANSPORT_PROPERTY_LOGONCERTENABLED failed !`
- `0x18045c89c`: `ITscAuthenticationBlob_CreateInstance failed!`

## pseudocode

```c
__int64 __fastcall CClientHTTPProxyTransport::OnConnected(CClientHTTPProxyTransport *this)
{
  unsigned int v1; // r12d
  _BYTE *v3; // r14
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int ActivityIdPrefix; // eax
  signed int v11; // ebx
  __int64 v12; // r12
  unsigned __int16 *v13; // rsi
  void *v14; // r13
  int v15; // eax
  __int64 v16; // rcx
  bool v17; // zf
  __int64 (__fastcall *v18)(__int64, const char *, __int64); // rax
  unsigned __int16 *v19; // rsi
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  unsigned __int16 *v24; // rsi
  const wchar_t *v25; // r9
  unsigned __int16 *v26; // rcx
  const unsigned __int16 *v27; // rdx
  unsigned int v28; // r8d
  HLOCAL v29; // rax
  HLOCAL v30; // r12
  unsigned __int16 *v31; // r14
  const wchar_t *v32; // r9
  unsigned int v33; // eax
  HLOCAL v34; // rax
  void *v35; // r12
  unsigned __int16 *v36; // rsi
  const wchar_t *v37; // r9
  unsigned __int16 *v38; // rcx
  const unsigned __int16 *v39; // rdx
  unsigned int v40; // r8d
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  HLOCAL v44; // rax
  unsigned __int16 *v45; // r14
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // r8
  __int64 v52; // r9
  _BYTE *v53; // rax
  __int64 v54; // r8
  __int64 v55; // r9
  HLOCAL v56; // rsi
  int v57; // eax
  __int64 v58; // rdx
  unsigned __int16 *v59; // rax
  unsigned __int16 *v60; // rsi
  __int64 v61; // rdx
  unsigned int v62; // ebx
  __int64 v63; // r8
  __int64 v64; // r9
  unsigned int v65; // eax
  __int64 v66; // rdx
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r9
  int v74; // eax
  __int64 v75; // rax
  __int64 v76; // rax
  struct ITscAuthenticationBlob *v77; // rsi
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // r9
  int v82; // eax
  unsigned int v83; // eax
  unsigned __int16 *v84; // rax
  __int64 v85; // rax
  unsigned __int16 *v86; // rax
  unsigned __int16 *v87; // rax
  unsigned __int16 *v88; // rax
  unsigned __int16 *v89; // rax
  unsigned __int16 *v90; // rsi
  _BYTE *v91; // rcx
  __int64 v92; // rax
  __int64 v93; // rcx
  _BYTE *v94; // rax
  int v96; // [rsp+28h] [rbp-51h]
  int v97; // [rsp+28h] [rbp-51h]
  int v98; // [rsp+28h] [rbp-51h]
  int v99; // [rsp+28h] [rbp-51h]
  signed int v100; // [rsp+30h] [rbp-49h]
  signed int v101; // [rsp+30h] [rbp-49h]
  signed int v102; // [rsp+30h] [rbp-49h]
  _BYTE *v103; // [rsp+40h] [rbp-39h]
  unsigned int v104; // [rsp+48h] [rbp-31h] BYREF
  __int64 v105; // [rsp+50h] [rbp-29h] BYREF
  __int64 v106; // [rsp+58h] [rbp-21h] BYREF
  struct ITscAuthenticationBlob *v107; // [rsp+60h] [rbp-19h] BYREF
  int v108; // [rsp+68h] [rbp-11h] BYREF
  int v109; // [rsp+6Ch] [rbp-Dh] BYREF
  int v110; // [rsp+70h] [rbp-9h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-1h] BYREF
  __int64 v112; // [rsp+80h] [rbp+7h] BYREF
  int v113[18]; // [rsp+88h] [rbp+Fh] BYREF
  int v114; // [rsp+E0h] [rbp+67h]
  SIZE_T uBytes; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v116; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int v117; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = 0;
  v106 = 0;
  LODWORD(uBytes) = 0;
  v108 = 0;
  v3 = 0;
  v107 = (CClientHTTPProxyTransport *)((char *)this + 1256);
  v110 = 0;
  v113[0] = 4;
  v109 = 0;
  v103 = 0;
  v116 = 0;
  v114 = 0;
  hMem = 0;
  v117 = 0;
  v112 = 0;
  CTSCriticalSection::Lock((CClientHTTPProxyTransport *)((char *)this + 1256));
  if ( *((_QWORD *)this + 156) )
  {
    TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v112);
    v112 = *((_QWORD *)this + 156);
    v4 = v112;
    TCntPtr<WindowsRemoteAppLib::CRailNotify>::SafeAddRef(&v112);
    v5 = v4;
  }
  else
  {
    v4 = 0;
    v5 = 0;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v107);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v7, v6, v8, v9);
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids,
        ActivityIdPrefix);
    }
    v11 = -2147467259;
    v3 = 0;
    goto LABEL_224;
  }
  v12 = (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 112) + 64LL))(*(_QWORD *)(v5 + 112));
  v11 = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 241) + 32LL))(
          *((_QWORD *)this + 241),
          "Gateway server UDP support",
          v12);
  if ( v11 < 0 )
  {
    v13 = (unsigned __int16 *)operator new(0x208u);
    if ( v13 )
    {
      *v13 = 0;
      StringCchPrintfW(
        v13,
        0x104u,
        L"'%s' in %s at %d err=[0x%x]",
        L"SetBoolProperty failed for IsUdpSupported!",
        L"CClientHTTPProxyTransport::OnConnected",
        259,
        v11);
      CClientProxyTransport::TLDiagEvent(this, v13, v11);
      operator delete(v13);
    }
    else
    {
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      CClientProxyTransport::TLDiagEvent(this, L"SetBoolProperty failed for IsUdpSupported!", v11);
    }
    v1 = 0;
    goto LABEL_224;
  }
  v14 = 0;
  v15 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 112) + 56LL))(*(_QWORD *)(v5 + 112));
  v16 = *((_QWORD *)this + 241);
  v17 = v15 == 1;
  v18 = *(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v16 + 24LL);
  if ( !v17 )
  {
    v11 = v18(v16, "Control channel connection type", 3);
    if ( v11 < 0 )
    {
      v88 = (unsigned __int16 *)operator new(0x208u);
      v19 = v88;
      if ( v88 )
      {
        v100 = v11;
        *v88 = 0;
        v96 = 624;
        goto LABEL_19;
      }
LABEL_21:
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      CClientProxyTransport::TLDiagEvent(this, L"SetProperty failed for Main transport type", v11);
      goto LABEL_20;
    }
LABEL_214:
    v35 = 0;
    goto LABEL_215;
  }
  v11 = v18(v16, "Control channel connection type", 4);
  if ( v11 < 0 )
  {
    v19 = (unsigned __int16 *)operator new(0x208u);
    if ( v19 )
    {
      v100 = v11;
      *v19 = 0;
      v96 = 268;
LABEL_19:
      StringCchPrintfW(
        v19,
        0x104u,
        L"'%s' in %s at %d err=[0x%x]",
        L"SetProperty failed for Main transport type",
        L"CClientHTTPProxyTransport::OnConnected",
        v96,
        v100);
      CClientProxyTransport::TLDiagEvent(this, v19, v11);
      operator delete(v19);
LABEL_20:
      v1 = 0;
      goto LABEL_224;
    }
    goto LABEL_21;
  }
  if ( (_DWORD)v12 )
  {
    v104 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
            *(_QWORD *)(v5 + 112),
            4,
            0,
            &uBytes);
    if ( v11 < 0 )
    {
      v24 = (unsigned __int16 *)operator new(0x208u);
      if ( v24 )
      {
        v101 = v11;
        v25 = L"GetSideTransportProperty for size of UDP cookie failed !";
        v97 = 281;
LABEL_26:
        *v24 = 0;
        StringCchPrintfW(
          v24,
          0x104u,
          L"'%s' in %s at %d err=[0x%x]",
          v25,
          L"CClientHTTPProxyTransport::OnConnected",
          v97,
          v101);
        CClientProxyTransport::TLDiagEvent(this, v24, v11);
        v26 = v24;
LABEL_27:
        operator delete(v26);
LABEL_28:
        v3 = 0;
        goto LABEL_20;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v27 = L"GetSideTransportProperty for size of UDP cookie failed !";
      goto LABEL_30;
    }
    if ( (_DWORD)uBytes )
    {
      v29 = LocalAlloc(0x40u, (unsigned int)uBytes);
      v30 = v29;
      if ( !v29 )
      {
        v11 = -2147024882;
        v31 = (unsigned __int16 *)operator new(0x208u);
        if ( !v31 )
        {
          CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", 0x8007000E);
          v28 = -2147024882;
          v27 = L"TSAlloc failed for sideChannelAuthCookie";
          goto LABEL_31;
        }
        v32 = L"TSAlloc failed for sideChannelAuthCookie";
        v98 = 291;
LABEL_36:
        *v31 = 0;
        StringCchPrintfW(
          v31,
          0x104u,
          L"'%s' in %s at %d err=[0x%x]",
          v32,
          L"CClientHTTPProxyTransport::OnConnected",
          v98,
          -2147024882);
        CClientProxyTransport::TLDiagEvent(this, v31, 0x8007000E);
        v26 = v31;
        goto LABEL_27;
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, HLOCAL, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
              *(_QWORD *)(v5 + 112),
              4,
              v29,
              &uBytes);
      if ( v11 < 0 )
      {
        v24 = (unsigned __int16 *)operator new(0x208u);
        if ( v24 )
        {
          v101 = v11;
          v25 = L"GetSideTransportProperty for UDP cookie failed !";
          v97 = 300;
          goto LABEL_26;
        }
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
        v27 = L"GetSideTransportProperty for UDP cookie failed !";
        goto LABEL_30;
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD, const char *, HLOCAL))(**((_QWORD **)this + 241) + 80LL))(
              *((_QWORD *)this + 241),
              "Side channel authentication cookie",
              v30);
      if ( v11 < 0 )
      {
        v24 = (unsigned __int16 *)operator new(0x208u);
        if ( v24 )
        {
          v101 = v11;
          v25 = L"SetUlongPtrProperty for m_upSideChannelAuthCookie failed !";
          v97 = 306;
          goto LABEL_26;
        }
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
        v27 = L"SetUlongPtrProperty for m_upSideChannelAuthCookie failed !";
        goto LABEL_30;
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 241) + 24LL))(
              *((_QWORD *)this + 241),
              "Side channel authentication cookie size",
              (unsigned int)uBytes);
      if ( v11 < 0 )
      {
        v24 = (unsigned __int16 *)operator new(0x208u);
        if ( v24 )
        {
          v101 = v11;
          v25 = L"SetProperty for m_dwSideChannelAuthCookieSize failed !";
          v97 = 312;
          goto LABEL_26;
        }
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
        v27 = L"SetProperty for m_dwSideChannelAuthCookieSize failed !";
        goto LABEL_30;
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v33 = RdpX_GetActivityIdPrefix(v21, v20, v22, v23);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids, v33);
    }
    LODWORD(uBytes) = 4;
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
            *(_QWORD *)(v5 + 112),
            1,
            &v104,
            &uBytes);
    if ( v11 < 0 )
    {
      v24 = (unsigned __int16 *)operator new(0x208u);
      if ( v24 )
      {
        v101 = v11;
        v25 = L"GetSideTransportProperty for UDP port failed !";
        v97 = 326;
        goto LABEL_26;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v27 = L"GetSideTransportProperty for UDP port failed !";
      goto LABEL_30;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 241) + 24LL))(
            *((_QWORD *)this + 241),
            "Side channel port",
            v104);
    if ( v11 < 0 )
    {
      v24 = (unsigned __int16 *)operator new(0x208u);
      if ( v24 )
      {
        v101 = v11;
        v25 = L"SetProperty for Udp port failed !";
        v97 = 332;
        goto LABEL_26;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v27 = L"SetProperty for Udp port failed !";
      goto LABEL_30;
    }
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, int *))(**(_QWORD **)(v5 + 112) + 88LL))(
          *(_QWORD *)(v5 + 112),
          12,
          &v108,
          v113);
  if ( v11 < 0 )
  {
    v24 = (unsigned __int16 *)operator new(0x208u);
    if ( v24 )
    {
      v101 = v11;
      v25 = L"GetProperty AA_TRANSPORT_PROPERTY_RESOURCECHANNEL Failed !";
      v97 = 341;
      goto LABEL_26;
    }
    CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
    v27 = L"GetProperty AA_TRANSPORT_PROPERTY_RESOURCECHANNEL Failed !";
    goto LABEL_30;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, const char *, int *))(**((_QWORD **)this + 241) + 96LL))(
          *((_QWORD *)this + 241),
          "GatewayBrokeringType",
          &v109);
  if ( v11 < 0 )
  {
    v24 = (unsigned __int16 *)operator new(0x208u);
    if ( v24 )
    {
      v101 = v11;
      v25 = L"GetProperty TS_PROP_TRANSPORT_PROXYBROKERINGTYPE Failed !";
      v97 = 346;
      goto LABEL_26;
    }
    CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
    v27 = L"GetProperty TS_PROP_TRANSPORT_PROXYBROKERINGTYPE Failed !";
    goto LABEL_30;
  }
  if ( !v108 || v109 != 1 )
    goto LABEL_214;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
          *(_QWORD *)(v5 + 112),
          11,
          0,
          &uBytes);
  if ( v11 < 0 )
  {
    v24 = (unsigned __int16 *)operator new(0x208u);
    if ( v24 )
    {
      v101 = v11;
      v25 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !";
      v97 = 370;
      goto LABEL_26;
    }
    CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
    v27 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !";
LABEL_30:
    v28 = v11;
LABEL_31:
    CClientProxyTransport::TLDiagEvent(this, v27, v28);
    goto LABEL_28;
  }
  v34 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v35 = v34;
  if ( !v34 )
  {
    v11 = -2147024882;
    v31 = (unsigned __int16 *)operator new(0x208u);
    if ( !v31 )
    {
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", 0x8007000E);
      v28 = -2147024882;
      v27 = L"TSAlloc failed for serverName";
      goto LABEL_31;
    }
    v32 = L"TSAlloc failed for serverName";
    v98 = 376;
    goto LABEL_36;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, HLOCAL, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
          *(_QWORD *)(v5 + 112),
          11,
          v34,
          &uBytes);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 234) + 160LL))(
            *((_QWORD *)this + 234),
            &v106);
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v37 = L"Failed to get CoreAPI from ITSInstance";
        v99 = 395;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v39 = L"Failed to get CoreAPI from ITSInstance";
      goto LABEL_88;
    }
    v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 40LL))(v106);
    v11 = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v41 + 32LL))(
            v41,
            "RedirectionClientRedirected",
            1);
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        *v36 = 0;
        v99 = 401;
LABEL_97:
        v37 = L"SetBoolProperty (TS_PROP_REDIRECTION_CLIENT_REDIRECTED) failed!";
        goto LABEL_85;
      }
      goto LABEL_98;
    }
    v42 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 40LL))(v106);
    v11 = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v42 + 32LL))(
            v42,
            "UseRedirectionServerName",
            1);
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v37 = L"SetBoolProperty (TS_PROP_USE_REDIRECTION_SERVERNAME) failed!";
        v99 = 407;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v39 = L"SetBoolProperty (TS_PROP_USE_REDIRECTION_SERVERNAME) failed!";
      goto LABEL_88;
    }
    v43 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 40LL))(v106);
    v11 = (*(__int64 (__fastcall **)(__int64, const char *, void *, _QWORD))(*(_QWORD *)v43 + 56LL))(
            v43,
            "ServerName",
            v35,
            0);
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v37 = L"SetStringProperty (TS_PROP_CORE_SERVERNAME) failed!";
        v99 = 413;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v39 = L"SetStringProperty (TS_PROP_CORE_SERVERNAME) failed!";
      goto LABEL_88;
    }
    v11 = CClientHTTPProxyTransport::TransformSidePropToCoreSPropSZ(this, 0xDu, "TargetCertificate");
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v37 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERCERT to TS_PROP_REDIRECTION_TARGET_CERTIFICATE failed !";
        v99 = 436;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v39 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERCERT to TS_PROP_REDIRECTION_TARGET_CERTIFICATE failed !";
      goto LABEL_88;
    }
    v11 = CClientHTTPProxyTransport::TransformSidePropToCoreSPropSZ(this, 0xFu, "RedirectionGuid");
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v37 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHGUID to TS_PROP_REDIRECTION_GUID failed !";
        v99 = 439;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v39 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHGUID to TS_PROP_REDIRECTION_GUID failed !";
      goto LABEL_88;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
            *(_QWORD *)(v5 + 112),
            17,
            0,
            &uBytes);
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v99 = 457;
        goto LABEL_83;
      }
      goto LABEL_87;
    }
    if ( !(_DWORD)uBytes )
    {
      LODWORD(uBytes) = 4;
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
              *(_QWORD *)(v5 + 112),
              18,
              &v110,
              &uBytes);
      if ( v11 < 0 )
      {
        v84 = (unsigned __int16 *)operator new(0x208u);
        v36 = v84;
        if ( v84 )
        {
          v102 = v11;
          *v84 = 0;
          v37 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_LOGONCERTENABLED failed !";
          v99 = 601;
          goto LABEL_85;
        }
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
        v39 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_LOGONCERTENABLED failed !";
        goto LABEL_88;
      }
      if ( v110 )
      {
        v85 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 40LL))(v106);
        v11 = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v85 + 32LL))(
                v85,
                "UseLogonCertificate",
                1);
        if ( v11 < 0 )
        {
          v86 = (unsigned __int16 *)operator new(0x208u);
          v36 = v86;
          if ( v86 )
          {
            v102 = v11;
            *v86 = 0;
            v99 = 609;
            goto LABEL_97;
          }
LABEL_98:
          CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
          v39 = L"SetBoolProperty (TS_PROP_REDIRECTION_CLIENT_REDIRECTED) failed!";
          goto LABEL_88;
        }
        v11 = CClientHTTPProxyTransport::TransformSidePropToCoreSPropSZ(this, 0xEu, "PKEncryptedPassword");
        if ( v11 < 0 )
        {
          v87 = (unsigned __int16 *)operator new(0x208u);
          v36 = v87;
          if ( v87 )
          {
            v102 = v11;
            *v87 = 0;
            v99 = 612;
            goto LABEL_147;
          }
LABEL_148:
          CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
          v39 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHBLOB to TS_PROP_REDIRECTION_PK_ENCRY"
                 "PTED_PASSWORD failed !";
          goto LABEL_88;
        }
      }
LABEL_215:
      v11 = CClientProxyTransport::OnConnected(this);
      if ( v11 < 0 )
      {
        v89 = (unsigned __int16 *)operator new(0x208u);
        v90 = v89;
        if ( v89 )
        {
          *v89 = 0;
          StringCchPrintfW(
            v89,
            0x104u,
            L"'%s' in %s at %d err=[0x%x]",
            L"OnConnected failed!",
            L"CClientHTTPProxyTransport::OnConnected",
            628,
            v11);
          CClientProxyTransport::TLDiagEvent(this, v90, v11);
          operator delete(v90);
        }
        else
        {
          CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
          CClientProxyTransport::TLDiagEvent(this, L"OnConnected failed!", v11);
        }
      }
      if ( !v35 )
        goto LABEL_221;
      goto LABEL_220;
    }
    v104 = 0;
    v44 = LocalAlloc(0x40u, (unsigned int)uBytes);
    v14 = v44;
    if ( !v44 )
    {
      v11 = -2147024882;
      v45 = (unsigned __int16 *)operator new(0x208u);
      if ( v45 )
      {
        *v45 = 0;
        StringCchPrintfW(
          v45,
          0x104u,
          L"'%s' in %s at %d err=[0x%x]",
          L"TSAlloc failed for userName",
          L"CClientHTTPProxyTransport::OnConnected",
          467,
          -2147024882);
        CClientProxyTransport::TLDiagEvent(this, v45, 0x8007000E);
        v38 = v45;
        goto LABEL_86;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", 0x8007000E);
      v40 = -2147024882;
      v39 = L"TSAlloc failed for userName";
LABEL_89:
      CClientProxyTransport::TLDiagEvent(this, v39, v40);
      goto LABEL_220;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, HLOCAL, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
            *(_QWORD *)(v5 + 112),
            17,
            v44,
            &uBytes);
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v37 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_USERNAME failed !";
        v99 = 476;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v39 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_USERNAME failed !";
      goto LABEL_88;
    }
    v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 40LL))(v106);
    v11 = (*(__int64 (__fastcall **)(__int64, const char *, void *, _QWORD))(*(_QWORD *)v46 + 56LL))(
            v46,
            "RedirectionUserName",
            v14,
            0);
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v37 = L"SetStringProperty (TS_PROP_REDIRECTION_USERNAME) failed!";
        v99 = 482;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v39 = L"SetStringProperty (TS_PROP_REDIRECTION_USERNAME) failed!";
      goto LABEL_88;
    }
    v47 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 40LL))(v106);
    v11 = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v47 + 32LL))(
            v47,
            "UseRedirectionUserName",
            1);
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v37 = L"SetBoolProperty (TS_PROP_USE_REDIRECTION_USERNAME) failed!";
        v99 = 488;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v39 = L"SetBoolProperty (TS_PROP_USE_REDIRECTION_USERNAME) failed!";
      goto LABEL_88;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, const char *, unsigned int *))(**((_QWORD **)this + 241) + 96LL))(
            *((_QWORD *)this + 241),
            "GatewayCredsSource",
            &v104);
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v37 = L"GetProperty TS_PROP_TRANSPORT_PROXYCREDSSOURCE Failed !";
        v99 = 497;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v39 = L"GetProperty TS_PROP_TRANSPORT_PROXYCREDSSOURCE Failed !";
      goto LABEL_88;
    }
    if ( v104 == 6 )
    {
      v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 40LL))(v106);
      v11 = (*(__int64 (__fastcall **)(__int64, const char *, void *, _QWORD))(*(_QWORD *)v48 + 56LL))(
              v48,
              "Domain",
              v35,
              0);
      if ( v11 < 0 )
      {
        v36 = (unsigned __int16 *)operator new(0x208u);
        if ( v36 )
        {
          v102 = v11;
          v37 = L"SetStringProperty (TS_PROP_CORE_DOMAIN) failed!";
          v99 = 507;
          goto LABEL_84;
        }
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
        v39 = L"SetStringProperty (TS_PROP_CORE_DOMAIN) failed!";
        goto LABEL_88;
      }
      v11 = CClientHTTPProxyTransport::TransformSidePropToCoreSPropSZ(this, 0xEu, "PKEncryptedPassword");
      if ( v11 < 0 )
      {
        v36 = (unsigned __int16 *)operator new(0x208u);
        if ( v36 )
        {
          v102 = v11;
          *v36 = 0;
          v99 = 510;
LABEL_147:
          v37 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHBLOB to TS_PROP_REDIRECTION_PK_ENCRY"
                 "PTED_PASSWORD failed !";
          goto LABEL_85;
        }
        goto LABEL_148;
      }
      goto LABEL_215;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD, unsigned int *))(**((_QWORD **)this + 241) + 136LL))(
            *((_QWORD *)this + 241),
            "GatewayPassword",
            0,
            &v116);
    if ( v11 < 0 )
    {
      v36 = (unsigned __int16 *)operator new(0x208u);
      if ( v36 )
      {
        v102 = v11;
        v37 = L"GetSecureStringProperty(TS_PROP_TRANSPORT_PROXYPASSWORD) failed!";
        v99 = 521;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
      v39 = L"GetSecureStringProperty(TS_PROP_TRANSPORT_PROXYPASSWORD) failed!";
      goto LABEL_88;
    }
    if ( !v116 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v83 = RdpX_GetActivityIdPrefix(v50, v49, v51, v52);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids, v83);
      }
      goto LABEL_215;
    }
    v107 = 0;
    v105 = 0;
    v114 = 2 * v116;
    if ( 2 * v116 < v116 )
    {
      v11 = -2147418113;
LABEL_156:
      RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v105, v49);
      goto LABEL_220;
    }
    v53 = LocalAlloc(0x40u, 2 * v116);
    v103 = v53;
    v56 = v53;
    if ( !v53 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v57 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v49, v54, v55);
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids,
          v57,
          (__int64)"PWSTR");
      }
      v11 = -2147024882;
      goto LABEL_156;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, const char *, _BYTE *, unsigned int *))(**((_QWORD **)this + 241) + 136LL))(
            *((_QWORD *)this + 241),
            "GatewayPassword",
            v53,
            &v116);
    if ( v11 < 0 )
    {
      v59 = (unsigned __int16 *)operator new(0x208u);
      v60 = v59;
      if ( v59 )
      {
        *v59 = 0;
        StringCchPrintfW(
          v59,
          0x104u,
          L"'%s' in %s at %d err=[0x%x]",
          L"GetSecureStringProperty(TS_PROP_TRANSPORT_PROXYPASSWORD) failed!",
          L"CClientHTTPProxyTransport::OnConnected",
          545,
          v11);
        CClientProxyTransport::TLDiagEvent(this, v60, v11);
        operator delete(v60);
      }
      else
      {
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
        CClientProxyTransport::TLDiagEvent(
          this,
          L"GetSecureStringProperty(TS_PROP_TRANSPORT_PROXYPASSWORD) failed!",
          v11);
      }
      goto LABEL_156;
    }
    v62 = RdpX_CreateObject(0, v58, 87, 124, &v105);
    if ( v62 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_173;
      }
      v65 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v61, v63, v64);
      v66 = 19;
    }
    else
    {
      v62 = (*(__int64 (__fastcall **)(__int64, void *, HLOCAL, HLOCAL *, unsigned int *))(*(_QWORD *)v105 + 48LL))(
              v105,
              v14,
              v56,
              &hMem,
              &v117);
      if ( !v62 )
      {
        v11 = ITscAuthenticationBlob_CreateInstance(hMem, v117, &v107);
        if ( v11 >= 0 )
        {
          v76 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 40LL))(v106);
          v77 = v107;
          v11 = (*(__int64 (__fastcall **)(__int64, const char *, struct ITscAuthenticationBlob *))(*(_QWORD *)v76 + 48LL))(
                  v76,
                  "CredentialsAuthenticationBlob",
                  v107);
          if ( v11 >= 0 )
          {
            RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v105, v78);
            if ( v77 )
              (*(void (__fastcall **)(struct ITscAuthenticationBlob *))(*(_QWORD *)v77 + 16LL))(v77);
            goto LABEL_215;
          }
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v82 = RdpX_GetActivityIdPrefix(v79, v78, v80, v81);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              (unsigned int)WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids,
              v82,
              (__int64)"SetIUnknownProperty (TS_PROP_AUTHENTICATION_BLOB) failed!",
              v11);
          }
          RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v105, v78);
          if ( !v77 )
            goto LABEL_220;
          v75 = *(_QWORD *)v77;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v74 = RdpX_GetActivityIdPrefix(v71, v70, v72, v73);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              (unsigned int)WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids,
              v74,
              (__int64)"ITscAuthenticationBlob_CreateInstance failed!",
              v11);
          }
          RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v105, v70);
          if ( !v107 )
            goto LABEL_220;
          v75 = *(_QWORD *)v107;
        }
        (*(void (**)(void))(v75 + 16))();
        goto LABEL_220;
      }
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_173;
      }
      v65 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v67, v68, v69);
      v66 = 20;
    }
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v66, WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids, v65, v62);
LABEL_173:
    v11 = MapXResultToHR(v62);
    goto LABEL_156;
  }
  v36 = (unsigned __int16 *)operator new(0x208u);
  if ( !v36 )
  {
LABEL_87:
    CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v11);
    v39 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !";
LABEL_88:
    v40 = v11;
    goto LABEL_89;
  }
  v102 = v11;
  v99 = 388;
LABEL_83:
  v37 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !";
LABEL_84:
  *v36 = 0;
LABEL_85:
  StringCchPrintfW(
    v36,
    0x104u,
    L"'%s' in %s at %d err=[0x%x]",
    v37,
    L"CClientHTTPProxyTransport::OnConnected",
    v99,
    v102);
  CClientProxyTransport::TLDiagEvent(this, v36, v11);
  v38 = v36;
LABEL_86:
  operator delete(v38);
LABEL_220:
  LocalFree(v35);
LABEL_221:
  if ( v14 )
    LocalFree(v14);
  v1 = v114;
  v3 = v103;
LABEL_224:
  v91 = hMem;
  if ( hMem )
  {
    v92 = v117;
    if ( v117 )
    {
      do
      {
        *v91++ = 0;
        --v92;
      }
      while ( v92 );
      v91 = hMem;
    }
    LocalFree(v91);
  }
  if ( v3 )
  {
    v93 = v1;
    v94 = v3;
    if ( v1 )
    {
      do
      {
        *v94++ = 0;
        --v93;
      }
      while ( v93 );
    }
    LocalFree(v3);
  }
  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v112);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v106);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18045b6b0  push    rbp
0x18045b6b2  push    rbx
0x18045b6b3  push    rsi
0x18045b6b4  push    rdi
0x18045b6b5  push    r12
0x18045b6b7  push    r13
0x18045b6b9  push    r14
0x18045b6bb  push    r15
0x18045b6bd  lea     rbp, [rsp-1Fh]
0x18045b6c2  sub     rsp, 98h
0x18045b6c9  xor     r12d, r12d
0x18045b6cc  mov     [rbp+57h+var_78], 0
0x18045b6d4  mov     rdi, rcx
0x18045b6d7  mov     dword ptr [rbp+57h+uBytes], 0
0x18045b6de  add     rcx, 4E8h; this
0x18045b6e5  mov     [rbp+57h+var_68], 0
0x18045b6ec  xor     r14d, r14d
0x18045b6ef  mov     [rbp+57h+var_70], rcx
0x18045b6f3  mov     r15d, 4
0x18045b6f9  mov     [rbp+57h+var_60], 0
0x18045b700  mov     [rbp+57h+var_48], r15d
0x18045b704  mov     [rbp+57h+var_64], 0
0x18045b70b  mov     [rbp+57h+var_90], r14
0x18045b70f  mov     [rbp+57h+arg_10], r14d
0x18045b713  mov     [rbp+57h+arg_0], r12d
0x18045b717  mov     [rbp+57h+hMem], r12
0x18045b71b  mov     [rbp+57h+arg_18], r12d
0x18045b71f  mov     [rbp+57h+var_50], r12
0x18045b723  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18045b728  cmp     [rdi+4E0h], r12
0x18045b72f  jz      short loc_18045B753
0x18045b731  lea     rcx, [rbp+57h+var_50]
0x18045b735  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x18045b73a  mov     rbx, [rdi+4E0h]
0x18045b741  lea     rcx, [rbp+57h+var_50]
0x18045b745  mov     [rbp+57h+var_50], rbx
0x18045b749  call    ?SafeAddRef@?$TCntPtr@VCRailNotify@WindowsRemoteAppLib@@@@AEAAXXZ; TCntPtr<WindowsRemoteAppLib::CRailNotify>::SafeAddRef(void)
0x18045b74e  mov     rsi, rbx
0x18045b751  jmp     short loc_18045B757
0x18045b753  xor     ebx, ebx
0x18045b755  xor     esi, esi
0x18045b757  lea     rcx, [rbp+57h+var_70]; this
0x18045b75b  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18045b760  test    rbx, rbx
0x18045b763  jnz     short loc_18045B7B6
0x18045b765  mov     rax, cs:WPP_GLOBAL_Control
0x18045b76c  lea     r14, WPP_GLOBAL_Control
0x18045b773  cmp     rax, r14
0x18045b776  jz      short loc_18045B7A9
0x18045b778  test    dword ptr [rax+1Ch], 800h
0x18045b77f  jz      short loc_18045B7A9
0x18045b781  cmp     byte ptr [rax+19h], 2
0x18045b785  jb      short loc_18045B7A9
0x18045b787  call    RdpX_GetActivityIdPrefix
0x18045b78c  mov     rcx, cs:WPP_GLOBAL_Control
0x18045b793  lea     edx, [rbx+0Fh]
0x18045b796  mov     r9d, eax
0x18045b799  lea     r8, WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids
0x18045b7a0  mov     rcx, [rcx+10h]
0x18045b7a4  call    WPP_SF_d
0x18045b7a9  mov     ebx, 80004005h
0x18045b7ae  mov     r14, r12
0x18045b7b1  jmp     loc_18045CC1C
0x18045b7b6  mov     rcx, [rsi+70h]
0x18045b7ba  mov     rax, [rcx]
0x18045b7bd  mov     rax, [rax+40h]
0x18045b7c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045b7c6  mov     rcx, [rdi+788h]
0x18045b7cd  lea     rdx, aGatewayServerU_0; "Gateway server UDP support"
0x18045b7d4  mov     r12d, eax
0x18045b7d7  mov     r8d, r12d
0x18045b7da  mov     rax, [rcx]
0x18045b7dd  mov     rax, [rax+20h]
0x18045b7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045b7e6  mov     ebx, eax
0x18045b7e8  test    eax, eax
0x18045b7ea  jns     loc_18045B87E
0x18045b7f0  mov     ecx, 208h; Size
0x18045b7f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18045b7fa  mov     rsi, rax
0x18045b7fd  test    rax, rax
0x18045b800  jz      short loc_18045B858
0x18045b802  mov     [rsp+0D0h+var_A0], ebx
0x18045b806  lea     rcx, aCclienthttppro_2; "CClientHTTPProxyTransport::OnConnected"
0x18045b80d  xor     eax, eax
0x18045b80f  mov     [rsp+0D0h+var_A8], 103h
0x18045b817  mov     [rsp+0D0h+var_B0], rcx
0x18045b81c  lea     r9, aSetboolpropert_53; "SetBoolProperty failed for IsUdpSupport"...
0x18045b823  mov     rcx, rsi; unsigned __int16 *
0x18045b826  mov     [rsi], ax
0x18045b829  lea     r8, aSInSAtDErr0xX; "'%s' in %s at %d err=[0x%x]"
0x18045b830  mov     edx, 104h; unsigned __int64
0x18045b835  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18045b83a  mov     r8d, ebx; unsigned int
0x18045b83d  mov     rdx, rsi; unsigned __int16 *
0x18045b840  mov     rcx, rdi; this
0x18045b843  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045b848  mov     rcx, rsi; Block
0x18045b84b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18045b850  mov     r12d, r14d
0x18045b853  jmp     loc_18045CC1C
0x18045b858  mov     r8d, ebx; unsigned int
0x18045b85b  lea     rdx, aCannotAllocate_0; "Cannot allocate memory"
0x18045b862  mov     rcx, rdi; this
0x18045b865  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045b86a  mov     r8d, ebx; unsigned int
0x18045b86d  lea     rdx, aSetboolpropert_53; "SetBoolProperty failed for IsUdpSupport"...
0x18045b874  mov     rcx, rdi; this
0x18045b877  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045b87c  jmp     short loc_18045B850
0x18045b87e  mov     rcx, [rsi+70h]
0x18045b882  xor     r13d, r13d
0x18045b885  mov     rax, [rcx]
0x18045b888  mov     rax, [rax+38h]
0x18045b88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045b891  mov     rcx, [rdi+788h]
0x18045b898  lea     rdx, aControlChannel; "Control channel connection type"
0x18045b89f  cmp     eax, 1
0x18045b8a2  mov     rax, [rcx]
0x18045b8a5  mov     rax, [rax+18h]
0x18045b8a9  jnz     loc_18045CB20
0x18045b8af  mov     r8d, r15d
0x18045b8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045b8b7  mov     ebx, eax
0x18045b8b9  test    eax, eax
0x18045b8bb  jns     loc_18045B94F
0x18045b8c1  mov     ecx, 208h; Size
0x18045b8c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18045b8cb  mov     rsi, rax
0x18045b8ce  test    rax, rax
0x18045b8d1  jz      short loc_18045B929
0x18045b8d3  xor     eax, eax
0x18045b8d5  mov     [rsp+0D0h+var_A0], ebx
0x18045b8d9  mov     [rsi], ax
0x18045b8dc  mov     [rsp+0D0h+var_A8], 10Ch
0x18045b8e4  lea     rcx, aCclienthttppro_2; "CClientHTTPProxyTransport::OnConnected"
0x18045b8eb  mov     edx, 104h; unsigned __int64
0x18045b8f0  mov     [rsp+0D0h+var_B0], rcx
0x18045b8f5  lea     r9, aSetpropertyFai_1; "SetProperty failed for Main transport t"...
0x18045b8fc  mov     rcx, rsi; unsigned __int16 *
0x18045b8ff  lea     r8, aSInSAtDErr0xX; "'%s' in %s at %d err=[0x%x]"
0x18045b906  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18045b90b  mov     r8d, ebx; unsigned int
0x18045b90e  mov     rdx, rsi; unsigned __int16 *
0x18045b911  mov     rcx, rdi; this
0x18045b914  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045b919  mov     rcx, rsi; Block
0x18045b91c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18045b921  mov     r12d, r13d
0x18045b924  jmp     loc_18045CC1C
0x18045b929  mov     r8d, ebx; unsigned int
0x18045b92c  lea     rdx, aCannotAllocate_0; "Cannot allocate memory"
0x18045b933  mov     rcx, rdi; this
0x18045b936  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045b93b  mov     r8d, ebx; unsigned int
0x18045b93e  lea     rdx, aSetpropertyFai_1; "SetProperty failed for Main transport t"...
0x18045b945  mov     rcx, rdi; this
0x18045b948  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045b94d  jmp     short loc_18045B921
0x18045b94f  lea     r14, WPP_GLOBAL_Control
0x18045b956  lea     r15, WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids
0x18045b95d  test    r12d, r12d
0x18045b960  jz      loc_18045BD28
0x18045b966  mov     [rbp+57h+var_88], r13d
0x18045b96a  lea     r9, [rbp+57h+uBytes]
0x18045b96e  mov     rcx, [rsi+70h]
0x18045b972  xor     r8d, r8d
0x18045b975  mov     rax, [rcx]
0x18045b978  lea     edx, [r8+4]
0x18045b97c  mov     rax, [rax+58h]
0x18045b980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045b985  mov     ebx, eax
0x18045b987  test    eax, eax
0x18045b989  jns     loc_18045BA1D
0x18045b98f  mov     ecx, 208h; Size
0x18045b994  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18045b999  mov     rsi, rax
0x18045b99c  test    rax, rax
0x18045b99f  jz      short loc_18045B9F7
0x18045b9a1  mov     [rsp+0D0h+var_A0], ebx
0x18045b9a5  lea     r9, aGetsidetranspo_2; "GetSideTransportProperty for size of UD"...
0x18045b9ac  mov     [rsp+0D0h+var_A8], 119h
0x18045b9b4  lea     rcx, aCclienthttppro_2; "CClientHTTPProxyTransport::OnConnected"
0x18045b9bb  xor     eax, eax
0x18045b9bd  mov     [rsp+0D0h+var_B0], rcx
0x18045b9c2  lea     r8, aSInSAtDErr0xX; "'%s' in %s at %d err=[0x%x]"
0x18045b9c9  mov     rcx, rsi; unsigned __int16 *
0x18045b9cc  mov     [rsi], ax
0x18045b9cf  mov     edx, 104h; unsigned __int64
0x18045b9d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18045b9d9  mov     r8d, ebx; unsigned int
0x18045b9dc  mov     rdx, rsi; unsigned __int16 *
0x18045b9df  mov     rcx, rdi; this
0x18045b9e2  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045b9e7  mov     rcx, rsi; Block
0x18045b9ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18045b9ef  mov     r14, r13
0x18045b9f2  jmp     loc_18045B921
0x18045b9f7  mov     r8d, ebx; unsigned int
0x18045b9fa  lea     rdx, aCannotAllocate_0; "Cannot allocate memory"
0x18045ba01  mov     rcx, rdi; this
0x18045ba04  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045ba09  lea     rdx, aGetsidetranspo_2; "GetSideTransportProperty for size of UD"...
0x18045ba10  mov     r8d, ebx; unsigned int
0x18045ba13  mov     rcx, rdi; this
0x18045ba16  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045ba1b  jmp     short loc_18045B9EF
0x18045ba1d  mov     eax, dword ptr [rbp+57h+uBytes]
0x18045ba20  test    eax, eax
0x18045ba22  jz      loc_18045BC12
0x18045ba28  mov     edx, eax; uBytes
0x18045ba2a  mov     ecx, 40h ; '@'; uFlags
0x18045ba2f  call    cs:__imp_LocalAlloc
0x18045ba35  mov     r12, rax
0x18045ba38  test    rax, rax
0x18045ba3b  jnz     loc_18045BACD
0x18045ba41  mov     ecx, 208h; Size
0x18045ba46  mov     ebx, 8007000Eh
0x18045ba4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18045ba50  mov     r14, rax
0x18045ba53  mov     esi, 8007000Eh
0x18045ba58  test    rax, rax
0x18045ba5b  jz      short loc_18045BAAC
0x18045ba5d  mov     [rsp+0D0h+var_A0], esi
0x18045ba61  lea     r9, aTsallocFailedF; "TSAlloc failed for sideChannelAuthCooki"...
0x18045ba68  mov     [rsp+0D0h+var_A8], 123h
0x18045ba70  lea     rcx, aCclienthttppro_2; "CClientHTTPProxyTransport::OnConnected"
0x18045ba77  xor     eax, eax
0x18045ba79  mov     [rsp+0D0h+var_B0], rcx
0x18045ba7e  lea     r8, aSInSAtDErr0xX; "'%s' in %s at %d err=[0x%x]"
0x18045ba85  mov     rcx, r14; unsigned __int16 *
0x18045ba88  mov     [r14], ax
0x18045ba8c  mov     edx, 104h; unsigned __int64
0x18045ba91  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18045ba96  mov     r8d, esi; unsigned int
0x18045ba99  mov     rdx, r14; unsigned __int16 *
0x18045ba9c  mov     rcx, rdi; this
0x18045ba9f  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045baa4  mov     rcx, r14
0x18045baa7  jmp     loc_18045B9EA
0x18045baac  mov     r8d, esi; unsigned int
0x18045baaf  lea     rdx, aCannotAllocate_0; "Cannot allocate memory"
0x18045bab6  mov     rcx, rdi; this
0x18045bab9  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045babe  mov     r8d, esi
0x18045bac1  lea     rdx, aTsallocFailedF; "TSAlloc failed for sideChannelAuthCooki"...
0x18045bac8  jmp     loc_18045BA13
0x18045bacd  mov     rcx, [rsi+70h]
0x18045bad1  lea     r9, [rbp+57h+uBytes]
0x18045bad5  mov     r8, r12
0x18045bad8  mov     edx, 4
0x18045badd  mov     rax, [rcx]
0x18045bae0  mov     rax, [rax+58h]
0x18045bae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045bae9  mov     ebx, eax
0x18045baeb  test    eax, eax
0x18045baed  jns     short loc_18045BB37
0x18045baef  mov     ecx, 208h; Size
0x18045baf4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18045baf9  mov     rsi, rax
0x18045bafc  test    rax, rax
0x18045baff  jz      short loc_18045BB19
0x18045bb01  mov     [rsp+0D0h+var_A0], ebx
0x18045bb05  lea     r9, aGetsidetranspo_3; "GetSideTransportProperty for UDP cookie"...
0x18045bb0c  mov     [rsp+0D0h+var_A8], 12Ch
0x18045bb14  jmp     loc_18045B9B4
0x18045bb19  mov     r8d, ebx; unsigned int
0x18045bb1c  lea     rdx, aCannotAllocate_0; "Cannot allocate memory"
0x18045bb23  mov     rcx, rdi; this
0x18045bb26  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045bb2b  lea     rdx, aGetsidetranspo_3; "GetSideTransportProperty for UDP cookie"...
0x18045bb32  jmp     loc_18045BA10
0x18045bb37  mov     rcx, [rdi+788h]
0x18045bb3e  lea     rdx, aSideChannelAut_0; "Side channel authentication cookie"
0x18045bb45  mov     r8, r12
0x18045bb48  mov     rax, [rcx]
0x18045bb4b  mov     rax, [rax+50h]
0x18045bb4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18045bb54  mov     ebx, eax
0x18045bb56  test    eax, eax
0x18045bb58  jns     short loc_18045BBA2
0x18045bb5a  mov     ecx, 208h; Size
0x18045bb5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18045bb64  mov     rsi, rax
0x18045bb67  test    rax, rax
0x18045bb6a  jz      short loc_18045BB84
0x18045bb6c  mov     [rsp+0D0h+var_A0], ebx
0x18045bb70  lea     r9, aSetulongptrpro; "SetUlongPtrProperty for m_upSideChannel"...
0x18045bb77  mov     [rsp+0D0h+var_A8], 132h
0x18045bb7f  jmp     loc_18045B9B4
0x18045bb84  mov     r8d, ebx; unsigned int
0x18045bb87  lea     rdx, aCannotAllocate_0; "Cannot allocate memory"
0x18045bb8e  mov     rcx, rdi; this
0x18045bb91  call    ?TLDiagEvent@CClientProxyTransport@@QEAAXPEBGK@Z; CClientProxyTransport::TLDiagEvent(ushort const *,ulong)
0x18045bb96  lea     rdx, aSetulongptrpro; "SetUlongPtrProperty for m_upSideChannel"...
0x18045bb9d  jmp     loc_18045BA10
0x18045bba2  mov     rcx, [rdi+788h]
0x18045bba9  lea     rdx, aSideChannelAut; "Side channel authentication cookie size"
0x18045bbb0  mov     r8d, dword ptr [rbp+57h+uBytes]
0x18045bbb4  mov     rax, [rcx]
  ... truncated ...
```
