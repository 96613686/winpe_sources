# NlSetServerClientSession(_CLIENT_SESSION *,_NL_DC_CACHE_ENTRY *,int,int)

- ea: `0x180067df0`
- end: `0x180068452`
- name: `?NlSetServerClientSession@@YAKPEAU_CLIENT_SESSION@@PEAU_NL_DC_CACHE_ENTRY@@HH@Z`
- size: `1634`
- prototype: `unsigned int __fastcall(struct _CLIENT_SESSION *, struct _NL_DC_CACHE_ENTRY *, int, int)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027d78`
- `0x180057aec`
- `0x18005b7e0`
- `0x180064834`

## callees

- `0x180007278`
- `0x18000d710`
- `0x18000ed34`
- `0x18003e71c`
- `0x18004fc18`
- `0x18004fdb0`
- `0x18004fe34`
- `0x180067df0`
- `0x180070544`
- `0x18008315c`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067fb0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067fc8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067fb0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180067fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800682d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800682d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800683d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800683e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800683f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800683d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800683e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800683f7`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180068245`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x180068245`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800682a9`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800682a9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800681a8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800681a8`
- `ntdll!RtlLeaveCriticalSection` at `0x180068118`
- `ntdll!RtlLeaveCriticalSection` at `0x180068404`
- `ntdll!RtlLeaveCriticalSection` at `0x180068435`
- `ntdll!RtlLeaveCriticalSection` at `0x180068118`
- `ntdll!RtlLeaveCriticalSection` at `0x180068404`
- `ntdll!RtlLeaveCriticalSection` at `0x180068435`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006818c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006818c`
- `ntdll!RtlEnterCriticalSection` at `0x180067f11`
- `ntdll!RtlEnterCriticalSection` at `0x1800680f9`
- `ntdll!RtlEnterCriticalSection` at `0x180067f11`
- `ntdll!RtlEnterCriticalSection` at `0x1800680f9`
- `ntdll!RtlReleaseResource` at `0x18006837e`
- `ntdll!RtlReleaseResource` at `0x18006837e`
- `netutils!NetApiBufferFree` at `0x180068125`
- `netutils!NetApiBufferFree` at `0x180068413`
- `netutils!NetApiBufferFree` at `0x180068125`
- `netutils!NetApiBufferFree` at `0x180068413`
- `netutils!NetApiBufferAllocate` at `0x180067f8f`
- `netutils!NetApiBufferAllocate` at `0x180067f8f`
- `netutils!NetpwNameCompare` at `0x1800680a2`
- `netutils!NetpwNameCompare` at `0x1800680a2`

## string_xrefs

