# CRDPENCCONStream::Initialize(IRDPENCPlatformContext *,IRDPENCConnectorEndpoint *,unsigned __int64,ulong,ulong,ulong,ulong)

- ea: `0x140077208`
- end: `0x140077c9f`
- name: `?Initialize@CRDPENCCONStream@@IEAAJPEAUIRDPENCPlatformContext@@PEAUIRDPENCConnectorEndpoint@@_KKKKK@Z`
- size: `2711`
- prototype: `__int64 __fastcall(CRDPENCCONStream *__hidden this, struct IRDPENCPlatformContext *, struct IRDPENCConnectorEndpoint *, unsigned __int64, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400769f8`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14000dcac`
- `0x14001e158`
- `0x14003c0f0`
- `0x140059acc`
- `0x14005a1a8`
- `0x140076760`
- `0x1400768ac`
- `0x140077208`
- `0x140079280`
- `0x1400799f0`
- `0x14007dce8`
- `0x14007deb8`
- `0x14007ee58`
- `0x14007f2b4`
- `0x140081250`
- `0x14008ebc4`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140077a73`
- `KERNEL32!GetTickCount` at `0x140077a73`
- `KERNEL32!CreateEventW` at `0x140077585`
- `KERNEL32!CreateEventW` at `0x140077585`
- `KERNEL32!GetLastError` at `0x140077597`
- `KERNEL32!GetLastError` at `0x140077597`
- `OLEAUT32!__imp_VariantInit` at `0x140077287`
- `OLEAUT32!__imp_VariantInit` at `0x140077287`
- `OLEAUT32!__imp_VariantClear` at `0x140077c4b`
- `OLEAUT32!__imp_VariantClear` at `0x140077c4b`
- `ADVAPI32!EventActivityIdControl` at `0x140077506`
- `ADVAPI32!EventActivityIdControl` at `0x14007756e`
- `ADVAPI32!EventActivityIdControl` at `0x1400777e9`
- `ADVAPI32!EventActivityIdControl` at `0x140077b72`
- `ADVAPI32!EventActivityIdControl` at `0x140077506`
- `ADVAPI32!EventActivityIdControl` at `0x14007756e`
- `ADVAPI32!EventActivityIdControl` at `0x1400777e9`
- `ADVAPI32!EventActivityIdControl` at `0x140077b72`
- `WS2_32!WSAIoctl` at `0x140077850`
- `WS2_32!WSAIoctl` at `0x140077850`
- `WS2_32!__imp_setsockopt` at `0x140077778`
- `WS2_32!__imp_setsockopt` at `0x1400777a6`
- `WS2_32!__imp_setsockopt` at `0x1400777d1`
- `WS2_32!__imp_setsockopt` at `0x140077778`
- `WS2_32!__imp_setsockopt` at `0x1400777a6`
- `WS2_32!__imp_setsockopt` at `0x1400777d1`
- `WS2_32!__imp_WSAGetLastError` at `0x140077875`
- `WS2_32!__imp_WSAGetLastError` at `0x140077875`
- `WS2_32!__imp_WSAStartup` at `0x1400776e9`
- `WS2_32!__imp_WSAStartup` at `0x1400776e9`

## string_xrefs

