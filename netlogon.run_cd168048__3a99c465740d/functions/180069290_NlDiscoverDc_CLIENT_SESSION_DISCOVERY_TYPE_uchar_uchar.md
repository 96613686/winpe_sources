# NlDiscoverDc(_CLIENT_SESSION *,_DISCOVERY_TYPE,uchar,uchar)

- ea: `0x180069290`
- end: `0x180069a2a`
- name: `?NlDiscoverDc@@YAJPEAU_CLIENT_SESSION@@W4_DISCOVERY_TYPE@@EE@Z`
- size: `1946`
- prototype: ``
- caller_count: `7`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180037344`
- `0x180039ac4`
- `0x18005ae88`
- `0x180068f40`
- `0x180069c60`
- `0x18006ad64`
- `0x18006b5b4`

## callees

- `0x180003340`
- `0x1800090c0`
- `0x18000ca88`
- `0x18000d7a0`
- `0x18000dd00`
- `0x18000e910`
- `0x18001fdb4`
- `0x1800217d8`
- `0x180025a74`
- `0x180040f18`
- `0x180043a40`
- `0x1800485d0`
- `0x1800690ac`
- `0x180069290`
- `0x18006cbc4`
- `0x18006d2b0`
- `0x18007ea48`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800694fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800694fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069565`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006944b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180069807`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180069837`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006996e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180069983`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006944b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180069807`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180069837`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006996e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180069983`
- `ntdll!RtlLeaveCriticalSection` at `0x1800694dc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800696a8`
- `ntdll!RtlLeaveCriticalSection` at `0x180069875`
- `ntdll!RtlLeaveCriticalSection` at `0x1800698fc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800699cc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800694dc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800696a8`
- `ntdll!RtlLeaveCriticalSection` at `0x180069875`
- `ntdll!RtlLeaveCriticalSection` at `0x1800698fc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800699cc`
- `ntdll!RtlEnterCriticalSection` at `0x18006937e`
- `ntdll!RtlEnterCriticalSection` at `0x180069513`
- `ntdll!RtlEnterCriticalSection` at `0x1800697a4`
- `ntdll!RtlEnterCriticalSection` at `0x180069857`
- `ntdll!RtlEnterCriticalSection` at `0x18006991c`
- `ntdll!RtlEnterCriticalSection` at `0x18006937e`
- `ntdll!RtlEnterCriticalSection` at `0x180069513`
- `ntdll!RtlEnterCriticalSection` at `0x1800697a4`
- `ntdll!RtlEnterCriticalSection` at `0x180069857`
- `ntdll!RtlEnterCriticalSection` at `0x18006991c`
- `SAMSRV!SampDsIsRunning` at `0x1800695a0`
- `SAMSRV!SampDsIsRunning` at `0x1800695c0`
- `SAMSRV!SampDsIsRunning` at `0x1800695a0`
- `SAMSRV!SampDsIsRunning` at `0x1800695c0`

## string_xrefs

