# NlDiscoverDc(_CLIENT_SESSION *,_DISCOVERY_TYPE,uchar,uchar)

- ea: `0x180064834`
- end: `0x180064f5b`
- name: `?NlDiscoverDc@@YAJPEAU_CLIENT_SESSION@@W4_DISCOVERY_TYPE@@EE@Z`
- size: `1831`
- prototype: `__int64 __fastcall(__int64, int, char, char)`
- caller_count: `7`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180035368`
- `0x1800378d4`
- `0x18005703c`
- `0x180064520`
- `0x18006515c`
- `0x180066108`
- `0x180066904`

## callees

- `0x180003220`
- `0x180008ba0`
- `0x18000c3ac`
- `0x18000d100`
- `0x18000d710`
- `0x18000e270`
- `0x18001ef7c`
- `0x1800208ac`
- `0x180024adc`
- `0x18003e71c`
- `0x180040f0c`
- `0x180045678`
- `0x180064674`
- `0x180064834`
- `0x180067df0`
- `0x180068458`
- `0x180078f00`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180064a90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180064a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064aeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064aeb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800649e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180064d6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180064d99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180064eb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180064ec1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800649e9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180064d6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180064d99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180064eb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180064ec1`
- `ntdll!RtlLeaveCriticalSection` at `0x180064a74`
- `ntdll!RtlLeaveCriticalSection` at `0x180064c1c`
- `ntdll!RtlLeaveCriticalSection` at `0x180064dcb`
- `ntdll!RtlLeaveCriticalSection` at `0x180064e4c`
- `ntdll!RtlLeaveCriticalSection` at `0x180064f04`
- `ntdll!RtlLeaveCriticalSection` at `0x180064a74`
- `ntdll!RtlLeaveCriticalSection` at `0x180064c1c`
- `ntdll!RtlLeaveCriticalSection` at `0x180064dcb`
- `ntdll!RtlLeaveCriticalSection` at `0x180064e4c`
- `ntdll!RtlLeaveCriticalSection` at `0x180064f04`
- `ntdll!RtlEnterCriticalSection` at `0x180064922`
- `ntdll!RtlEnterCriticalSection` at `0x180064a9f`
- `ntdll!RtlEnterCriticalSection` at `0x180064d12`
- `ntdll!RtlEnterCriticalSection` at `0x180064db3`
- `ntdll!RtlEnterCriticalSection` at `0x180064e66`
- `ntdll!RtlEnterCriticalSection` at `0x180064922`
- `ntdll!RtlEnterCriticalSection` at `0x180064a9f`
- `ntdll!RtlEnterCriticalSection` at `0x180064d12`
- `ntdll!RtlEnterCriticalSection` at `0x180064db3`
- `ntdll!RtlEnterCriticalSection` at `0x180064e66`
- `SAMSRV!SampDsIsRunning` at `0x180064b20`
- `SAMSRV!SampDsIsRunning` at `0x180064b3a`
- `SAMSRV!SampDsIsRunning` at `0x180064b20`
- `SAMSRV!SampDsIsRunning` at `0x180064b3a`

## string_xrefs

- `0x180064a19`: `ClientSession->CsFlags & CS_WRITER`
- `0x180064e10`: `ClientSession->CsFlags & CS_WRITER`
- `0x1800648f6`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x180064e09`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006493c`: `NlDiscoverDc: Synchronous discovery attempt of indirect trust.\n`
- `0x180064de4`: `NlDiscoverDc: Async discovery completed by another thread (current value ignored).\n`

## pseudocode