- `0x180067e61`: `ClientSession->CsFlags & CS_WRITER`
- `0x180067e13`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x1800681ff`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006833c`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180068054`: `NlSetServerClientSession: New DC runs the time service: %ws\n`
- `0x18006825a`: `NlSetServerClientSession: Delete successful.\n`
- `0x18006826b`: `NlSetServerClientSession: Could not delete old perf instance: Status = %d\n`
- `0x1800682e4`: `NlAllocateClientSession: Could not create new perf instance: "%ws"\nClientSession = %p\n    Error = %d\n`

## pseudocode

```c
__int64 __fastcall NlSetServerClientSession(
        struct _CLIENT_SESSION *a1,
        struct _NL_DC_CACHE_ENTRY *a2,
        int a3,
        char *a4)
{
  int v4; // r12d
  int v7; // r15d
  __int64 v8; // rbx
  int v9; // r8d
  char *v10; // rcx
  int v11; // eax
  int v12; // r15d
  __int64 v13; // rax
  DWORD v14; // r13d
  DWORD v15; // esi
  unsigned int v16; // esi
  unsigned __int16 *v17; // r8
  __int64 v18; // rcx
  int v19; // ebx
  const WCHAR *InstanceName; // rax
  char *v21; // r9
  ULONG v22; // esi
  unsigned int Counter32; // r15d
  char *v24; // r9
  unsigned int v25; // r12d
  unsigned __int16 *v26; // rax
  __int64 v27; // rcx
  ULONG v28; // eax
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax
  unsigned __int16 *v30; // r9
  __int64 v31; // rcx
  unsigned __int16 *v32; // rax
  __int64 v33; // rcx
  int v34; // eax
  char *v35; // rcx
  __int64 v37; // [rsp+20h] [rbp-10h]
  LPVOID Buffer; // [rsp+70h] [rbp+40h] BYREF
  int v39; // [rsp+80h] [rbp+50h]
  int v40; // [rsp+88h] [rbp+58h]

  v40 = (int)a4;
  v39 = a3;
  v4 = (int)a4;
  Buffer = 0;
  v7 = 0;
  v8 = 0;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      5231,
      a4);
  if ( v4 )
  {
    if ( (*((_BYTE *)a1 + 292) & 8) != 0 )
      goto LABEL_18;
    v9 = 5238;
    v10 = "ClientSession->CsFlags & CS_WRITER";
    goto LABEL_17;
  }
  if ( *((_DWORD *)a1 + 71) )
    NlAssertFailed(
      "ClientSession->CsState == CS_IDLE",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      5244,
      a4);
  if ( *((_QWORD *)a1 + 63) )
    NlAssertFailed(
      "ClientSession->CsUncServerName == NULL",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      5245,
      a4);
  if ( *((_DWORD *)a1 + 130) )
    NlAssertFailed(
      "ClientSession->CsServerSockAddr.iSockaddrLength == 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      5246,
      a4);
  if ( *((_QWORD *)a1 + 57) )
    NlAssertFailed(
      "ClientSession->ClientAuthData == NULL",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      5247,
      a4);
  if ( *((_QWORD *)a1 + 59) || *((_QWORD *)a1 + 58) )
  {
    v9 = 5248;
    v10 = "ClientSession->CsCredHandle.dwUpper == 0 && ClientSession->CsCredHandle.dwLower == 0";
LABEL_17:
    NlAssertFailed(v10, "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx", v9, a4);
  }
LABEL_18:
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  v11 = *((_DWORD *)a2 + 67);
  if ( (v11 & 2) != 0 )
  {
    if ( *((_QWORD *)a2 + 10) )
    {
      v8 = *((_QWORD *)a2 + 10);
      v7 = 256;
    }
    else if ( *((_QWORD *)a2 + 9) )
    {
      v8 = *((_QWORD *)a2 + 9);
    }
    v12 = v7 | 0x40;
  }
  else
  {
    if ( (v11 & 1) == 0 )
    {
LABEL_85:
      NlPrintRoutine(0x100u, L"NlSetServerClientSession: Invalid data\n");
      v15 = 13;
LABEL_86:
      RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
      return v15;
    }
    if ( *((_QWORD *)a2 + 9) )
    {
      v8 = *((_QWORD *)a2 + 9);
    }
    else if ( *((_QWORD *)a2 + 10) )
    {
      v8 = *((_QWORD *)a2 + 10);
      v7 = 256;
    }
    v12 = v7 | 0x20;
  }
  if ( !v8 )
    goto LABEL_85;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(v8 + 2 * v13) );
  v14 = 2 * v13 + 6;
  v15 = NetApiBufferAllocate(v14, &Buffer);
  if ( v15 )
    goto LABEL_86;
  _o_wcscpy_s(Buffer, (unsigned __int64)v14 >> 1);
  _o_wcscpy_s((char *)Buffer + 4, (unsigned __int64)(v14 - 2) >> 1);
  v16 = v12 | 0x10;
  if ( !*((_DWORD *)a2 + 24) )
    v16 = v12;
  if ( (*((_BYTE *)a2 + 264) & 0x10) != 0 )
  {
    v16 |= 4u;
    NlPrintCsRoutine(0x80000u, a1, L"NlSetServerClientSession: New DC is an NT 5 DC: %ws\n", Buffer);
  }
  if ( *((_QWORD *)a2 + 30) && *((_QWORD *)a2 + 31) )
  {
    if ( *((char *)a2 + 264) >= 0 )
      goto LABEL_44;
    v17 = L"NlSetServerClientSession: New DC is in closest site: %ws\n";
  }
  else
  {
    v17 = L"NlSetServerClientSession: New DC site isn't known (assume closest site): %ws\n";
  }
  v16 |= 8u;
  NlPrintCsRoutine(0x80000u, a1, v17, Buffer);
