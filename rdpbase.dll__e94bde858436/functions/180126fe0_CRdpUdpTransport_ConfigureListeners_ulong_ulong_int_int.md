# CRdpUdpTransport::ConfigureListeners(ulong,ulong,int,int)

- ea: `0x180126fe0`
- end: `0x180127917`
- name: `?ConfigureListeners@CRdpUdpTransport@@UEAAJKKHH@Z`
- size: `2359`
- prototype: `int(CRdpUdpTransport *__hidden this, unsigned int, unsigned int, int, int)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180002550`
- `0x180004970`
- `0x180004a94`
- `0x180005090`
- `0x180019a80`
- `0x1800787d4`
- `0x1800e9c80`
- `0x1800e9ce0`
- `0x1800e9f30`
- `0x1800ff018`
- `0x180126ba0`
- `0x180126fe0`
- `0x180133dec`
- `0x180144b50`
- `0x180145320`
- `0x180162010`

## import_xrefs

- `WS2_32!__imp_htons` at `0x180127589`
- `WS2_32!__imp_htons` at `0x180127589`
- `OLEAUT32!__imp_VariantInit` at `0x180127034`
- `OLEAUT32!__imp_VariantInit` at `0x18012703e`
- `OLEAUT32!__imp_VariantInit` at `0x180127048`
- `OLEAUT32!__imp_VariantInit` at `0x180127034`
- `OLEAUT32!__imp_VariantInit` at `0x18012703e`
- `OLEAUT32!__imp_VariantInit` at `0x180127048`
- `OLEAUT32!__imp_VariantClear` at `0x1801278e0`
- `OLEAUT32!__imp_VariantClear` at `0x1801278ea`
- `OLEAUT32!__imp_VariantClear` at `0x1801278f4`
- `OLEAUT32!__imp_VariantClear` at `0x1801278e0`
- `OLEAUT32!__imp_VariantClear` at `0x1801278ea`
- `OLEAUT32!__imp_VariantClear` at `0x1801278f4`

## string_xrefs

- `0x180127120`: `ConfigureListeners`
- `0x1801271c3`: `ConfigureListeners`
- `0x1801272d9`: `ConfigureListeners`
- `0x18012787d`: `ConfigureListeners`
- `0x180127064`: `RDPUDPTransport::ConfigureListener called`
- `0x1801272f8`: `Udp:SxSPortRedirectorPath`
- `0x180127320`: `Failed to get CONN_PROPERTY_UDP_SXS_PORT_REDIRECTOR_PATH property`
- `0x1801273ea`: `No interface found for protocol`
- `0x1801275fb`: `Port redirector listener created`
- `0x1801276a5`: `Failed to create CRdpUdpPortRedirectorEndpoint`
- `0x1801277a5`: `Failed to create CRdpUdpLocalEndpoint`

## pseudocode