```c
__int64 __fastcall NlDiscoverDc(__int64 a1, int a2, char a3, char a4)
{
  char *v7; // r9
  void *v8; // rsp
  unsigned __int16 *hMem; // r15
  _DWORD *v10; // rax
  __int64 v11; // r8
  char *v12; // r9
  int v13; // eax
  unsigned int v14; // edi
  unsigned int v15; // edi
  int v16; // r14d
  int v17; // eax
  DWORD v18; // edi
  DWORD LastError; // eax
  __int64 v20; // rcx
  int v21; // r13d
  const char *v22; // r9
  char IsEnabled; // al
  unsigned __int16 *v24; // rcx
  int v25; // eax
  int v26; // ecx
  int v27; // edx
  int v28; // ecx
  int v29; // eax
  unsigned int v30; // r12d
  const WCHAR *lpWideCharStr; // r8
  char v32; // r14
  const unsigned __int16 *v33; // r9
  unsigned int Name; // edi
  struct _RTL_CRITICAL_SECTION *v35; // rcx
  char *v36; // r9
  int v37; // r9d
  unsigned int v38; // eax
  __int64 v40; // [rsp-20h] [rbp-320h] BYREF
  __int64 v41; // [rsp+0h] [rbp-300h]
  int v42; // [rsp+70h] [rbp-290h] BYREF
  __int64 v43; // [rsp+78h] [rbp-288h] BYREF
  char v44; // [rsp+300h] [rbp+0h]
  char v45; // [rsp+301h] [rbp+1h]
  struct _NL_DC_CACHE_ENTRY *v46; // [rsp+308h] [rbp+8h] BYREF
  unsigned int v47; // [rsp+310h] [rbp+10h]
  unsigned int v48; // [rsp+314h] [rbp+14h]
  unsigned __int16 *v49; // [rsp+318h] [rbp+18h]
  struct _GUID *Buf1; // [rsp+320h] [rbp+20h]
  void *v51; // [rsp+328h] [rbp+28h]

  v44 = a4;
  v45 = a3;
  v46 = 0;
  if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x280
    || (unsigned __int64)(g_ulAdditionalProbeSize + 648) < 0x280
    || !(unsigned int)VerifyStackAvailable()
    || (v8 = alloca(656), &v40 == (__int64 *)-144LL)
    || (hMem = (unsigned __int16 *)&v43, v42 = 1801679955, &v42 == (int *)-8LL) )
  {
    v10 = (_DWORD *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(648);
    if ( !v10 )
      return 3221225495LL;
    hMem = (unsigned __int16 *)(v10 + 2);
    *v10 = 1885431112;
    if ( v10 == (_DWORD *)-8LL )
      return 3221225495LL;
  }
  if ( !*(_DWORD *)(a1 + 328) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
      5849,
      v7);
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  v13 = *(_DWORD *)(a1 + 292);
  if ( (v13 & 0x10) != 0 )
  {
    if ( a3 )
    {
      if ( a2 == 2 )
        NlAssertFailed(
          "DiscoveryType != DT_Synchronous",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
          5889,
          v12);
    }
    else
    {
      if ( (v13 & 8) == 0 )
        NlAssertFailed(
          "ClientSession->CsFlags & CS_WRITER",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
          5896,
          v12);
      v17 = *(_DWORD *)(a1 + 408) & 2;
      if ( a2 != 2 )
      {
        if ( !v17 )
          NlDcQueueDiscovery(a1, a2, v11, v12);
        goto LABEL_92;
      }
      if ( v17 )
      {
        if ( !(unsigned int)NlQueueWorkItem((struct _WORKER_ITEM *)(a1 + 56), 0, 1) )
          NlPrintCsRoutine(
            0x100u,
            (struct _CLIENT_SESSION *)a1,
            L"NlDiscoverDc: Failed to boost ASYNC discovery priority\n");
        RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
        v18 = WaitForSingleObject(*(HANDLE *)(a1 + 416), 1000 * (dword_1800F1134 + 16));
        RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
        if ( !v18 )
        {
          if ( *(_DWORD *)(a1 + 284) != 1 )
          {
            v14 = *(_DWORD *)(a1 + 288);
            NlPrintCsRoutine(
              0x100u,
              (struct _CLIENT_SESSION *)a1,
              L"NlDiscoverDc: ASYNC discovery failed so we will too 0x%lx.\n",
              v14);
            goto LABEL_93;
          }
LABEL_89:
          v14 = 0;
          goto LABEL_93;
        }
        if ( v18 == 258 )
        {
          NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: ASYNC discovery took too long.\n");
          goto LABEL_13;
        }
        LastError = GetLastError();
        LODWORD(v41) = v18;
        NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: wait error: %ld %ld\n", LastError, v41);
        v20 = v18;
LABEL_38:
        v14 = NetpApiStatusToNtStatus(v20);
        goto LABEL_93;
      }
    }
    v15 = 0;
    if ( (*(_BYTE *)(a1 + 292) & 4) != 0 )
      v15 = 4096;
    v16 = 0;
    switch ( *(_DWORD *)(a1 + 280) )
    {
      case 2:
        v21 = 128;
        v15 |= 1u;
        break;
      case 3:
        v21 = 1024;
        break;
      case 4:
        v21 = 64;
        break;
      case 6:
        v21 = 256;
        v15 |= 1u;
        v16 = (unsigned __int8)SampDsIsRunning() != 0 ? 0x80 : 0;
        break;
      case 7:
        v21 = 1048704;
        v15 |= 1u;
        v16 = (unsigned __int8)SampDsIsRunning() != 0 ? 0xC1000 : 0;
        break;
      default:
        NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: invalid SecureChannelType retry %ld\n");
        v14 = -1073741730;
        GetSystemTimeAsFileTime((LPFILETIME)(a1 + 24));
        if ( !*(_DWORD *)(a1 + 284) )
        {
          *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 24);
          *(_DWORD *)(a1 + 288) = -1073741730;
        }
        goto LABEL_93;
    }
    v22 = "Synchronous";
    if ( a2 != 2 )
      v22 = "Async";
    NlPrintCsRoutine(0x200u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: Start %hs Discovery\n", v22);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
    v24 = hMem + 256;
    if ( IsEnabled )
    {
      v25 = NlCaptureSiteName(v24);
      v26 = v15 | 4;
      if ( !v25 )
        v26 = v15;
      v15 = v26;
      v49 = (unsigned __int16 *)((unsigned __int64)(hMem + 256) & -(__int64)(v25 != 0));
    }
    else if ( (unsigned int)NlCaptureSiteName_Old(v24) )
    {
      v15 |= 4u;
      v49 = hMem + 256;
    }
    else
    {
      v49 = 0;
    }
    v27 = *(_DWORD *)(a1 + 292);
    v28 = v16 | 0x20;
    if ( (v27 & 4) == 0 )
      v28 = v16;
    v29 = v28 | 1;
    if ( (v27 & 0x10000) == 0 )
      v29 = v28;
    v48 = v29 | 0x4000;
    RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
    NlCaptureDnsForestName(hMem);
    v30 = (a2 != 0) + 1;
    v47 = 1000 * (dword_1800F1134 + 15);
    Buf1 = *(struct _GUID **)(a1 + 176);
    v51 = *(void **)(a1 + 264);
    if ( NlDnsHasDnsServers() )
      lpWideCharStr = *(const WCHAR **)(a1 + 160);
    else
      lpWideCharStr = 0;
    v32 = v44;
    if ( v44 )
      v33 = *(const unsigned __int16 **)(a1 + 200);
    else
      v33 = 0;
    Name = NetpDcGetName(
             *(void **)(a1 + 272),
             *(const unsigned __int16 **)(*(_QWORD *)(a1 + 272) + 264LL),
             *(const unsigned __int16 **)(*(_QWORD *)(a1 + 272) + 280LL),
             v33,
             v21 & (unsigned int)-(v44 != 0),
             *(WCHAR **)(a1 + 120),
             lpWideCharStr,
             (unsigned __int64)hMem,
             v51,
             Buf1,
             v49,
             v48,
             v15,
             v47,
             v30,
             0,
             &v46);
    RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
    if ( Name )
    {
      if ( Name == 1317 )
      {
        NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: DC reports no such account found.\n");
        v14 = -1073741429;
      }
      else
      {
        if ( Name == 1355 )
          NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: Cannot find DC.\n");
        else
          NlPrintCsRoutine(
            0x100u,
            (struct _CLIENT_SESSION *)a1,
            L"NlDiscoverDc: NetpDcGetName Unknown error %ld.\n",
            Name);
        v14 = -1073741730;
      }
      GetSystemTimeAsFileTime((LPFILETIME)(a1 + 24));
      if ( !*(_DWORD *)(a1 + 284) )
      {
        *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 24);
        *(_DWORD *)(a1 + 288) = v14;
      }
      if ( v32 )
        GetSystemTimeAsFileTime((LPFILETIME)(a1 + 32));
      goto LABEL_93;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)(a1 + 272) + 400LL));
    v35 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 272);
    *(_DWORD *)(a1 + 292) |= 0x10000u;
    RtlLeaveCriticalSection(v35 + 10);
    if ( *(_DWORD *)(a1 + 284) )
    {
      if ( v45 )
      {
        NlPrintCsRoutine(
          0x100u,
          (struct _CLIENT_SESSION *)a1,
          L"NlDiscoverDc: Async discovery completed by another thread (current value ignored).\n");
        goto LABEL_89;
      }
      if ( (*(_BYTE *)(a1 + 292) & 8) == 0 )
        NlAssertFailed(
          "ClientSession->CsFlags & CS_WRITER",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
          6248,
          v36);
      v37 = *(_DWORD *)(a1 + 408);
      if ( ((v37 & 4) != 0 || (*((_BYTE *)v46 + 264) & 0x10) == 0) && ((v37 & 8) != 0 || *((char *)v46 + 264) >= 0) )
      {
        LODWORD(v41) = *((_DWORD *)v46 + 66);
        NlPrintCsRoutine(
          0x200u,
          (struct _CLIENT_SESSION *)a1,
          L"NlDiscoverDc: Better DC not found (keeping NT old DC). 0x%lx 0x%lx\n");
        GetSystemTimeAsFileTime((LPFILETIME)(a1 + 24));
        if ( v32 )
          GetSystemTimeAsFileTime((LPFILETIME)(a1 + 32));
        goto LABEL_89;
      }
      RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
      NlSetStatusClientSession((struct _CLIENT_SESSION *)a1, -1073741730);
      RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
    }
    v38 = NlSetServerClientSession((struct _CLIENT_SESSION *)a1, v46, v32 != 0, 0);
    if ( !v38 )
    {
      NlPrintCsRoutine(0x200u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: Found DC %ws\n", *(_QWORD *)(a1 + 504));
      goto LABEL_89;
    }
    v20 = v38;
    goto LABEL_38;
  }
  if ( a2 != 2 )
  {
LABEL_92:
    v14 = 259;
    goto LABEL_93;
  }
  NlPrintCsRoutine(
    0x100u,
    (struct _CLIENT_SESSION *)a1,
    L"NlDiscoverDc: Synchronous discovery attempt of indirect trust.\n");
LABEL_13:
  v14 = -1073741730;
LABEL_93:
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  if ( v46 )
    NetpDcDerefCacheEntry(v46);
  if ( hMem )
  {
    if ( *((_DWORD *)hMem - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v14;
}

```

