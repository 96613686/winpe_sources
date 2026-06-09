# CRDPENCCONDTLSSecurityFilterStream::DTLSHandshake(uchar *,ulong,int,int)

- ea: `0x1800fa994`
- end: `0x1800fb63b`
- name: `?DTLSHandshake@CRDPENCCONDTLSSecurityFilterStream@@AEAAJPEAEKHH@Z`
- size: `3239`
- prototype: `__int64 __usercall@<rax>(CRDPENCCONDTLSSecurityFilterStream *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, int@<r9d>, int)`
- caller_count: `4`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800fb650`
- `0x1800fcec0`
- `0x1800fd470`
- `0x1800fdc3c`

## callees

- `0x1800018a4`
- `0x180002550`
- `0x180003158`
- `0x180004970`
- `0x180004a94`
- `0x180046a84`
- `0x1800711c8`
- `0x1800923f8`
- `0x1800fa994`
- `0x1800fb74c`
- `0x1800fb8d4`
- `0x1800fe398`
- `0x18015cac8`
- `0x18015d530`
- `0x18015e090`
- `0x180162010`

## import_xrefs

- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1800faa9d`
- `SspiCli!SeciAllocateAndSetIPAddress` at `0x1800faa9d`
- `SspiCli!SeciFreeCallContext` at `0x1800fb61f`
- `SspiCli!SeciFreeCallContext` at `0x1800fb61f`

## string_xrefs

- `0x1800faa42`: `CRDPENCCONDTLSSecurityFilterStream::DTLSHandshake dtlsState: %d, pcbIn: %d`
- `0x1800fb153`: `Out of order receive during DTLS handshake`
- `0x1800fb13e`: `DTLSSendBufferOutAndCallSSPAgain and bSendComplete is true`
- `0x1800fb30d`: `DTLSSendBufferOutAndCallSSPAgain: DTLS hand shake is complete`
- `0x1800faef0`: `DTLSSendBufferOutAndReceiveAndThenCallSSPAgain and bSendComplete`
- `0x1800fad9e`: `DTLSDataTransfer: DTLS hand shake is complete`
- `0x1800fb51d`: `DTLS handshake is complete`
- `0x1800fb5bb`: `m_pSecFilter->GetStreamSizes failed.`

## pseudocode

