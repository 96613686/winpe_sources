# FwDynDataNotifySinkProc

- ea: `0x180095b40`
- end: `0x18009632f`
- name: `FwDynDataNotifySinkProc`
- size: `2031`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x18005adb4`
- `0x18005ca4c`
- `0x18005ccd0`
- `0x1800683d0`
- `0x18006d0b8`
- `0x1800729c0`
- `0x180073488`
- `0x18007687c`
- `0x180085ed0`
- `0x180092424`
- `0x180092720`
- `0x1800945b0`
- `0x180095b40`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095cea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009613e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009617a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095cea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095ecd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009613e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009617a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180095f24`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180095f24`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180096056`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180096056`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800962b9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800962b9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180095c08`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180095c08`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180095c61`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180095c61`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800962d2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800962eb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800962ff`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800962d2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800962eb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800962ff`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180095ccf`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180095d4b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180095ccf`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180095d4b`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180095e4c`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180095ebd`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800960d0`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18009612a`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180095e4c`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x180095ebd`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x1800960d0`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18009612a`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x180095d2d`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x180095e9f`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x180095f74`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x1800960ff`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x180095d2d`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x180095e9f`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x180095f74`
- `fwbase!FwLicensingIsNetIsolationOnly` at `0x1800960ff`

## string_xrefs

- `0x180095c58`: `ServicesActive`

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
    if ( !WaitForSingleObjectEx(qword_180133330, 0xFFFFFFFF, 1) )
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
            _InterlockedCompareExchange((_DWORD *)&qword_180133C10 + 1, 1, 0);
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
            WPP_SF_d(*(_QWORD *)(v16 + 16), v18, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids, v19);
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
        WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids,
        (unsigned int)v14);
LABEL_57:
      v16 = WPP_GLOBAL_Control;
      goto LABEL_58;
    }
    if ( ((pNotifyBuffer.ServiceStatus.dwCurrentState - 1) & 0xFFFFFFFD) == 0 )
    {
      _InterlockedCompareExchange((_DWORD *)&qword_180133C10 + 1, 0, 1);
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
      WPP_SF_d(*(_QWORD *)(v6 + 16), v7, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids, v8);
LABEL_94:
      v6 = WPP_GLOBAL_Control;
    }
LABEL_95:
    if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 4) != 0 )
      WPP_SF_(*(_QWORD *)(v6 + 16), 73, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids);
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
0x180095b40  push    rbx
0x180095b42  push    rsi
0x180095b43  push    rdi
0x180095b44  push    r12
0x180095b46  push    r14
0x180095b48  push    r15
0x180095b4a  sub     rsp, 138h
0x180095b51  mov     rax, cs:__security_cookie
0x180095b58  xor     rax, rsp
0x180095b5b  mov     [rsp+168h+var_48], rax
0x180095b63  xor     ebx, ebx
0x180095b65  mov     r12d, ebx
0x180095b68  mov     [rsp+168h+var_128], rbx
0x180095b6d  mov     [rsp+168h+var_50], ebx
0x180095b74  mov     [rsp+168h+var_148], ebx
0x180095b78  mov     edi, ebx
0x180095b7a  mov     [rsp+168h+var_100], rbx
0x180095b7f  mov     [rsp+168h+hService], rbx
0x180095b84  mov     esi, ebx
0x180095b86  mov     [rsp+168h+hSCObject], rbx
0x180095b8b  lea     r14d, [rbx+50h]
0x180095b8f  mov     r8d, r14d; Size
0x180095b92  xor     edx, edx; Val
0x180095b94  lea     rcx, [rsp+168h+pNotifyBuffer]; void *
0x180095b99  call    memset_0
0x180095b9e  mov     [rsp+168h+var_58], ebx
0x180095ba5  mov     r8d, r14d; Size
0x180095ba8  xor     edx, edx; Val
0x180095baa  lea     rcx, [rsp+168h+var_A8]; void *
0x180095bb2  call    memset_0
0x180095bb7  mov     [rsp+168h+var_54], ebx
0x180095bbe  lea     r14d, [rbx+1]
0x180095bc2  mov     [rsp+168h+pNotifyBuffer.dwVersion], r14d
0x180095bc7  lea     rcx, ?FwDynDataSvcNotify@@YAXPEAX@Z; FwDynDataSvcNotify(void *)
0x180095bce  mov     [rsp+168h+pNotifyBuffer.pfnNotifyCallback], rcx
0x180095bd3  lea     rax, [rsp+168h+var_58]
0x180095bdb  mov     [rsp+168h+pNotifyBuffer.pContext], rax
0x180095be3  mov     [rsp+168h+var_A8.dwVersion], r14d
0x180095beb  mov     [rsp+168h+var_A8.pfnNotifyCallback], rcx
0x180095bf3  lea     rax, [rsp+168h+var_54]
0x180095bfb  mov     [rsp+168h+var_A8.pContext], rax
0x180095c03  lea     edx, [rbx+4]; dwCoInit
0x180095c06  xor     ecx, ecx; pvReserved
0x180095c08  call    cs:__imp_CoInitializeEx
0x180095c0f  nop     dword ptr [rax+rax+00h]
0x180095c14  test    eax, eax
0x180095c16  jns     short loc_180095C50
0x180095c18  mov     [rsp+168h+var_144], ebx
0x180095c1c  mov     r15d, ebx
0x180095c1f  mov     [rsp+168h+var_140], rbx
0x180095c24  lea     rsi, WPP_GLOBAL_Control
0x180095c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180095c32  cmp     rcx, rsi
0x180095c35  jz      loc_18009628E
0x180095c3b  test    [rcx+1Ch], r14b
0x180095c3f  jz      loc_18009621D
0x180095c45  lea     edx, [rbx+3Ch]
0x180095c48  mov     r9d, eax
0x180095c4b  jmp     loc_180096206
0x180095c50  mov     [rsp+168h+var_144], r14d
0x180095c55  mov     r8d, r14d; dwDesiredAccess
0x180095c58  lea     rdx, DatabaseName; "ServicesActive"
0x180095c5f  xor     ecx, ecx; lpMachineName
0x180095c61  call    cs:__imp_OpenSCManagerW
0x180095c68  nop     dword ptr [rax+rax+00h]
0x180095c6d  mov     r15, rax
0x180095c70  mov     [rsp+168h+var_140], rax
0x180095c75  mov     [rsp+168h+var_118], rax
0x180095c7a  test    rax, rax
0x180095c7d  jnz     short loc_180095CBF
0x180095c7f  call    cs:__imp_GetLastError
0x180095c86  nop     dword ptr [rax+rax+00h]
0x180095c8b  test    eax, eax
0x180095c8d  jle     short loc_180095C97
0x180095c8f  movzx   eax, ax
0x180095c92  or      eax, 80070000h
0x180095c97  lea     rsi, WPP_GLOBAL_Control
0x180095c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180095ca5  cmp     rcx, rsi
0x180095ca8  jz      loc_18009628E
0x180095cae  test    [rcx+1Ch], r14b
0x180095cb2  jz      loc_18009621D
0x180095cb8  mov     edx, 3Dh ; '='
0x180095cbd  jmp     short loc_180095C48
0x180095cbf  mov     r8d, 4; dwDesiredAccess
0x180095cc5  lea     rdx, aNetprofm; "NetProfm"
0x180095ccc  mov     rcx, r15; hSCManager
0x180095ccf  call    cs:__imp_OpenServiceW
0x180095cd6  nop     dword ptr [rax+rax+00h]
0x180095cdb  mov     [rsp+168h+hService], rax
0x180095ce0  mov     [rsp+168h+var_110], rax
0x180095ce5  test    rax, rax
0x180095ce8  jnz     short loc_180095D2D
0x180095cea  call    cs:__imp_GetLastError
0x180095cf1  nop     dword ptr [rax+rax+00h]
0x180095cf6  test    eax, eax
0x180095cf8  jle     short loc_180095D02
0x180095cfa  movzx   eax, ax
0x180095cfd  or      eax, 80070000h
0x180095d02  lea     rsi, WPP_GLOBAL_Control
0x180095d09  mov     rcx, cs:WPP_GLOBAL_Control
0x180095d10  cmp     rcx, rsi
0x180095d13  jz      loc_18009628E
0x180095d19  test    [rcx+1Ch], r14b
0x180095d1d  jz      loc_18009621D
0x180095d23  mov     edx, 3Eh ; '>'
0x180095d28  jmp     loc_180095C48
0x180095d2d  call    cs:__imp_FwLicensingIsNetIsolationOnly
0x180095d34  nop     dword ptr [rax+rax+00h]
0x180095d39  test    eax, eax
0x180095d3b  jnz     short loc_180095DA7
0x180095d3d  lea     r8d, [rax+4]; dwDesiredAccess
0x180095d41  lea     rdx, aIphlpsvc; "IpHlpSvc"
0x180095d48  mov     rcx, r15; hSCManager
0x180095d4b  call    cs:__imp_OpenServiceW
0x180095d52  nop     dword ptr [rax+rax+00h]
0x180095d57  mov     rsi, rax
0x180095d5a  mov     [rsp+168h+hSCObject], rax
0x180095d5f  test    rax, rax
0x180095d62  jnz     short loc_180095DA7
0x180095d64  call    cs:__imp_GetLastError
0x180095d6b  nop     dword ptr [rax+rax+00h]
0x180095d70  test    eax, eax
0x180095d72  jle     short loc_180095D7C
0x180095d74  movzx   eax, ax
0x180095d77  or      eax, 80070000h
0x180095d7c  lea     rsi, WPP_GLOBAL_Control
0x180095d83  mov     rcx, cs:WPP_GLOBAL_Control
0x180095d8a  cmp     rcx, rsi
0x180095d8d  jz      loc_18009628E
0x180095d93  test    [rcx+1Ch], r14b
0x180095d97  jz      loc_18009621D
0x180095d9d  mov     edx, 3Fh ; '?'
0x180095da2  jmp     loc_180095C48
0x180095da7  mov     ecx, 68h ; 'h'; Size
0x180095dac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180095db1  mov     rdi, rax
0x180095db4  mov     [rsp+168h+var_108], rax
0x180095db9  xor     edx, edx; Val
0x180095dbb  lea     r8d, [rdx+68h]; Size
0x180095dbf  mov     rcx, rax; void *
0x180095dc2  call    memset_0
0x180095dc7  mov     rcx, rdi; this
0x180095dca  call    ??0CNetProfileEventSink@@QEAA@XZ; CNetProfileEventSink::CNetProfileEventSink(void)
0x180095dcf  mov     rdi, rax
0x180095dd2  test    rdi, rdi
0x180095dd5  jz      loc_1800961DE
0x180095ddb  mov     rcx, rdi; this
0x180095dde  cmp     [rax+0Ch], ebx
0x180095de1  jge     short loc_180095DF7
0x180095de3  call    ??_GCNetProfileEventSink@@QEAAPEAXI@Z; CNetProfileEventSink::`scalar deleting destructor'(uint)
0x180095de8  mov     rdi, rbx
0x180095deb  lea     rsi, WPP_GLOBAL_Control
0x180095df2  jmp     loc_180096216
0x180095df7  mov     rax, [rax]
0x180095dfa  lea     r8, [rsp+168h+var_100]
0x180095dff  lea     rdx, IID_IUnknown
0x180095e06  mov     rax, [rax]
0x180095e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095e0e  test    eax, eax
0x180095e10  jns     short loc_180095E3D
0x180095e12  lea     rsi, WPP_GLOBAL_Control
0x180095e19  mov     rcx, cs:WPP_GLOBAL_Control
0x180095e20  cmp     rcx, rsi
0x180095e23  jz      loc_18009627A
0x180095e29  test    [rcx+1Ch], r14b
0x180095e2d  jz      loc_18009621D
0x180095e33  mov     edx, 41h ; 'A'
0x180095e38  jmp     loc_180095C48
0x180095e3d  lea     r8, [rsp+168h+pNotifyBuffer]; pNotifyBuffer
0x180095e42  mov     edx, 0Ch; dwNotifyMask
0x180095e47  mov     rcx, [rsp+168h+hService]; hService
0x180095e4c  call    cs:__imp_NotifyServiceStatusChangeW
0x180095e53  nop     dword ptr [rax+rax+00h]
0x180095e58  test    eax, eax
0x180095e5a  jz      short loc_180095E9F
0x180095e5c  call    cs:__imp_GetLastError
0x180095e63  nop     dword ptr [rax+rax+00h]
0x180095e68  test    eax, eax
0x180095e6a  jle     short loc_180095E74
0x180095e6c  movzx   eax, ax
0x180095e6f  or      eax, 80070000h
0x180095e74  lea     rsi, WPP_GLOBAL_Control
0x180095e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180095e82  cmp     rcx, rsi
0x180095e85  jz      loc_18009627A
0x180095e8b  test    [rcx+1Ch], r14b
0x180095e8f  jz      loc_18009621D
0x180095e95  mov     edx, 42h ; 'B'
0x180095e9a  jmp     loc_180095C48
0x180095e9f  call    cs:__imp_FwLicensingIsNetIsolationOnly
0x180095ea6  nop     dword ptr [rax+rax+00h]
0x180095eab  test    eax, eax
0x180095ead  jnz     short loc_180095F10
0x180095eaf  lea     r8, [rsp+168h+var_A8]; pNotifyBuffer
0x180095eb7  lea     edx, [rax+8]; dwNotifyMask
0x180095eba  mov     rcx, rsi; hService
0x180095ebd  call    cs:__imp_NotifyServiceStatusChangeW
0x180095ec4  nop     dword ptr [rax+rax+00h]
0x180095ec9  test    eax, eax
0x180095ecb  jz      short loc_180095F10
0x180095ecd  call    cs:__imp_GetLastError
0x180095ed4  nop     dword ptr [rax+rax+00h]
0x180095ed9  test    eax, eax
0x180095edb  jle     short loc_180095EE5
0x180095edd  movzx   eax, ax
0x180095ee0  or      eax, 80070000h
0x180095ee5  lea     rsi, WPP_GLOBAL_Control
0x180095eec  mov     rcx, cs:WPP_GLOBAL_Control
0x180095ef3  cmp     rcx, rsi
0x180095ef6  jz      loc_18009627A
0x180095efc  test    [rcx+1Ch], r14b
0x180095f00  jz      loc_18009621D
0x180095f06  mov     edx, 43h ; 'C'
0x180095f0b  jmp     loc_180095C48
0x180095f10  lea     rsi, WPP_GLOBAL_Control
0x180095f17  mov     r8d, r14d; bAlertable
0x180095f1a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180095f1d  mov     rcx, cs:qword_180133330; hHandle
0x180095f24  call    cs:__imp_WaitForSingleObjectEx
0x180095f2b  nop     dword ptr [rax+rax+00h]
0x180095f30  test    eax, eax
0x180095f32  jz      loc_180096216
0x180095f38  cmp     [rsp+168h+var_54], r14d
0x180095f40  jnz     short loc_180095F56
0x180095f42  cmp     [rsp+168h+var_A8.ServiceStatus.dwCurrentState], 4
0x180095f4a  jnz     short loc_180095F56
0x180095f4c  call    FwAdhSitesSubnetsRefreshSubscription
0x180095f51  call    FwHttpProxyRefreshSubscription
0x180095f56  cmp     [rsp+168h+var_58], r14d
0x180095f5e  jnz     loc_1800960E4
0x180095f64  mov     eax, [rsp+168h+pNotifyBuffer.ServiceStatus.dwCurrentState]
0x180095f6b  cmp     eax, 4
0x180095f6e  jnz     loc_18009608B
0x180095f74  call    cs:__imp_FwLicensingIsNetIsolationOnly
0x180095f7b  nop     dword ptr [rax+rax+00h]
0x180095f80  test    eax, eax
0x180095f82  jz      short loc_180095F89
0x180095f84  call    FwHttpProxyRefreshSubscription
0x180095f89  mov     r8d, [rsp+168h+var_50]; unsigned int
0x180095f91  mov     edx, [rsp+168h+var_148]; int
0x180095f95  lea     rcx, [rsp+168h+var_128]; struct IConnectionPoint **
0x180095f9a  call    ?FwDynDataNLSConnectionPointObjectsRefresh@@YAJPEAPEAUIConnectionPoint@@HK@Z; FwDynDataNLSConnectionPointObjectsRefresh(IConnectionPoint * *,int,ulong)
0x180095f9f  mov     r15d, eax
0x180095fa2  test    eax, eax
0x180095fa4  jns     short loc_180095FD0
0x180095fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180095fad  cmp     rcx, rsi
0x180095fb0  jz      short loc_180095FD7
0x180095fb2  test    byte ptr [rcx+1Ch], 4
0x180095fb6  jz      short loc_180095FD7
0x180095fb8  mov     edx, 44h ; 'D'
0x180095fbd  mov     r9d, eax
0x180095fc0  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x180095fc7  mov     rcx, [rcx+10h]
0x180095fcb  call    WPP_SF_d
0x180095fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180095fd7  mov     [rsp+168h+var_148], ebx
0x180095fdb  mov     r12, [rsp+168h+var_128]
0x180095fe0  test    r12, r12
0x180095fe3  jz      short loc_180096025
0x180095fe5  mov     rax, [r12]
0x180095fe9  lea     r8, [rsp+168h+var_50]
0x180095ff1  mov     rdx, [rsp+168h+var_100]
0x180095ff6  mov     rcx, r12
0x180095ff9  mov     rax, [rax+28h]
0x180095ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096002  mov     r15d, eax
0x180096005  test    eax, eax
0x180096007  jns     short loc_180096067
0x180096009  mov     rcx, cs:WPP_GLOBAL_Control
0x180096010  cmp     rcx, rsi
0x180096013  jz      short loc_180096048
0x180096015  test    byte ptr [rcx+1Ch], 4
0x180096019  jz      short loc_180096048
0x18009601b  mov     edx, 45h ; 'E'
0x180096020  mov     r9d, eax
0x180096023  jmp     short loc_180096038
0x180096025  cmp     rcx, rsi
0x180096028  jz      short loc_180096048
0x18009602a  test    byte ptr [rcx+1Ch], 4
0x18009602e  jz      short loc_180096048
0x180096030  mov     edx, 46h ; 'F'
0x180096035  mov     r9d, r15d
0x180096038  lea     r8, WPP_0043c1167b9d39bdb1a15ac1c4aee9c9_Traceguids
0x18009603f  mov     rcx, [rcx+10h]
0x180096043  call    WPP_SF_d
0x180096048  cmp     r15d, 8000000Ah
0x18009604f  jnz     short loc_18009606C
0x180096051  mov     ecx, 0FAh; dwMilliseconds
0x180096056  call    cs:__imp_Sleep
0x18009605d  nop     dword ptr [rax+rax+00h]
0x180096062  jmp     loc_180095F89
0x180096067  mov     [rsp+168h+var_148], r14d
0x18009606c  xor     eax, eax
0x18009606e  lock cmpxchg dword ptr cs:qword_180133C10+4, r14d
0x180096077  mov     rcx, rdi; this
0x18009607a  call    ?RegisterForNlmQuarantineSync@CNetProfileEventSink@@QEAAJXZ; CNetProfileEventSink::RegisterForNlmQuarantineSync(void)
0x18009607f  xor     edx, edx; bool
0x180096081  mov     rcx, rdi; this
  ... truncated ...
```