## disassembly

```asm
0x180064834  push    rbp
0x180064836  push    rbx
0x180064837  push    rsi
0x180064838  push    rdi
0x180064839  push    r12
0x18006483b  push    r13
0x18006483d  push    r14
0x18006483f  push    r15
0x180064841  sub     rsp, 0D8h
0x180064848  lea     rbp, [rsp+90h]
0x180064850  mov     rax, cs:__security_cookie
0x180064857  xor     rax, rbp
0x18006485a  mov     [rbp+80h+var_50], rax
0x18006485e  xor     r13d, r13d
0x180064861  mov     [rbp+80h+var_80], r9b
0x180064865  mov     r12d, edx
0x180064868  mov     [rbp+80h+var_7F], r8b
0x18006486c  mov     edx, 280h
0x180064871  mov     [rbp+80h+var_78], r13
0x180064875  cmp     cs:g_ulMaxStackAllocSize, rdx
0x18006487c  mov     dil, r8b
0x18006487f  mov     rbx, rcx
0x180064882  jb      short loc_1800648C9
0x180064884  mov     rcx, cs:g_ulAdditionalProbeSize
0x18006488b  add     rcx, 288h
0x180064892  cmp     rcx, rdx
0x180064895  jb      short loc_1800648C9
0x180064897  call    VerifyStackAvailable
0x18006489c  test    eax, eax
0x18006489e  jz      short loc_1800648C9
0x1800648a0  mov     eax, [rsp+110h+var_110]
0x1800648a3  mov     eax, 290h
0x1800648a8  sub     rsp, rax
0x1800648ab  lea     rcx, [rsp+3A0h+var_310]
0x1800648b3  mov     eax, [rcx]
0x1800648b5  test    rcx, rcx
0x1800648b8  jz      short loc_1800648C9
0x1800648ba  lea     r15, [rcx+8]
0x1800648be  mov     dword ptr [rcx], 6B637453h
0x1800648c4  test    r15, r15
0x1800648c7  jnz     short loc_1800648F6
0x1800648c9  mov     rax, cs:g_pfnAllocate
0x1800648d0  mov     ecx, 288h
0x1800648d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800648da  test    rax, rax
0x1800648dd  jz      loc_180064F39
0x1800648e3  lea     r15, [rax+8]
0x1800648e7  mov     dword ptr [rax], 70616548h
0x1800648ed  test    r15, r15
0x1800648f0  jz      loc_180064F39
0x1800648f6  lea     rsi, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800648fd  cmp     [rbx+148h], r13d
0x180064904  ja      short loc_18006491B
0x180064906  mov     r8d, 16D9h; unsigned int
0x18006490c  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x180064913  mov     rdx, rsi; void *
0x180064916  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006491b  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180064922  call    cs:__imp_RtlEnterCriticalSection
0x180064928  mov     eax, [rbx+124h]
0x18006492e  test    al, 10h
0x180064930  jnz     short loc_18006495A
0x180064932  cmp     r12d, 2
0x180064936  jnz     loc_180064EF8
0x18006493c  lea     r8, aNldiscoverdcSy; "NlDiscoverDc: Synchronous discovery att"...
0x180064943  mov     ecx, 100h; unsigned int
0x180064948  mov     rdx, rbx; struct _CLIENT_SESSION *
0x18006494b  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180064950  mov     edi, 0C000005Eh
0x180064955  jmp     loc_180064EFD
0x18006495a  test    dil, dil
0x18006495d  jz      loc_180064A0F
0x180064963  cmp     r12d, 2
0x180064967  jnz     short loc_18006497E
0x180064969  mov     r8d, 1701h; unsigned int
0x18006496f  lea     rcx, aDiscoverytypeD; "DiscoveryType != DT_Synchronous"
0x180064976  mov     rdx, rsi; void *
0x180064979  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18006497e  test    byte ptr [rbx+124h], 4
0x180064985  mov     edi, r13d
0x180064988  mov     r9d, [rbx+118h]
0x18006498f  mov     eax, 1000h
0x180064994  mov     ecx, r9d
0x180064997  cmovnz  edi, eax
0x18006499a  mov     r14d, r13d
0x18006499d  mov     esi, 100h
0x1800649a2  sub     ecx, 2
0x1800649a5  jz      loc_180064B5E
0x1800649ab  sub     ecx, 1
0x1800649ae  jz      loc_180064B56
0x1800649b4  sub     ecx, 1
0x1800649b7  jz      loc_180064B4E
0x1800649bd  sub     ecx, 2
0x1800649c0  jz      loc_180064B34
0x1800649c6  cmp     ecx, 1
0x1800649c9  jz      loc_180064B17
0x1800649cf  lea     r8, aNldiscoverdcIn; "NlDiscoverDc: invalid SecureChannelType"...
0x1800649d6  mov     rdx, rbx; struct _CLIENT_SESSION *
0x1800649d9  mov     ecx, esi; unsigned int
0x1800649db  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800649e0  lea     rcx, [rbx+18h]; lpSystemTimeAsFileTime
0x1800649e4  mov     edi, 0C000005Eh
0x1800649e9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800649ef  cmp     [rbx+11Ch], r13d
0x1800649f6  jnz     loc_180064EFD
0x1800649fc  mov     rax, [rbx+18h]
0x180064a00  mov     [rbx+10h], rax
0x180064a04  mov     [rbx+120h], edi
0x180064a0a  jmp     loc_180064EFD
0x180064a0f  test    al, 8
0x180064a11  jnz     short loc_180064A28
0x180064a13  mov     r8d, 1708h; unsigned int
0x180064a19  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x180064a20  mov     rdx, rsi; void *
0x180064a23  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180064a28  mov     eax, [rbx+198h]
0x180064a2e  and     eax, 2
0x180064a31  cmp     r12d, 2
0x180064a35  jnz     loc_180064EE9
0x180064a3b  test    eax, eax
0x180064a3d  jz      loc_18006497E
0x180064a43  lea     rcx, [rbx+38h]; struct _WORKER_ITEM *
0x180064a47  xor     edx, edx; int
0x180064a49  lea     r8d, [r12-1]; int
0x180064a4e  call    ?NlQueueWorkItem@@YAHPEAU_WORKER_ITEM@@HH@Z; NlQueueWorkItem(_WORKER_ITEM *,int,int)
0x180064a53  mov     esi, 100h
0x180064a58  test    eax, eax
0x180064a5a  jnz     short loc_180064A6D
0x180064a5c  lea     r8, aNldiscoverdcFa; "NlDiscoverDc: Failed to boost ASYNC dis"...
0x180064a63  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180064a66  mov     ecx, esi; unsigned int
0x180064a68  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180064a6d  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180064a74  call    cs:__imp_RtlLeaveCriticalSection
0x180064a7a  mov     eax, cs:dword_1800F1134
0x180064a80  mov     rcx, [rbx+1A0h]; hHandle
0x180064a87  add     eax, 10h
0x180064a8a  imul    edx, eax, 3E8h; dwMilliseconds
0x180064a90  call    cs:__imp_WaitForSingleObject
0x180064a96  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180064a9d  mov     edi, eax
0x180064a9f  call    cs:__imp_RtlEnterCriticalSection
0x180064aa5  test    edi, edi
0x180064aa7  jnz     short loc_180064AD5
0x180064aa9  cmp     dword ptr [rbx+11Ch], 1
0x180064ab0  jz      loc_180064EE4
0x180064ab6  mov     edi, [rbx+120h]
0x180064abc  lea     r8, aNldiscoverdcAs_0; "NlDiscoverDc: ASYNC discovery failed so"...
0x180064ac3  mov     r9d, edi
0x180064ac6  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180064ac9  mov     ecx, esi; unsigned int
0x180064acb  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180064ad0  jmp     loc_180064EFD
0x180064ad5  cmp     edi, 102h
0x180064adb  jnz     short loc_180064AEB
0x180064add  lea     r8, aNldiscoverdcAs; "NlDiscoverDc: ASYNC discovery took too "...
0x180064ae4  mov     ecx, esi
0x180064ae6  jmp     loc_180064948
0x180064aeb  call    cs:__imp_GetLastError
0x180064af1  lea     r8, aNldiscoverdcWa; "NlDiscoverDc: wait error: %ld %ld\n"
0x180064af8  mov     dword ptr [rsp+3A0h+var_380], edi
0x180064afc  mov     r9d, eax
0x180064aff  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180064b02  mov     ecx, esi; unsigned int
0x180064b04  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180064b09  mov     ecx, edi
0x180064b0b  call    NetpApiStatusToNtStatus
0x180064b10  mov     edi, eax
0x180064b12  jmp     loc_180064EFD
0x180064b17  mov     r13d, 100080h
0x180064b1d  or      edi, 1
0x180064b20  call    cs:__imp_SampDsIsRunning
0x180064b26  neg     al
0x180064b28  sbb     r14d, r14d
0x180064b2b  and     r14d, 0C1000h
0x180064b32  jmp     short loc_180064B67
0x180064b34  mov     r13d, esi
0x180064b37  or      edi, 1
0x180064b3a  call    cs:__imp_SampDsIsRunning
0x180064b40  neg     al
0x180064b42  sbb     r14d, r14d
0x180064b45  and     r14d, 80h
0x180064b4c  jmp     short loc_180064B67
0x180064b4e  mov     r13d, 40h ; '@'
0x180064b54  jmp     short loc_180064B67
0x180064b56  mov     r13d, 400h
0x180064b5c  jmp     short loc_180064B67
0x180064b5e  mov     r13d, 80h
0x180064b64  or      edi, 1
0x180064b67  cmp     r12d, 2
0x180064b6b  lea     rax, aAsync; "Async"
0x180064b72  lea     r9, aSynchronous; "Synchronous"
0x180064b79  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180064b7c  cmovnz  r9, rax
0x180064b80  lea     r8, aNldiscoverdcSt; "NlDiscoverDc: Start %hs Discovery\n"
0x180064b87  mov     ecx, 200h; unsigned int
0x180064b8c  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180064b91  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x180064b98  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x180064b9d  lea     rcx, [r15+200h]; unsigned __int16 *
0x180064ba4  test    al, al
0x180064ba6  jz      short loc_180064BCE
0x180064ba8  call    ?NlCaptureSiteName@@YAHPEAG@Z; NlCaptureSiteName(ushort *)
0x180064bad  mov     ecx, edi
0x180064baf  or      ecx, 4
0x180064bb2  test    eax, eax
0x180064bb4  cmovz   ecx, edi
0x180064bb7  neg     eax
0x180064bb9  mov     edi, ecx
0x180064bbb  lea     rax, [r15+200h]
0x180064bc2  sbb     rcx, rcx
0x180064bc5  and     rcx, rax
0x180064bc8  mov     [rbp+80h+var_68], rcx
0x180064bcc  jmp     short loc_180064BEF
0x180064bce  call    ?NlCaptureSiteName_Old@@YAHQEAG@Z; NlCaptureSiteName_Old(ushort * const)
0x180064bd3  test    eax, eax
0x180064bd5  jz      short loc_180064BE7
0x180064bd7  lea     rax, [r15+200h]
0x180064bde  or      edi, 4
0x180064be1  mov     [rbp+80h+var_68], rax
0x180064be5  jmp     short loc_180064BEF
0x180064be7  mov     [rbp+80h+var_68], 0
0x180064bef  mov     edx, [rbx+124h]
0x180064bf5  mov     ecx, r14d
0x180064bf8  or      ecx, 20h
0x180064bfb  test    dl, 4
0x180064bfe  cmovz   ecx, r14d
0x180064c02  mov     eax, ecx
0x180064c04  or      eax, 1
0x180064c07  bt      edx, 10h
0x180064c0b  cmovnb  eax, ecx
0x180064c0e  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180064c15  bts     eax, 0Eh
0x180064c19  mov     [rbp+80h+var_6C], eax
0x180064c1c  call    cs:__imp_RtlLeaveCriticalSection
0x180064c22  mov     rcx, r15; unsigned __int16 *
0x180064c25  call    ?NlCaptureDnsForestName@@YAXQEAG@Z; NlCaptureDnsForestName(ushort * const)
0x180064c2a  mov     eax, cs:dword_1800F1134
0x180064c30  neg     r12d
0x180064c33  sbb     r12d, r12d
0x180064c36  add     eax, 0Fh
0x180064c39  imul    eax, 3E8h
0x180064c3f  neg     r12d
0x180064c42  inc     r12d
0x180064c45  mov     [rbp+80h+var_70], eax
0x180064c48  mov     rax, [rbx+0B0h]
0x180064c4f  mov     [rbp+80h+var_60], rax
0x180064c53  mov     rax, [rbx+108h]
0x180064c5a  mov     [rbp+80h+var_58], rax
0x180064c5e  call    ?NlDnsHasDnsServers@@YAEXZ; NlDnsHasDnsServers(void)
0x180064c63  test    al, al
0x180064c65  jz      short loc_180064C70
0x180064c67  mov     r8, [rbx+0A0h]
0x180064c6e  jmp     short loc_180064C73
0x180064c70  xor     r8d, r8d
0x180064c73  mov     r14b, [rbp+80h+var_80]
0x180064c77  mov     r10, [rbx+78h]
0x180064c7b  mov     al, r14b
0x180064c7e  neg     al
0x180064c80  sbb     edx, edx
0x180064c82  and     edx, r13d
0x180064c85  xor     r13d, r13d
0x180064c88  test    r14b, r14b
0x180064c8b  jz      short loc_180064C96
0x180064c8d  mov     r9, [rbx+0C8h]
0x180064c94  jmp     short loc_180064C99
0x180064c96  mov     r9, r13; unsigned __int16 *
0x180064c99  mov     rcx, [rbx+110h]; void *
0x180064ca0  lea     rax, [rbp+80h+var_78]
0x180064ca4  mov     [rsp+3A0h+var_320], rax; struct _NL_DC_CACHE_ENTRY **
0x180064cac  mov     eax, [rbp+80h+var_70]
0x180064caf  mov     [rsp+3A0h+var_328], r13; struct _DOMAIN_CONTROLLER_INFOW **
0x180064cb4  mov     [rsp+3A0h+var_330], r12d; unsigned int
0x180064cb9  mov     [rsp+3A0h+var_338], eax; unsigned int
0x180064cbd  mov     eax, [rbp+80h+var_6C]
0x180064cc0  mov     [rsp+3A0h+var_340], edi; unsigned int
0x180064cc4  mov     [rsp+3A0h+var_348], eax; unsigned int
0x180064cc8  mov     rax, [rbp+80h+var_68]
0x180064ccc  mov     [rsp+3A0h+var_350], rax; unsigned __int16 *
0x180064cd1  mov     rax, [rbp+80h+var_60]
0x180064cd5  mov     [rsp+3A0h+Buf1], rax; Buf1
0x180064cda  mov     rax, [rbp+80h+var_58]
0x180064cde  mov     [rsp+3A0h+var_360], rax; void *
0x180064ce3  mov     [rsp+3A0h+hMem], r15; hMem
0x180064ce8  mov     [rsp+3A0h+lpWideCharStr], r8; lpWideCharStr
0x180064ced  mov     r8, [rcx+118h]; unsigned __int16 *
0x180064cf4  mov     [rsp+3A0h+SourceString], r10; SourceString
0x180064cf9  mov     dword ptr [rsp+3A0h+var_380], edx; unsigned int
0x180064cfd  mov     rdx, [rcx+108h]; unsigned __int16 *
0x180064d04  call    ?NetpDcGetName@@YAKPEAXPEBG11K1110PEAU_GUID@@1KKKKPEAPEAU_DOMAIN_CONTROLLER_INFOW@@PEAPEAU_NL_DC_CACHE_ENTRY@@@Z; NetpDcGetName(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ulong,ulong,ulong,ulong,_DOMAIN_CONTROLLER_INFOW * *,_NL_DC_CACHE_ENTRY * *)
0x180064d09  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180064d10  mov     edi, eax
0x180064d12  call    cs:__imp_RtlEnterCriticalSection
0x180064d18  test    edi, edi
0x180064d1a  jz      loc_180064DA4
0x180064d20  mov     ecx, edi
0x180064d22  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180064d25  sub     ecx, 525h
0x180064d2b  jz      short loc_180064D58
0x180064d2d  cmp     ecx, 26h ; '&'
  ... truncated ...
```
