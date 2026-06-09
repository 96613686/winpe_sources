# CRDPENCCONStream::Initialize(IRDPENCPlatformContext *,IRDPENCConnectorEndpoint *,unsigned __int64,ulong,ulong,ulong,ulong)

- ea: `0x18003f900`
- end: `0x1800403a1`
- name: `?Initialize@CRDPENCCONStream@@IEAAJPEAUIRDPENCPlatformContext@@PEAUIRDPENCConnectorEndpoint@@_KKKKK@Z`
- size: `2721`
- prototype: `__int64 __fastcall(CRDPENCCONStream *__hidden this, struct IRDPENCPlatformContext *, struct IRDPENCConnectorEndpoint *, unsigned __int64, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003f5c8`

## callees

- `0x180018a10`
- `0x180019a80`
- `0x180019ab0`
- `0x18001b3f8`
- `0x18001d8c0`
- `0x18001e164`
- `0x18003f900`
- `0x180046a84`
- `0x180047464`
- `0x180047c24`
- `0x180047f1c`
- `0x1800480a0`
- `0x18004b600`
- `0x18006e7d4`
- `0x18006f440`
- `0x1800711c8`
- `0x1800721d4`
- `0x180072470`
- `0x180078c20`
- `0x18007969c`
- `0x1800888d8`
- `0x1800e4f70`
- `0x18015e498`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003fbfd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003fbfd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180040164`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180040164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fc8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fc8a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003fc78`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003fc78`
- `WS2_32!WSAIoctl` at `0x18003ff40`
- `WS2_32!WSAIoctl` at `0x18003ff40`
- `WS2_32!__imp_setsockopt` at `0x18003fe5c`
- `WS2_32!__imp_setsockopt` at `0x18003fe8a`
- `WS2_32!__imp_setsockopt` at `0x18003feb1`
- `WS2_32!__imp_setsockopt` at `0x18003fe5c`
- `WS2_32!__imp_setsockopt` at `0x18003fe8a`
- `WS2_32!__imp_setsockopt` at `0x18003feb1`
- `WS2_32!__imp_WSAGetLastError` at `0x18003ff66`
- `WS2_32!__imp_WSAGetLastError` at `0x18003ff66`
- `WS2_32!__imp_WSAStartup` at `0x18003fde0`
- `WS2_32!__imp_WSAStartup` at `0x18003fde0`
- `OLEAUT32!__imp_VariantInit` at `0x18003f97d`
- `OLEAUT32!__imp_VariantInit` at `0x18003f97d`
- `OLEAUT32!__imp_VariantClear` at `0x180040338`
- `OLEAUT32!__imp_VariantClear` at `0x180040338`

## string_xrefs

- `0x18003fd2b`: `Failed to create IO Context pool`
- `0x18003fdcb`: `Failed to create Large StreamBuffer pool`
- `0x18003fd7b`: `Failed to create Small StreamBuffer pool`
- `0x180040208`: `Failed to associate sock with IO completion port.`

## pseudocode

```c
__int64 __fastcall CRDPENCCONStream::Initialize(
        CRDPENCCONStream *this,
        struct IRDPENCPlatformContext *a2,
        struct IRDPENCConnectorEndpoint *a3,
        SOCKET a4,
        unsigned int a5,
        unsigned int a6)
{
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  signed int Instance; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v14; // edx
  const char *v15; // rcx
  PVOID *v16; // rax
  unsigned int v17; // eax
  int v18; // eax
  char v19; // bl
  unsigned int v20; // eax
  int v21; // eax
  char v22; // bl
  unsigned int v23; // eax
  int v24; // eax
  char v25; // bl
  unsigned int v26; // eax
  unsigned int v27; // eax
  HANDLE EventW; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  signed int LastError; // ebx
  unsigned int v32; // eax
  bool v33; // sf
  __int64 v34; // rdx
  __int64 v35; // rcx
  unsigned int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  unsigned int v39; // eax
  unsigned int v40; // eax
  int v41; // eax
  unsigned int v42; // eax
  SOCKET v43; // rsi
  SOCKET v44; // rcx
  int Error; // ebx
  unsigned int v46; // eax
  unsigned int v47; // eax
  __int64 v48; // rsi
  unsigned int v49; // eax
  const wchar_t *bstrVal; // rbx
  int v51; // eax
  char v52; // bl
  PVOID *v53; // rcx
  unsigned int v54; // eax
  __int64 v55; // rbx
  int v56; // edi
  unsigned int v57; // eax
  unsigned int v58; // eax
  unsigned int v59; // eax
  int v60; // ebx
  int v61; // edi
  unsigned int v62; // eax
  unsigned int TLSLoggerInstance; // eax
  unsigned int v64; // eax
  __int64 v65; // rcx
  void *v66; // rcx
  char optval[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v69; // [rsp+58h] [rbp-A8h] BYREF
  void *v70; // [rsp+60h] [rbp-A0h] BYREF
  SOCKET s; // [rsp+68h] [rbp-98h] BYREF
  int v72; // [rsp+70h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  __int64 v74; // [rsp+90h] [rbp-70h]
  CRDPENCCONStream *v75; // [rsp+98h] [rbp-68h]
  GUID ActivityId; // [rsp+A0h] [rbp-60h] BYREF
  __int64 vInBuffer; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v78; // [rsp+B8h] [rbp-48h]
  __int128 v79; // [rsp+C0h] [rbp-40h] BYREF
  WSAData WSAData; // [rsp+D0h] [rbp-30h] BYREF

  s = a4;
  vInBuffer = 0;
  v78 = 0;
  *(_DWORD *)optval = 0;
  v70 = 0;
  v69 = 0;
  v79 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(&WSAData, 0, sizeof(WSAData));
  VariantInit(&pvarg);
  v9 = (*(__int64 (__fastcall **)(struct IRDPENCConnectorEndpoint *))(*(_QWORD *)a3 + 104LL))(a3);
  v10 = *(_QWORD *)a3;
  v72 = v9;
  v74 = (*(__int64 (__fastcall **)(struct IRDPENCConnectorEndpoint *))(v10 + 80))(a3);
  *((_DWORD *)this + 7) |= 2u;
  v11 = *(_QWORD *)a3;
  v75 = (CRDPENCCONStream *)((char *)this + 8);
  Instance = (*(__int64 (__fastcall **)(struct IRDPENCConnectorEndpoint *, __int128 *))(v11 + 112))(a3, &v79);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_132;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 16;
    v15 = "Failed to retrieve the connection UUID";
    goto LABEL_131;
  }
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v17, a5, a6);
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  Instance = -2147467259;
  if ( a2 )
  {
    v18 = (**(__int64 (__fastcall ***)(struct IRDPENCPlatformContext *, GUID *, __int64 *))a2)(
            a2,
            &IID_IRDPCollection,
            &v69);
    v19 = v18;
    if ( v18 >= 0 )
      goto LABEL_18;
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v19 = 5;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 && *((_BYTE *)v16 + 25) >= 2u )
  {
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
      v20,
      (__int64)"Failed to QI for IRDPENCPlatformContext",
      v19);
  }
