# FwDynDataNotifySinkProc

- ea: `0x180090ff0`
- end: `0x180091748`
- name: `FwDynDataNotifySinkProc`
- size: `1880`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x180055f28`
- `0x1800579d8`
- `0x180057c88`
- `0x180064ba0`
- `0x18006a320`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800733bc`
- `0x180081d48`
- `0x18008db40`
- `0x18008de10`
- `0x18008fbf8`
- `0x180090ff0`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800911ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800912d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009157c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800915b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800911ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800912d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009157c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800915b2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180091386`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180091386`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800914ac`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800914ac`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800916eb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800916eb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800910b8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800910b8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009110b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009110b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800916fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180091711`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009171f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800916fe`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180091711`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009171f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009116d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800911d7`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009116d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800911d7`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800912cc`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18009132b`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180091520`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18009156e`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800912cc`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18009132b`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180091520`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18009156e`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x1800911bf`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x180091313`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x1800913d0`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x180091549`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x1800911bf`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x180091313`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x1800913d0`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x180091549`

## string_xrefs

- `0x180091102`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FwDynDataNotifySinkProc(PVOID Parameter)
{
  struct IConnectionPoint *v1; // r12
  CNetProfileEventSink *v2; // rdi
  SC_HANDLE v3; // rsi
  int LastError; // eax
  SC_HANDLE v5; // r15
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  SC_HANDLE v9; // rax
  SC_HANDLE v11; // rax
  int *v12; // rax
  unsigned int v13; // edx
  int v14; // eax
  unsigned int v15; // r15d
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r9
  int v21; // [rsp+20h] [rbp-148h]
  int v22; // [rsp+24h] [rbp-144h]
  SC_HANDLE v23; // [rsp+28h] [rbp-140h]
  SC_HANDLE hService; // [rsp+30h] [rbp-138h]
  struct IConnectionPoint *v25; // [rsp+40h] [rbp-128h] BYREF
  SC_HANDLE hSCObject; // [rsp+48h] [rbp-120h]
  SC_HANDLE v27; // [rsp+50h] [rbp-118h]
  SC_HANDLE v28; // [rsp+58h] [rbp-110h]
  void *v29; // [rsp+60h] [rbp-108h]
  __int64 v30; // [rsp+68h] [rbp-100h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+70h] [rbp-F8h] BYREF
  SERVICE_NOTIFY_2W v32; // [rsp+C0h] [rbp-A8h] BYREF
  int v33; // [rsp+110h] [rbp-58h] BYREF
  int v34; // [rsp+114h] [rbp-54h] BYREF
  unsigned int v35; // [rsp+118h] [rbp-50h] BYREF

  v1 = 0;
  v25 = 0;
  v35 = 0;
  v21 = 0;
  v2 = 0;
  v30 = 0;
  hService = 0;
  v3 = 0;
  hSCObject = 0;
  memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
  v33 = 0;
  memset_0(&v32, 0, sizeof(v32));
  v34 = 0;
  pNotifyBuffer.dwVersion = 1;
  pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)FwDynDataSvcNotify;
  pNotifyBuffer.pContext = &v33;
  v32.dwVersion = 1;
  v32.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)FwDynDataSvcNotify;
  v32.pContext = &v34;
  LastError = CoInitializeEx(0, 4u);
  if ( LastError < 0 )
  {
    v22 = 0;
    v5 = 0;
    v23 = 0;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 60;
        goto LABEL_5;
      }
      goto LABEL_95;
    }
    goto LABEL_104;
  }
  v22 = 1;
  v9 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v5 = v9;
  v23 = v9;
  v27 = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 61;
        goto LABEL_5;
      }
      goto LABEL_95;
    }
    goto LABEL_104;
  }
  hService = OpenServiceW(v9, L"NetProfm", 4u);
  v28 = hService;
  if ( !hService )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 62;
        goto LABEL_5;
      }
      goto LABEL_95;
    }
    goto LABEL_104;
  }
  if ( !(unsigned int)FwLicensingIsNetIsolationOnly() )
  {
    v11 = OpenServiceW(v5, L"IpHlpSvc", 4u);
    v3 = v11;
    hSCObject = v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v7 = 63;
          goto LABEL_5;
        }
        goto LABEL_95;
      }
      goto LABEL_104;
    }
  }
  try
  {
    v29 = operator new(0x68u);
    memset_0(v29, 0, 0x68u);
    v12 = (int *)CNetProfileEventSink::CNetProfileEventSink((CNetProfileEventSink *)v29);
  }
  catch ( ... )
  {
    v1 = v25;
    v21 = 0;
    v2 = 0;
    v22 = 1;
    v5 = v27;
    v23 = v27;
    hService = v28;
    goto LABEL_90;
  }
  v2 = (CNetProfileEventSink *)v12;
  if ( !v12 )
  {
LABEL_90:
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 64;
        v8 = 2147942414LL;
        goto LABEL_93;
      }
      goto LABEL_95;
    }
    goto LABEL_104;
  }
  if ( v12[3] < 0 )
  {
    CNetProfileEventSink::`scalar deleting destructor'((CNetProfileEventSink *)v12, v13);
    v2 = 0;
    goto LABEL_94;
  }
  LastError = (**(__int64 (__fastcall ***)(int *, GUID *, __int64 *))v12)(v12, &IID_IUnknown, &v30);
  if ( LastError < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 65;
        goto LABEL_5;
      }
      goto LABEL_95;
    }
    goto LABEL_103;
  }
  if ( NotifyServiceStatusChangeW(hService, 0xCu, &pNotifyBuffer) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 66;
        goto LABEL_5;
      }
      goto LABEL_95;
    }
    goto LABEL_103;
  }
  if ( !(unsigned int)FwLicensingIsNetIsolationOnly() && NotifyServiceStatusChangeW(v3, 8u, &v32) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 67;
        goto LABEL_5;
      }
      goto LABEL_95;
    }
    goto LABEL_103;
  }
  while ( 1 )
  {
    if ( !WaitForSingleObjectEx(qword_18012D160, 0xFFFFFFFF, 1) )
      goto LABEL_94;
    if ( v34 == 1 && v32.ServiceStatus.dwCurrentState == 4 )
    {
      FwAdhSitesSubnetsRefreshSubscription();
      FwHttpProxyRefreshSubscription();
    }
    if ( v33 != 1 )
      goto LABEL_76;
    if ( pNotifyBuffer.ServiceStatus.dwCurrentState == 4 )
    {
      if ( (unsigned int)FwLicensingIsNetIsolationOnly() )
        FwHttpProxyRefreshSubscription();
      while ( 1 )
      {
        v14 = FwDynDataNLSConnectionPointObjectsRefresh(&v25, v21, v35);
        v15 = v14;
        if ( v14 >= 0 )
          goto LABEL_57;
        v16 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          break;
LABEL_58:
        v21 = 0;
        v1 = v25;
        if ( v25 )
        {
          v17 = ((__int64 (__fastcall *)(struct IConnectionPoint *, __int64, unsigned int *))v25->lpVtbl->Advise)(
                  v25,
                  v30,
                  &v35);
          v15 = v17;
          if ( v17 >= 0 )
          {
            v21 = 1;
LABEL_70:
            _InterlockedCompareExchange((_DWORD *)&qword_18012DA40 + 1, 1, 0);
            CNetProfileEventSink::RegisterForNlmQuarantineSync(v2);
            CNetProfileEventSink::Operate(v2, 0);
LABEL_73:
            if ( v33 == 1 )
              goto LABEL_74;
            goto LABEL_76;
          }
          v16 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          {
            v18 = 69;
            v19 = (unsigned int)v17;
LABEL_66:
            WPP_SF_d(*(_QWORD *)(v16 + 16), v18, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids, v19);
          }
        }
        else if ( (_UNKNOWN *)v16 != &WPP_GLOBAL_Control && (*(_BYTE *)(v16 + 28) & 4) != 0 )
        {
          v18 = 70;
          v19 = v15;
          goto LABEL_66;
        }
        if ( v15 != -2147483638 )
          goto LABEL_70;
        Sleep(0xFAu);
      }
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        68,
        WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids,
        (unsigned int)v14);
LABEL_57:
      v16 = WPP_GLOBAL_Control;
      goto LABEL_58;
    }
    if ( ((pNotifyBuffer.ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) == 0 )
    {
      _InterlockedCompareExchange((_DWORD *)&qword_18012DA40 + 1, 0, 1);
      CNetProfileEventSink::UnregisterForNlmQuarantineSync(v2);
      goto LABEL_73;
    }
LABEL_74:
    if ( !pNotifyBuffer.dwNotificationStatus )
    {
      v33 = 0;
      if ( NotifyServiceStatusChangeW(hService, 0xCu, &pNotifyBuffer) )
        break;
    }
LABEL_76:
    if ( v34 == 1 && !v32.dwNotificationStatus && !(unsigned int)FwLicensingIsNetIsolationOnly() )
    {
      v34 = 0;
      if ( NotifyServiceStatusChangeW(hSCObject, 8u, &v32) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v7 = 72;
            goto LABEL_5;
          }
          goto LABEL_95;
        }
        goto LABEL_98;
      }
    }
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 71;
LABEL_5:
      v8 = (unsigned int)LastError;
