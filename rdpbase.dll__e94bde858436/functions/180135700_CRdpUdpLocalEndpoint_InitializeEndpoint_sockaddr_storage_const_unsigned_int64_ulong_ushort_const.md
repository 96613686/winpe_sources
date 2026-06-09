# CRdpUdpLocalEndpoint::InitializeEndpoint(sockaddr_storage const &,unsigned __int64,ulong,ushort const *)

- ea: `0x180135700`
- end: `0x1801361eb`
- name: `?InitializeEndpoint@CRdpUdpLocalEndpoint@@MEAAJAEBUsockaddr_storage@@_KKPEBG@Z`
- size: `2795`
- prototype: `int(CRdpUdpLocalEndpoint *__hidden this, const struct sockaddr_storage *, unsigned __int64, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001414`
- `0x1800018a4`
- `0x180001aa0`
- `0x180006e18`
- `0x180078c20`
- `0x1801281e0`
- `0x180135700`
- `0x18013693c`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180135857`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180135848`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180135848`
- `WS2_32!WSAIoctl` at `0x180135f86`
- `WS2_32!WSAIoctl` at `0x18013606c`
- `WS2_32!WSAIoctl` at `0x180135f86`
- `WS2_32!WSAIoctl` at `0x18013606c`
- `WS2_32!WSAEventSelect` at `0x1801359cb`
- `WS2_32!WSAEventSelect` at `0x1801359cb`
- `WS2_32!__imp_bind` at `0x180135b61`
- `WS2_32!__imp_bind` at `0x180135b61`
- `WS2_32!__imp_connect` at `0x180135ded`
- `WS2_32!__imp_connect` at `0x180135ded`
- `WS2_32!__imp_getsockname` at `0x180135ea2`
- `WS2_32!__imp_getsockname` at `0x180135ea2`
- `WS2_32!__imp_setsockopt` at `0x180135ac4`
- `WS2_32!__imp_setsockopt` at `0x180135c13`
- `WS2_32!__imp_setsockopt` at `0x180135ac4`
- `WS2_32!__imp_setsockopt` at `0x180135c13`
- `WS2_32!__imp_socket` at `0x180135786`
- `WS2_32!__imp_socket` at `0x180135786`
- `WS2_32!__imp_WSAGetLastError` at `0x180135796`
- `WS2_32!__imp_WSAGetLastError` at `0x1801359e8`
- `WS2_32!__imp_WSAGetLastError` at `0x180135ad3`
- `WS2_32!__imp_WSAGetLastError` at `0x180135b70`
- `WS2_32!__imp_WSAGetLastError` at `0x180135c22`
- `WS2_32!__imp_WSAGetLastError` at `0x180135dfd`
- `WS2_32!__imp_WSAGetLastError` at `0x180135eb6`
- `WS2_32!__imp_WSAGetLastError` at `0x180135f9a`
- `WS2_32!__imp_WSAGetLastError` at `0x180136080`
- `WS2_32!__imp_WSAGetLastError` at `0x180136150`
- `WS2_32!__imp_WSAGetLastError` at `0x180135796`
- `WS2_32!__imp_WSAGetLastError` at `0x1801359e8`
- `WS2_32!__imp_WSAGetLastError` at `0x180135ad3`
- `WS2_32!__imp_WSAGetLastError` at `0x180135b70`
- `WS2_32!__imp_WSAGetLastError` at `0x180135c22`
- `WS2_32!__imp_WSAGetLastError` at `0x180135dfd`
- `WS2_32!__imp_WSAGetLastError` at `0x180135eb6`
- `WS2_32!__imp_WSAGetLastError` at `0x180135f9a`
- `WS2_32!__imp_WSAGetLastError` at `0x180136080`
- `WS2_32!__imp_WSAGetLastError` at `0x180136150`

## string_xrefs

- `0x1801357ba`: `Failed to create socket`
- `0x18013591b`: `Failed to create shared handle in CRdpUdpLocalEndpoint::InitializeEndpoint`
- `0x18013587b`: `Failed to create socket event`

## pseudocode

```c
__int64 __fastcall CRdpUdpLocalEndpoint::InitializeEndpoint(
        CRdpUdpLocalEndpoint *this,
        const struct sockaddr *a2,
        int a3,
        unsigned int a4)
{
  int sa_family; // ecx
  SOCKET v8; // rax
  int Error; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  unsigned int v13; // ebx
  int *v14; // rdx
  const char **v15; // rax
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rcx
  void *v24; // rax
  CRdpUdpLocalEndpoint *v25; // rcx
  int v26; // eax
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  __int16 *v30; // rdx
  unsigned int *v31; // rax
  SOCKET v32; // rcx
  int v33; // eax
  int v34; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  CRdpUdpLocalEndpoint *v38; // rcx
  int v39; // eax
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  int v46; // edi
  int v47; // eax
  int v48; // ecx
  int v49; // r8d
  int v50; // r9d
  SOCKET v51; // rcx
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  unsigned int v55; // eax
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  const char *v59; // r13
  unsigned int v60; // eax
  unsigned int v61; // eax
  __int16 *v62; // rdx
  unsigned int v63; // eax
  int v64; // eax
  int v65; // ecx
  int v66; // r8d
  int v67; // r9d
  unsigned int *cbOutBuffer; // [rsp+28h] [rbp-79h]
  const char **lpcbBytesReturned; // [rsp+30h] [rbp-71h]
  struct ISharedHandle **lpcbBytesReturneda; // [rsp+30h] [rbp-71h]
  unsigned int *lpOverlapped; // [rsp+38h] [rbp-69h]
  char *lpOverlappeda; // [rsp+38h] [rbp-69h]
  unsigned int *lpCompletionRoutine; // [rsp+40h] [rbp-61h]
  struct ISharedHandle **v75; // [rsp+48h] [rbp-59h]
  char optval[8]; // [rsp+50h] [rbp-51h] BYREF
  unsigned int v77[2]; // [rsp+58h] [rbp-49h] BYREF
  struct ISharedHandle *v78; // [rsp+60h] [rbp-41h] BYREF
  const char *v79; // [rsp+68h] [rbp-39h] BYREF
  const char *v80; // [rsp+70h] [rbp-31h] BYREF
  const char *v81; // [rsp+78h] [rbp-29h] BYREF
  const char *v82; // [rsp+80h] [rbp-21h] BYREF
  int v83; // [rsp+88h] [rbp-19h] BYREF
  DWORD cbBytesReturned; // [rsp+8Ch] [rbp-15h] BYREF
  int namelen; // [rsp+90h] [rbp-11h] BYREF
  _DWORD vInBuffer[4]; // [rsp+98h] [rbp-9h] BYREF
  _DWORD v87[4]; // [rsp+A8h] [rbp+7h] BYREF

  v77[0] = a4;
  vInBuffer[0] = -158738488;
  vInBuffer[1] = 1131114271;
  sa_family = a2->sa_family;
  vInBuffer[2] = 1340429194;
  vInBuffer[3] = 583225827;
  v87[0] = -1539184878;
  v87[1] = 1137341775;
  v87[2] = -301095036;
  v87[3] = 1835061060;
  cbBytesReturned = 0;
  v8 = socket(sa_family, 2, 17);
  if ( v8 == -1 )
  {
    Error = WSAGetLastError();
    v13 = Error;
    if ( Error > 0 )
      v13 = (unsigned __int16)Error | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v83 = 202;
      v78 = (struct ISharedHandle *)"Failed to create socket";
      *(_QWORD *)v77 = "InitializeEndpoint";
      v79 = "Error condition failed";
      v82 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      v75 = &v78;
      v14 = (int *)byte_1801D4B41;
      lpCompletionRoutine = v77;
      lpOverlapped = (unsigned int *)&v83;
      lpcbBytesReturned = &v82;
      v15 = &v79;
LABEL_6:
      *(_DWORD *)optval = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v10,
        (_DWORD)v14,
        v11,
        v12,
        (__int64)v15,
        (__int64)optval,
        (__int64)lpcbBytesReturned,
        (__int64)lpOverlapped,
        (__int64)lpCompletionRoutine,
        (__int64)v75);
      return v13;
    }
    return v13;
  }
  _InterlockedExchange64((volatile __int64 *)this + 84, v8);
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      *(_DWORD *)optval = 211;
      v79 = "Failed to create socket event";
      v82 = "InitializeEndpoint";
      *(_QWORD *)v77 = "Error condition failed";
      v78 = (struct ISharedHandle *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      v83 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v18,
        (unsigned int)&word_1801D528E,
        v19,
        v20,
        (__int64)v77,
        (__int64)&v83,
        (__int64)&v78,
        (__int64)optval,
        (__int64)&v82,
        (__int64)&v79);
    }
    return v13;
  }
  v78 = 0;
  v13 = SharedHandle::CreateInstance(EventW, &v78);
  if ( (v13 & 0x80000000) != 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      *(_DWORD *)optval = 215;
      v79 = "Failed to create shared handle in CRdpUdpLocalEndpoint::InitializeEndpoint";
      v82 = "InitializeEndpoint";
      *(_QWORD *)v77 = "Error HResult failed";
      v78 = (struct ISharedHandle *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      v83 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_1801D532D,
        v21,
        v22,
        (__int64)v77,
        (__int64)&v83,
        (__int64)&v78,
        (__int64)optval,
        (__int64)&v82,
        (__int64)&v79);
    }
    return v13;
  }
  v23 = *((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v78;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v24 = (void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 7) + 24LL))(*((_QWORD *)this + 7));
  if ( WSAEventSelect(*((_QWORD *)this + 84), v24, 3) == -1 )
  {
    v26 = WSAGetLastError();
    v13 = v26;
    if ( v26 > 0 )
      v13 = (unsigned __int16)v26 | 0x80070000;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_83;
    *(_DWORD *)optval = 222;
    v79 = "Failed to select socket event";
    v30 = &word_1801D4AF6;
    v78 = (struct ISharedHandle *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
    *(_QWORD *)v77 = "Error condition failed";
    lpOverlappeda = optval;
    lpcbBytesReturneda = &v78;
    cbOutBuffer = (unsigned int *)&v83;
    v31 = v77;
    v83 = v13;
LABEL_23:
    v82 = "InitializeEndpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v27,
      (_DWORD)v30,
      v28,
      v29,
      (__int64)v31,
      (__int64)cbOutBuffer,
      (__int64)lpcbBytesReturneda,
      (__int64)lpOverlappeda,
      (__int64)&v82,
      (__int64)&v79);
LABEL_83:
    if ( !v13 )
    {
      v64 = WSAGetLastError();
      v13 = v64;
      if ( v64 > 0 )
        v13 = (unsigned __int16)v64 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v81 = "InitializeEndpoint";
        v79 = "Outgoing connection request failed";
        LODWORD(v78) = 348;
        v80 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
        v77[0] = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v65,
          (unsigned int)word_1801D4EAA,
          v66,
          v67,
          (__int64)&v79,
          (__int64)v77,
          (__int64)&v80,
          (__int64)&v78,
          (__int64)&v81);
      }
    }
    return v13;
  }
  if ( !*((_DWORD *)this + 157) )
  {
    v13 = CRdpUdpLocalEndpoint::SetSocketOptions(v25, *((_QWORD *)this + 84), 0, a2->sa_family == 23, 0xFFFFFFFF);
    if ( (v13 & 0x80000000) != 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v80 = "InitializeEndpoint";
        v81 = "Failed to set socket options";
        LODWORD(v78) = 266;
        v82 = "Error HResult failed";
        v79 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
        v77[0] = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v43,
          (unsigned int)byte_1801D5489,
          v44,
          v45,
          (__int64)&v82,
          (__int64)v77,
          (__int64)&v79,
          (__int64)&v78,
          (__int64)&v80,
          (__int64)&v81);
      }
      return v13;
    }
    v46 = connect(*((_QWORD *)this + 84), a2, a3);
    if ( v46 )
    {
      v47 = WSAGetLastError();
      v13 = v47;
      if ( v47 > 0 )
        v13 = (unsigned __int16)v47 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v80 = "InitializeEndpoint";
        v81 = "Failed to connect socket";
        LODWORD(v78) = 273;
        v82 = "Error condition failed";
        v79 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
        v77[0] = v13;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v48,
          (unsigned int)&dword_1801D48BC,
          v49,
          v50,
          (__int64)&v82,
          (__int64)v77,
          (__int64)&v79,
          (__int64)&v78,
          (__int64)&v80,
          (__int64)&v81);
      }
      goto LABEL_82;
    }