```c
__int64 __fastcall CRdpUdpTransport::ConfigureListeners(
        CRdpUdpTransport *this,
        unsigned int a2,
        int a3,
        __int64 a4,
        int a5)
{
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  CRDPENCONIPHelper *v11; // rax
  CRDPENCONIPHelper *v12; // r14
  unsigned int v13; // edx
  int v14; // edi
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // ecx
  struct _SOCKET_ADDRESS *Next; // rbx
  int v31; // r8d
  int v32; // r9d
  const struct sockaddr_storage *lpSockaddr; // r12
  int v34; // r12d
  __int64 v35; // rcx
  unsigned __int64 v36; // rdx
  struct IRDPENCConnectorCallbacks *v37; // r9
  unsigned __int64 iSockaddrLength; // r8
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  struct IRdpUdpLocalEndpoint *v42; // rbx
  __int64 v43; // rax
  __int16 *v44; // rdx
  const char **v45; // rax
  const char *v46; // rax
  char *v47; // rdx
  const char **v49; // [rsp+30h] [rbp-81h]
  const char **v50; // [rsp+40h] [rbp-71h]
  const char **v51; // [rsp+48h] [rbp-69h]
  LONG lVal; // [rsp+50h] [rbp-61h] BYREF
  const char *v53; // [rsp+58h] [rbp-59h] BYREF
  struct IRdpUdpLocalEndpoint *v54; // [rsp+60h] [rbp-51h] BYREF
  const char *v55; // [rsp+68h] [rbp-49h] BYREF
  const char *v56; // [rsp+70h] [rbp-41h] BYREF
  const char *v57; // [rsp+78h] [rbp-39h] BYREF
  const char *v58; // [rsp+80h] [rbp-31h] BYREF
  VARIANTARG v59; // [rsp+88h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-11h] BYREF
  VARIANTARG v61; // [rsp+B8h] [rbp+7h] BYREF
  LONG v62; // [rsp+110h] [rbp+5Fh] BYREF
  int v63; // [rsp+120h] [rbp+6Fh]

  v63 = a3;
  v62 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v59, 0, sizeof(v59));
  memset(&v61, 0, sizeof(v61));
  VariantInit(&pvarg);
  VariantInit(&v59);
  VariantInit(&v61);
  *((_DWORD *)this + 110) = 1;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v54 = (struct IRdpUdpLocalEndpoint *)"RDPUDPTransport::ConfigureListener called";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)word_1801D0FF2,
      0,
      v10,
      (__int64)&v54);
  }
  if ( *((_QWORD *)this + 12) )
  {
    v14 = -2147418113;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_67;
    v46 = "Called after accept";
    LODWORD(v55) = 1550;
    v47 = &byte_1801D0EA7;
    goto LABEL_66;
  }
  v11 = (CRDPENCONIPHelper *)operator new(0x18u);
  v12 = v11;
  if ( !v11 )
  {
    v14 = -2147024882;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_67;
    v46 = "CRDPENCONIPHelper allocation failed";
    LODWORD(v55) = 1553;
    v47 = byte_1801D0333;
LABEL_66:
    v58 = v46;
    v53 = "ConfigureListeners";
    v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
    v54 = (struct IRdpUdpLocalEndpoint *)"Error condition failed";
    lVal = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v8,
      (_DWORD)v47,
      v9,
      v10,
      (__int64)&v54,
      (__int64)&lVal,
      (__int64)&v56,
      (__int64)&v55,
      (__int64)&v53,
      (__int64)&v58);
    goto LABEL_67;
  }
  *(_QWORD *)v11 = 0;
  *((_QWORD *)v11 + 1) = 0;
  *((_QWORD *)v11 + 2) = 0;
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 9) + 24LL))(
         *((_QWORD *)this + 9),
         L"BindAddress",
         &pvarg) >= 0 )
  {
    v14 = CRDPENCONIPHelper::Initialize(v12, a2, a5, pvarg.bstrVal);
    if ( v14 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        lVal = 1573;
        v53 = "Failed to initialize the ip helper";
        v56 = "ConfigureListeners";
        v54 = (struct IRdpUdpLocalEndpoint *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
        LODWORD(v57) = v14;
        v55 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v17,
          (unsigned int)&word_1801D29AE,
          v18,
          v19,
          (__int64)&v55,
          (__int64)&v57,
          (__int64)&v54,
          (__int64)&lVal,
          (__int64)&v56,
          (__int64)&v53);
      }
      goto LABEL_61;
    }
LABEL_12:
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 9) + 24LL))(
           *((_QWORD *)this + 9),
           L"LanAdapter",
           &v59) < 0 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v53 = "UDP listener not restricted to network adapter";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)byte_1801CFF91,
          0,
          v22,
          (__int64)&v53);
      }
      v59.lVal = -1;
      v59.vt = 19;
    }
    else if ( (unsigned int)CallbackContext > 4 )
    {
      lVal = v59.lVal;
      v53 = "UDP listener restricted to network adapter with index";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v20,
        (unsigned int)word_1801D0022,
        v21,
        v22,
        (__int64)&v53,
        (__int64)&lVal);
    }
    v14 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, LONG *))(**((_QWORD **)this + 9) + 32LL))(
            *((_QWORD *)this + 9),
            L"Udp:UseSxSPortRedirector",
            &v62);
    if ( v14 >= 0 && v62 )
    {
      v14 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 9) + 24LL))(
              *((_QWORD *)this + 9),
              L"Udp:SxSPortRedirectorPath",
              &v61);
      if ( v14 < 0 )
      {
        v62 = 0;
        if ( (unsigned int)CallbackContext > 3 )
        {
          v53 = "ConfigureListeners";
          v56 = "Failed to get CONN_PROPERTY_UDP_SXS_PORT_REDIRECTOR_PATH property";
          lVal = v14;
          v54 = (struct IRdpUdpLocalEndpoint *)"HResult failed but continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v23,
            (unsigned int)&byte_1801D0CDF,
            v24,
            v25,
            (__int64)&v54,
            (__int64)&v56,
            (__int64)&lVal,
            (__int64)&v53);
        }
      }
    }
    else
    {
      v62 = 0;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      lVal = v62;
      v53 = "UDP CDV Port Redirector mode";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)byte_1801D207B,
        v24,
        v25,
        (__int64)&v53,
        (__int64)&lVal);
    }
    if ( (unsigned int)CRDPENCONIPHelper::StartEnum(v12) )
    {
      Next = CRDPENCONIPHelper::GetNext(v12);
      if ( Next )
      {
        if ( !a3 )
          goto LABEL_60;
        LODWORD(v57) = 0;
        do
        {
          lpSockaddr = (const struct sockaddr_storage *)Next->lpSockaddr;
          if ( Next->lpSockaddr->sa_family == 2 || lpSockaddr->ss_family == 23 )
          {
            v35 = *((_QWORD *)this + 49);
            v54 = 0;
            if ( v35 )
              (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v35 + 24LL))(
                v35,
                L"UDP",
                (unsigned __int16)v63);
            *(_WORD *)lpSockaddr->__ss_pad1 = htons(v63);
            v36 = (unsigned __int64)this + 24;
            v37 = (struct IRDPENCConnectorCallbacks *)*((_QWORD *)this + 15);
            iSockaddrLength = Next->iSockaddrLength;
            if ( v62 )
            {
              v14 = CRdpUdpLocalEndpointPortRedirectorListener_CreateInstance(
                      (struct IRdpUdpLocalEndpointCallback *)(v36 & -(__int64)(this != (CRdpUdpTransport *)48)),
                      (const struct sockaddr_storage *)Next->lpSockaddr,
                      iSockaddrLength,
                      v59.cyVal.Lo,
                      v61.bstrVal,
                      v37,
                      &v54);
              if ( v14 < 0 )
              {
                if ( (unsigned int)CallbackContext > 2 )
                {
                  v56 = "ConfigureListeners";
                  v53 = "Failed to create CRdpUdpPortRedirectorEndpoint";
                  v44 = &word_1801D17DE;
                  LODWORD(v55) = 1679;
                  v57 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
                  v58 = "Error HResult failed";
                  v51 = &v53;
                  v50 = &v56;
                  v49 = &v57;
                  v45 = &v58;
                  goto LABEL_54;
                }
                goto LABEL_55;
              }
              if ( (unsigned int)CallbackContext > 4 )
              {
                LODWORD(v55) = lpSockaddr->ss_family;
                v53 = "Port redirector listener created";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v39,
                  (unsigned int)byte_1801D2F23,
                  v40,
                  v41,
                  (__int64)&v53,
                  (__int64)&v55);
              }
            }
            else
            {
              v14 = CRdpUdpLocalEndpointListener_CreateInstance(
                      (struct IRdpUdpLocalEndpointCallback *)(v36 & -(__int64)(this != (CRdpUdpTransport *)48)),
                      (const struct sockaddr_storage *)Next->lpSockaddr,
                      iSockaddrLength,
                      v59.cyVal.Lo,
                      v37,
                      &v54);
              if ( v14 < 0 )
              {
                if ( (unsigned int)CallbackContext > 2 )
                {
                  v53 = "ConfigureListeners";
                  v58 = "Failed to create CRdpUdpLocalEndpoint";
                  v44 = (__int16 *)qword_1801D09B0;
                  LODWORD(v55) = 1693;
                  v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
                  v57 = "Error HResult failed";
                  v51 = &v58;
                  v50 = &v53;
                  v49 = &v56;
                  v45 = &v57;
LABEL_54:
                  lVal = v14;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v39,
                    (_DWORD)v44,
                    v40,
                    v41,
                    (__int64)v45,
                    (__int64)&lVal,
                    (__int64)v49,
                    (__int64)&v55,
                    (__int64)v50,
                    (__int64)v51);
                }
LABEL_55:
                TCntPtr<IXMLDOMNodeList>::SafeRelease(&v54);
                goto LABEL_61;
              }
            }
            v42 = v54;
            v14 = CRdpUdpLocalEndpointTable::AddLocalEndpoint((CRdpUdpTransport *)((char *)this + 128), v54);
            if ( v14 < 0 )
            {
              if ( (unsigned int)CallbackContext > 2 )
              {
                v53 = "ConfigureListeners";
                v58 = "Failed to add the socket to the socket list";
                v44 = &word_1801CFFD6;
                LODWORD(v55) = 1697;
                v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
                v57 = "Error HResult failed";
                v51 = &v58;
                v50 = &v53;
                v49 = &v56;
                v45 = &v57;
                goto LABEL_54;
              }
              goto LABEL_55;
            }
            v43 = *(_QWORD *)v42;
            v34 = (_DWORD)v57 + 1;
            LODWORD(v57) = (_DWORD)v57 + 1;
            (*(void (__fastcall **)(struct IRdpUdpLocalEndpoint *, const char **))(v43 + 112))(v42, &v58);
            CRdpUdpTransport::AddSocketHandle((CRdpUdpTransport *)((char *)this - 48));
            TCntPtr<IXMLDOMNodeList>::SafeRelease(&v54);
          }
          else
          {
            if ( (unsigned int)CallbackContext > 3 )
            {
              LODWORD(v55) = lpSockaddr->ss_family;
              v53 = "Ignoring unknown address family";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v29,
                (unsigned int)qword_1801D24C8,
                v31,
                v32,
                (__int64)&v53,
                (__int64)&v55);
            }
            v34 = (int)v57;
          }
          Next = CRDPENCONIPHelper::GetNext(v12);
        }
        while ( Next );
        if ( v34 || !v63 )
LABEL_60:
          v14 = 0;
      }
      else
      {
        v14 = -2147014846;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v53 = "ConfigureListeners";
          v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
          LODWORD(v55) = 1640;
          v54 = (struct IRdpUdpLocalEndpoint *)"Cant get a connectable IP address.";
          lVal = -2147014846;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v29,
            (unsigned int)&word_1801D1356,
            v31,
            v32,
            (__int64)&v54,
            (__int64)&lVal,
            (__int64)&v56,
            (__int64)&v55,
            (__int64)&v53);
        }
      }
    }
    else
    {
      v14 = -2147014853;
      if ( (unsigned int)CallbackContext > 2 )
      {
        lVal = a2;
        v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
        v53 = "ConfigureListeners";
        v54 = (struct IRdpUdpLocalEndpoint *)"No interface found for protocol";
        LODWORD(v57) = 1631;
        LODWORD(v55) = -2147014853;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v26,
          (unsigned int)word_1801D22FA,
          v27,
          v28,
          (__int64)&v54,
          (__int64)&v55,
          (__int64)&v56,
          (__int64)&v57,
          (__int64)&v53,
          (__int64)&lVal);
      }
    }
    goto LABEL_61;
  }
  v14 = CRDPENCONIPHelper::Initialize(v12, a2, a5, (unsigned __int16 *)&word_18016FF08);
  if ( v14 >= 0 )
    goto LABEL_12;
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v57) = 1567;
    v54 = (struct IRdpUdpLocalEndpoint *)"Failed to initialize the ip helper";
    v55 = "ConfigureListeners";
    v56 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudptransport.cpp";
    lVal = v14;
    v53 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)CallbackContext,
      (unsigned int)word_1801D0732,
      v15,
      v16,
      (__int64)&v53,
      (__int64)&lVal,
      (__int64)&v56,
      (__int64)&v57,
      (__int64)&v55,
      (__int64)&v54);
  }
LABEL_61:
  CRDPENCONIPHelper::`scalar deleting destructor'(v12, v13);