```c
__int64 __fastcall CRDPENCCONDTLSSecurityFilterStream::DTLSHandshake(
        CRDPENCCONDTLSSecurityFilterStream *this,
        unsigned __int8 *a2,
        unsigned int a3,
        int a4,
        int a5)
{
  int v6; // ecx
  __int64 v10; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int StreamSizes; // ebx
  int v13; // r15d
  _WORD *v14; // rcx
  __int16 *v15; // rdx
  const char **v16; // rax
  unsigned int v17; // eax
  int v18; // edx
  const char *v19; // rcx
  int v20; // ecx
  unsigned int v21; // edx
  unsigned int v22; // eax
  int v23; // edx
  const char *v24; // rcx
  int v25; // ecx
  const char *v26; // rax
  __int16 *v27; // rdx
  unsigned int v28; // edx
  int v29; // ecx
  int v30; // ecx
  unsigned int v31; // eax
  __int64 v32; // rcx
  unsigned int *v34; // [rsp+28h] [rbp-59h]
  int *v35; // [rsp+38h] [rbp-49h]
  const char **v36; // [rsp+40h] [rbp-41h]
  const char **v37; // [rsp+48h] [rbp-39h]
  unsigned int v38; // [rsp+50h] [rbp-31h] BYREF
  int v39; // [rsp+54h] [rbp-2Dh] BYREF
  const char *v40; // [rsp+58h] [rbp-29h] BYREF
  const char *v41; // [rsp+60h] [rbp-21h] BYREF
  unsigned __int8 *v42; // [rsp+68h] [rbp-19h] BYREF
  int v43; // [rsp+70h] [rbp-11h] BYREF
  const char *v44; // [rsp+78h] [rbp-9h] BYREF
  const char *v45; // [rsp+80h] [rbp-1h] BYREF
  int v46[18]; // [rsp+88h] [rbp+7h] BYREF
  unsigned __int8 v47; // [rsp+E0h] [rbp+5Fh] BYREF

  v6 = 0;
  v42 = 0;
  v38 = 0;
  v10 = *((_QWORD *)this + 46);
  v47 = 0;
  v46[0] = 0;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        (unsigned int)WPP_310100a96f023abf06e7a5d6677d258d_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"m_pSecFilter");
    }
    StreamSizes = -2147467261;
    goto LABEL_133;
  }
  v13 = *(_DWORD *)(v10 + 136);
  StreamSizes = 0;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v43 = a3;
    v41 = "CRDPENCCONDTLSSecurityFilterStream::DTLSHandshake dtlsState: %d, pcbIn: %d";
    v39 = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      0,
      (unsigned int)byte_1801C4843,
      a3,
      a4,
      (__int64)&v41,
      (__int64)&v39,
      (__int64)&v43);
  }
  v14 = (_WORD *)((char *)this + 464);
  if ( *((_WORD *)this + 232) == 2 || *v14 == 23 )
    SeciAllocateAndSetIPAddress(v14, *((unsigned int *)this + 114), v46);
  v6 = v13 - 2;
  switch ( v13 )
  {
    case 2:
      goto LABEL_116;
    case 3:
      if ( a4 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          v26 = "DTLSSendBufferOutAndCallSSPAgain and bSendComplete is true";
          v27 = (__int16 *)byte_1801C4801;
LABEL_91:
          v40 = v26;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (_DWORD)v27,
            0,
            a4,
            (__int64)&v40);
        }
      }
      else if ( (unsigned int)CallbackContext > 4 )
      {
        v26 = "Out of order receive during DTLS handshake";
        v27 = word_1801C4822;
        goto LABEL_91;
      }
      StreamSizes = CRdpDTLSFilter::DoDTLSHandshake(
                      *((CRdpDTLSFilter **)this + 46),
                      0,
                      a2,
                      a3,
                      &v42,
                      &v38,
                      (unsigned int *)this + 105,
                      &v47);
      if ( StreamSizes < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_133;
        }
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 65;
        goto LABEL_30;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v41) = v38;
        v29 = *(_DWORD *)(*((_QWORD *)this + 46) + 136LL);
        v40 = "After m_pSecFilter->DoDTLSHandshake dtlsState: %d cbOut: %d";
        v39 = v29;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v29,
          (unsigned int)qword_1801C4790,
          a3,
          a4,
          (__int64)&v40,
          (__int64)&v39,
          (__int64)&v41);
      }
      if ( v42 && v38 )
      {
        if ( (unsigned int)CallbackContext > 4 )
        {
          LODWORD(v41) = v38;
          v40 = " DTLS handshake trying to send %d bytes";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v6,
            (unsigned int)byte_1801C47D9,
            a3,
            a4,
            (__int64)&v40,
            (__int64)&v41);
        }
        StreamSizes = CRDPENCCONDTLSSecurityFilterStream::SendToClient(this, v42, v38);
        if ( StreamSizes >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_133;
        }
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 66;
        goto LABEL_43;
      }
      if ( *(_DWORD *)(*((_QWORD *)this + 46) + 136LL) != 6 )
        goto LABEL_133;
      if ( (unsigned int)CallbackContext > 4 )
      {
        v40 = "DTLSSendBufferOutAndCallSSPAgain: DTLS hand shake is complete";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)&byte_1801C476F,
          0,
          a4,
          (__int64)&v40);
      }
      StreamSizes = CRdpDTLSFilter::SetMTU(*((CRdpDTLSFilter **)this + 46), v28);
      if ( StreamSizes >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_133;
      }
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v18 = 67;
      v19 = "SetMTU failed";
      goto LABEL_31;
    case 4:
      if ( !a4 )
      {
        StreamSizes = CRdpDTLSFilter::DoDTLSHandshake(
                        *((CRdpDTLSFilter **)this + 46),
                        a5,
                        a2,
                        a3,
                        &v42,
                        &v38,
                        (unsigned int *)this + 105,
                        &v47);
        if ( StreamSizes < 0 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_133;
          }
          v17 = RdpWppGetCurrentThreadActivityIdPrefix();
          v18 = 70;
          goto LABEL_30;
        }
        if ( (unsigned int)CallbackContext > 4 )
        {
          LODWORD(v41) = v38;
          v25 = *(_DWORD *)(*((_QWORD *)this + 46) + 136LL);
          v40 = "After m_pSecFilter->DoDTLSHandshake dtlsState: %d cbOut: %d";
          v39 = v25;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v25,
            (unsigned int)&word_1801C4726,
            a3,
            a4,
            (__int64)&v40,
            (__int64)&v39,
            (__int64)&v41);
        }
        if ( !v42 || !v38 )
          goto LABEL_133;
        if ( (unsigned int)CallbackContext > 4 )
        {
          LODWORD(v41) = v38;
          v40 = "DTLS handshake trying to send %d bytes";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v6,
            (unsigned int)&dword_1801C4694,
            a3,
            a4,
            (__int64)&v40,
            (__int64)&v41);
        }
        StreamSizes = CRDPENCCONDTLSSecurityFilterStream::SendToClient(this, v42, v38);
        if ( StreamSizes >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_133;
        }
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 71;
        goto LABEL_43;
      }
      if ( (unsigned int)CallbackContext > 4 )
      {
        v40 = "DTLSSendBufferOutAndReceiveAndThenCallSSPAgain and bSendComplete";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)byte_1801C4705,
          0,
          a4,
          (__int64)&v40);
      }
      StreamSizes = CRDPENCCONDTLSSecurityFilterStream::DTLSStopTimer(this);
      if ( StreamSizes >= 0 )
      {
        StreamSizes = CRDPENCCONDTLSSecurityFilterStream::DTLSStartTimer(this);
        if ( StreamSizes >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_133;
        }
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 69;
        v19 = "DTLSStartTimer failed";
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_133;
        }
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 68;
        v19 = "DTLSStopTimer failed";
      }
LABEL_31:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        (unsigned int)WPP_310100a96f023abf06e7a5d6677d258d_Traceguids,
        v17,
        (__int64)v19,
        StreamSizes);
      goto LABEL_133;
  }
  v6 = v13 - 5;
  if ( v13 == 5 )
  {
LABEL_116:
    if ( a4 )
      goto LABEL_133;
    StreamSizes = CRdpDTLSFilter::DoDTLSHandshake(
                    *((CRdpDTLSFilter **)this + 46),
                    a5,
                    a2,
                    a3,
                    &v42,
                    &v38,
                    (unsigned int *)this + 105,
                    &v47);
    if ( StreamSizes < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_133;
      }
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v18 = 72;
      goto LABEL_30;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v41) = v38;
      v30 = *(_DWORD *)(*((_QWORD *)this + 46) + 136LL);
      v40 = "After m_pSecFilter->DoDTLSHandshake dtlsState: %d cbOut: %d";
      v39 = v30;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)&dword_1801C46BC,
        a3,
        a4,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v41);
    }
    if ( !v42 || !v38 )
      goto LABEL_133;
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v41) = v38;
      v40 = "DTLS handshake trying to send %d bytes";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&byte_1801C4627,
        a3,
        a4,
        (__int64)&v40,
        (__int64)&v41);
    }
    StreamSizes = CRDPENCCONDTLSSecurityFilterStream::SendToClient(this, v42, v38);
    if ( StreamSizes >= 0
      || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_133;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 73;
LABEL_43:
    v19 = "SendToClient failed.";
    goto LABEL_31;
  }
  if ( v13 == 6 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v41) = 1679;
      v44 = "DTLSDataTransfer: DTLS hand shake is complete";
      v40 = "DTLSHandshake";
      v45 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpdtlsfilterserver.cpp";
      v39 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        0,
        (unsigned int)&byte_1801C464F,
        a3,
        a4,
        (__int64)&v44,
        (__int64)&v39,
        (__int64)&v45,
        (__int64)&v41,
        (__int64)&v40);
    }
    StreamSizes = CRDPENCCONDTLSSecurityFilterStream::DTLSStopTimer(this);
    if ( StreamSizes >= 0 )
    {
      StreamSizes = CRdpDTLSFilter::SetMTU(*((CRdpDTLSFilter **)this + 46), v21);
      if ( StreamSizes >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_133;
      }
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 75;
      v24 = "m_pSecFilter->SetMTU failed";
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_133;
      }
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      v23 = 74;
      v24 = "DTLSStopTimer failed";
    }
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v23,
      (unsigned int)WPP_310100a96f023abf06e7a5d6677d258d_Traceguids,
      v22,
      (__int64)v24,
      StreamSizes);
    goto LABEL_133;
  }
  v6 = v13 - 7;
  if ( v13 == 7 )
  {
    StreamSizes = CRdpDTLSFilter::DoDTLSHandshake(
                    *((CRdpDTLSFilter **)this + 46),
                    a5,
                    a2,
                    a3,
                    &v42,
                    &v38,
                    (unsigned int *)this + 105,
                    &v47);
    if ( StreamSizes < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_133;
      }
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      v18 = 76;
LABEL_30:
      v19 = "DoDTLSHandshake failed";
      goto LABEL_31;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v41) = v38;
      v20 = *(_DWORD *)(*((_QWORD *)this + 46) + 136LL);
      v40 = "After m_pSecFilter->DoDTLSHandshake dtlsState: %d cbOut: %d";
      v39 = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v20,
        (unsigned int)&word_1801C45B6,
        a3,
        a4,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v41);
    }
    if ( !v42 || !v38 )
      goto LABEL_133;
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v41) = v38;
      v40 = "DTLS handshake trying to send %d bytes";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&byte_1801C45FF,
        a3,
        a4,
        (__int64)&v40,
        (__int64)&v41);
    }
    StreamSizes = CRDPENCCONDTLSSecurityFilterStream::SendToClient(this, v42, v38);
    if ( StreamSizes >= 0
      || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_133;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 77;
    goto LABEL_43;
  }
  if ( v13 == 9 )
  {
    StreamSizes = *(_DWORD *)(*((_QWORD *)this + 46) + 208LL);
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_133;
    LODWORD(v41) = *(_DWORD *)(*((_QWORD *)this + 46) + 208LL);
    v44 = "dtlsState == DTLSError hr: 0x%x";
    v40 = "DTLSHandshake";
    v37 = &v41;
    v15 = (__int16 *)byte_1801C451D;
    v39 = 1719;
    v36 = &v40;
    v35 = &v39;
    v34 = (unsigned int *)&v43;
    v16 = &v44;
    v43 = -2147467259;
  }
  else
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_133;
    v39 = v13;
    v40 = "unknown dtlsState: %d";
    v44 = "DTLSHandshake";
    v37 = (const char **)&v39;
    v15 = &word_1801C4566;
    v43 = 1724;
    v36 = &v44;
    v35 = &v43;
    v34 = (unsigned int *)&v41;
    v16 = &v40;
    LODWORD(v41) = -2147467259;
  }
  v45 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpdtlsfilterserver.cpp";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
    v6,
    (_DWORD)v15,
    a3,
    a4,
    (__int64)v16,
    (__int64)v34,
    (__int64)&v45,
    (__int64)v35,
    (__int64)v36,
    (__int64)v37);
LABEL_133:
  if ( v47 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v40 = "DTLSHandshake";
      v44 = "DTLS handshake is complete";
      LODWORD(v41) = 1737;
      v45 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpdtlsfilterserver.cpp";
      v39 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)qword_1801C44D8,
        a3,
        a4,
        (__int64)&v44,
        (__int64)&v39,
        (__int64)&v45,
        (__int64)&v41,
        (__int64)&v40);
    }
    StreamSizes = CRdpDTLSFilter::GetStreamSizes(
                    *((CRdpDTLSFilter **)this + 46),
                    (unsigned int *)this + 97,
                    (unsigned int *)this + 95,
                    (unsigned int *)this + 96);
    if ( StreamSizes < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v31 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        (unsigned int)WPP_310100a96f023abf06e7a5d6677d258d_Traceguids,
        v31,
        (__int64)"m_pSecFilter->GetStreamSizes failed.",
        StreamSizes);
    }
    *((_DWORD *)this + 76) = 3;
  }
  if ( v42 )
  {
    v32 = *(_QWORD *)(*((_QWORD *)this + 46) + 56LL);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 32LL))(v32);
  }
  if ( v46[0] )
    SeciFreeCallContext();
  return (unsigned int)StreamSizes;
}

```