LABEL_44:
  if ( (*((_BYTE *)a2 + 264) & 0x40) != 0 )
  {
    v16 |= 0x80u;
    NlPrintCsRoutine(0x80000u, a1, L"NlSetServerClientSession: New DC runs the time service: %ws\n", Buffer);
  }
  v18 = *((_QWORD *)a1 + 63);
  if ( !v18 )
    goto LABEL_54;
  if ( (*((_DWORD *)a1 + 102) & 0x100) != 0 )
  {
    if ( (v16 & 0x100) != 0
      && (unsigned int)NlEqualDnsName((const unsigned __int16 *)(v18 + 4), (const unsigned __int16 *)Buffer + 2) )
    {
      goto LABEL_54;
    }
  }
  else if ( (v16 & 0x100) == 0 && !(unsigned int)NetpwNameCompare(v18 + 4, (char *)Buffer + 4, 4) )
  {
    goto LABEL_54;
  }
  NlPrintCsRoutine(
    0x200u,
    a1,
    L"NlSetServerClientSession: New DC name: %ws; Old DC name: %ws\n",
    Buffer,
    *((_QWORD *)a1 + 63));
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 344));
  NlLogTimeoutRecurringEvents(a1);
  *((_QWORD *)a1 + 49) = 0;
  *((_QWORD *)a1 + 50) = 0;
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 344));
  NetApiBufferFree(*((LPVOID *)a1 + 63));
  *((_QWORD *)a1 + 63) = 0;
