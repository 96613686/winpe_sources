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
  unsigned int ActivityIdPrefix; // eax
  signed int v10; // ebx
  __int64 v11; // r12
  unsigned __int16 *v12; // rsi
  void *v13; // r13
  int v14; // eax
  __int64 v15; // rcx
  bool v16; // zf
  __int64 (__fastcall *v17)(__int64, const char *, __int64); // rax
  unsigned __int16 *v18; // rsi
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  unsigned __int16 *v22; // rsi
  const wchar_t *v23; // r9
  unsigned __int16 *v24; // rcx
  const unsigned __int16 *v25; // rdx
  unsigned int v26; // r8d
  HLOCAL v27; // rax
  HLOCAL v28; // r12
  unsigned __int16 *v29; // r14
  const wchar_t *v30; // r9
  unsigned int v31; // eax
  HLOCAL v32; // rax
  void *v33; // r12
  unsigned __int16 *v34; // rsi
  const wchar_t *v35; // r9
  unsigned __int16 *v36; // rcx
  const unsigned __int16 *v37; // rdx
  unsigned int v38; // r8d
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  HLOCAL v42; // rax
  unsigned __int16 *v43; // r14
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  _BYTE *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  HLOCAL v53; // rsi
  int v54; // eax
  __int64 v55; // rdx
  unsigned __int16 *v56; // rax
  unsigned __int16 *v57; // rsi
  __int64 v58; // rdx
  unsigned int v59; // ebx
  __int64 v60; // r8
  unsigned int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  int v68; // eax
  __int64 v69; // rax
  __int64 v70; // rax
  struct ITscAuthenticationBlob *v71; // rsi
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  int v75; // eax
  unsigned int v76; // eax
  unsigned __int16 *v77; // rax
  __int64 v78; // rax
  unsigned __int16 *v79; // rax
  unsigned __int16 *v80; // rax
  unsigned __int16 *v81; // rax
  unsigned __int16 *v82; // rax
  unsigned __int16 *v83; // rsi
  _BYTE *v84; // rcx
  __int64 v85; // rax
  __int64 v86; // rcx
  _BYTE *v87; // rax
  int v89; // [rsp+28h] [rbp-51h]
  int v90; // [rsp+28h] [rbp-51h]
  int v91; // [rsp+28h] [rbp-51h]
  int v92; // [rsp+28h] [rbp-51h]
  signed int v93; // [rsp+30h] [rbp-49h]
  signed int v94; // [rsp+30h] [rbp-49h]
  signed int v95; // [rsp+30h] [rbp-49h]
  _BYTE *v96; // [rsp+40h] [rbp-39h]
  unsigned int v97; // [rsp+48h] [rbp-31h] BYREF
  __int64 v98; // [rsp+50h] [rbp-29h] BYREF
  __int64 v99; // [rsp+58h] [rbp-21h] BYREF
  struct ITscAuthenticationBlob *v100; // [rsp+60h] [rbp-19h] BYREF
  int v101; // [rsp+68h] [rbp-11h] BYREF
  int v102; // [rsp+6Ch] [rbp-Dh] BYREF
  int v103; // [rsp+70h] [rbp-9h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-1h] BYREF
  __int64 v105; // [rsp+80h] [rbp+7h] BYREF
  int v106[18]; // [rsp+88h] [rbp+Fh] BYREF
  int v107; // [rsp+E0h] [rbp+67h]
  SIZE_T uBytes; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v109; // [rsp+F0h] [rbp+77h] BYREF
  unsigned int v110; // [rsp+F8h] [rbp+7Fh] BYREF

  v1 = 0;
  v99 = 0;
  LODWORD(uBytes) = 0;
  v101 = 0;
  v3 = 0;
  v100 = (CClientHTTPProxyTransport *)((char *)this + 1256);
  v103 = 0;
  v106[0] = 4;
  v102 = 0;
  v96 = 0;
  v109 = 0;
  v107 = 0;
  hMem = 0;
  v110 = 0;
  v105 = 0;
  CTSCriticalSection::Lock((CClientHTTPProxyTransport *)((char *)this + 1256));
  if ( *((_QWORD *)this + 156) )
  {
    TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v105);
    v105 = *((_QWORD *)this + 156);
    v4 = v105;
    TCntPtr<WindowsRemoteAppLib::CRailNotify>::SafeAddRef(&v105);
    v5 = v4;
  }
  else
  {
    v4 = 0;
    v5 = 0;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v100);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(v7, v6, v8);
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids,
        ActivityIdPrefix);
    }
    v10 = -2147467259;
    v3 = 0;
    goto LABEL_224;
  }
  v11 = (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 112) + 64LL))(*(_QWORD *)(v5 + 112));
  v10 = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64))(**((_QWORD **)this + 241) + 32LL))(
          *((_QWORD *)this + 241),
          "Gateway server UDP support",
          v11);
  if ( v10 < 0 )
  {
    v12 = (unsigned __int16 *)operator new(0x208u);
    if ( v12 )
    {
      *v12 = 0;
      StringCchPrintfW(
        v12,
        0x104u,
        L"'%s' in %s at %d err=[0x%x]",
        L"SetBoolProperty failed for IsUdpSupported!",
        L"CClientHTTPProxyTransport::OnConnected",
        259,
        v10);
      CClientProxyTransport::TLDiagEvent(this, v12, v10);
      operator delete(v12);
    }
    else
    {
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      CClientProxyTransport::TLDiagEvent(this, L"SetBoolProperty failed for IsUdpSupported!", v10);
    }
    v1 = 0;
    goto LABEL_224;
  }
  v13 = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 112) + 56LL))(*(_QWORD *)(v5 + 112));
  v15 = *((_QWORD *)this + 241);
  v16 = v14 == 1;
  v17 = *(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v15 + 24LL);
  if ( !v16 )
  {
    v10 = v17(v15, "Control channel connection type", 3);
    if ( v10 < 0 )
    {
      v81 = (unsigned __int16 *)operator new(0x208u);
      v18 = v81;
      if ( v81 )
      {
        v93 = v10;
        *v81 = 0;
        v89 = 624;
        goto LABEL_19;
      }
LABEL_21:
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      CClientProxyTransport::TLDiagEvent(this, L"SetProperty failed for Main transport type", v10);
      goto LABEL_20;
    }
LABEL_214:
    v33 = 0;
    goto LABEL_215;
  }
  v10 = v17(v15, "Control channel connection type", 4);
  if ( v10 < 0 )
  {
    v18 = (unsigned __int16 *)operator new(0x208u);
    if ( v18 )
    {
      v93 = v10;
      *v18 = 0;
      v89 = 268;
LABEL_19:
      StringCchPrintfW(
        v18,
        0x104u,
        L"'%s' in %s at %d err=[0x%x]",
        L"SetProperty failed for Main transport type",
        L"CClientHTTPProxyTransport::OnConnected",
        v89,
        v93);
      CClientProxyTransport::TLDiagEvent(this, v18, v10);
      operator delete(v18);
LABEL_20:
      v1 = 0;
      goto LABEL_224;
    }
    goto LABEL_21;
  }
  if ( (_DWORD)v11 )
  {
    v97 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
            *(_QWORD *)(v5 + 112),
            4,
            0,
            &uBytes);
    if ( v10 < 0 )
    {
      v22 = (unsigned __int16 *)operator new(0x208u);
      if ( v22 )
      {
        v94 = v10;
        v23 = L"GetSideTransportProperty for size of UDP cookie failed !";
        v90 = 281;
LABEL_26:
        *v22 = 0;
        StringCchPrintfW(
          v22,
          0x104u,
          L"'%s' in %s at %d err=[0x%x]",
          v23,
          L"CClientHTTPProxyTransport::OnConnected",
          v90,
          v94);
        CClientProxyTransport::TLDiagEvent(this, v22, v10);
        v24 = v22;
LABEL_27:
        operator delete(v24);
LABEL_28:
        v3 = 0;
        goto LABEL_20;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v25 = L"GetSideTransportProperty for size of UDP cookie failed !";
      goto LABEL_30;
    }
    if ( (_DWORD)uBytes )
    {
      v27 = LocalAlloc(0x40u, (unsigned int)uBytes);
      v28 = v27;
      if ( !v27 )
      {
        v10 = -2147024882;
        v29 = (unsigned __int16 *)operator new(0x208u);
        if ( !v29 )
        {
          CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", 0x8007000E);
          v26 = -2147024882;
          v25 = L"TSAlloc failed for sideChannelAuthCookie";
          goto LABEL_31;
        }
        v30 = L"TSAlloc failed for sideChannelAuthCookie";
        v91 = 291;
LABEL_36:
        *v29 = 0;
        StringCchPrintfW(
          v29,
          0x104u,
          L"'%s' in %s at %d err=[0x%x]",
          v30,
          L"CClientHTTPProxyTransport::OnConnected",
          v91,
          -2147024882);
        CClientProxyTransport::TLDiagEvent(this, v29, 0x8007000E);
        v24 = v29;
        goto LABEL_27;
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, HLOCAL, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
              *(_QWORD *)(v5 + 112),
              4,
              v27,
              &uBytes);
      if ( v10 < 0 )
      {
        v22 = (unsigned __int16 *)operator new(0x208u);
        if ( v22 )
        {
          v94 = v10;
          v23 = L"GetSideTransportProperty for UDP cookie failed !";
          v90 = 300;
          goto LABEL_26;
        }
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
        v25 = L"GetSideTransportProperty for UDP cookie failed !";
        goto LABEL_30;
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, const char *, HLOCAL))(**((_QWORD **)this + 241) + 80LL))(
              *((_QWORD *)this + 241),
              "Side channel authentication cookie",
              v28);
      if ( v10 < 0 )
      {
        v22 = (unsigned __int16 *)operator new(0x208u);
        if ( v22 )
        {
          v94 = v10;
          v23 = L"SetUlongPtrProperty for m_upSideChannelAuthCookie failed !";
          v90 = 306;
          goto LABEL_26;
        }
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
        v25 = L"SetUlongPtrProperty for m_upSideChannelAuthCookie failed !";
        goto LABEL_30;
      }
      v10 = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 241) + 24LL))(
              *((_QWORD *)this + 241),
              "Side channel authentication cookie size",
              (unsigned int)uBytes);
      if ( v10 < 0 )
      {
        v22 = (unsigned __int16 *)operator new(0x208u);
        if ( v22 )
        {
          v94 = v10;
          v23 = L"SetProperty for m_dwSideChannelAuthCookieSize failed !";
          v90 = 312;
          goto LABEL_26;
        }
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
        v25 = L"SetProperty for m_dwSideChannelAuthCookieSize failed !";
        goto LABEL_30;
      }
    }
    else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
           && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v31 = RdpX_GetActivityIdPrefix(v20, v19, v21);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids, v31);
    }
    LODWORD(uBytes) = 4;
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
            *(_QWORD *)(v5 + 112),
            1,
            &v97,
            &uBytes);
    if ( v10 < 0 )
    {
      v22 = (unsigned __int16 *)operator new(0x208u);
      if ( v22 )
      {
        v94 = v10;
        v23 = L"GetSideTransportProperty for UDP port failed !";
        v90 = 326;
        goto LABEL_26;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v25 = L"GetSideTransportProperty for UDP port failed !";
      goto LABEL_30;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 241) + 24LL))(
            *((_QWORD *)this + 241),
            "Side channel port",
            v97);
    if ( v10 < 0 )
    {
      v22 = (unsigned __int16 *)operator new(0x208u);
      if ( v22 )
      {
        v94 = v10;
        v23 = L"SetProperty for Udp port failed !";
        v90 = 332;
        goto LABEL_26;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v25 = L"SetProperty for Udp port failed !";
      goto LABEL_30;
    }
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, int *))(**(_QWORD **)(v5 + 112) + 88LL))(
          *(_QWORD *)(v5 + 112),
          12,
          &v101,
          v106);
  if ( v10 < 0 )
  {
    v22 = (unsigned __int16 *)operator new(0x208u);
    if ( v22 )
    {
      v94 = v10;
      v23 = L"GetProperty AA_TRANSPORT_PROPERTY_RESOURCECHANNEL Failed !";
      v90 = 341;
      goto LABEL_26;
    }
    CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
    v25 = L"GetProperty AA_TRANSPORT_PROPERTY_RESOURCECHANNEL Failed !";
    goto LABEL_30;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, const char *, int *))(**((_QWORD **)this + 241) + 96LL))(
          *((_QWORD *)this + 241),
          "GatewayBrokeringType",
          &v102);
  if ( v10 < 0 )
  {
    v22 = (unsigned __int16 *)operator new(0x208u);
    if ( v22 )
    {
      v94 = v10;
      v23 = L"GetProperty TS_PROP_TRANSPORT_PROXYBROKERINGTYPE Failed !";
      v90 = 346;
      goto LABEL_26;
    }
    CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
    v25 = L"GetProperty TS_PROP_TRANSPORT_PROXYBROKERINGTYPE Failed !";
    goto LABEL_30;
  }
  if ( !v101 || v102 != 1 )
    goto LABEL_214;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
          *(_QWORD *)(v5 + 112),
          11,
          0,
          &uBytes);
  if ( v10 < 0 )
  {
    v22 = (unsigned __int16 *)operator new(0x208u);
    if ( v22 )
    {
      v94 = v10;
      v23 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !";
      v90 = 370;
      goto LABEL_26;
    }
    CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
    v25 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !";
LABEL_30:
    v26 = v10;
LABEL_31:
    CClientProxyTransport::TLDiagEvent(this, v25, v26);
    goto LABEL_28;
  }
  v32 = LocalAlloc(0x40u, (unsigned int)uBytes);
  v33 = v32;
  if ( !v32 )
  {
    v10 = -2147024882;
    v29 = (unsigned __int16 *)operator new(0x208u);
    if ( !v29 )
    {
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", 0x8007000E);
      v26 = -2147024882;
      v25 = L"TSAlloc failed for serverName";
      goto LABEL_31;
    }
    v30 = L"TSAlloc failed for serverName";
    v91 = 376;
    goto LABEL_36;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, HLOCAL, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
          *(_QWORD *)(v5 + 112),
          11,
          v32,
          &uBytes);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 234) + 160LL))(
            *((_QWORD *)this + 234),
            &v99);
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v35 = L"Failed to get CoreAPI from ITSInstance";
        v92 = 395;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v37 = L"Failed to get CoreAPI from ITSInstance";
      goto LABEL_88;
    }
    v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 40LL))(v99);
    v10 = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v39 + 32LL))(
            v39,
            "RedirectionClientRedirected",
            1);
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        *v34 = 0;
        v92 = 401;