## disassembly

```asm
0x1800fa994  push    rbp
0x1800fa996  push    rbx
0x1800fa997  push    rsi
0x1800fa998  push    rdi
0x1800fa999  push    r12
0x1800fa99b  push    r13
0x1800fa99d  push    r14
0x1800fa99f  push    r15
0x1800fa9a1  lea     rbp, [rsp-17h]
0x1800fa9a6  sub     rsp, 98h
0x1800fa9ad  mov     rdi, rcx
0x1800fa9b0  lea     r15, WPP_GLOBAL_Control
0x1800fa9b7  xor     ecx, ecx
0x1800fa9b9  mov     r14d, r9d
0x1800fa9bc  mov     r12d, r8d
0x1800fa9bf  mov     [rbp+4Fh+var_68], rcx
0x1800fa9c3  mov     r13, rdx
0x1800fa9c6  mov     [rbp+4Fh+var_80], ecx
0x1800fa9c9  mov     rax, [rdi+170h]
0x1800fa9d0  mov     [rbp+4Fh+arg_0], cl
0x1800fa9d3  mov     [rbp+4Fh+var_48], ecx
0x1800fa9d6  test    rax, rax
0x1800fa9d9  jnz     short loc_1800FAA2E
0x1800fa9db  mov     rax, cs:WPP_GLOBAL_Control
0x1800fa9e2  lea     esi, [rcx+2]
0x1800fa9e5  cmp     rax, r15
0x1800fa9e8  jz      short loc_1800FAA24
0x1800fa9ea  test    byte ptr [rax+1Ch], 8
0x1800fa9ee  jz      short loc_1800FAA24
0x1800fa9f0  cmp     [rax+19h], sil
0x1800fa9f4  jb      short loc_1800FAA24
0x1800fa9f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fa9fb  lea     rcx, aMPsecfilter; "m_pSecFilter"
0x1800faa02  mov     r9d, eax
0x1800faa05  mov     [rsp+0D0h+var_B0], rcx
0x1800faa0a  lea     edx, [rsi+3Eh]
0x1800faa0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800faa14  lea     r8, WPP_310100a96f023abf06e7a5d6677d258d_Traceguids
0x1800faa1b  mov     rcx, [rcx+10h]
0x1800faa1f  call    WPP_SF_Ds
0x1800faa24  mov     ebx, 80004003h
0x1800faa29  jmp     loc_1800FB4FB
0x1800faa2e  mov     r15d, [rax+88h]
0x1800faa35  mov     ebx, ecx
0x1800faa37  mov     eax, cs:CallbackContext
0x1800faa3d  cmp     eax, 4
0x1800faa40  jbe     short loc_1800FAA7C
0x1800faa42  lea     rax, aCrdpenccondtls_3; "CRDPENCCONDTLSSecurityFilterStream::DTL"...
0x1800faa49  mov     [rbp+4Fh+var_60], r12d
0x1800faa4d  mov     [rbp+4Fh+var_70], rax
0x1800faa51  lea     rdx, byte_1801C4843
0x1800faa58  lea     rax, [rbp+4Fh+var_60]
0x1800faa5c  mov     [rbp+4Fh+var_7C], r15d
0x1800faa60  mov     [rsp+0D0h+var_A0], rax
0x1800faa65  lea     rax, [rbp+4Fh+var_7C]
0x1800faa69  mov     [rsp+0D0h+var_A8], rax
0x1800faa6e  lea     rax, [rbp+4Fh+var_70]
0x1800faa72  mov     [rsp+0D0h+var_B0], rax
0x1800faa77  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800faa7c  lea     rcx, [rdi+1D0h]
0x1800faa83  mov     esi, 2
0x1800faa88  cmp     [rcx], si
0x1800faa8b  jz      short loc_1800FAA93
0x1800faa8d  cmp     word ptr [rcx], 17h
0x1800faa91  jnz     short loc_1800FAAA3
0x1800faa93  mov     edx, [rdi+1C8h]
0x1800faa99  lea     r8, [rbp+4Fh+var_48]
0x1800faa9d  call    cs:__imp_SeciAllocateAndSetIPAddress
0x1800faaa3  mov     ecx, r15d
0x1800faaa6  sub     ecx, esi
0x1800faaa8  jz      loc_1800FB38E
0x1800faaae  sub     ecx, 1
0x1800faab1  jz      loc_1800FB12E
0x1800faab7  sub     ecx, 1
0x1800faaba  jz      loc_1800FAEDC
0x1800faac0  sub     ecx, 1
0x1800faac3  jz      loc_1800FB38E
0x1800faac9  sub     ecx, 1
0x1800faacc  jz      loc_1800FAD94
0x1800faad2  sub     ecx, 1
0x1800faad5  jz      loc_1800FABF1
0x1800faadb  cmp     ecx, esi
0x1800faadd  jz      loc_1800FAB72
0x1800faae3  mov     eax, cs:CallbackContext
0x1800faae9  cmp     eax, esi
0x1800faaeb  jbe     loc_1800FB4F4
0x1800faaf1  lea     rax, aUnknownDtlssta; "unknown dtlsState: %d"
0x1800faaf8  mov     [rbp+4Fh+var_7C], r15d
0x1800faafc  mov     [rbp+4Fh+var_78], rax
0x1800fab00  lea     r14, aDtlshandshake; "DTLSHandshake"
0x1800fab07  lea     rax, [rbp+4Fh+var_7C]
0x1800fab0b  mov     [rbp+4Fh+var_58], r14
0x1800fab0f  mov     [rsp+0D0h+var_88], rax
0x1800fab14  lea     rdx, word_1801C4566
0x1800fab1b  lea     rax, [rbp+4Fh+var_58]
0x1800fab1f  mov     [rbp+4Fh+var_60], 6BCh
0x1800fab26  mov     [rsp+0D0h+var_90], rax
0x1800fab2b  lea     rax, [rbp+4Fh+var_60]
0x1800fab2f  mov     [rsp+0D0h+var_98], rax
0x1800fab34  lea     rax, [rbp+4Fh+var_50]
0x1800fab38  mov     [rsp+0D0h+var_A0], rax
0x1800fab3d  lea     rax, [rbp+4Fh+var_70]
0x1800fab41  mov     [rsp+0D0h+var_A8], rax
0x1800fab46  lea     rax, [rbp+4Fh+var_78]
0x1800fab4a  mov     dword ptr [rbp+4Fh+var_70], 80004005h
0x1800fab51  lea     r12, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fab58  mov     [rsp+0D0h+var_B0], rax
0x1800fab5d  mov     [rbp+4Fh+var_50], r12
0x1800fab61  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800fab66  lea     r15, WPP_GLOBAL_Control
0x1800fab6d  jmp     loc_1800FB509
0x1800fab72  mov     rax, [rdi+170h]
0x1800fab79  mov     ebx, [rax+0D0h]
0x1800fab7f  mov     eax, cs:CallbackContext
0x1800fab85  cmp     eax, esi
0x1800fab87  jbe     loc_1800FB4F4
0x1800fab8d  lea     rax, aDtlsstateDtlse; "dtlsState == DTLSError hr: 0x%x"
0x1800fab94  mov     dword ptr [rbp+4Fh+var_70], ebx
0x1800fab97  mov     [rbp+4Fh+var_58], rax
0x1800fab9b  lea     r14, aDtlshandshake; "DTLSHandshake"
0x1800faba2  lea     rax, [rbp+4Fh+var_70]
0x1800faba6  mov     [rbp+4Fh+var_78], r14
0x1800fabaa  mov     [rsp+0D0h+var_88], rax
0x1800fabaf  lea     rdx, byte_1801C451D
0x1800fabb6  lea     rax, [rbp+4Fh+var_78]
0x1800fabba  mov     [rbp+4Fh+var_7C], 6B7h
0x1800fabc1  mov     [rsp+0D0h+var_90], rax
0x1800fabc6  lea     rax, [rbp+4Fh+var_7C]
0x1800fabca  mov     [rsp+0D0h+var_98], rax
0x1800fabcf  lea     rax, [rbp+4Fh+var_50]
0x1800fabd3  mov     [rsp+0D0h+var_A0], rax
0x1800fabd8  lea     rax, [rbp+4Fh+var_60]
0x1800fabdc  mov     [rsp+0D0h+var_A8], rax
0x1800fabe1  lea     rax, [rbp+4Fh+var_58]
0x1800fabe5  mov     [rbp+4Fh+var_60], 80004005h
0x1800fabec  jmp     loc_1800FAB51
0x1800fabf1  mov     edx, [rbp+4Fh+arg_20]; int
0x1800fabf4  lea     rcx, [rbp+4Fh+arg_0]
0x1800fabf8  mov     [rsp+0D0h+var_98], rcx; unsigned __int8 *
0x1800fabfd  lea     rax, [rdi+1A4h]
0x1800fac04  mov     rcx, [rdi+170h]; this
0x1800fac0b  mov     r9d, r12d; unsigned int
0x1800fac0e  mov     [rsp+0D0h+var_A0], rax; unsigned int *
0x1800fac13  mov     r8, r13; unsigned __int8 *
0x1800fac16  lea     rax, [rbp+4Fh+var_80]
0x1800fac1a  mov     [rsp+0D0h+var_A8], rax; unsigned int *
0x1800fac1f  lea     rax, [rbp+4Fh+var_68]
0x1800fac23  mov     [rsp+0D0h+var_B0], rax; unsigned __int8 **
0x1800fac28  call    ?DoDTLSHandshake@CRdpDTLSFilter@@QEAAJHPEAEKPEAPEAEPEAK20@Z; CRdpDTLSFilter::DoDTLSHandshake(int,uchar *,ulong,uchar * *,ulong *,ulong *,uchar *)
0x1800fac2d  mov     ebx, eax
0x1800fac2f  test    eax, eax
0x1800fac31  jns     short loc_1800FAC97
0x1800fac33  mov     rax, cs:WPP_GLOBAL_Control
0x1800fac3a  lea     r15, WPP_GLOBAL_Control
0x1800fac41  cmp     rax, r15
0x1800fac44  jz      loc_1800FB4FB
0x1800fac4a  test    byte ptr [rax+1Ch], 8
0x1800fac4e  jz      loc_1800FB4FB
0x1800fac54  cmp     [rax+19h], sil
0x1800fac58  jb      loc_1800FB4FB
0x1800fac5e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fac63  mov     edx, 4Ch ; 'L'
0x1800fac68  lea     rcx, aDodtlshandshak; "DoDTLSHandshake failed"
0x1800fac6f  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x1800fac73  lea     r8, WPP_310100a96f023abf06e7a5d6677d258d_Traceguids
0x1800fac7a  mov     [rsp+0D0h+var_B0], rcx
0x1800fac7f  mov     r9d, eax
0x1800fac82  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fac89  mov     rcx, [rcx+10h]
0x1800fac8d  call    WPP_SF_DsD
0x1800fac92  jmp     loc_1800FB4FB
0x1800fac97  mov     eax, cs:CallbackContext
0x1800fac9d  cmp     eax, 4
0x1800faca0  jbe     short loc_1800FACEA
0x1800faca2  mov     eax, [rbp+4Fh+var_80]
0x1800faca5  lea     rdx, word_1801C45B6
0x1800facac  mov     dword ptr [rbp+4Fh+var_70], eax
0x1800facaf  mov     rax, [rdi+170h]
0x1800facb6  mov     ecx, [rax+88h]
0x1800facbc  lea     rax, aAfterMPsecfilt; "After m_pSecFilter->DoDTLSHandshake dtl"...
0x1800facc3  mov     [rbp+4Fh+var_78], rax
0x1800facc7  lea     rax, [rbp+4Fh+var_70]
0x1800faccb  mov     [rsp+0D0h+var_A0], rax
0x1800facd0  lea     rax, [rbp+4Fh+var_7C]
0x1800facd4  mov     [rsp+0D0h+var_A8], rax
0x1800facd9  lea     rax, [rbp+4Fh+var_78]
0x1800facdd  mov     [rsp+0D0h+var_B0], rax
0x1800face2  mov     [rbp+4Fh+var_7C], ecx
0x1800face5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800facea  cmp     [rbp+4Fh+var_68], 0
0x1800facef  jz      loc_1800FB4F4
0x1800facf5  cmp     [rbp+4Fh+var_80], 0
0x1800facf9  jbe     loc_1800FB4F4
0x1800facff  mov     eax, cs:CallbackContext
0x1800fad05  cmp     eax, 4
0x1800fad08  jbe     short loc_1800FAD39
0x1800fad0a  mov     eax, [rbp+4Fh+var_80]
0x1800fad0d  lea     rdx, byte_1801C45FF
0x1800fad14  mov     dword ptr [rbp+4Fh+var_70], eax
0x1800fad17  lea     rax, aDtlsHandshakeT_0; "DTLS handshake trying to send %d bytes"
0x1800fad1e  mov     [rbp+4Fh+var_78], rax
0x1800fad22  lea     rax, [rbp+4Fh+var_70]
0x1800fad26  mov     [rsp+0D0h+var_A8], rax
0x1800fad2b  lea     rax, [rbp+4Fh+var_78]
0x1800fad2f  mov     [rsp+0D0h+var_B0], rax
0x1800fad34  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800fad39  mov     r8d, [rbp+4Fh+var_80]; unsigned int
0x1800fad3d  mov     rcx, rdi; this
0x1800fad40  mov     rdx, [rbp+4Fh+var_68]; unsigned __int8 *
0x1800fad44  call    ?SendToClient@CRDPENCCONDTLSSecurityFilterStream@@AEAAJPEAEK@Z; CRDPENCCONDTLSSecurityFilterStream::SendToClient(uchar *,ulong)
0x1800fad49  mov     ebx, eax
0x1800fad4b  test    eax, eax
0x1800fad4d  jns     loc_1800FB4F4
0x1800fad53  mov     rax, cs:WPP_GLOBAL_Control
0x1800fad5a  lea     r15, WPP_GLOBAL_Control
0x1800fad61  cmp     rax, r15
0x1800fad64  jz      loc_1800FB4FB
0x1800fad6a  test    byte ptr [rax+1Ch], 8
0x1800fad6e  jz      loc_1800FB4FB
0x1800fad74  cmp     [rax+19h], sil
0x1800fad78  jb      loc_1800FB4FB
0x1800fad7e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fad83  mov     edx, 4Dh ; 'M'
0x1800fad88  lea     rcx, aSendtoclientFa; "SendToClient failed."
0x1800fad8f  jmp     loc_1800FAC6F
0x1800fad94  mov     eax, cs:CallbackContext
0x1800fad9a  cmp     eax, esi
0x1800fad9c  jbe     short loc_1800FAE08
0x1800fad9e  lea     rax, aDtlsdatatransf; "DTLSDataTransfer: DTLS hand shake is co"...
0x1800fada5  mov     dword ptr [rbp+4Fh+var_70], 68Fh
0x1800fadac  mov     [rbp+4Fh+var_58], rax
0x1800fadb0  lea     r14, aDtlshandshake; "DTLSHandshake"
0x1800fadb7  lea     rax, [rbp+4Fh+var_78]
0x1800fadbb  mov     [rbp+4Fh+var_78], r14
0x1800fadbf  mov     [rsp+0D0h+var_90], rax
0x1800fadc4  lea     r12, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fadcb  lea     rax, [rbp+4Fh+var_70]
0x1800fadcf  mov     [rbp+4Fh+var_50], r12
0x1800fadd3  mov     [rsp+0D0h+var_98], rax
0x1800fadd8  lea     rdx, byte_1801C464F
0x1800faddf  lea     rax, [rbp+4Fh+var_50]
0x1800fade3  mov     [rbp+4Fh+var_7C], 80004005h
0x1800fadea  mov     [rsp+0D0h+var_A0], rax
0x1800fadef  lea     rax, [rbp+4Fh+var_7C]
0x1800fadf3  mov     [rsp+0D0h+var_A8], rax
0x1800fadf8  lea     rax, [rbp+4Fh+var_58]
0x1800fadfc  mov     [rsp+0D0h+var_B0], rax
0x1800fae01  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800fae06  jmp     short loc_1800FAE16
0x1800fae08  lea     r14, aDtlshandshake; "DTLSHandshake"
0x1800fae0f  lea     r12, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fae16  mov     rcx, rdi; this
0x1800fae19  call    ?DTLSStopTimer@CRDPENCCONDTLSSecurityFilterStream@@AEAAJXZ; CRDPENCCONDTLSSecurityFilterStream::DTLSStopTimer(void)
0x1800fae1e  mov     ebx, eax
0x1800fae20  test    eax, eax
0x1800fae22  jns     short loc_1800FAE88
0x1800fae24  mov     rax, cs:WPP_GLOBAL_Control
0x1800fae2b  lea     r15, WPP_GLOBAL_Control
0x1800fae32  cmp     rax, r15
0x1800fae35  jz      loc_1800FB509
0x1800fae3b  test    byte ptr [rax+1Ch], 8
0x1800fae3f  jz      loc_1800FB509
0x1800fae45  cmp     [rax+19h], sil
0x1800fae49  jb      loc_1800FB509
0x1800fae4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800fae54  mov     edx, 4Ah ; 'J'
0x1800fae59  lea     rcx, aDtlsstoptimerF; "DTLSStopTimer failed"
0x1800fae60  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x1800fae64  lea     r8, WPP_310100a96f023abf06e7a5d6677d258d_Traceguids
0x1800fae6b  mov     [rsp+0D0h+var_B0], rcx
0x1800fae70  mov     r9d, eax
0x1800fae73  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fae7a  mov     rcx, [rcx+10h]
0x1800fae7e  call    WPP_SF_DsD
0x1800fae83  jmp     loc_1800FB509
0x1800fae88  mov     rcx, [rdi+170h]; this
0x1800fae8f  call    ?SetMTU@CRdpDTLSFilter@@QEAAJK@Z; CRdpDTLSFilter::SetMTU(ulong)
0x1800fae94  mov     ebx, eax
0x1800fae96  test    eax, eax
0x1800fae98  jns     loc_1800FAB66
0x1800fae9e  mov     rax, cs:WPP_GLOBAL_Control
0x1800faea5  lea     r15, WPP_GLOBAL_Control
0x1800faeac  cmp     rax, r15
0x1800faeaf  jz      loc_1800FB509
0x1800faeb5  test    byte ptr [rax+1Ch], 8
0x1800faeb9  jz      loc_1800FB509
0x1800faebf  cmp     [rax+19h], sil
0x1800faec3  jb      loc_1800FB509
0x1800faec9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800faece  mov     edx, 4Bh ; 'K'
0x1800faed3  lea     rcx, aMPsecfilterSet; "m_pSecFilter->SetMTU failed"
0x1800faeda  jmp     short loc_1800FAE60
0x1800faedc  test    r14d, r14d
0x1800faedf  jz      loc_1800FAFBC
0x1800faee5  mov     eax, cs:CallbackContext
0x1800faeeb  cmp     eax, 4
0x1800faeee  jbe     short loc_1800FAF1A
0x1800faef0  lea     rax, aDtlssendbuffer; "DTLSSendBufferOutAndReceiveAndThenCallS"...
0x1800faef7  xor     r8d, r8d
0x1800faefa  mov     [rbp+4Fh+var_78], rax
  ... truncated ...
```
