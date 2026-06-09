# DDMCleanUp(void)

- ea: `0x1800205b0`
- end: `0x180020e23`
- name: `?DDMCleanUp@@YAXXZ`
- size: `2163`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180008650`
- `0x18001bf40`

## callees

- `0x180007c0c`
- `0x180014e40`
- `0x1800205b0`
- `0x180028024`
- `0x18002ab4c`
- `0x18003bf14`
- `0x18003c2c8`
- `0x18003d278`
- `0x180049c50`
- `0x180052d5c`
- `0x180058dac`
- `0x1800593c4`
- `0x1800822a8`
- `0x180085cb4`
- `0x180089a14`
- `0x18008ba58`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800209a9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020a61`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020aae`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800209a9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020a61`
- `msvcrt!??3@YAXPEAX@Z` at `0x180020aae`
- `KERNEL32!LocalFree` at `0x180020916`
- `KERNEL32!LocalFree` at `0x180020929`
- `KERNEL32!LocalFree` at `0x180020951`
- `KERNEL32!LocalFree` at `0x180020964`
- `KERNEL32!LocalFree` at `0x180020916`
- `KERNEL32!LocalFree` at `0x180020929`
- `KERNEL32!LocalFree` at `0x180020951`
- `KERNEL32!LocalFree` at `0x180020964`
- `KERNEL32!DeleteCriticalSection` at `0x180020b2b`
- `KERNEL32!DeleteCriticalSection` at `0x180020b3e`
- `KERNEL32!DeleteCriticalSection` at `0x180020c01`
- `KERNEL32!DeleteCriticalSection` at `0x180020c14`
- `KERNEL32!DeleteCriticalSection` at `0x180020b2b`
- `KERNEL32!DeleteCriticalSection` at `0x180020b3e`
- `KERNEL32!DeleteCriticalSection` at `0x180020c01`
- `KERNEL32!DeleteCriticalSection` at `0x180020c14`
- `KERNEL32!FreeLibrary` at `0x1800205f8`
- `KERNEL32!FreeLibrary` at `0x18002065d`
- `KERNEL32!FreeLibrary` at `0x18002078d`
- `KERNEL32!FreeLibrary` at `0x1800207d2`
- `KERNEL32!FreeLibrary` at `0x1800205f8`
- `KERNEL32!FreeLibrary` at `0x18002065d`
- `KERNEL32!FreeLibrary` at `0x18002078d`
- `KERNEL32!FreeLibrary` at `0x1800207d2`
- `KERNEL32!HeapDestroy` at `0x180020c54`
- `KERNEL32!HeapDestroy` at `0x180020c54`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180020ced`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180020ced`
- `KERNEL32!CloseHandle` at `0x180020af0`
- `KERNEL32!CloseHandle` at `0x180020bbb`
- `KERNEL32!CloseHandle` at `0x180020d05`
- `KERNEL32!CloseHandle` at `0x180020af0`
- `KERNEL32!CloseHandle` at `0x180020bbb`
- `KERNEL32!CloseHandle` at `0x180020d05`
- `KERNEL32!LeaveCriticalSection` at `0x180020bf2`
- `KERNEL32!LeaveCriticalSection` at `0x180020bf2`
- `KERNEL32!EnterCriticalSection` at `0x180020b18`
- `KERNEL32!EnterCriticalSection` at `0x180020b79`
- `KERNEL32!EnterCriticalSection` at `0x180020b18`
- `KERNEL32!EnterCriticalSection` at `0x180020b79`
- `KERNEL32!HeapFree` at `0x1800207ba`
- `KERNEL32!HeapFree` at `0x1800207f3`
- `KERNEL32!HeapFree` at `0x180020814`
- `KERNEL32!HeapFree` at `0x180020835`
- `KERNEL32!HeapFree` at `0x180020856`
- `KERNEL32!HeapFree` at `0x180020877`
- `KERNEL32!HeapFree` at `0x180020898`
- `KERNEL32!HeapFree` at `0x1800208b9`
- `KERNEL32!HeapFree` at `0x1800208da`
- `KERNEL32!HeapFree` at `0x1800208fb`
- `KERNEL32!HeapFree` at `0x180020bd3`
- `KERNEL32!HeapFree` at `0x180020c35`
- `KERNEL32!HeapFree` at `0x1800207ba`
- `KERNEL32!HeapFree` at `0x1800207f3`
- `KERNEL32!HeapFree` at `0x180020814`
- `KERNEL32!HeapFree` at `0x180020835`
- `KERNEL32!HeapFree` at `0x180020856`
- `KERNEL32!HeapFree` at `0x180020877`
- `KERNEL32!HeapFree` at `0x180020898`
- `KERNEL32!HeapFree` at `0x1800208b9`
- `KERNEL32!HeapFree` at `0x1800208da`
- `KERNEL32!HeapFree` at `0x1800208fb`
- `KERNEL32!HeapFree` at `0x180020bd3`
- `KERNEL32!HeapFree` at `0x180020c35`
- `ADVAPI32!EventUnregister` at `0x180020d56`
- `ADVAPI32!EventUnregister` at `0x180020d56`
- `ADVAPI32!RegCloseKey` at `0x180020707`
- `ADVAPI32!RegCloseKey` at `0x180020726`
- `ADVAPI32!RegCloseKey` at `0x180020745`
- `ADVAPI32!RegCloseKey` at `0x180020707`
- `ADVAPI32!RegCloseKey` at `0x180020726`
- `ADVAPI32!RegCloseKey` at `0x180020745`
- `eappprxy!EapHostPeerUninitialize` at `0x180020696`
- `eappprxy!EapHostPeerUninitialize` at `0x180020696`
- `fwpuclnt!FwpmEngineClose0` at `0x180020a0c`
- `fwpuclnt!FwpmEngineClose0` at `0x180020a0c`