LABEL_54:
  v19 = *((_DWORD *)a1 + 102) & 0x1FC;
  if ( v19 != v16 )
  {
    LODWORD(v37) = *((_DWORD *)a1 + 102) & 0x1FC;
    NlPrintCsRoutine(
      0x80000u,
      a1,
      L"NlSetServerClientSession: New discovery flags: 0x%lx; Old flags: 0x%lx\n",
      v16,
      v37);
    *((_DWORD *)a1 + 102) = v16 | *((_DWORD *)a1 + 102) & ~v19;
  }
  if ( !*((_QWORD *)a1 + 63) )
  {
    *((_QWORD *)a1 + 63) = Buffer;
    Buffer = 0;
  }
  RtlAcquireResourceExclusive(&NlPcGlobalLock, 1u);
  InstanceName = NlPcGetInstanceName(*((struct _PERF_COUNTERSET_INSTANCE **)a1 + 84));
  if ( lstrcmpW(InstanceName, *((LPCWSTR *)a1 + 63)) )
  {
    v22 = 0;
    Counter32 = NlPcReadCounter32(*((_QWORD *)a1 + 84), 1);
    v25 = NlPcReadCounter32(*((_QWORD *)a1 + 84), 0);
    if ( *((_QWORD *)a1 + 84) )
    {
      if ( !hDataSource_PerfCntr_1 )
        NlAssertFailed(
          "NLPC_HPROVIDER != NULL",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
          5510,
          v24);
      v26 = NlPcGetInstanceName(*((struct _PERF_COUNTERSET_INSTANCE **)a1 + 84));
      NlPrintRoutine(
        0x8000u,
        L"NlSetServerClientSession: Connection changing (%p): \"%ws\"\n    ClientSession: %p",
        v27,
        v26,
        a1);
      v28 = PerfDeleteInstance(hDataSource_PerfCntr_1, *((PPERF_COUNTERSET_INSTANCE *)a1 + 84));
      *((_QWORD *)a1 + 84) = 0;
      v22 = v28;
      if ( v28 )
        NlPrintRoutine(0x8000u, L"NlSetServerClientSession: Could not delete old perf instance: Status = %d\n", v28);
      else
        NlPrintRoutine(0x8000u, L"NlSetServerClientSession: Delete successful.\n");
    }
    if ( hDataSource_PerfCntr_1 && !v22 )
    {
      Instance = PerfCreateInstance(
                   hDataSource_PerfCntr_1,
                   &CtrSet_PerfCntr_1_1Guid,
                   *((PCWSTR *)a1 + 63),
                   _InterlockedIncrement((volatile signed __int32 *)&NlPcGlobalInstanceNumber));
      *((_QWORD *)a1 + 84) = Instance;
      if ( Instance )
      {
        v30 = NlPcGetInstanceName(Instance);
        NlPrintRoutine(
          0x8000u,
          L"NlAllocateClientSession: New Perf Instance (%p): \"%ws\"\n    ClientSession: %p\n",
          v31,
          v30,
          a1);
      }
      else
      {
        LODWORD(v37) = GetLastError();
        NlPrintRoutine(
          0x8000u,
          L"NlAllocateClientSession: Could not create new perf instance: \"%ws\"\nClientSession = %p\n    Error = %d\n",
          *((_QWORD *)a1 + 63),
          a1,
          v37);
      }
    }
    NlPcWriteCounter32(*((_QWORD *)a1 + 84), 0, v25);
    NlPcWriteCounter32(*((_QWORD *)a1 + 84), 1, Counter32);
    v4 = v40;
  }
  else if ( *((_QWORD *)a1 + 84) )
  {
    if ( !hDataSource_PerfCntr_1 )
      NlAssertFailed(
        "NLPC_HPROVIDER != NULL",
        "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
        5654,
        v21);
    v32 = NlPcGetInstanceName(*((struct _PERF_COUNTERSET_INSTANCE **)a1 + 84));
    NlPrintRoutine(
      0x8000u,
      L"NlSetServerClientSession: Not changing connection (%p): \"%ws\"\n    ClientSession: %p",
      v33,
      v32,
      a1);
  }
  RtlReleaseResource(&NlPcGlobalLock);
  v34 = *((_DWORD *)a2 + 24);
  v35 = (char *)a1 + 528;
  if ( v34 )
  {
    *((_DWORD *)a1 + 130) = v34;
    *((_QWORD *)a1 + 64) = v35;
    memcpy_0(v35, *((const void **)a2 + 11), *((int *)a2 + 24));
  }
  else
  {
    *((_OWORD *)a1 + 32) = 0;
    memset_0(v35, 0, 0x80u);
  }
  if ( !v4 )
  {
    *((_QWORD *)a1 + 2) = 0;
    GetSystemTimeAsFileTime((LPFILETIME)a1 + 3);
    if ( v39 )
      GetSystemTimeAsFileTime((LPFILETIME)a1 + 4);
    *((_DWORD *)a1 + 71) = 1;
  }
  GetSystemTimeAsFileTime((LPFILETIME)a1 + 5);
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  if ( Buffer )
    NetApiBufferFree(Buffer);
  return 0;
}