LABEL_18:
  if ( v69 )
  {
    v21 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, GUID *, char *))(*(_QWORD *)v69 + 48LL))(
            v69,
            L"RDP::EventLog::Session",
            &IID_IRdpTransportEventLogCallbacks,
            (char *)this + 72);
    v22 = v21;
    if ( v21 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v23,
        (__int64)"The eventlog session does not exsit",
        v22);
    }
    v24 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, GUID *, char *))(*(_QWORD *)v69 + 48LL))(
            v69,
            L"RDP::EventLog::Session",
            &IID_IRdpStateTransitionEventLogCallbacks,
            (char *)this + 80);
    v25 = v24;
    if ( v24 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v26,
        (__int64)"The state transition eventlog session does not exist",
        v25);
    }
  }
  ActivityId = *(GUID *)((char *)this + 216);
  EventActivityIdControl(4u, &ActivityId);
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRDPENCCONStream *)((char *)this + 88)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v27,
        (__int64)"Encoder failed to initialize lock",
        5);
    }
LABEL_34:
    CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
LABEL_132:
    CRDPENCCONStream::Terminate(v75);
    goto LABEL_133;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 16) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v32,
        LastError);
    }
    v33 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v33 = LastError < 0;
    }
    if ( !v33 )
      LastError = -2147467259;
    Instance = LastError;
    goto LABEL_34;
  }
  Instance = CTSObjectPool<CRdpEncIoContext>::CreateInstance(v30, v29, (char *)this + 168);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v36 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v36,
        (__int64)"Failed to create IO Context pool",
        Instance);
    }
    goto LABEL_34;
  }
  Instance = CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(v35, v34, (char *)this + 176);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v39,
        (__int64)"Failed to create Small StreamBuffer pool",
        Instance);
    }
    goto LABEL_34;
  }
  Instance = CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(v38, v37, (char *)this + 184);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v40 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v40,
        (__int64)"Failed to create Large StreamBuffer pool",
        Instance);
    }
    goto LABEL_34;
  }
  v41 = WSAStartup(2u, &WSAData);
  Instance = v41;
  if ( v41 > 0 )
    Instance = (unsigned __int16)v41 | 0x80070000;
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v42 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v42,
        (__int64)"WSAStartup failed",
        Instance);
    }
    goto LABEL_34;
  }
  v43 = s;
  v44 = s;
  *((_DWORD *)this + 30) = 1;
  *(_DWORD *)optval = 1;
  if ( setsockopt(v44, 6, 1, optval, 4) == -1
    || (*(_DWORD *)optval = 0, setsockopt(v43, 0xFFFF, -129, optval, 4) == -1)
    || (*(_DWORD *)optval = 1, setsockopt(v43, 0xFFFF, 8, optval, 4) == -1) )
  {
    Instance = RDPENCHLPWSErr2Hr();
    CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
    if ( Instance < 0 )
      goto LABEL_132;
    goto LABEL_133;
  }
  if ( a5 )
  {
    HIDWORD(vInBuffer) = a5;
    v78 = a6;
    LODWORD(s) = 0;
    LODWORD(vInBuffer) = 1;
    if ( WSAIoctl(v43, 0x98000004, &vInBuffer, 0xCu, 0, 0, (LPDWORD)&s, 0, 0) == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        Error = WSAGetLastError();
        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v46, Error);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v47 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v47);
    }
  }
  *((_QWORD *)this + 13) = v43;
  v48 = v74;
  if ( v74 != *((_QWORD *)this + 20) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 160);
    *((_QWORD *)this + 20) = v48;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 160);
  }
  *((_DWORD *)this + 49) = v72;
  if ( (int)RDPAPI_GetGlobalObject(&CLSID_RDPPlatformPerfMonLogger, &IID_IRdpPerfMonLogger, &v70) < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v49 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v49);
    }
    goto LABEL_104;
  }
  bstrVal = L"RDP-tcp";
  if ( a2
    && (*(int (__fastcall **)(struct IRDPENCPlatformContext *, const wchar_t *, VARIANTARG *))(*(_QWORD *)a2 + 24LL))(
         a2,
         L"RDP::TerminalName",
         &pvarg) >= 0
    && pvarg.vt == 8 )
  {
    bstrVal = pvarg.bstrVal;
  }
  v51 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, char *))(*(_QWORD *)v70 + 32LL))(
          v70,
          *((unsigned int *)this + 49),
          bstrVal,
          (char *)this + 200);
  v52 = v51;
  if ( v51 >= 0 )
    goto LABEL_98;
  v53 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_99:
      if ( v53 != &WPP_GLOBAL_Control && (*((_DWORD *)v53 + 7) & 0x800) != 0 && *((_BYTE *)v53 + 25) >= 5u )
      {
        v55 = *((_QWORD *)this + 25);
        v56 = *((_DWORD *)this + 49);
        v57 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ddg(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
          v57,
          v56,
          v55);
      }
      goto LABEL_103;
    }
    v54 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
      v54,
      (__int64)"GetTransportPerfMonSession failed. Perfmon counter sill not be available",
      v52);
