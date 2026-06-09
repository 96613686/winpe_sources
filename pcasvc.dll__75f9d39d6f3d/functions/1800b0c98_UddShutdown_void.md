# UddShutdown(void)

- ea: `0x1800b0c98`
- end: `0x1800b0e64`
- name: `?UddShutdown@@YAXXZ`
- size: `460`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002f4ac`
- `0x1800b0e70`

## callees

- `0x1800010e8`
- `0x18001606c`
- `0x18003222c`
- `0x1800b0c98`
- `0x1800b0e88`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800b0cc6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800b0d55`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800b0cc6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800b0d55`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800b0cda`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800b0d76`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800b0cda`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800b0d76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0d24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b0d24`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800b0d07`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800b0d07`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b0d8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800b0d8a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b0cfa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800b0cfa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b0d97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800b0d97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800b0e34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1800b0e34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0d41`

## pseudocode

```c
void UddShutdown(void)
{
  PVOID v0; // rcx
  __int64 v1; // rax
  _DWORD *v2; // rbx
  __int64 v3; // rax

  if ( UddpInitialized && !UddpShuttingDown )
  {
    RtlAcquireSRWLockExclusive(&UddpLock);
    UddpShuttingDown = 1;
    RtlReleaseSRWLockExclusive(&UddpLock);
    TraceLoggingUnregister_EventUnregister(&dword_1801564D8);
    if ( UddpServicesNotifyTPWait )
    {
      WaitForThreadpoolWaitCallbacks(UddpServicesNotifyTPWait, 1);
      CloseThreadpoolWait(UddpServicesNotifyTPWait);
      UddpServicesNotifyTPWait = 0;
    }
    if ( UddpServicesNotifyKeyHandle )
    {
      RegCloseKey(UddpServicesNotifyKeyHandle);
      UddpServicesNotifyKeyHandle = 0;
    }
    if ( UddpServicesNotifyEventHandle )
    {
      CloseHandle(UddpServicesNotifyEventHandle);
      UddpServicesNotifyEventHandle = 0;
    }
    RtlAcquireSRWLockExclusive(&UddpLock);
    UddpFreeServiceKeyNameList(&UddpServiceKeyNameList);
    UddpFreeServiceKeyNameList(&stru_180159410);
    RtlReleaseSRWLockExclusive(&UddpLock);
    if ( UddpTPWork )
    {
      WaitForThreadpoolWorkCallbacks(UddpTPWork, 0);
      CloseThreadpoolWork(UddpTPWork);
      UddpTPWork = 0;
    }
    while ( 1 )
    {
      v0 = UddpWorkList;
      if ( UddpWorkList == &UddpWorkList )
        break;
      if ( *((PVOID **)UddpWorkList + 1) != &UddpWorkList
        || (v1 = *(_QWORD *)UddpWorkList, *(PVOID *)(*(_QWORD *)UddpWorkList + 8LL) != UddpWorkList) )
      {
LABEL_21:
        __fastfail(3u);
      }
      UddpWorkList = *(PVOID *)UddpWorkList;
      *(_QWORD *)(v1 + 8) = &UddpWorkList;
      UddpFreeWork(v0);
    }
    while ( 1 )
    {
      v2 = UddpPendingRetryWorkList;
      if ( UddpPendingRetryWorkList == &UddpPendingRetryWorkList )
        break;
      if ( *((PVOID **)UddpPendingRetryWorkList + 1) != &UddpPendingRetryWorkList )
        goto LABEL_21;
      v3 = *(_QWORD *)UddpPendingRetryWorkList;
      if ( *(PVOID *)(*(_QWORD *)UddpPendingRetryWorkList + 8LL) != UddpPendingRetryWorkList )
        goto LABEL_21;
      UddpPendingRetryWorkList = *(PVOID *)UddpPendingRetryWorkList;
      *(_QWORD *)(v3 + 8) = &UddpPendingRetryWorkList;
      if ( v2[10] == 3 )
        UddpDisableUnsignedBootDriver(v2);
      UddpFreeWork(v2);
    }
    if ( UddpTPPool )
    {
      CloseThreadpool(UddpTPPool);
      UddpTPPool = 0;
    }
    UddpShuttingDown = 0;
    UddpInitialized = 0;
  }
}

```