LABEL_53:
    v51 = *((_QWORD *)this + 84);
    namelen = 128;
    if ( getsockname(v51, (struct sockaddr *)this + 5, &namelen) == -1 )
    {
      v13 = -2147024809;
      v46 = WSAGetLastError();
      if ( (unsigned int)CallbackContext > 2 )
      {
        v81 = (const char *)this;
        v80 = "InitializeEndpoint";
        LODWORD(v78) = 287;
        v79 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
        if ( v46 > 0 )
          v55 = (unsigned __int16)v46 | 0x80070000;
        else
          v55 = v46;
        v77[0] = v55;
        v82 = "UDP local endpoint failed to initialize";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v52,
          (unsigned int)byte_1801D575D,
          v53,
          v54,
          (__int64)&v82,
          (__int64)v77,
          (__int64)&v79,
          (__int64)&v78,
          (__int64)&v80,
          (__int64)&v81);
      }
      goto LABEL_82;
    }
    if ( WSAIoctl(*((_QWORD *)this + 84), 0xC8000006, vInBuffer, 0x10u, (char *)this + 64, 8u, &cbBytesReturned, 0, 0) != -1 )
    {
      if ( WSAIoctl(*((_QWORD *)this + 84), 0xC8000006, v87, 0x10u, (char *)this + 72, 8u, &cbBytesReturned, 0, 0) != -1 )
        return v13;
      v13 = -2147418113;
      v46 = WSAGetLastError();
      v59 = "UDP local endpoint failed to query WSASendMsg";
      if ( (unsigned int)CallbackContext > 3 )
      {
        if ( v46 > 0 )
          v63 = (unsigned __int16)v46 | 0x80070000;
        else
          v63 = v46;
        LODWORD(v78) = v63;
        v80 = "UDP local endpoint failed to query WSASendMsg";
        v81 = (char *)this + 208;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v56,
          (unsigned int)&unk_1801D5720,
          v57,
          v58,
          (__int64)&v80,
          (__int64)&v81,
          (__int64)&v78);
      }
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_82;
      v81 = "InitializeEndpoint";
      LODWORD(v78) = 336;
      v80 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      if ( v46 > 0 )
        v61 = (unsigned __int16)v46 | 0x80070000;
      else
        v61 = v46;
      v62 = (__int16 *)byte_1801D5673;
      goto LABEL_81;
    }
    v13 = -2147418113;
    v46 = WSAGetLastError();
    v59 = "UDP local endpoint failed to query WSARecvMsg";
    if ( (unsigned int)CallbackContext > 3 )
    {
      if ( v46 > 0 )
        v60 = (unsigned __int16)v46 | 0x80070000;
      else
        v60 = v46;
      LODWORD(v78) = v60;
      v80 = "UDP local endpoint failed to query WSARecvMsg";
      v81 = (char *)this + 208;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v56,
        (unsigned int)byte_1801D581D,
        v57,
        v58,
        (__int64)&v80,
        (__int64)&v81,
        (__int64)&v78);
    }
    if ( (unsigned int)CallbackContext > 2 )
    {
      v81 = "InitializeEndpoint";
      LODWORD(v78) = 312;
      v80 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      if ( v46 > 0 )
        v61 = (unsigned __int16)v46 | 0x80070000;
      else
        v61 = v46;
      v62 = word_1801D585A;
LABEL_81:
      v77[0] = v61;
      v79 = v59;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v56,
        (_DWORD)v62,
        v57,
        v58,
        (__int64)&v79,
        (__int64)v77,
        (__int64)&v80,
        (__int64)&v78,
        (__int64)&v81);
    }
