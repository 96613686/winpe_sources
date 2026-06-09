# NlAllocateClientApi(_CLIENT_SESSION *,ulong,uchar *)

- ea: `0x1800685c4`
- end: `0x180068914`
- name: `?NlAllocateClientApi@@YAPEAU_CLIENT_API@@PEAU_CLIENT_SESSION@@KPEAE@Z`
- size: `848`
- prototype: `struct _CLIENT_API *__fastcall(struct _CLIENT_SESSION *, DWORD dwMilliseconds, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180031a3c`

## callees

- `0x18000dd00`
- `0x180040f18`
- `0x180053274`
- `0x180053360`
- `0x18005342c`
- `0x1800534ec`
- `0x1800685c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800686c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800686c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006876b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006876b`
- `ntdll!RtlAcquireResourceShared` at `0x180068638`
- `ntdll!RtlAcquireResourceShared` at `0x1800686da`
- `ntdll!RtlAcquireResourceShared` at `0x180068638`
- `ntdll!RtlAcquireResourceShared` at `0x1800686da`
- `ntdll!RtlLeaveCriticalSection` at `0x18006889f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800688c1`
- `ntdll!RtlLeaveCriticalSection` at `0x18006889f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800688c1`
- `ntdll!RtlEnterCriticalSection` at `0x18006885b`
- `ntdll!RtlEnterCriticalSection` at `0x18006885b`
- `ntdll!RtlReleaseResource` at `0x1800686ad`
- `ntdll!RtlReleaseResource` at `0x1800687cd`
- `ntdll!RtlReleaseResource` at `0x180068840`
- `ntdll!RtlReleaseResource` at `0x1800686ad`
- `ntdll!RtlReleaseResource` at `0x1800687cd`
- `ntdll!RtlReleaseResource` at `0x180068840`

## string_xrefs

- `0x1800685e8`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180068711`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180068754`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x1800688d3`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180068718`: `(LONG) NlPcReadCounter32(ClientSession->CsPerfData, NLPC_Waiters) >= 0`
- `0x18006875b`: `(LONG) NlPcReadCounter32(NlPcGlobalTotalInstance, NLPC_Waiters) >= 0`

## pseudocode

