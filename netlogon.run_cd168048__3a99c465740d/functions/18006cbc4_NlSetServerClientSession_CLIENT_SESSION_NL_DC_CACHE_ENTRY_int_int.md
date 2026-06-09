# NlSetServerClientSession(_CLIENT_SESSION *,_NL_DC_CACHE_ENTRY *,int,int)

- ea: `0x18006cbc4`
- end: `0x18006d2a7`
- name: `?NlSetServerClientSession@@YAKPEAU_CLIENT_SESSION@@PEAU_NL_DC_CACHE_ENTRY@@HH@Z`
- size: `1763`
- prototype: `unsigned int __fastcall(struct _CLIENT_SESSION *, struct _NL_DC_CACHE_ENTRY *, int, int)`
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029218`
- `0x18005b9cc`
- `0x18005fa30`
- `0x180069290`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000f3e4`
- `0x180040f18`
- `0x180053344`
- `0x1800534ec`
- `0x180053574`
- `0x18006cbc4`
- `0x180075998`
- `0x1800892fc`
- `0x180090204`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006cd90`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006cdae`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006cd90`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18006cdae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d0fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d0fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d203`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d219`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d233`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d203`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d219`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006d233`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18006d055`
- `api-ms-win-core-perfcounters-l1-1-0!PerfDeleteInstance` at `0x18006d055`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18006d0c7`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18006d0c7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18006cfb2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18006cfb2`
- `ntdll!RtlLeaveCriticalSection` at `0x18006cf10`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d246`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d283`
- `ntdll!RtlLeaveCriticalSection` at `0x18006cf10`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d246`
- `ntdll!RtlLeaveCriticalSection` at `0x18006d283`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006cf90`
- `ntdll!RtlAcquireResourceExclusive` at `0x18006cf90`
- `ntdll!RtlEnterCriticalSection` at `0x18006cce5`
- `ntdll!RtlEnterCriticalSection` at `0x18006ceeb`
- `ntdll!RtlEnterCriticalSection` at `0x18006cce5`
- `ntdll!RtlEnterCriticalSection` at `0x18006ceeb`
- `ntdll!RtlReleaseResource` at `0x18006d1a8`
- `ntdll!RtlReleaseResource` at `0x18006d1a8`
- `netutils!NetApiBufferFree` at `0x18006cf23`
- `netutils!NetApiBufferFree` at `0x18006d25b`
- `netutils!NetApiBufferFree` at `0x18006cf23`
- `netutils!NetApiBufferFree` at `0x18006d25b`
- `netutils!NetApiBufferAllocate` at `0x18006cd69`
- `netutils!NetApiBufferAllocate` at `0x18006cd69`
- `netutils!NetpwNameCompare` at `0x18006ce8e`
- `netutils!NetpwNameCompare` at `0x18006ce8e`

## string_xrefs

