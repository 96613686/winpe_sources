# UddInitialize(void)

- ea: `0x18002f4ac`
- end: `0x18002f7aa`
- name: `?UddInitialize@@YAKXZ`
- size: `766`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18002f2a0`

## callees

- `0x180012920`
- `0x180015e54`
- `0x18002f4ac`
- `0x18002f7b0`
- `0x18002f860`
- `0x18004f8c0`
- `0x1800b0c98`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x18002f511`
- `ntdll!RtlInitializeSRWLock` at `0x18002f511`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f6dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002f6dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f6b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f6b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002f621`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002f621`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002f659`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002f659`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002f5c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002f5c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002f786`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002f786`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002f716`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18002f716`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002f612`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002f612`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18002f756`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18002f756`

## string_xrefs

- `0x18002f6a7`: `SYSTEM\CurrentControlSet\Services`
- `0x18002f6c1`: `Failed to open services key [%d]`
- `0x18002f72d`: `Failed to create threadpoolWait [%d]`
- `0x18002f6f4`: `Failed to create 'services' event [%d]`
- `0x18002f670`: `Failed to create threadpoolWork [%d]`
- `0x18002f630`: `Failed to set threadpool minimum [%d]`
- `0x18002f5e0`: `Failed to create threadpool [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 UddInitialize(void)
{
  struct _TP_POOL *Threadpool; // rax
  unsigned int LastError; // eax
  const char *v3; // r9
  int v4; // r8d
  unsigned int v5; // ebx
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-38h] BYREF
  struct _FILETIME pftTimeout; // [rsp+70h] [rbp+8h] BYREF

  pftTimeout = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  if ( (unsigned int)UddpIsSystemSetupInProgress() )
    return 0;
  if ( !UddpInitialized && !UddpShuttingDown )
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1801564D8);
    RtlInitializeSRWLock(&UddpLock);
    UddpLastServiceKeyNameListIndex = 2;
    stru_180159410.Blink = &stru_180159410;
    stru_180159410.Flink = &stru_180159410;
    UddpServiceKeyNameList.Blink = &UddpServiceKeyNameList;
    qword_180159368 = (__int64)&UddpWorkList;
    UddpWorkList = &UddpWorkList;
    UddpServiceKeyNameList.Flink = &UddpServiceKeyNameList;
    qword_1801593F8 = (__int64)&UddpPendingRetryWorkList;
    UddpPendingRetryWorkList = &UddpPendingRetryWorkList;
    UddpInitialized = 1;
    UddpTPEnvironment.Version = 3;
    UddpTPEnvironment.Pool = 0;
    UddpTPEnvironment.CleanupGroup = 0;
    UddpTPEnvironment.CleanupGroupCancelCallback = 0;
    *(_OWORD *)&UddpTPEnvironment.RaceDll = 0;
    UddpTPEnvironment.FinalizationCallback = 0;
    UddpTPEnvironment.u.Flags = 0;
    UddpTPEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
    UddpTPEnvironment.Size = 72;
    Threadpool = CreateThreadpool(0);
    UddpTPPool = Threadpool;
    if ( Threadpool )
    {
      SetThreadpoolThreadMaximum(Threadpool, 1u);
      if ( SetThreadpoolThreadMinimum(UddpTPPool, 1u) )
      {
        UddpTPEnvironment.Pool = UddpTPPool;
        UddpTPWork = CreateThreadpoolWork(UddpTPWorkCallback, 0, 0);
        if ( UddpTPWork )
        {
          v5 = UddpPopulateServiceKeyNameList(&UddpServiceKeyNameList);
          if ( v5 )
            goto LABEL_9;
          v5 = RegOpenKeyExW(
                 HKEY_LOCAL_MACHINE,
                 L"SYSTEM\\CurrentControlSet\\Services",
                 0,
                 0x10u,
                 &UddpServicesNotifyKeyHandle);
          if ( v5 )
          {
            v3 = "Failed to open services key [%d]";
            v4 = 761;
            goto LABEL_8;
          }
          UddpServicesNotifyEventHandle = CreateEventW(0, 0, 0, 0);
          if ( UddpServicesNotifyEventHandle )
          {
            UddpServicesNotifyTPWait = CreateThreadpoolWait(UddpServicesNotifyTPWaitCallback, 0, &UddpTPEnvironment);
            if ( UddpServicesNotifyTPWait )
            {
              memset(&SystemInfo, 0, sizeof(SystemInfo));
              GetSystemInfo(&SystemInfo);
              if ( !SystemInfo.wProcessorArchitecture )
                UddpProcessorArchitectureIsx86 = 1;
              pftTimeout = (struct _FILETIME)-10000LL;
              SetThreadpoolWait(UddpServicesNotifyTPWait, UddpServicesNotifyEventHandle, &pftTimeout);
              return 0;
            }
            LastError = UddpGetLastError();
            v3 = "Failed to create threadpoolWait [%d]";
            v4 = 783;
          }
          else
          {
            LastError = UddpGetLastError();
            v3 = "Failed to create 'services' event [%d]";
            v4 = 772;
          }
        }
        else
        {
          LastError = UddpGetLastError();
          v3 = "Failed to create threadpoolWork [%d]";
          v4 = 739;
        }
      }
      else
      {
        LastError = UddpGetLastError();
        v3 = "Failed to set threadpool minimum [%d]";
        v4 = 726;
      }
    }
    else
    {
      LastError = UddpGetLastError();
      v3 = "Failed to create threadpool [%d]";
      v4 = 718;
    }
    v5 = LastError;
LABEL_8:
    AslLogCallPrintf(1, (unsigned int)"UddInitialize", v4, (_DWORD)v3);
LABEL_9:
    UddShutdown();
    return v5;
  }
  return 1056;
}

```