## pseudocode

```c
void DDMCleanUp(void)
{
  int v0; // esi
  char *v1; // rbx
  __int64 v2; // rdi
  void (*v3)(void); // rax
  void (__fastcall *v4)(_QWORD); // rax
  HMODULE v5; // rcx
  unsigned int v6; // ecx
  unsigned int v7; // edi
  char *i; // r8
  char *v9; // rbx
  void (*v10)(void); // rax
  DdmThreadPool *v11; // rbx
  DdmDeviceTable *Instance; // rax
  DdmThreadPool *v13; // rbx
  DdmDeviceTable *v14; // rbx
  HANDLE *v15; // rdx
  unsigned int v16; // edi
  unsigned int v17; // esi
  __int64 v18; // rbx
  HANDLE v19; // rcx
  LPVOID *v20; // rbx
  LPVOID *v21; // rax
  __int64 v22; // r8
  __int64 v23; // rax
  struct _VPN_DEVICE near **v24; // rbx
  __int64 v25; // rdi
  __int64 v26; // rcx
  REGHANDLE v27; // rcx
  struct _GUID v28; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v29; // [rsp+40h] [rbp-38h]
  int v30; // [rsp+48h] [rbp-30h]
  int v31; // [rsp+4Ch] [rbp-2Ch]

  v0 = *(_DWORD *)DdmDeviceTable::GetInstance(0x11u);
  if ( hLibModule )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
    qword_1800CF528 = 0;
    qword_1800CF530 = 0;
  }
  v1 = byte_1800CE498;
  v2 = 3;
  do
  {
    if ( !*(_DWORD *)v1 && *((_DWORD *)v1 + 1) )
    {
      v3 = (void (*)(void))*((_QWORD *)v1 + 5);
      if ( v3 )
        v3();
      if ( dword_1800CF654 )
      {
        v4 = (void (__fastcall *)(_QWORD))*((_QWORD *)v1 + 3);
        if ( v4 )
          v4(0);
      }
    }
    v5 = (HMODULE)*((_QWORD *)v1 + 1);
    if ( v5 )
    {
      FreeLibrary(v5);
      *(_QWORD *)v1 = 0;
      *((_QWORD *)v1 + 1) = 0;
      *((_QWORD *)v1 + 2) = 0;
      *((_QWORD *)v1 + 3) = 0;
      *((_QWORD *)v1 + 4) = 0;
      *((_QWORD *)v1 + 5) = 0;
      *((_QWORD *)v1 + 6) = 0;
    }
    v1 += 80;
    --v2;
  }
  while ( v2 );
  if ( dword_1800CF668 )
    EapHostPeerUninitialize();
  if ( (dword_1800CF4E0 & 0x20) != 0 )
    RasInterfaceMgmtUninit();
  if ( dword_1800CF518 )
  {
    v28 = GUID_NULL;
    RasSrvrStop(&v28, 0, 0);
    dword_1800CF518 = 0;
  }
  if ( dword_1800CF51C )
  {
    v28 = GUID_NULL;
    RasIpv6SrvrStop(&v28);
    dword_1800CF51C = 0;
  }
  RasSrvrUninitialize();
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( qword_1800CF548 )
  {
    RegCloseKey(qword_1800CF548);
    qword_1800CF548 = 0;
  }
  if ( qword_1800CF550 )
  {
    RegCloseKey(qword_1800CF550);
    qword_1800CF550 = 0;
  }
  v6 = dword_1800CF568;
  v7 = 0;
  for ( i = (char *)qword_1800CF560; v7 < v6; ++v7 )
  {
    v9 = &i[168 * v7];
    if ( *(_QWORD *)v9 )
    {
      v10 = (void (*)(void))*((_QWORD *)v9 + 14);
      if ( v10 )
        v10();
      FreeLibrary(*(HMODULE *)v9);
      v6 = dword_1800CF568;
      i = (char *)qword_1800CF560;
    }
  }
  if ( i )
    HeapFree(hHeap, 0, i);
  if ( hModule )
    FreeLibrary(hModule);
  if ( gblpRouterPhoneBook )
    HeapFree(hHeap, 0, (LPVOID)gblpRouterPhoneBook);
  if ( gblpszAdminRequest )
    HeapFree(hHeap, 0, gblpszAdminRequest);
  if ( gblpszUserRequest )
    HeapFree(hHeap, 0, gblpszUserRequest);
  if ( gblpszHardwareFailure )
    HeapFree(hHeap, 0, gblpszHardwareFailure);
  if ( gblpszUnknownReason )
    HeapFree(hHeap, 0, gblpszUnknownReason);
  if ( gblpszPm )
    HeapFree(hHeap, 0, gblpszPm);
  if ( gblpszAm )
    HeapFree(hHeap, 0, gblpszAm);
  if ( gblpszIdleDisconnect )
    HeapFree(hHeap, 0, gblpszIdleDisconnect);
  if ( gblpszSessionTimeout )
    HeapFree(hHeap, 0, gblpszSessionTimeout);
  if ( hMem )
  {
    LocalFree(*(HLOCAL *)hMem);
    LocalFree(hMem);
    hMem = 0;
    dword_1800CF62C = 0;
  }
  if ( qword_1800CF640 )
  {
    LocalFree(*(HLOCAL *)qword_1800CF640);
    LocalFree(qword_1800CF640);
    qword_1800CF640 = 0;
    dword_1800CF638 = 0;
  }
  v11 = qword_1800CF678;
  dword_1800CF628 = 0;
  if ( qword_1800CF678 )
  {
    *(_QWORD *)qword_1800CF678 = &DdmThreadPool::`vftable';
    if ( *((_DWORD *)v11 + 24) )
      DdmThreadPool::Uninitialize(v11);
    operator delete(v11);
    qword_1800CF678 = 0;
  }
  if ( dword_1800CF654 )
  {
    DdmDisableServerIpSecFilter();
    RasIpsecTrace("DwUnInitializeIpSec");
    if ( gFwpEngineHandle )
    {
      FwpmEngineClose0(gFwpEngineHandle);
      gFwpEngineHandle = 0;
    }
  }
  else
  {
    *(_QWORD *)&v28.Data1 = &DeviceClose::`vftable';
    Instance = DdmDeviceTable::GetInstance(0x11u);
    DdmDeviceTable::AcceptVisitor(Instance, (struct DdmDeviceVisitor *)&v28, 0, 0);
  }
  if ( DdmNotificationHandler::pInstance )
    (**(void (__fastcall ***)(struct DdmNotificationHandler *, __int64))DdmNotificationHandler::pInstance)(
      DdmNotificationHandler::pInstance,
      1);
  v13 = qword_1800CF670;
  DdmNotificationHandler::pInstance = 0;
  if ( qword_1800CF670 )
  {
    *(_QWORD *)qword_1800CF670 = &DdmThreadPool::`vftable';
    if ( *((_DWORD *)v13 + 24) )
      DdmThreadPool::Uninitialize(v13);
    operator delete(v13);
    qword_1800CF670 = 0;
  }
  if ( DdmConnectionTable::pInstance )
    (**(void (__fastcall ***)(struct DdmConnectionTable *, __int64))DdmConnectionTable::pInstance)(
      DdmConnectionTable::pInstance,
      1);
  v14 = DdmDeviceTable::pInstance;
  DdmConnectionTable::pInstance = 0;
  if ( DdmDeviceTable::pInstance )
  {
    DdmDeviceTable::~DdmDeviceTable(DdmDeviceTable::pInstance);
    operator delete(v14);
  }
  v15 = gblSupervisorEvents;
  DdmDeviceTable::pInstance = 0;
  if ( gblSupervisorEvents )
  {
    v16 = 0;
    v17 = 3 * (v0 + 2);
    if ( v17 )
    {
      v18 = 0;
      do
      {
        v19 = v15[v18];
        if ( v19 )
        {
          if ( v16 >= 2 )
          {
            CloseHandle(v19);
            v15 = gblSupervisorEvents;
          }
          v15[v18] = 0;
        }
        ++v16;
        ++v18;
      }
      while ( v16 < v17 );
    }
  }
  EnterCriticalSection(&gblDeviceTable);
  DeleteCriticalSection(&gblDeviceTable);
  DeleteCriticalSection((LPCRITICAL_SECTION)(&xmmword_1800D07D0 + 1));
  *(_OWORD *)&xmmword_1800D07D0 = 0;
  xmmword_1800D07E0 = 0;
  xmmword_1800D07F0 = 0;
  if ( (dword_1800CF4E0 & 0x80u) != 0 )
  {
    EnterCriticalSection(&stru_1800CF600);
    v20 = (LPVOID *)lpMem;
    if ( lpMem )
    {
      while ( v20 != &lpMem )
      {
        if ( v20[1] != &lpMem || (v21 = (LPVOID *)*v20, *((LPVOID **)*v20 + 1) != v20) )
          __fastfail(3u);
        lpMem = *v20;
        v21[1] = &lpMem;
        CloseHandle(v20[3]);
        HeapFree(hHeap, 0, v20);
        v20 = (LPVOID *)lpMem;
      }
    }
    LeaveCriticalSection(&stru_1800CF600);
    DeleteCriticalSection(&stru_1800CF600);
  }
  DeleteCriticalSection(&stru_1800CF740);
  v22 = *((_QWORD *)&gblMediaTable + 1);
  if ( *((_QWORD *)&gblMediaTable + 1) )
  {
    HeapFree(hHeap, 0, *((LPVOID *)&gblMediaTable + 1));
    *((_QWORD *)&gblMediaTable + 1) = 0;
  }
  if ( hHeap )
    HeapDestroy(hHeap);
  if ( (dword_1800CF4E0 & 0x10) != 0 )
    McGenEventUnregister_EventUnregister(MPRDDM_EVENT_SOURCE_Context);
  if ( dword_1800CF654 )
  {
    if ( (byte_1800CF404 & 0x10) != 0 )
    {
      v23 = -1;
      do
        ++v23;
      while ( aDeinitddmdrive[v23] );
      v29 = L"DeinitDdmDriverHelper";
      v30 = 2 * v23 + 2;
      v31 = 0;
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v22, 2, &v28);
    }
    if ( CompletionPort )
      PostQueuedCompletionStatus(CompletionPort, 0, 0, &Overlapped);
    if ( gblDdmDriverInfo )
      CloseHandle(gblDdmDriverInfo);
    v24 = &gblVpnDeviceTable;
    v25 = 5;
    do
    {
      v26 = *((unsigned int *)v24 + 3);
      if ( (_DWORD)v26 )
      {
        RasLineClose(v26);
        *(_DWORD *)v24 = 0;
      }
      v24 += 39;
      --v25;
    }
    while ( v25 );
    CleanupNdproxyIoControl();
  }
  MprDdmUnRegisterEtw();
  v27 = RegHandle;
  RegHandle = 0;
  dword_1800CE720 = 0;
  EventUnregister(v27);
  stru_1800CF740.SpinCount = 0;
  *(_OWORD *)&gblDeviceTable.DebugInfo = 0;
  *(_OWORD *)&gblDeviceTable.OwningThread = 0;
  *(_OWORD *)&gblDeviceTable.SpinCount = 0;
  gblMediaTable = 0;
  *(_OWORD *)&stru_1800CF740.DebugInfo = 0;
  *(_OWORD *)&stru_1800CF740.OwningThread = 0;
  memset_0(&gblEventHandlerTable, 0, 0x60u);
  gblSupervisorEvents = 0;
  gblphEventDDMServiceState = 0;
  gblpRouterPhoneBook = 0;
  gblpszAdminRequest = 0;
  gblpszUserRequest = 0;
  gblpszHardwareFailure = 0;
  gblpszUnknownReason = 0;
  gblpszPm = 0;
  gblpszAm = 0;
  gblpszIdleDisconnect = 0;
  gblpszSessionTimeout = 0;
}