- `0x18006cc35`: `ClientSession->CsFlags & CS_WRITER`
- `0x18006cbe7`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006d00f`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006d166`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006ce40`: `NlSetServerClientSession: New DC runs the time service: %ws\n`
- `0x18006d070`: `NlSetServerClientSession: Delete successful.\n`
- `0x18006d081`: `NlSetServerClientSession: Could not delete old perf instance: Status = %d\n`
- `0x18006d10e`: `NlAllocateClientSession: Could not create new perf instance: "%ws"\nClientSession = %p\n    Error = %d\n`

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
  unsigned int v9; // r8d
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
      0x146Fu,
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
      0x147Cu,
      a4);
  if ( *((_QWORD *)a1 + 63) )
    NlAssertFailed(
      "ClientSession->CsUncServerName == NULL",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0x147Du,
      a4);
  if ( *((_DWORD *)a1 + 130) )
    NlAssertFailed(
      "ClientSession->CsServerSockAddr.iSockaddrLength == 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0x147Eu,
      a4);
  if ( *((_QWORD *)a1 + 57) )
    NlAssertFailed(
      "ClientSession->ClientAuthData == NULL",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      0x147Fu,
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
  _o_wcscpy_s(Buffer, (unsigned __int64)v14 >> 1, L"\\\\");
  _o_wcscpy_s((char *)Buffer + 4, (unsigned __int64)(v14 - 2) >> 1, v8);
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
          0x1586u,
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
        0x1616u,
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
0x18006cbc4  mov     [rsp-38h+arg_8], rbx
0x18006cbc9  mov     [rsp-38h+arg_18], r9d
0x18006cbce  mov     [rsp-38h+arg_10], r8d
0x18006cbd3  push    rbp
0x18006cbd4  push    rsi
0x18006cbd5  push    rdi
0x18006cbd6  push    r12
0x18006cbd8  push    r13
0x18006cbda  push    r14
0x18006cbdc  push    r15
0x18006cbde  mov     rbp, rsp
0x18006cbe1  sub     rsp, 30h
0x18006cbe5  xor     esi, esi
0x18006cbe7  lea     r13, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006cbee  mov     r12d, r9d
0x18006cbf1  mov     r14, rdx
0x18006cbf4  mov     rdi, rcx
0x18006cbf7  mov     [rbp+Buffer], rsi
0x18006cbfb  mov     r15d, esi
0x18006cbfe  mov     ebx, esi
0x18006cc00  cmp     [rcx+148h], esi
0x18006cc06  ja      short loc_18006CC1D
0x18006cc08  mov     r8d, 146Fh; unsigned int
0x18006cc0e  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18006cc15  mov     rdx, r13; void *
0x18006cc18  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006cc1d  test    r12d, r12d
0x18006cc20  jz      short loc_18006CC41
0x18006cc22  test    byte ptr [rdi+124h], 8
0x18006cc29  jnz     loc_18006CCDE
0x18006cc2f  mov     r8d, 1476h
0x18006cc35  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x18006cc3c  jmp     loc_18006CCD6
0x18006cc41  cmp     [rdi+11Ch], esi
0x18006cc47  jz      short loc_18006CC5E
0x18006cc49  mov     r8d, 147Ch; unsigned int
0x18006cc4f  lea     rcx, aClientsessionC_10; "ClientSession->CsState == CS_IDLE"
0x18006cc56  mov     rdx, r13; void *
0x18006cc59  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006cc5e  cmp     [rdi+1F8h], rsi
0x18006cc65  jz      short loc_18006CC7C
0x18006cc67  mov     r8d, 147Dh; unsigned int
0x18006cc6d  lea     rcx, aClientsessionC; "ClientSession->CsUncServerName == NULL"
0x18006cc74  mov     rdx, r13; void *
0x18006cc77  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006cc7c  cmp     [rdi+208h], esi
0x18006cc82  jz      short loc_18006CC99
0x18006cc84  mov     r8d, 147Eh; unsigned int
0x18006cc8a  lea     rcx, aClientsessionC_0; "ClientSession->CsServerSockAddr.iSockad"...
0x18006cc91  mov     rdx, r13; void *
0x18006cc94  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006cc99  cmp     [rdi+1C8h], rsi
0x18006cca0  jz      short loc_18006CCB7
0x18006cca2  mov     r8d, 147Fh; unsigned int
0x18006cca8  lea     rcx, aClientsessionC_8; "ClientSession->ClientAuthData == NULL"
0x18006ccaf  mov     rdx, r13; void *
0x18006ccb2  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006ccb7  cmp     [rdi+1D8h], rsi
0x18006ccbe  jnz     short loc_18006CCC9
0x18006ccc0  cmp     [rdi+1D0h], rsi
0x18006ccc7  jz      short loc_18006CCDE
0x18006ccc9  mov     r8d, 1480h; unsigned int
0x18006cccf  lea     rcx, aClientsessionC_11; "ClientSession->CsCredHandle.dwUpper == "...
0x18006ccd6  mov     rdx, r13; void *
0x18006ccd9  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006ccde  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006cce5  call    cs:__imp_RtlEnterCriticalSection
0x18006ccec  nop     dword ptr [rax+rax+00h]
0x18006ccf1  mov     eax, [r14+10Ch]
0x18006ccf8  mov     ecx, 100h; unsigned int
0x18006ccfd  test    al, 2
0x18006ccff  jz      short loc_18006CD1F
0x18006cd01  cmp     [r14+50h], rsi
0x18006cd05  jz      short loc_18006CD10
0x18006cd07  mov     rbx, [r14+50h]
0x18006cd0b  mov     r15d, ecx
0x18006cd0e  jmp     short loc_18006CD19
0x18006cd10  cmp     [r14+48h], rsi
0x18006cd14  cmovnz  rbx, [r14+48h]
0x18006cd19  or      r15d, 40h
0x18006cd1d  jmp     short loc_18006CD44
0x18006cd1f  test    al, 1
0x18006cd21  jz      loc_18006D26B
0x18006cd27  cmp     [r14+48h], rsi
0x18006cd2b  jz      short loc_18006CD33
0x18006cd2d  mov     rbx, [r14+48h]
0x18006cd31  jmp     short loc_18006CD40
0x18006cd33  cmp     [r14+50h], rsi
0x18006cd37  jz      short loc_18006CD40
0x18006cd39  mov     rbx, [r14+50h]
0x18006cd3d  mov     r15d, ecx
0x18006cd40  or      r15d, 20h
0x18006cd44  test    rbx, rbx
0x18006cd47  jz      loc_18006D26B
0x18006cd4d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006cd51  inc     rax
0x18006cd54  cmp     [rbx+rax*2], si
0x18006cd58  jnz     short loc_18006CD51
0x18006cd5a  lea     r13d, ds:6[rax*2]
0x18006cd62  mov     ecx, r13d; ByteCount
0x18006cd65  lea     rdx, [rbp+Buffer]; Buffer
0x18006cd69  call    cs:__imp_NetApiBufferAllocate
0x18006cd70  nop     dword ptr [rax+rax+00h]
0x18006cd75  mov     esi, eax
0x18006cd77  test    eax, eax
0x18006cd79  jnz     loc_18006D27C
0x18006cd7f  mov     rcx, [rbp+Buffer]
0x18006cd83  lea     r8, String2; "\\\\"
0x18006cd8a  mov     edx, r13d
0x18006cd8d  shr     rdx, 1
0x18006cd90  call    cs:__imp__o_wcscpy_s
0x18006cd97  nop     dword ptr [rax+rax+00h]
0x18006cd9c  mov     rcx, [rbp+Buffer]
0x18006cda0  lea     edx, [r13-2]
0x18006cda4  shr     rdx, 1
0x18006cda7  add     rcx, 4
0x18006cdab  mov     r8, rbx
0x18006cdae  call    cs:__imp__o_wcscpy_s
0x18006cdb5  nop     dword ptr [rax+rax+00h]
0x18006cdba  mov     esi, r15d
0x18006cdbd  xor     r13d, r13d
0x18006cdc0  or      esi, 10h
0x18006cdc3  cmp     [r14+60h], r13d
0x18006cdc7  cmovz   esi, r15d
0x18006cdcb  test    byte ptr [r14+108h], 10h
0x18006cdd3  mov     r15d, 80000h
0x18006cdd9  jz      short loc_18006CDF4
0x18006cddb  mov     r9, [rbp+Buffer]
0x18006cddf  lea     r8, aNlsetservercli; "NlSetServerClientSession: New DC is an "...
0x18006cde6  or      esi, 4
0x18006cde9  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006cdec  mov     ecx, r15d; unsigned int
0x18006cdef  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006cdf4  cmp     [r14+0F0h], r13
0x18006cdfb  jz      short loc_18006CE19
0x18006cdfd  cmp     [r14+0F8h], r13
0x18006ce04  jz      short loc_18006CE19
0x18006ce06  test    byte ptr [r14+108h], 80h
0x18006ce0e  jz      short loc_18006CE32
0x18006ce10  lea     r8, aNlsetservercli_2; "NlSetServerClientSession: New DC is in "...
0x18006ce17  jmp     short loc_18006CE20
0x18006ce19  lea     r8, aNlsetservercli_7; "NlSetServerClientSession: New DC site i"...
0x18006ce20  mov     r9, [rbp+Buffer]
0x18006ce24  or      esi, 8
0x18006ce27  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006ce2a  mov     ecx, r15d; unsigned int
0x18006ce2d  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006ce32  test    byte ptr [r14+108h], 40h
0x18006ce3a  jz      short loc_18006CE56
0x18006ce3c  mov     r9, [rbp+Buffer]
0x18006ce40  lea     r8, aNlsetservercli_4; "NlSetServerClientSession: New DC runs t"...
0x18006ce47  bts     esi, 7
0x18006ce4b  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006ce4e  mov     ecx, r15d; unsigned int
0x18006ce51  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006ce56  mov     rcx, [rdi+1F8h]
0x18006ce5d  test    rcx, rcx
0x18006ce60  jz      loc_18006CF36
0x18006ce66  mov     edx, 100h
0x18006ce6b  mov     eax, esi
0x18006ce6d  and     eax, edx
0x18006ce6f  test    [rdi+198h], edx
0x18006ce75  jnz     short loc_18006CEA4
0x18006ce77  test    eax, eax
0x18006ce79  jnz     short loc_18006CEBD
0x18006ce7b  mov     rdx, [rbp+Buffer]
0x18006ce7f  lea     r8d, [rax+4]
0x18006ce83  add     rdx, 4
0x18006ce87  add     rcx, 4
0x18006ce8b  xor     r9d, r9d
0x18006ce8e  call    cs:__imp_NetpwNameCompare
0x18006ce95  nop     dword ptr [rax+rax+00h]
0x18006ce9a  test    eax, eax
0x18006ce9c  jz      loc_18006CF36
0x18006cea2  jmp     short loc_18006CEBD
0x18006cea4  test    eax, eax
0x18006cea6  jz      short loc_18006CEBD
0x18006cea8  mov     rdx, [rbp+Buffer]
0x18006ceac  add     rcx, 4; unsigned __int16 *
0x18006ceb0  add     rdx, 4; unsigned __int16 *
0x18006ceb4  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18006ceb9  test    eax, eax
0x18006cebb  jnz     short loc_18006CF36
0x18006cebd  mov     rax, [rdi+1F8h]
0x18006cec4  lea     r8, aNlsetservercli_9; "NlSetServerClientSession: New DC name: "...
0x18006cecb  mov     r9, [rbp+Buffer]
0x18006cecf  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006ced2  mov     ecx, 200h; unsigned int
0x18006ced7  mov     [rsp+30h+var_10], rax
0x18006cedc  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006cee1  lea     rbx, [rdi+158h]
0x18006cee8  mov     rcx, rbx; CriticalSection
0x18006ceeb  call    cs:__imp_RtlEnterCriticalSection
0x18006cef2  nop     dword ptr [rax+rax+00h]
0x18006cef7  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18006cefa  call    ?NlLogTimeoutRecurringEvents@@YAXPEAU_CLIENT_SESSION@@@Z; NlLogTimeoutRecurringEvents(_CLIENT_SESSION *)
0x18006ceff  mov     rcx, rbx; CriticalSection
0x18006cf02  mov     [rdi+188h], r13
0x18006cf09  mov     [rdi+190h], r13
0x18006cf10  call    cs:__imp_RtlLeaveCriticalSection
0x18006cf17  nop     dword ptr [rax+rax+00h]
0x18006cf1c  mov     rcx, [rdi+1F8h]; Buffer
0x18006cf23  call    cs:__imp_NetApiBufferFree
0x18006cf2a  nop     dword ptr [rax+rax+00h]
0x18006cf2f  mov     [rdi+1F8h], r13
0x18006cf36  mov     ebx, [rdi+198h]
0x18006cf3c  and     ebx, 1FCh
0x18006cf42  cmp     ebx, esi
0x18006cf44  jz      short loc_18006CF6F
0x18006cf46  mov     r9d, esi
0x18006cf49  mov     dword ptr [rsp+30h+var_10], ebx
0x18006cf4d  lea     r8, aNlsetservercli_3; "NlSetServerClientSession: New discovery"...
0x18006cf54  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18006cf57  mov     ecx, r15d; unsigned int
0x18006cf5a  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006cf5f  not     ebx
0x18006cf61  and     ebx, [rdi+198h]
0x18006cf67  or      ebx, esi
0x18006cf69  mov     [rdi+198h], ebx
0x18006cf6f  cmp     [rdi+1F8h], r13
0x18006cf76  jnz     short loc_18006CF87
0x18006cf78  mov     rax, [rbp+Buffer]
0x18006cf7c  mov     [rdi+1F8h], rax
0x18006cf83  mov     [rbp+Buffer], r13
0x18006cf87  mov     dl, 1; Wait
0x18006cf89  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x18006cf90  call    cs:__imp_RtlAcquireResourceExclusive
0x18006cf97  nop     dword ptr [rax+rax+00h]
0x18006cf9c  mov     rcx, [rdi+2A0h]; struct _PERF_COUNTERSET_INSTANCE *
0x18006cfa3  call    ?NlPcGetInstanceName@@YAPEAGPEAU_PERF_COUNTERSET_INSTANCE@@@Z; NlPcGetInstanceName(_PERF_COUNTERSET_INSTANCE *)
0x18006cfa8  mov     rdx, [rdi+1F8h]; lpString2
0x18006cfaf  mov     rcx, rax; lpString1
0x18006cfb2  call    cs:__imp_lstrcmpW
0x18006cfb9  nop     dword ptr [rax+rax+00h]
0x18006cfbe  test    eax, eax
0x18006cfc0  jz      loc_18006D14E
0x18006cfc6  mov     rcx, [rdi+2A0h]
0x18006cfcd  mov     edx, 1
0x18006cfd2  mov     esi, r13d
0x18006cfd5  call    ?NlPcReadCounter32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@@Z; NlPcReadCounter32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS)
0x18006cfda  mov     rcx, [rdi+2A0h]
0x18006cfe1  xor     edx, edx
0x18006cfe3  mov     r15d, eax
0x18006cfe6  call    ?NlPcReadCounter32@@YAKPEAU_PERF_COUNTERSET_INSTANCE@@W4_NLPC_COUNTER_IDS@@@Z; NlPcReadCounter32(_PERF_COUNTERSET_INSTANCE *,_NLPC_COUNTER_IDS)
0x18006cfeb  mov     r12d, eax
0x18006cfee  mov     ebx, 8000h
0x18006cff3  cmp     [rdi+2A0h], r13
0x18006cffa  jz      loc_18006D08D
0x18006d000  cmp     cs:hDataSource_PerfCntr_1, r13
0x18006d007  jnz     short loc_18006D022
0x18006d009  mov     r8d, 1586h; unsigned int
0x18006d00f  lea     rdx, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18006d016  lea     rcx, aNlpcHproviderN; "NLPC_HPROVIDER != NULL"
0x18006d01d  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006d022  mov     rcx, [rdi+2A0h]; struct _PERF_COUNTERSET_INSTANCE *
0x18006d029  call    ?NlPcGetInstanceName@@YAPEAGPEAU_PERF_COUNTERSET_INSTANCE@@@Z; NlPcGetInstanceName(_PERF_COUNTERSET_INSTANCE *)
0x18006d02e  mov     r8, rcx
0x18006d031  mov     [rsp+30h+var_10], rdi
0x18006d036  mov     r9, rax
0x18006d039  lea     rdx, aNlsetservercli_5; "NlSetServerClientSession: Connection ch"...
0x18006d040  mov     ecx, ebx; unsigned int
0x18006d042  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006d047  mov     rdx, [rdi+2A0h]; InstanceBlock
0x18006d04e  mov     rcx, cs:hDataSource_PerfCntr_1; Provider
0x18006d055  call    cs:__imp_PerfDeleteInstance
0x18006d05c  nop     dword ptr [rax+rax+00h]
0x18006d061  mov     [rdi+2A0h], r13
0x18006d068  mov     ecx, ebx; unsigned int
0x18006d06a  mov     esi, eax
0x18006d06c  test    eax, eax
0x18006d06e  jnz     short loc_18006D07E
0x18006d070  lea     rdx, aNlsetservercli_6; "NlSetServerClientSession: Delete succes"...
0x18006d077  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006d07c  jmp     short loc_18006D08D
0x18006d07e  mov     r8d, eax
0x18006d081  lea     rdx, aNlsetservercli_8; "NlSetServerClientSession: Could not del"...
0x18006d088  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006d08d  cmp     cs:hDataSource_PerfCntr_1, r13
0x18006d094  jz      loc_18006D123
0x18006d09a  test    esi, esi
0x18006d09c  jnz     loc_18006D123
0x18006d0a2  lea     r9d, [rsi+1]
0x18006d0a6  lock xadd cs:?NlPcGlobalInstanceNumber@@3KA, r9d; ulong NlPcGlobalInstanceNumber
0x18006d0af  mov     r8, [rdi+1F8h]; Name
0x18006d0b6  lea     rdx, CtrSet_PerfCntr_1_1Guid; CounterSetGuid
0x18006d0bd  mov     rcx, cs:hDataSource_PerfCntr_1; ProviderHandle
0x18006d0c4  inc     r9d; Id
0x18006d0c7  call    cs:__imp_PerfCreateInstance
0x18006d0ce  nop     dword ptr [rax+rax+00h]
0x18006d0d3  mov     [rdi+2A0h], rax
0x18006d0da  mov     rcx, rax; struct _PERF_COUNTERSET_INSTANCE *
0x18006d0dd  test    rax, rax
0x18006d0e0  jz      short loc_18006D0FB
0x18006d0e2  call    ?NlPcGetInstanceName@@YAPEAGPEAU_PERF_COUNTERSET_INSTANCE@@@Z; NlPcGetInstanceName(_PERF_COUNTERSET_INSTANCE *)
0x18006d0e7  mov     r9, rax
0x18006d0ea  mov     [rsp+30h+var_10], rdi
0x18006d0ef  mov     r8, rcx
0x18006d0f2  lea     rdx, aNlallocateclie_1; "NlAllocateClientSession: New Perf Insta"...
0x18006d0f9  jmp     short loc_18006D11C
0x18006d0fb  call    cs:__imp_GetLastError
  ... truncated ...
```
