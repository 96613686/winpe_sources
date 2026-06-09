# CRDPENCONTCPListener::ConfigureListeners(ulong,ulong,int,int)

- ea: `0x14006a970`
- end: `0x14006b40d`
- name: `?ConfigureListeners@CRDPENCONTCPListener@@UEAAJKKHH@Z`
- size: `2717`
- prototype: `int(CRDPENCONTCPListener *__hidden this, unsigned int, unsigned int, int, int)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1400019e8`
- `0x140001b00`
- `0x140001c24`
- `0x140001e98`
- `0x140003b08`
- `0x140003b2c`
- `0x14000b7d8`
- `0x14000c7f8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14000dcac`
- `0x14003e0b4`
- `0x14005b6d8`
- `0x14005bc74`
- `0x14006a970`
- `0x14006dbe8`
- `0x14006dd4c`
- `0x140075e14`
- `0x140075e70`
- `0x14007634c`
- `0x140077208`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x14006a9e1`
- `OLEAUT32!__imp_VariantInit` at `0x14006a9eb`
- `OLEAUT32!__imp_VariantInit` at `0x14006a9e1`
- `OLEAUT32!__imp_VariantInit` at `0x14006a9eb`
- `OLEAUT32!__imp_VariantClear` at `0x14006b3ca`
- `OLEAUT32!__imp_VariantClear` at `0x14006b3d4`
- `OLEAUT32!__imp_VariantClear` at `0x14006b3ca`
- `OLEAUT32!__imp_VariantClear` at `0x14006b3d4`
- `WS2_32!__imp_htons` at `0x14006afd6`
- `WS2_32!__imp_htons` at `0x14006afd6`

## string_xrefs

- `0x14006ae7a`: `ConfigureListeners`
- `0x14006aef3`: `ConfigureListeners`
- `0x14006b0bb`: `ConfigureListeners`
- `0x14006b134`: `ConfigureListeners`
- `0x14006b270`: `ConfigureListeners`
- `0x14006b286`: `No interface found for protocol %d `
- `0x14006abb8`: `Failed to add the port to the temp list`
- `0x14006b212`: `Failed to add the port to the temp list`
- `0x14006b17c`: `Failed to create a listener on protocol type %d`

## pseudocode

```c
__int64 __fastcall CRDPENCONTCPListener::ConfigureListeners(
        CRDPENCONTCPListener *this,
        unsigned int a2,
        int a3,
        int a4,
        int a5)
{
  int v6; // r12d
  __int64 v7; // rbx
  CRDPENCONIPHelper *v10; // rax
  CRDPENCONIPHelper *v11; // rdi
  int v12; // r14d
  unsigned int v13; // eax
  void *v14; // r8
  __int64 v15; // rcx
  unsigned int v16; // eax
  int v17; // eax
  int v18; // ebx
  __int64 v19; // rax
  unsigned int v20; // eax
  int v21; // edx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  unsigned int v25; // eax
  unsigned int v26; // eax
  _DWORD *v27; // rax
  _DWORD *v28; // rax
  struct _SOCKET_ADDRESS *Next; // rcx
  int v30; // r8d
  int v31; // r9d
  struct sockaddr *lpSockaddr; // r8
  u_short v33; // ax
  int v34; // edx
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  __int64 v38; // rcx
  struct CRDPENCONPort *v39; // rbx
  CRDPENCONTCPListener *v40; // rcx
  CRDPENCNATHelper *v41; // rcx
  int v42; // eax
  int v43; // r8d
  int v44; // r9d
  struct sockaddr *v45; // rax
  unsigned int v46; // eax
  void *v47; // rcx
  void *v48; // rcx
  unsigned int v49; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v52; // [rsp+28h] [rbp-D8h]
  struct CRDPENCONPort *v53; // [rsp+60h] [rbp-A0h] BYREF
  struct CRDPENCONPort *v54; // [rsp+68h] [rbp-98h] BYREF
  int v55; // [rsp+70h] [rbp-90h] BYREF
  struct sockaddr *v56; // [rsp+78h] [rbp-88h] BYREF
  int v57; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+84h] [rbp-7Ch] BYREF
  const char *v59; // [rsp+88h] [rbp-78h] BYREF
  const char *v60; // [rsp+90h] [rbp-70h] BYREF
  const char *v61; // [rsp+98h] [rbp-68h] BYREF
  const char *v62; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-58h] BYREF
  int v64; // [rsp+B0h] [rbp-50h]
  int v65; // [rsp+B4h] [rbp-4Ch] BYREF
  const char *v66; // [rsp+B8h] [rbp-48h] BYREF
  addrinfo v67; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v68; // [rsp+F0h] [rbp-10h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+8h] BYREF
  int v70; // [rsp+120h] [rbp+20h] BYREF
  GUID v71; // [rsp+124h] [rbp+24h]
  __int128 v72; // [rsp+134h] [rbp+34h]

  v64 = a4;
  v57 = a3;
  LODWORD(v54) = a2;
  v6 = 0;
  v7 = 0;
  v63 = 0;
  memset(&v67, 0, sizeof(v67));
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v68, 0, sizeof(v68));
  VariantInit(&pvarg);
  VariantInit(&v68);
  if ( *((_QWORD *)this + 5) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        &WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147418113);
    }
    v12 = -2147418113;
  }
  else
  {
    LODWORD(v62) = *((_DWORD *)this + 19);
    v10 = (CRDPENCONIPHelper *)operator new(0x18u);
    v11 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = 0;
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = 0;
      CRDPENCONTCPListener::SetETWActivityID((CRDPENCONTCPListener *)((char *)this - 48));
      v53 = (CRDPENCONTCPListener *)((char *)this + 112);
      CTSCriticalSection::Lock((CRDPENCONTCPListener *)((char *)this + 112));
      if ( (*((_BYTE *)this - 20) & 4) != 0 )
      {
        v12 = -2147467260;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
            v13,
            (__int64)"Listener is terminated",
            -2147467260);
        }
        CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v53);
        goto LABEL_88;
      }
      if ( *((_QWORD *)this + 3) )
      {
        TCntPtr<IXMLDOMNodeList>::SafeRelease(&v63);
        v7 = *((_QWORD *)this + 3);
        v63 = v7;
        TCntPtr<ITSAsyncCallback>::SafeAddRef(&v63);
      }
      CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v53);
      if ( a2 == 34 )
      {
        v14 = (void *)*((_QWORD *)this + 21);
        v70 = 34;
        v67.ai_family = 34;
        v54 = 0;
        v67.ai_socktype = 1;
        v71 = HV_GUID_PARENT;
        v67.ai_protocol = 1;
        v72 = RDP_HVSOCKET_CLIENT_SERVICE_ID;
        v67.ai_canonname = 0;
        v67.ai_addrlen = 36;
        v67.ai_addr = (struct sockaddr *)&v70;
        v67.ai_next = 0;
        v12 = CRDPENCONPort::CreateInstance(&v67, a4, v14, &v54);
        if ( v12 >= 0 )
        {
          v15 = *((_QWORD *)this + 23);
          if ( v15 )
            (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v15 + 24LL))(v15, L"HVSOCKET", 0);
          v12 = (*(__int64 (__fastcall **)(char *, struct CRDPENCONPort *))(*((_QWORD *)this + 7) + 8LL))(
                  (char *)this + 56,
                  v54);
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                48,
                (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
                v16,
                (__int64)"Failed to add the port to the temp list",
                v12);
            }
            TCntPtr<CTSCoreEventSink>::SafeRelease(&v54);
            goto LABEL_88;
          }
          v6 = 1;
        }
        TCntPtr<CTSCoreEventSink>::SafeRelease(&v54);
        v17 = 0;
        if ( !v6 )
          v17 = v12;
        v12 = v17;