- `0x180069481`: `ClientSession->CsFlags & CS_WRITER`
- `0x1800698c0`: `ClientSession->CsFlags & CS_WRITER`
- `0x180069352`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x1800698b9`: `onecore\ds\netapi\svcdlls\logonsrv\server\trustutl.cxx`
- `0x18006939e`: `NlDiscoverDc: Synchronous discovery attempt of indirect trust.\n`
- `0x180069894`: `NlDiscoverDc: Async discovery completed by another thread (current value ignored).\n`

## pseudocode

```c
__int64 __fastcall NlDiscoverDc(__int64 a1, unsigned int a2, char a3, char a4)
{
  char *v7; // r9
  void *v8; // rsp
  unsigned __int16 *hMem; // r15
  _DWORD *v10; // rax
  char *v11; // r9
  int v12; // eax
  unsigned int v13; // edi
  unsigned int v14; // edi
  int v15; // r14d
  int v16; // eax
  DWORD v17; // edi
  DWORD LastError; // eax
  __int64 v19; // rcx
  int v20; // r13d
  const char *v21; // r9
  char IsEnabled; // al
  unsigned __int16 *v23; // rcx
  int v24; // eax
  int v25; // ecx
  int v26; // edx
  int v27; // ecx
  int v28; // eax
  unsigned int v29; // r12d
  const WCHAR *lpWideCharStr; // r8
  char v31; // r14
  const unsigned __int16 *v32; // r9
  unsigned int Name; // edi
  struct _RTL_CRITICAL_SECTION *v34; // rcx
  char *v35; // r9
  int v36; // r9d
  __int64 v37; // r8
  char *v38; // r9
  unsigned int v39; // eax
  __int64 v41; // [rsp-20h] [rbp-320h] BYREF
  __int64 v42; // [rsp+0h] [rbp-300h]
  int v43; // [rsp+70h] [rbp-290h] BYREF
  __int64 v44; // [rsp+78h] [rbp-288h] BYREF
  char v45; // [rsp+300h] [rbp+0h]
  char v46; // [rsp+301h] [rbp+1h]
  struct _NL_DC_CACHE_ENTRY *v47; // [rsp+308h] [rbp+8h] BYREF
  unsigned int v48; // [rsp+310h] [rbp+10h]
  unsigned int v49; // [rsp+314h] [rbp+14h]
  unsigned __int16 *v50; // [rsp+318h] [rbp+18h]
  struct _GUID *Buf1; // [rsp+320h] [rbp+20h]
  void *v52; // [rsp+328h] [rbp+28h]

  v45 = a4;
  v46 = a3;
  v47 = 0;
  if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x280
    || (unsigned __int64)(g_ulAdditionalProbeSize + 648) < 0x280
    || !(unsigned int)VerifyStackAvailable()
    || (v8 = alloca(656), &v41 == (__int64 *)-144LL)
    || (hMem = (unsigned __int16 *)&v44, v43 = 1801679955, &v43 == (int *)-8LL) )
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
      0x16D9u,
      v7);
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  v12 = *(_DWORD *)(a1 + 292);
  if ( (v12 & 0x10) != 0 )
  {
    if ( a3 )
    {
      if ( a2 == 2 )
        NlAssertFailed(
          "DiscoveryType != DT_Synchronous",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
          0x1701u,
          v11);
    }
    else
    {
      if ( (v12 & 8) == 0 )
        NlAssertFailed(
          "ClientSession->CsFlags & CS_WRITER",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\trustutl.cxx",
          0x1708u,
          v11);
      v16 = *(_DWORD *)(a1 + 408) & 2;
      if ( a2 != 2 )
      {
        if ( !v16 )
          NlDcQueueDiscovery(a1, a2);
        goto LABEL_92;
      }
      if ( v16 )
      {
        if ( !(unsigned int)NlQueueWorkItem((struct _WORKER_ITEM *)(a1 + 56), 0, 1) )
          NlPrintCsRoutine(
            0x100u,
            (struct _CLIENT_SESSION *)a1,
            L"NlDiscoverDc: Failed to boost ASYNC discovery priority\n");
        RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
        v17 = WaitForSingleObject(*(HANDLE *)(a1 + 416), 1000 * (dword_1800F8134 + 16));
        RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
        if ( !v17 )
        {
          if ( *(_DWORD *)(a1 + 284) != 1 )
          {
            v13 = *(_DWORD *)(a1 + 288);
            NlPrintCsRoutine(
              0x100u,
              (struct _CLIENT_SESSION *)a1,
              L"NlDiscoverDc: ASYNC discovery failed so we will too 0x%lx.\n",
              v13);
            goto LABEL_93;
          }
LABEL_89:
          v13 = 0;
          goto LABEL_93;
        }
        if ( v17 == 258 )
        {
          NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: ASYNC discovery took too long.\n");
          goto LABEL_13;
        }
        LastError = GetLastError();
        LODWORD(v42) = v17;
        NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: wait error: %ld %ld\n", LastError, v42);
        v19 = v17;
LABEL_38:
        v13 = NetpApiStatusToNtStatus(v19);
        goto LABEL_93;
      }
    }
    v14 = 0;
    if ( (*(_BYTE *)(a1 + 292) & 4) != 0 )
      v14 = 4096;
    v15 = 0;
    switch ( *(_DWORD *)(a1 + 280) )
    {
      case 2:
        v20 = 128;
        v14 |= 1u;
        break;
      case 3:
        v20 = 1024;
        break;
      case 4:
        v20 = 64;
        break;
      case 6:
        v20 = 256;
        v14 |= 1u;
        v15 = (unsigned __int8)SampDsIsRunning() != 0 ? 0x80 : 0;
        break;
      case 7:
        v20 = 1048704;
        v14 |= 1u;
        v15 = (unsigned __int8)SampDsIsRunning() != 0 ? 0xC1000 : 0;
        break;
      default:
        NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: invalid SecureChannelType retry %ld\n");
        v13 = -1073741730;
        GetSystemTimeAsFileTime((LPFILETIME)(a1 + 24));
        if ( !*(_DWORD *)(a1 + 284) )
        {
          *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 24);
          *(_DWORD *)(a1 + 288) = -1073741730;
        }
        goto LABEL_93;
    }
    v21 = "Synchronous";
    if ( a2 != 2 )
      v21 = "Async";
    NlPrintCsRoutine(0x200u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: Start %hs Discovery\n", v21);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl);
    v23 = hMem + 256;
    if ( IsEnabled )
    {
      v24 = NlCaptureSiteName(v23);
      v25 = v14 | 4;
      if ( !v24 )
        v25 = v14;
      v14 = v25;
      v50 = (unsigned __int16 *)((unsigned __int64)(hMem + 256) & -(__int64)(v24 != 0));
    }
    else if ( (unsigned int)NlCaptureSiteName_Old(v23) )
    {
      v14 |= 4u;
      v50 = hMem + 256;
    }
    else
    {
      v50 = 0;
    }
    v26 = *(_DWORD *)(a1 + 292);
    v27 = v15 | 0x20;
    if ( (v26 & 4) == 0 )
      v27 = v15;
    v28 = v27 | 1;
    if ( (v26 & 0x10000) == 0 )
      v28 = v27;
    v49 = v28 | 0x4000;
    RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
    NlCaptureDnsForestName(hMem);
    v29 = (a2 != 0) + 1;
    v48 = 1000 * (dword_1800F8134 + 15);
    Buf1 = *(struct _GUID **)(a1 + 176);
    v52 = *(void **)(a1 + 264);
    if ( NlDnsHasDnsServers() )
      lpWideCharStr = *(const WCHAR **)(a1 + 160);
    else
      lpWideCharStr = 0;
    v31 = v45;
    if ( v45 )
      v32 = *(const unsigned __int16 **)(a1 + 200);
    else
      v32 = 0;
    Name = NetpDcGetName(
             *(void **)(a1 + 272),
             *(const unsigned __int16 **)(*(_QWORD *)(a1 + 272) + 264LL),
             *(const unsigned __int16 **)(*(_QWORD *)(a1 + 272) + 280LL),
             v32,
             v20 & (unsigned int)-(v45 != 0),
             *(WCHAR **)(a1 + 120),
             lpWideCharStr,
             (unsigned __int64)hMem,
             v52,
             Buf1,
             v50,
             v49,
             v14,
             v48,
             v29,
             0,
             &v47);
    RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
    if ( Name )
    {
      if ( Name == 1317 )
      {
        NlPrintCsRoutine(0x100u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: DC reports no such account found.\n");
        v13 = -1073741429;
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
        v13 = -1073741730;
      }
      GetSystemTimeAsFileTime((LPFILETIME)(a1 + 24));
      if ( !*(_DWORD *)(a1 + 284) )
      {
        *(_QWORD *)(a1 + 16) = *(_QWORD *)(a1 + 24);
        *(_DWORD *)(a1 + 288) = v13;
      }
      if ( v31 )
        GetSystemTimeAsFileTime((LPFILETIME)(a1 + 32));
      goto LABEL_93;
    }
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*(_QWORD *)(a1 + 272) + 400LL));
    v34 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 272);
    *(_DWORD *)(a1 + 292) |= 0x10000u;
    RtlLeaveCriticalSection(v34 + 10);
    if ( *(_DWORD *)(a1 + 284) )
    {
      if ( v46 )
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
          0x1868u,
          v35);
      v36 = *(_DWORD *)(a1 + 408);
      if ( ((v36 & 4) != 0 || (*((_BYTE *)v47 + 264) & 0x10) == 0) && ((v36 & 8) != 0 || *((char *)v47 + 264) >= 0) )
      {
        LODWORD(v42) = *((_DWORD *)v47 + 66);
        NlPrintCsRoutine(
          0x200u,
          (struct _CLIENT_SESSION *)a1,
          L"NlDiscoverDc: Better DC not found (keeping NT old DC). 0x%lx 0x%lx\n");
        GetSystemTimeAsFileTime((LPFILETIME)(a1 + 24));
        if ( v31 )
          GetSystemTimeAsFileTime((LPFILETIME)(a1 + 32));
        goto LABEL_89;
      }
      RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
      NlSetStatusClientSession((struct _CLIENT_SESSION *)a1, -1073741730, v37, v38);
      RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
    }
    v39 = NlSetServerClientSession((struct _CLIENT_SESSION *)a1, v47, v31 != 0, 0);
    if ( !v39 )
    {
      NlPrintCsRoutine(0x200u, (struct _CLIENT_SESSION *)a1, L"NlDiscoverDc: Found DC %ws\n", *(_QWORD *)(a1 + 504));
      goto LABEL_89;
    }
    v19 = v39;
    goto LABEL_38;
  }
  if ( a2 != 2 )
  {
LABEL_92:
    v13 = 259;
    goto LABEL_93;
  }
  NlPrintCsRoutine(
    0x100u,
    (struct _CLIENT_SESSION *)a1,
    L"NlDiscoverDc: Synchronous discovery attempt of indirect trust.\n");
