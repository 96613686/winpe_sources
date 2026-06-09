# NlAllocateClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *,ulong,_NETLOGON_SECURE_CHANNEL_TYPE,ulong)

- ea: `0x180063f6c`
- end: `0x180064221`
- name: `?NlAllocateClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@KW4_NETLOGON_SECURE_CHANNEL_TYPE@@K@Z`
- size: `693`
- prototype: `HLOCAL __fastcall(struct _DOMAIN_INFO *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, void *, struct _GUID *, int, int, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180026c90`
- `0x180027d78`
- `0x18005322c`
- `0x18006a694`

## callees

- `0x180007278`
- `0x18000bd98`
- `0x18000da94`
- `0x18004fc18`
- `0x180063f6c`
- `0x1800679fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800640d3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18006410a`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800640d3`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18006410a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064130`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180064130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800641c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800641c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063fc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063fc9`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180064196`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180064196`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006416c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006416c`
- `ntdll!RtlInitializeCriticalSection` at `0x180064013`
- `ntdll!RtlInitializeCriticalSection` at `0x180064013`
- `ntdll!RtlReleaseResource` at `0x1800641f0`
- `ntdll!RtlReleaseResource` at `0x1800641f0`

## string_xrefs

- `0x1800641d1`: `NlAllocateClientSession: Could not create new perf instance: "%ws"\n    ClientSession = %p\n    Error = %d\n`

## pseudocode