LABEL_25:
        if ( v12 < 0 )
        {
LABEL_26:
          if ( v6 )
          {
            v18 = (int)v62;
            do
            {
              v19 = *((_QWORD *)this + 7);
              v53 = 0;
              (*(void (__fastcall **)(char *, _QWORD, struct CRDPENCONPort **))(v19 + 48))(
                (char *)this + 56,
                (unsigned int)(v6 + v18 - 1),
                &v53);
              (*(void (__fastcall **)(char *, struct CRDPENCONPort *))(*((_QWORD *)this + 7) + 16LL))(
                (char *)this + 56,
                v53);
              TCntPtr<CTSCoreEventSink>::SafeRelease(&v53);
              --v6;
            }
            while ( v6 );
          }
        }
        goto LABEL_88;
      }
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, VARIANTARG *))(*(_QWORD *)v7 + 24LL))(
             v7,
             L"BindAddress",
             &pvarg) >= 0 )
      {
        v12 = CRDPENCONIPHelper::Initialize(v11, a2, a5, pvarg.bstrVal);
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_88;
          }
          v20 = RdpWppGetCurrentThreadActivityIdPrefix();
          v21 = 50;
          goto LABEL_41;
        }
      }
      else
      {
        v12 = CRDPENCONIPHelper::Initialize(v11, a2, a5, 0);
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_88;
          }
          v20 = RdpWppGetCurrentThreadActivityIdPrefix();
          v21 = 49;