LABEL_97:
        v35 = L"SetBoolProperty (TS_PROP_REDIRECTION_CLIENT_REDIRECTED) failed!";
        goto LABEL_85;
      }
      goto LABEL_98;
    }
    v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 40LL))(v99);
    v10 = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v40 + 32LL))(
            v40,
            "UseRedirectionServerName",
            1);
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v35 = L"SetBoolProperty (TS_PROP_USE_REDIRECTION_SERVERNAME) failed!";
        v92 = 407;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v37 = L"SetBoolProperty (TS_PROP_USE_REDIRECTION_SERVERNAME) failed!";
      goto LABEL_88;
    }
    v41 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 40LL))(v99);
    v10 = (*(__int64 (__fastcall **)(__int64, const char *, void *, _QWORD))(*(_QWORD *)v41 + 56LL))(
            v41,
            "ServerName",
            v33,
            0);
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v35 = L"SetStringProperty (TS_PROP_CORE_SERVERNAME) failed!";
        v92 = 413;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v37 = L"SetStringProperty (TS_PROP_CORE_SERVERNAME) failed!";
      goto LABEL_88;
    }
    v10 = CClientHTTPProxyTransport::TransformSidePropToCoreSPropSZ(this, 0xDu, "TargetCertificate");
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v35 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERCERT to TS_PROP_REDIRECTION_TARGET_CERTIFICATE failed !";
        v92 = 436;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v37 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERCERT to TS_PROP_REDIRECTION_TARGET_CERTIFICATE failed !";
      goto LABEL_88;
    }
    v10 = CClientHTTPProxyTransport::TransformSidePropToCoreSPropSZ(this, 0xFu, "RedirectionGuid");
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v35 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHGUID to TS_PROP_REDIRECTION_GUID failed !";
        v92 = 439;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v37 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHGUID to TS_PROP_REDIRECTION_GUID failed !";
      goto LABEL_88;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
            *(_QWORD *)(v5 + 112),
            17,
            0,
            &uBytes);
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v92 = 457;
        goto LABEL_83;
      }
      goto LABEL_87;
    }
    if ( !(_DWORD)uBytes )
    {
      LODWORD(uBytes) = 4;
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, int *, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
              *(_QWORD *)(v5 + 112),
              18,
              &v103,
              &uBytes);
      if ( v10 < 0 )
      {
        v77 = (unsigned __int16 *)operator new(0x208u);
        v34 = v77;
        if ( v77 )
        {
          v95 = v10;
          *v77 = 0;
          v35 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_LOGONCERTENABLED failed !";
          v92 = 601;
          goto LABEL_85;
        }
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
        v37 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_LOGONCERTENABLED failed !";
        goto LABEL_88;
      }
      if ( v103 )
      {
        v78 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 40LL))(v99);
        v10 = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v78 + 32LL))(
                v78,
                "UseLogonCertificate",
                1);
        if ( v10 < 0 )
        {
          v79 = (unsigned __int16 *)operator new(0x208u);
          v34 = v79;
          if ( v79 )
          {
            v95 = v10;
            *v79 = 0;
            v92 = 609;
            goto LABEL_97;
          }
LABEL_98:
          CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
          v37 = L"SetBoolProperty (TS_PROP_REDIRECTION_CLIENT_REDIRECTED) failed!";
          goto LABEL_88;
        }
        v10 = CClientHTTPProxyTransport::TransformSidePropToCoreSPropSZ(this, 0xEu, "PKEncryptedPassword");
        if ( v10 < 0 )
        {
          v80 = (unsigned __int16 *)operator new(0x208u);
          v34 = v80;
          if ( v80 )
          {
            v95 = v10;
            *v80 = 0;
            v92 = 612;
            goto LABEL_147;
          }
LABEL_148:
          CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
          v37 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHBLOB to TS_PROP_REDIRECTION_PK_ENCRY"
                 "PTED_PASSWORD failed !";
          goto LABEL_88;
        }
      }