```c
HLOCAL __fastcall NlAllocateClientSession(
        struct _DOMAIN_INFO *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        void *a4,
        struct _GUID *a5,
        int a6,
        int a7,
        int a8)
{
  char *v12; // rax
  HLOCAL v13; // rbx
  unsigned int v14; // edx
  unsigned int v15; // r8d
  __int64 v16; // rax
  HANDLE Semaphore; // rax
  HANDLE v18; // rax
  HANDLE EventW; // rax
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax
  unsigned __int16 *InstanceName; // r9
  __int64 v22; // rcx
  DWORD dwFlags[2]; // [rsp+20h] [rbp-48h]

  if ( a2 && a2->Length > 0x1Eu )
  {
    NlPrintDomRoutine(0x100u, a1, L"NlAllocateClientSession given too long domain name %wZ\n", a2);
    return 0;
  }
  v12 = (char *)LocalAlloc(0x40u, 560LL * (NlGlobalMaxConcurrentApi - 1) + 1240);
  v13 = v12;
  if ( !v12 )
    return 0;
  *((_DWORD *)v12 + 70) = a7;
  *((_DWORD *)v12 + 73) = a6;
  *((_DWORD *)v12 + 71) = 0;
  *((_DWORD *)v12 + 82) = 1;
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v12 + 344));
  v14 = 0;
  v15 = NlGlobalMaxConcurrentApi;
  *((_DWORD *)v13 + 74) = a8;
  *((_QWORD *)v13 + 49) = 0;
  *((_QWORD *)v13 + 50) = 0;
  *((_DWORD *)v13 + 72) = -1073741730;
  *((_QWORD *)v13 + 34) = a1;
  *((_QWORD *)v13 + 1) = v13;
  *(_QWORD *)v13 = v13;
  *((_QWORD *)v13 + 9) = NlDcDiscoveryWorker;
  *((_QWORD *)v13 + 10) = v13;
  *((_BYTE *)v13 + 88) = 0;
  if ( v15 )
  {
    do
    {
      v16 = v14++;
      *((_DWORD *)v13 + 140 * v16 + 172) = -1;
    }
    while ( v14 < v15 );
  }
  if ( !(unsigned int)NlSetNamesClientSession((struct _CLIENT_SESSION *)v13, a2, a3, a4, a5)
    || (Semaphore = CreateSemaphoreExW(0, 1, 1, 0, 0, 0x1F0003u), (*((_QWORD *)v13 + 42) = Semaphore) == 0)
    || NlGlobalMaxConcurrentApi > 1
    && (v18 = CreateSemaphoreExW(0, NlGlobalMaxConcurrentApi - 1, NlGlobalMaxConcurrentApi - 1, 0, 0, 0x1F0003u),
        (*((_QWORD *)v13 + 83) = v18) == 0)
    || a7 != 2 && (EventW = CreateEventW(0, 1, 0, 0), (*((_QWORD *)v13 + 52) = EventW) == 0) )
  {
    NlUnrefClientSession(v13);
    return 0;
  }
  if ( hDataSource_PerfCntr_1 && *((_QWORD *)v13 + 63) )
  {
    RtlAcquireResourceExclusive(&NlPcGlobalLock, 1u);
    Instance = PerfCreateInstance(
                 hDataSource_PerfCntr_1,
                 &CtrSet_PerfCntr_1_1Guid,
                 *((PCWSTR *)v13 + 63),
                 _InterlockedIncrement((volatile signed __int32 *)&NlPcGlobalInstanceNumber));
    *((_QWORD *)v13 + 84) = Instance;
    if ( Instance )
    {
      InstanceName = NlPcGetInstanceName(Instance);
      NlPrintRoutine(
        0x8000u,
        L"NlAllocateClientSession: New Perf Instance (%p): \"%ws\"\n    ClientSession: %p\n",
        v22,
        InstanceName,
        v13);
    }
    else
    {
      dwFlags[0] = GetLastError();
      NlPrintRoutine(
        0x8000u,
        L"NlAllocateClientSession: Could not create new perf instance: \"%ws\"\n"
         "    ClientSession = %p\n"
         "    Error = %d\n",
        *((_QWORD *)v13 + 63),
        v13,
        *(_QWORD *)dwFlags);
    }
    RtlReleaseResource(&NlPcGlobalLock);
  }
  else
  {
    *((_QWORD *)v13 + 84) = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x180063f6c  push    rbx
0x180063f6e  push    rbp
0x180063f6f  push    rsi
0x180063f70  push    rdi
0x180063f71  push    r13
0x180063f73  push    r14
0x180063f75  push    r15
0x180063f77  sub     rsp, 30h
0x180063f7b  mov     r14, r9
0x180063f7e  mov     r15, r8
0x180063f81  mov     rdi, rdx
0x180063f84  mov     rsi, rcx
0x180063f87  test    rdx, rdx
0x180063f8a  jz      short loc_180063FAE
0x180063f8c  cmp     word ptr [rdx], 1Eh
0x180063f90  jbe     short loc_180063FAE
0x180063f92  mov     r9, rdx
0x180063f95  lea     r8, aNlallocateclie_4; "NlAllocateClientSession given too long "...
0x180063f9c  mov     rdx, rcx; struct _DOMAIN_INFO *
0x180063f9f  mov     ecx, 100h; unsigned int
0x180063fa4  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180063fa9  jmp     loc_180064210
0x180063fae  mov     ecx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x180063fb4  dec     ecx
0x180063fb6  imul    rdx, rcx, 230h
0x180063fbd  mov     ecx, 40h ; '@'; uFlags
0x180063fc2  add     rdx, 4D8h; uBytes
0x180063fc9  call    cs:__imp_LocalAlloc
0x180063fcf  mov     rbx, rax
0x180063fd2  test    rax, rax
0x180063fd5  jz      loc_180064210
0x180063fdb  mov     ebp, [rsp+68h+arg_30]
0x180063fe2  lea     rcx, [rbx+158h]; CriticalSection
0x180063fe9  mov     [rax+118h], ebp
0x180063fef  mov     r13d, 1
0x180063ff5  mov     eax, [rsp+68h+arg_28]
0x180063ffc  mov     [rbx+124h], eax
0x180064002  mov     dword ptr [rbx+11Ch], 0
0x18006400c  mov     [rbx+148h], r13d
0x180064013  call    cs:__imp_RtlInitializeCriticalSection
0x180064019  mov     eax, [rsp+68h+arg_38]
0x180064020  xor     edx, edx
0x180064022  mov     r8d, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x180064029  mov     [rbx+128h], eax
0x18006402f  lea     rax, ?NlDcDiscoveryWorker@@YAXPEAX@Z; NlDcDiscoveryWorker(void *)
0x180064036  mov     qword ptr [rbx+188h], 0
0x180064041  mov     qword ptr [rbx+190h], 0
0x18006404c  mov     dword ptr [rbx+120h], 0C000005Eh
0x180064056  mov     [rbx+110h], rsi
0x18006405d  mov     [rbx+8], rbx
0x180064061  mov     [rbx], rbx
0x180064064  mov     [rbx+48h], rax
0x180064068  mov     [rbx+50h], rbx
0x18006406c  mov     byte ptr [rbx+58h], 0
0x180064070  test    r8d, r8d
0x180064073  jz      short loc_180064091
0x180064075  mov     eax, edx
0x180064077  add     edx, r13d
0x18006407a  imul    rcx, rax, 230h
0x180064081  mov     dword ptr [rcx+rbx+2B0h], 0FFFFFFFFh
0x18006408c  cmp     edx, r8d
0x18006408f  jb      short loc_180064075
0x180064091  mov     rax, [rsp+68h+arg_20]
0x180064099  mov     r9, r14; Src
0x18006409c  mov     r8, r15; struct _UNICODE_STRING *
0x18006409f  mov     qword ptr [rsp+68h+dwFlags], rax; struct _GUID *
0x1800640a4  mov     rdx, rdi; struct _UNICODE_STRING *
0x1800640a7  mov     rcx, rbx; struct _CLIENT_SESSION *
0x1800640aa  call    ?NlSetNamesClientSession@@YAHPEAU_CLIENT_SESSION@@PEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@@Z; NlSetNamesClientSession(_CLIENT_SESSION *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *)
0x1800640af  test    eax, eax
0x1800640b1  jz      loc_180064208
0x1800640b7  mov     edi, 1F0003h
0x1800640bc  xor     r9d, r9d; lpName
0x1800640bf  mov     [rsp+68h+dwDesiredAccess], edi; dwDesiredAccess
0x1800640c3  mov     r8d, r13d; lMaximumCount
0x1800640c6  mov     edx, r13d; lInitialCount
0x1800640c9  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800640d1  xor     ecx, ecx; lpSemaphoreAttributes
0x1800640d3  call    cs:__imp_CreateSemaphoreExW
0x1800640d9  mov     [rbx+150h], rax
0x1800640e0  test    rax, rax
0x1800640e3  jz      loc_180064208
0x1800640e9  mov     edx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x1800640ef  cmp     edx, r13d
0x1800640f2  jbe     short loc_180064120
0x1800640f4  dec     edx; lInitialCount
0x1800640f6  mov     [rsp+68h+dwDesiredAccess], edi; dwDesiredAccess
0x1800640fa  mov     r8d, edx; lMaximumCount
0x1800640fd  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180064105  xor     r9d, r9d; lpName
0x180064108  xor     ecx, ecx; lpSemaphoreAttributes
0x18006410a  call    cs:__imp_CreateSemaphoreExW
0x180064110  mov     [rbx+298h], rax
0x180064117  test    rax, rax
0x18006411a  jz      loc_180064208
0x180064120  cmp     ebp, 2
0x180064123  jz      short loc_180064146
0x180064125  xor     r9d, r9d; lpName
0x180064128  xor     r8d, r8d; bInitialState
0x18006412b  mov     edx, r13d; bManualReset
0x18006412e  xor     ecx, ecx; lpEventAttributes
0x180064130  call    cs:__imp_CreateEventW
0x180064136  mov     [rbx+1A0h], rax
0x18006413d  test    rax, rax
0x180064140  jz      loc_180064208
0x180064146  cmp     cs:hDataSource_PerfCntr_1, 0
0x18006414e  jz      loc_1800641F8
0x180064154  cmp     qword ptr [rbx+1F8h], 0
0x18006415c  jz      loc_1800641F8
0x180064162  mov     dl, r13b; Wait
0x180064165  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x18006416c  call    cs:__imp_RtlAcquireResourceExclusive
0x180064172  mov     r9d, r13d
0x180064175  lock xadd cs:?NlPcGlobalInstanceNumber@@3KA, r9d; ulong NlPcGlobalInstanceNumber
0x18006417e  mov     r8, [rbx+1F8h]; Name
0x180064185  lea     rdx, CtrSet_PerfCntr_1_1Guid; CounterSetGuid
0x18006418c  mov     rcx, cs:hDataSource_PerfCntr_1; ProviderHandle
0x180064193  add     r9d, r13d; Id
0x180064196  call    cs:__imp_PerfCreateInstance
0x18006419c  mov     [rbx+2A0h], rax
0x1800641a3  mov     rcx, rax; struct _PERF_COUNTERSET_INSTANCE *
0x1800641a6  test    rax, rax
0x1800641a9  jz      short loc_1800641C4
0x1800641ab  call    ?NlPcGetInstanceName@@YAPEAGPEAU_PERF_COUNTERSET_INSTANCE@@@Z; NlPcGetInstanceName(_PERF_COUNTERSET_INSTANCE *)
0x1800641b0  mov     r9, rax
0x1800641b3  mov     qword ptr [rsp+68h+dwFlags], rbx
0x1800641b8  mov     r8, rcx
0x1800641bb  lea     rdx, aNlallocateclie_1; "NlAllocateClientSession: New Perf Insta"...
0x1800641c2  jmp     short loc_1800641DF
0x1800641c4  call    cs:__imp_GetLastError
0x1800641ca  mov     r8, [rbx+1F8h]
0x1800641d1  lea     rdx, aNlallocateclie; "NlAllocateClientSession: Could not crea"...
0x1800641d8  mov     [rsp+68h+dwFlags], eax
0x1800641dc  mov     r9, rbx
0x1800641df  mov     ecx, 8000h; unsigned int
0x1800641e4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800641e9  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x1800641f0  call    cs:__imp_RtlReleaseResource
0x1800641f6  jmp     short loc_180064203
0x1800641f8  mov     qword ptr [rbx+2A0h], 0
0x180064203  mov     rax, rbx
0x180064206  jmp     short loc_180064212
0x180064208  mov     rcx, rbx; hMem
0x18006420b  call    ?NlUnrefClientSession@@YAXPEAU_CLIENT_SESSION@@@Z; NlUnrefClientSession(_CLIENT_SESSION *)
0x180064210  xor     eax, eax
0x180064212  add     rsp, 30h
0x180064216  pop     r15
0x180064218  pop     r14
0x18006421a  pop     r13
0x18006421c  pop     rdi
0x18006421d  pop     rsi
0x18006421e  pop     rbp
0x18006421f  pop     rbx
0x180064220  retn
```
