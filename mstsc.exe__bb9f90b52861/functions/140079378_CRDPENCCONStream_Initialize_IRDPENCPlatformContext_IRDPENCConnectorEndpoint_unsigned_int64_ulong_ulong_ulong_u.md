# CRDPENCCONStream::Initialize(IRDPENCPlatformContext *,IRDPENCConnectorEndpoint *,unsigned __int64,ulong,ulong,ulong,ulong)

- ea: `0x140079378`
- end: `0x140079e0f`
- name: `?Initialize@CRDPENCCONStream@@IEAAJPEAUIRDPENCPlatformContext@@PEAUIRDPENCConnectorEndpoint@@_KKKKK@Z`
- size: `2711`
- prototype: `__int64 __fastcall(CRDPENCCONStream *__hidden this, struct IRDPENCPlatformContext *, struct IRDPENCConnectorEndpoint *, unsigned __int64, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140078b68`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x14000dcac`
- `0x14001e158`
- `0x14003e0b4`
- `0x14005bc3c`
- `0x14005c318`
- `0x1400788d0`
- `0x140078a1c`
- `0x140079378`
- `0x14007b3f0`
- `0x14007bb60`
- `0x14007fe58`
- `0x140080028`
- `0x140080fc8`
- `0x140081424`
- `0x1400833c0`
- `0x140090d34`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140079be3`
- `KERNEL32!GetTickCount` at `0x140079be3`
- `KERNEL32!CreateEventW` at `0x1400796f5`
- `KERNEL32!CreateEventW` at `0x1400796f5`
- `KERNEL32!GetLastError` at `0x140079707`
- `KERNEL32!GetLastError` at `0x140079707`
- `OLEAUT32!__imp_VariantInit` at `0x1400793f7`
- `OLEAUT32!__imp_VariantInit` at `0x1400793f7`
- `OLEAUT32!__imp_VariantClear` at `0x140079dbb`
- `OLEAUT32!__imp_VariantClear` at `0x140079dbb`
- `ADVAPI32!EventActivityIdControl` at `0x140079676`
- `ADVAPI32!EventActivityIdControl` at `0x1400796de`
- `ADVAPI32!EventActivityIdControl` at `0x140079959`
- `ADVAPI32!EventActivityIdControl` at `0x140079ce2`
- `ADVAPI32!EventActivityIdControl` at `0x140079676`
- `ADVAPI32!EventActivityIdControl` at `0x1400796de`
- `ADVAPI32!EventActivityIdControl` at `0x140079959`
- `ADVAPI32!EventActivityIdControl` at `0x140079ce2`
- `WS2_32!WSAIoctl` at `0x1400799c0`
- `WS2_32!WSAIoctl` at `0x1400799c0`
- `WS2_32!__imp_setsockopt` at `0x1400798e8`
- `WS2_32!__imp_setsockopt` at `0x140079916`
- `WS2_32!__imp_setsockopt` at `0x140079941`
- `WS2_32!__imp_setsockopt` at `0x1400798e8`
- `WS2_32!__imp_setsockopt` at `0x140079916`
- `WS2_32!__imp_setsockopt` at `0x140079941`
- `WS2_32!__imp_WSAGetLastError` at `0x1400799e5`
- `WS2_32!__imp_WSAGetLastError` at `0x1400799e5`
- `WS2_32!__imp_WSAStartup` at `0x140079859`
- `WS2_32!__imp_WSAStartup` at `0x140079859`

## string_xrefs