- `0x140077634`: `Failed to create IO Context pool`
- `0x140077689`: `Failed to create Small StreamBuffer pool`
- `0x1400776d2`: `Failed to create Large StreamBuffer pool`
- `0x140077b0f`: `Failed to associate sock with IO completion port.`

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
  int v37; // edx
  const char *v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  int v41; // eax
  unsigned int v42; // eax
  SOCKET v43; // rsi
  int Error; // ebx
  unsigned int v45; // eax
  unsigned int v46; // eax
  __int64 v47; // rsi
  unsigned int v48; // eax
  const wchar_t *bstrVal; // rbx
  int v50; // eax
  char v51; // bl
  PVOID *v52; // rcx
  unsigned int v53; // eax
  __int64 v54; // rbx
  int v55; // edi
  unsigned int v56; // eax
  int v57; // ebx
  int v58; // edi
  unsigned int v59; // eax
  __int64 v60; // rcx
  unsigned int TLSLoggerInstance; // eax
  __int64 v62; // rcx
  unsigned int v63; // eax
  void *v64; // rcx
  char optval[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v67; // [rsp+58h] [rbp-A8h] BYREF
  void *v68; // [rsp+60h] [rbp-A0h] BYREF
  SOCKET s; // [rsp+68h] [rbp-98h] BYREF
  int v70; // [rsp+70h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  __int64 v72; // [rsp+90h] [rbp-70h]
  CRDPENCCONStream *v73; // [rsp+98h] [rbp-68h]
  GUID ActivityId; // [rsp+A0h] [rbp-60h] BYREF
  __int64 vInBuffer; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v76; // [rsp+B8h] [rbp-48h]
  __int128 v77; // [rsp+C0h] [rbp-40h] BYREF
  WSAData WSAData; // [rsp+D0h] [rbp-30h] BYREF

  s = a4;
  vInBuffer = 0;
  *(_DWORD *)optval = 0;
  v68 = 0;
  v76 = 0;
  v67 = 0;
  v77 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(&WSAData, 0, sizeof(WSAData));
  VariantInit(&pvarg);
  v9 = (*(__int64 (__fastcall **)(struct IRDPENCConnectorEndpoint *))(*(_QWORD *)a3 + 104LL))(a3);
  v10 = *(_QWORD *)a3;
  v70 = v9;
  v72 = (*(__int64 (__fastcall **)(struct IRDPENCConnectorEndpoint *))(v10 + 80))(a3);
  *((_DWORD *)this + 7) |= 2u;
  v11 = *(_QWORD *)a3;
  v73 = (CRDPENCCONStream *)((char *)this + 8);
  Instance = (*(__int64 (__fastcall **)(struct IRDPENCConnectorEndpoint *, __int128 *))(v11 + 112))(a3, &v77);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_134;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v14 = 16;
    v15 = "Failed to retrieve the connection UUID";
    goto LABEL_133;
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
            &v67);
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
  if ( v67 )
  {
    v21 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, GUID *, char *))(*(_QWORD *)v67 + 48LL))(
            v67,
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
    v24 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, GUID *, char *))(*(_QWORD *)v67 + 48LL))(
            v67,
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
    goto LABEL_34;
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
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v36 = RdpWppGetCurrentThreadActivityIdPrefix();
    v37 = 23;
    v38 = "Failed to create IO Context pool";
LABEL_50:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v37,
      (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
      v36,
      (__int64)v38,
      Instance);
LABEL_34:
    EventActivityIdControl(2u, &ActivityId);
LABEL_134:
    CRDPENCCONStream::Terminate(v73);
    goto LABEL_135;
  }
  Instance = CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(v35, v34, (char *)this + 176);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v36 = RdpWppGetCurrentThreadActivityIdPrefix();
    v37 = 24;
    v38 = "Failed to create Small StreamBuffer pool";
    goto LABEL_50;
  }
  Instance = CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(v40, v39, (char *)this + 184);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v36 = RdpWppGetCurrentThreadActivityIdPrefix();
    v37 = 25;
    v38 = "Failed to create Large StreamBuffer pool";
    goto LABEL_50;
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
  *((_DWORD *)this + 30) = 1;
  *(_DWORD *)optval = 1;
  if ( setsockopt(v43, 6, 1, optval, 4) == -1
    || (*(_DWORD *)optval = 0, setsockopt(v43, 0xFFFF, -129, optval, 4) == -1)
    || (*(_DWORD *)optval = 1, setsockopt(v43, 0xFFFF, 8, optval, 4) == -1) )
  {
    Instance = RDPENCHLPWSErr2Hr();
    EventActivityIdControl(2u, &ActivityId);
    if ( Instance >= 0 )
      goto LABEL_135;
    goto LABEL_134;
  }
  if ( a5 )
  {
    HIDWORD(vInBuffer) = a5;
    v76 = a6;
    LODWORD(s) = 0;
    LODWORD(vInBuffer) = 1;
    if ( WSAIoctl(v43, 0x98000004, &vInBuffer, 0xCu, 0, 0, (LPDWORD)&s, 0, 0) == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        Error = WSAGetLastError();
        v45 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v45, Error);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v46 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v46);
    }
  }
  *((_QWORD *)this + 13) = v43;
  v47 = v72;
  if ( v72 != *((_QWORD *)this + 20) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 160);
    *((_QWORD *)this + 20) = v47;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 160);
  }
  *((_DWORD *)this + 49) = v70;
  if ( (int)RDPAPI_GetGlobalObject(&CLSID_RDPPlatformPerfMonLogger, &IID_IRdpPerfMonLogger, &v68) >= 0 )
  {
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
    v50 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, char *))(*(_QWORD *)v68 + 32LL))(
            v68,
            *((unsigned int *)this + 49),
            bstrVal,
            (char *)this + 200);
    v51 = v50;
    if ( v50 < 0 )
    {
      v52 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_105:
        *((_DWORD *)this + 60) = GetTickCount();
        goto LABEL_106;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_101:
        if ( v52 != &WPP_GLOBAL_Control && (*((_DWORD *)v52 + 7) & 0x800) != 0 && *((_BYTE *)v52 + 25) >= 5u )
        {
          v54 = *((_QWORD *)this + 25);
          v55 = *((_DWORD *)this + 49);
          v56 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ddq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
            v56,
            v55,
            v54);
        }
        goto LABEL_105;
      }
      v53 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v53,
        (__int64)"GetTransportPerfMonSession failed. Perfmon counter sill not be available",
        v51);
    }
    v52 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_101;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v48 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v48);
  }