## disassembly

```asm
0x18002f4ac  mov     rax, rsp
0x18002f4af  mov     [rax+10h], rbx
0x18002f4b3  mov     [rax+18h], rsi
0x18002f4b7  push    rdi
0x18002f4b8  sub     rsp, 60h
0x18002f4bc  xorps   xmm0, xmm0
0x18002f4bf  xor     edi, edi
0x18002f4c1  mov     [rax+8], rdi
0x18002f4c5  movups  xmmword ptr [rax-38h], xmm0
0x18002f4c9  movups  xmmword ptr [rax-28h], xmm0
0x18002f4cd  movups  xmmword ptr [rax-18h], xmm0
0x18002f4d1  call    UddpIsSystemSetupInProgress
0x18002f4d6  test    eax, eax
0x18002f4d8  jz      short loc_18002F4E1
0x18002f4da  xor     eax, eax
0x18002f4dc  jmp     loc_18002F798
0x18002f4e1  cmp     cs:?UddpInitialized@@3HA, edi; int UddpInitialized
0x18002f4e7  jnz     loc_18002F793
0x18002f4ed  cmp     cs:?UddpShuttingDown@@3HA, edi; int UddpShuttingDown
0x18002f4f3  jnz     loc_18002F793
0x18002f4f9  xor     r8d, r8d
0x18002f4fc  lea     rcx, dword_1801564D8; CallbackContext
0x18002f503  xor     edx, edx
0x18002f505  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002f50a  lea     rcx, ?UddpLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK UddpLock
0x18002f511  call    cs:__imp_RtlInitializeSRWLock
0x18002f517  lea     rax, stru_180159410
0x18002f51e  mov     cs:?UddpLastServiceKeyNameListIndex@@3KA, 2; ulong UddpLastServiceKeyNameListIndex
0x18002f528  mov     cs:stru_180159410.Blink, rax
0x18002f52f  lea     rbx, ?UddpServiceKeyNameList@@3PAU_LIST_ENTRY@@A; _LIST_ENTRY near * UddpServiceKeyNameList
0x18002f536  mov     cs:stru_180159410.Flink, rax
0x18002f53d  mov     esi, 1
0x18002f542  lea     rax, ?UddpWorkList@@3U_LIST_ENTRY@@A; _LIST_ENTRY UddpWorkList
0x18002f549  mov     cs:?UddpServiceKeyNameList@@3PAU_LIST_ENTRY@@A.Blink, rbx; _LIST_ENTRY near * UddpServiceKeyNameList ...
0x18002f550  mov     cs:qword_180159368, rax
0x18002f557  xorps   xmm0, xmm0
0x18002f55a  mov     cs:?UddpWorkList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY UddpWorkList
0x18002f561  xor     ecx, ecx; reserved
0x18002f563  lea     rax, ?UddpPendingRetryWorkList@@3U_LIST_ENTRY@@A; _LIST_ENTRY UddpPendingRetryWorkList
0x18002f56a  mov     cs:?UddpServiceKeyNameList@@3PAU_LIST_ENTRY@@A.Flink, rbx; _LIST_ENTRY near * UddpServiceKeyNameList ...
0x18002f571  mov     cs:qword_1801593F8, rax
0x18002f578  mov     cs:?UddpPendingRetryWorkList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY UddpPendingRetryWorkList
0x18002f57f  mov     cs:?UddpInitialized@@3HA, esi; int UddpInitialized
0x18002f585  mov     cs:?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 UddpTPEnvironment ...
0x18002f58f  mov     cs:?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rdi; _TP_CALLBACK_ENVIRON_V3 UddpTPEnvironment ...
0x18002f596  mov     cs:?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rdi; _TP_CALLBACK_ENVIRON_V3 UddpTPEnvironment ...
0x18002f59d  mov     cs:?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 UddpTPEnvironment ...
0x18002f5a4  movdqa  xmmword ptr cs:?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 UddpTPEnvironment ...
0x18002f5ac  mov     cs:?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rdi; _TP_CALLBACK_ENVIRON_V3 UddpTPEnvironment ...
0x18002f5b3  mov     dword ptr cs:?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, edi; _TP_CALLBACK_ENVIRON_V3 UddpTPEnvironment ...
0x18002f5b9  mov     cs:?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, esi; _TP_CALLBACK_ENVIRON_V3 UddpTPEnvironment ...
0x18002f5bf  mov     cs:?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 UddpTPEnvironment ...
0x18002f5c9  call    cs:__imp_CreateThreadpool
0x18002f5cf  mov     cs:?UddpTPPool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * UddpTPPool
0x18002f5d6  test    rax, rax
0x18002f5d9  jnz     short loc_18002F60D
0x18002f5db  call    UddpGetLastError
0x18002f5e0  lea     r9, aFailedToCreate_30; "Failed to create threadpool [%d]"
0x18002f5e7  mov     r8d, 2CEh
0x18002f5ed  mov     ebx, eax
0x18002f5ef  lea     rdx, aUddinitialize; "UddInitialize"
0x18002f5f6  mov     dword ptr [rsp+68h+phkResult], eax
0x18002f5fa  mov     ecx, esi
0x18002f5fc  call    AslLogCallPrintf
0x18002f601  call    ?UddShutdown@@YAXXZ; UddShutdown(void)
0x18002f606  mov     eax, ebx
0x18002f608  jmp     loc_18002F798
0x18002f60d  mov     edx, esi; cthrdMost
0x18002f60f  mov     rcx, rax; ptpp
0x18002f612  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002f618  mov     rcx, cs:?UddpTPPool@@3PEAU_TP_POOL@@EA; ptpp
0x18002f61f  mov     edx, esi; cthrdMic
0x18002f621  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002f627  test    eax, eax
0x18002f629  jnz     short loc_18002F63F
0x18002f62b  call    UddpGetLastError
0x18002f630  lea     r9, aFailedToSetThr; "Failed to set threadpool minimum [%d]"
0x18002f637  mov     r8d, 2D6h
0x18002f63d  jmp     short loc_18002F5ED
0x18002f63f  mov     rax, cs:?UddpTPPool@@3PEAU_TP_POOL@@EA; _TP_POOL * UddpTPPool
0x18002f646  lea     rcx, UddpTPWorkCallback; pfnwk
0x18002f64d  xor     r8d, r8d; pcbe
0x18002f650  mov     cs:?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 UddpTPEnvironment ...
0x18002f657  xor     edx, edx; pv
0x18002f659  call    cs:__imp_CreateThreadpoolWork
0x18002f65f  mov     cs:?UddpTPWork@@3PEAU_TP_WORK@@EA, rax; _TP_WORK * UddpTPWork
0x18002f666  test    rax, rax
0x18002f669  jnz     short loc_18002F682
0x18002f66b  call    UddpGetLastError
0x18002f670  lea     r9, aFailedToCreate_16; "Failed to create threadpoolWork [%d]"
0x18002f677  mov     r8d, 2E3h
0x18002f67d  jmp     loc_18002F5ED
0x18002f682  mov     rcx, rbx; struct _LIST_ENTRY *
0x18002f685  call    ?UddpPopulateServiceKeyNameList@@YAKPEAU_LIST_ENTRY@@@Z; UddpPopulateServiceKeyNameList(_LIST_ENTRY *)
0x18002f68a  mov     ebx, eax
0x18002f68c  test    eax, eax
0x18002f68e  jnz     loc_18002F601
0x18002f694  lea     rax, ?UddpServicesNotifyKeyHandle@@3PEAUHKEY__@@EA; HKEY__ * UddpServicesNotifyKeyHandle
0x18002f69b  xor     r8d, r8d; ulOptions
0x18002f69e  lea     r9d, [rbx+10h]; samDesired
0x18002f6a2  mov     [rsp+68h+phkResult], rax; phkResult
0x18002f6a7  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services"
0x18002f6ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f6b5  call    cs:__imp_RegOpenKeyExW
0x18002f6bb  mov     ebx, eax
0x18002f6bd  test    eax, eax
0x18002f6bf  jz      short loc_18002F6D3
0x18002f6c1  lea     r9, aFailedToOpenSe; "Failed to open services key [%d]"
0x18002f6c8  mov     r8d, 2F9h
0x18002f6ce  jmp     loc_18002F5EF
0x18002f6d3  xor     r9d, r9d; lpName
0x18002f6d6  xor     r8d, r8d; bInitialState
0x18002f6d9  xor     edx, edx; bManualReset
0x18002f6db  xor     ecx, ecx; lpEventAttributes
0x18002f6dd  call    cs:__imp_CreateEventW
0x18002f6e3  mov     cs:?UddpServicesNotifyEventHandle@@3PEAXEA, rax; void * UddpServicesNotifyEventHandle
0x18002f6ea  test    rax, rax
0x18002f6ed  jnz     short loc_18002F706
0x18002f6ef  call    UddpGetLastError
0x18002f6f4  lea     r9, aFailedToCreate_4; "Failed to create 'services' event [%d]"
0x18002f6fb  mov     r8d, 304h
0x18002f701  jmp     loc_18002F5ED
0x18002f706  lea     r8, ?UddpTPEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18002f70d  xor     edx, edx; pv
0x18002f70f  lea     rcx, UddpServicesNotifyTPWaitCallback; pfnwa
0x18002f716  call    cs:__imp_CreateThreadpoolWait
0x18002f71c  mov     cs:?UddpServicesNotifyTPWait@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * UddpServicesNotifyTPWait
0x18002f723  test    rax, rax
0x18002f726  jnz     short loc_18002F73F
0x18002f728  call    UddpGetLastError
0x18002f72d  lea     r9, aFailedToCreate_46; "Failed to create threadpoolWait [%d]"
0x18002f734  mov     r8d, 30Fh
0x18002f73a  jmp     loc_18002F5ED
0x18002f73f  xorps   xmm0, xmm0
0x18002f742  lea     rcx, [rsp+68h+SystemInfo]; lpSystemInfo
0x18002f747  movups  xmmword ptr [rsp+68h+SystemInfo], xmm0
0x18002f74c  movups  xmmword ptr [rsp+68h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18002f751  movups  xmmword ptr [rsp+68h+SystemInfo.dwNumberOfProcessors], xmm0
0x18002f756  call    cs:__imp_GetSystemInfo
0x18002f75c  cmp     word ptr [rsp+68h+SystemInfo], di
0x18002f761  jnz     short loc_18002F76A
0x18002f763  mov     cs:?UddpProcessorArchitectureIsx86@@3EA, sil; uchar UddpProcessorArchitectureIsx86
0x18002f76a  mov     rdx, cs:?UddpServicesNotifyEventHandle@@3PEAXEA; h
0x18002f771  lea     r8, [rsp+68h+pftTimeout]; pftTimeout
0x18002f776  mov     rcx, cs:?UddpServicesNotifyTPWait@@3PEAU_TP_WAIT@@EA; pwa
0x18002f77d  mov     qword ptr [rsp+68h+pftTimeout.dwLowDateTime], 0FFFFFFFFFFFFD8F0h
0x18002f786  call    cs:__imp_SetThreadpoolWait
0x18002f78c  mov     ebx, edi
0x18002f78e  jmp     loc_18002F606
0x18002f793  mov     eax, 420h
0x18002f798  lea     r11, [rsp+68h+var_8]
0x18002f79d  mov     rbx, [r11+18h]
0x18002f7a1  mov     rsi, [r11+20h]
0x18002f7a5  mov     rsp, r11
0x18002f7a8  pop     rdi
0x18002f7a9  retn
```
