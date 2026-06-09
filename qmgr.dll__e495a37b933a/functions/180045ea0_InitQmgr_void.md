# InitQmgr(void)

- ea: `0x180045ea0`
- end: `0x18004669d`
- name: `?InitQmgr@@YAJXZ`
- size: `2045`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18008fbfc`

## callees

- `0x18000c520`
- `0x180045ea0`
- `0x1800466a4`
- `0x180046790`
- `0x180046948`
- `0x180046b90`
- `0x180046de8`
- `0x180046f5c`
- `0x180047114`
- `0x18008f1ec`
- `0x1800914d8`
- `0x180099850`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800ab6e8`
- `0x1800ab738`
- `0x1800ab7b0`
- `0x1800ab7fc`
- `0x1800ab83c`
- `0x1800b6fb0`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x180046220`
- `combase!__imp_CoGetSharedServiceId` at `0x180046220`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180046249`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180046249`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800460b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004616e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800462b0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800460b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004616e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800462b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004647d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004647d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800464b8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800464b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800465bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800465bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046046`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046525`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046548`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046046`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046525`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180046548`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046609`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046609`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045f68`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180045f68`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180045edf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180045edf`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800465cd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800465cd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180046473`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180046473`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 InitQmgr(void)
{
  unsigned int v0; // esi
  HRESULT v1; // eax
  void (*v2)(void); // r9
  unsigned int v3; // edi
  __int64; // rax
  HRESULT v5; // eax
  int v6; // eax
  ULONGLONG TickCount64; // r14
  int v8; // eax
  void *v9; // rax
  void *v10; // rax
  struct BitsComModule *v11; // rbx
  int SharedServiceId; // eax
  int v13; // eax
  void *v14; // rax
  CJobManager *v15; // rax
  CJobManager *v16; // rcx
  BitsComModule *v17; // rcx
  EVENT_LOG *v18; // rcx
  DWORD v19; // esi
  unsigned int i; // edi
  DWORD LastError; // eax
  CJobManager *v22; // rcx
  ULONGLONG v23; // rax
  EVENT_LOG *v24; // rcx
  int v25; // r8d
  int v26; // ebx
  unsigned int v27; // [rsp+30h] [rbp-368h] BYREF
  int v28; // [rsp+34h] [rbp-364h] BYREF
  _QWORD Context[3]; // [rsp+38h] [rbp-360h] BYREF
  HANDLE WaitHandle; // [rsp+50h] [rbp-348h]
  HANDLE hEvent; // [rsp+58h] [rbp-340h]
  __int64 v32; // [rsp+60h] [rbp-338h]
  ULONGLONG v33; // [rsp+68h] [rbp-330h]
  const ComError *v34; // [rsp+70h] [rbp-328h] BYREF
  void **pExceptionObject; // [rsp+80h] [rbp-318h] BYREF
  __int128 v36; // [rsp+88h] [rbp-310h]
  HRESULT v37; // [rsp+98h] [rbp-300h]
  int v38; // [rsp+9Ch] [rbp-2FCh]
  int v39; // [rsp+A0h] [rbp-2F8h]
  void **v40; // [rsp+E0h] [rbp-2B8h] BYREF
  __int128 v41; // [rsp+E8h] [rbp-2B0h]
  int v42; // [rsp+F8h] [rbp-2A0h]
  int v43; // [rsp+FCh] [rbp-29Ch]
  int v44; // [rsp+100h] [rbp-298h]
  void **v45; // [rsp+140h] [rbp-258h] BYREF
  __int128 v46; // [rsp+148h] [rbp-250h]
  int v47; // [rsp+158h] [rbp-240h]
  int v48; // [rsp+15Ch] [rbp-23Ch]
  int v49; // [rsp+160h] [rbp-238h]
  void **v50; // [rsp+1A0h] [rbp-1F8h] BYREF
  __int128 v51; // [rsp+1A8h] [rbp-1F0h]
  int v52; // [rsp+1B8h] [rbp-1E0h]
  int v53; // [rsp+1BCh] [rbp-1DCh]
  int v54; // [rsp+1C0h] [rbp-1D8h]
  void **v55; // [rsp+200h] [rbp-198h] BYREF
  __int128 v56; // [rsp+208h] [rbp-190h]
  int v57; // [rsp+218h] [rbp-180h]
  int v58; // [rsp+21Ch] [rbp-17Ch]
  int v59; // [rsp+220h] [rbp-178h]
  void **v60; // [rsp+260h] [rbp-138h] BYREF
  __int128 v61; // [rsp+268h] [rbp-130h]
  int v62; // [rsp+278h] [rbp-120h]
  int v63; // [rsp+27Ch] [rbp-11Ch]
  int v64; // [rsp+280h] [rbp-118h]
  void **v65; // [rsp+2C0h] [rbp-D8h] BYREF
  __int128 v66; // [rsp+2C8h] [rbp-D0h]
  int v67; // [rsp+2D8h] [rbp-C0h]
  int v68; // [rsp+2DCh] [rbp-BCh]
  int v69; // [rsp+2E0h] [rbp-B8h]
  void **v70; // [rsp+320h] [rbp-78h] BYREF
  __int128 v71; // [rsp+328h] [rbp-70h]
  int v72; // [rsp+338h] [rbp-60h]
  int v73; // [rsp+33Ch] [rbp-5Ch]
  int v74; // [rsp+340h] [rbp-58h]
  unsigned int v75; // [rsp+3A0h] [rbp+8h]
  unsigned int; // [rsp+3A0h] [rbp+8h]
  LPVOID ppv; // [rsp+3A8h] [rbp+10h] BYREF

  v0 = g_ServiceInstance;
  v75 = g_ServiceInstance;
  g_Manager = 0;
  g_EventLogger = 0;
  g_NetworkMonitor = 0;
  v1 = CoInitializeEx(0, 0);
  v3 = v1;
  if ( v1 < 0 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids, v0, v1);
     = v3;
    goto LABEL_102;
  }
  ScopedWatchdogTimer::ScopedWatchdogTimer(Context, 0x3A980u, -2147467234, v2);
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( v5 < 0 )
    {
      v36 = 0;
      pExceptionObject = &ComError::`vftable';
      v37 = v5;
      v38 = 49;
      v39 = 1;
      throw (ComError *)&pExceptionObject;
    }
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
    if ( v6 < 0 )
    {
      v41 = 0;
      v40 = &ComError::`vftable';
      v42 = v6;
      v43 = 50;
      v44 = 1;
      throw (ComError *)&v40;
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    TickCount64 = GetTickCount64();
    v8 = CheckLanManHashDisabled();
    if ( v8 < 0 )
    {
      v46 = 0;
      v45 = &ComError::`vftable';
      v47 = v8;
      v48 = 56;
      v49 = 1;
      throw (ComError *)&v45;
    }
    v9 = HeapAlloc(hBitsHeap, 8u, 0x18u);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 24);
      v51 = 0;
      v50 = &ComError::`vftable';
      v52 = -2147024882;
      v53 = 0;
      v54 = 1;
      throw (ComError *)&v50;
    }
    ppv = v9;
    g_EventLogger = EVENT_LOG::EVENT_LOG((EVENT_LOG *)v9);
    v10 = HeapAlloc(hBitsHeap, 8u, 0x470u);
    if ( !v10 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 1136);
      v56 = 0;
      v55 = &ComError::`vftable';
      v57 = -2147024882;
      v58 = 0;
      v59 = 1;
      throw (ComError *)&v55;
    }
    ppv = v10;
    g_NetworkMonitor = CNetworkMonitor::CNetworkMonitor((CNetworkMonitor *)v10);
    v11 = g_ComServerModule;
    SharedServiceId = CoGetSharedServiceId((char *)g_ComServerModule + 20);
    if ( SharedServiceId < 0 )
    {
      v71 = 0;
      v70 = &ComError::`vftable';
      v72 = SharedServiceId;
      v73 = 59;
      v74 = 1;
      throw (ComError *)&v70;
    }
    *((_DWORD *)v11 + 4) = 1;
    v13 = CoRegisterServerShutdownDelay(g_hServiceStopEvent, *((unsigned int *)g_GlobalInfo + 59));
    if ( v13 < 0 )
    {
      v61 = 0;
      v60 = &ComError::`vftable';
      v62 = v13;
      v63 = 60;
      v64 = 1;
      throw (ComError *)&v60;
    }
    v14 = HeapAlloc(hBitsHeap, 8u, 0x720u);
    if ( !v14 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 1824);
      v66 = 0;
      v65 = &ComError::`vftable';
      v67 = -2147024882;
      v68 = 0;
      v69 = 1;
      throw (ComError *)&v65;
    }
    ppv = v14;
    v15 = CJobManager::CJobManager((CJobManager *)v14);
    g_Manager = v15;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids, v0, v15);
    CJobManager::Startup(v16);
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids);
    g_ServiceState = 2;
    ReportServiceStartupPhase(11);
    BitsComModule::RegisterExternalClasses(v17);
    ReportStartupComplete();
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids);
      v18 = WPP_GLOBAL_Control;
    }
    if ( gServiceStatus.dwCurrentState != 4 )
    {
      v19 = 0;
      if ( v18 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x200) != 0 )
      {
        WPP_SF_ll(*((_QWORD *)v18 + 2));
        v18 = WPP_GLOBAL_Control;
      }
      gServiceStatus.dwControlsAccepted |= 0x101u;
      *(_QWORD *)&gServiceStatus.dwCheckPoint = 0;
      gServiceStatus.dwCurrentState = 4;
      for ( i = 0; i < 0xA; ++i )
      {
        if ( SetServiceStatus(ghServiceHandle, &gServiceStatus) )
          goto LABEL_57;
        LastError = GetLastError();
        v19 = LastError;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_533829f6437c324cb0547291f5f8d64b_Traceguids,
            i,
            LastError);
        Sleep(0x3E8u);
        v18 = WPP_GLOBAL_Control;
      }
      if ( v19 )
      {
        if ( v18 == (EVENT_LOG *)&WPP_GLOBAL_Control )
          goto LABEL_61;
        if ( (*((_BYTE *)v18 + 28) & 4) != 0 )
        {
          WPP_SF_Sd(*((_QWORD *)v18 + 2), 22, (int)WPP_533829f6437c324cb0547291f5f8d64b_Traceguids, (int)L"BITS", v19);
LABEL_57:
          v18 = WPP_GLOBAL_Control;
        }
      }
      if ( v18 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v18 + 2), 23, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids, 4);
    }
