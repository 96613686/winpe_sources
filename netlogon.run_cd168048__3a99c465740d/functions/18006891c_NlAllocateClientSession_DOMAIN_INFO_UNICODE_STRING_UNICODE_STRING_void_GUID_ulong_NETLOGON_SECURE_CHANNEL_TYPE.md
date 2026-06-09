# NlAllocateClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *,ulong,_NETLOGON_SECURE_CHANNEL_TYPE,ulong)

- ea: `0x18006891c`
- end: `0x180068c08`
- name: `?NlAllocateClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@KW4_NETLOGON_SECURE_CHANNEL_TYPE@@K@Z`
- size: `748`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180027fa4`
- `0x180029218`
- `0x180056bac`
- `0x18006f6b0`

## callees

- `0x180007518`
- `0x18000c440`
- `0x18000e0e0`
- `0x180053344`
- `0x18006891c`
- `0x18006c784`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180068a8f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180068acc`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180068a8f`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x180068acc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180068af8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180068af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068b9e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068979`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068979`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180068b6a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180068b6a`
- `ntdll!RtlAcquireResourceExclusive` at `0x180068b3a`
- `ntdll!RtlAcquireResourceExclusive` at `0x180068b3a`
- `ntdll!RtlInitializeCriticalSection` at `0x1800689c9`
- `ntdll!RtlInitializeCriticalSection` at `0x1800689c9`
- `ntdll!RtlReleaseResource` at `0x180068bd0`
- `ntdll!RtlReleaseResource` at `0x180068bd0`

## string_xrefs