LABEL_106:
  Instance = CRdpEncTransportWorker::CreateInstance((struct CRdpEncTransportWorker **)this + 26);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v36 = RdpWppGetCurrentThreadActivityIdPrefix();
    v37 = 32;
    v38 = "Failed to initialize the transport worker";
    goto LABEL_50;
  }
  Instance = CRdpEncTransportWorker::AssociateSocketWithIOPort(*((PVOID *)this + 26), *((HANDLE *)this + 13));
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v36 = RdpWppGetCurrentThreadActivityIdPrefix();
    v37 = 33;
    v38 = "Failed to associate sock with IO completion port.";
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v57 = *((_DWORD *)this + 26);
    v58 = *((_DWORD *)this + 49);
    v59 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v59, v58, v57);
  }
  EventActivityIdControl(2u, &ActivityId);
  if ( *((_QWORD *)this + 9)
    && (unsigned int)IsTLSLoggerEnabled(
                       -2147483646,
                       L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations") == 1 )
  {
    TLSLoggerInstance = CreateTLSLoggerInstance(v60, (char *)this + 248);
    Instance = MapXResultToHR(TLSLoggerInstance);
    if ( Instance >= 0 )
    {
      v63 = CreateTLSLoggerInstance(v62, (char *)this + 256);
      Instance = MapXResultToHR(v63);
      if ( Instance >= 0 )
        goto LABEL_135;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_134;
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
        goto LABEL_134;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v14 = 35;
    }
    v15 = "Failed to initialize TLSLogger in CRDPENCCONStream!";
LABEL_133:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v15,
      Instance);
    goto LABEL_134;
  }
LABEL_135:
  VariantClear(&pvarg);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v67);
  v64 = v68;
  if ( v68 )
  {
    v68 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v64 + 16LL))(v64);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140077208  push    rbp