```

## disassembly

```asm
0x180067df0  mov     [rsp-38h+arg_8], rbx
0x180067df5  mov     [rsp-38h+arg_18], r9d
0x180067dfa  mov     [rsp-38h+arg_10], r8d
0x180067dff  push    rbp
0x180067e00  push    rsi
0x180067e01  push    rdi
0x180067e02  push    r12
0x180067e04  push    r13
0x180067e06  push    r14
0x180067e08  push    r15
0x180067e0a  mov     rbp, rsp
0x180067e0d  sub     rsp, 30h
0x180067e11  xor     esi, esi
0x180067e13  lea     r13, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180067e1a  mov     r12d, r9d
0x180067e1d  mov     r14, rdx
0x180067e20  mov     rdi, rcx
0x180067e23  mov     [rbp+Buffer], rsi
0x180067e27  mov     r15d, esi
0x180067e2a  mov     ebx, esi
0x180067e2c  cmp     [rcx+148h], esi
0x180067e32  ja      short loc_180067E49
0x180067e34  mov     r8d, 146Fh; unsigned int
0x180067e3a  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180067e41  mov     rdx, r13; void *
0x180067e44  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180067e49  test    r12d, r12d
0x180067e4c  jz      short loc_180067E6D
0x180067e4e  test    byte ptr [rdi+124h], 8
0x180067e55  jnz     loc_180067F0A
0x180067e5b  mov     r8d, 1476h
0x180067e61  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x180067e68  jmp     loc_180067F02
0x180067e6d  cmp     [rdi+11Ch], esi
0x180067e73  jz      short loc_180067E8A
0x180067e75  mov     r8d, 147Ch; unsigned int
0x180067e7b  lea     rcx, aClientsessionC_10; "ClientSession->CsState == CS_IDLE"
0x180067e82  mov     rdx, r13; void *
0x180067e85  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180067e8a  cmp     [rdi+1F8h], rsi
0x180067e91  jz      short loc_180067EA8
0x180067e93  mov     r8d, 147Dh; unsigned int
0x180067e99  lea     rcx, aClientsessionC; "ClientSession->CsUncServerName == NULL"
0x180067ea0  mov     rdx, r13; void *
0x180067ea3  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180067ea8  cmp     [rdi+208h], esi
0x180067eae  jz      short loc_180067EC5
0x180067eb0  mov     r8d, 147Eh; unsigned int
0x180067eb6  lea     rcx, aClientsessionC_0; "ClientSession->CsServerSockAddr.iSockad"...
0x180067ebd  mov     rdx, r13; void *
0x180067ec0  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180067ec5  cmp     [rdi+1C8h], rsi
0x180067ecc  jz      short loc_180067EE3
0x180067ece  mov     r8d, 147Fh; unsigned int
0x180067ed4  lea     rcx, aClientsessionC_8; "ClientSession->ClientAuthData == NULL"
0x180067edb  mov     rdx, r13; void *
0x180067ede  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180067ee3  cmp     [rdi+1D8h], rsi
0x180067eea  jnz     short loc_180067EF5
0x180067eec  cmp     [rdi+1D0h], rsi
0x180067ef3  jz      short loc_180067F0A
0x180067ef5  mov     r8d, 1480h; unsigned int
0x180067efb  lea     rcx, aClientsessionC_11; "ClientSession->CsCredHandle.dwUpper == "...
0x180067f02  mov     rdx, r13; void *
0x180067f05  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180067f0a  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180067f11  call    cs:__imp_RtlEnterCriticalSection
0x180067f17  mov     eax, [r14+10Ch]
0x180067f1e  mov     ecx, 100h; unsigned int
0x180067f23  test    al, 2
0x180067f25  jz      short loc_180067F45
0x180067f27  cmp     [r14+50h], rsi
0x180067f2b  jz      short loc_180067F36
0x180067f2d  mov     rbx, [r14+50h]
0x180067f31  mov     r15d, ecx
0x180067f34  jmp     short loc_180067F3F
0x180067f36  cmp     [r14+48h], rsi
0x180067f3a  cmovnz  rbx, [r14+48h]
0x180067f3f  or      r15d, 40h
0x180067f43  jmp     short loc_180067F6A
0x180067f45  test    al, 1
0x180067f47  jz      loc_18006841D
0x180067f4d  cmp     [r14+48h], rsi
0x180067f51  jz      short loc_180067F59
0x180067f53  mov     rbx, [r14+48h]
0x180067f57  jmp     short loc_180067F66
0x180067f59  cmp     [r14+50h], rsi
0x180067f5d  jz      short loc_180067F66
0x180067f5f  mov     rbx, [r14+50h]
0x180067f63  mov     r15d, ecx
0x180067f66  or      r15d, 20h
0x180067f6a  test    rbx, rbx
0x180067f6d  jz      loc_18006841D
0x180067f73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180067f77  inc     rax
0x180067f7a  cmp     [rbx+rax*2], si
0x180067f7e  jnz     short loc_180067F77
0x180067f80  lea     r13d, ds:6[rax*2]
0x180067f88  mov     ecx, r13d; ByteCount
0x180067f8b  lea     rdx, [rbp+Buffer]; Buffer
0x180067f8f  call    cs:__imp_NetApiBufferAllocate
0x180067f95  mov     esi, eax
0x180067f97  test    eax, eax
0x180067f99  jnz     loc_18006842E
0x180067f9f  mov     rcx, [rbp+Buffer]
0x180067fa3  lea     r8, String2; "\\\\"
0x180067faa  mov     edx, r13d
0x180067fad  shr     rdx, 1
0x180067fb0  call    cs:__imp__o_wcscpy_s
0x180067fb6  mov     rcx, [rbp+Buffer]
0x180067fba  lea     edx, [r13-2]
0x180067fbe  shr     rdx, 1
0x180067fc1  add     rcx, 4
0x180067fc5  mov     r8, rbx
0x180067fc8  call    cs:__imp__o_wcscpy_s
0x180067fce  mov     esi, r15d
0x180067fd1  xor     r13d, r13d
0x180067fd4  or      esi, 10h
0x180067fd7  cmp     [r14+60h], r13d
0x180067fdb  cmovz   esi, r15d
0x180067fdf  test    byte ptr [r14+108h], 10h
0x180067fe7  mov     r15d, 80000h
0x180067fed  jz      short loc_180068008
0x180067fef  mov     r9, [rbp+Buffer]
0x180067ff3  lea     r8, aNlsetservercli; "NlSetServerClientSession: New DC is an "...
0x180067ffa  or      esi, 4
0x180067ffd  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180068000  mov     ecx, r15d; unsigned int
0x180068003  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068008  cmp     [r14+0F0h], r13
0x18006800f  jz      short loc_18006802D
0x180068011  cmp     [r14+0F8h], r13
0x180068018  jz      short loc_18006802D
0x18006801a  test    byte ptr [r14+108h], 80h
0x180068022  jz      short loc_180068046
0x180068024  lea     r8, aNlsetservercli_2; "NlSetServerClientSession: New DC is in "...
0x18006802b  jmp     short loc_180068034
0x18006802d  lea     r8, aNlsetservercli_7; "NlSetServerClientSession: New DC site i"...
0x180068034  mov     r9, [rbp+Buffer]
0x180068038  or      esi, 8
0x18006803b  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006803e  mov     ecx, r15d; unsigned int
0x180068041  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180068046  test    byte ptr [r14+108h], 40h
0x18006804e  jz      short loc_18006806A
0x180068050  mov     r9, [rbp+Buffer]
0x180068054  lea     r8, aNlsetservercli_4; "NlSetServerClientSession: New DC runs t"...
0x18006805b  bts     esi, 7
0x18006805f  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180068062  mov     ecx, r15d; unsigned int
0x180068065  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006806a  mov     rcx, [rdi+1F8h]
0x180068071  test    rcx, rcx
0x180068074  jz      loc_180068132
0x18006807a  mov     edx, 100h
0x18006807f  mov     eax, esi
0x180068081  and     eax, edx
0x180068083  test    [rdi+198h], edx
0x180068089  jnz     short loc_1800680B2
0x18006808b  test    eax, eax
0x18006808d  jnz     short loc_1800680CB
0x18006808f  mov     rdx, [rbp+Buffer]
0x180068093  lea     r8d, [rax+4]
0x180068097  add     rdx, 4
0x18006809b  add     rcx, 4
0x18006809f  xor     r9d, r9d
0x1800680a2  call    cs:__imp_NetpwNameCompare
0x1800680a8  test    eax, eax
0x1800680aa  jz      loc_180068132
0x1800680b0  jmp     short loc_1800680CB
0x1800680b2  test    eax, eax
0x1800680b4  jz      short loc_1800680CB
0x1800680b6  mov     rdx, [rbp+Buffer]
0x1800680ba  add     rcx, 4; unsigned __int16 *
0x1800680be  add     rdx, 4; unsigned __int16 *
0x1800680c2  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x1800680c7  test    eax, eax
0x1800680c9  jnz     short loc_180068132
0x1800680cb  mov     rax, [rdi+1F8h]
0x1800680d2  lea     r8, aNlsetservercli_9; "NlSetServerClientSession: New DC name: "...
0x1800680d9  mov     r9, [rbp+Buffer]
0x1800680dd  mov     rdx, rdi; struct _CLIENT_SESSION *
0x1800680e0  mov     ecx, 200h; unsigned int
0x1800680e5  mov     [rsp+30h+var_10], rax
0x1800680ea  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800680ef  lea     rbx, [rdi+158h]
0x1800680f6  mov     rcx, rbx; CriticalSection
0x1800680f9  call    cs:__imp_RtlEnterCriticalSection
0x1800680ff  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180068102  call    ?NlLogTimeoutRecurringEvents@@YAXPEAU_CLIENT_SESSION@@@Z; NlLogTimeoutRecurringEvents(_CLIENT_SESSION *)
0x180068107  mov     rcx, rbx; CriticalSection
0x18006810a  mov     [rdi+188h], r13
0x180068111  mov     [rdi+190h], r13
0x180068118  call    cs:__imp_RtlLeaveCriticalSection
0x18006811e  mov     rcx, [rdi+1F8h]; Buffer
0x180068125  call    cs:__imp_NetApiBufferFree
0x18006812b  mov     [rdi+1F8h], r13
0x180068132  mov     ebx, [rdi+198h]
0x180068138  and     ebx, 1FCh
0x18006813e  cmp     ebx, esi
0x180068140  jz      short loc_18006816B
0x180068142  mov     r9d, esi
0x180068145  mov     dword ptr [rsp+30h+var_10], ebx
0x180068149  lea     r8, aNlsetservercli_3; "NlSetServerClientSession: New discovery"...
0x180068150  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180068153  mov     ecx, r15d; unsigned int
0x180068156  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006815b  not     ebx
0x18006815d  and     ebx, [rdi+198h]
0x180068163  or      ebx, esi
0x180068165  mov     [rdi+198h], ebx
0x18006816b  cmp     [rdi+1F8h], r13
0x180068172  jnz     short loc_180068183
0x180068174  mov     rax, [rbp+Buffer]
0x180068178  mov     [rdi+1F8h], rax
0x18006817f  mov     [rbp+Buffer], r13
0x180068183  mov     dl, 1; Wait
0x180068185  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x18006818c  call    cs:__imp_RtlAcquireResourceExclusive
0x180068192  mov     rcx, [rdi+2A0h]; struct _PERF_COUNTERSET_INSTANCE *
0x180068199  call    ?NlPcGetInstanceName@@YAPEAGPEAU_PERF_COUNTERSET_INSTANCE@@@Z; NlPcGetInstanceName(_PERF_COUNTERSET_INSTANCE *)
0x18006819e  mov     rdx, [rdi+1F8h]; lpString2
0x1800681a5  mov     rcx, rax; lpString1
0x1800681a8  call    cs:__imp_lstrcmpW
0x1800681ae  test    eax, eax
0x1800681b0  jz      loc_180068324
0x1800681b6  mov     rcx, [rdi+2A0h]
0x1800681bd  mov     edx, 1
0x1800681c2  mov     esi, r13d
0x1800681c5  call    ?NlPcReadCounter32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@@Z; NlPcReadCounter32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS)
0x1800681ca  mov     rcx, [rdi+2A0h]
0x1800681d1  xor     edx, edx
0x1800681d3  mov     r15d, eax
0x1800681d6  call    ?NlPcReadCounter32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@@Z; NlPcReadCounter32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS)
0x1800681db  mov     r12d, eax
0x1800681de  mov     ebx, 8000h
0x1800681e3  cmp     [rdi+2A0h], r13
0x1800681ea  jz      loc_180068277
0x1800681f0  cmp     cs:hDataSource_PerfCntr_1, r13
0x1800681f7  jnz     short loc_180068212
0x1800681f9  mov     r8d, 1586h; unsigned int
0x1800681ff  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180068206  lea     rcx, aNlpcHproviderN; "NLPC_HPROVIDER != NULL"
0x18006820d  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180068212  mov     rcx, [rdi+2A0h]; struct _PERF_COUNTERSET_INSTANCE *
0x180068219  call    ?NlPcGetInstanceName@@YAPEAGPEAU_PERF_COUNTERSET_INSTANCE@@@Z; NlPcGetInstanceName(_PERF_COUNTERSET_INSTANCE *)
0x18006821e  mov     r8, rcx
0x180068221  mov     [rsp+30h+var_10], rdi
0x180068226  mov     r9, rax
0x180068229  lea     rdx, aNlsetservercli_5; "NlSetServerClientSession: Connection ch"...
0x180068230  mov     ecx, ebx; unsigned int
0x180068232  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180068237  mov     rdx, [rdi+2A0h]; InstanceBlock
0x18006823e  mov     rcx, cs:hDataSource_PerfCntr_1; Provider
0x180068245  call    cs:__imp_PerfDeleteInstance
0x18006824b  mov     [rdi+2A0h], r13
0x180068252  mov     ecx, ebx; unsigned int
0x180068254  mov     esi, eax
0x180068256  test    eax, eax
0x180068258  jnz     short loc_180068268
0x18006825a  lea     rdx, aNlsetservercli_6; "NlSetServerClientSession: Delete succes"...
0x180068261  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180068266  jmp     short loc_180068277
0x180068268  mov     r8d, eax
0x18006826b  lea     rdx, aNlsetservercli_8; "NlSetServerClientSession: Could not del"...
0x180068272  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180068277  cmp     cs:hDataSource_PerfCntr_1, r13
0x18006827e  jz      short loc_1800682F9
0x180068280  test    esi, esi
0x180068282  jnz     short loc_1800682F9
0x180068284  lea     r9d, [rsi+1]
0x180068288  lock xadd cs:?NlPcGlobalInstanceNumber@@3KA, r9d; ulong NlPcGlobalInstanceNumber
0x180068291  mov     r8, [rdi+1F8h]; Name
0x180068298  lea     rdx, CtrSet_PerfCntr_1_1Guid; CounterSetGuid
0x18006829f  mov     rcx, cs:hDataSource_PerfCntr_1; ProviderHandle
0x1800682a6  inc     r9d; Id
0x1800682a9  call    cs:__imp_PerfCreateInstance
0x1800682af  mov     [rdi+2A0h], rax
0x1800682b6  mov     rcx, rax; struct _PERF_COUNTERSET_INSTANCE *
0x1800682b9  test    rax, rax
0x1800682bc  jz      short loc_1800682D7
0x1800682be  call    ?NlPcGetInstanceName@@YAPEAGPEAU_PERF_COUNTERSET_INSTANCE@@@Z; NlPcGetInstanceName(_PERF_COUNTERSET_INSTANCE *)
0x1800682c3  mov     r9, rax
0x1800682c6  mov     [rsp+30h+var_10], rdi
0x1800682cb  mov     r8, rcx
0x1800682ce  lea     rdx, aNlallocateclie_1; "NlAllocateClientSession: New Perf Insta"...
0x1800682d5  jmp     short loc_1800682F2
0x1800682d7  call    cs:__imp_GetLastError
0x1800682dd  mov     r8, [rdi+1F8h]
0x1800682e4  lea     rdx, aNlallocateclie_0; "NlAllocateClientSession: Could not crea"...
0x1800682eb  mov     dword ptr [rsp+30h+var_10], eax
0x1800682ef  mov     r9, rdi
0x1800682f2  mov     ecx, ebx; unsigned int
0x1800682f4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800682f9  mov     rcx, [rdi+2A0h]
0x180068300  mov     r8d, r12d
0x180068303  xor     edx, edx
0x180068305  call    ?NlPcWriteCounter32@@YAXPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@K@Z; NlPcWriteCounter32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS,ulong)
0x18006830a  mov     rcx, [rdi+2A0h]
0x180068311  mov     r8d, r15d
  ... truncated ...
```