LABEL_41:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v21,
            (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
            v20,
            (__int64)"Failed to initialize the ip helper",
            v12);
LABEL_88:
          v47 = (void *)*((_QWORD *)v11 + 1);
          if ( v47 )
          {
            operator delete(v47);
            *((_QWORD *)v11 + 1) = 0;
          }
          v48 = (void *)*((_QWORD *)v11 + 2);
          if ( v48 )
          {
            operator delete(v48);
            *((_QWORD *)v11 + 2) = 0;
          }
          *(_QWORD *)v11 = 0;
          operator delete(v11);
          goto LABEL_103;
        }
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 3) + 24LL))(
              *((_QWORD *)this + 3),
              L"LanAdapter",
              &v68);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v26 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids, v26);
        }
        v68.lVal = -1;
        v68.vt = 19;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v25 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          &WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
          v25,
          v68.lVal);
      }
      v27 = (_DWORD *)*((_QWORD *)v11 + 2);
      *(_QWORD *)v11 = 0;
      if ( v27 && *v27 || (v28 = (_DWORD *)*((_QWORD *)v11 + 1)) != 0 && *v28 )
      {
        Next = CRDPENCONIPHelper::GetNext(v11);
        if ( Next )
        {
          do
          {
            lpSockaddr = Next->lpSockaddr;
            v56 = lpSockaddr;
            if ( lpSockaddr->sa_family == 2 || lpSockaddr->sa_family == 23 )
            {
              v67.ai_family = lpSockaddr->sa_family;
              v67.ai_addrlen = Next->iSockaddrLength;
              v53 = 0;
              v67.ai_socktype = 1;
              v67.ai_protocol = 6;
              v67.ai_canonname = 0;
              v67.ai_addr = lpSockaddr;
              v67.ai_next = 0;
              v33 = htons(v57);
              v34 = v64;
              *(_WORD *)v56->sa_data = v33;
              v12 = CRDPENCONPort::CreateInstance(&v67, v34, *((void **)this + 21), &v53);
              if ( v12 < 0 )
              {
                if ( (unsigned int)dword_140152118 > 2 )
                {
                  v45 = v56;
                  v60 = "ConfigureListeners";
                  LODWORD(v56) = 976;
                  LODWORD(v61) = -2147467259;
                  LOWORD(v55) = v45->sa_family;
                  v59 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
                  v66 = "Failed to create a listener on protocol type %d";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
                    v35,
                    (unsigned int)&byte_14013FDC7,
                    v36,
                    v37,
                    (__int64)&v66,
                    (__int64)&v61,
                    (__int64)&v59,
                    (__int64)&v56,
                    (__int64)&v60,
                    (__int64)&v55);
                }
              }
              else
              {
                v38 = *((_QWORD *)this + 23);
                if ( v38 )
                  (*(void (__fastcall **)(__int64, const OLECHAR *, _QWORD))(*(_QWORD *)v38 + 24LL))(
                    v38,
                    L"TCP",
                    (unsigned __int16)v57);
                v39 = v53;
                v12 = (*(__int64 (__fastcall **)(char *, struct CRDPENCONPort *))(*((_QWORD *)this + 7) + 8LL))(
                        (char *)this + 56,
                        v53);
                if ( v12 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v46 = RdpWppGetCurrentThreadActivityIdPrefix();
                    LODWORD(v52) = v12;
                    WPP_SF_DsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      53,
                      (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
                      v46,
                      (__int64)"Failed to add the port to the temp list",
                      v52);
                  }
                  TCntPtr<CTSCoreEventSink>::SafeRelease(&v53);
                  goto LABEL_26;
                }
                CRDPENCONTCPListener::RestrictListenerAdapter(
                  v40,
                  *((_QWORD *)v39 + 8),
                  v56->sa_family == 23,
                  v68.cyVal.Lo);
                if ( v56->sa_family == 2 )
                {
                  v41 = (CRDPENCNATHelper *)*((_QWORD *)this + 13);
                  if ( v41 )
                  {
                    v42 = CRDPENCNATHelper::AddPortMapping(v41, *((unsigned __int16 **)v39 + 9), *((_DWORD *)v39 + 13));
                    if ( v42 < 0 && (unsigned int)dword_140152118 > 2 )
                    {
                      LODWORD(v56) = v42;
                      v65 = *((_DWORD *)v39 + 13);
                      v60 = "ConfigureListeners";
                      v59 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
                      v61 = "Failed to add a NAT mapping for port %d (0x%08x)";
                      v58 = 971;
                      LODWORD(v54) = -2147467259;
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                        dword_140152118,
                        (unsigned int)word_14013FE22,
                        v43,
                        v44,
                        (__int64)&v61,
                        (__int64)&v54,
                        (__int64)&v59,
                        (__int64)&v58,
                        (__int64)&v60,
                        (__int64)&v65,
                        (__int64)&v56);
                    }
                  }
                }
                ++v6;
              }
              TCntPtr<CTSCoreEventSink>::SafeRelease(&v53);
            }
            else if ( (unsigned int)dword_140152118 > 2 )
            {
              LOWORD(v55) = lpSockaddr->sa_family;
              v60 = "Ignoring unknown address family %d";
              v59 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
              v53 = (struct CRDPENCONPort *)"ConfigureListeners";
              LODWORD(v61) = 979;
              LODWORD(v56) = -2147467259;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>>(
                (_DWORD)Next,
                (unsigned int)&word_14013FECE,
                (_DWORD)lpSockaddr,
                v31,
                (__int64)&v60,
                (__int64)&v56,
                (__int64)&v59,
                (__int64)&v61,
                (__int64)&v53,
                (__int64)&v55);
            }
            Next = CRDPENCONIPHelper::GetNext(v11);
          }
          while ( Next );
          if ( !v6 )
            goto LABEL_25;
          v12 = 0;
        }
        else
        {
          if ( (unsigned int)dword_140152118 > 2 )
          {
            v57 = 909;
            v53 = (struct CRDPENCONPort *)"ConfigureListeners";
            v55 = -2147467259;
            v62 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
            v54 = (struct CRDPENCONPort *)"Cant get a connectable IP address.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              0,
              (unsigned int)byte_14013FE89,
              v30,
              v31,
              (__int64)&v54,
              (__int64)&v55,
              (__int64)&v62,
              (__int64)&v57,
              (__int64)&v53);
          }
          v12 = -2147014846;
        }
      }
      else
      {
        if ( (unsigned int)dword_140152118 > 2 )
        {
          LODWORD(v62) = (_DWORD)v54;
          v66 = "ConfigureListeners";
          v60 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpenctcplsncon.cpp";
          v59 = "No interface found for protocol %d ";
          LODWORD(v54) = 901;
          v58 = -2147467259;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)byte_14013FF29,
            v23,
            v24,
            (__int64)&v59,
            (__int64)&v58,
            (__int64)&v60,
            (__int64)&v54,
            (__int64)&v66,
            (__int64)&v62);
        }
        v12 = -2147014853;
      }
      goto LABEL_88;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v49 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        (unsigned int)&WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids,
        v49,
        (__int64)"\"CRDPENCONIPHelper\"");
    }
    v12 = -2147024882;
  }