0x14007720a  push    rbx
0x14007720b  push    rsi
0x14007720c  push    rdi
0x14007720d  push    r12
0x14007720f  push    r13
0x140077211  push    r14
0x140077213  push    r15
0x140077215  lea     rbp, [rsp-188h]
0x14007721d  sub     rsp, 288h
0x140077224  mov     rax, cs:__security_cookie
0x14007722b  xor     rax, rsp
0x14007722e  mov     [rbp+1C0h+var_50], rax
0x140077235  xor     eax, eax
0x140077237  mov     [rsp+2C0h+s], r9
0x14007723c  xor     r14d, r14d
0x14007723f  mov     [rbp+1C0h+vInBuffer], rax
0x140077243  mov     rbx, r8
0x140077246  mov     dword ptr [rsp+2C0h+optval], r14d
0x14007724b  mov     rdi, rdx
0x14007724e  mov     [rsp+2C0h+var_260], r14
0x140077253  mov     r15, rcx
0x140077256  mov     [rbp+1C0h+var_208], eax
0x140077259  xorps   xmm0, xmm0
0x14007725c  mov     [rsp+2C0h+var_268], r14
0x140077261  xorps   xmm1, xmm1
0x140077264  mov     qword ptr [rbp+1C0h+pvarg+10h], rax
0x140077268  xor     edx, edx; Val
0x14007726a  lea     rcx, [rbp+1C0h+WSAData]; void *
0x14007726e  mov     r8d, 198h; Size
0x140077274  movups  [rbp+1C0h+var_200], xmm0
0x140077278  movups  xmmword ptr [rsp+2C0h+pvarg], xmm1
0x14007727d  call    memset_0
0x140077282  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x140077287  call    cs:__imp_VariantInit
0x14007728d  mov     rax, [rbx]
0x140077290  mov     rcx, rbx
0x140077293  mov     rax, [rax+68h]
0x140077297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007729c  mov     rdx, [rbx]
0x14007729f  mov     rcx, rbx
0x1400772a2  mov     [rsp+2C0h+var_250], eax
0x1400772a6  mov     rax, [rdx+50h]
0x1400772aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400772af  mov     [rbp+1C0h+var_230], rax
0x1400772b3  mov     rcx, rbx
0x1400772b6  lea     rax, [r15+8]
0x1400772ba  or      dword ptr [rax+14h], 2
0x1400772be  mov     rdx, [rbx]
0x1400772c1  mov     [rbp+1C0h+var_228], rax
0x1400772c5  mov     rax, [rdx+70h]
0x1400772c9  lea     rdx, [rbp+1C0h+var_200]
0x1400772cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400772d2  mov     esi, eax
0x1400772d4  test    eax, eax
0x1400772d6  jns     short loc_140077325
0x1400772d8  mov     rax, cs:WPP_GLOBAL_Control
0x1400772df  lea     r14, WPP_GLOBAL_Control
0x1400772e6  cmp     rax, r14
0x1400772e9  jz      loc_140077C3D
0x1400772ef  mov     r13d, 8
0x1400772f5  test    [rax+1Ch], r13b
0x1400772f9  jz      loc_140077C3D
0x1400772ff  cmp     byte ptr [rax+19h], 2
0x140077303  jb      loc_140077C3D
0x140077309  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007730e  lea     edx, [r13+8]
0x140077312  lea     rcx, aFailedToRetrie; "Failed to retrieve the connection UUID"
0x140077319  lea     r8, WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids
0x140077320  jmp     loc_140077C21
0x140077325  mov     rax, cs:WPP_GLOBAL_Control
0x14007732c  lea     r14, WPP_GLOBAL_Control
0x140077333  lea     r12, WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids
0x14007733a  cmp     rax, r14
0x14007733d  jz      short loc_140077389
0x14007733f  test    dword ptr [rax+1Ch], 800h
0x140077346  jz      short loc_140077389
0x140077348  cmp     byte ptr [rax+19h], 4
0x14007734c  jb      short loc_140077389
0x14007734e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140077353  mov     ecx, [rbp+1C0h+arg_28]
0x140077359  mov     edx, 11h
0x14007735e  mov     [rsp+2C0h+cbOutBuffer], ecx
0x140077362  mov     r9d, eax
0x140077365  mov     ecx, [rbp+1C0h+arg_20]
0x14007736b  mov     r8, r12
0x14007736e  mov     [rsp+2C0h+optlen], ecx
0x140077372  mov     rcx, cs:WPP_GLOBAL_Control
0x140077379  mov     rcx, [rcx+10h]
0x14007737d  call    WPP_SF_DLD
0x140077382  mov     rax, cs:WPP_GLOBAL_Control
0x140077389  mov     esi, 80004005h
0x14007738e  mov     r13d, 8
0x140077394  test    rdi, rdi
0x140077397  jz      short loc_1400773C2
0x140077399  mov     rax, [rdi]
0x14007739c  lea     r8, [rsp+2C0h+var_268]
0x1400773a1  lea     rdx, IID_IRDPCollection
0x1400773a8  mov     rcx, rdi
0x1400773ab  mov     rax, [rax]
0x1400773ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400773b3  mov     ebx, eax
0x1400773b5  test    eax, eax
0x1400773b7  jns     short loc_140077405
0x1400773b9  mov     rax, cs:WPP_GLOBAL_Control
0x1400773c0  jmp     short loc_1400773C4
0x1400773c2  mov     ebx, esi
0x1400773c4  cmp     rax, r14
0x1400773c7  jz      short loc_140077405
0x1400773c9  test    [rax+1Ch], r13b
0x1400773cd  jz      short loc_140077405
0x1400773cf  cmp     byte ptr [rax+19h], 2
0x1400773d3  jb      short loc_140077405
0x1400773d5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400773da  lea     rcx, aFailedToQiForI; "Failed to QI for IRDPENCPlatformContext"
0x1400773e1  mov     [rsp+2C0h+cbOutBuffer], ebx
0x1400773e5  mov     qword ptr [rsp+2C0h+optlen], rcx
0x1400773ea  mov     edx, 12h
0x1400773ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400773f6  mov     r9d, eax
0x1400773f9  mov     r8, r12
0x1400773fc  mov     rcx, [rcx+10h]
0x140077400  call    WPP_SF_DsD
0x140077405  mov     rcx, [rsp+2C0h+var_268]
0x14007740a  test    rcx, rcx
0x14007740d  jz      loc_1400774F0
0x140077413  mov     rax, [rcx]
0x140077416  lea     r9, [r15+48h]
0x14007741a  lea     r8, IID_IRdpTransportEventLogCallbacks
0x140077421  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x140077428  mov     rax, [rax+30h]
0x14007742c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140077431  mov     ebx, eax
0x140077433  test    eax, eax
0x140077435  jns     short loc_14007747F
0x140077437  mov     rcx, cs:WPP_GLOBAL_Control
0x14007743e  cmp     rcx, r14
0x140077441  jz      short loc_14007747F
0x140077443  test    [rcx+1Ch], r13b
0x140077447  jz      short loc_14007747F
0x140077449  cmp     byte ptr [rcx+19h], 2
0x14007744d  jb      short loc_14007747F
0x14007744f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140077454  lea     rcx, aTheEventlogSes; "The eventlog session does not exsit"
0x14007745b  mov     [rsp+2C0h+cbOutBuffer], ebx
0x14007745f  mov     qword ptr [rsp+2C0h+optlen], rcx
0x140077464  mov     edx, 13h
0x140077469  mov     rcx, cs:WPP_GLOBAL_Control
0x140077470  mov     r9d, eax
0x140077473  mov     r8, r12
0x140077476  mov     rcx, [rcx+10h]
0x14007747a  call    WPP_SF_DsD
0x14007747f  mov     rcx, [rsp+2C0h+var_268]
0x140077484  lea     r9, [r15+50h]
0x140077488  lea     r8, IID_IRdpStateTransitionEventLogCallbacks
0x14007748f  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x140077496  mov     rax, [rcx]
0x140077499  mov     rax, [rax+30h]
0x14007749d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400774a2  mov     ebx, eax
0x1400774a4  test    eax, eax
0x1400774a6  jns     short loc_1400774F0
0x1400774a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400774af  cmp     rcx, r14
0x1400774b2  jz      short loc_1400774F0
0x1400774b4  test    [rcx+1Ch], r13b
0x1400774b8  jz      short loc_1400774F0
0x1400774ba  cmp     byte ptr [rcx+19h], 2
0x1400774be  jb      short loc_1400774F0
0x1400774c0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400774c5  lea     rcx, aTheStateTransi; "The state transition eventlog session d"...
0x1400774cc  mov     [rsp+2C0h+cbOutBuffer], ebx
0x1400774d0  mov     qword ptr [rsp+2C0h+optlen], rcx
0x1400774d5  mov     edx, 14h
0x1400774da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400774e1  mov     r9d, eax
0x1400774e4  mov     r8, r12
0x1400774e7  mov     rcx, [rcx+10h]
0x1400774eb  call    WPP_SF_DsD
0x1400774f0  movups  xmm0, xmmword ptr [r15+0D8h]
0x1400774f8  lea     rdx, [rbp+1C0h+ActivityId]; ActivityId
0x1400774fc  mov     ecx, 4; ControlCode
0x140077501  movdqu  xmmword ptr [rbp+1C0h+ActivityId.Data1], xmm0
0x140077506  call    cs:__imp_EventActivityIdControl
0x14007750c  lea     rcx, [r15+58h]; this
0x140077510  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x140077515  test    eax, eax
0x140077517  jnz     short loc_140077579
0x140077519  mov     rax, cs:WPP_GLOBAL_Control
0x140077520  cmp     rax, r14
0x140077523  jz      short loc_140077565
0x140077525  test    [rax+1Ch], r13b
0x140077529  jz      short loc_140077565
0x14007752b  cmp     byte ptr [rax+19h], 2
0x14007752f  jb      short loc_140077565
0x140077531  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140077536  lea     r8, aEncoderFailedT; "Encoder failed to initialize lock"
0x14007753d  mov     [rsp+2C0h+cbOutBuffer], 80004005h
0x140077545  mov     qword ptr [rsp+2C0h+optlen], r8
0x14007754a  mov     edx, 15h
0x14007754f  mov     rcx, cs:WPP_GLOBAL_Control
0x140077556  mov     r9d, eax
0x140077559  mov     r8, r12
0x14007755c  mov     rcx, [rcx+10h]
0x140077560  call    WPP_SF_DsD
0x140077565  mov     ecx, 2; ControlCode
0x14007756a  lea     rdx, [rbp+1C0h+ActivityId]; ActivityId
0x14007756e  call    cs:__imp_EventActivityIdControl
0x140077574  jmp     loc_140077C3D
0x140077579  xor     r9d, r9d; lpName
0x14007757c  xor     r8d, r8d; bInitialState
0x14007757f  xor     ecx, ecx; lpEventAttributes
0x140077581  lea     edx, [r9+1]; bManualReset
0x140077585  call    cs:__imp_CreateEventW
0x14007758b  mov     [r15+80h], rax
0x140077592  test    rax, rax
0x140077595  jnz     short loc_1400775F4
0x140077597  call    cs:__imp_GetLastError
0x14007759d  mov     ebx, eax
0x14007759f  mov     rax, cs:WPP_GLOBAL_Control
0x1400775a6  cmp     rax, r14
0x1400775a9  jz      short loc_1400775DB
0x1400775ab  test    [rax+1Ch], r13b
0x1400775af  jz      short loc_1400775DB
0x1400775b1  cmp     byte ptr [rax+19h], 2
0x1400775b5  jb      short loc_1400775DB
0x1400775b7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400775bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400775c3  mov     edx, 16h
0x1400775c8  mov     r9d, eax
0x1400775cb  mov     [rsp+2C0h+optlen], ebx
0x1400775cf  mov     r8, r12
0x1400775d2  mov     rcx, [rcx+10h]
0x1400775d6  call    WPP_SF_Dd
0x1400775db  test    ebx, ebx
0x1400775dd  jle     short loc_1400775EA
0x1400775df  movzx   ebx, bx
0x1400775e2  or      ebx, 80070000h
0x1400775e8  test    ebx, ebx
0x1400775ea  cmovns  ebx, esi
0x1400775ed  mov     esi, ebx
0x1400775ef  jmp     loc_140077565
0x1400775f4  lea     r8, [r15+0A8h]
0x1400775fb  call    ?CreateInstance@?$CTSObjectPool@VCRdpEncIoContext@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRdpEncIoContext>::CreateInstance(uint,uint,CTSObjectPool<CRdpEncIoContext> * *,int)
0x140077600  mov     esi, eax
0x140077602  test    eax, eax
0x140077604  jns     short loc_140077649
0x140077606  mov     rax, cs:WPP_GLOBAL_Control
0x14007760d  cmp     rax, r14
0x140077610  jz      loc_140077565
0x140077616  test    [rax+1Ch], r13b
0x14007761a  jz      loc_140077565
0x140077620  cmp     byte ptr [rax+19h], 2
0x140077624  jb      loc_140077565
0x14007762a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007762f  mov     edx, 17h
0x140077634  lea     rcx, aFailedToCreate_34; "Failed to create IO Context pool"
0x14007763b  mov     [rsp+2C0h+cbOutBuffer], esi
0x14007763f  mov     qword ptr [rsp+2C0h+optlen], rcx
0x140077644  jmp     loc_14007754F
0x140077649  lea     r8, [r15+0B0h]
0x140077650  call    ?CreateInstance@?$CTSObjectPool@VCRDPENCCONStreamBufferPoolObject@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(uint,uint,CTSObjectPool<CRDPENCCONStreamBufferPoolObject> * *,int)
0x140077655  mov     esi, eax
0x140077657  test    eax, eax
0x140077659  jns     short loc_140077692
0x14007765b  mov     rax, cs:WPP_GLOBAL_Control
0x140077662  cmp     rax, r14
0x140077665  jz      loc_140077565
0x14007766b  test    [rax+1Ch], r13b
0x14007766f  jz      loc_140077565
0x140077675  cmp     byte ptr [rax+19h], 2
0x140077679  jb      loc_140077565
0x14007767f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140077684  mov     edx, 18h
0x140077689  lea     rcx, aFailedToCreate_11; "Failed to create Small StreamBuffer poo"...
0x140077690  jmp     short loc_14007763B
0x140077692  lea     r8, [r15+0B8h]
0x140077699  call    ?CreateInstance@?$CTSObjectPool@VCRDPENCCONStreamBufferPoolObject@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(uint,uint,CTSObjectPool<CRDPENCCONStreamBufferPoolObject> * *,int)
0x14007769e  mov     esi, eax
0x1400776a0  test    eax, eax
0x1400776a2  jns     short loc_1400776DE
0x1400776a4  mov     rax, cs:WPP_GLOBAL_Control
0x1400776ab  cmp     rax, r14
0x1400776ae  jz      loc_140077565
0x1400776b4  test    [rax+1Ch], r13b
0x1400776b8  jz      loc_140077565
0x1400776be  cmp     byte ptr [rax+19h], 2
0x1400776c2  jb      loc_140077565
0x1400776c8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400776cd  mov     edx, 19h
0x1400776d2  lea     rcx, aFailedToCreate_22; "Failed to create Large StreamBuffer poo"...
0x1400776d9  jmp     loc_14007763B
0x1400776de  mov     ebx, 2
0x1400776e3  lea     rdx, [rbp+1C0h+WSAData]; lpWSAData
0x1400776e7  mov     ecx, ebx; wVersionRequested
0x1400776e9  call    cs:__imp_WSAStartup
0x1400776ef  mov     esi, eax
0x1400776f1  test    eax, eax
0x1400776f3  jle     short loc_1400776FE
0x1400776f5  movzx   esi, ax
  ... truncated ...
```