LABEL_98:
    v53 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_99;
  }
LABEL_103:
  *((_DWORD *)this + 60) = GetTickCount();
LABEL_104:
  Instance = CRdpEncTransportWorker::CreateInstance((struct CRdpEncTransportWorker **)this + 26);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v58 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v58,
        (__int64)"Failed to initialize the transport worker",
        Instance);
    }
    goto LABEL_34;
  }
  Instance = CRdpEncTransportWorker::AssociateSocketWithIOPort(*((PVOID *)this + 26), *((HANDLE *)this + 13));
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v59 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v59,
        (__int64)"Failed to associate sock with IO completion port.",
        Instance);
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v60 = *((_DWORD *)this + 26);
    v61 = *((_DWORD *)this + 49);
    v62 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v62, v61, v60);
  }
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  if ( *((_QWORD *)this + 9) && (unsigned int)IsTLSLoggerEnabled(1) == 1 )
  {
    TLSLoggerInstance = CreateTLSLoggerInstance(1, (char *)this + 248);
    Instance = MapXResultToHR(TLSLoggerInstance);
    if ( Instance >= 0 )
    {
      v64 = CreateTLSLoggerInstance(1, (char *)this + 256);
      Instance = MapXResultToHR(v64);
      if ( Instance >= 0 )
        goto LABEL_133;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_132;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 36;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_132;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 35;
    }
    v15 = "Failed to initialize TLSLogger in CRDPENCCONStream!";
LABEL_131:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v15,
      Instance);
    goto LABEL_132;
  }