LABEL_61:
    if ( GetTickCount64() - TickCount64 > 0x7530 )
      ReportStartupDelayed();
    if ( hEvent )
    {
      v23 = GetTickCount64();
      v33 = v23;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a2fd4d7841f73b87c8a9d4021a310f46_Traceguids, v23 - v32);
        v24 = WPP_GLOBAL_Control;
      }
      if ( WaitHandle )
      {
        if ( v24 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
          WPP_SF_q(*((_QWORD *)v24 + 2), 14, WPP_a2fd4d7841f73b87c8a9d4021a310f46_Traceguids, Context);
        SetEvent(hEvent);
        UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        WaitHandle = 0;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a2fd4d7841f73b87c8a9d4021a310f46_Traceguids, Context);
      }
      CloseHandle(hEvent);
      hEvent = 0;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ComError `RTTI Type Descriptor', &v34) )
    {
      v25 = *((_DWORD *)v34 + 6);
      LODWORD(ppv) = v25;
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids, v75, v25);
      UninitQmgr();
       = (unsigned int)ppv;
      __eh34_try_continuation(0, &ComError `RTTI Type Descriptor', &loc_18004666E);
      goto LABEL_102;
    }
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)&v27) )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids, v27);
      UninitQmgr();
       = v27;
      __eh34_try_continuation(0, &long `RTTI Type Descriptor', &loc_180046677);
LABEL_102:
      ;
    }
    if ( __eh34_catch_type(0, &unsigned long `RTTI Type Descriptor', (ulong *)&v28) )
    {
      if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v26 = v28;
      }
      else
      {
        v26 = v28;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids,
          (unsigned int)v28);
      }
      UninitQmgr();
      if ( v26 > 0 )
         = (unsigned __int16)v26 | 0x80070000;
      else
         = v26;
       = ;
      __eh34_try_continuation(0, &unsigned long `RTTI Type Descriptor', &loc_18004667D);
      goto LABEL_102;
    }
  }
  CJobManager::TaskThread(v22);
  UninitQmgr();
   = 0;
  goto LABEL_102;
}

```

## disassembly

```asm
0x180045ea0  mov     [rsp+arg_10], rbx
0x180045ea5  mov     [rsp+arg_18], rsi
0x180045eaa  push    rdi
0x180045eab  push    r14
0x180045ead  push    r15
0x180045eaf  sub     rsp, 380h
0x180045eb6  mov     esi, cs:?g_ServiceInstance@@3JA; long g_ServiceInstance
0x180045ebc  mov     [rsp+398h+arg_0], esi
0x180045ec3  xor     r15d, r15d
0x180045ec6  mov     cs:?g_Manager@@3PEAVCJobManager@@EA, r15; CJobManager * g_Manager
0x180045ecd  mov     cs:?g_EventLogger@@3PEAVEVENT_LOG@@EA, r15; EVENT_LOG * g_EventLogger
0x180045ed4  mov     cs:?g_NetworkMonitor@@3PEAVCNetworkMonitor@@EA, r15; CNetworkMonitor * g_NetworkMonitor
0x180045edb  xor     edx, edx; dwCoInit
0x180045edd  xor     ecx, ecx; pvReserved
0x180045edf  call    cs:__imp_CoInitializeEx
0x180045ee5  mov     edi, eax
0x180045ee7  test    eax, eax
0x180045ee9  jns     short loc_180045F27
0x180045eeb  lea     rbx, WPP_GLOBAL_Control
0x180045ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x180045ef9  cmp     rcx, rbx
0x180045efc  jz      short loc_180045F20
0x180045efe  test    byte ptr [rcx+1Ch], 1
0x180045f02  jz      short loc_180045F20
0x180045f04  mov     edx, 0Ah
0x180045f09  mov     dword ptr [rsp+398h+ppv], eax
0x180045f0d  mov     r9d, esi
0x180045f10  lea     r8, WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids
0x180045f17  mov     rcx, [rcx+10h]
0x180045f1b  call    WPP_SF_Dd
0x180045f20  mov     eax, edi
0x180045f22  jmp     loc_180046684
0x180045f27  mov     edx, 3A980h; dwMilliseconds
0x180045f2c  mov     r8d, 8000401Eh; int
0x180045f32  lea     rcx, [rsp+398h+Context]; Context
0x180045f37  call    ??0ScopedWatchdogTimer@@QEAA@KJP6AXXZ@Z; ScopedWatchdogTimer::ScopedWatchdogTimer(ulong,long,void (*)(void))
0x180045f3c  nop
0x180045f3d  mov     [rsp+398h+arg_8], r15
0x180045f45  lea     rax, [rsp+398h+arg_8]
0x180045f4d  mov     [rsp+398h+ppv], rax; ppv
0x180045f52  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180045f59  xor     edx, edx; pUnkOuter
0x180045f5b  mov     r8d, 1; dwClsContext
0x180045f61  lea     rcx, CLSID_GlobalOptions; rclsid
0x180045f68  call    cs:__imp_CoCreateInstance
0x180045f6e  test    eax, eax
0x180045f70  jns     short loc_180045FBD
0x180045f72  xorps   xmm0, xmm0
0x180045f75  movups  [rsp+398h+var_310], xmm0
0x180045f7d  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180045f84  mov     [rsp+398h+pExceptionObject], rcx
0x180045f8c  mov     [rsp+398h+var_300], eax
0x180045f93  mov     [rsp+398h+var_2FC], 31h ; '1'
0x180045f9e  mov     [rsp+398h+var_2F8], 1
0x180045fa9  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180045fb0  lea     rcx, [rsp+398h+pExceptionObject]; pExceptionObject
0x180045fb8  call    _CxxThrowException_0
0x180045fbd  mov     rcx, [rsp+398h+arg_8]
0x180045fc5  mov     rax, [rcx]
0x180045fc8  mov     edx, 5
0x180045fcd  mov     r8d, 1
0x180045fd3  mov     rax, [rax+18h]
0x180045fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045fdc  test    eax, eax
0x180045fde  jns     short loc_18004602C
0x180045fe0  xorps   xmm0, xmm0
0x180045fe3  movups  [rsp+398h+var_2B0], xmm0
0x180045feb  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180045ff2  mov     [rsp+398h+var_2B8], rcx
0x180045ffa  mov     [rsp+398h+var_2A0], eax
0x180046001  mov     [rsp+398h+var_29C], 32h ; '2'
0x18004600c  mov     [rsp+398h+var_298], 1
0x180046017  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18004601e  lea     rcx, [rsp+398h+var_2B8]; pExceptionObject
0x180046026  call    _CxxThrowException_0
0x18004602c  mov     rcx, [rsp+398h+arg_8]
0x180046034  test    rcx, rcx
0x180046037  jz      short loc_180046046
0x180046039  mov     rax, [rcx]
0x18004603c  mov     rax, [rax+10h]
0x180046040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046045  nop
0x180046046  call    cs:__imp_GetTickCount64
0x18004604c  mov     r14, rax
0x18004604f  call    ?CheckLanManHashDisabled@@YAJXZ; CheckLanManHashDisabled(void)
0x180046054  test    eax, eax
0x180046056  jns     short loc_1800460A3
0x180046058  xorps   xmm0, xmm0
0x18004605b  movups  [rsp+398h+var_250], xmm0
0x180046063  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004606a  mov     [rsp+398h+var_258], rcx
0x180046072  mov     [rsp+398h+var_240], eax
0x180046079  mov     [rsp+398h+var_23C], 38h ; '8'
0x180046084  mov     [rsp+398h+var_238], 1
0x18004608f  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180046096  lea     rcx, [rsp+398h+var_258]; pExceptionObject
0x18004609e  call    _CxxThrowException_0
0x1800460a3  mov     edx, 8; dwFlags
0x1800460a8  mov     r8d, 18h; dwBytes
0x1800460ae  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800460b5  call    cs:__imp_HeapAlloc
0x1800460bb  test    rax, rax
0x1800460be  jnz     loc_180046144
0x1800460c4  lea     rbx, WPP_GLOBAL_Control
0x1800460cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800460d2  cmp     rcx, rbx
0x1800460d5  jz      short loc_1800460F8
0x1800460d7  test    byte ptr [rcx+1Ch], 4
0x1800460db  jz      short loc_1800460F8
0x1800460dd  mov     edx, 0Ah
0x1800460e2  mov     r9d, 18h
0x1800460e8  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800460ef  mov     rcx, [rcx+10h]
0x1800460f3  call    WPP_SF_d
0x1800460f8  xorps   xmm0, xmm0
0x1800460fb  movups  [rsp+398h+var_1F0], xmm0
0x180046103  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18004610a  mov     [rsp+398h+var_1F8], rcx
0x180046112  mov     [rsp+398h+var_1E0], 8007000Eh
0x18004611d  mov     [rsp+398h+var_1DC], r15d
0x180046125  mov     [rsp+398h+var_1D8], 1
0x180046130  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180046137  lea     rcx, [rsp+398h+var_1F8]; pExceptionObject
0x18004613f  call    _CxxThrowException_0
0x180046144  mov     [rsp+398h+arg_8], rax
0x18004614c  mov     rcx, rax; this
0x18004614f  call    ??0EVENT_LOG@@QEAA@XZ; EVENT_LOG::EVENT_LOG(void)
0x180046154  nop
0x180046155  mov     cs:?g_EventLogger@@3PEAVEVENT_LOG@@EA, rax; EVENT_LOG * g_EventLogger
0x18004615c  mov     edx, 8; dwFlags
0x180046161  mov     r8d, 470h; dwBytes
0x180046167  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x18004616e  call    cs:__imp_HeapAlloc
0x180046174  test    rax, rax
0x180046177  jnz     loc_1800461FD
0x18004617d  lea     rbx, WPP_GLOBAL_Control
0x180046184  mov     rcx, cs:WPP_GLOBAL_Control
0x18004618b  cmp     rcx, rbx
0x18004618e  jz      short loc_1800461B1
0x180046190  test    byte ptr [rcx+1Ch], 4
0x180046194  jz      short loc_1800461B1
0x180046196  mov     edx, 0Ah
0x18004619b  mov     r9d, 470h
0x1800461a1  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800461a8  mov     rcx, [rcx+10h]
0x1800461ac  call    WPP_SF_d
0x1800461b1  xorps   xmm0, xmm0
0x1800461b4  movups  [rsp+398h+var_190], xmm0
0x1800461bc  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800461c3  mov     [rsp+398h+var_198], rcx
0x1800461cb  mov     [rsp+398h+var_180], 8007000Eh
0x1800461d6  mov     [rsp+398h+var_17C], r15d
0x1800461de  mov     [rsp+398h+var_178], 1
0x1800461e9  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800461f0  lea     rcx, [rsp+398h+var_198]; pExceptionObject
0x1800461f8  call    _CxxThrowException_0
0x1800461fd  mov     [rsp+398h+arg_8], rax
0x180046205  mov     rcx, rax; this
0x180046208  call    ??0CNetworkMonitor@@QEAA@XZ; CNetworkMonitor::CNetworkMonitor(void)
0x18004620d  nop
0x18004620e  mov     cs:?g_NetworkMonitor@@3PEAVCNetworkMonitor@@EA, rax; CNetworkMonitor * g_NetworkMonitor
0x180046215  mov     rbx, cs:?g_ComServerModule@@3PEAVBitsComModule@@EA; BitsComModule * g_ComServerModule
0x18004621c  lea     rcx, [rbx+14h]
0x180046220  call    cs:__imp_CoGetSharedServiceId
0x180046226  test    eax, eax
0x180046228  js      loc_180046622
0x18004622e  mov     dword ptr [rbx+10h], 1
0x180046235  mov     rdx, cs:?g_GlobalInfo@@3PEAVGlobalInfo@@EA; GlobalInfo * g_GlobalInfo
0x18004623c  mov     edx, [rdx+0ECh]
0x180046242  mov     rcx, cs:?g_hServiceStopEvent@@3V?$auto_HANDLE@$0A@@@A; auto_HANDLE<0> g_hServiceStopEvent
0x180046249  call    cs:__imp_CoRegisterServerShutdownDelay
0x18004624f  test    eax, eax
0x180046251  jns     short loc_18004629E
0x180046253  xorps   xmm0, xmm0
0x180046256  movups  [rsp+398h+var_130], xmm0
0x18004625e  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180046265  mov     [rsp+398h+var_138], rcx
0x18004626d  mov     [rsp+398h+var_120], eax
0x180046274  mov     [rsp+398h+var_11C], 3Ch ; '<'
0x18004627f  mov     [rsp+398h+var_118], 1
0x18004628a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180046291  lea     rcx, [rsp+398h+var_138]; pExceptionObject
0x180046299  call    _CxxThrowException_0
0x18004629e  mov     edx, 8; dwFlags
0x1800462a3  mov     r8d, 720h; dwBytes
0x1800462a9  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x1800462b0  call    cs:__imp_HeapAlloc
0x1800462b6  test    rax, rax
0x1800462b9  jnz     loc_18004633F
0x1800462bf  lea     rbx, WPP_GLOBAL_Control
0x1800462c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462cd  cmp     rcx, rbx
0x1800462d0  jz      short loc_1800462F3
0x1800462d2  test    byte ptr [rcx+1Ch], 4
0x1800462d6  jz      short loc_1800462F3
0x1800462d8  mov     edx, 0Ah
0x1800462dd  mov     r9d, 720h
0x1800462e3  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x1800462ea  mov     rcx, [rcx+10h]
0x1800462ee  call    WPP_SF_d
0x1800462f3  xorps   xmm0, xmm0
0x1800462f6  movups  [rsp+398h+var_D0], xmm0
0x1800462fe  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180046305  mov     [rsp+398h+var_D8], rcx
0x18004630d  mov     [rsp+398h+var_C0], 8007000Eh
0x180046318  mov     [rsp+398h+var_BC], r15d
0x180046320  mov     [rsp+398h+var_B8], 1
0x18004632b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180046332  lea     rcx, [rsp+398h+var_D8]; pExceptionObject
0x18004633a  call    _CxxThrowException_0
0x18004633f  mov     [rsp+398h+arg_8], rax
0x180046347  mov     rcx, rax; this
0x18004634a  call    ??0CJobManager@@QEAA@XZ; CJobManager::CJobManager(void)
0x18004634f  nop
0x180046350  mov     cs:?g_Manager@@3PEAVCJobManager@@EA, rax; CJobManager * g_Manager
0x180046357  lea     rbx, WPP_GLOBAL_Control
0x18004635e  mov     rcx, cs:WPP_GLOBAL_Control
0x180046365  cmp     rcx, rbx
0x180046368  jz      short loc_18004638D
0x18004636a  test    byte ptr [rcx+1Ch], 1
0x18004636e  jz      short loc_18004638D
0x180046370  mov     edx, 0Bh
0x180046375  mov     [rsp+398h+ppv], rax
0x18004637a  mov     r9d, esi
0x18004637d  lea     r8, WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids
0x180046384  mov     rcx, [rcx+10h]
0x180046388  call    WPP_SF_dq
0x18004638d  call    ?Startup@CJobManager@@QEAAXXZ; CJobManager::Startup(void)
0x180046392  mov     rcx, cs:WPP_GLOBAL_Control
0x180046399  cmp     rcx, rbx
0x18004639c  jz      short loc_1800463B9
0x18004639e  test    byte ptr [rcx+1Ch], 1
0x1800463a2  jz      short loc_1800463B9
0x1800463a4  mov     edx, 0Ch
0x1800463a9  lea     r8, WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids
0x1800463b0  mov     rcx, [rcx+10h]
0x1800463b4  call    WPP_SF_
0x1800463b9  mov     cs:?g_ServiceState@@3W4MANAGER_STATE@@A, 2; MANAGER_STATE g_ServiceState
0x1800463c3  mov     ecx, 0Bh; int
0x1800463c8  call    ?ReportServiceStartupPhase@@YAJH@Z; ReportServiceStartupPhase(int)
0x1800463cd  call    ?RegisterExternalClasses@BitsComModule@@QEAAXXZ; BitsComModule::RegisterExternalClasses(void)
0x1800463d2  call    ?ReportStartupComplete@@YAXXZ; ReportStartupComplete(void)
0x1800463d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463de  cmp     rcx, rbx
0x1800463e1  jz      short loc_180046405
0x1800463e3  test    byte ptr [rcx+1Ch], 1
0x1800463e7  jz      short loc_180046405
0x1800463e9  mov     edx, 0Dh
0x1800463ee  lea     r8, WPP_9e7222c116ff303f5c9199a04bbad3e0_Traceguids
0x1800463f5  mov     rcx, [rcx+10h]
0x1800463f9  call    WPP_SF_
0x1800463fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180046405  mov     r9d, cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS gServiceStatus ...
0x18004640c  cmp     r9d, 4
0x180046410  jz      loc_180046525
0x180046416  mov     esi, r15d
0x180046419  cmp     rcx, rbx
0x18004641c  jz      short loc_18004643F
0x18004641e  test    dword ptr [rcx+1Ch], 200h
0x180046425  jz      short loc_18004643F
0x180046427  mov     dword ptr [rsp+398h+ppv], 4
0x18004642f  mov     rcx, [rcx+10h]
0x180046433  call    WPP_SF_ll
0x180046438  mov     rcx, cs:WPP_GLOBAL_Control
0x18004643f  or      cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 101h; _SERVICE_STATUS gServiceStatus ...
0x180046449  mov     qword ptr cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r15; _SERVICE_STATUS gServiceStatus ...
0x180046450  mov     cs:?gServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS gServiceStatus ...
0x18004645a  mov     edi, r15d
0x18004645d  nop     dword ptr [rax]
0x180046460  cmp     edi, 0Ah
0x180046463  jnb     short loc_1800464C9
0x180046465  lea     rdx, ?gServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18004646c  mov     rcx, cs:?ghServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180046473  call    cs:__imp_SetServiceStatus
0x180046479  test    eax, eax
0x18004647b  jnz     short loc_1800464F8
0x18004647d  call    cs:__imp_GetLastError
0x180046483  mov     esi, eax
0x180046485  mov     rcx, cs:WPP_GLOBAL_Control
0x18004648c  cmp     rcx, rbx
0x18004648f  jz      short loc_1800464B3
0x180046491  test    byte ptr [rcx+1Ch], 4
0x180046495  jz      short loc_1800464B3
0x180046497  mov     edx, 15h
0x18004649c  mov     dword ptr [rsp+398h+ppv], eax
0x1800464a0  mov     r9d, edi
0x1800464a3  lea     r8, WPP_533829f6437c324cb0547291f5f8d64b_Traceguids
0x1800464aa  mov     rcx, [rcx+10h]
0x1800464ae  call    WPP_SF_Dd
0x1800464b3  mov     ecx, 3E8h; dwMilliseconds
0x1800464b8  call    cs:__imp_Sleep
0x1800464be  inc     edi
0x1800464c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800464c7  jmp     short loc_180046460
0x1800464c9  test    esi, esi
0x1800464cb  jz      short loc_1800464FF
0x1800464cd  cmp     rcx, rbx
0x1800464d0  jz      short loc_180046525
0x1800464d2  test    byte ptr [rcx+1Ch], 4
0x1800464d6  jz      short loc_1800464FF
  ... truncated ...
```
