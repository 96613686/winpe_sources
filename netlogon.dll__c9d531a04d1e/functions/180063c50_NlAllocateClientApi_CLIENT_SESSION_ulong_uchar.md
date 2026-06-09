# NlAllocateClientApi(_CLIENT_SESSION *,ulong,uchar *)

- ea: `0x180063c50`
- end: `0x180063f63`
- name: `?NlAllocateClientApi@@YAPEAU_CLIENT_API@@PEAU_CLIENT_SESSION@@KPEAE@Z`
- size: `787`
- prototype: `struct _CLIENT_API *__fastcall(struct _CLIENT_SESSION *, DWORD dwMilliseconds, unsigned __int8 *, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002fdb4`

## callees

- `0x18000d710`
- `0x18003e71c`
- `0x18004fb50`
- `0x18004fc34`
- `0x18004fcf8`
- `0x18004fdb0`
- `0x180063c50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180063d42`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180063d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063ddf`
- `ntdll!RtlAcquireResourceShared` at `0x180063cc4`
- `ntdll!RtlAcquireResourceShared` at `0x180063d54`
- `ntdll!RtlAcquireResourceShared` at `0x180063cc4`
- `ntdll!RtlAcquireResourceShared` at `0x180063d54`
- `ntdll!RtlLeaveCriticalSection` at `0x180063efb`
- `ntdll!RtlLeaveCriticalSection` at `0x180063f17`
- `ntdll!RtlLeaveCriticalSection` at `0x180063efb`
- `ntdll!RtlLeaveCriticalSection` at `0x180063f17`
- `ntdll!RtlEnterCriticalSection` at `0x180063ebd`
- `ntdll!RtlEnterCriticalSection` at `0x180063ebd`
- `ntdll!RtlReleaseResource` at `0x180063d33`
- `ntdll!RtlReleaseResource` at `0x180063e3b`
- `ntdll!RtlReleaseResource` at `0x180063ea8`
- `ntdll!RtlReleaseResource` at `0x180063d33`
- `ntdll!RtlReleaseResource` at `0x180063e3b`
- `ntdll!RtlReleaseResource` at `0x180063ea8`

## string_xrefs

- `0x180063c74`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180063d85`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180063dc8`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180063f23`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180063d8c`: `(LONG) NlPcReadCounter32(ClientSession->CsPerfData, NLPC_Waiters) >= 0`
- `0x180063dcf`: `(LONG) NlPcReadCounter32(NlPcGlobalTotalInstance, NLPC_Waiters) >= 0`

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
0x180063c50  push    rbx
0x180063c52  push    rbp
0x180063c53  push    rsi
0x180063c54  push    rdi
0x180063c55  push    r12
0x180063c57  push    r14
0x180063c59  sub     rsp, 38h
0x180063c5d  cmp     dword ptr [rcx+148h], 0
0x180063c64  mov     rdi, r8
0x180063c67  mov     ebp, edx
0x180063c69  mov     rbx, rcx
0x180063c6c  ja      short loc_180063C87
0x180063c6e  mov     r8d, 588h; unsigned int
0x180063c74  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180063c7b  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180063c82  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180063c87  mov     r12d, 1
0x180063c8d  cmp     cs:?NlGlobalMaxConcurrentApi@@3KA, r12d; ulong NlGlobalMaxConcurrentApi
0x180063c94  jz      loc_180063F4F
0x180063c9a  cmp     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, 0; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180063ca2  jnz     short loc_180063CB2
0x180063ca4  cmp     cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, 0; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x180063cac  jz      loc_180063F4F
0x180063cb2  test    rdi, rdi
0x180063cb5  jz      short loc_180063CBA
0x180063cb7  mov     [rdi], r12b
0x180063cba  mov     dl, r12b; Wait
0x180063cbd  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180063cc4  call    cs:__imp_RtlAcquireResourceShared
0x180063cca  mov     rax, [rbx+110h]
0x180063cd1  xor     edx, edx
0x180063cd3  mov     rcx, [rbx+2A0h]
0x180063cda  mov     r14, [rax+160h]
0x180063ce1  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180063ce6  mov     r9, [rbx+2A0h]
0x180063ced  test    r9, r9
0x180063cf0  jz      short loc_180063CF9
0x180063cf2  mov     sil, r12b
0x180063cf5  test    eax, eax
0x180063cf7  jz      short loc_180063D14
0x180063cf9  lea     r8, aFailedToIncrem_0; "Failed to increment waiters: 0x%p 0x%08"...
0x180063d00  mov     [rsp+68h+var_48], eax
0x180063d04  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180063d07  mov     ecx, 200h; unsigned int
0x180063d0c  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180063d11  xor     sil, sil
0x180063d14  xor     edx, edx
0x180063d16  mov     rcx, r14
0x180063d19  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180063d1e  mov     rcx, cs:?NlPcGlobalTotalInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; _PERF_COUNTERSET_INSTANCE * NlPcGlobalTotalInstance
0x180063d25  xor     edx, edx
0x180063d27  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180063d2c  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180063d33  call    cs:__imp_RtlReleaseResource
0x180063d39  mov     rcx, [rbx+298h]; hHandle
0x180063d40  mov     edx, ebp; dwMilliseconds
0x180063d42  call    cs:__imp_WaitForSingleObject
0x180063d48  mov     dl, r12b; Wait
0x180063d4b  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180063d52  mov     ebp, eax
0x180063d54  call    cs:__imp_RtlAcquireResourceShared
0x180063d5a  test    sil, sil
0x180063d5d  jz      short loc_180063D98
0x180063d5f  mov     rcx, [rbx+2A0h]
0x180063d66  xor     edx, edx
0x180063d68  call    ?NlPcDecrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcDecrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180063d6d  mov     rcx, [rbx+2A0h]
0x180063d74  xor     edx, edx
0x180063d76  call    ?NlPcReadCounter32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@@Z; NlPcReadCounter32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS)
0x180063d7b  test    eax, eax
0x180063d7d  jns     short loc_180063D98
0x180063d7f  mov     r8d, 5B9h; unsigned int
0x180063d85  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180063d8c  lea     rcx, aLongNlpcreadco; "(LONG) NlPcReadCounter32(ClientSession-"...
0x180063d93  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180063d98  xor     edx, edx
0x180063d9a  mov     rcx, r14
0x180063d9d  call    ?NlPcDecrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcDecrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180063da2  mov     rcx, cs:?NlPcGlobalTotalInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; _PERF_COUNTERSET_INSTANCE * NlPcGlobalTotalInstance
0x180063da9  xor     edx, edx
0x180063dab  call    ?NlPcDecrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcDecrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180063db0  mov     rcx, cs:?NlPcGlobalTotalInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; _PERF_COUNTERSET_INSTANCE * NlPcGlobalTotalInstance
0x180063db7  xor     edx, edx
0x180063db9  call    ?NlPcReadCounter32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@@Z; NlPcReadCounter32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS)
0x180063dbe  test    eax, eax
0x180063dc0  jns     short loc_180063DDB
0x180063dc2  mov     r8d, 5BDh; unsigned int
0x180063dc8  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180063dcf  lea     rcx, aLongNlpcreadco_2; "(LONG) NlPcReadCounter32(NlPcGlobalTota"...
0x180063dd6  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180063ddb  test    ebp, ebp
0x180063ddd  jz      short loc_180063E48
0x180063ddf  call    cs:__imp_GetLastError
0x180063de5  lea     r8, aNlallocateclie_2; "NlAllocateClientApi timed out: %ld %ld"...
0x180063dec  mov     [rsp+68h+var_48], ebp
0x180063df0  mov     r9d, eax
0x180063df3  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180063df6  mov     ecx, 100h; unsigned int
0x180063dfb  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180063e00  mov     rcx, [rbx+2A0h]
0x180063e07  mov     edi, 3
0x180063e0c  mov     edx, edi
0x180063e0e  mov     r8, r12
0x180063e11  call    ?NlPcIncrement64@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@_K@Z; NlPcIncrement64(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,unsigned __int64)
0x180063e16  mov     r8, r12
0x180063e19  mov     edx, edi
0x180063e1b  mov     rcx, r14
0x180063e1e  call    ?NlPcIncrement64@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@_K@Z; NlPcIncrement64(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,unsigned __int64)
0x180063e23  mov     rcx, cs:?NlPcGlobalTotalInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; _PERF_COUNTERSET_INSTANCE * NlPcGlobalTotalInstance
0x180063e2a  mov     r8, r12
0x180063e2d  mov     edx, edi
0x180063e2f  call    ?NlPcIncrement64@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@_K@Z; NlPcIncrement64(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,unsigned __int64)
0x180063e34  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180063e3b  call    cs:__imp_RtlReleaseResource
0x180063e41  xor     eax, eax
0x180063e43  jmp     loc_180063F56
0x180063e48  mov     rcx, [rbx+2A0h]
0x180063e4f  mov     edx, r12d
0x180063e52  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180063e57  mov     r9, [rbx+2A0h]
0x180063e5e  test    r9, r9
0x180063e61  jz      short loc_180063E67
0x180063e63  test    eax, eax
0x180063e65  jz      short loc_180063E87
0x180063e67  lea     r8, aFailedToIncrem; "Failed to increment holders: 0x%p 0x%08"...
0x180063e6e  mov     [rsp+68h+var_48], eax
0x180063e72  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180063e75  mov     ecx, 200h; unsigned int
0x180063e7a  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180063e7f  test    rdi, rdi
0x180063e82  jz      short loc_180063E87
0x180063e84  mov     byte ptr [rdi], 0
0x180063e87  mov     edx, r12d
0x180063e8a  mov     rcx, r14
0x180063e8d  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180063e92  mov     rcx, cs:?NlPcGlobalTotalInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA; _PERF_COUNTERSET_INSTANCE * NlPcGlobalTotalInstance
0x180063e99  mov     edx, r12d
0x180063e9c  call    ?NlPcIncrement32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcIncrement32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x180063ea1  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180063ea8  call    cs:__imp_RtlReleaseResource
0x180063eae  mov     rcx, [rbx+110h]
0x180063eb5  mov     esi, 190h
0x180063eba  add     rcx, rsi; CriticalSection
0x180063ebd  call    cs:__imp_RtlEnterCriticalSection
0x180063ec3  mov     ecx, r12d
0x180063ec6  cmp     ecx, cs:?NlGlobalMaxConcurrentApi@@3KA; ulong NlGlobalMaxConcurrentApi
0x180063ecc  jnb     short loc_180063F0D
0x180063ece  mov     eax, ecx
0x180063ed0  imul    rdi, rax, 230h
0x180063ed7  mov     eax, [rdi+rbx+2C0h]
0x180063ede  test    al, 8
0x180063ee0  jz      short loc_180063EE7
0x180063ee2  add     ecx, r12d
0x180063ee5  jmp     short loc_180063EC6
0x180063ee7  or      eax, 8
0x180063eea  mov     [rdi+rbx+2C0h], eax
0x180063ef1  mov     rcx, [rbx+110h]
0x180063ef8  add     rcx, rsi; CriticalSection
0x180063efb  call    cs:__imp_RtlLeaveCriticalSection
0x180063f01  lea     rax, [rbx+2A8h]
0x180063f08  add     rax, rdi
0x180063f0b  jmp     short loc_180063F56
0x180063f0d  mov     rcx, [rbx+110h]
0x180063f14  add     rcx, rsi; CriticalSection
0x180063f17  call    cs:__imp_RtlLeaveCriticalSection
0x180063f1d  mov     r8d, 5F5h; unsigned int
0x180063f23  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180063f2a  lea     rcx, aFalse; "FALSE"
0x180063f31  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180063f36  lea     r8, aNlallocateclie_3; "NlAllocateClientApi all entries are in "...
0x180063f3d  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180063f40  mov     ecx, 100h; unsigned int
0x180063f45  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180063f4a  jmp     loc_180063E41
0x180063f4f  lea     rax, [rbx+2A8h]
0x180063f56  add     rsp, 38h
0x180063f5a  pop     r14
0x180063f5c  pop     r12
0x180063f5e  pop     rdi
0x180063f5f  pop     rsi
0x180063f60  pop     rbp
0x180063f61  pop     rbx
0x180063f62  retn
```