LABEL_93:
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids, v8);
LABEL_94:
      v6 = WPP_GLOBAL_Control;
    }
LABEL_95:
    if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(v6 + 16), 73, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids);
  }
LABEL_98:
  if ( v21 == 1 )
    ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v1->lpVtbl->Unadvise)(v1, v35);
  if ( v1 )
    ((void (__fastcall *)(struct IConnectionPoint *))v1->lpVtbl->Release)(v1);
  v5 = v23;
  if ( v2 )
  {
LABEL_103:
    (*(void (__fastcall **)(CNetProfileEventSink *))(*(_QWORD *)v2 + 16LL))(v2);
    v30 = 0;
  }
LABEL_104:
  FwReleaseMarshalData();
  if ( lpParameter )
  {
    ((void (__fastcall *)(IUnknown *))lpParameter->lpVtbl->Release)(lpParameter);
    lpParameter = 0;
  }
  if ( v22 == 1 )
    CoUninitialize();
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  if ( hService )
    CloseServiceHandle(hService);
  if ( v5 )
    CloseServiceHandle(v5);
  return 0;
}

```

## disassembly

```asm
0x180090ff0  push    rbx
0x180090ff2  push    rsi
0x180090ff3  push    rdi
0x180090ff4  push    r12
0x180090ff6  push    r14
0x180090ff8  push    r15
0x180090ffa  sub     rsp, 138h
0x180091001  mov     rax, cs:__security_cookie
0x180091008  xor     rax, rsp
0x18009100b  mov     [rsp+168h+var_48], rax
0x180091013  xor     ebx, ebx
0x180091015  mov     r12d, ebx
0x180091018  mov     [rsp+168h+var_128], rbx
0x18009101d  mov     [rsp+168h+var_50], ebx
0x180091024  mov     [rsp+168h+var_148], ebx
0x180091028  mov     edi, ebx
0x18009102a  mov     [rsp+168h+var_100], rbx
0x18009102f  mov     [rsp+168h+hService], rbx
0x180091034  mov     esi, ebx
0x180091036  mov     [rsp+168h+hSCObject], rbx
0x18009103b  lea     r14d, [rbx+50h]
0x18009103f  mov     r8d, r14d; Size
0x180091042  xor     edx, edx; Val
0x180091044  lea     rcx, [rsp+168h+pNotifyBuffer]; void *
0x180091049  call    memset_0
0x18009104e  mov     [rsp+168h+var_58], ebx
0x180091055  mov     r8d, r14d; Size
0x180091058  xor     edx, edx; Val
0x18009105a  lea     rcx, [rsp+168h+var_A8]; void *
0x180091062  call    memset_0
0x180091067  mov     [rsp+168h+var_54], ebx
0x18009106e  lea     r14d, [rbx+1]
0x180091072  mov     [rsp+168h+pNotifyBuffer.dwVersion], r14d
0x180091077  lea     rcx, ?FwDynDataSvcNotify@@YAXPEAX@Z; FwDynDataSvcNotify(void *)
0x18009107e  mov     [rsp+168h+pNotifyBuffer.pfnNotifyCallback], rcx
0x180091083  lea     rax, [rsp+168h+var_58]
0x18009108b  mov     [rsp+168h+pNotifyBuffer.pContext], rax
0x180091093  mov     [rsp+168h+var_A8.dwVersion], r14d
0x18009109b  mov     [rsp+168h+var_A8.pfnNotifyCallback], rcx
0x1800910a3  lea     rax, [rsp+168h+var_54]
0x1800910ab  mov     [rsp+168h+var_A8.pContext], rax
0x1800910b3  lea     edx, [rbx+4]; dwCoInit
0x1800910b6  xor     ecx, ecx; pvReserved
0x1800910b8  call    cs:__imp_CoInitializeEx
0x1800910be  test    eax, eax
0x1800910c0  jns     short loc_1800910FA
0x1800910c2  mov     [rsp+168h+var_144], ebx
0x1800910c6  mov     r15d, ebx
0x1800910c9  mov     [rsp+168h+var_140], rbx
0x1800910ce  lea     rsi, WPP_GLOBAL_Control
0x1800910d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800910dc  cmp     rcx, rsi
0x1800910df  jz      loc_1800916C0
0x1800910e5  test    [rcx+1Ch], r14b
0x1800910e9  jz      loc_18009164F
0x1800910ef  lea     edx, [rbx+3Ch]
0x1800910f2  mov     r9d, eax
0x1800910f5  jmp     loc_180091638
0x1800910fa  mov     [rsp+168h+var_144], r14d
0x1800910ff  mov     r8d, r14d; dwDesiredAccess
0x180091102  lea     rdx, DatabaseName; "ServicesActive"
0x180091109  xor     ecx, ecx; lpMachineName
0x18009110b  call    cs:__imp_OpenSCManagerW
0x180091111  mov     r15, rax
0x180091114  mov     [rsp+168h+var_140], rax
0x180091119  mov     [rsp+168h+var_118], rax
0x18009111e  test    rax, rax
0x180091121  jnz     short loc_18009115D
0x180091123  call    cs:__imp_GetLastError
0x180091129  test    eax, eax
0x18009112b  jle     short loc_180091135
0x18009112d  movzx   eax, ax
0x180091130  or      eax, 80070000h
0x180091135  lea     rsi, WPP_GLOBAL_Control
0x18009113c  mov     rcx, cs:WPP_GLOBAL_Control
0x180091143  cmp     rcx, rsi
0x180091146  jz      loc_1800916C0
0x18009114c  test    [rcx+1Ch], r14b
0x180091150  jz      loc_18009164F
0x180091156  mov     edx, 3Dh ; '='
0x18009115b  jmp     short loc_1800910F2
0x18009115d  mov     r8d, 4; dwDesiredAccess
0x180091163  lea     rdx, aNetprofm; "NetProfm"
0x18009116a  mov     rcx, r15; hSCManager
0x18009116d  call    cs:__imp_OpenServiceW
0x180091173  mov     [rsp+168h+hService], rax
0x180091178  mov     [rsp+168h+var_110], rax
0x18009117d  test    rax, rax
0x180091180  jnz     short loc_1800911BF
0x180091182  call    cs:__imp_GetLastError
0x180091188  test    eax, eax
0x18009118a  jle     short loc_180091194
0x18009118c  movzx   eax, ax
0x18009118f  or      eax, 80070000h
0x180091194  lea     rsi, WPP_GLOBAL_Control
0x18009119b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800911a2  cmp     rcx, rsi
0x1800911a5  jz      loc_1800916C0
0x1800911ab  test    [rcx+1Ch], r14b
0x1800911af  jz      loc_18009164F
0x1800911b5  mov     edx, 3Eh ; '>'
0x1800911ba  jmp     loc_1800910F2
0x1800911bf  call    cs:__imp_FwLicensingIsNetIsolationOnly
0x1800911c5  test    eax, eax
0x1800911c7  jnz     short loc_180091227
0x1800911c9  lea     r8d, [rax+4]; dwDesiredAccess
0x1800911cd  lea     rdx, aIphlpsvc; "IpHlpSvc"
0x1800911d4  mov     rcx, r15; hSCManager
0x1800911d7  call    cs:__imp_OpenServiceW
0x1800911dd  mov     rsi, rax
0x1800911e0  mov     [rsp+168h+hSCObject], rax
0x1800911e5  test    rax, rax
0x1800911e8  jnz     short loc_180091227
0x1800911ea  call    cs:__imp_GetLastError
0x1800911f0  test    eax, eax
0x1800911f2  jle     short loc_1800911FC
0x1800911f4  movzx   eax, ax
0x1800911f7  or      eax, 80070000h
0x1800911fc  lea     rsi, WPP_GLOBAL_Control
0x180091203  mov     rcx, cs:WPP_GLOBAL_Control
0x18009120a  cmp     rcx, rsi
0x18009120d  jz      loc_1800916C0
0x180091213  test    [rcx+1Ch], r14b
0x180091217  jz      loc_18009164F
0x18009121d  mov     edx, 3Fh ; '?'
0x180091222  jmp     loc_1800910F2
0x180091227  mov     ecx, 68h ; 'h'; Size
0x18009122c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180091231  mov     rdi, rax
0x180091234  mov     [rsp+168h+var_108], rax
0x180091239  xor     edx, edx; Val
0x18009123b  lea     r8d, [rdx+68h]; Size
0x18009123f  mov     rcx, rax; void *
0x180091242  call    memset_0
0x180091247  mov     rcx, rdi; this
0x18009124a  call    ??0CNetProfileEventSink@@QEAA@XZ; CNetProfileEventSink::CNetProfileEventSink(void)
0x18009124f  mov     rdi, rax
0x180091252  test    rdi, rdi
0x180091255  jz      loc_180091610
0x18009125b  mov     rcx, rdi; this
0x18009125e  cmp     [rax+0Ch], ebx
0x180091261  jge     short loc_180091277
0x180091263  call    ??_GCNetProfileEventSink@@QEAAPEAXI@Z; CNetProfileEventSink::`scalar deleting destructor'(uint)
0x180091268  mov     rdi, rbx
0x18009126b  lea     rsi, WPP_GLOBAL_Control
0x180091272  jmp     loc_180091648
0x180091277  mov     rax, [rax]
0x18009127a  lea     r8, [rsp+168h+var_100]
0x18009127f  lea     rdx, IID_IUnknown
0x180091286  mov     rax, [rax]
0x180091289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009128e  test    eax, eax
0x180091290  jns     short loc_1800912BD
0x180091292  lea     rsi, WPP_GLOBAL_Control
0x180091299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800912a0  cmp     rcx, rsi
0x1800912a3  jz      loc_1800916AC
0x1800912a9  test    [rcx+1Ch], r14b
0x1800912ad  jz      loc_18009164F
0x1800912b3  mov     edx, 41h ; 'A'
0x1800912b8  jmp     loc_1800910F2
0x1800912bd  lea     r8, [rsp+168h+pNotifyBuffer]; pNotifyBuffer
0x1800912c2  mov     edx, 0Ch; dwNotifyMask
0x1800912c7  mov     rcx, [rsp+168h+hService]; hService
0x1800912cc  call    cs:__imp_NotifyServiceStatusChangeW
0x1800912d2  test    eax, eax
0x1800912d4  jz      short loc_180091313
0x1800912d6  call    cs:__imp_GetLastError
0x1800912dc  test    eax, eax
0x1800912de  jle     short loc_1800912E8
0x1800912e0  movzx   eax, ax
0x1800912e3  or      eax, 80070000h
0x1800912e8  lea     rsi, WPP_GLOBAL_Control
0x1800912ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800912f6  cmp     rcx, rsi
0x1800912f9  jz      loc_1800916AC
0x1800912ff  test    [rcx+1Ch], r14b
0x180091303  jz      loc_18009164F
0x180091309  mov     edx, 42h ; 'B'
0x18009130e  jmp     loc_1800910F2
0x180091313  call    cs:__imp_FwLicensingIsNetIsolationOnly
0x180091319  test    eax, eax
0x18009131b  jnz     short loc_180091372
0x18009131d  lea     r8, [rsp+168h+var_A8]; pNotifyBuffer
0x180091325  lea     edx, [rax+8]; dwNotifyMask
0x180091328  mov     rcx, rsi; hService
0x18009132b  call    cs:__imp_NotifyServiceStatusChangeW
0x180091331  test    eax, eax
0x180091333  jz      short loc_180091372
0x180091335  call    cs:__imp_GetLastError
0x18009133b  test    eax, eax
0x18009133d  jle     short loc_180091347
0x18009133f  movzx   eax, ax
0x180091342  or      eax, 80070000h
0x180091347  lea     rsi, WPP_GLOBAL_Control
0x18009134e  mov     rcx, cs:WPP_GLOBAL_Control
0x180091355  cmp     rcx, rsi
0x180091358  jz      loc_1800916AC
0x18009135e  test    [rcx+1Ch], r14b
0x180091362  jz      loc_18009164F
0x180091368  mov     edx, 43h ; 'C'
0x18009136d  jmp     loc_1800910F2
0x180091372  lea     rsi, WPP_GLOBAL_Control
0x180091379  mov     r8d, r14d; bAlertable
0x18009137c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18009137f  mov     rcx, cs:qword_18012D160; hHandle
0x180091386  call    cs:__imp_WaitForSingleObjectEx
0x18009138c  test    eax, eax
0x18009138e  jz      loc_180091648
0x180091394  cmp     [rsp+168h+var_54], r14d
0x18009139c  jnz     short loc_1800913B2
0x18009139e  cmp     [rsp+168h+var_A8.ServiceStatus.dwCurrentState], 4
0x1800913a6  jnz     short loc_1800913B2
0x1800913a8  call    FwAdhSitesSubnetsRefreshSubscription
0x1800913ad  call    FwHttpProxyRefreshSubscription
0x1800913b2  cmp     [rsp+168h+var_58], r14d
0x1800913ba  jnz     loc_18009152E
0x1800913c0  mov     eax, [rsp+168h+pNotifyBuffer.ServiceStatus.dwCurrentState]
0x1800913c7  cmp     eax, 4
0x1800913ca  jnz     loc_1800914DB
0x1800913d0  call    cs:__imp_FwLicensingIsNetIsolationOnly
0x1800913d6  test    eax, eax
0x1800913d8  jz      short loc_1800913DF
0x1800913da  call    FwHttpProxyRefreshSubscription
0x1800913df  mov     r8d, [rsp+168h+var_50]; unsigned int
0x1800913e7  mov     edx, [rsp+168h+var_148]; int
0x1800913eb  lea     rcx, [rsp+168h+var_128]; struct IConnectionPoint **
0x1800913f0  call    ?FwDynDataNLSConnectionPointObjectsRefresh@@YAJPEAPEAUIConnectionPoint@@HK@Z; FwDynDataNLSConnectionPointObjectsRefresh(IConnectionPoint * *,int,ulong)
0x1800913f5  mov     r15d, eax
0x1800913f8  test    eax, eax
0x1800913fa  jns     short loc_180091426
0x1800913fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180091403  cmp     rcx, rsi
0x180091406  jz      short loc_18009142D
0x180091408  test    byte ptr [rcx+1Ch], 4
0x18009140c  jz      short loc_18009142D
0x18009140e  mov     edx, 44h ; 'D'
0x180091413  mov     r9d, eax
0x180091416  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x18009141d  mov     rcx, [rcx+10h]
0x180091421  call    WPP_SF_d
0x180091426  mov     rcx, cs:WPP_GLOBAL_Control
0x18009142d  mov     [rsp+168h+var_148], ebx
0x180091431  mov     r12, [rsp+168h+var_128]
0x180091436  test    r12, r12
0x180091439  jz      short loc_18009147B
0x18009143b  mov     rax, [r12]
0x18009143f  lea     r8, [rsp+168h+var_50]
0x180091447  mov     rdx, [rsp+168h+var_100]
0x18009144c  mov     rcx, r12
0x18009144f  mov     rax, [rax+28h]
0x180091453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091458  mov     r15d, eax
0x18009145b  test    eax, eax
0x18009145d  jns     short loc_1800914B7
0x18009145f  mov     rcx, cs:WPP_GLOBAL_Control
0x180091466  cmp     rcx, rsi
0x180091469  jz      short loc_18009149E
0x18009146b  test    byte ptr [rcx+1Ch], 4
0x18009146f  jz      short loc_18009149E
0x180091471  mov     edx, 45h ; 'E'
0x180091476  mov     r9d, eax
0x180091479  jmp     short loc_18009148E
0x18009147b  cmp     rcx, rsi
0x18009147e  jz      short loc_18009149E
0x180091480  test    byte ptr [rcx+1Ch], 4
0x180091484  jz      short loc_18009149E
0x180091486  mov     edx, 46h ; 'F'
0x18009148b  mov     r9d, r15d
0x18009148e  lea     r8, WPP_c17a8bb60d3a3c8fffd8e1287cd6d1ad_Traceguids
0x180091495  mov     rcx, [rcx+10h]
0x180091499  call    WPP_SF_d
0x18009149e  cmp     r15d, 8000000Ah
0x1800914a5  jnz     short loc_1800914BC
0x1800914a7  mov     ecx, 0FAh; dwMilliseconds
0x1800914ac  call    cs:__imp_Sleep
0x1800914b2  jmp     loc_1800913DF
0x1800914b7  mov     [rsp+168h+var_148], r14d
0x1800914bc  xor     eax, eax
0x1800914be  lock cmpxchg dword ptr cs:qword_18012DA40+4, r14d
0x1800914c7  mov     rcx, rdi; this
0x1800914ca  call    ?RegisterForNlmQuarantineSync@CNetProfileEventSink@@QEAAJXZ; CNetProfileEventSink::RegisterForNlmQuarantineSync(void)
0x1800914cf  xor     edx, edx; bool
0x1800914d1  mov     rcx, rdi; this
0x1800914d4  call    ?Operate@CNetProfileEventSink@@QEAAJ_N@Z; CNetProfileEventSink::Operate(bool)
0x1800914d9  jmp     short loc_1800914F7
0x1800914db  dec     eax
0x1800914dd  test    eax, 0FFFFFFFDh
0x1800914e2  jnz     short loc_180091501
0x1800914e4  mov     eax, r14d
0x1800914e7  lock cmpxchg dword ptr cs:qword_18012DA40+4, ebx
0x1800914ef  mov     rcx, rdi; this
0x1800914f2  call    ?UnregisterForNlmQuarantineSync@CNetProfileEventSink@@QEAAXXZ; CNetProfileEventSink::UnregisterForNlmQuarantineSync(void)
0x1800914f7  cmp     [rsp+168h+var_58], r14d
0x1800914ff  jnz     short loc_18009152E
0x180091501  cmp     [rsp+168h+pNotifyBuffer.dwNotificationStatus], ebx
0x180091508  jnz     short loc_18009152E
0x18009150a  mov     [rsp+168h+var_58], ebx
0x180091511  lea     r8, [rsp+168h+pNotifyBuffer]; pNotifyBuffer
0x180091516  mov     edx, 0Ch; dwNotifyMask
  ... truncated ...
```