- `0x180068bb1`: `NlAllocateClientSession: Could not create new perf instance: "%ws"\n    ClientSession = %p\n    Error = %d\n`

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
0x18006891c  push    rbx
0x18006891e  push    rbp
0x18006891f  push    rsi
0x180068920  push    rdi
0x180068921  push    r13
0x180068923  push    r14
0x180068925  push    r15
0x180068927  sub     rsp, 30h
0x18006892b  mov     r14, r9
0x18006892e  mov     r15, r8
0x180068931  mov     rdi, rdx
0x180068934  mov     rsi, rcx
0x180068937  test    rdx, rdx
0x18006893a  jz      short loc_18006895E
0x18006893c  cmp     word ptr [rdx], 1Eh
0x180068940  jbe     short loc_18006895E
0x180068942  mov     r9, rdx
0x180068945  lea     r8, aNlallocateclie_4; "NlAllocateClientSession given too long "...
0x18006894c  mov     rdx, rcx; struct _DOMAIN_INFO *
0x18006894f  mov     ecx, 100h; unsigned int
0x180068954  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180068959  jmp     loc_180068BF6
0x18006895e  mov     ecx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x180068964  dec     ecx
0x180068966  imul    rdx, rcx, 230h
0x18006896d  mov     ecx, 40h ; '@'; uFlags
0x180068972  add     rdx, 4D8h; uBytes
0x180068979  call    cs:__imp_LocalAlloc
0x180068980  nop     dword ptr [rax+rax+00h]
0x180068985  mov     rbx, rax
0x180068988  test    rax, rax
0x18006898b  jz      loc_180068BF6
0x180068991  mov     ebp, [rsp+68h+arg_30]
0x180068998  lea     rcx, [rbx+158h]; CriticalSection
0x18006899f  mov     [rax+118h], ebp
0x1800689a5  mov     r13d, 1
0x1800689ab  mov     eax, [rsp+68h+arg_28]
0x1800689b2  mov     [rbx+124h], eax
0x1800689b8  mov     dword ptr [rbx+11Ch], 0
0x1800689c2  mov     [rbx+148h], r13d
0x1800689c9  call    cs:__imp_RtlInitializeCriticalSection
0x1800689d0  nop     dword ptr [rax+rax+00h]
0x1800689d5  mov     eax, [rsp+68h+arg_38]
0x1800689dc  xor     edx, edx
0x1800689de  mov     r8d, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x1800689e5  mov     [rbx+128h], eax
0x1800689eb  lea     rax, ?NlDcDiscoveryWorker@@YAXPEAX@Z; NlDcDiscoveryWorker(void *)
0x1800689f2  mov     qword ptr [rbx+188h], 0
0x1800689fd  mov     qword ptr [rbx+190h], 0
0x180068a08  mov     dword ptr [rbx+120h], 0C000005Eh
0x180068a12  mov     [rbx+110h], rsi
0x180068a19  mov     [rbx+8], rbx
0x180068a1d  mov     [rbx], rbx
0x180068a20  mov     [rbx+48h], rax
0x180068a24  mov     [rbx+50h], rbx
0x180068a28  mov     byte ptr [rbx+58h], 0
0x180068a2c  test    r8d, r8d
0x180068a2f  jz      short loc_180068A4D
0x180068a31  mov     eax, edx
0x180068a33  add     edx, r13d
0x180068a36  imul    rcx, rax, 230h
0x180068a3d  mov     dword ptr [rcx+rbx+2B0h], 0FFFFFFFFh
0x180068a48  cmp     edx, r8d
0x180068a4b  jb      short loc_180068A31
0x180068a4d  mov     rax, [rsp+68h+arg_20]
0x180068a55  mov     r9, r14; Src
0x180068a58  mov     r8, r15; struct _UNICODE_STRING *
0x180068a5b  mov     qword ptr [rsp+68h+dwFlags], rax; struct _GUID *
0x180068a60  mov     rdx, rdi; struct _UNICODE_STRING *
0x180068a63  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180068a66  call    ?NlSetNamesClientSession@@YAHPEAU_CLIENT_SESSION@@PEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@@Z; NlSetNamesClientSession(_CLIENT_SESSION *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *)
0x180068a6b  test    eax, eax
0x180068a6d  jz      loc_180068BEE
0x180068a73  mov     edi, 1F0003h
0x180068a78  xor     r9d, r9d; lpName
0x180068a7b  mov     [rsp+68h+dwDesiredAccess], edi; dwDesiredAccess
0x180068a7f  mov     r8d, r13d; lMaximumCount
0x180068a82  mov     edx, r13d; lInitialCount
0x180068a85  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180068a8d  xor     ecx, ecx; lpSemaphoreAttributes
0x180068a8f  call    cs:__imp_CreateSemaphoreExW
0x180068a96  nop     dword ptr [rax+rax+00h]
0x180068a9b  mov     [rbx+150h], rax
0x180068aa2  test    rax, rax
0x180068aa5  jz      loc_180068BEE
0x180068aab  mov     edx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x180068ab1  cmp     edx, r13d
0x180068ab4  jbe     short loc_180068AE8
0x180068ab6  dec     edx; lInitialCount
0x180068ab8  mov     [rsp+68h+dwDesiredAccess], edi; dwDesiredAccess
0x180068abc  mov     r8d, edx; lMaximumCount
0x180068abf  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180068ac7  xor     r9d, r9d; lpName
0x180068aca  xor     ecx, ecx; lpSemaphoreAttributes
0x180068acc  call    cs:__imp_CreateSemaphoreExW
0x180068ad3  nop     dword ptr [rax+rax+00h]
0x180068ad8  mov     [rbx+298h], rax
0x180068adf  test    rax, rax
0x180068ae2  jz      loc_180068BEE
0x180068ae8  cmp     ebp, 2
0x180068aeb  jz      short loc_180068B14
0x180068aed  xor     r9d, r9d; lpName
0x180068af0  xor     r8d, r8d; bInitialState
0x180068af3  mov     edx, r13d; bManualReset
0x180068af6  xor     ecx, ecx; lpEventAttributes
0x180068af8  call    cs:__imp_CreateEventW
0x180068aff  nop     dword ptr [rax+rax+00h]
0x180068b04  mov     [rbx+1A0h], rax
0x180068b0b  test    rax, rax
0x180068b0e  jz      loc_180068BEE
0x180068b14  cmp     cs:hDataSource_PerfCntr_1, 0
0x180068b1c  jz      loc_180068BDE
0x180068b22  cmp     qword ptr [rbx+1F8h], 0
0x180068b2a  jz      loc_180068BDE
0x180068b30  mov     dl, r13b; Wait
0x180068b33  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180068b3a  call    cs:__imp_RtlAcquireResourceExclusive
0x180068b41  nop     dword ptr [rax+rax+00h]
0x180068b46  mov     r9d, r13d
0x180068b49  lock xadd cs:?NlPcGlobalInstanceNumber@@3KA, r9d; ulong NlPcGlobalInstanceNumber
0x180068b52  mov     r8, [rbx+1F8h]; Name
0x180068b59  lea     rdx, CtrSet_PerfCntr_1_1Guid; CounterSetGuid
0x180068b60  mov     rcx, cs:hDataSource_PerfCntr_1; ProviderHandle
0x180068b67  add     r9d, r13d; Id
0x180068b6a  call    cs:__imp_PerfCreateInstance
0x180068b71  nop     dword ptr [rax+rax+00h]
0x180068b76  mov     [rbx+2A0h], rax
0x180068b7d  mov     rcx, rax; struct _PERF_COUNTERSET_INSTANCE *
0x180068b80  test    rax, rax
0x180068b83  jz      short loc_180068B9E
0x180068b85  call    ?NlPcGetInstanceName@@YAPEAGPEAU_PERF_COUNTERSET_INSTANCE@@@Z; NlPcGetInstanceName(_PERF_COUNTERSET_INSTANCE *)
0x180068b8a  mov     r9, rax
0x180068b8d  mov     qword ptr [rsp+68h+dwFlags], rbx
0x180068b92  mov     r8, rcx
0x180068b95  lea     rdx, aNlallocateclie_1; "NlAllocateClientSession: New Perf Insta"...
0x180068b9c  jmp     short loc_180068BBF
0x180068b9e  call    cs:__imp_GetLastError
0x180068ba5  nop     dword ptr [rax+rax+00h]
0x180068baa  mov     r8, [rbx+1F8h]
0x180068bb1  lea     rdx, aNlallocateclie; "NlAllocateClientSession: Could not crea"...
0x180068bb8  mov     [rsp+68h+dwFlags], eax
0x180068bbc  mov     r9, rbx
0x180068bbf  mov     ecx, 8000h; unsigned int
0x180068bc4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180068bc9  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180068bd0  call    cs:__imp_RtlReleaseResource
0x180068bd7  nop     dword ptr [rax+rax+00h]
0x180068bdc  jmp     short loc_180068BE9
0x180068bde  mov     qword ptr [rbx+2A0h], 0
0x180068be9  mov     rax, rbx
0x180068bec  jmp     short loc_180068BF8
0x180068bee  mov     rcx, rbx; hMem
0x180068bf1  call    ?NlUnrefClientSession@@YAXPEAU_CLIENT_SESSION@@@Z; NlUnrefClientSession(_CLIENT_SESSION *)
0x180068bf6  xor     eax, eax
0x180068bf8  add     rsp, 30h
0x180068bfc  pop     r15
0x180068bfe  pop     r14
0x180068c00  pop     r13
0x180068c02  pop     rdi
0x180068c03  pop     rsi
0x180068c04  pop     rbp
0x180068c05  pop     rbx
0x180068c06  retn
```