```c
struct _CLIENT_API *__fastcall NlAllocateClientApi(
        struct _CLIENT_SESSION *a1,
        DWORD dwMilliseconds,
        unsigned __int8 *a3,
        char *a4)
{
  __int64 v7; // r14
  int v8; // eax
  char v9; // si
  DWORD v10; // ebp
  char *v11; // r9
  char *v12; // r9
  DWORD LastError; // eax
  int v15; // eax
  unsigned int i; // ecx
  __int64 v17; // rdi
  int v18; // eax
  char *v19; // r9

  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0x588u,
      a4);
  if ( NlGlobalMaxConcurrentApi == 1 || !NlGlobalWinsockPnpAddresses && !NlGlobalV6WinsockPnpAddresses )
    return (struct _CLIENT_SESSION *)((char *)a1 + 680);
  if ( a3 )
    *a3 = 1;
  RtlAcquireResourceShared(&NlPcGlobalLock, 1u);
  v7 = *(_QWORD *)(*((_QWORD *)a1 + 34) + 352LL);
  v8 = NlPcIncrement32(*((_QWORD *)a1 + 84), 0);
  if ( !*((_QWORD *)a1 + 84) || (v9 = 1, v8) )
  {
    NlPrintCsRoutine(0x200u, a1, L"Failed to increment waiters: 0x%p 0x%08x\n");
    v9 = 0;
  }
  NlPcIncrement32(v7, 0);
  NlPcIncrement32(NlPcGlobalTotalInstance, 0);
  RtlReleaseResource(&NlPcGlobalLock);
  v10 = WaitForSingleObject(*((HANDLE *)a1 + 83), dwMilliseconds);
  RtlAcquireResourceShared(&NlPcGlobalLock, 1u);
  if ( v9 )
  {
    NlPcDecrement32(*((_QWORD *)a1 + 84), 0);
    if ( (int)NlPcReadCounter32(*((_QWORD *)a1 + 84), 0) < 0 )
      NlAssertFailed(
        "(LONG) NlPcReadCounter32(ClientSession->CsPerfData, NLPC_Waiters) >= 0",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
        0x5B9u,
        v11);
  }
  NlPcDecrement32(v7, 0);
  NlPcDecrement32(NlPcGlobalTotalInstance, 0);
  if ( (int)NlPcReadCounter32(NlPcGlobalTotalInstance, 0) < 0 )
    NlAssertFailed(
      "(LONG) NlPcReadCounter32(NlPcGlobalTotalInstance, NLPC_Waiters) >= 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0x5BDu,
      v12);
  if ( v10 )
  {
    LastError = GetLastError();
    NlPrintCsRoutine(0x100u, a1, L"NlAllocateClientApi timed out: %ld %ld\n", LastError, v10);
    NlPcIncrement64(*((_QWORD *)a1 + 84), 3, 1);
    NlPcIncrement64(v7, 3, 1);
    NlPcIncrement64(NlPcGlobalTotalInstance, 3, 1);
    RtlReleaseResource(&NlPcGlobalLock);
  }
  else
  {
    v15 = NlPcIncrement32(*((_QWORD *)a1 + 84), 1);
    if ( !*((_QWORD *)a1 + 84) || v15 )
    {
      NlPrintCsRoutine(0x200u, a1, L"Failed to increment holders: 0x%p 0x%08x\n");
      if ( a3 )
        *a3 = 0;
    }
    NlPcIncrement32(v7, 1);
    NlPcIncrement32(NlPcGlobalTotalInstance, 1);
    RtlReleaseResource(&NlPcGlobalLock);
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    for ( i = 1; i < NlGlobalMaxConcurrentApi; ++i )
    {
      v17 = 560LL * i;
      v18 = *(_DWORD *)((char *)a1 + v17 + 704);
      if ( (v18 & 8) == 0 )
      {
        *(_DWORD *)((char *)a1 + v17 + 704) = v18 | 8;
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
        return (struct _CLIENT_SESSION *)((char *)a1 + v17 + 680);
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    NlAssertFailed("FALSE", "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx", 0x5F5u, v19);
    NlPrintCsRoutine(0x100u, a1, L"NlAllocateClientApi all entries are in use. (This can't happen)\n");
  }
  return 0;
}

```

## disassembly

