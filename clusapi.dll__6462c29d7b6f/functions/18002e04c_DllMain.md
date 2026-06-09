# DllMain

- ea: `0x18002e04c`
- end: `0x18002e0fa`
- name: `DllMain`
- size: `174`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002db4`

## callees

- `0x180001160`
- `0x180001210`
- `0x18002e04c`
- `0x18009e1f8`
- `0x18009e238`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18002e0dd`
- `ntdll!EtwEventUnregister` at `0x18002e0dd`
- `ntdll!EtwEventRegister` at `0x18002e08e`
- `ntdll!EtwEventRegister` at `0x18002e08e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002e09b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002e09b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e0ea`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002e0ea`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF

  if ( fdwReason == 1 )
  {
    g_ClusapiModule = hinstDLL;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(hinstDLL, fdwReason, lpvReserved);
    v4 = MICROSOFT_FAILOVER_CLUSTER_API_PUBLISHER;
    if ( !_InterlockedExchange(&lHandleRegistered, 1) )
      ((void (__fastcall *)(__int128 *, _QWORD, _QWORD, unsigned __int64 *))EtwEventRegister)(&v4, 0, 0, &handle);
    InitializeCriticalSection(&EventLogLock);
    ClRtlInitializeQueue((__int64)&g_ClusterHandleList);
  }
  else if ( !fdwReason )
  {
    ClRtlDeleteQueue(&g_ClusterHandleList);
    TraceLoggingUnregister_EventUnregister();
    if ( _InterlockedExchange(&lHandleRegistered, 0) == 1 && handle )
      EtwEventUnregister();
    DeleteCriticalSection(&EventLogLock);
  }
  return 1;
}

```

## disassembly

```asm
0x18002e04c  sub     rsp, 38h
0x18002e050  cmp     edx, 1
0x18002e053  jnz     short loc_18002E0AF
0x18002e055  mov     cs:?g_ClusapiModule@@3PEAUHINSTANCE__@@EA, rcx; HINSTANCE__ * g_ClusapiModule
0x18002e05c  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002e061  movups  xmm0, cs:MICROSOFT_FAILOVER_CLUSTER_API_PUBLISHER
0x18002e068  mov     eax, 1
0x18002e06d  movdqu  [rsp+38h+var_18], xmm0
0x18002e073  xchg    eax, cs:?lHandleRegistered@@3JC; long volatile lHandleRegistered
0x18002e079  test    eax, eax
0x18002e07b  jnz     short loc_18002E094
0x18002e07d  lea     r9, ?handle@@3_KA; unsigned __int64 handle
0x18002e084  xor     r8d, r8d
0x18002e087  xor     edx, edx
0x18002e089  lea     rcx, [rsp+38h+var_18]
0x18002e08e  call    cs:__imp_EtwEventRegister
0x18002e094  lea     rcx, EventLogLock; lpCriticalSection
0x18002e09b  call    cs:__imp_InitializeCriticalSection
0x18002e0a1  lea     rcx, ?g_ClusterHandleList@@3U_CL_QUEUE@@A; _CL_QUEUE g_ClusterHandleList
0x18002e0a8  call    ClRtlInitializeQueue
0x18002e0ad  jmp     short loc_18002E0F0
0x18002e0af  test    edx, edx
0x18002e0b1  jnz     short loc_18002E0F0
0x18002e0b3  lea     rcx, ?g_ClusterHandleList@@3U_CL_QUEUE@@A; void *
0x18002e0ba  call    ClRtlDeleteQueue
0x18002e0bf  call    TraceLoggingUnregister_EventUnregister
0x18002e0c4  xor     eax, eax
0x18002e0c6  xchg    eax, cs:?lHandleRegistered@@3JC; long volatile lHandleRegistered
0x18002e0cc  cmp     eax, 1
0x18002e0cf  jnz     short loc_18002E0E3
0x18002e0d1  mov     rcx, cs:?handle@@3_KA; unsigned __int64 handle
0x18002e0d8  test    rcx, rcx
0x18002e0db  jz      short loc_18002E0E3
0x18002e0dd  call    cs:__imp_EtwEventUnregister
0x18002e0e3  lea     rcx, EventLogLock; lpCriticalSection
0x18002e0ea  call    cs:__imp_DeleteCriticalSection
0x18002e0f0  mov     eax, 1
0x18002e0f5  add     rsp, 38h
0x18002e0f9  retn
```
