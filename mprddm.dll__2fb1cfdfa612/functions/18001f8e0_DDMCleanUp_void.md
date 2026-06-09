# DDMCleanUp(void)

- ea: `0x18001f8e0`
- end: `0x18002008f`
- name: `?DDMCleanUp@@YAXXZ`
- size: `1967`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800085b0`
- `0x18001b570`

## callees

- `0x180007b7c`
- `0x180014a90`
- `0x18001f8e0`
- `0x180025dfc`
- `0x180028908`
- `0x18003a6d4`
- `0x18003a9dc`
- `0x18003b8f4`
- `0x1800489b0`
- `0x180051368`
- `0x180056f10`
- `0x180057498`
- `0x18007d1f8`
- `0x1800803a8`
- `0x180083c10`
- `0x180085a48`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001fc9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd48`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fc9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd48`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd8f`
- `KERNEL32!LocalFree` at `0x18001fc1b`
- `KERNEL32!LocalFree` at `0x18001fc28`
- `KERNEL32!LocalFree` at `0x18001fc4b`
- `KERNEL32!LocalFree` at `0x18001fc58`
- `KERNEL32!LocalFree` at `0x18001fc1b`
- `KERNEL32!LocalFree` at `0x18001fc28`
- `KERNEL32!LocalFree` at `0x18001fc4b`
- `KERNEL32!LocalFree` at `0x18001fc58`
- `KERNEL32!DeleteCriticalSection` at `0x18001fdf6`
- `KERNEL32!DeleteCriticalSection` at `0x18001fe03`
- `KERNEL32!DeleteCriticalSection` at `0x18001fea8`
- `KERNEL32!DeleteCriticalSection` at `0x18001feb5`
- `KERNEL32!DeleteCriticalSection` at `0x18001fdf6`
- `KERNEL32!DeleteCriticalSection` at `0x18001fe03`
- `KERNEL32!DeleteCriticalSection` at `0x18001fea8`
- `KERNEL32!DeleteCriticalSection` at `0x18001feb5`
- `KERNEL32!FreeLibrary` at `0x18001f923`
- `KERNEL32!FreeLibrary` at `0x18001f99b`
- `KERNEL32!FreeLibrary` at `0x18001fad7`
- `KERNEL32!FreeLibrary` at `0x18001fb13`
- `KERNEL32!FreeLibrary` at `0x18001f923`
- `KERNEL32!FreeLibrary` at `0x18001f99b`
- `KERNEL32!FreeLibrary` at `0x18001fad7`
- `KERNEL32!FreeLibrary` at `0x18001fb13`
- `KERNEL32!HeapDestroy` at `0x18001fee9`
- `KERNEL32!HeapDestroy` at `0x18001fee9`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18001ff6f`
- `KERNEL32!PostQueuedCompletionStatus` at `0x18001ff6f`
- `KERNEL32!CloseHandle` at `0x18001fdcb`
- `KERNEL32!CloseHandle` at `0x18001fe74`
- `KERNEL32!CloseHandle` at `0x18001ff81`
- `KERNEL32!CloseHandle` at `0x18001fdcb`
- `KERNEL32!CloseHandle` at `0x18001fe74`
- `KERNEL32!CloseHandle` at `0x18001ff81`
- `KERNEL32!LeaveCriticalSection` at `0x18001fe9f`
- `KERNEL32!LeaveCriticalSection` at `0x18001fe9f`
- `KERNEL32!EnterCriticalSection` at `0x18001fde9`
- `KERNEL32!EnterCriticalSection` at `0x18001fe38`
- `KERNEL32!EnterCriticalSection` at `0x18001fde9`
- `KERNEL32!EnterCriticalSection` at `0x18001fe38`
- `KERNEL32!HeapFree` at `0x18001fb01`
- `KERNEL32!HeapFree` at `0x18001fb2e`
- `KERNEL32!HeapFree` at `0x18001fb49`
- `KERNEL32!HeapFree` at `0x18001fb64`
- `KERNEL32!HeapFree` at `0x18001fb7f`
- `KERNEL32!HeapFree` at `0x18001fb9a`
- `KERNEL32!HeapFree` at `0x18001fbb5`
- `KERNEL32!HeapFree` at `0x18001fbd0`
- `KERNEL32!HeapFree` at `0x18001fbeb`
- `KERNEL32!HeapFree` at `0x18001fc06`
- `KERNEL32!HeapFree` at `0x18001fe86`
- `KERNEL32!HeapFree` at `0x18001fed0`
- `KERNEL32!HeapFree` at `0x18001fb01`
- `KERNEL32!HeapFree` at `0x18001fb2e`
- `KERNEL32!HeapFree` at `0x18001fb49`
- `KERNEL32!HeapFree` at `0x18001fb64`
- `KERNEL32!HeapFree` at `0x18001fb7f`
- `KERNEL32!HeapFree` at `0x18001fb9a`
- `KERNEL32!HeapFree` at `0x18001fbb5`
- `KERNEL32!HeapFree` at `0x18001fbd0`
- `KERNEL32!HeapFree` at `0x18001fbeb`
- `KERNEL32!HeapFree` at `0x18001fc06`
- `KERNEL32!HeapFree` at `0x18001fe86`
- `KERNEL32!HeapFree` at `0x18001fed0`
- `ADVAPI32!EventUnregister` at `0x18001ffd2`
- `ADVAPI32!EventUnregister` at `0x18001ffd2`
- `ADVAPI32!RegCloseKey` at `0x18001fa62`
- `ADVAPI32!RegCloseKey` at `0x18001fa7b`
- `ADVAPI32!RegCloseKey` at `0x18001fa94`
- `ADVAPI32!RegCloseKey` at `0x18001fa62`
- `ADVAPI32!RegCloseKey` at `0x18001fa7b`
- `ADVAPI32!RegCloseKey` at `0x18001fa94`
- `eappprxy!EapHostPeerUninitialize` at `0x18001f9f3`
- `eappprxy!EapHostPeerUninitialize` at `0x18001f9f3`
- `fwpuclnt!FwpmEngineClose0` at `0x18001fcf8`
- `fwpuclnt!FwpmEngineClose0` at `0x18001fcf8`

## pseudocode

```c
void DDMCleanUp(void)
{
  int v0; // ebp
  __int64 v1; // rdi
  unsigned __int64 v2; // rbx
  void (*v3)(void); // rax
  void (__fastcall *v4)(_QWORD); // rax
  HMODULE v5; // rcx
  unsigned int v6; // ecx
  unsigned int v7; // edi
  char *i; // rbx
  __int64 v9; // rsi
  void (*v10)(void); // rax
  DdmThreadPool *v11; // rbx
  DdmDeviceTable *Instance; // rax
  DdmThreadPool *v13; // rbx
  DdmDeviceTable *v14; // rbx
  HANDLE *v15; // rdx
  unsigned int v16; // ebx
  unsigned int v17; // esi
  HANDLE v18; // rcx
  LPVOID *v19; // rbx
  LPVOID *v20; // rax
  __int64 v21; // r8
  __int64 j; // rbx
  REGHANDLE v23; // rcx
  struct _GUID v24; // [rsp+30h] [rbp-78h] BYREF
  const wchar_t *v25; // [rsp+40h] [rbp-68h]
  __int64 v26; // [rsp+48h] [rbp-60h]

  v0 = *(_DWORD *)DdmDeviceTable::GetInstance(0x11u);
  if ( hLibModule )
  {
    FreeLibrary(hLibModule);
    hLibModule = 0;
    qword_1800C8528 = 0;
    qword_1800C8530 = 0;
  }
  v1 = 0;
  v2 = 0;
  do
  {
    if ( !*(_DWORD *)&byte_1800C7498[v2] && dword_1800C749C[v2 / 4] )
    {
      v3 = (void (*)(void))qword_1800C74A0[v2 / 8 + 4];
      if ( v3 )
        v3();
      if ( dword_1800C8654 )
      {
        v4 = (void (__fastcall *)(_QWORD))qword_1800C74A0[v2 / 8 + 2];
        if ( v4 )
          v4(0);
      }
    }
    v5 = (HMODULE)qword_1800C74A0[v2 / 8];
    if ( v5 )
    {
      FreeLibrary(v5);
      *(_QWORD *)&byte_1800C7498[v2] = 0;
      qword_1800C74A0[v2 / 8] = 0;
      qword_1800C74A0[v2 / 8 + 1] = 0;
      qword_1800C74A0[v2 / 8 + 2] = 0;
      qword_1800C74A0[v2 / 8 + 3] = 0;
      qword_1800C74A0[v2 / 8 + 4] = 0;
      qword_1800C74C8[v2 / 8] = 0;
    }
    ++v1;
    v2 += 80LL;
  }
  while ( v1 != 3 );
  if ( dword_1800C8668 )
    EapHostPeerUninitialize();
  if ( (dword_1800C84E0 & 0x20) != 0 )
    RasInterfaceMgmtUninit();
  if ( dword_1800C8518 )
  {
    v24 = GUID_NULL;
    RasSrvrStop(&v24, 0, 0);
    dword_1800C8518 = 0;
  }
  if ( dword_1800C851C )
  {
    v24 = GUID_NULL;
    RasIpv6SrvrStop(&v24);
    dword_1800C851C = 0;
  }
  RasSrvrUninitialize();
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( qword_1800C8548 )
  {
    RegCloseKey(qword_1800C8548);
    qword_1800C8548 = 0;
  }
  if ( qword_1800C8550 )
  {
    RegCloseKey(qword_1800C8550);
    qword_1800C8550 = 0;
  }
  v6 = dword_1800C8568;
  v7 = 0;
  for ( i = (char *)qword_1800C8560; v7 < v6; ++v7 )
  {
    v9 = 168LL * v7;
    if ( *(_QWORD *)&i[v9] )
    {
      v10 = *(void (**)(void))&i[v9 + 112];
      if ( v10 )
        v10();
      FreeLibrary(*(HMODULE *)&i[v9]);
      v6 = dword_1800C8568;
      i = (char *)qword_1800C8560;
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
    dword_1800C862C = 0;
  }
  if ( qword_1800C8640 )
  {
    LocalFree(*(HLOCAL *)qword_1800C8640);
    LocalFree(qword_1800C8640);
    qword_1800C8640 = 0;
    dword_1800C8638 = 0;
  }
  v11 = qword_1800C8678;
  dword_1800C8628 = 0;
  if ( qword_1800C8678 )
  {
    *(_QWORD *)qword_1800C8678 = &DdmThreadPool::`vftable';
    if ( *((_DWORD *)v11 + 24) )
      DdmThreadPool::Uninitialize(v11);
    operator delete(v11);
    qword_1800C8678 = 0;
  }
  if ( dword_1800C8654 )
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
    *(_QWORD *)&v24.Data1 = &DeviceClose::`vftable';
    Instance = DdmDeviceTable::GetInstance(0x11u);
    DdmDeviceTable::AcceptVisitor(Instance, (struct DdmDeviceVisitor *)&v24, 0, 0);
  }
  if ( DdmNotificationHandler::pInstance )
    (**(void (__fastcall ***)(struct DdmNotificationHandler *, __int64))DdmNotificationHandler::pInstance)(
      DdmNotificationHandler::pInstance,
      1);
  v13 = qword_1800C8670;
  DdmNotificationHandler::pInstance = 0;
  if ( qword_1800C8670 )
  {
    *(_QWORD *)qword_1800C8670 = &DdmThreadPool::`vftable';
    if ( *((_DWORD *)v13 + 24) )
      DdmThreadPool::Uninitialize(v13);
    operator delete(v13);
    qword_1800C8670 = 0;
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
      do
      {
        v18 = v15[v16];
        if ( v18 )
        {
          if ( v16 >= 2 )
          {
            CloseHandle(v18);
            v15 = gblSupervisorEvents;
          }
          v15[v16] = 0;
        }
        ++v16;
      }
      while ( v16 < v17 );
    }
  }
  EnterCriticalSection(&gblDeviceTable);
  DeleteCriticalSection(&gblDeviceTable);
  DeleteCriticalSection((LPCRITICAL_SECTION)(&xmmword_1800C97D0 + 1));
  *(_OWORD *)&xmmword_1800C97D0 = 0;
  xmmword_1800C97E0 = 0;
  xmmword_1800C97F0 = 0;
  if ( (dword_1800C84E0 & 0x80u) != 0 )
  {
    EnterCriticalSection(&CriticalSection);
    v19 = (LPVOID *)lpMem;
    if ( lpMem )
    {
      while ( v19 != &lpMem )
      {
        if ( v19[1] != &lpMem || (v20 = (LPVOID *)*v19, *((LPVOID **)*v19 + 1) != v19) )
          __fastfail(3u);
        lpMem = *v19;
        v20[1] = &lpMem;
        CloseHandle(v19[3]);
        HeapFree(hHeap, 0, v19);
        v19 = (LPVOID *)lpMem;
      }
    }
    LeaveCriticalSection(&CriticalSection);
    DeleteCriticalSection(&CriticalSection);
  }
  DeleteCriticalSection(&stru_1800C8740);
  v21 = *((_QWORD *)&gblMediaTable + 1);
  if ( *((_QWORD *)&gblMediaTable + 1) )
  {
    HeapFree(hHeap, 0, *((LPVOID *)&gblMediaTable + 1));
    *((_QWORD *)&gblMediaTable + 1) = 0;
  }
  if ( hHeap )
    HeapDestroy(hHeap);
  if ( (dword_1800C84E0 & 0x10) != 0 )
    McGenEventUnregister_EventUnregister(MPRDDM_EVENT_SOURCE_Context);
  if ( dword_1800C8654 )
  {
    LOBYTE(v24.Data1) = byte_1800C8404 & 0x10;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v26 = 44;
      v25 = L"DeinitDdmDriverHelper";
      McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v21, 2, &v24);
    }
    if ( CompletionPort )
      PostQueuedCompletionStatus(CompletionPort, 0, 0, &Overlapped);
    if ( gblDdmDriverInfo )
      CloseHandle(gblDdmDriverInfo);
    for ( j = 0; j != 5; ++j )
    {
      if ( *(&dword_1800C8FFC + 78 * j) )
      {
        RasLineClose();
        *((_DWORD *)&gblVpnDeviceTable + 78 * j) = 0;
      }
    }
    CleanupNdproxyIoControl();
  }
  MprDdmUnRegisterEtw();
  v23 = RegHandle;
  dword_1800C7720 = 0;
  RegHandle = 0;
  EventUnregister(v23);
  stru_1800C8740.SpinCount = 0;
  *(_OWORD *)&gblDeviceTable.DebugInfo = 0;
  *(_OWORD *)&gblDeviceTable.OwningThread = 0;
  *(_OWORD *)&gblDeviceTable.SpinCount = 0;
  gblMediaTable = 0;
  *(_OWORD *)&stru_1800C8740.DebugInfo = 0;
  *(_OWORD *)&stru_1800C8740.OwningThread = 0;
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
0x18001f8e0  push    rbx
0x18001f8e2  push    rbp
0x18001f8e3  push    rsi
0x18001f8e4  push    rdi
0x18001f8e5  push    r14
0x18001f8e7  push    r15
0x18001f8e9  sub     rsp, 78h
0x18001f8ed  movaps  [rsp+0A8h+var_48], xmm6
0x18001f8f2  mov     rax, cs:__security_cookie
0x18001f8f9  xor     rax, rsp
0x18001f8fc  mov     [rsp+0A8h+var_58], rax
0x18001f901  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18001f908  mov     ecx, 11h; unsigned int
0x18001f90d  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001f912  mov     rcx, cs:hLibModule; hLibModule
0x18001f919  xor     r14d, r14d
0x18001f91c  mov     ebp, [rax]
0x18001f91e  test    rcx, rcx
0x18001f921  jz      short loc_18001F93E
0x18001f923  call    cs:__imp_FreeLibrary
0x18001f929  mov     cs:hLibModule, r14
0x18001f930  mov     cs:qword_1800C8528, r14
0x18001f937  mov     cs:qword_1800C8530, r14
0x18001f93e  mov     rdi, r14
0x18001f941  lea     r15, cs:180000000h
0x18001f948  mov     rbx, r14
0x18001f94b  cmp     [rbx+r15+0C7498h], r14d
0x18001f953  jnz     short loc_18001F98E
0x18001f955  cmp     [rbx+r15+0C749Ch], r14d
0x18001f95d  jz      short loc_18001F98E
0x18001f95f  mov     rax, [rbx+r15+0C74C0h]
0x18001f967  test    rax, rax
0x18001f96a  jz      short loc_18001F971
0x18001f96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f971  cmp     cs:dword_1800C8654, r14d
0x18001f978  jz      short loc_18001F98E
0x18001f97a  mov     rax, [rbx+r15+0C74B0h]
0x18001f982  test    rax, rax
0x18001f985  jz      short loc_18001F98E
0x18001f987  xor     ecx, ecx
0x18001f989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f98e  mov     rcx, [rbx+r15+0C74A0h]; hLibModule
0x18001f996  test    rcx, rcx
0x18001f999  jz      short loc_18001F9D9
0x18001f99b  call    cs:__imp_FreeLibrary
0x18001f9a1  mov     [rbx+r15+0C7498h], r14
0x18001f9a9  mov     [rbx+r15+0C74A0h], r14
0x18001f9b1  mov     [rbx+r15+0C74A8h], r14
0x18001f9b9  mov     [rbx+r15+0C74B0h], r14
0x18001f9c1  mov     [rbx+r15+0C74B8h], r14
0x18001f9c9  mov     [rbx+r15+0C74C0h], r14
0x18001f9d1  mov     [rbx+r15+0C74C8h], r14
0x18001f9d9  inc     rdi
0x18001f9dc  add     rbx, 50h ; 'P'
0x18001f9e0  cmp     rdi, 3
0x18001f9e4  jnz     loc_18001F94B
0x18001f9ea  cmp     cs:dword_1800C8668, r14d
0x18001f9f1  jz      short loc_18001F9F9
0x18001f9f3  call    cs:__imp_EapHostPeerUninitialize
0x18001f9f9  test    byte ptr cs:dword_1800C84E0, 20h
0x18001fa00  jz      short loc_18001FA07
0x18001fa02  call    RasInterfaceMgmtUninit
0x18001fa07  cmp     cs:dword_1800C8518, r14d
0x18001fa0e  jz      short loc_18001FA2C
0x18001fa10  xor     r8d, r8d
0x18001fa13  movdqa  xmmword ptr [rsp+0A8h+var_78.Data1], xmm6
0x18001fa19  xor     edx, edx
0x18001fa1b  lea     rcx, [rsp+0A8h+var_78]
0x18001fa20  call    RasSrvrStop
0x18001fa25  mov     cs:dword_1800C8518, r14d
0x18001fa2c  cmp     cs:dword_1800C851C, r14d
0x18001fa33  jz      short loc_18001FA51
0x18001fa35  xor     r8d, r8d
0x18001fa38  movdqa  xmmword ptr [rsp+0A8h+var_78.Data1], xmm6
0x18001fa3e  xor     edx, edx
0x18001fa40  lea     rcx, [rsp+0A8h+var_78]; struct _GUID *
0x18001fa45  call    RasIpv6SrvrStop
0x18001fa4a  mov     cs:dword_1800C851C, r14d
0x18001fa51  call    RasSrvrUninitialize
0x18001fa56  mov     rcx, cs:hKey; hKey
0x18001fa5d  test    rcx, rcx
0x18001fa60  jz      short loc_18001FA6F
0x18001fa62  call    cs:__imp_RegCloseKey
0x18001fa68  mov     cs:hKey, r14
0x18001fa6f  mov     rcx, cs:qword_1800C8548; hKey
0x18001fa76  test    rcx, rcx
0x18001fa79  jz      short loc_18001FA88
0x18001fa7b  call    cs:__imp_RegCloseKey
0x18001fa81  mov     cs:qword_1800C8548, r14
0x18001fa88  mov     rcx, cs:qword_1800C8550; hKey
0x18001fa8f  test    rcx, rcx
0x18001fa92  jz      short loc_18001FAA1
0x18001fa94  call    cs:__imp_RegCloseKey
0x18001fa9a  mov     cs:qword_1800C8550, r14
0x18001faa1  mov     ecx, cs:dword_1800C8568
0x18001faa7  mov     edi, r14d
0x18001faaa  mov     rbx, cs:qword_1800C8560
0x18001fab1  test    ecx, ecx
0x18001fab3  jz      short loc_18001FAF0
0x18001fab5  mov     eax, edi
0x18001fab7  imul    rsi, rax, 0A8h
0x18001fabe  cmp     [rsi+rbx], r14
0x18001fac2  jz      short loc_18001FAEA
0x18001fac4  mov     rax, [rsi+rbx+70h]
0x18001fac9  test    rax, rax
0x18001facc  jz      short loc_18001FAD3
0x18001face  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fad3  mov     rcx, [rsi+rbx]; hLibModule
0x18001fad7  call    cs:__imp_FreeLibrary
0x18001fadd  mov     ecx, cs:dword_1800C8568
0x18001fae3  mov     rbx, cs:qword_1800C8560
0x18001faea  inc     edi
0x18001faec  cmp     edi, ecx
0x18001faee  jb      short loc_18001FAB5
0x18001faf0  test    rbx, rbx
0x18001faf3  jz      short loc_18001FB07
0x18001faf5  mov     rcx, cs:hHeap; hHeap
0x18001fafc  mov     r8, rbx; lpMem
0x18001faff  xor     edx, edx; dwFlags
0x18001fb01  call    cs:__imp_HeapFree
0x18001fb07  mov     rcx, cs:hModule; hLibModule
0x18001fb0e  test    rcx, rcx
0x18001fb11  jz      short loc_18001FB19
0x18001fb13  call    cs:__imp_FreeLibrary
0x18001fb19  mov     r8, cs:gblpRouterPhoneBook; lpMem
0x18001fb20  test    r8, r8
0x18001fb23  jz      short loc_18001FB34
0x18001fb25  mov     rcx, cs:hHeap; hHeap
0x18001fb2c  xor     edx, edx; dwFlags
0x18001fb2e  call    cs:__imp_HeapFree
0x18001fb34  mov     r8, cs:gblpszAdminRequest; lpMem
0x18001fb3b  test    r8, r8
0x18001fb3e  jz      short loc_18001FB4F
0x18001fb40  mov     rcx, cs:hHeap; hHeap
0x18001fb47  xor     edx, edx; dwFlags
0x18001fb49  call    cs:__imp_HeapFree
0x18001fb4f  mov     r8, cs:gblpszUserRequest; lpMem
0x18001fb56  test    r8, r8
0x18001fb59  jz      short loc_18001FB6A
0x18001fb5b  mov     rcx, cs:hHeap; hHeap
0x18001fb62  xor     edx, edx; dwFlags
0x18001fb64  call    cs:__imp_HeapFree
0x18001fb6a  mov     r8, cs:gblpszHardwareFailure; lpMem
0x18001fb71  test    r8, r8
0x18001fb74  jz      short loc_18001FB85
0x18001fb76  mov     rcx, cs:hHeap; hHeap
0x18001fb7d  xor     edx, edx; dwFlags
0x18001fb7f  call    cs:__imp_HeapFree
0x18001fb85  mov     r8, cs:gblpszUnknownReason; lpMem
0x18001fb8c  test    r8, r8
0x18001fb8f  jz      short loc_18001FBA0
0x18001fb91  mov     rcx, cs:hHeap; hHeap
0x18001fb98  xor     edx, edx; dwFlags
0x18001fb9a  call    cs:__imp_HeapFree
0x18001fba0  mov     r8, cs:gblpszPm; lpMem
0x18001fba7  test    r8, r8
0x18001fbaa  jz      short loc_18001FBBB
0x18001fbac  mov     rcx, cs:hHeap; hHeap
0x18001fbb3  xor     edx, edx; dwFlags
0x18001fbb5  call    cs:__imp_HeapFree
0x18001fbbb  mov     r8, cs:gblpszAm; lpMem
0x18001fbc2  test    r8, r8
0x18001fbc5  jz      short loc_18001FBD6
0x18001fbc7  mov     rcx, cs:hHeap; hHeap
0x18001fbce  xor     edx, edx; dwFlags
0x18001fbd0  call    cs:__imp_HeapFree
0x18001fbd6  mov     r8, cs:gblpszIdleDisconnect; lpMem
0x18001fbdd  test    r8, r8
0x18001fbe0  jz      short loc_18001FBF1
0x18001fbe2  mov     rcx, cs:hHeap; hHeap
0x18001fbe9  xor     edx, edx; dwFlags
0x18001fbeb  call    cs:__imp_HeapFree
0x18001fbf1  mov     r8, cs:gblpszSessionTimeout; lpMem
0x18001fbf8  test    r8, r8
0x18001fbfb  jz      short loc_18001FC0C
0x18001fbfd  mov     rcx, cs:hHeap; hHeap
0x18001fc04  xor     edx, edx; dwFlags
0x18001fc06  call    cs:__imp_HeapFree
0x18001fc0c  mov     rcx, cs:hMem
0x18001fc13  test    rcx, rcx
0x18001fc16  jz      short loc_18001FC3C
0x18001fc18  mov     rcx, [rcx]; hMem
0x18001fc1b  call    cs:__imp_LocalFree
0x18001fc21  mov     rcx, cs:hMem; hMem
0x18001fc28  call    cs:__imp_LocalFree
0x18001fc2e  mov     cs:hMem, r14
0x18001fc35  mov     cs:dword_1800C862C, r14d
0x18001fc3c  mov     rcx, cs:qword_1800C8640
0x18001fc43  test    rcx, rcx
0x18001fc46  jz      short loc_18001FC6C
0x18001fc48  mov     rcx, [rcx]; hMem
0x18001fc4b  call    cs:__imp_LocalFree
0x18001fc51  mov     rcx, cs:qword_1800C8640; hMem
0x18001fc58  call    cs:__imp_LocalFree
0x18001fc5e  mov     cs:qword_1800C8640, r14
0x18001fc65  mov     cs:dword_1800C8638, r14d
0x18001fc6c  mov     rbx, cs:qword_1800C8678
0x18001fc73  lea     rdi, ??_7DdmThreadPool@@6B@; const DdmThreadPool::`vftable'
0x18001fc7a  mov     cs:dword_1800C8628, r14d
0x18001fc81  test    rbx, rbx
0x18001fc84  jz      short loc_18001FCA7
0x18001fc86  mov     [rbx], rdi
0x18001fc89  cmp     [rbx+60h], r14d
0x18001fc8d  jz      short loc_18001FC97
0x18001fc8f  mov     rcx, rbx; this
0x18001fc92  call    ?Uninitialize@DdmThreadPool@@UEAAKXZ; DdmThreadPool::Uninitialize(void)
0x18001fc97  mov     rcx, rbx
0x18001fc9a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fca0  mov     cs:qword_1800C8678, r14
0x18001fca7  cmp     cs:dword_1800C8654, r14d
0x18001fcae  jnz     short loc_18001FCDB
0x18001fcb0  lea     rax, ??_7DeviceClose@@6B@; const DeviceClose::`vftable'
0x18001fcb7  mov     ecx, 11h; unsigned int
0x18001fcbc  mov     qword ptr [rsp+0A8h+var_78.Data1], rax
0x18001fcc1  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18001fcc6  xor     r9d, r9d; void *
0x18001fcc9  lea     rdx, [rsp+0A8h+var_78]; struct DdmDeviceVisitor *
0x18001fcce  xor     r8d, r8d; int
0x18001fcd1  mov     rcx, rax; this
0x18001fcd4  call    ?AcceptVisitor@DdmDeviceTable@@QEAAKAEAVDdmDeviceVisitor@@HPEAX@Z; DdmDeviceTable::AcceptVisitor(DdmDeviceVisitor &,int,void *)
0x18001fcd9  jmp     short loc_18001FD05
0x18001fcdb  call    ?DdmDisableServerIpSecFilter@@YAKXZ; DdmDisableServerIpSecFilter(void)
0x18001fce0  lea     rcx, aDwuninitialize; "DwUnInitializeIpSec"
0x18001fce7  call    RasIpsecTrace
0x18001fcec  mov     rcx, cs:gFwpEngineHandle; engineHandle
0x18001fcf3  test    rcx, rcx
0x18001fcf6  jz      short loc_18001FD05
0x18001fcf8  call    cs:__imp_FwpmEngineClose0
0x18001fcfe  mov     cs:gFwpEngineHandle, r14
0x18001fd05  mov     rcx, cs:?pInstance@DdmNotificationHandler@@0PEAV1@EA; DdmNotificationHandler * DdmNotificationHandler::pInstance
0x18001fd0c  test    rcx, rcx
0x18001fd0f  jz      short loc_18001FD21
0x18001fd11  mov     rax, [rcx]
0x18001fd14  mov     edx, 1
0x18001fd19  mov     rax, [rax]
0x18001fd1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd21  mov     rbx, cs:qword_1800C8670
0x18001fd28  mov     cs:?pInstance@DdmNotificationHandler@@0PEAV1@EA, r14; DdmNotificationHandler * DdmNotificationHandler::pInstance
0x18001fd2f  test    rbx, rbx
0x18001fd32  jz      short loc_18001FD55
0x18001fd34  mov     [rbx], rdi
0x18001fd37  cmp     [rbx+60h], r14d
0x18001fd3b  jz      short loc_18001FD45
0x18001fd3d  mov     rcx, rbx; this
0x18001fd40  call    ?Uninitialize@DdmThreadPool@@UEAAKXZ; DdmThreadPool::Uninitialize(void)
0x18001fd45  mov     rcx, rbx
0x18001fd48  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fd4e  mov     cs:qword_1800C8670, r14
0x18001fd55  mov     rcx, cs:?pInstance@DdmConnectionTable@@0PEAV1@EA; DdmConnectionTable * DdmConnectionTable::pInstance
0x18001fd5c  test    rcx, rcx
0x18001fd5f  jz      short loc_18001FD71
0x18001fd61  mov     rax, [rcx]
0x18001fd64  mov     edx, 1
0x18001fd69  mov     rax, [rax]
0x18001fd6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd71  mov     rbx, cs:?pInstance@DdmDeviceTable@@0PEAV1@EA; DdmDeviceTable * DdmDeviceTable::pInstance
0x18001fd78  mov     cs:?pInstance@DdmConnectionTable@@0PEAV1@EA, r14; DdmConnectionTable * DdmConnectionTable::pInstance
0x18001fd7f  test    rbx, rbx
0x18001fd82  jz      short loc_18001FD95
0x18001fd84  mov     rcx, rbx; this
0x18001fd87  call    ??1DdmDeviceTable@@QEAA@XZ; DdmDeviceTable::~DdmDeviceTable(void)
0x18001fd8c  mov     rcx, rbx
0x18001fd8f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fd95  mov     rdx, cs:gblSupervisorEvents
0x18001fd9c  mov     cs:?pInstance@DdmDeviceTable@@0PEAV1@EA, r14; DdmDeviceTable * DdmDeviceTable::pInstance
0x18001fda3  test    rdx, rdx
0x18001fda6  jz      short loc_18001FDE2
0x18001fda8  lea     eax, [rbp+2]
0x18001fdab  mov     ebx, r14d
0x18001fdae  lea     esi, [rax+rax*2]
0x18001fdb1  test    esi, esi
0x18001fdb3  jz      short loc_18001FDE2
0x18001fdb5  mov     edi, ebx
0x18001fdb7  mov     rcx, [rdx+rdi*8]; hObject
0x18001fdbb  test    rcx, rcx
0x18001fdbe  jz      short loc_18001FDDC
0x18001fdc0  mov     eax, ebx
0x18001fdc2  test    ebx, ebx
0x18001fdc4  jz      short loc_18001FDD8
0x18001fdc6  cmp     eax, 1
0x18001fdc9  jz      short loc_18001FDD8
0x18001fdcb  call    cs:__imp_CloseHandle
0x18001fdd1  mov     rdx, cs:gblSupervisorEvents
0x18001fdd8  mov     [rdx+rdi*8], r14
0x18001fddc  inc     ebx
0x18001fdde  cmp     ebx, esi
0x18001fde0  jb      short loc_18001FDB5
0x18001fde2  lea     rcx, gblDeviceTable; lpCriticalSection
0x18001fde9  call    cs:__imp_EnterCriticalSection
0x18001fdef  lea     rcx, gblDeviceTable; lpCriticalSection
0x18001fdf6  call    cs:__imp_DeleteCriticalSection
0x18001fdfc  lea     rcx, xmmword_1800C97D0+8; lpCriticalSection
0x18001fe03  call    cs:__imp_DeleteCriticalSection
0x18001fe09  test    byte ptr cs:dword_1800C84E0, 80h
0x18001fe10  xorps   xmm0, xmm0
0x18001fe13  movups  cs:xmmword_1800C97D0, xmm0
0x18001fe1a  movups  cs:xmmword_1800C97E0, xmm0
0x18001fe21  movups  cs:xmmword_1800C97F0, xmm0
0x18001fe28  jz      loc_18001FEAE
0x18001fe2e  lea     rdi, CriticalSection
  ... truncated ...
```