LABEL_103:
  VariantClear(&pvarg);
  VariantClear(&v68);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v63);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14006a970  mov     [rsp-8+arg_18], rbx
0x14006a975  push    rbp
0x14006a976  push    rsi
0x14006a977  push    rdi
0x14006a978  push    r12
0x14006a97a  push    r13
0x14006a97c  push    r14
0x14006a97e  push    r15
0x14006a980  lea     rbp, [rsp-50h]
0x14006a985  sub     rsp, 150h
0x14006a98c  mov     rax, cs:__security_cookie
0x14006a993  xor     rax, rsp
0x14006a996  mov     [rbp+80h+var_38], rax
0x14006a99a  xorps   xmm0, xmm0
0x14006a99d  mov     [rbp+80h+var_D0], r9d
0x14006a9a1  xor     eax, eax
0x14006a9a3  mov     [rbp+80h+var_100], r8d
0x14006a9a7  mov     r13, rcx
0x14006a9aa  mov     dword ptr [rsp+180h+var_118], edx
0x14006a9ae  xorps   xmm1, xmm1
0x14006a9b1  mov     qword ptr [rbp+80h+pvarg+10h], rax
0x14006a9b5  xor     r12d, r12d
0x14006a9b8  mov     qword ptr [rbp+80h+var_90+10h], rax
0x14006a9bc  mov     ebx, r12d
0x14006a9bf  lea     rcx, [rbp+80h+pvarg]; pvarg
0x14006a9c3  mov     [rbp+80h+var_D8], rbx
0x14006a9c7  mov     r15d, r9d
0x14006a9ca  mov     r14d, edx
0x14006a9cd  movups  xmmword ptr [rbp+80h+var_C0.ai_flags], xmm0
0x14006a9d1  movups  xmmword ptr [rbp+80h+var_C0.ai_addrlen], xmm0
0x14006a9d5  movups  xmmword ptr [rbp+80h+var_C0.ai_addr], xmm0
0x14006a9d9  movups  xmmword ptr [rbp+80h+pvarg], xmm0
0x14006a9dd  movups  xmmword ptr [rbp+80h+var_90], xmm1
0x14006a9e1  call    cs:__imp_VariantInit
0x14006a9e7  lea     rcx, [rbp+80h+var_90]; pvarg
0x14006a9eb  call    cs:__imp_VariantInit
0x14006a9f1  cmp     [r13+28h], r12
0x14006a9f5  jnz     loc_14006B372
0x14006a9fb  mov     eax, [r13+4Ch]
0x14006a9ff  lea     ecx, [r12+18h]; Size
0x14006aa04  mov     dword ptr [rbp+80h+var_E0], eax
0x14006aa07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006aa0c  mov     rdi, rax
0x14006aa0f  test    rax, rax
0x14006aa12  jz      loc_14006B318
0x14006aa18  lea     rcx, [r13-30h]; this
0x14006aa1c  mov     [rax], r12
0x14006aa1f  mov     [rax+8], r12
0x14006aa23  mov     [rax+10h], r12
0x14006aa27  call    ?SetETWActivityID@CRDPENCONTCPListener@@IEAAJXZ; CRDPENCONTCPListener::SetETWActivityID(void)
0x14006aa2c  lea     rcx, [r13+70h]; this
0x14006aa30  mov     [rsp+180h+var_120], rcx
0x14006aa35  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x14006aa3a  test    byte ptr [r13-14h], 4
0x14006aa3f  jz      short loc_14006AAB0
0x14006aa41  mov     r14d, 80004004h
0x14006aa47  mov     rax, cs:WPP_GLOBAL_Control
0x14006aa4e  lea     r15, WPP_GLOBAL_Control
0x14006aa55  cmp     rax, r15
0x14006aa58  jz      short loc_14006AAA1
0x14006aa5a  test    byte ptr [rax+1Ch], 8
0x14006aa5e  jz      short loc_14006AAA1
0x14006aa60  lea     esi, [r12+2]
0x14006aa65  cmp     [rax+19h], sil
0x14006aa69  jb      short loc_14006AAA1
0x14006aa6b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006aa70  lea     rcx, aListenerIsTerm; "Listener is terminated"
0x14006aa77  mov     dword ptr [rsp+180h+var_158], 80004004h
0x14006aa7f  mov     [rsp+180h+var_160], rcx
0x14006aa84  lea     edx, [rsi+2Dh]
0x14006aa87  mov     rcx, cs:WPP_GLOBAL_Control
0x14006aa8e  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006aa95  mov     r9d, eax
0x14006aa98  mov     rcx, [rcx+10h]
0x14006aa9c  call    WPP_SF_DsD
0x14006aaa1  lea     rcx, [rsp+180h+var_120]; this
0x14006aaa6  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14006aaab  jmp     loc_14006B2E2
0x14006aab0  xor     esi, esi
0x14006aab2  cmp     [r13+18h], rsi
0x14006aab6  jz      short loc_14006AAD2
0x14006aab8  lea     rcx, [rbp+80h+var_D8]
0x14006aabc  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x14006aac1  mov     rbx, [r13+18h]
0x14006aac5  lea     rcx, [rbp+80h+var_D8]
0x14006aac9  mov     [rbp+80h+var_D8], rbx
0x14006aacd  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x14006aad2  lea     rcx, [rsp+180h+var_120]; this
0x14006aad7  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x14006aadc  mov     ecx, 22h ; '"'
0x14006aae1  cmp     r14d, ecx
0x14006aae4  jnz     loc_14006AC6F
0x14006aaea  movups  xmm0, xmmword ptr cs:HV_GUID_PARENT.Data1
0x14006aaf1  mov     r8, [r13+0A8h]; void *
0x14006aaf8  lea     ebx, [rcx-21h]
0x14006aafb  movups  xmm1, cs:RDP_HVSOCKET_CLIENT_SERVICE_ID
0x14006ab02  mov     [rbp+80h+var_60], ecx
0x14006ab05  lea     rax, [rbp+80h+var_60]
0x14006ab09  mov     [rbp+80h+var_C0.ai_family], ecx
0x14006ab0c  lea     r9, [rsp+180h+var_118]; struct CRDPENCONPort **
0x14006ab11  mov     edx, r15d; int
0x14006ab14  mov     [rsp+180h+var_118], rsi
0x14006ab19  lea     rcx, [rbp+80h+var_C0]; struct addrinfo *
0x14006ab1d  mov     [rbp+80h+var_C0.ai_socktype], ebx
0x14006ab20  movdqu  [rbp+80h+var_5C], xmm0
0x14006ab25  mov     [rbp+80h+var_C0.ai_protocol], ebx
0x14006ab28  movdqu  [rbp+80h+var_4C], xmm1
0x14006ab2d  mov     [rbp+80h+var_C0.ai_canonname], rsi
0x14006ab31  mov     [rbp+80h+var_C0.ai_addrlen], 24h ; '$'
0x14006ab39  mov     [rbp+80h+var_C0.ai_addr], rax
0x14006ab3d  mov     [rbp+80h+var_C0.ai_next], rsi
0x14006ab41  call    ?CreateInstance@CRDPENCONPort@@SAJPEAUaddrinfo@@HPEAXPEAPEAV1@@Z; CRDPENCONPort::CreateInstance(addrinfo *,int,void *,CRDPENCONPort * *)
0x14006ab46  mov     r14d, eax
0x14006ab49  test    eax, eax
0x14006ab4b  js      loc_14006ABF8
0x14006ab51  mov     rcx, [r13+0B8h]
0x14006ab58  test    rcx, rcx
0x14006ab5b  jz      short loc_14006AB73
0x14006ab5d  mov     rax, [rcx]
0x14006ab60  lea     rdx, aHvsocket; "HVSOCKET"
0x14006ab67  xor     r8d, r8d
0x14006ab6a  mov     rax, [rax+18h]
0x14006ab6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ab73  mov     rdx, [rsp+180h+var_118]
0x14006ab78  lea     rcx, [r13+38h]
0x14006ab7c  mov     rax, [rcx]
0x14006ab7f  mov     rax, [rax+8]
0x14006ab83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ab88  mov     r14d, eax
0x14006ab8b  test    eax, eax
0x14006ab8d  jns     short loc_14006ABF5
0x14006ab8f  mov     rax, cs:WPP_GLOBAL_Control
0x14006ab96  lea     r15, WPP_GLOBAL_Control
0x14006ab9d  cmp     rax, r15
0x14006aba0  jz      short loc_14006ABE6
0x14006aba2  test    byte ptr [rax+1Ch], 8
0x14006aba6  jz      short loc_14006ABE6
0x14006aba8  mov     esi, 2
0x14006abad  cmp     [rax+19h], sil
0x14006abb1  jb      short loc_14006ABE6
0x14006abb3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006abb8  lea     rcx, aFailedToAddThe_2; "Failed to add the port to the temp list"
0x14006abbf  mov     dword ptr [rsp+180h+var_158], r14d
0x14006abc4  mov     [rsp+180h+var_160], rcx
0x14006abc9  lea     edx, [rsi+2Eh]
0x14006abcc  mov     rcx, cs:WPP_GLOBAL_Control
0x14006abd3  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006abda  mov     r9d, eax
0x14006abdd  mov     rcx, [rcx+10h]
0x14006abe1  call    WPP_SF_DsD
0x14006abe6  lea     rcx, [rsp+180h+var_118]
0x14006abeb  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14006abf0  jmp     loc_14006B2E2
0x14006abf5  mov     r12d, ebx
0x14006abf8  lea     rcx, [rsp+180h+var_118]
0x14006abfd  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14006ac02  test    r12d, r12d
0x14006ac05  mov     eax, esi
0x14006ac07  cmovz   eax, r14d
0x14006ac0b  mov     r14d, eax
0x14006ac0e  test    r14d, r14d
0x14006ac11  jns     loc_14006B2E2
0x14006ac17  test    r12d, r12d
0x14006ac1a  jz      loc_14006B2E2
0x14006ac20  mov     ebx, dword ptr [rbp+80h+var_E0]
0x14006ac23  mov     rax, [r13+38h]
0x14006ac27  lea     edx, [rbx-1]
0x14006ac2a  add     edx, r12d
0x14006ac2d  mov     [rsp+180h+var_120], rsi
0x14006ac32  lea     r8, [rsp+180h+var_120]
0x14006ac37  lea     rcx, [r13+38h]
0x14006ac3b  mov     rax, [rax+30h]
0x14006ac3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ac44  mov     rax, [r13+38h]
0x14006ac48  lea     rcx, [r13+38h]
0x14006ac4c  mov     rdx, [rsp+180h+var_120]
0x14006ac51  mov     rax, [rax+10h]
0x14006ac55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ac5a  lea     rcx, [rsp+180h+var_120]
0x14006ac5f  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSink@@@@AEAAXXZ; TCntPtr<CTSCoreEventSink>::SafeRelease(void)
0x14006ac64  add     r12d, 0FFFFFFFFh
0x14006ac68  jnz     short loc_14006AC23
0x14006ac6a  jmp     loc_14006B2E2
0x14006ac6f  mov     rax, [rbx]
0x14006ac72  lea     r8, [rbp+80h+pvarg]
0x14006ac76  lea     rdx, aBindaddress; "BindAddress"
0x14006ac7d  mov     rcx, rbx
0x14006ac80  mov     rax, [rax+18h]
0x14006ac84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ac89  mov     r8d, [rbp+80h+arg_20]; int
0x14006ac90  mov     edx, r14d; unsigned int
0x14006ac93  mov     rcx, rdi; this
0x14006ac96  test    eax, eax
0x14006ac98  jns     short loc_14006ACE7
0x14006ac9a  xor     r9d, r9d; unsigned __int16 *
0x14006ac9d  call    ?Initialize@CRDPENCONIPHelper@@QEAAJKHPEAG@Z; CRDPENCONIPHelper::Initialize(ulong,int,ushort *)
0x14006aca2  mov     r14d, eax
0x14006aca5  test    eax, eax
0x14006aca7  jns     loc_14006AD5F
0x14006acad  mov     rax, cs:WPP_GLOBAL_Control
0x14006acb4  lea     r15, WPP_GLOBAL_Control
0x14006acbb  cmp     rax, r15
0x14006acbe  jz      loc_14006B2E2
0x14006acc4  test    byte ptr [rax+1Ch], 8
0x14006acc8  jz      loc_14006B2E2
0x14006acce  mov     esi, 2
0x14006acd3  cmp     [rax+19h], sil
0x14006acd7  jb      loc_14006B2E2
0x14006acdd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006ace2  lea     edx, [rsi+2Fh]
0x14006ace5  jmp     short loc_14006AD2F
0x14006ace7  mov     r9, qword ptr [rbp+80h+pvarg+8]; unsigned __int16 *
0x14006aceb  call    ?Initialize@CRDPENCONIPHelper@@QEAAJKHPEAG@Z; CRDPENCONIPHelper::Initialize(ulong,int,ushort *)
0x14006acf0  mov     r14d, eax
0x14006acf3  test    eax, eax
0x14006acf5  jns     short loc_14006AD5F
0x14006acf7  mov     rax, cs:WPP_GLOBAL_Control
0x14006acfe  lea     r15, WPP_GLOBAL_Control
0x14006ad05  cmp     rax, r15
0x14006ad08  jz      loc_14006B2E2
0x14006ad0e  test    byte ptr [rax+1Ch], 8
0x14006ad12  jz      loc_14006B2E2
0x14006ad18  mov     esi, 2
0x14006ad1d  cmp     [rax+19h], sil
0x14006ad21  jb      loc_14006B2E2
0x14006ad27  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006ad2c  lea     edx, [rsi+30h]
0x14006ad2f  lea     rcx, aFailedToInitia_12; "Failed to initialize the ip helper"
0x14006ad36  mov     dword ptr [rsp+180h+var_158], r14d
0x14006ad3b  mov     [rsp+180h+var_160], rcx
0x14006ad40  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006ad47  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ad4e  mov     r9d, eax
0x14006ad51  mov     rcx, [rcx+10h]
0x14006ad55  call    WPP_SF_DsD
0x14006ad5a  jmp     loc_14006B2E2
0x14006ad5f  mov     rcx, [r13+18h]
0x14006ad63  lea     r8, [rbp+80h+var_90]
0x14006ad67  lea     rdx, aLanadapter; "LanAdapter"
0x14006ad6e  mov     rax, [rcx]
0x14006ad71  mov     rax, [rax+18h]
0x14006ad75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006ad7a  mov     r14d, eax
0x14006ad7d  test    eax, eax
0x14006ad7f  js      short loc_14006ADDC
0x14006ad81  mov     rax, cs:WPP_GLOBAL_Control
0x14006ad88  lea     r15, WPP_GLOBAL_Control
0x14006ad8f  cmp     rax, r15
0x14006ad92  jz      loc_14006AE32
0x14006ad98  test    dword ptr [rax+1Ch], 800h
0x14006ad9f  jz      loc_14006AE32
0x14006ada5  cmp     byte ptr [rax+19h], 4
0x14006ada9  jb      loc_14006AE32
0x14006adaf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006adb4  mov     ecx, dword ptr [rbp+80h+var_90+8]
0x14006adb7  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006adbe  mov     dword ptr [rsp+180h+var_160], ecx
0x14006adc2  mov     edx, 33h ; '3'
0x14006adc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14006adce  mov     r9d, eax
0x14006add1  mov     rcx, [rcx+10h]
0x14006add5  call    WPP_SF_Dd
0x14006adda  jmp     short loc_14006AE32
0x14006addc  mov     rax, cs:WPP_GLOBAL_Control
0x14006ade3  lea     r15, WPP_GLOBAL_Control
0x14006adea  cmp     rax, r15
0x14006aded  jz      short loc_14006AE22
0x14006adef  test    dword ptr [rax+1Ch], 800h
0x14006adf6  jz      short loc_14006AE22
0x14006adf8  cmp     byte ptr [rax+19h], 4
0x14006adfc  jb      short loc_14006AE22
0x14006adfe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14006ae03  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ae0a  lea     r8, WPP_c1b825be4b33356d276804fb7e600bc9_Traceguids
0x14006ae11  mov     edx, 34h ; '4'
0x14006ae16  mov     r9d, eax
0x14006ae19  mov     rcx, [rcx+10h]
0x14006ae1d  call    WPP_SF_d
0x14006ae22  mov     eax, 13h
0x14006ae27  mov     dword ptr [rbp+80h+var_90+8], 0FFFFFFFFh
0x14006ae2e  mov     word ptr [rbp+80h+var_90], ax
0x14006ae32  mov     rax, [rdi+10h]
0x14006ae36  mov     [rdi], rsi
0x14006ae39  test    rax, rax
0x14006ae3c  jz      short loc_14006AE42
0x14006ae3e  cmp     [rax], esi
0x14006ae40  jnz     short loc_14006AE57
0x14006ae42  mov     rax, [rdi+8]
0x14006ae46  test    rax, rax
0x14006ae49  jz      loc_14006B253
0x14006ae4f  cmp     [rax], esi
0x14006ae51  jz      loc_14006B253
0x14006ae57  mov     rcx, rdi; this
0x14006ae5a  call    ?GetNext@CRDPENCONIPHelper@@QEAAPEAU_SOCKET_ADDRESS@@XZ; CRDPENCONIPHelper::GetNext(void)
0x14006ae5f  mov     rcx, rax
0x14006ae62  mov     esi, 2
0x14006ae67  test    rax, rax
0x14006ae6a  jnz     loc_14006AEF3
0x14006ae70  mov     eax, cs:dword_140152118
0x14006ae76  cmp     eax, esi
  ... truncated ...
```