LABEL_67:
  VariantClear(&pvarg);
  VariantClear(&v59);
  VariantClear(&v61);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180126fe0  mov     [rsp-8+arg_8], rbx
0x180126fe5  mov     [rsp-8+arg_10], r8d
0x180126fea  push    rbp
0x180126feb  push    rsi
0x180126fec  push    rdi
0x180126fed  push    r12
0x180126fef  push    r13
0x180126ff1  push    r14
0x180126ff3  push    r15
0x180126ff5  lea     rbp, [rsp-1Fh]
0x180126ffa  sub     rsp, 0D0h
0x180127001  xor     eax, eax
0x180127003  xorps   xmm0, xmm0
0x180127006  mov     r13, rcx
0x180127009  mov     qword ptr [rbp+4Fh+pvarg+10h], rax
0x18012700d  xorps   xmm1, xmm1
0x180127010  mov     qword ptr [rbp+4Fh+var_78+10h], rax
0x180127014  xor     r12d, r12d
0x180127017  mov     qword ptr [rbp+4Fh+var_48+10h], rax
0x18012701b  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18012701f  mov     [rbp+4Fh+arg_0], r12d
0x180127023  movups  xmmword ptr [rbp+4Fh+pvarg], xmm0
0x180127027  mov     esi, r8d
0x18012702a  mov     ebx, edx
0x18012702c  movups  xmmword ptr [rbp+4Fh+var_78], xmm1
0x180127030  movups  xmmword ptr [rbp+4Fh+var_48], xmm0
0x180127034  call    cs:__imp_VariantInit
0x18012703a  lea     rcx, [rbp+4Fh+var_78]; pvarg
0x18012703e  call    cs:__imp_VariantInit
0x180127044  lea     rcx, [rbp+4Fh+var_48]; pvarg
0x180127048  call    cs:__imp_VariantInit
0x18012704e  mov     dword ptr [r13+1B8h], 1
0x180127059  mov     eax, cs:CallbackContext
0x18012705f  cmp     eax, 4
0x180127062  jbe     short loc_18012708E
0x180127064  lea     rax, aRdpudptranspor_0; "RDPUDPTransport::ConfigureListener call"...
0x18012706b  xor     r8d, r8d
0x18012706e  mov     [rbp+4Fh+var_A0], rax
0x180127072  lea     rdx, word_1801D0FF2
0x180127079  lea     rax, [rbp+4Fh+var_A0]
0x18012707d  lea     rcx, CallbackContext
0x180127084  mov     [rsp+100h+var_E0], rax
0x180127089  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18012708e  cmp     [r13+60h], r12
0x180127092  jnz     loc_180127850
0x180127098  mov     ecx, 18h; Size
0x18012709d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801270a2  mov     r14, rax
0x1801270a5  test    rax, rax
0x1801270a8  jz      loc_180127821
0x1801270ae  mov     [rax], r12
0x1801270b1  lea     r8, [rbp+4Fh+pvarg]
0x1801270b5  mov     [rax+8], r12
0x1801270b9  lea     rdx, aBindaddress; "BindAddress"
0x1801270c0  mov     [rax+10h], r12
0x1801270c4  mov     rcx, [r13+48h]
0x1801270c8  mov     rax, [rcx]
0x1801270cb  mov     rax, [rax+18h]
0x1801270cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801270d4  mov     r8d, [rbp+4Fh+arg_20]; int
0x1801270d8  mov     edx, ebx; unsigned int
0x1801270da  mov     rcx, r14; this
0x1801270dd  test    eax, eax
0x1801270df  jns     loc_18012718B
0x1801270e5  lea     r9, word_18016FF08; unsigned __int16 *
0x1801270ec  call    ?Initialize@CRDPENCONIPHelper@@QEAAJKHPEAG@Z; CRDPENCONIPHelper::Initialize(ulong,int,ushort *)
0x1801270f1  mov     edi, eax
0x1801270f3  test    eax, eax
0x1801270f5  jns     loc_180127224
0x1801270fb  mov     ecx, cs:CallbackContext
0x180127101  mov     esi, 2
0x180127106  cmp     ecx, esi
0x180127108  jbe     loc_180127814
0x18012710e  lea     rax, aFailedToInitia_24; "Failed to initialize the ip helper"
0x180127115  mov     dword ptr [rbp+4Fh+var_88], 61Fh
0x18012711c  mov     [rbp+4Fh+var_A0], rax
0x180127120  lea     r15, aConfigureliste; "ConfigureListeners"
0x180127127  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18012712e  mov     [rbp+4Fh+var_98], r15
0x180127132  mov     [rbp+4Fh+var_90], rax
0x180127136  lea     rdx, word_1801D0732
0x18012713d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180127144  mov     [rbp+4Fh+var_B0], edi
0x180127147  mov     [rbp+4Fh+var_A8], rax
0x18012714b  lea     rax, [rbp+4Fh+var_A0]
0x18012714f  mov     [rsp+100h+var_B8], rax
0x180127154  lea     rax, [rbp+4Fh+var_98]
0x180127158  mov     [rsp+100h+var_C0], rax
0x18012715d  lea     rax, [rbp+4Fh+var_88]
0x180127161  mov     [rsp+100h+var_C8], rax
0x180127166  lea     rax, [rbp+4Fh+var_90]
0x18012716a  mov     [rsp+100h+var_D0], rax
0x18012716f  lea     rax, [rbp+4Fh+var_B0]
0x180127173  mov     [rsp+100h+var_D8], rax
0x180127178  lea     rax, [rbp+4Fh+var_A8]
0x18012717c  mov     [rsp+100h+var_E0], rax
0x180127181  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180127186  jmp     loc_180127814
0x18012718b  mov     r9, qword ptr [rbp+4Fh+pvarg+8]; unsigned __int16 *
0x18012718f  call    ?Initialize@CRDPENCONIPHelper@@QEAAJKHPEAG@Z; CRDPENCONIPHelper::Initialize(ulong,int,ushort *)
0x180127194  mov     edi, eax
0x180127196  test    eax, eax
0x180127198  jns     loc_180127224
0x18012719e  mov     eax, cs:CallbackContext
0x1801271a4  mov     esi, 2
0x1801271a9  cmp     eax, esi
0x1801271ab  jbe     loc_180127814
0x1801271b1  lea     rax, aFailedToInitia_24; "Failed to initialize the ip helper"
0x1801271b8  mov     [rbp+4Fh+var_B0], 625h
0x1801271bf  mov     [rbp+4Fh+var_A8], rax
0x1801271c3  lea     r15, aConfigureliste; "ConfigureListeners"
0x1801271ca  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801271d1  mov     [rbp+4Fh+var_90], r15
0x1801271d5  mov     [rbp+4Fh+var_A0], rax
0x1801271d9  lea     rdx, word_1801D29AE
0x1801271e0  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1801271e7  mov     dword ptr [rbp+4Fh+var_88], edi
0x1801271ea  mov     [rbp+4Fh+var_98], rax
0x1801271ee  lea     rax, [rbp+4Fh+var_A8]
0x1801271f2  mov     [rsp+100h+var_B8], rax
0x1801271f7  lea     rax, [rbp+4Fh+var_90]
0x1801271fb  mov     [rsp+100h+var_C0], rax
0x180127200  lea     rax, [rbp+4Fh+var_B0]
0x180127204  mov     [rsp+100h+var_C8], rax
0x180127209  lea     rax, [rbp+4Fh+var_A0]
0x18012720d  mov     [rsp+100h+var_D0], rax
0x180127212  lea     rax, [rbp+4Fh+var_88]
0x180127216  mov     [rsp+100h+var_D8], rax
0x18012721b  lea     rax, [rbp+4Fh+var_98]
0x18012721f  jmp     loc_18012717C
0x180127224  mov     rcx, [r13+48h]
0x180127228  lea     r8, [rbp+4Fh+var_78]
0x18012722c  lea     rdx, aLanadapter; "LanAdapter"
0x180127233  mov     rax, [rcx]
0x180127236  mov     rax, [rax+18h]
0x18012723a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012723f  test    eax, eax
0x180127241  mov     eax, cs:CallbackContext
0x180127247  js      short loc_18012727F
0x180127249  cmp     eax, 4
0x18012724c  jbe     short loc_1801272BE
0x18012724e  mov     eax, dword ptr [rbp+4Fh+var_78+8]
0x180127251  lea     rdx, word_1801D0022
0x180127258  mov     [rbp+4Fh+var_B0], eax
0x18012725b  lea     rax, aUdpListenerRes; "UDP listener restricted to network adap"...
0x180127262  mov     [rbp+4Fh+var_A8], rax
0x180127266  lea     rax, [rbp+4Fh+var_B0]
0x18012726a  mov     [rsp+100h+var_D8], rax
0x18012726f  lea     rax, [rbp+4Fh+var_A8]
0x180127273  mov     [rsp+100h+var_E0], rax
0x180127278  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18012727d  jmp     short loc_1801272BE
0x18012727f  cmp     eax, 4
0x180127282  jbe     short loc_1801272AE
0x180127284  lea     rax, aUdpListenerNot; "UDP listener not restricted to network "...
0x18012728b  xor     r8d, r8d
0x18012728e  mov     [rbp+4Fh+var_A8], rax
0x180127292  lea     rdx, byte_1801CFF91
0x180127299  lea     rax, [rbp+4Fh+var_A8]
0x18012729d  lea     rcx, CallbackContext
0x1801272a4  mov     [rsp+100h+var_E0], rax
0x1801272a9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1801272ae  mov     eax, 13h
0x1801272b3  mov     dword ptr [rbp+4Fh+var_78+8], 0FFFFFFFFh
0x1801272ba  mov     word ptr [rbp+4Fh+var_78], ax
0x1801272be  mov     rcx, [r13+48h]
0x1801272c2  lea     r8, [rbp+4Fh+arg_0]
0x1801272c6  lea     rdx, aUdpUsesxsportr; "Udp:UseSxSPortRedirector"
0x1801272cd  mov     rax, [rcx]
0x1801272d0  mov     rax, [rax+20h]
0x1801272d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801272d9  lea     r15, aConfigureliste; "ConfigureListeners"
0x1801272e0  mov     edi, eax
0x1801272e2  test    eax, eax
0x1801272e4  js      loc_18012736F
0x1801272ea  cmp     [rbp+4Fh+arg_0], r12d
0x1801272ee  jz      short loc_18012736F
0x1801272f0  mov     rcx, [r13+48h]
0x1801272f4  lea     r8, [rbp+4Fh+var_48]
0x1801272f8  lea     rdx, aUdpSxsportredi; "Udp:SxSPortRedirectorPath"
0x1801272ff  mov     rax, [rcx]
0x180127302  mov     rax, [rax+18h]
0x180127306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012730b  mov     edi, eax
0x18012730d  test    eax, eax
0x18012730f  jns     short loc_180127373
0x180127311  mov     eax, cs:CallbackContext
0x180127317  mov     [rbp+4Fh+arg_0], r12d
0x18012731b  cmp     eax, 3
0x18012731e  jbe     short loc_180127373
0x180127320  lea     rax, aFailedToGetCon_0; "Failed to get CONN_PROPERTY_UDP_SXS_POR"...
0x180127327  mov     [rbp+4Fh+var_A8], r15
0x18012732b  mov     [rbp+4Fh+var_90], rax
0x18012732f  lea     rdx, byte_1801D0CDF
0x180127336  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18012733d  mov     [rbp+4Fh+var_B0], edi
0x180127340  mov     [rbp+4Fh+var_A0], rax
0x180127344  lea     rax, [rbp+4Fh+var_A8]
0x180127348  mov     [rsp+100h+var_C8], rax
0x18012734d  lea     rax, [rbp+4Fh+var_B0]
0x180127351  mov     [rsp+100h+var_D0], rax
0x180127356  lea     rax, [rbp+4Fh+var_90]
0x18012735a  mov     [rsp+100h+var_D8], rax
0x18012735f  lea     rax, [rbp+4Fh+var_A0]
0x180127363  mov     [rsp+100h+var_E0], rax
0x180127368  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18012736d  jmp     short loc_180127373
0x18012736f  mov     [rbp+4Fh+arg_0], r12d
0x180127373  mov     eax, cs:CallbackContext
0x180127379  cmp     eax, 4
0x18012737c  jbe     short loc_1801273AD
0x18012737e  mov     eax, [rbp+4Fh+arg_0]
0x180127381  lea     rdx, byte_1801D207B
0x180127388  mov     [rbp+4Fh+var_B0], eax
0x18012738b  lea     rax, aUdpCdvPortRedi; "UDP CDV Port Redirector mode"
0x180127392  mov     [rbp+4Fh+var_A8], rax
0x180127396  lea     rax, [rbp+4Fh+var_B0]
0x18012739a  mov     [rsp+100h+var_D8], rax
0x18012739f  lea     rax, [rbp+4Fh+var_A8]
0x1801273a3  mov     [rsp+100h+var_E0], rax
0x1801273a8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1801273ad  mov     rcx, r14; this
0x1801273b0  call    ?StartEnum@CRDPENCONIPHelper@@QEAAHXZ; CRDPENCONIPHelper::StartEnum(void)
0x1801273b5  test    eax, eax
0x1801273b7  jnz     loc_180127443
0x1801273bd  mov     eax, cs:CallbackContext
0x1801273c3  mov     esi, 2
0x1801273c8  mov     edi, 8007273Bh
0x1801273cd  cmp     eax, esi
0x1801273cf  jbe     loc_180127814
0x1801273d5  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801273dc  mov     [rbp+4Fh+var_B0], ebx
0x1801273df  mov     [rbp+4Fh+var_90], rax
0x1801273e3  lea     rdx, word_1801D22FA
0x1801273ea  lea     rax, aNoInterfaceFou_0; "No interface found for protocol"
0x1801273f1  mov     [rbp+4Fh+var_A8], r15
0x1801273f5  mov     [rbp+4Fh+var_A0], rax
0x1801273f9  lea     rax, [rbp+4Fh+var_B0]
0x1801273fd  mov     [rsp+100h+var_B8], rax
0x180127402  lea     rax, [rbp+4Fh+var_A8]
0x180127406  mov     [rsp+100h+var_C0], rax
0x18012740b  lea     rax, [rbp+4Fh+var_88]
0x18012740f  mov     [rsp+100h+var_C8], rax
0x180127414  lea     rax, [rbp+4Fh+var_90]
0x180127418  mov     [rsp+100h+var_D0], rax
0x18012741d  lea     rax, [rbp+4Fh+var_98]
0x180127421  mov     [rsp+100h+var_D8], rax
0x180127426  lea     rax, [rbp+4Fh+var_A0]
0x18012742a  mov     [rsp+100h+var_E0], rax
0x18012742f  mov     dword ptr [rbp+4Fh+var_88], 65Fh
0x180127436  mov     dword ptr [rbp+4Fh+var_98], edi
0x180127439  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18012743e  jmp     loc_180127814
0x180127443  mov     rcx, r14; this
0x180127446  call    ?GetNext@CRDPENCONIPHelper@@QEAAPEAU_SOCKET_ADDRESS@@XZ; CRDPENCONIPHelper::GetNext(void)
0x18012744b  mov     rbx, rax
0x18012744e  test    rax, rax
0x180127451  jnz     short loc_1801274CB
0x180127453  mov     eax, cs:CallbackContext
0x180127459  lea     esi, [rbx+2]
0x18012745c  mov     edi, 80072742h
0x180127461  cmp     eax, esi
0x180127463  jbe     loc_180127814
0x180127469  lea     rax, aOnecoreTermsrv_77; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180127470  mov     [rbp+4Fh+var_A8], r15
0x180127474  mov     [rbp+4Fh+var_90], rax
0x180127478  lea     rdx, word_1801D1356
0x18012747f  lea     rax, aCantGetAConnec; "Cant get a connectable IP address."
0x180127486  mov     dword ptr [rbp+4Fh+var_98], 668h
0x18012748d  mov     [rbp+4Fh+var_A0], rax
0x180127491  lea     rax, [rbp+4Fh+var_A8]
0x180127495  mov     [rsp+100h+var_C0], rax
0x18012749a  lea     rax, [rbp+4Fh+var_98]
0x18012749e  mov     [rsp+100h+var_C8], rax
0x1801274a3  lea     rax, [rbp+4Fh+var_90]
0x1801274a7  mov     [rsp+100h+var_D0], rax
0x1801274ac  lea     rax, [rbp+4Fh+var_B0]
0x1801274b0  mov     [rsp+100h+var_D8], rax
0x1801274b5  lea     rax, [rbp+4Fh+var_A0]
0x1801274b9  mov     [rsp+100h+var_E0], rax
0x1801274be  mov     [rbp+4Fh+var_B0], edi
0x1801274c1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801274c6  jmp     loc_180127814
0x1801274cb  test    esi, esi
0x1801274cd  jz      loc_180127811
0x1801274d3  mov     dword ptr [rbp+4Fh+var_88], r12d
0x1801274d7  mov     esi, 2
0x1801274dc  mov     r12, [rbx]
0x1801274df  cmp     [r12], si
0x1801274e4  jz      short loc_180127559
0x1801274e6  cmp     word ptr [r12], 17h
0x1801274ec  jz      short loc_180127559
0x1801274ee  mov     eax, cs:CallbackContext
0x1801274f4  cmp     eax, 3
0x1801274f7  jbe     short loc_18012752A
0x1801274f9  movzx   eax, word ptr [r12]
0x1801274fe  lea     rdx, qword_1801D24C8
0x180127505  mov     dword ptr [rbp+4Fh+var_98], eax
0x180127508  lea     rax, aIgnoringUnknow; "Ignoring unknown address family"
0x18012750f  mov     [rbp+4Fh+var_A8], rax
  ... truncated ...
```