LABEL_215:
      v10 = CClientProxyTransport::OnConnected(this);
      if ( v10 < 0 )
      {
        v82 = (unsigned __int16 *)operator new(0x208u);
        v83 = v82;
        if ( v82 )
        {
          *v82 = 0;
          StringCchPrintfW(
            v82,
            0x104u,
            L"'%s' in %s at %d err=[0x%x]",
            L"OnConnected failed!",
            L"CClientHTTPProxyTransport::OnConnected",
            628,
            v10);
          CClientProxyTransport::TLDiagEvent(this, v83, v10);
          operator delete(v83);
        }
        else
        {
          CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
          CClientProxyTransport::TLDiagEvent(this, L"OnConnected failed!", v10);
        }
      }
      if ( !v33 )
        goto LABEL_221;
      goto LABEL_220;
    }
    v97 = 0;
    v42 = LocalAlloc(0x40u, (unsigned int)uBytes);
    v13 = v42;
    if ( !v42 )
    {
      v10 = -2147024882;
      v43 = (unsigned __int16 *)operator new(0x208u);
      if ( v43 )
      {
        *v43 = 0;
        StringCchPrintfW(
          v43,
          0x104u,
          L"'%s' in %s at %d err=[0x%x]",
          L"TSAlloc failed for userName",
          L"CClientHTTPProxyTransport::OnConnected",
          467,
          -2147024882);
        CClientProxyTransport::TLDiagEvent(this, v43, 0x8007000E);
        v36 = v43;
        goto LABEL_86;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", 0x8007000E);
      v38 = -2147024882;
      v37 = L"TSAlloc failed for userName";
LABEL_89:
      CClientProxyTransport::TLDiagEvent(this, v37, v38);
      goto LABEL_220;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, HLOCAL, SIZE_T *))(**(_QWORD **)(v5 + 112) + 88LL))(
            *(_QWORD *)(v5 + 112),
            17,
            v42,
            &uBytes);
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v35 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_USERNAME failed !";
        v92 = 476;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v37 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_USERNAME failed !";
      goto LABEL_88;
    }
    v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 40LL))(v99);
    v10 = (*(__int64 (__fastcall **)(__int64, const char *, void *, _QWORD))(*(_QWORD *)v44 + 56LL))(
            v44,
            "RedirectionUserName",
            v13,
            0);
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v35 = L"SetStringProperty (TS_PROP_REDIRECTION_USERNAME) failed!";
        v92 = 482;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v37 = L"SetStringProperty (TS_PROP_REDIRECTION_USERNAME) failed!";
      goto LABEL_88;
    }
    v45 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 40LL))(v99);
    v10 = (*(__int64 (__fastcall **)(__int64, const char *, __int64))(*(_QWORD *)v45 + 32LL))(
            v45,
            "UseRedirectionUserName",
            1);
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v35 = L"SetBoolProperty (TS_PROP_USE_REDIRECTION_USERNAME) failed!";
        v92 = 488;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v37 = L"SetBoolProperty (TS_PROP_USE_REDIRECTION_USERNAME) failed!";
      goto LABEL_88;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, const char *, unsigned int *))(**((_QWORD **)this + 241) + 96LL))(
            *((_QWORD *)this + 241),
            "GatewayCredsSource",
            &v97);
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v35 = L"GetProperty TS_PROP_TRANSPORT_PROXYCREDSSOURCE Failed !";
        v92 = 497;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v37 = L"GetProperty TS_PROP_TRANSPORT_PROXYCREDSSOURCE Failed !";
      goto LABEL_88;
    }
    if ( v97 == 6 )
    {
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 40LL))(v99);
      v10 = (*(__int64 (__fastcall **)(__int64, const char *, void *, _QWORD))(*(_QWORD *)v46 + 56LL))(
              v46,
              "Domain",
              v33,
              0);
      if ( v10 < 0 )
      {
        v34 = (unsigned __int16 *)operator new(0x208u);
        if ( v34 )
        {
          v95 = v10;
          v35 = L"SetStringProperty (TS_PROP_CORE_DOMAIN) failed!";
          v92 = 507;
          goto LABEL_84;
        }
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
        v37 = L"SetStringProperty (TS_PROP_CORE_DOMAIN) failed!";
        goto LABEL_88;
      }
      v10 = CClientHTTPProxyTransport::TransformSidePropToCoreSPropSZ(this, 0xEu, "PKEncryptedPassword");
      if ( v10 < 0 )
      {
        v34 = (unsigned __int16 *)operator new(0x208u);
        if ( v34 )
        {
          v95 = v10;
          *v34 = 0;
          v92 = 510;
LABEL_147:
          v35 = L"TransformSidePropToCoreSPropSZ from AA_TRANSPORT_PROPERTY_SERVERAUTHBLOB to TS_PROP_REDIRECTION_PK_ENCRY"
                 "PTED_PASSWORD failed !";
          goto LABEL_85;
        }
        goto LABEL_148;
      }
      goto LABEL_215;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD, unsigned int *))(**((_QWORD **)this + 241) + 136LL))(
            *((_QWORD *)this + 241),
            "GatewayPassword",
            0,
            &v109);
    if ( v10 < 0 )
    {
      v34 = (unsigned __int16 *)operator new(0x208u);
      if ( v34 )
      {
        v95 = v10;
        v35 = L"GetSecureStringProperty(TS_PROP_TRANSPORT_PROXYPASSWORD) failed!";
        v92 = 521;
        goto LABEL_84;
      }
      CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
      v37 = L"GetSecureStringProperty(TS_PROP_TRANSPORT_PROXYPASSWORD) failed!";
      goto LABEL_88;
    }
    if ( !v109 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v76 = RdpX_GetActivityIdPrefix(v48, v47, v49);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids, v76);
      }
      goto LABEL_215;
    }
    v100 = 0;
    v98 = 0;
    v107 = 2 * v109;
    if ( 2 * v109 < v109 )
    {
      v10 = -2147418113;
LABEL_156:
      RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v98);
      goto LABEL_220;
    }
    v50 = LocalAlloc(0x40u, 2 * v109);
    v96 = v50;
    v53 = v50;
    if ( !v50 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v54 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v51, v52);
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids,
          v54,
          (__int64)"PWSTR");
      }
      v10 = -2147024882;
      goto LABEL_156;
    }
    v10 = (*(__int64 (__fastcall **)(_QWORD, const char *, _BYTE *, unsigned int *))(**((_QWORD **)this + 241) + 136LL))(
            *((_QWORD *)this + 241),
            "GatewayPassword",
            v50,
            &v109);
    if ( v10 < 0 )
    {
      v56 = (unsigned __int16 *)operator new(0x208u);
      v57 = v56;
      if ( v56 )
      {
        *v56 = 0;
        StringCchPrintfW(
          v56,
          0x104u,
          L"'%s' in %s at %d err=[0x%x]",
          L"GetSecureStringProperty(TS_PROP_TRANSPORT_PROXYPASSWORD) failed!",
          L"CClientHTTPProxyTransport::OnConnected",
          545,
          v10);
        CClientProxyTransport::TLDiagEvent(this, v57, v10);
        operator delete(v57);
      }
      else
      {
        CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
        CClientProxyTransport::TLDiagEvent(
          this,
          L"GetSecureStringProperty(TS_PROP_TRANSPORT_PROXYPASSWORD) failed!",
          v10);
      }
      goto LABEL_156;
    }
    v59 = RdpX_CreateObject(0, v55, 87, 124, &v98);
    if ( v59 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_173;
      }
      v61 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v58, v60);
      v62 = 19;
    }
    else
    {
      v59 = (*(__int64 (__fastcall **)(__int64, void *, HLOCAL, HLOCAL *, unsigned int *))(*(_QWORD *)v98 + 48LL))(
              v98,
              v13,
              v53,
              &hMem,
              &v110);
      if ( !v59 )
      {
        v10 = ITscAuthenticationBlob_CreateInstance(hMem, v110, &v100);
        if ( v10 >= 0 )
        {
          v70 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v99 + 40LL))(v99);
          v71 = v100;
          v10 = (*(__int64 (__fastcall **)(__int64, const char *, struct ITscAuthenticationBlob *))(*(_QWORD *)v70 + 48LL))(
                  v70,
                  "CredentialsAuthenticationBlob",
                  v100);
          if ( v10 >= 0 )
          {
            RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v98);
            if ( v71 )
              (*(void (__fastcall **)(struct ITscAuthenticationBlob *))(*(_QWORD *)v71 + 16LL))(v71);
            goto LABEL_215;
          }
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v75 = RdpX_GetActivityIdPrefix(v73, v72, v74);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              (unsigned int)WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids,
              v75,
              (__int64)"SetIUnknownProperty (TS_PROP_AUTHENTICATION_BLOB) failed!",
              v10);
          }
          RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v98);
          if ( !v71 )
            goto LABEL_220;
          v69 = *(_QWORD *)v71;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v68 = RdpX_GetActivityIdPrefix(v66, v65, v67);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              (unsigned int)WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids,
              v68,
              (__int64)"ITscAuthenticationBlob_CreateInstance failed!",
              v10);
          }
          RdpXSPtr<RdpXTapVcCallbackItem>::SafeRelease(&v98);
          if ( !v100 )
            goto LABEL_220;
          v69 = *(_QWORD *)v100;
        }
        (*(void (**)(void))(v69 + 16))();
        goto LABEL_220;
      }
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_173;
      }
      v61 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v63, v64);
      v62 = 20;
    }
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v62, WPP_c9ead2e8f0ca31f6112399792691be3b_Traceguids, v61, v59);
LABEL_173:
    v10 = MapXResultToHR(v59);
    goto LABEL_156;
  }
  v34 = (unsigned __int16 *)operator new(0x208u);
  if ( !v34 )
  {
LABEL_87:
    CClientProxyTransport::TLDiagEvent(this, L"Cannot allocate memory", v10);
    v37 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !";
LABEL_88:
    v38 = v10;
    goto LABEL_89;
  }
  v95 = v10;
  v92 = 388;