LABEL_82:
    if ( v46 != -1 )
      return v13;
    goto LABEL_83;
  }
  LODWORD(v78) = 1;
  if ( a2->sa_family == 23 )
  {
    v32 = *((_QWORD *)this + 84);
    *(_DWORD *)optval = 10;
    if ( setsockopt(v32, 41, 23, optval, 4) == -1 )
    {
      v33 = WSAGetLastError();
      v13 = v33;
      if ( v33 > 0 )
        v13 = (unsigned __int16)v33 | 0x80070000;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_83;
      v83 = 240;
      v79 = "IPV6_PROTECTION_LEVEL failed";
      v30 = &word_1801D56B6;
      v80 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      v81 = "Error condition failed";
      lpOverlappeda = (char *)&v83;
      lpcbBytesReturneda = (struct ISharedHandle **)&v80;
      cbOutBuffer = v77;
      v31 = (unsigned int *)&v81;
      v77[0] = v13;
      goto LABEL_23;
    }
  }
  if ( bind(*((_QWORD *)this + 84), a2, a3) == -1 )
  {
    v34 = WSAGetLastError();
    v13 = v34;
    if ( v34 > 0 )
      v13 = (unsigned __int16)v34 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v80 = "InitializeEndpoint";
      v81 = "Bind failed";
      v77[0] = 245;
      v82 = "Error condition failed";
      v79 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      *(_DWORD *)optval = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v35,
        (unsigned int)byte_1801D4BAB,
        v36,
        v37,
        (__int64)&v82,
        (__int64)optval,
        (__int64)&v79,
        (__int64)v77,
        (__int64)&v80,
        (__int64)&v81);
    }
    goto LABEL_83;
  }
  if ( setsockopt(*((_QWORD *)this + 84), 0xFFFF, -5, (const char *)&v78, 4) == -1 )
  {
    v39 = WSAGetLastError();
    v13 = v39;
    if ( v39 > 0 )
      v13 = (unsigned __int16)v39 | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v80 = "InitializeEndpoint";
      v81 = "SO_EXCLUSIVEADDRUSE failed";
      v77[0] = 250;
      v82 = "Error condition failed";
      v79 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
      *(_DWORD *)optval = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v40,
        (unsigned int)&dword_1801D5004,
        v41,
        v42,
        (__int64)&v82,
        (__int64)optval,
        (__int64)&v79,
        (__int64)v77,
        (__int64)&v80,
        (__int64)&v81);
    }
    goto LABEL_83;
  }
  v13 = CRdpUdpLocalEndpoint::SetSocketOptions(v38, *((_QWORD *)this + 84), 1, a2->sa_family == 23, v77[0]);
  if ( (v13 & 0x80000000) == 0 )
    goto LABEL_53;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v80 = "InitializeEndpoint";
    v81 = "Failed to set socket options";
    v14 = &dword_1801D4D0C;
    v77[0] = 257;
    v82 = "Error HResult failed";
    v75 = (struct ISharedHandle **)&v81;
    lpCompletionRoutine = (unsigned int *)&v80;
    lpOverlapped = v77;
    lpcbBytesReturned = &v79;
    v15 = &v82;
    v79 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudplocalendpoint.cpp";
    goto LABEL_6;
  }
  return v13;
}