LABEL_133:
  VariantClear(&pvarg);
  v65 = v69;
  if ( v69 )
  {
    v69 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  }
  v66 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v66 + 16LL))(v66);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18003f900  push    rbp
0x18003f902  push    rbx
0x18003f903  push    rsi
0x18003f904  push    rdi
0x18003f905  push    r12
0x18003f907  push    r13
0x18003f909  push    r14
0x18003f90b  push    r15
0x18003f90d  lea     rbp, [rsp-188h]
0x18003f915  sub     rsp, 288h
0x18003f91c  mov     rax, cs:__security_cookie
0x18003f923  xor     rax, rsp
0x18003f926  mov     [rbp+1C0h+var_50], rax
0x18003f92d  xor     eax, eax
0x18003f92f  mov     [rsp+2C0h+s], r9
0x18003f934  mov     r13, rcx
0x18003f937  mov     [rbp+1C0h+vInBuffer], rax
0x18003f93b  xor     ecx, ecx
0x18003f93d  mov     [rbp+1C0h+var_208], eax
0x18003f940  mov     dword ptr [rsp+2C0h+optval], ecx
0x18003f944  mov     rbx, r8
0x18003f947  mov     [rsp+2C0h+var_260], rcx
0x18003f94c  mov     rdi, rdx
0x18003f94f  mov     [rsp+2C0h+var_268], rcx
0x18003f954  xorps   xmm0, xmm0
0x18003f957  xorps   xmm1, xmm1
0x18003f95a  mov     qword ptr [rbp+1C0h+pvarg+10h], rax
0x18003f95e  lea     rcx, [rbp+1C0h+WSAData]; void *
0x18003f962  xor     edx, edx; Val
0x18003f964  mov     r8d, 198h; Size
0x18003f96a  movups  [rbp+1C0h+var_200], xmm0
0x18003f96e  movups  xmmword ptr [rsp+2C0h+pvarg], xmm1
0x18003f973  call    memset_0
0x18003f978  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x18003f97d  call    cs:__imp_VariantInit
0x18003f983  mov     rax, [rbx]
0x18003f986  mov     rcx, rbx
0x18003f989  mov     rax, [rax+68h]
0x18003f98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f992  mov     rdx, [rbx]
0x18003f995  mov     rcx, rbx
0x18003f998  mov     [rsp+2C0h+var_250], eax
0x18003f99c  mov     rax, [rdx+50h]
0x18003f9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9a5  mov     [rbp+1C0h+var_230], rax
0x18003f9a9  mov     rcx, rbx
0x18003f9ac  lea     rax, [r13+8]
0x18003f9b0  or      dword ptr [rax+14h], 2
0x18003f9b4  mov     rdx, [rbx]
0x18003f9b7  mov     [rbp+1C0h+var_228], rax
0x18003f9bb  mov     rax, [rdx+70h]
0x18003f9bf  lea     rdx, [rbp+1C0h+var_200]
0x18003f9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9c8  mov     esi, eax
0x18003f9ca  test    eax, eax
0x18003f9cc  jns     short loc_18003FA1C
0x18003f9ce  mov     rax, cs:WPP_GLOBAL_Control
0x18003f9d5  lea     r14, WPP_GLOBAL_Control
0x18003f9dc  cmp     rax, r14
0x18003f9df  jz      loc_18004032A
0x18003f9e5  mov     r12d, 8
0x18003f9eb  test    [rax+1Ch], r12b
0x18003f9ef  jz      loc_18004032A
0x18003f9f5  cmp     byte ptr [rax+19h], 2
0x18003f9f9  jb      loc_18004032A
0x18003f9ff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fa04  lea     edx, [r12+8]
0x18003fa09  lea     rcx, aFailedToRetrie; "Failed to retrieve the connection UUID"
0x18003fa10  lea     r8, WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids
0x18003fa17  jmp     loc_18004030E
0x18003fa1c  mov     rax, cs:WPP_GLOBAL_Control
0x18003fa23  lea     r14, WPP_GLOBAL_Control
0x18003fa2a  lea     r15, WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids
0x18003fa31  cmp     rax, r14
0x18003fa34  jz      short loc_18003FA80
0x18003fa36  test    dword ptr [rax+1Ch], 800h
0x18003fa3d  jz      short loc_18003FA80
0x18003fa3f  cmp     byte ptr [rax+19h], 4
0x18003fa43  jb      short loc_18003FA80
0x18003fa45  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fa4a  mov     ecx, [rbp+1C0h+arg_28]
0x18003fa50  mov     edx, 11h
0x18003fa55  mov     [rsp+2C0h+cbOutBuffer], ecx
0x18003fa59  mov     r9d, eax
0x18003fa5c  mov     ecx, [rbp+1C0h+arg_20]
0x18003fa62  mov     r8, r15
0x18003fa65  mov     [rsp+2C0h+optlen], ecx
0x18003fa69  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa70  mov     rcx, [rcx+10h]
0x18003fa74  call    WPP_SF_DLD
0x18003fa79  mov     rax, cs:WPP_GLOBAL_Control
0x18003fa80  mov     esi, 80004005h
0x18003fa85  mov     r12d, 8
0x18003fa8b  test    rdi, rdi
0x18003fa8e  jz      short loc_18003FAB9
0x18003fa90  mov     rax, [rdi]
0x18003fa93  lea     r8, [rsp+2C0h+var_268]
0x18003fa98  lea     rdx, IID_IRDPCollection
0x18003fa9f  mov     rcx, rdi
0x18003faa2  mov     rax, [rax]
0x18003faa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003faaa  mov     ebx, eax
0x18003faac  test    eax, eax
0x18003faae  jns     short loc_18003FAFC
0x18003fab0  mov     rax, cs:WPP_GLOBAL_Control
0x18003fab7  jmp     short loc_18003FABB
0x18003fab9  mov     ebx, esi
0x18003fabb  cmp     rax, r14
0x18003fabe  jz      short loc_18003FAFC
0x18003fac0  test    [rax+1Ch], r12b
0x18003fac4  jz      short loc_18003FAFC
0x18003fac6  cmp     byte ptr [rax+19h], 2
0x18003faca  jb      short loc_18003FAFC
0x18003facc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fad1  lea     rcx, aFailedToQiForI; "Failed to QI for IRDPENCPlatformContext"
0x18003fad8  mov     [rsp+2C0h+cbOutBuffer], ebx
0x18003fadc  mov     qword ptr [rsp+2C0h+optlen], rcx
0x18003fae1  mov     edx, 12h
0x18003fae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003faed  mov     r9d, eax
0x18003faf0  mov     r8, r15
0x18003faf3  mov     rcx, [rcx+10h]
0x18003faf7  call    WPP_SF_DsD
0x18003fafc  mov     rcx, [rsp+2C0h+var_268]
0x18003fb01  test    rcx, rcx
0x18003fb04  jz      loc_18003FBE7
0x18003fb0a  mov     rax, [rcx]
0x18003fb0d  lea     r9, [r13+48h]
0x18003fb11  lea     r8, IID_IRdpTransportEventLogCallbacks
0x18003fb18  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x18003fb1f  mov     rax, [rax+30h]
0x18003fb23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb28  mov     ebx, eax
0x18003fb2a  test    eax, eax
0x18003fb2c  jns     short loc_18003FB76
0x18003fb2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb35  cmp     rcx, r14
0x18003fb38  jz      short loc_18003FB76
0x18003fb3a  test    [rcx+1Ch], r12b
0x18003fb3e  jz      short loc_18003FB76
0x18003fb40  cmp     byte ptr [rcx+19h], 2
0x18003fb44  jb      short loc_18003FB76
0x18003fb46  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fb4b  lea     rcx, aTheEventlogSes; "The eventlog session does not exsit"
0x18003fb52  mov     [rsp+2C0h+cbOutBuffer], ebx
0x18003fb56  mov     qword ptr [rsp+2C0h+optlen], rcx
0x18003fb5b  mov     edx, 13h
0x18003fb60  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fb67  mov     r9d, eax
0x18003fb6a  mov     r8, r15
0x18003fb6d  mov     rcx, [rcx+10h]
0x18003fb71  call    WPP_SF_DsD
0x18003fb76  mov     rcx, [rsp+2C0h+var_268]
0x18003fb7b  lea     r9, [r13+50h]
0x18003fb7f  lea     r8, IID_IRdpStateTransitionEventLogCallbacks
0x18003fb86  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x18003fb8d  mov     rax, [rcx]
0x18003fb90  mov     rax, [rax+30h]
0x18003fb94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb99  mov     ebx, eax
0x18003fb9b  test    eax, eax
0x18003fb9d  jns     short loc_18003FBE7
0x18003fb9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fba6  cmp     rcx, r14
0x18003fba9  jz      short loc_18003FBE7
0x18003fbab  test    [rcx+1Ch], r12b
0x18003fbaf  jz      short loc_18003FBE7
0x18003fbb1  cmp     byte ptr [rcx+19h], 2
0x18003fbb5  jb      short loc_18003FBE7
0x18003fbb7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fbbc  lea     rcx, aTheStateTransi_0; "The state transition eventlog session d"...
0x18003fbc3  mov     [rsp+2C0h+cbOutBuffer], ebx
0x18003fbc7  mov     qword ptr [rsp+2C0h+optlen], rcx
0x18003fbcc  mov     edx, 14h
0x18003fbd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fbd8  mov     r9d, eax
0x18003fbdb  mov     r8, r15
0x18003fbde  mov     rcx, [rcx+10h]
0x18003fbe2  call    WPP_SF_DsD
0x18003fbe7  movups  xmm0, xmmword ptr [r13+0D8h]
0x18003fbef  lea     rdx, [rbp+1C0h+ActivityId]; ActivityId
0x18003fbf3  mov     ecx, 4; ControlCode
0x18003fbf8  movdqu  xmmword ptr [rbp+1C0h+ActivityId.Data1], xmm0
0x18003fbfd  call    cs:__imp_EventActivityIdControl
0x18003fc03  lea     rcx, [r13+58h]; this
0x18003fc07  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18003fc0c  test    eax, eax
0x18003fc0e  jnz     short loc_18003FC6A
0x18003fc10  mov     rax, cs:WPP_GLOBAL_Control
0x18003fc17  cmp     rax, r14
0x18003fc1a  jz      short loc_18003FC5C
0x18003fc1c  test    [rax+1Ch], r12b
0x18003fc20  jz      short loc_18003FC5C
0x18003fc22  cmp     byte ptr [rax+19h], 2
0x18003fc26  jb      short loc_18003FC5C
0x18003fc28  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fc2d  mov     edx, 15h
0x18003fc32  mov     [rsp+2C0h+cbOutBuffer], 80004005h
0x18003fc3a  lea     rcx, aEncoderFailedT_0; "Encoder failed to initialize lock"
0x18003fc41  mov     qword ptr [rsp+2C0h+optlen], rcx
0x18003fc46  mov     r9d, eax
0x18003fc49  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fc50  mov     r8, r15
0x18003fc53  mov     rcx, [rcx+10h]
0x18003fc57  call    WPP_SF_DsD
0x18003fc5c  lea     rcx, [rbp+1C0h+ActivityId]; ActivityId
0x18003fc60  call    ??1CAutoSetThreadActivityId@@QEAA@XZ; CAutoSetThreadActivityId::~CAutoSetThreadActivityId(void)
0x18003fc65  jmp     loc_18004032A
0x18003fc6a  xor     r9d, r9d; lpName
0x18003fc6d  xor     r8d, r8d; bInitialState
0x18003fc70  xor     ecx, ecx; lpEventAttributes
0x18003fc72  lea     ebx, [r9+1]
0x18003fc76  mov     edx, ebx; bManualReset
0x18003fc78  call    cs:__imp_CreateEventW
0x18003fc7e  mov     [r13+80h], rax
0x18003fc85  test    rax, rax
0x18003fc88  jnz     short loc_18003FCE7
0x18003fc8a  call    cs:__imp_GetLastError
0x18003fc90  mov     ebx, eax
0x18003fc92  mov     rax, cs:WPP_GLOBAL_Control
0x18003fc99  cmp     rax, r14
0x18003fc9c  jz      short loc_18003FCCE
0x18003fc9e  test    [rax+1Ch], r12b
0x18003fca2  jz      short loc_18003FCCE
0x18003fca4  cmp     byte ptr [rax+19h], 2
0x18003fca8  jb      short loc_18003FCCE
0x18003fcaa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fcaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fcb6  mov     edx, 16h
0x18003fcbb  mov     r9d, eax
0x18003fcbe  mov     [rsp+2C0h+optlen], ebx
0x18003fcc2  mov     r8, r15
0x18003fcc5  mov     rcx, [rcx+10h]
0x18003fcc9  call    WPP_SF_Dd
0x18003fcce  test    ebx, ebx
0x18003fcd0  jle     short loc_18003FCDD
0x18003fcd2  movzx   ebx, bx
0x18003fcd5  or      ebx, 80070000h
0x18003fcdb  test    ebx, ebx
0x18003fcdd  cmovns  ebx, esi
0x18003fce0  mov     esi, ebx
0x18003fce2  jmp     loc_18003FC5C
0x18003fce7  lea     r8, [r13+0A8h]
0x18003fcee  call    ?CreateInstance@?$CTSObjectPool@VCRdpEncIoContext@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRdpEncIoContext>::CreateInstance(uint,uint,CTSObjectPool<CRdpEncIoContext> * *,int)
0x18003fcf3  mov     esi, eax
0x18003fcf5  test    eax, eax
0x18003fcf7  jns     short loc_18003FD37
0x18003fcf9  mov     rax, cs:WPP_GLOBAL_Control
0x18003fd00  cmp     rax, r14
0x18003fd03  jz      loc_18003FC5C
0x18003fd09  test    [rax+1Ch], r12b
0x18003fd0d  jz      loc_18003FC5C
0x18003fd13  cmp     byte ptr [rax+19h], 2
0x18003fd17  jb      loc_18003FC5C
0x18003fd1d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fd22  mov     edx, 17h
0x18003fd27  mov     [rsp+2C0h+cbOutBuffer], esi
0x18003fd2b  lea     rcx, aFailedToCreate_59; "Failed to create IO Context pool"
0x18003fd32  jmp     loc_18003FC41
0x18003fd37  lea     r8, [r13+0B0h]
0x18003fd3e  call    ?CreateInstance@?$CTSObjectPool@VCRDPENCCONStreamBufferPoolObject@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(uint,uint,CTSObjectPool<CRDPENCCONStreamBufferPoolObject> * *,int)
0x18003fd43  mov     esi, eax
0x18003fd45  test    eax, eax
0x18003fd47  jns     short loc_18003FD87
0x18003fd49  mov     rax, cs:WPP_GLOBAL_Control
0x18003fd50  cmp     rax, r14
0x18003fd53  jz      loc_18003FC5C
0x18003fd59  test    [rax+1Ch], r12b
0x18003fd5d  jz      loc_18003FC5C
0x18003fd63  cmp     byte ptr [rax+19h], 2
0x18003fd67  jb      loc_18003FC5C
0x18003fd6d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fd72  mov     edx, 18h
0x18003fd77  mov     [rsp+2C0h+cbOutBuffer], esi
0x18003fd7b  lea     rcx, aFailedToCreate_16; "Failed to create Small StreamBuffer poo"...
0x18003fd82  jmp     loc_18003FC41
0x18003fd87  lea     r8, [r13+0B8h]
0x18003fd8e  call    ?CreateInstance@?$CTSObjectPool@VCRDPENCCONStreamBufferPoolObject@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(uint,uint,CTSObjectPool<CRDPENCCONStreamBufferPoolObject> * *,int)
0x18003fd93  mov     esi, eax
0x18003fd95  test    eax, eax
0x18003fd97  jns     short loc_18003FDD7
0x18003fd99  mov     rax, cs:WPP_GLOBAL_Control
0x18003fda0  cmp     rax, r14
0x18003fda3  jz      loc_18003FC5C
0x18003fda9  test    [rax+1Ch], r12b
0x18003fdad  jz      loc_18003FC5C
0x18003fdb3  cmp     byte ptr [rax+19h], 2
0x18003fdb7  jb      loc_18003FC5C
0x18003fdbd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003fdc2  mov     edx, 19h
0x18003fdc7  mov     [rsp+2C0h+cbOutBuffer], esi
0x18003fdcb  lea     rcx, aFailedToCreate_38; "Failed to create Large StreamBuffer poo"...
0x18003fdd2  jmp     loc_18003FC41
0x18003fdd7  mov     ecx, 2; wVersionRequested
0x18003fddc  lea     rdx, [rbp+1C0h+WSAData]; lpWSAData
0x18003fde0  call    cs:__imp_WSAStartup
0x18003fde6  mov     esi, eax
0x18003fde8  test    eax, eax
0x18003fdea  jle     short loc_18003FDF5
0x18003fdec  movzx   esi, ax
  ... truncated ...
```