LABEL_13:
  v13 = -1073741730;
LABEL_93:
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  if ( v47 )
    NetpDcDerefCacheEntry(v47);
  if ( hMem )
  {
    if ( *((_DWORD *)hMem - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v13;
}

```

## disassembly

```asm
0x180069290  push    rbp
0x180069292  push    rbx
0x180069293  push    rsi
0x180069294  push    rdi
0x180069295  push    r12
0x180069297  push    r13
0x180069299  push    r14
0x18006929b  push    r15
0x18006929d  sub     rsp, 0D8h
0x1800692a4  lea     rbp, [rsp+90h]
0x1800692ac  mov     rax, cs:__security_cookie
0x1800692b3  xor     rax, rbp
0x1800692b6  mov     [rbp+80h+var_50], rax
0x1800692ba  xor     r13d, r13d
0x1800692bd  mov     [rbp+80h+var_80], r9b
0x1800692c1  mov     r12d, edx
0x1800692c4  mov     [rbp+80h+var_7F], r8b
0x1800692c8  mov     edx, 280h
0x1800692cd  mov     [rbp+80h+var_78], r13
0x1800692d1  cmp     cs:g_ulMaxStackAllocSize, rdx
0x1800692d8  mov     dil, r8b
0x1800692db  mov     rbx, rcx
0x1800692de  jb      short loc_180069325
0x1800692e0  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800692e7  add     rcx, 288h
0x1800692ee  cmp     rcx, rdx
0x1800692f1  jb      short loc_180069325
0x1800692f3  call    VerifyStackAvailable
0x1800692f8  test    eax, eax
0x1800692fa  jz      short loc_180069325
0x1800692fc  mov     eax, [rsp+110h+var_110]
0x1800692ff  mov     eax, 290h
0x180069304  sub     rsp, rax
0x180069307  lea     rcx, [rsp+3A0h+var_310]
0x18006930f  mov     eax, [rcx]
0x180069311  test    rcx, rcx
0x180069314  jz      short loc_180069325
0x180069316  lea     r15, [rcx+8]
0x18006931a  mov     dword ptr [rcx], 6B637453h
0x180069320  test    r15, r15
0x180069323  jnz     short loc_180069352
0x180069325  mov     rax, cs:g_pfnAllocate
0x18006932c  mov     ecx, 288h
0x180069331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069336  test    rax, rax
0x180069339  jz      loc_180069A07
0x18006933f  lea     r15, [rax+8]
0x180069343  mov     dword ptr [rax], 70616548h
0x180069349  test    r15, r15
0x18006934c  jz      loc_180069A07
0x180069352  lea     rsi, aOnecoreDsNetap_16; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180069359  cmp     [rbx+148h], r13d
0x180069360  ja      short loc_180069377
0x180069362  mov     r8d, 16D9h; unsigned int
0x180069368  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18006936f  mov     rdx, rsi; void *
0x180069372  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180069377  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006937e  call    cs:__imp_RtlEnterCriticalSection
0x180069385  nop     dword ptr [rax+rax+00h]
0x18006938a  mov     eax, [rbx+124h]
0x180069390  test    al, 10h
0x180069392  jnz     short loc_1800693BC
0x180069394  cmp     r12d, 2
0x180069398  jnz     loc_1800699C0
0x18006939e  lea     r8, aNldiscoverdcSy; "NlDiscoverDc: Synchronous discovery att"...
0x1800693a5  mov     ecx, 100h; unsigned int
0x1800693aa  mov     rdx, rbx; struct _CLIENT_SESSION *
0x1800693ad  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800693b2  mov     edi, 0C000005Eh
0x1800693b7  jmp     loc_1800699C5
0x1800693bc  test    dil, dil
0x1800693bf  jz      loc_180069477
0x1800693c5  cmp     r12d, 2
0x1800693c9  jnz     short loc_1800693E0
0x1800693cb  mov     r8d, 1701h; unsigned int
0x1800693d1  lea     rcx, aDiscoverytypeD; "DiscoveryType != DT_Synchronous"
0x1800693d8  mov     rdx, rsi; void *
0x1800693db  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800693e0  test    byte ptr [rbx+124h], 4
0x1800693e7  mov     edi, r13d
0x1800693ea  mov     r9d, [rbx+118h]
0x1800693f1  mov     eax, 1000h
0x1800693f6  mov     ecx, r9d
0x1800693f9  cmovnz  edi, eax
0x1800693fc  mov     r14d, r13d
0x1800693ff  mov     esi, 100h
0x180069404  sub     ecx, 2
0x180069407  jz      loc_1800695EA
0x18006940d  sub     ecx, 1
0x180069410  jz      loc_1800695E2
0x180069416  sub     ecx, 1
0x180069419  jz      loc_1800695DA
0x18006941f  sub     ecx, 2
0x180069422  jz      loc_1800695BA
0x180069428  cmp     ecx, 1
0x18006942b  jz      loc_180069597
0x180069431  lea     r8, aNldiscoverdcIn; "NlDiscoverDc: invalid SecureChannelType"...
0x180069438  mov     rdx, rbx; struct _CLIENT_SESSION *
0x18006943b  mov     ecx, esi; unsigned int
0x18006943d  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180069442  lea     rcx, [rbx+18h]; lpSystemTimeAsFileTime
0x180069446  mov     edi, 0C000005Eh
0x18006944b  call    cs:__imp_GetSystemTimeAsFileTime
0x180069452  nop     dword ptr [rax+rax+00h]
0x180069457  cmp     [rbx+11Ch], r13d
0x18006945e  jnz     loc_1800699C5
0x180069464  mov     rax, [rbx+18h]
0x180069468  mov     [rbx+10h], rax
0x18006946c  mov     [rbx+120h], edi
0x180069472  jmp     loc_1800699C5
0x180069477  test    al, 8
0x180069479  jnz     short loc_180069490
0x18006947b  mov     r8d, 1708h; unsigned int
0x180069481  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x180069488  mov     rdx, rsi; void *
0x18006948b  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180069490  mov     eax, [rbx+198h]
0x180069496  and     eax, 2
0x180069499  cmp     r12d, 2
0x18006949d  jnz     loc_1800699B1
0x1800694a3  test    eax, eax
0x1800694a5  jz      loc_1800693E0
0x1800694ab  lea     rcx, [rbx+38h]; struct _WORKER_ITEM *
0x1800694af  xor     edx, edx; int
0x1800694b1  lea     r8d, [r12-1]; int
0x1800694b6  call    ?NlQueueWorkItem@@YAHPEAU_WORKER_ITEM@@HH@Z; NlQueueWorkItem(_WORKER_ITEM *,int,int)
0x1800694bb  mov     esi, 100h
0x1800694c0  test    eax, eax
0x1800694c2  jnz     short loc_1800694D5
0x1800694c4  lea     r8, aNldiscoverdcFa; "NlDiscoverDc: Failed to boost ASYNC dis"...
0x1800694cb  mov     rdx, rbx; struct _CLIENT_SESSION *
0x1800694ce  mov     ecx, esi; unsigned int
0x1800694d0  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x1800694d5  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800694dc  call    cs:__imp_RtlLeaveCriticalSection
0x1800694e3  nop     dword ptr [rax+rax+00h]
0x1800694e8  mov     eax, cs:dword_1800F8134
0x1800694ee  mov     rcx, [rbx+1A0h]; hHandle
0x1800694f5  add     eax, 10h
0x1800694f8  imul    edx, eax, 3E8h; dwMilliseconds
0x1800694fe  call    cs:__imp_WaitForSingleObject
0x180069505  nop     dword ptr [rax+rax+00h]
0x18006950a  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180069511  mov     edi, eax
0x180069513  call    cs:__imp_RtlEnterCriticalSection
0x18006951a  nop     dword ptr [rax+rax+00h]
0x18006951f  test    edi, edi
0x180069521  jnz     short loc_18006954F
0x180069523  cmp     dword ptr [rbx+11Ch], 1
0x18006952a  jz      loc_1800699AC
0x180069530  mov     edi, [rbx+120h]
0x180069536  lea     r8, aNldiscoverdcAs_0; "NlDiscoverDc: ASYNC discovery failed so"...
0x18006953d  mov     r9d, edi
0x180069540  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180069543  mov     ecx, esi; unsigned int
0x180069545  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006954a  jmp     loc_1800699C5
0x18006954f  cmp     edi, 102h
0x180069555  jnz     short loc_180069565
0x180069557  lea     r8, aNldiscoverdcAs; "NlDiscoverDc: ASYNC discovery took too "...
0x18006955e  mov     ecx, esi
0x180069560  jmp     loc_1800693AA
0x180069565  call    cs:__imp_GetLastError
0x18006956c  nop     dword ptr [rax+rax+00h]
0x180069571  lea     r8, aNldiscoverdcWa; "NlDiscoverDc: wait error: %ld %ld\n"
0x180069578  mov     dword ptr [rsp+3A0h+var_380], edi
0x18006957c  mov     r9d, eax
0x18006957f  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180069582  mov     ecx, esi; unsigned int
0x180069584  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180069589  mov     ecx, edi
0x18006958b  call    NetpApiStatusToNtStatus
0x180069590  mov     edi, eax
0x180069592  jmp     loc_1800699C5
0x180069597  mov     r13d, 100080h
0x18006959d  or      edi, 1
0x1800695a0  call    cs:__imp_SampDsIsRunning
0x1800695a7  nop     dword ptr [rax+rax+00h]
0x1800695ac  neg     al
0x1800695ae  sbb     r14d, r14d
0x1800695b1  and     r14d, 0C1000h
0x1800695b8  jmp     short loc_1800695F3
0x1800695ba  mov     r13d, esi
0x1800695bd  or      edi, 1
0x1800695c0  call    cs:__imp_SampDsIsRunning
0x1800695c7  nop     dword ptr [rax+rax+00h]
0x1800695cc  neg     al
0x1800695ce  sbb     r14d, r14d
0x1800695d1  and     r14d, 80h
0x1800695d8  jmp     short loc_1800695F3
0x1800695da  mov     r13d, 40h ; '@'
0x1800695e0  jmp     short loc_1800695F3
0x1800695e2  mov     r13d, 400h
0x1800695e8  jmp     short loc_1800695F3
0x1800695ea  mov     r13d, 80h
0x1800695f0  or      edi, 1
0x1800695f3  cmp     r12d, 2
0x1800695f7  lea     rax, aAsync; "Async"
0x1800695fe  lea     r9, aSynchronous; "Synchronous"
0x180069605  mov     rdx, rbx; struct _CLIENT_SESSION *
0x180069608  cmovnz  r9, rax
0x18006960c  lea     r8, aNldiscoverdcSt; "NlDiscoverDc: Start %hs Discovery\n"
0x180069613  mov     ecx, 200h; unsigned int
0x180069618  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18006961d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x180069624  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x180069629  lea     rcx, [r15+200h]; unsigned __int16 *
0x180069630  test    al, al
0x180069632  jz      short loc_18006965A
0x180069634  call    ?NlCaptureSiteName@@YAHPEAG@Z; NlCaptureSiteName(ushort *)
0x180069639  mov     ecx, edi
0x18006963b  or      ecx, 4
0x18006963e  test    eax, eax
0x180069640  cmovz   ecx, edi
0x180069643  neg     eax
0x180069645  mov     edi, ecx
0x180069647  lea     rax, [r15+200h]
0x18006964e  sbb     rcx, rcx
0x180069651  and     rcx, rax
0x180069654  mov     [rbp+80h+var_68], rcx
0x180069658  jmp     short loc_18006967B
0x18006965a  call    ?NlCaptureSiteName_Old@@YAHQEAG@Z; NlCaptureSiteName_Old(ushort * const)
0x18006965f  test    eax, eax
0x180069661  jz      short loc_180069673
0x180069663  lea     rax, [r15+200h]
0x18006966a  or      edi, 4
0x18006966d  mov     [rbp+80h+var_68], rax
0x180069671  jmp     short loc_18006967B
0x180069673  mov     [rbp+80h+var_68], 0
0x18006967b  mov     edx, [rbx+124h]
0x180069681  mov     ecx, r14d
0x180069684  or      ecx, 20h
0x180069687  test    dl, 4
0x18006968a  cmovz   ecx, r14d
0x18006968e  mov     eax, ecx
0x180069690  or      eax, 1
0x180069693  bt      edx, 10h
0x180069697  cmovnb  eax, ecx
0x18006969a  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800696a1  bts     eax, 0Eh
0x1800696a5  mov     [rbp+80h+var_6C], eax
0x1800696a8  call    cs:__imp_RtlLeaveCriticalSection
0x1800696af  nop     dword ptr [rax+rax+00h]
0x1800696b4  mov     rcx, r15; unsigned __int16 *
0x1800696b7  call    ?NlCaptureDnsForestName@@YAXQEAG@Z; NlCaptureDnsForestName(ushort * const)
0x1800696bc  mov     eax, cs:dword_1800F8134
0x1800696c2  neg     r12d
0x1800696c5  sbb     r12d, r12d
0x1800696c8  add     eax, 0Fh
0x1800696cb  imul    eax, 3E8h
0x1800696d1  neg     r12d
0x1800696d4  inc     r12d
0x1800696d7  mov     [rbp+80h+var_70], eax
0x1800696da  mov     rax, [rbx+0B0h]
0x1800696e1  mov     [rbp+80h+var_60], rax
0x1800696e5  mov     rax, [rbx+108h]
0x1800696ec  mov     [rbp+80h+var_58], rax
0x1800696f0  call    ?NlDnsHasDnsServers@@YAEXZ; NlDnsHasDnsServers(void)
0x1800696f5  test    al, al
0x1800696f7  jz      short loc_180069702
0x1800696f9  mov     r8, [rbx+0A0h]
0x180069700  jmp     short loc_180069705
0x180069702  xor     r8d, r8d
0x180069705  mov     r14b, [rbp+80h+var_80]
0x180069709  mov     r10, [rbx+78h]
0x18006970d  mov     al, r14b
0x180069710  neg     al
0x180069712  sbb     edx, edx
0x180069714  and     edx, r13d
0x180069717  xor     r13d, r13d
0x18006971a  test    r14b, r14b
0x18006971d  jz      short loc_180069728
0x18006971f  mov     r9, [rbx+0C8h]
0x180069726  jmp     short loc_18006972B
0x180069728  mov     r9, r13; unsigned __int16 *
0x18006972b  mov     rcx, [rbx+110h]; void *
0x180069732  lea     rax, [rbp+80h+var_78]
0x180069736  mov     [rsp+3A0h+var_320], rax; struct _NL_DC_CACHE_ENTRY **
0x18006973e  mov     eax, [rbp+80h+var_70]
0x180069741  mov     [rsp+3A0h+var_328], r13; struct _DOMAIN_CONTROLLER_INFOW **
0x180069746  mov     [rsp+3A0h+var_330], r12d; unsigned int
0x18006974b  mov     [rsp+3A0h+var_338], eax; unsigned int
0x18006974f  mov     eax, [rbp+80h+var_6C]
0x180069752  mov     [rsp+3A0h+var_340], edi; unsigned int
0x180069756  mov     [rsp+3A0h+var_348], eax; unsigned int
0x18006975a  mov     rax, [rbp+80h+var_68]
0x18006975e  mov     [rsp+3A0h+var_350], rax; unsigned __int16 *
0x180069763  mov     rax, [rbp+80h+var_60]
0x180069767  mov     [rsp+3A0h+Buf1], rax; Buf1
0x18006976c  mov     rax, [rbp+80h+var_58]
0x180069770  mov     [rsp+3A0h+var_360], rax; void *
0x180069775  mov     [rsp+3A0h+hMem], r15; hMem
0x18006977a  mov     [rsp+3A0h+lpWideCharStr], r8; lpWideCharStr
0x18006977f  mov     r8, [rcx+118h]; unsigned __int16 *
0x180069786  mov     [rsp+3A0h+SourceString], r10; SourceString
0x18006978b  mov     dword ptr [rsp+3A0h+var_380], edx; unsigned int
0x18006978f  mov     rdx, [rcx+108h]; unsigned __int16 *
0x180069796  call    ?NetpDcGetName@@YAKPEAXPEBG11K1110PEAU_GUID@@1KKKKPEAPEAU_DOMAIN_CONTROLLER_INFOW@@PEAPEAU_NL_DC_CACHE_ENTRY@@@Z; NetpDcGetName(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ulong,ulong,ulong,ulong,_DOMAIN_CONTROLLER_INFOW * *,_NL_DC_CACHE_ENTRY * *)
0x18006979b  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
  ... truncated ...
```