- `0x1400797a4`: `Failed to create IO Context pool`
- `0x1400797f9`: `Failed to create Small StreamBuffer pool`
- `0x140079842`: `Failed to create Large StreamBuffer pool`
- `0x140079c7f`: `Failed to associate sock with IO completion port.`

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
  int v18; // ebx
  unsigned int v19; // eax
  int v20; // ebx
  unsigned int v21; // eax
  int v22; // ebx
  unsigned int v23; // eax
  unsigned int v24; // eax
  HANDLE EventW; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  signed int LastError; // ebx
  unsigned int v29; // eax
  bool v30; // sf
  __int64 v31; // rdx
  __int64 v32; // rcx
  unsigned int v33; // eax
  int v34; // edx
  const char *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  int v38; // eax
  unsigned int v39; // eax
  SOCKET v40; // rsi
  int Error; // ebx
  unsigned int v42; // eax
  unsigned int v43; // eax
  __int64 v44; // rsi
  unsigned int v45; // eax
  const wchar_t *bstrVal; // rbx
  int v47; // ebx
  PVOID *v48; // rcx
  unsigned int v49; // eax
  __int64 v50; // rbx
  int v51; // edi
  unsigned int v52; // eax
  int v53; // ebx
  int v54; // edi
  unsigned int v55; // eax
  __int64 v56; // rcx
  unsigned int TLSLoggerInstance; // eax
  __int64 v58; // rcx
  unsigned int v59; // eax
  void *v60; // rcx
  DWORD cbOutBuffer[2]; // [rsp+28h] [rbp-D8h]
  char optval[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v64; // [rsp+58h] [rbp-A8h] BYREF
  void *v65; // [rsp+60h] [rbp-A0h] BYREF
  SOCKET s; // [rsp+68h] [rbp-98h] BYREF
  int v67; // [rsp+70h] [rbp-90h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  __int64 v69; // [rsp+90h] [rbp-70h]
  CRDPENCCONStream *v70; // [rsp+98h] [rbp-68h]
  GUID ActivityId; // [rsp+A0h] [rbp-60h] BYREF
  __int64 vInBuffer; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v73; // [rsp+B8h] [rbp-48h]
  __int128 v74; // [rsp+C0h] [rbp-40h] BYREF
  WSAData WSAData; // [rsp+D0h] [rbp-30h] BYREF

  s = a4;
  vInBuffer = 0;
  *(_DWORD *)optval = 0;
  v65 = 0;
  v73 = 0;
  v64 = 0;
  v74 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(&WSAData, 0, sizeof(WSAData));
  VariantInit(&pvarg);
  v9 = (*(__int64 (__fastcall **)(struct IRDPENCConnectorEndpoint *))(*(_QWORD *)a3 + 104LL))(a3);
  v10 = *(_QWORD *)a3;
  v67 = v9;
  v69 = (*(__int64 (__fastcall **)(struct IRDPENCConnectorEndpoint *))(v10 + 80))(a3);
  *((_DWORD *)this + 7) |= 2u;
  v11 = *(_QWORD *)a3;
  v70 = (CRDPENCCONStream *)((char *)this + 8);
  Instance = (*(__int64 (__fastcall **)(struct IRDPENCConnectorEndpoint *, __int128 *))(v11 + 112))(a3, &v74);
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
            &v64);
    if ( v18 >= 0 )
      goto LABEL_18;
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v18 = -2147467259;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 8) != 0 && *((_BYTE *)v16 + 25) >= 2u )
  {
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    cbOutBuffer[0] = v18;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
      v19,
      (__int64)"Failed to QI for IRDPENCPlatformContext",
      *(_QWORD *)cbOutBuffer);
  }
LABEL_18:
  if ( v64 )
  {
    v20 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, GUID *, char *))(*(_QWORD *)v64 + 48LL))(
            v64,
            L"RDP::EventLog::Session",
            &IID_IRdpTransportEventLogCallbacks,
            (char *)this + 72);
    if ( v20 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      cbOutBuffer[0] = v20;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v21,
        (__int64)"The eventlog session does not exsit",
        *(_QWORD *)cbOutBuffer);
    }
    v22 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, GUID *, char *))(*(_QWORD *)v64 + 48LL))(
            v64,
            L"RDP::EventLog::Session",
            &IID_IRdpStateTransitionEventLogCallbacks,
            (char *)this + 80);
    if ( v22 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      cbOutBuffer[0] = v22;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v23,
        (__int64)"The state transition eventlog session does not exist",
        *(_QWORD *)cbOutBuffer);
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
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      cbOutBuffer[0] = -2147467259;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v24,
        (__int64)"Encoder failed to initialize lock",
        *(_QWORD *)cbOutBuffer);
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
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v29,
        LastError);
    }
    v30 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v30 = LastError < 0;
    }
    if ( !v30 )
      LastError = -2147467259;
    Instance = LastError;
    goto LABEL_34;
  }
  Instance = CTSObjectPool<CRdpEncIoContext>::CreateInstance(v27, v26, (char *)this + 168);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v33 = RdpWppGetCurrentThreadActivityIdPrefix();
    v34 = 23;
    v35 = "Failed to create IO Context pool";