```asm
0x1800685c4  push    rbx
0x1800685c6  push    rbp
0x1800685c7  push    rsi
0x1800685c8  push    rdi
0x1800685c9  push    r12
0x1800685cb  push    r14
0x1800685cd  sub     rsp, 38h
0x1800685d1  cmp     dword ptr [rcx+148h], 0
0x1800685d8  mov     rdi, r8
0x1800685db  mov     ebp, edx
0x1800685dd  mov     rbx, rcx
0x1800685e0  ja      short loc_1800685FB
0x1800685e2  mov     r8d, 588h; unsigned int
0x1800685e8  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800685ef  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x1800685f6  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800685fb  mov     r12d, 1
0x180068601  cmp     cs:?NlGlobalMaxConcurrentApi@@3KA, r12d; ulong NlGlobalMaxConcurrentApi
0x180068608  jz      loc_1800688FF
0x18006860e  cmp     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, 0; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180068616  jnz     short loc_180068626
0x180068618  cmp     cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, 0; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x180068620  jz      loc_1800688FF
0x180068626  test    rdi, rdi
0x180068629  jz      short loc_18006862E
0x18006862b  mov     [rdi], r12b
0x18006862e  mov     dl, r12b; Wait
0x180068631  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180068638  call    cs:__imp_RtlAcquireResourceShared
0x18006863f  nop     dword ptr [rax+rax+00h]
0x180068644  mov     rax, [rbx+110h]
0x18006864b  xor     edx, edx
0x18006864d  mov     rcx, [rbx+2A0h]
0x180068654  mov     r14, [rax+160h]
0x18006865b  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180068660  mov     r9, [rbx+2A0h]
0x180068667  test    r9, r9
0x18006866a  jz      short loc_180068673
0x18006866c  mov     sil, r12b
0x18006866f  test    eax, eax
0x180068671  jz      short loc_18006868E
0x180068673  lea     r8, aFailedToIncrem_0; "Failed to increment waiters: 0x%p 0x%08"...
0x18006867a  mov     [rsp+68h+var_48], eax
0x18006867e  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180068681  mov     ecx, 200h; unsigned int
0x180068686  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006868b  xor     sil, sil
0x18006868e  xor     edx, edx
0x180068690  mov     rcx, r14
0x180068693  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180068698  mov     rcx, cs:?NlPcGlobalTotalInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; _PERF_COUNTERSET_INSTANCE * NlPcGlobalTotalInstance
0x18006869f  xor     edx, edx
0x1800686a1  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x1800686a6  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x1800686ad  call    cs:__imp_RtlReleaseResource
0x1800686b4  nop     dword ptr [rax+rax+00h]
0x1800686b9  mov     rcx, [rbx+298h]; hHandle
0x1800686c0  mov     edx, ebp; dwMilliseconds
0x1800686c2  call    cs:__imp_WaitForSingleObject
0x1800686c9  nop     dword ptr [rax+rax+00h]
0x1800686ce  mov     dl, r12b; Wait
0x1800686d1  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x1800686d8  mov     ebp, eax
0x1800686da  call    cs:__imp_RtlAcquireResourceShared
0x1800686e1  nop     dword ptr [rax+rax+00h]
0x1800686e6  test    sil, sil
0x1800686e9  jz      short loc_180068724
0x1800686eb  mov     rcx, [rbx+2A0h]
0x1800686f2  xor     edx, edx
0x1800686f4  call    ?NlPcDecrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcDecrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x1800686f9  mov     rcx, [rbx+2A0h]
0x180068700  xor     edx, edx
0x180068702  call    ?NlPcReadCounter32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@@Z; NlPcReadCounter32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS)
0x180068707  test    eax, eax
0x180068709  jns     short loc_180068724
0x18006870b  mov     r8d, 5B9h; unsigned int
0x180068711  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180068718  lea     rcx, aLongNlpcreadco; "(LONG) NlPcReadCounter32(ClientSession-"...
0x18006871f  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180068724  xor     edx, edx
0x180068726  mov     rcx, r14
0x180068729  call    ?NlPcDecrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcDecrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x18006872e  mov     rcx, cs:?NlPcGlobalTotalInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; _PERF_COUNTERSET_INSTANCE * NlPcGlobalTotalInstance
0x180068735  xor     edx, edx
0x180068737  call    ?NlPcDecrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcDecrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x18006873c  mov     rcx, cs:?NlPcGlobalTotalInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; _PERF_COUNTERSET_INSTANCE * NlPcGlobalTotalInstance
0x180068743  xor     edx, edx
0x180068745  call    ?NlPcReadCounter32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@@Z; NlPcReadCounter32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS)
0x18006874a  test    eax, eax
0x18006874c  jns     short loc_180068767
0x18006874e  mov     r8d, 5BDh; unsigned int
0x180068754  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006875b  lea     rcx, aLongNlpcreadco_2; "(LONG) NlPcReadCounter32(NlPcGlobalTota"...
0x180068762  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180068767  test    ebp, ebp
0x180068769  jz      short loc_1800687E0
0x18006876b  call    cs:__imp_GetLastError
0x180068772  nop     dword ptr [rax+rax+00h]
0x180068777  lea     r8, aNlallocateclie_2; "NlAllocateClientApi timed out: %ld %ld"...
0x18006877e  mov     [rsp+68h+var_48], ebp
0x180068782  mov     r9d, eax
0x180068785  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180068788  mov     ecx, 100h; unsigned int
0x18006878d  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068792  mov     rcx, [rbx+2A0h]
0x180068799  mov     edi, 3
0x18006879e  mov     edx, edi
0x1800687a0  mov     r8, r12
0x1800687a3  call    ?NlPcIncrement64@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@_K@Z; NlPcIncrement64(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,unsigned __int64)
0x1800687a8  mov     r8, r12
0x1800687ab  mov     edx, edi
0x1800687ad  mov     rcx, r14
0x1800687b0  call    ?NlPcIncrement64@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@_K@Z; NlPcIncrement64(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,unsigned __int64)
0x1800687b5  mov     rcx, cs:?NlPcGlobalTotalInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; _PERF_COUNTERSET_INSTANCE * NlPcGlobalTotalInstance
0x1800687bc  mov     r8, r12
0x1800687bf  mov     edx, edi
0x1800687c1  call    ?NlPcIncrement64@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@_K@Z; NlPcIncrement64(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,unsigned __int64)
0x1800687c6  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x1800687cd  call    cs:__imp_RtlReleaseResource
0x1800687d4  nop     dword ptr [rax+rax+00h]
0x1800687d9  xor     eax, eax
0x1800687db  jmp     loc_180068906
0x1800687e0  mov     rcx, [rbx+2A0h]
0x1800687e7  mov     edx, r12d
0x1800687ea  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x1800687ef  mov     r9, [rbx+2A0h]
0x1800687f6  test    r9, r9
0x1800687f9  jz      short loc_1800687FF
0x1800687fb  test    eax, eax
0x1800687fd  jz      short loc_18006881F
0x1800687ff  lea     r8, aFailedToIncrem; "Failed to increment holders: 0x%p 0x%08"...
0x180068806  mov     [rsp+68h+var_48], eax
0x18006880a  mov     rdx, rbx; struct _CLIENT_SESSION *
0x18006880d  mov     ecx, 200h; unsigned int
0x180068812  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068817  test    rdi, rdi
0x18006881a  jz      short loc_18006881F
0x18006881c  mov     byte ptr [rdi], 0
0x18006881f  mov     edx, r12d
0x180068822  mov     rcx, r14
0x180068825  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x18006882a  mov     rcx, cs:?NlPcGlobalTotalInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; _PERF_COUNTERSET_INSTANCE * NlPcGlobalTotalInstance
0x180068831  mov     edx, r12d
0x180068834  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180068839  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180068840  call    cs:__imp_RtlReleaseResource
0x180068847  nop     dword ptr [rax+rax+00h]
0x18006884c  mov     rcx, [rbx+110h]
0x180068853  mov     esi, 190h
0x180068858  add     rcx, rsi; CriticalSection
0x18006885b  call    cs:__imp_RtlEnterCriticalSection
0x180068862  nop     dword ptr [rax+rax+00h]
0x180068867  mov     ecx, r12d
0x18006886a  cmp     ecx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x180068870  jnb     short loc_1800688B7
0x180068872  mov     eax, ecx
0x180068874  imul    rdi, rax, 230h
0x18006887b  mov     eax, [rdi+rbx+2C0h]
0x180068882  test    al, 8
0x180068884  jz      short loc_18006888B
0x180068886  add     ecx, r12d
0x180068889  jmp     short loc_18006886A
0x18006888b  or      eax, 8
0x18006888e  mov     [rdi+rbx+2C0h], eax
0x180068895  mov     rcx, [rbx+110h]
0x18006889c  add     rcx, rsi; CriticalSection
0x18006889f  call    cs:__imp_RtlLeaveCriticalSection
0x1800688a6  nop     dword ptr [rax+rax+00h]
0x1800688ab  lea     rax, [rbx+2A8h]
0x1800688b2  add     rax, rdi
0x1800688b5  jmp     short loc_180068906
0x1800688b7  mov     rcx, [rbx+110h]
0x1800688be  add     rcx, rsi; CriticalSection
0x1800688c1  call    cs:__imp_RtlLeaveCriticalSection
0x1800688c8  nop     dword ptr [rax+rax+00h]
0x1800688cd  mov     r8d, 5F5h; unsigned int
0x1800688d3  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800688da  lea     rcx, aFalse; "FALSE"
0x1800688e1  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800688e6  lea     r8, aNlallocateclie_3; "NlAllocateClientApi all entries are in "...
0x1800688ed  mov     rdx, rbx; struct _CLIENT_SESSION *
0x1800688f0  mov     ecx, 100h; unsigned int
0x1800688f5  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800688fa  jmp     loc_1800687D9
0x1800688ff  lea     rax, [rbx+2A8h]
0x180068906  add     rsp, 38h
0x18006890a  pop     r14
0x18006890c  pop     r12
0x18006890e  pop     rdi
0x18006890f  pop     rsi
0x180068910  pop     rbp
0x180068911  pop     rbx
0x180068912  retn
```