```

## disassembly

```asm
0x180135700  mov     [rsp-8+arg_18], rbx
0x180135705  push    rbp
0x180135706  push    rsi
0x180135707  push    rdi
0x180135708  push    r12
0x18013570a  push    r13
0x18013570c  push    r14
0x18013570e  push    r15
0x180135710  lea     rbp, [rsp-1Fh]
0x180135715  sub     rsp, 0C0h
0x18013571c  mov     rax, cs:__security_cookie
0x180135723  xor     rax, rsp
0x180135726  mov     [rbp+4Fh+var_38], rax
0x18013572a  mov     r13, r8
0x18013572d  mov     [rbp+4Fh+var_98], r9d
0x180135731  mov     r8d, 11h; protocol
0x180135737  mov     [rbp+4Fh+vInBuffer], 0F689D7C8h
0x18013573e  mov     r14, rcx
0x180135741  mov     [rbp+4Fh+var_54], 436B6F1Fh
0x180135748  movzx   ecx, word ptr [rdx]; af
0x18013574b  mov     rdi, rdx
0x18013574e  mov     [rbp+4Fh+var_50], 4FE5538Ah
0x180135755  lea     r15d, [r8-0Fh]
0x180135759  mov     [rbp+4Fh+var_4C], 22C351E3h
0x180135760  mov     edx, r15d; type
0x180135763  mov     [rbp+4Fh+var_48], 0A441E712h
0x18013576a  mov     [rbp+4Fh+var_44], 43CA754Fh
0x180135771  mov     [rbp+4Fh+var_40], 0EE0DA784h
0x180135778  mov     [rbp+4Fh+var_3C], 6D60CF44h
0x18013577f  mov     [rbp+4Fh+cbBytesReturned], 0
0x180135786  call    cs:__imp_socket
0x18013578c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180135790  jnz     loc_180135837
0x180135796  call    cs:__imp_WSAGetLastError
0x18013579c  mov     ebx, eax
0x18013579e  test    eax, eax
0x1801357a0  jle     short loc_1801357AB
0x1801357a2  movzx   ebx, ax
0x1801357a5  or      ebx, 80070000h
0x1801357ab  mov     eax, cs:CallbackContext
0x1801357b1  cmp     eax, r15d
0x1801357b4  jbe     loc_1801361C2
0x1801357ba  lea     rax, aFailedToCreate_50; "Failed to create socket"
0x1801357c1  mov     [rbp+4Fh+var_68], 0CAh
0x1801357c8  mov     [rbp+4Fh+var_90], rax
0x1801357cc  lea     r15, aInitializeendp_0; "InitializeEndpoint"
0x1801357d3  lea     rax, aErrorCondition; "Error condition failed"
0x1801357da  mov     qword ptr [rbp+4Fh+var_98], r15
0x1801357de  mov     [rbp+4Fh+var_88], rax
0x1801357e2  lea     r12, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801357e9  lea     rax, [rbp+4Fh+var_90]
0x1801357ed  mov     [rbp+4Fh+var_70], r12
0x1801357f1  mov     [rsp+0F0h+var_A8], rax
0x1801357f6  lea     rdx, byte_1801D4B41
0x1801357fd  lea     rax, [rbp+4Fh+var_98]
0x180135801  mov     [rsp+0F0h+lpCompletionRoutine], rax
0x180135806  lea     rax, [rbp+4Fh+var_68]
0x18013580a  mov     [rsp+0F0h+lpOverlapped], rax
0x18013580f  lea     rax, [rbp+4Fh+var_70]
0x180135813  mov     [rsp+0F0h+lpcbBytesReturned], rax
0x180135818  lea     rax, [rbp+4Fh+optval]
0x18013581c  mov     qword ptr [rsp+0F0h+cbOutBuffer], rax
0x180135821  lea     rax, [rbp+4Fh+var_88]
0x180135825  mov     dword ptr [rbp+4Fh+optval], ebx
0x180135828  mov     qword ptr [rsp+0F0h+optlen], rax
0x18013582d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180135832  jmp     loc_1801361C2
0x180135837  xchg    rax, [r14+2A0h]
0x18013583e  xor     r9d, r9d; lpName
0x180135841  xor     r8d, r8d; bInitialState
0x180135844  xor     edx, edx; bManualReset
0x180135846  xor     ecx, ecx; lpEventAttributes
0x180135848  call    cs:__imp_CreateEventW
0x18013584e  test    rax, rax
0x180135851  jnz     loc_1801358EE
0x180135857  call    cs:__imp_GetLastError
0x18013585d  mov     ebx, eax
0x18013585f  test    eax, eax
0x180135861  jle     short loc_18013586C
0x180135863  movzx   ebx, ax
0x180135866  or      ebx, 80070000h
0x18013586c  mov     eax, cs:CallbackContext
0x180135872  cmp     eax, r15d
0x180135875  jbe     loc_1801361C2
0x18013587b  lea     rax, aFailedToCreate_86; "Failed to create socket event"
0x180135882  mov     dword ptr [rbp+4Fh+optval], 0D3h
0x180135889  mov     [rbp+4Fh+var_88], rax
0x18013588d  lea     r15, aInitializeendp_0; "InitializeEndpoint"
0x180135894  lea     rax, aErrorCondition; "Error condition failed"
0x18013589b  mov     [rbp+4Fh+var_70], r15
0x18013589f  mov     qword ptr [rbp+4Fh+var_98], rax
0x1801358a3  lea     r12, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801358aa  lea     rax, [rbp+4Fh+var_88]
0x1801358ae  mov     [rbp+4Fh+var_90], r12
0x1801358b2  mov     [rsp+0F0h+var_A8], rax
0x1801358b7  lea     rdx, word_1801D528E
0x1801358be  lea     rax, [rbp+4Fh+var_70]
0x1801358c2  mov     [rbp+4Fh+var_68], ebx
0x1801358c5  mov     [rsp+0F0h+lpCompletionRoutine], rax
0x1801358ca  lea     rax, [rbp+4Fh+optval]
0x1801358ce  mov     [rsp+0F0h+lpOverlapped], rax
0x1801358d3  lea     rax, [rbp+4Fh+var_90]
0x1801358d7  mov     [rsp+0F0h+lpcbBytesReturned], rax
0x1801358dc  lea     rax, [rbp+4Fh+var_68]
0x1801358e0  mov     qword ptr [rsp+0F0h+cbOutBuffer], rax
0x1801358e5  lea     rax, [rbp+4Fh+var_98]
0x1801358e9  jmp     loc_180135828
0x1801358ee  lea     rdx, [rbp+4Fh+var_90]; struct ISharedHandle **
0x1801358f2  mov     [rbp+4Fh+var_90], 0
0x1801358fa  mov     rcx, rax; void *
0x1801358fd  call    ?CreateInstance@SharedHandle@@SAJPEAXPEAPEAUISharedHandle@@@Z; SharedHandle::CreateInstance(void *,ISharedHandle * *)
0x180135902  mov     ebx, eax
0x180135904  test    eax, eax
0x180135906  jns     loc_18013598E
0x18013590c  mov     ecx, cs:CallbackContext
0x180135912  cmp     ecx, r15d
0x180135915  jbe     loc_1801361C2
0x18013591b  lea     rax, aFailedToCreate_18; "Failed to create shared handle in CRdpU"...
0x180135922  mov     dword ptr [rbp+4Fh+optval], 0D7h
0x180135929  mov     [rbp+4Fh+var_88], rax
0x18013592d  lea     r15, aInitializeendp_0; "InitializeEndpoint"
0x180135934  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18013593b  mov     [rbp+4Fh+var_70], r15
0x18013593f  mov     qword ptr [rbp+4Fh+var_98], rax
0x180135943  lea     r12, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18013594a  lea     rax, [rbp+4Fh+var_88]
0x18013594e  mov     [rbp+4Fh+var_90], r12
0x180135952  mov     [rsp+0F0h+var_A8], rax
0x180135957  lea     rdx, byte_1801D532D
0x18013595e  lea     rax, [rbp+4Fh+var_70]
0x180135962  mov     [rbp+4Fh+var_68], ebx
0x180135965  mov     [rsp+0F0h+lpCompletionRoutine], rax
0x18013596a  lea     rax, [rbp+4Fh+optval]
0x18013596e  mov     [rsp+0F0h+lpOverlapped], rax
0x180135973  lea     rax, [rbp+4Fh+var_90]
0x180135977  mov     [rsp+0F0h+lpcbBytesReturned], rax
0x18013597c  lea     rax, [rbp+4Fh+var_68]
0x180135980  mov     qword ptr [rsp+0F0h+cbOutBuffer], rax
0x180135985  lea     rax, [rbp+4Fh+var_98]
0x180135989  jmp     loc_180135828
0x18013598e  mov     rcx, [r14+38h]
0x180135992  mov     rax, [rbp+4Fh+var_90]
0x180135996  mov     [r14+38h], rax
0x18013599a  test    rcx, rcx
0x18013599d  jz      short loc_1801359AB
0x18013599f  mov     rax, [rcx]
0x1801359a2  mov     rax, [rax+10h]
0x1801359a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801359ab  mov     rcx, [r14+38h]
0x1801359af  mov     rax, [rcx]
0x1801359b2  mov     rax, [rax+18h]
0x1801359b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801359bb  mov     rcx, [r14+2A0h]; s
0x1801359c2  mov     r8d, 3; lNetworkEvents
0x1801359c8  mov     rdx, rax; hEventObject
0x1801359cb  call    cs:__imp_WSAEventSelect
0x1801359d1  lea     r15, aInitializeendp_0; "InitializeEndpoint"
0x1801359d8  lea     r12, aOnecoreTermsrv_26; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801359df  cmp     eax, 0FFFFFFFFh
0x1801359e2  jnz     loc_180135A7C
0x1801359e8  call    cs:__imp_WSAGetLastError
0x1801359ee  mov     ebx, eax
0x1801359f0  mov     esi, 80070000h
0x1801359f5  test    eax, eax
0x1801359f7  jle     short loc_1801359FE
0x1801359f9  movzx   ebx, ax
0x1801359fc  or      ebx, esi
0x1801359fe  mov     eax, cs:CallbackContext
0x180135a04  cmp     eax, 2
0x180135a07  jbe     loc_18013614C
0x180135a0d  lea     rax, aFailedToSelect; "Failed to select socket event"
0x180135a14  mov     dword ptr [rbp+4Fh+optval], 0DEh
0x180135a1b  mov     [rbp+4Fh+var_88], rax
0x180135a1f  lea     rdx, word_1801D4AF6
0x180135a26  lea     rax, aErrorCondition; "Error condition failed"
0x180135a2d  mov     [rbp+4Fh+var_90], r12
0x180135a31  mov     qword ptr [rbp+4Fh+var_98], rax
0x180135a35  lea     rax, [rbp+4Fh+var_88]
0x180135a39  mov     [rsp+0F0h+var_A8], rax
0x180135a3e  lea     rax, [rbp+4Fh+var_70]
0x180135a42  mov     [rsp+0F0h+lpCompletionRoutine], rax
0x180135a47  lea     rax, [rbp+4Fh+optval]
0x180135a4b  mov     [rsp+0F0h+lpOverlapped], rax
0x180135a50  lea     rax, [rbp+4Fh+var_90]
0x180135a54  mov     [rsp+0F0h+lpcbBytesReturned], rax
0x180135a59  lea     rax, [rbp+4Fh+var_68]
0x180135a5d  mov     qword ptr [rsp+0F0h+cbOutBuffer], rax
0x180135a62  lea     rax, [rbp+4Fh+var_98]
0x180135a66  mov     [rbp+4Fh+var_68], ebx
0x180135a69  mov     [rbp+4Fh+var_70], r15
0x180135a6d  mov     qword ptr [rsp+0F0h+optlen], rax
0x180135a72  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180135a77  jmp     loc_18013614C
0x180135a7c  cmp     dword ptr [r14+274h], 0
0x180135a84  mov     esi, 80070000h
0x180135a89  mov     ebx, 17h
0x180135a8e  jz      loc_180135D45
0x180135a94  mov     dword ptr [rbp+4Fh+var_90], 1
0x180135a9b  cmp     [rdi], bx
0x180135a9e  jnz     loc_180135B54
0x180135aa4  mov     rcx, [r14+2A0h]; s
0x180135aab  lea     r9, [rbp+4Fh+optval]; optval
0x180135aaf  mov     r8d, ebx; optname
0x180135ab2  mov     dword ptr [rbp+4Fh+optval], 0Ah
0x180135ab9  lea     edx, [rbx+12h]; level
0x180135abc  mov     [rsp+0F0h+optlen], 4; optlen
0x180135ac4  call    cs:__imp_setsockopt
0x180135aca  cmp     eax, 0FFFFFFFFh
0x180135acd  jnz     loc_180135B54
0x180135ad3  call    cs:__imp_WSAGetLastError
0x180135ad9  mov     ebx, eax
0x180135adb  test    eax, eax
0x180135add  jle     short loc_180135AE4
0x180135adf  movzx   ebx, ax
0x180135ae2  or      ebx, esi
0x180135ae4  mov     eax, cs:CallbackContext
0x180135aea  cmp     eax, 2
0x180135aed  jbe     loc_18013614C
0x180135af3  lea     rax, aIpv6Protection; "IPV6_PROTECTION_LEVEL failed"
0x180135afa  mov     [rbp+4Fh+var_68], 0F0h
0x180135b01  mov     [rbp+4Fh+var_88], rax
0x180135b05  lea     rdx, word_1801D56B6
0x180135b0c  lea     rax, aErrorCondition; "Error condition failed"
0x180135b13  mov     [rbp+4Fh+var_80], r12
0x180135b17  mov     [rbp+4Fh+var_78], rax
0x180135b1b  lea     rax, [rbp+4Fh+var_88]
0x180135b1f  mov     [rsp+0F0h+var_A8], rax
0x180135b24  lea     rax, [rbp+4Fh+var_70]
0x180135b28  mov     [rsp+0F0h+lpCompletionRoutine], rax
0x180135b2d  lea     rax, [rbp+4Fh+var_68]
0x180135b31  mov     [rsp+0F0h+lpOverlapped], rax
0x180135b36  lea     rax, [rbp+4Fh+var_80]
0x180135b3a  mov     [rsp+0F0h+lpcbBytesReturned], rax
0x180135b3f  lea     rax, [rbp+4Fh+var_98]
0x180135b43  mov     qword ptr [rsp+0F0h+cbOutBuffer], rax
0x180135b48  lea     rax, [rbp+4Fh+var_78]
0x180135b4c  mov     [rbp+4Fh+var_98], ebx
0x180135b4f  jmp     loc_180135A69
0x180135b54  mov     rcx, [r14+2A0h]; s
0x180135b5b  mov     r8d, r13d; namelen
0x180135b5e  mov     rdx, rdi; name
0x180135b61  call    cs:__imp_bind
0x180135b67  cmp     eax, 0FFFFFFFFh
0x180135b6a  jnz     loc_180135BF5
0x180135b70  call    cs:__imp_WSAGetLastError
0x180135b76  mov     ebx, eax
0x180135b78  test    eax, eax
0x180135b7a  jle     short loc_180135B81
0x180135b7c  movzx   ebx, ax
0x180135b7f  or      ebx, esi
0x180135b81  mov     eax, cs:CallbackContext
0x180135b87  cmp     eax, 2
0x180135b8a  jbe     loc_18013614C
0x180135b90  lea     rax, aBindFailed; "Bind failed"
0x180135b97  mov     [rbp+4Fh+var_80], r15
0x180135b9b  mov     [rbp+4Fh+var_78], rax
0x180135b9f  lea     rdx, byte_1801D4BAB
0x180135ba6  lea     rax, aErrorCondition; "Error condition failed"
0x180135bad  mov     [rbp+4Fh+var_98], 0F5h
0x180135bb4  mov     [rbp+4Fh+var_70], rax
0x180135bb8  lea     rax, [rbp+4Fh+var_78]
0x180135bbc  mov     [rsp+0F0h+var_A8], rax
0x180135bc1  lea     rax, [rbp+4Fh+var_80]
0x180135bc5  mov     [rsp+0F0h+lpCompletionRoutine], rax
0x180135bca  lea     rax, [rbp+4Fh+var_98]
0x180135bce  mov     [rsp+0F0h+lpOverlapped], rax
0x180135bd3  lea     rax, [rbp+4Fh+var_88]
0x180135bd7  mov     [rsp+0F0h+lpcbBytesReturned], rax
0x180135bdc  lea     rax, [rbp+4Fh+optval]
0x180135be0  mov     qword ptr [rsp+0F0h+cbOutBuffer], rax
0x180135be5  lea     rax, [rbp+4Fh+var_70]
0x180135be9  mov     [rbp+4Fh+var_88], r12
0x180135bed  mov     dword ptr [rbp+4Fh+optval], ebx
0x180135bf0  jmp     loc_180135A6D
0x180135bf5  mov     rcx, [r14+2A0h]; s
0x180135bfc  lea     r9, [rbp+4Fh+var_90]; optval
0x180135c00  mov     edx, 0FFFFh; level
0x180135c05  mov     [rsp+0F0h+optlen], 4; optlen
0x180135c0d  mov     r8d, 0FFFFFFFBh; optname
0x180135c13  call    cs:__imp_setsockopt
0x180135c19  cmp     eax, 0FFFFFFFFh
0x180135c1c  jnz     loc_180135CA7
0x180135c22  call    cs:__imp_WSAGetLastError
0x180135c28  mov     ebx, eax
0x180135c2a  test    eax, eax
0x180135c2c  jle     short loc_180135C33
0x180135c2e  movzx   ebx, ax
0x180135c31  or      ebx, esi
0x180135c33  mov     eax, cs:CallbackContext
0x180135c39  cmp     eax, 2
0x180135c3c  jbe     loc_18013614C
0x180135c42  lea     rax, aSoExclusiveadd; "SO_EXCLUSIVEADDRUSE failed"
0x180135c49  mov     [rbp+4Fh+var_80], r15
0x180135c4d  mov     [rbp+4Fh+var_78], rax
0x180135c51  lea     rdx, dword_1801D5004
0x180135c58  lea     rax, aErrorCondition; "Error condition failed"
0x180135c5f  mov     [rbp+4Fh+var_98], 0FAh
0x180135c66  mov     [rbp+4Fh+var_70], rax
0x180135c6a  lea     rax, [rbp+4Fh+var_78]
0x180135c6e  mov     [rsp+0F0h+var_A8], rax
  ... truncated ...
```