LABEL_50:
    cbOutBuffer[0] = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v34,
      (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
      v33,
      (__int64)v35,
      *(_QWORD *)cbOutBuffer);
LABEL_34:
    EventActivityIdControl(2u, &ActivityId);
LABEL_134:
    CRDPENCCONStream::Terminate(v70);
    goto LABEL_135;
  }
  Instance = CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(v32, v31, (char *)this + 176);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v33 = RdpWppGetCurrentThreadActivityIdPrefix();
    v34 = 24;
    v35 = "Failed to create Small StreamBuffer pool";
    goto LABEL_50;
  }
  Instance = CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(v37, v36, (char *)this + 184);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_34;
    }
    v33 = RdpWppGetCurrentThreadActivityIdPrefix();
    v34 = 25;
    v35 = "Failed to create Large StreamBuffer pool";
    goto LABEL_50;
  }
  v38 = WSAStartup(2u, &WSAData);
  Instance = v38;
  if ( v38 > 0 )
    Instance = (unsigned __int16)v38 | 0x80070000;
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = RdpWppGetCurrentThreadActivityIdPrefix();
      cbOutBuffer[0] = Instance;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v39,
        (__int64)"WSAStartup failed",
        *(_QWORD *)cbOutBuffer);
    }
    goto LABEL_34;
  }
  v40 = s;
  *((_DWORD *)this + 30) = 1;
  *(_DWORD *)optval = 1;
  if ( setsockopt(v40, 6, 1, optval, 4) == -1
    || (*(_DWORD *)optval = 0, setsockopt(v40, 0xFFFF, -129, optval, 4) == -1)
    || (*(_DWORD *)optval = 1, setsockopt(v40, 0xFFFF, 8, optval, 4) == -1) )
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
    v73 = a6;
    LODWORD(s) = 0;
    LODWORD(vInBuffer) = 1;
    if ( WSAIoctl(v40, 0x98000004, &vInBuffer, 0xCu, 0, 0, (LPDWORD)&s, 0, 0) == -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        Error = WSAGetLastError();
        v42 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v42, Error);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v43 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v43);
    }
  }
  *((_QWORD *)this + 13) = v40;
  v44 = v69;
  if ( v69 != *((_QWORD *)this + 20) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 160);
    *((_QWORD *)this + 20) = v44;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 160);
  }
  *((_DWORD *)this + 49) = v67;
  if ( (int)RDPAPI_GetGlobalObject(&CLSID_RDPPlatformPerfMonLogger, &IID_IRdpPerfMonLogger, &v65) >= 0 )
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
    v47 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, char *))(*(_QWORD *)v65 + 32LL))(
            v65,
            *((unsigned int *)this + 49),
            bstrVal,
            (char *)this + 200);
    if ( v47 < 0 )
    {
      v48 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_105:
        *((_DWORD *)this + 60) = GetTickCount();
        goto LABEL_106;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_101:
        if ( v48 != &WPP_GLOBAL_Control && (*((_DWORD *)v48 + 7) & 0x800) != 0 && *((_BYTE *)v48 + 25) >= 5u )
        {
          v50 = *((_QWORD *)this + 25);
          v51 = *((_DWORD *)this + 49);
          v52 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ddq(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            31,
            &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
            v52,
            v51,
            v50);
        }
        goto LABEL_105;
      }
      v49 = RdpWppGetCurrentThreadActivityIdPrefix();
      cbOutBuffer[0] = v47;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
        v49,
        (__int64)"GetTransportPerfMonSession failed. Perfmon counter sill not be available",
        *(_QWORD *)cbOutBuffer);
    }
    v48 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_101;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v45 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v45);
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
    v33 = RdpWppGetCurrentThreadActivityIdPrefix();
    v34 = 32;
    v35 = "Failed to initialize the transport worker";
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
    v33 = RdpWppGetCurrentThreadActivityIdPrefix();
    v34 = 33;
    v35 = "Failed to associate sock with IO completion port.";
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v53 = *((_DWORD *)this + 26);
    v54 = *((_DWORD *)this + 49);
    v55 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids, v55, v54, v53);
  }
  EventActivityIdControl(2u, &ActivityId);
  if ( *((_QWORD *)this + 9)
    && (unsigned int)IsTLSLoggerEnabled(
                       -2147483646,
                       L"SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations") == 1 )
  {
    TLSLoggerInstance = CreateTLSLoggerInstance(v56, (char *)this + 248);
    Instance = MapXResultToHR(TLSLoggerInstance);
    if ( Instance >= 0 )
    {
      v59 = CreateTLSLoggerInstance(v58, (char *)this + 256);
      Instance = MapXResultToHR(v59);
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
    cbOutBuffer[0] = Instance;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v14,
      (unsigned int)&WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v15,
      *(_QWORD *)cbOutBuffer);
    goto LABEL_134;
  }