```

## disassembly

```asm
0x1800205b0  mov     rax, rsp
0x1800205b3  mov     [rax+8], rbx
0x1800205b7  mov     [rax+10h], rbp
0x1800205bb  mov     [rax+18h], rsi
0x1800205bf  push    rdi
0x1800205c0  sub     rsp, 70h
0x1800205c4  movaps  xmmword ptr [rax-18h], xmm6
0x1800205c8  mov     rax, cs:__security_cookie
0x1800205cf  xor     rax, rsp
0x1800205d2  mov     [rsp+78h+var_28], rax
0x1800205d7  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x1800205de  mov     ecx, 11h; unsigned int
0x1800205e3  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x1800205e8  mov     rcx, cs:hLibModule; hLibModule
0x1800205ef  xor     ebp, ebp
0x1800205f1  mov     esi, [rax]
0x1800205f3  test    rcx, rcx
0x1800205f6  jz      short loc_180020619
0x1800205f8  call    cs:__imp_FreeLibrary
0x1800205ff  nop     dword ptr [rax+rax+00h]
0x180020604  mov     cs:hLibModule, rbp
0x18002060b  mov     cs:qword_1800CF528, rbp
0x180020612  mov     cs:qword_1800CF530, rbp
0x180020619  lea     rbx, byte_1800CE498
0x180020620  mov     edi, 3
0x180020625  cmp     [rbx], ebp
0x180020627  jnz     short loc_180020654
0x180020629  cmp     [rbx+4], ebp
0x18002062c  jz      short loc_180020654
0x18002062e  mov     rax, [rbx+28h]
0x180020632  test    rax, rax
0x180020635  jz      short loc_18002063C
0x180020637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002063c  cmp     cs:dword_1800CF654, ebp
0x180020642  jz      short loc_180020654
0x180020644  mov     rax, [rbx+18h]
0x180020648  test    rax, rax
0x18002064b  jz      short loc_180020654
0x18002064d  xor     ecx, ecx
0x18002064f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020654  mov     rcx, [rbx+8]; hLibModule
0x180020658  test    rcx, rcx
0x18002065b  jz      short loc_180020684
0x18002065d  call    cs:__imp_FreeLibrary
0x180020664  nop     dword ptr [rax+rax+00h]
0x180020669  mov     [rbx], rbp
0x18002066c  mov     [rbx+8], rbp
0x180020670  mov     [rbx+10h], rbp
0x180020674  mov     [rbx+18h], rbp
0x180020678  mov     [rbx+20h], rbp
0x18002067c  mov     [rbx+28h], rbp
0x180020680  mov     [rbx+30h], rbp
0x180020684  add     rbx, 50h ; 'P'
0x180020688  sub     rdi, 1
0x18002068c  jnz     short loc_180020625
0x18002068e  cmp     cs:dword_1800CF668, ebp
0x180020694  jz      short loc_1800206A2
0x180020696  call    cs:__imp_EapHostPeerUninitialize
0x18002069d  nop     dword ptr [rax+rax+00h]
0x1800206a2  test    byte ptr cs:dword_1800CF4E0, 20h
0x1800206a9  jz      short loc_1800206B0
0x1800206ab  call    RasInterfaceMgmtUninit
0x1800206b0  cmp     cs:dword_1800CF518, ebp
0x1800206b6  jz      short loc_1800206D3
0x1800206b8  xor     r8d, r8d
0x1800206bb  movdqa  xmmword ptr [rsp+78h+var_48.Data1], xmm6
0x1800206c1  xor     edx, edx
0x1800206c3  lea     rcx, [rsp+78h+var_48]
0x1800206c8  call    RasSrvrStop
0x1800206cd  mov     cs:dword_1800CF518, ebp
0x1800206d3  cmp     cs:dword_1800CF51C, ebp
0x1800206d9  jz      short loc_1800206F6
0x1800206db  xor     r8d, r8d
0x1800206de  movdqa  xmmword ptr [rsp+78h+var_48.Data1], xmm6
0x1800206e4  xor     edx, edx
0x1800206e6  lea     rcx, [rsp+78h+var_48]; struct _GUID *
0x1800206eb  call    RasIpv6SrvrStop
0x1800206f0  mov     cs:dword_1800CF51C, ebp
0x1800206f6  call    RasSrvrUninitialize
0x1800206fb  mov     rcx, cs:hKey; hKey
0x180020702  test    rcx, rcx
0x180020705  jz      short loc_18002071A
0x180020707  call    cs:__imp_RegCloseKey
0x18002070e  nop     dword ptr [rax+rax+00h]
0x180020713  mov     cs:hKey, rbp
0x18002071a  mov     rcx, cs:qword_1800CF548; hKey
0x180020721  test    rcx, rcx
0x180020724  jz      short loc_180020739
0x180020726  call    cs:__imp_RegCloseKey
0x18002072d  nop     dword ptr [rax+rax+00h]
0x180020732  mov     cs:qword_1800CF548, rbp
0x180020739  mov     rcx, cs:qword_1800CF550; hKey
0x180020740  test    rcx, rcx
0x180020743  jz      short loc_180020758
0x180020745  call    cs:__imp_RegCloseKey
0x18002074c  nop     dword ptr [rax+rax+00h]
0x180020751  mov     cs:qword_1800CF550, rbp
0x180020758  mov     ecx, cs:dword_1800CF568
0x18002075e  mov     edi, ebp
0x180020760  mov     r8, cs:qword_1800CF560
0x180020767  test    ecx, ecx
0x180020769  jz      short loc_1800207AC
0x18002076b  mov     eax, edi
0x18002076d  imul    rbx, rax, 0A8h
0x180020774  add     rbx, r8
0x180020777  cmp     [rbx], rbp
0x18002077a  jz      short loc_1800207A6
0x18002077c  mov     rax, [rbx+70h]
0x180020780  test    rax, rax
0x180020783  jz      short loc_18002078A
0x180020785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002078a  mov     rcx, [rbx]; hLibModule
0x18002078d  call    cs:__imp_FreeLibrary
0x180020794  nop     dword ptr [rax+rax+00h]
0x180020799  mov     ecx, cs:dword_1800CF568
0x18002079f  mov     r8, cs:qword_1800CF560; lpMem
0x1800207a6  inc     edi
0x1800207a8  cmp     edi, ecx
0x1800207aa  jb      short loc_18002076B
0x1800207ac  test    r8, r8
0x1800207af  jz      short loc_1800207C6
0x1800207b1  mov     rcx, cs:hHeap; hHeap
0x1800207b8  xor     edx, edx; dwFlags
0x1800207ba  call    cs:__imp_HeapFree
0x1800207c1  nop     dword ptr [rax+rax+00h]
0x1800207c6  mov     rcx, cs:hModule; hLibModule
0x1800207cd  test    rcx, rcx
0x1800207d0  jz      short loc_1800207DE
0x1800207d2  call    cs:__imp_FreeLibrary
0x1800207d9  nop     dword ptr [rax+rax+00h]
0x1800207de  mov     r8, cs:gblpRouterPhoneBook; lpMem
0x1800207e5  test    r8, r8
0x1800207e8  jz      short loc_1800207FF
0x1800207ea  mov     rcx, cs:hHeap; hHeap
0x1800207f1  xor     edx, edx; dwFlags
0x1800207f3  call    cs:__imp_HeapFree
0x1800207fa  nop     dword ptr [rax+rax+00h]
0x1800207ff  mov     r8, cs:gblpszAdminRequest; lpMem
0x180020806  test    r8, r8
0x180020809  jz      short loc_180020820
0x18002080b  mov     rcx, cs:hHeap; hHeap
0x180020812  xor     edx, edx; dwFlags
0x180020814  call    cs:__imp_HeapFree
0x18002081b  nop     dword ptr [rax+rax+00h]
0x180020820  mov     r8, cs:gblpszUserRequest; lpMem
0x180020827  test    r8, r8
0x18002082a  jz      short loc_180020841
0x18002082c  mov     rcx, cs:hHeap; hHeap
0x180020833  xor     edx, edx; dwFlags
0x180020835  call    cs:__imp_HeapFree
0x18002083c  nop     dword ptr [rax+rax+00h]
0x180020841  mov     r8, cs:gblpszHardwareFailure; lpMem
0x180020848  test    r8, r8
0x18002084b  jz      short loc_180020862
0x18002084d  mov     rcx, cs:hHeap; hHeap
0x180020854  xor     edx, edx; dwFlags
0x180020856  call    cs:__imp_HeapFree
0x18002085d  nop     dword ptr [rax+rax+00h]
0x180020862  mov     r8, cs:gblpszUnknownReason; lpMem
0x180020869  test    r8, r8
0x18002086c  jz      short loc_180020883
0x18002086e  mov     rcx, cs:hHeap; hHeap
0x180020875  xor     edx, edx; dwFlags
0x180020877  call    cs:__imp_HeapFree
0x18002087e  nop     dword ptr [rax+rax+00h]
0x180020883  mov     r8, cs:gblpszPm; lpMem
0x18002088a  test    r8, r8
0x18002088d  jz      short loc_1800208A4
0x18002088f  mov     rcx, cs:hHeap; hHeap
0x180020896  xor     edx, edx; dwFlags
0x180020898  call    cs:__imp_HeapFree
0x18002089f  nop     dword ptr [rax+rax+00h]
0x1800208a4  mov     r8, cs:gblpszAm; lpMem
0x1800208ab  test    r8, r8
0x1800208ae  jz      short loc_1800208C5
0x1800208b0  mov     rcx, cs:hHeap; hHeap
0x1800208b7  xor     edx, edx; dwFlags
0x1800208b9  call    cs:__imp_HeapFree
0x1800208c0  nop     dword ptr [rax+rax+00h]
0x1800208c5  mov     r8, cs:gblpszIdleDisconnect; lpMem
0x1800208cc  test    r8, r8
0x1800208cf  jz      short loc_1800208E6
0x1800208d1  mov     rcx, cs:hHeap; hHeap
0x1800208d8  xor     edx, edx; dwFlags
0x1800208da  call    cs:__imp_HeapFree
0x1800208e1  nop     dword ptr [rax+rax+00h]
0x1800208e6  mov     r8, cs:gblpszSessionTimeout; lpMem
0x1800208ed  test    r8, r8
0x1800208f0  jz      short loc_180020907
0x1800208f2  mov     rcx, cs:hHeap; hHeap
0x1800208f9  xor     edx, edx; dwFlags
0x1800208fb  call    cs:__imp_HeapFree
0x180020902  nop     dword ptr [rax+rax+00h]
0x180020907  mov     rcx, cs:hMem
0x18002090e  test    rcx, rcx
0x180020911  jz      short loc_180020942
0x180020913  mov     rcx, [rcx]; hMem
0x180020916  call    cs:__imp_LocalFree
0x18002091d  nop     dword ptr [rax+rax+00h]
0x180020922  mov     rcx, cs:hMem; hMem
0x180020929  call    cs:__imp_LocalFree
0x180020930  nop     dword ptr [rax+rax+00h]
0x180020935  mov     cs:hMem, rbp
0x18002093c  mov     cs:dword_1800CF62C, ebp
0x180020942  mov     rcx, cs:qword_1800CF640
0x180020949  test    rcx, rcx
0x18002094c  jz      short loc_18002097D
0x18002094e  mov     rcx, [rcx]; hMem
0x180020951  call    cs:__imp_LocalFree
0x180020958  nop     dword ptr [rax+rax+00h]
0x18002095d  mov     rcx, cs:qword_1800CF640; hMem
0x180020964  call    cs:__imp_LocalFree
0x18002096b  nop     dword ptr [rax+rax+00h]
0x180020970  mov     cs:qword_1800CF640, rbp
0x180020977  mov     cs:dword_1800CF638, ebp
0x18002097d  mov     rbx, cs:qword_1800CF678
0x180020984  lea     rdi, ??_7DdmThreadPool@@6B@; const DdmThreadPool::`vftable'
0x18002098b  mov     cs:dword_1800CF628, ebp
0x180020991  test    rbx, rbx
0x180020994  jz      short loc_1800209BC
0x180020996  mov     [rbx], rdi
0x180020999  cmp     [rbx+60h], ebp
0x18002099c  jz      short loc_1800209A6
0x18002099e  mov     rcx, rbx; this
0x1800209a1  call    ?Uninitialize@DdmThreadPool@@UEAAKXZ; DdmThreadPool::Uninitialize(void)
0x1800209a6  mov     rcx, rbx
0x1800209a9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800209b0  nop     dword ptr [rax+rax+00h]
0x1800209b5  mov     cs:qword_1800CF678, rbp
0x1800209bc  cmp     cs:dword_1800CF654, ebp
0x1800209c2  jnz     short loc_1800209EF
0x1800209c4  lea     rax, ??_7DeviceClose@@6B@; const DeviceClose::`vftable'
0x1800209cb  mov     ecx, 11h; unsigned int
0x1800209d0  mov     qword ptr [rsp+78h+var_48.Data1], rax
0x1800209d5  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x1800209da  xor     r9d, r9d; void *
0x1800209dd  lea     rdx, [rsp+78h+var_48]; struct DdmDeviceVisitor *
0x1800209e2  xor     r8d, r8d; int
0x1800209e5  mov     rcx, rax; this
0x1800209e8  call    ?AcceptVisitor@DdmDeviceTable@@QEAAKAEAVDdmDeviceVisitor@@HPEAX@Z; DdmDeviceTable::AcceptVisitor(DdmDeviceVisitor &,int,void *)
0x1800209ed  jmp     short loc_180020A1F
0x1800209ef  call    ?DdmDisableServerIpSecFilter@@YAKXZ; DdmDisableServerIpSecFilter(void)
0x1800209f4  lea     rcx, aDwuninitialize; "DwUnInitializeIpSec"
0x1800209fb  call    RasIpsecTrace
0x180020a00  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x180020a07  test    rcx, rcx
0x180020a0a  jz      short loc_180020A1F
0x180020a0c  call    cs:__imp_FwpmEngineClose0
0x180020a13  nop     dword ptr [rax+rax+00h]
0x180020a18  mov     cs:gFwpEngineHandle, rbp
0x180020a1f  mov     rcx, cs:?pInstance@DdmNotificationHandler@@0PEAV1@EA; DdmNotificationHandler * DdmNotificationHandler::pInstance
0x180020a26  test    rcx, rcx
0x180020a29  jz      short loc_180020A3B
0x180020a2b  mov     rax, [rcx]
0x180020a2e  mov     edx, 1
0x180020a33  mov     rax, [rax]
0x180020a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a3b  mov     rbx, cs:qword_1800CF670
0x180020a42  mov     cs:?pInstance@DdmNotificationHandler@@0PEAV1@EA, rbp; DdmNotificationHandler * DdmNotificationHandler::pInstance
0x180020a49  test    rbx, rbx
0x180020a4c  jz      short loc_180020A74
0x180020a4e  mov     [rbx], rdi
0x180020a51  cmp     [rbx+60h], ebp
0x180020a54  jz      short loc_180020A5E
0x180020a56  mov     rcx, rbx; this
0x180020a59  call    ?Uninitialize@DdmThreadPool@@UEAAKXZ; DdmThreadPool::Uninitialize(void)
0x180020a5e  mov     rcx, rbx
0x180020a61  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020a68  nop     dword ptr [rax+rax+00h]
0x180020a6d  mov     cs:qword_1800CF670, rbp
0x180020a74  mov     rcx, cs:?pInstance@DdmConnectionTable@@0PEAV1@EA; DdmConnectionTable * DdmConnectionTable::pInstance
0x180020a7b  test    rcx, rcx
0x180020a7e  jz      short loc_180020A90
0x180020a80  mov     rax, [rcx]
0x180020a83  mov     edx, 1
0x180020a88  mov     rax, [rax]
0x180020a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a90  mov     rbx, cs:?pInstance@DdmDeviceTable@@0PEAV1@EA; DdmDeviceTable * DdmDeviceTable::pInstance
0x180020a97  mov     cs:?pInstance@DdmConnectionTable@@0PEAV1@EA, rbp; DdmConnectionTable * DdmConnectionTable::pInstance
0x180020a9e  test    rbx, rbx
0x180020aa1  jz      short loc_180020ABA
0x180020aa3  mov     rcx, rbx; this
0x180020aa6  call    ??1DdmDeviceTable@@QEAA@XZ; DdmDeviceTable::~DdmDeviceTable(void)
0x180020aab  mov     rcx, rbx
0x180020aae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180020ab5  nop     dword ptr [rax+rax+00h]
0x180020aba  mov     rdx, cs:gblSupervisorEvents
0x180020ac1  mov     cs:?pInstance@DdmDeviceTable@@0PEAV1@EA, rbp; DdmDeviceTable * DdmDeviceTable::pInstance
0x180020ac8  test    rdx, rdx
0x180020acb  jz      short loc_180020B11
0x180020acd  lea     eax, [rsi+2]
0x180020ad0  mov     edi, ebp
0x180020ad2  lea     esi, [rax+rax*2]
0x180020ad5  test    esi, esi
0x180020ad7  jz      short loc_180020B11
0x180020ad9  mov     rbx, rbp
0x180020adc  mov     rcx, [rbx+rdx]; hObject
0x180020ae0  test    rcx, rcx
0x180020ae3  jz      short loc_180020B07
0x180020ae5  mov     eax, edi
  ... truncated ...
```