## disassembly

```asm
0x1800b0c98  mov     [rsp+arg_0], rbx
0x1800b0c9d  push    rsi
0x1800b0c9e  sub     rsp, 20h
0x1800b0ca2  cmp     cs:?UddpInitialized@@3HA, 0; int UddpInitialized
0x1800b0ca9  jz      loc_1800B0E59
0x1800b0caf  cmp     cs:?UddpShuttingDown@@3HA, 0; int UddpShuttingDown
0x1800b0cb6  jnz     loc_1800B0E59
0x1800b0cbc  lea     rbx, ?UddpLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK UddpLock
0x1800b0cc3  mov     rcx, rbx
0x1800b0cc6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800b0ccc  mov     esi, 1
0x1800b0cd1  mov     rcx, rbx
0x1800b0cd4  mov     cs:?UddpShuttingDown@@3HA, esi; int UddpShuttingDown
0x1800b0cda  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800b0ce0  lea     rcx, dword_1801564D8
0x1800b0ce7  call    TraceLoggingUnregister_EventUnregister
0x1800b0cec  mov     rcx, cs:?UddpServicesNotifyTPWait@@3PEAU_TP_WAIT@@EA; pwa
0x1800b0cf3  test    rcx, rcx
0x1800b0cf6  jz      short loc_1800B0D18
0x1800b0cf8  mov     edx, esi; fCancelPendingCallbacks
0x1800b0cfa  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800b0d00  mov     rcx, cs:?UddpServicesNotifyTPWait@@3PEAU_TP_WAIT@@EA; pwa
0x1800b0d07  call    cs:__imp_CloseThreadpoolWait
0x1800b0d0d  mov     cs:?UddpServicesNotifyTPWait@@3PEAU_TP_WAIT@@EA, 0; _TP_WAIT * UddpServicesNotifyTPWait
0x1800b0d18  mov     rcx, cs:?UddpServicesNotifyKeyHandle@@3PEAUHKEY__@@EA; hKey
0x1800b0d1f  test    rcx, rcx
0x1800b0d22  jz      short loc_1800B0D35
0x1800b0d24  call    cs:__imp_RegCloseKey
0x1800b0d2a  mov     cs:?UddpServicesNotifyKeyHandle@@3PEAUHKEY__@@EA, 0; HKEY__ * UddpServicesNotifyKeyHandle
0x1800b0d35  mov     rcx, cs:?UddpServicesNotifyEventHandle@@3PEAXEA; hObject
0x1800b0d3c  test    rcx, rcx
0x1800b0d3f  jz      short loc_1800B0D52
0x1800b0d41  call    cs:__imp_CloseHandle
0x1800b0d47  mov     cs:?UddpServicesNotifyEventHandle@@3PEAXEA, 0; void * UddpServicesNotifyEventHandle
0x1800b0d52  mov     rcx, rbx
0x1800b0d55  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800b0d5b  lea     rcx, ?UddpServiceKeyNameList@@3PAU_LIST_ENTRY@@A; struct _LIST_ENTRY *
0x1800b0d62  call    ?UddpFreeServiceKeyNameList@@YAXPEAU_LIST_ENTRY@@@Z; UddpFreeServiceKeyNameList(_LIST_ENTRY *)
0x1800b0d67  lea     rcx, stru_180159410; struct _LIST_ENTRY *
0x1800b0d6e  call    ?UddpFreeServiceKeyNameList@@YAXPEAU_LIST_ENTRY@@@Z; UddpFreeServiceKeyNameList(_LIST_ENTRY *)
0x1800b0d73  mov     rcx, rbx
0x1800b0d76  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800b0d7c  mov     rcx, cs:?UddpTPWork@@3PEAU_TP_WORK@@EA; pwk
0x1800b0d83  test    rcx, rcx
0x1800b0d86  jz      short loc_1800B0DA8
0x1800b0d88  xor     edx, edx; fCancelPendingCallbacks
0x1800b0d8a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800b0d90  mov     rcx, cs:?UddpTPWork@@3PEAU_TP_WORK@@EA; pwk
0x1800b0d97  call    cs:__imp_CloseThreadpoolWork
0x1800b0d9d  mov     cs:?UddpTPWork@@3PEAU_TP_WORK@@EA, 0; _TP_WORK * UddpTPWork
0x1800b0da8  lea     rbx, ?UddpWorkList@@3U_LIST_ENTRY@@A; _LIST_ENTRY UddpWorkList
0x1800b0daf  mov     rcx, cs:?UddpWorkList@@3U_LIST_ENTRY@@A; P
0x1800b0db6  cmp     rcx, rbx
0x1800b0db9  jz      short loc_1800B0DDC
0x1800b0dbb  cmp     [rcx+8], rbx
0x1800b0dbf  jnz     short loc_1800B0E21
0x1800b0dc1  mov     rax, [rcx]
0x1800b0dc4  cmp     [rax+8], rcx
0x1800b0dc8  jnz     short loc_1800B0E21
0x1800b0dca  mov     cs:?UddpWorkList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY UddpWorkList
0x1800b0dd1  mov     [rax+8], rbx
0x1800b0dd5  call    UddpFreeWork
0x1800b0dda  jmp     short loc_1800B0DAF
0x1800b0ddc  lea     rsi, ?UddpPendingRetryWorkList@@3U_LIST_ENTRY@@A; _LIST_ENTRY UddpPendingRetryWorkList
0x1800b0de3  mov     rbx, cs:?UddpPendingRetryWorkList@@3U_LIST_ENTRY@@A; _LIST_ENTRY UddpPendingRetryWorkList
0x1800b0dea  cmp     rbx, rsi
0x1800b0ded  jz      short loc_1800B0E28
0x1800b0def  cmp     [rbx+8], rsi
0x1800b0df3  jnz     short loc_1800B0E21
0x1800b0df5  mov     rax, [rbx]
0x1800b0df8  cmp     [rax+8], rbx
0x1800b0dfc  jnz     short loc_1800B0E21
0x1800b0dfe  mov     cs:?UddpPendingRetryWorkList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY UddpPendingRetryWorkList
0x1800b0e05  mov     [rax+8], rsi
0x1800b0e09  cmp     dword ptr [rbx+28h], 3
0x1800b0e0d  jnz     short loc_1800B0E17
0x1800b0e0f  mov     rcx, rbx
0x1800b0e12  call    UddpDisableUnsignedBootDriver
0x1800b0e17  mov     rcx, rbx; P
0x1800b0e1a  call    UddpFreeWork
0x1800b0e1f  jmp     short loc_1800B0DE3
0x1800b0e21  mov     ecx, 3
0x1800b0e26  int     29h; Win8: RtlFailFast(ecx)
0x1800b0e28  mov     rcx, cs:?UddpTPPool@@3PEAU_TP_POOL@@EA; ptpp
0x1800b0e2f  test    rcx, rcx
0x1800b0e32  jz      short loc_1800B0E45
0x1800b0e34  call    cs:__imp_CloseThreadpool
0x1800b0e3a  mov     cs:?UddpTPPool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * UddpTPPool
0x1800b0e45  mov     cs:?UddpShuttingDown@@3HA, 0; int UddpShuttingDown
0x1800b0e4f  mov     cs:?UddpInitialized@@3HA, 0; int UddpInitialized
0x1800b0e59  mov     rbx, [rsp+28h+arg_0]
0x1800b0e5e  add     rsp, 20h
0x1800b0e62  pop     rsi
0x1800b0e63  retn
```