LABEL_135:
  VariantClear(&pvarg);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v64);
  v60 = v65;
  if ( v65 )
  {
    v65 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v60 + 16LL))(v60);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140079378  push    rbp
0x14007937a  push    rbx
0x14007937b  push    rsi
0x14007937c  push    rdi
0x14007937d  push    r12
0x14007937f  push    r13
0x140079381  push    r14
0x140079383  push    r15
0x140079385  lea     rbp, [rsp-188h]
0x14007938d  sub     rsp, 288h
0x140079394  mov     rax, cs:__security_cookie
0x14007939b  xor     rax, rsp
0x14007939e  mov     [rbp+1C0h+var_50], rax
0x1400793a5  xor     eax, eax
0x1400793a7  mov     [rsp+2C0h+s], r9
0x1400793ac  xor     r14d, r14d
0x1400793af  mov     [rbp+1C0h+vInBuffer], rax
0x1400793b3  mov     rbx, r8
0x1400793b6  mov     dword ptr [rsp+2C0h+optval], r14d
0x1400793bb  mov     rdi, rdx
0x1400793be  mov     [rsp+2C0h+var_260], r14
0x1400793c3  mov     r15, rcx
0x1400793c6  mov     [rbp+1C0h+var_208], eax
0x1400793c9  xorps   xmm0, xmm0
0x1400793cc  mov     [rsp+2C0h+var_268], r14
0x1400793d1  xorps   xmm1, xmm1
0x1400793d4  mov     qword ptr [rbp+1C0h+pvarg+10h], rax
0x1400793d8  xor     edx, edx; Val
0x1400793da  lea     rcx, [rbp+1C0h+WSAData]; void *
0x1400793de  mov     r8d, 198h; Size
0x1400793e4  movups  [rbp+1C0h+var_200], xmm0
0x1400793e8  movups  xmmword ptr [rsp+2C0h+pvarg], xmm1
0x1400793ed  call    memset_0
0x1400793f2  lea     rcx, [rsp+2C0h+pvarg]; pvarg
0x1400793f7  call    cs:__imp_VariantInit
0x1400793fd  mov     rax, [rbx]
0x140079400  mov     rcx, rbx
0x140079403  mov     rax, [rax+68h]
0x140079407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007940c  mov     rdx, [rbx]
0x14007940f  mov     rcx, rbx
0x140079412  mov     [rsp+2C0h+var_250], eax
0x140079416  mov     rax, [rdx+50h]
0x14007941a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007941f  mov     [rbp+1C0h+var_230], rax
0x140079423  mov     rcx, rbx
0x140079426  lea     rax, [r15+8]
0x14007942a  or      dword ptr [rax+14h], 2
0x14007942e  mov     rdx, [rbx]
0x140079431  mov     [rbp+1C0h+var_228], rax
0x140079435  mov     rax, [rdx+70h]
0x140079439  lea     rdx, [rbp+1C0h+var_200]
0x14007943d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079442  mov     esi, eax
0x140079444  test    eax, eax
0x140079446  jns     short loc_140079495
0x140079448  mov     rax, cs:WPP_GLOBAL_Control
0x14007944f  lea     r14, WPP_GLOBAL_Control
0x140079456  cmp     rax, r14
0x140079459  jz      loc_140079DAD
0x14007945f  mov     r13d, 8
0x140079465  test    [rax+1Ch], r13b
0x140079469  jz      loc_140079DAD
0x14007946f  cmp     byte ptr [rax+19h], 2
0x140079473  jb      loc_140079DAD
0x140079479  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007947e  lea     edx, [r13+8]
0x140079482  lea     rcx, aFailedToRetrie; "Failed to retrieve the connection UUID"
0x140079489  lea     r8, WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids
0x140079490  jmp     loc_140079D91
0x140079495  mov     rax, cs:WPP_GLOBAL_Control
0x14007949c  lea     r14, WPP_GLOBAL_Control
0x1400794a3  lea     r12, WPP_c2bf2f543ca332c7069d5f3b56e12da2_Traceguids
0x1400794aa  cmp     rax, r14
0x1400794ad  jz      short loc_1400794F9
0x1400794af  test    dword ptr [rax+1Ch], 800h
0x1400794b6  jz      short loc_1400794F9
0x1400794b8  cmp     byte ptr [rax+19h], 4
0x1400794bc  jb      short loc_1400794F9
0x1400794be  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400794c3  mov     ecx, [rbp+1C0h+arg_28]
0x1400794c9  mov     edx, 11h
0x1400794ce  mov     [rsp+2C0h+cbOutBuffer], ecx
0x1400794d2  mov     r9d, eax
0x1400794d5  mov     ecx, [rbp+1C0h+arg_20]
0x1400794db  mov     r8, r12
0x1400794de  mov     [rsp+2C0h+optlen], ecx
0x1400794e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400794e9  mov     rcx, [rcx+10h]
0x1400794ed  call    WPP_SF_DLD
0x1400794f2  mov     rax, cs:WPP_GLOBAL_Control
0x1400794f9  mov     esi, 80004005h
0x1400794fe  mov     r13d, 8
0x140079504  test    rdi, rdi
0x140079507  jz      short loc_140079532
0x140079509  mov     rax, [rdi]
0x14007950c  lea     r8, [rsp+2C0h+var_268]
0x140079511  lea     rdx, IID_IRDPCollection
0x140079518  mov     rcx, rdi
0x14007951b  mov     rax, [rax]
0x14007951e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079523  mov     ebx, eax
0x140079525  test    eax, eax
0x140079527  jns     short loc_140079575
0x140079529  mov     rax, cs:WPP_GLOBAL_Control
0x140079530  jmp     short loc_140079534
0x140079532  mov     ebx, esi
0x140079534  cmp     rax, r14
0x140079537  jz      short loc_140079575
0x140079539  test    [rax+1Ch], r13b
0x14007953d  jz      short loc_140079575
0x14007953f  cmp     byte ptr [rax+19h], 2
0x140079543  jb      short loc_140079575
0x140079545  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007954a  lea     rcx, aFailedToQiForI; "Failed to QI for IRDPENCPlatformContext"
0x140079551  mov     [rsp+2C0h+cbOutBuffer], ebx
0x140079555  mov     qword ptr [rsp+2C0h+optlen], rcx
0x14007955a  mov     edx, 12h
0x14007955f  mov     rcx, cs:WPP_GLOBAL_Control
0x140079566  mov     r9d, eax
0x140079569  mov     r8, r12
0x14007956c  mov     rcx, [rcx+10h]
0x140079570  call    WPP_SF_DsD
0x140079575  mov     rcx, [rsp+2C0h+var_268]
0x14007957a  test    rcx, rcx
0x14007957d  jz      loc_140079660
0x140079583  mov     rax, [rcx]
0x140079586  lea     r9, [r15+48h]
0x14007958a  lea     r8, IID_IRdpTransportEventLogCallbacks
0x140079591  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x140079598  mov     rax, [rax+30h]
0x14007959c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400795a1  mov     ebx, eax
0x1400795a3  test    eax, eax
0x1400795a5  jns     short loc_1400795EF
0x1400795a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400795ae  cmp     rcx, r14
0x1400795b1  jz      short loc_1400795EF
0x1400795b3  test    [rcx+1Ch], r13b
0x1400795b7  jz      short loc_1400795EF
0x1400795b9  cmp     byte ptr [rcx+19h], 2
0x1400795bd  jb      short loc_1400795EF
0x1400795bf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400795c4  lea     rcx, aTheEventlogSes; "The eventlog session does not exsit"
0x1400795cb  mov     [rsp+2C0h+cbOutBuffer], ebx
0x1400795cf  mov     qword ptr [rsp+2C0h+optlen], rcx
0x1400795d4  mov     edx, 13h
0x1400795d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400795e0  mov     r9d, eax
0x1400795e3  mov     r8, r12
0x1400795e6  mov     rcx, [rcx+10h]
0x1400795ea  call    WPP_SF_DsD
0x1400795ef  mov     rcx, [rsp+2C0h+var_268]
0x1400795f4  lea     r9, [r15+50h]
0x1400795f8  lea     r8, IID_IRdpStateTransitionEventLogCallbacks
0x1400795ff  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x140079606  mov     rax, [rcx]
0x140079609  mov     rax, [rax+30h]
0x14007960d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140079612  mov     ebx, eax
0x140079614  test    eax, eax
0x140079616  jns     short loc_140079660
0x140079618  mov     rcx, cs:WPP_GLOBAL_Control
0x14007961f  cmp     rcx, r14
0x140079622  jz      short loc_140079660
0x140079624  test    [rcx+1Ch], r13b
0x140079628  jz      short loc_140079660
0x14007962a  cmp     byte ptr [rcx+19h], 2
0x14007962e  jb      short loc_140079660
0x140079630  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140079635  lea     rcx, aTheStateTransi; "The state transition eventlog session d"...
0x14007963c  mov     [rsp+2C0h+cbOutBuffer], ebx
0x140079640  mov     qword ptr [rsp+2C0h+optlen], rcx
0x140079645  mov     edx, 14h
0x14007964a  mov     rcx, cs:WPP_GLOBAL_Control
0x140079651  mov     r9d, eax
0x140079654  mov     r8, r12
0x140079657  mov     rcx, [rcx+10h]
0x14007965b  call    WPP_SF_DsD
0x140079660  movups  xmm0, xmmword ptr [r15+0D8h]
0x140079668  lea     rdx, [rbp+1C0h+ActivityId]; ActivityId
0x14007966c  mov     ecx, 4; ControlCode
0x140079671  movdqu  xmmword ptr [rbp+1C0h+ActivityId.Data1], xmm0
0x140079676  call    cs:__imp_EventActivityIdControl
0x14007967c  lea     rcx, [r15+58h]; this
0x140079680  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x140079685  test    eax, eax
0x140079687  jnz     short loc_1400796E9
0x140079689  mov     rax, cs:WPP_GLOBAL_Control
0x140079690  cmp     rax, r14
0x140079693  jz      short loc_1400796D5
0x140079695  test    [rax+1Ch], r13b
0x140079699  jz      short loc_1400796D5
0x14007969b  cmp     byte ptr [rax+19h], 2
0x14007969f  jb      short loc_1400796D5
0x1400796a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400796a6  lea     r8, aEncoderFailedT; "Encoder failed to initialize lock"
0x1400796ad  mov     [rsp+2C0h+cbOutBuffer], 80004005h
0x1400796b5  mov     qword ptr [rsp+2C0h+optlen], r8
0x1400796ba  mov     edx, 15h
0x1400796bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400796c6  mov     r9d, eax
0x1400796c9  mov     r8, r12
0x1400796cc  mov     rcx, [rcx+10h]
0x1400796d0  call    WPP_SF_DsD
0x1400796d5  mov     ecx, 2; ControlCode
0x1400796da  lea     rdx, [rbp+1C0h+ActivityId]; ActivityId
0x1400796de  call    cs:__imp_EventActivityIdControl
0x1400796e4  jmp     loc_140079DAD
0x1400796e9  xor     r9d, r9d; lpName
0x1400796ec  xor     r8d, r8d; bInitialState
0x1400796ef  xor     ecx, ecx; lpEventAttributes
0x1400796f1  lea     edx, [r9+1]; bManualReset
0x1400796f5  call    cs:__imp_CreateEventW
0x1400796fb  mov     [r15+80h], rax
0x140079702  test    rax, rax
0x140079705  jnz     short loc_140079764
0x140079707  call    cs:__imp_GetLastError
0x14007970d  mov     ebx, eax
0x14007970f  mov     rax, cs:WPP_GLOBAL_Control
0x140079716  cmp     rax, r14
0x140079719  jz      short loc_14007974B
0x14007971b  test    [rax+1Ch], r13b
0x14007971f  jz      short loc_14007974B
0x140079721  cmp     byte ptr [rax+19h], 2
0x140079725  jb      short loc_14007974B
0x140079727  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007972c  mov     rcx, cs:WPP_GLOBAL_Control
0x140079733  mov     edx, 16h
0x140079738  mov     r9d, eax
0x14007973b  mov     [rsp+2C0h+optlen], ebx
0x14007973f  mov     r8, r12
0x140079742  mov     rcx, [rcx+10h]
0x140079746  call    WPP_SF_Dd
0x14007974b  test    ebx, ebx
0x14007974d  jle     short loc_14007975A
0x14007974f  movzx   ebx, bx
0x140079752  or      ebx, 80070000h
0x140079758  test    ebx, ebx
0x14007975a  cmovns  ebx, esi
0x14007975d  mov     esi, ebx
0x14007975f  jmp     loc_1400796D5
0x140079764  lea     r8, [r15+0A8h]
0x14007976b  call    ?CreateInstance@?$CTSObjectPool@VCRdpEncIoContext@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRdpEncIoContext>::CreateInstance(uint,uint,CTSObjectPool<CRdpEncIoContext> * *,int)
0x140079770  mov     esi, eax
0x140079772  test    eax, eax
0x140079774  jns     short loc_1400797B9
0x140079776  mov     rax, cs:WPP_GLOBAL_Control
0x14007977d  cmp     rax, r14
0x140079780  jz      loc_1400796D5
0x140079786  test    [rax+1Ch], r13b
0x14007978a  jz      loc_1400796D5
0x140079790  cmp     byte ptr [rax+19h], 2
0x140079794  jb      loc_1400796D5
0x14007979a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007979f  mov     edx, 17h
0x1400797a4  lea     rcx, aFailedToCreate_34; "Failed to create IO Context pool"
0x1400797ab  mov     [rsp+2C0h+cbOutBuffer], esi
0x1400797af  mov     qword ptr [rsp+2C0h+optlen], rcx
0x1400797b4  jmp     loc_1400796BF
0x1400797b9  lea     r8, [r15+0B0h]
0x1400797c0  call    ?CreateInstance@?$CTSObjectPool@VCRDPENCCONStreamBufferPoolObject@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(uint,uint,CTSObjectPool<CRDPENCCONStreamBufferPoolObject> * *,int)
0x1400797c5  mov     esi, eax
0x1400797c7  test    eax, eax
0x1400797c9  jns     short loc_140079802
0x1400797cb  mov     rax, cs:WPP_GLOBAL_Control
0x1400797d2  cmp     rax, r14
0x1400797d5  jz      loc_1400796D5
0x1400797db  test    [rax+1Ch], r13b
0x1400797df  jz      loc_1400796D5
0x1400797e5  cmp     byte ptr [rax+19h], 2
0x1400797e9  jb      loc_1400796D5
0x1400797ef  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400797f4  mov     edx, 18h
0x1400797f9  lea     rcx, aFailedToCreate_11; "Failed to create Small StreamBuffer poo"...
0x140079800  jmp     short loc_1400797AB
0x140079802  lea     r8, [r15+0B8h]
0x140079809  call    ?CreateInstance@?$CTSObjectPool@VCRDPENCCONStreamBufferPoolObject@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CRDPENCCONStreamBufferPoolObject>::CreateInstance(uint,uint,CTSObjectPool<CRDPENCCONStreamBufferPoolObject> * *,int)
0x14007980e  mov     esi, eax
0x140079810  test    eax, eax
0x140079812  jns     short loc_14007984E
0x140079814  mov     rax, cs:WPP_GLOBAL_Control
0x14007981b  cmp     rax, r14
0x14007981e  jz      loc_1400796D5
0x140079824  test    [rax+1Ch], r13b
0x140079828  jz      loc_1400796D5
0x14007982e  cmp     byte ptr [rax+19h], 2
0x140079832  jb      loc_1400796D5
0x140079838  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14007983d  mov     edx, 19h
0x140079842  lea     rcx, aFailedToCreate_22; "Failed to create Large StreamBuffer poo"...
0x140079849  jmp     loc_1400797AB
0x14007984e  mov     ebx, 2
0x140079853  lea     rdx, [rbp+1C0h+WSAData]; lpWSAData
0x140079857  mov     ecx, ebx; wVersionRequested
0x140079859  call    cs:__imp_WSAStartup
0x14007985f  mov     esi, eax
0x140079861  test    eax, eax
0x140079863  jle     short loc_14007986E
0x140079865  movzx   esi, ax
  ... truncated ...
```