LABEL_83:
  v35 = L"GetSideTransportProperty for AA_TRANSPORT_PROPERTY_SERVERNAME failed !";
LABEL_84:
  *v34 = 0;
LABEL_85:
  StringCchPrintfW(
    v34,
    0x104u,
    L"'%s' in %s at %d err=[0x%x]",
    v35,
    L"CClientHTTPProxyTransport::OnConnected",
    v92,
    v95);
  CClientProxyTransport::TLDiagEvent(this, v34, v10);
  v36 = v34;
LABEL_86:
  operator delete(v36);
LABEL_220:
  LocalFree(v33);
LABEL_221:
  if ( v13 )
    LocalFree(v13);
  v1 = v107;
  v3 = v96;
LABEL_224:
  v84 = hMem;
  if ( hMem )
  {
    v85 = v110;
    if ( v110 )
    {
      do
      {
        *v84++ = 0;
        --v85;
      }
      while ( v85 );
      v84 = hMem;
    }
    LocalFree(v84);
  }
  if ( v3 )
  {
    v86 = v1;
    v87 = v3;
    if ( v1 )
    {
      do
      {
        *v87++ = 0;
        --v86;
      }
      while ( v86 );
    }
    LocalFree(v3);
  }
  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v105);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v99);
  return (unsigned int)v10;
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
