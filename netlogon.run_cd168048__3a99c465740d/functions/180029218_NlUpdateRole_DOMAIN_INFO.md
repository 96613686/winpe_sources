# NlUpdateRole(_DOMAIN_INFO *)

- ea: `0x180029218`
- end: `0x180029852`
- name: `?NlUpdateRole@@YAKPEAU_DOMAIN_INFO@@@Z`
- size: `1594`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180026518`
- `0x180026d40`

## callees

- `0x180003340`
- `0x18000c440`
- `0x18000ca88`
- `0x18000dd00`
- `0x18000e0e0`
- `0x18000e910`
- `0x18001fdb4`
- `0x18001fe18`
- `0x180021524`
- `0x1800217d8`
- `0x180025eb8`
- `0x1800283ec`
- `0x180029218`
- `0x180029bb0`
- `0x18003a51c`
- `0x18003d208`
- `0x180041f80`
- `0x18006891c`
- `0x18006c2e8`
- `0x18006cbc4`
- `0x18006d2b0`
- `0x18006e444`
- `0x18007ea48`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029535`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029535`
- `ntdll!RtlLeaveCriticalSection` at `0x180029413`
- `ntdll!RtlLeaveCriticalSection` at `0x1800294eb`
- `ntdll!RtlLeaveCriticalSection` at `0x18002954d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002974f`
- `ntdll!RtlLeaveCriticalSection` at `0x180029413`
- `ntdll!RtlLeaveCriticalSection` at `0x1800294eb`
- `ntdll!RtlLeaveCriticalSection` at `0x18002954d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002974f`
- `ntdll!RtlEnterCriticalSection` at `0x18002938f`
- `ntdll!RtlEnterCriticalSection` at `0x180029504`
- `ntdll!RtlEnterCriticalSection` at `0x180029735`
- `ntdll!RtlEnterCriticalSection` at `0x18002938f`
- `ntdll!RtlEnterCriticalSection` at `0x180029504`
- `ntdll!RtlEnterCriticalSection` at `0x180029735`
- `netutils!NetpwNameCompare` at `0x1800297d2`
- `netutils!NetpwNameCompare` at `0x1800297d2`

## string_xrefs

- `0x1800296ab`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`
- `0x180029821`: `Domain thread asked to terminate\n`
- `0x1800292f5`: `NlUpdateRole: Failed to NlGetRoleInformation. %ld\n`
- `0x18002979e`: `NlUpdateRole: Couldn't register DNS names %ld\n`
- `0x18002943e`: `NlUpdateRole Failed %ld`

## pseudocode

```c
__int64 __fastcall NlUpdateRole(struct _DOMAIN_INFO *a1)
{
  void *v2; // rsp
  unsigned __int16 *v3; // r12
  unsigned __int16 *v4; // rax
  unsigned int RoleInformation; // eax
  char *v6; // r9
  int v7; // edi
  int v8; // ecx
  int v9; // ebx
  const char *v10; // r9
  const char *v11; // rax
  HLOCAL ClientSession; // rax
  _QWORD **v14; // rbx
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  struct _GUID *Buf1; // r14
  void *v18; // rdi
  unsigned int v19; // ebx
  unsigned int v20; // esi
  unsigned __int8 HasDnsServers; // al
  const unsigned __int16 *v22; // r8
  int Name; // eax
  bool v24; // zf
  int v25; // ecx
  int v26; // eax
  unsigned __int16 **v27; // r9
  unsigned int v28; // edx
  unsigned int v29; // ecx
  struct _CLIENT_SESSION *v30; // rax
  struct _CLIENT_SESSION *v31; // rbx
  __int64 v32; // r8
  char *v33; // r9
  unsigned int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // [rsp-20h] [rbp-6B0h] BYREF
  unsigned int v37[2]; // [rsp+0h] [rbp-690h]
  PCWSTR SourceString; // [rsp+8h] [rbp-688h]
  LPCWCH lpWideCharStr; // [rsp+10h] [rbp-680h]
  struct _NL_DC_CACHE_ENTRY **v40; // [rsp+60h] [rbp-630h]
  int v41; // [rsp+70h] [rbp-620h]
  _BYTE v42[1416]; // [rsp+78h] [rbp-618h] BYREF
  unsigned __int8 v43[4]; // [rsp+690h] [rbp+0h] BYREF
  unsigned __int8 v44; // [rsp+694h] [rbp+4h] BYREF
  unsigned __int8 v45[3]; // [rsp+695h] [rbp+5h] BYREF
  unsigned __int16 *v46; // [rsp+698h] [rbp+8h] BYREF
  struct _NL_DC_CACHE_ENTRY *v47; // [rsp+6A0h] [rbp+10h] BYREF
  __int128 v48; // [rsp+6A8h] [rbp+18h] BYREF
  struct _GUID v49; // [rsp+6B8h] [rbp+28h] BYREF

  *(_DWORD *)v43 = 0;
  v49 = 0;
  v47 = 0;
  v44 = 0;
  v45[0] = 0;
  if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x60A
    || (unsigned __int64)(g_ulAdditionalProbeSize + 1554) < 0x60A
    || !(unsigned int)VerifyStackAvailable()
    || (v2 = alloca(1568), &v36 == (__int64 *)-144LL)
    || (v41 = 1801679955, (v3 = (unsigned __int16 *)v42) == 0) )
  {
    v4 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(1554);
    v3 = v4;
    if ( !v4 )
      goto LABEL_22;
    *(_DWORD *)v4 = 1885431112;
    v3 = v4 + 4;
    if ( v4 == (unsigned __int16 *)-8LL )
      goto LABEL_22;
  }
  RoleInformation = NlGetRoleInformation(a1, &v44, v45);
  *(_DWORD *)v43 = RoleInformation;
  if ( RoleInformation )
  {
    NlPrintDomRoutine(0x100u, a1, L"NlUpdateRole: Failed to NlGetRoleInformation. %ld\n", RoleInformation);
    goto LABEL_23;
  }
  v7 = 0;
  v8 = *((_DWORD *)a1 + 147);
  v9 = 2 - (v44 != 0);
  if ( v8 != v9 )
  {
    v10 = "PDC";
    if ( v9 == 1 )
    {
      v11 = "PDC";
    }
    else
    {
      v11 = "BDC";
      if ( v9 != 2 )
        v11 = "NONE";
    }
    if ( v8 != 1 )
    {
      v10 = "BDC";
      if ( v8 != 2 )
        v10 = "NONE";
    }
    NlPrintDomRoutine(0x400u, a1, L"Changing role from %hs to %hs.\n", v10, v11);
    *((_DWORD *)a1 + 147) = v9;
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a1 + 10);
    if ( !*((_QWORD *)a1 + 61) )
    {
      ClientSession = NlAllocateClientSession(
                        a1,
                        (struct _UNICODE_STRING *)((char *)a1 + 56),
                        (struct _UNICODE_STRING *)a1 + 8,
                        *((void **)a1 + 23),
                        *((struct _GUID **)a1 + 26),
                        *((_WORD *)a1 + 64) != 0 ? 20 : 16,
                        (unsigned int)(NlGlobalCDC != 0) + 6,
                        0);
      *((_QWORD *)a1 + 61) = ClientSession;
      if ( !ClientSession )
      {
        RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a1 + 10);
        NlPrintDomRoutine(0x100u, a1, L"Cannot allocate PDC ClientSession\n");
LABEL_22:
        *(_DWORD *)v43 = 8;
LABEL_23:
        v46 = 0;
        NlPrintDomRoutine(0x100u, a1, L"NlUpdateRole Failed %ld", *(unsigned int *)v43);
        v46 = (unsigned __int16 *)*(unsigned int *)v43;
        NlpWriteEventlog(0x1669u, 1u, 0x40000000u, &v46, 1u, v43, 4u);
        goto LABEL_24;
      }
    }
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a1 + 10);
    if ( *((_DWORD *)a1 + 147) == 1 )
    {
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a1 + 10);
      v14 = (_QWORD **)((char *)a1 + 640);
      while ( 1 )
      {
        v15 = *v14;
        if ( *v14 == v14 )
          break;
        if ( (_QWORD **)v15[1] != v14 || (v16 = (_QWORD *)*v15, *(_QWORD **)(*v15 + 8LL) != v15) )
          __fastfail(3u);
        *v14 = v16;
        v16[1] = v14;
        LocalFree(v15);
      }
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a1 + 10);
    }
    NlBrowserUpdate(a1, *((_DWORD *)a1 + 147));
    Buf1 = NlCaptureDomainInfo(a1, v3, &v49);
    NlCaptureDnsForestName(v3 + 256);
    v18 = (void *)*((_QWORD *)a1 + 23);
    v19 = 1000 * (dword_1800F8134 + 15);
    v20 = NlGlobalCDC != 0 ? 806913 : 16513;
    HasDnsServers = NlDnsHasDnsServers();
    v22 = (const unsigned __int16 *)*((_QWORD *)a1 + 35);
    v40 = &v47;
    Name = NetpDcGetName(
             a1,
             *((const unsigned __int16 **)a1 + 33),
             v22,
             0,
             0,
             (WCHAR *)a1 + 36,
             (LPCWCH)((unsigned __int64)v3 & -(__int64)(HasDnsServers != 0)),
             (unsigned __int64)(v3 + 256),
             v18,
             Buf1,
             0,
             v20,
             0,
             v19,
             2u,
             0,
             &v47);
    v24 = (*((_BYTE *)a1 + 592) & 0x40) == 0;
    v25 = Name;
    *(_DWORD *)v43 = Name;
    if ( !v24 || NlGlobalTerminate )
    {
      NlPrintDomRoutine(0x400u, a1, L"Domain thread asked to terminate\n");
      *(_DWORD *)v43 = 995;
      goto LABEL_23;
    }
    if ( NlGlobalCDC && !Name )
      goto LABEL_44;
    v26 = *((_DWORD *)a1 + 147);
    if ( v25 )
    {
      if ( v26 != 2 )
      {
LABEL_49:
        v7 = 0;
        goto LABEL_50;
      }
      LODWORD(lpWideCharStr) = 0;
      v27 = 0;
      SourceString = 0;
      v28 = 2;
      v37[0] = 0;
      v29 = 3096;
    }
    else
    {
      if ( v26 != 1 )
      {
LABEL_44:
        v7 = 1;
        goto LABEL_50;
      }
      v35 = *((_QWORD *)v47 + 9);
      if ( !v35 || !(unsigned int)NetpwNameCompare(*((_QWORD *)a1 + 33), v35, 4) )
        goto LABEL_49;
      v27 = (unsigned __int16 **)&v48;
      LODWORD(lpWideCharStr) = 0;
      v48 = 0;
      SourceString = 0;
      v28 = 1;
      v48 = *((unsigned __int64 *)v47 + 9);
      v29 = 3097;
      v37[0] = 1;
    }
    NlpWriteEventlog(v29, v28, 0, v27, v37[0], (unsigned __int8 *)SourceString, (unsigned int)lpWideCharStr);
    goto LABEL_49;
  }
LABEL_50:
  if ( (*((_DWORD *)a1 + 148) & 0x1000) == 0 )
    NlAssertFailed(
      "ISPRIMARYDOMAIN( DomainInfo )",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\domain.cxx",
      0xA27u,
      v6);
  if ( *((_DWORD *)a1 + 147) == 2 || NlGlobalCDC )
  {
    if ( v7 )
    {
      v30 = NlRefDomClientSession(a1);
      v31 = v30;
      if ( v30 )
      {
        if ( (unsigned int)NlTimeoutSetWriterClientSession(v30, dwMilliseconds) )
        {
          if ( *((_DWORD *)v31 + 71) != 2 )
          {
            NlSetStatusClientSession(v31, -1073741730, v32, v33);
            if ( !(unsigned int)NlSetServerClientSession(v31, v47, 0, 0) )
            {
              RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
              *((_DWORD *)v31 + 102) |= 0xCu;
              RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
              if ( NlGlobalChangeLogNetlogonState != 1 )
                NlSessionSetupEx(v31);
            }
          }
          NlResetWriterClientSession(v31);
        }
        NlUnrefClientSession(v31);
      }
    }
  }
  if ( NlGlobalChangeLogNetlogonState != 1 )
  {
    v34 = NlDnsAddDomainRecords(a1, 0);
    *(_DWORD *)v43 = v34;
    if ( v34 )
    {
      NlPrintDomRoutine(0x100u, a1, L"NlUpdateRole: Couldn't register DNS names %ld\n", v34);
      goto LABEL_23;
    }
    NlDnsForceScavenge(0, 0);
  }
  *(_DWORD *)v43 = 0;
LABEL_24:
  if ( *(_DWORD *)v43 )
    *((_DWORD *)a1 + 147) = 0;
  if ( v47 )
    NetpDcDerefCacheEntry(v47);
  if ( v3 && *((_DWORD *)v3 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return *(unsigned int *)v43;
}

```

## disassembly

```asm
0x180029218  push    rbp
0x18002921a  push    rbx
0x18002921b  push    rsi
0x18002921c  push    rdi
0x18002921d  push    r12
0x18002921f  push    r13
0x180029221  push    r14
0x180029223  push    r15
0x180029225  sub     rsp, 0D8h
0x18002922c  lea     rbp, [rsp+90h]
0x180029234  mov     rax, cs:__security_cookie
0x18002923b  xor     rax, rbp
0x18002923e  mov     [rbp+80h+var_48], rax
0x180029242  xor     esi, esi
0x180029244  mov     edx, 60Ah
0x180029249  cmp     cs:g_ulMaxStackAllocSize, rdx
0x180029250  xorps   xmm0, xmm0
0x180029253  mov     r13, rcx
0x180029256  mov     dword ptr [rbp+80h+var_80], esi
0x180029259  movups  xmmword ptr [rbp+80h+var_58.Data1], xmm0
0x18002925d  mov     [rbp+80h+var_70], rsi
0x180029261  mov     [rbp+80h+var_7C], sil
0x180029265  mov     [rbp+80h+var_7B], sil
0x180029269  jb      short loc_1800292B1
0x18002926b  mov     rcx, cs:g_ulAdditionalProbeSize
0x180029272  add     rcx, 612h
0x180029279  cmp     rcx, rdx
0x18002927c  jb      short loc_1800292B1
0x18002927e  call    VerifyStackAvailable
0x180029283  test    eax, eax
0x180029285  jz      short loc_1800292B1
0x180029287  mov     eax, [rsp+110h+var_110]
0x18002928a  mov     eax, 620h
0x18002928f  sub     rsp, rax
0x180029292  lea     r12, [rsp+730h+var_6A0]
0x18002929a  mov     eax, [r12]
0x18002929e  test    r12, r12
0x1800292a1  jz      short loc_1800292B1
0x1800292a3  mov     dword ptr [r12], 6B637453h
0x1800292ab  add     r12, 8
0x1800292af  jnz     short loc_1800292DE
0x1800292b1  mov     rax, cs:g_pfnAllocate
0x1800292b8  mov     ecx, 612h
0x1800292bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292c2  mov     r12, rax
0x1800292c5  test    rax, rax
0x1800292c8  jz      loc_180029433
0x1800292ce  mov     dword ptr [rax], 70616548h
0x1800292d4  add     r12, 8
0x1800292d8  jz      loc_180029433
0x1800292de  lea     r8, [rbp+80h+var_7B]; unsigned __int8 *
0x1800292e2  mov     rcx, r13; struct _DOMAIN_INFO *
0x1800292e5  lea     rdx, [rbp+80h+var_7C]; unsigned __int8 *
0x1800292e9  call    ?NlGetRoleInformation@@YAKPEAU_DOMAIN_INFO@@PEAE1@Z; NlGetRoleInformation(_DOMAIN_INFO *,uchar *,uchar *)
0x1800292ee  mov     dword ptr [rbp+80h+var_80], eax
0x1800292f1  test    eax, eax
0x1800292f3  jz      short loc_180029311
0x1800292f5  lea     r8, aNlupdateroleFa_0; "NlUpdateRole: Failed to NlGetRoleInform"...
0x1800292fc  mov     r9d, eax
0x1800292ff  mov     rdx, r13; struct _DOMAIN_INFO *
0x180029302  mov     ecx, 100h; unsigned int
0x180029307  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002930c  jmp     loc_18002943A
0x180029311  mov     al, [rbp+80h+var_7C]
0x180029314  mov     edi, esi
0x180029316  mov     ecx, [r13+24Ch]
0x18002931d  neg     al
0x18002931f  sbb     ebx, ebx
0x180029321  add     ebx, 2
0x180029324  cmp     ecx, ebx
0x180029326  jz      loc_180029698
0x18002932c  lea     rdx, aNone_1; "NONE"
0x180029333  lea     r9, aPdc; "PDC"
0x18002933a  cmp     ebx, 1
0x18002933d  jnz     short loc_180029344
0x18002933f  mov     rax, r9
0x180029342  jmp     short loc_180029352
0x180029344  cmp     ebx, 2
0x180029347  lea     rax, aBdc; "BDC"
0x18002934e  cmovnz  rax, rdx
0x180029352  cmp     ecx, 1
0x180029355  jz      short loc_180029365
0x180029357  cmp     ecx, 2
0x18002935a  lea     r9, aBdc; "BDC"
0x180029361  cmovnz  r9, rdx
0x180029365  lea     r8, aChangingRoleFr; "Changing role from %hs to %hs.\n"
0x18002936c  mov     qword ptr [rsp+730h+var_710], rax
0x180029371  mov     rdx, r13; struct _DOMAIN_INFO *
0x180029374  mov     ecx, 400h; unsigned int
0x180029379  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18002937e  lea     rdi, [r13+190h]
0x180029385  mov     [r13+24Ch], ebx
0x18002938c  mov     rcx, rdi; CriticalSection
0x18002938f  call    cs:__imp_RtlEnterCriticalSection
0x180029396  nop     dword ptr [rax+rax+00h]
0x18002939b  cmp     [r13+1E8h], rsi
0x1800293a2  jnz     loc_1800294E8
0x1800293a8  mov     eax, cs:?NlGlobalCDC@@3HA; int NlGlobalCDC
0x1800293ae  lea     r8, [r13+80h]
0x1800293b5  neg     eax
0x1800293b7  mov     dword ptr [rsp+730h+hMem], esi
0x1800293bb  movzx   eax, word ptr [r8]
0x1800293bf  lea     rdx, [r13+38h]
0x1800293c3  sbb     r10d, r10d
0x1800293c6  mov     rcx, r13
0x1800293c9  neg     r10d
0x1800293cc  add     r10d, 6
0x1800293d0  neg     ax
0x1800293d3  mov     dword ptr [rsp+730h+lpWideCharStr], r10d
0x1800293d8  mov     rax, [r13+0D0h]
0x1800293df  sbb     r9d, r9d
0x1800293e2  and     r9d, 4
0x1800293e6  add     r9d, 10h
0x1800293ea  mov     dword ptr [rsp+730h+SourceString], r9d
0x1800293ef  mov     r9, [r13+0B8h]
0x1800293f6  mov     qword ptr [rsp+730h+var_710], rax
0x1800293fb  call    ?NlAllocateClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@KW4_NETLOGON_SECURE_CHANNEL_TYPE@@K@Z; NlAllocateClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *,ulong,_NETLOGON_SECURE_CHANNEL_TYPE,ulong)
0x180029400  mov     [r13+1E8h], rax
0x180029407  test    rax, rax
0x18002940a  jnz     loc_1800294E8
0x180029410  mov     rcx, rdi; CriticalSection
0x180029413  call    cs:__imp_RtlLeaveCriticalSection
0x18002941a  nop     dword ptr [rax+rax+00h]
0x18002941f  lea     r8, aCannotAllocate; "Cannot allocate PDC ClientSession\n"
0x180029426  mov     rdx, r13; struct _DOMAIN_INFO *
0x180029429  mov     ecx, 100h; unsigned int
0x18002942e  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180029433  mov     dword ptr [rbp+80h+var_80], 8
0x18002943a  mov     r9d, dword ptr [rbp+80h+var_80]
0x18002943e  lea     r8, aNlupdateroleFa; "NlUpdateRole Failed %ld"
0x180029445  mov     rdx, r13; struct _DOMAIN_INFO *
0x180029448  mov     [rbp+80h+var_78], rsi
0x18002944c  mov     ecx, 100h; unsigned int
0x180029451  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180029456  mov     eax, dword ptr [rbp+80h+var_80]
0x180029459  lea     r9, [rbp+80h+var_78]; unsigned __int16 **
0x18002945d  mov     [rbp+80h+var_78], rax
0x180029461  mov     edx, 1; unsigned int
0x180029466  lea     rax, [rbp+80h+var_80]
0x18002946a  mov     dword ptr [rsp+730h+lpWideCharStr], 4; unsigned int
0x180029472  mov     [rsp+730h+SourceString], rax; unsigned __int8 *
0x180029477  mov     ecx, 1669h; unsigned int
0x18002947c  mov     r8d, 40000000h; unsigned int
0x180029482  mov     [rsp+730h+var_710], 1; unsigned int
0x18002948a  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x18002948f  cmp     dword ptr [rbp+80h+var_80], esi
0x180029492  jz      short loc_18002949B
0x180029494  mov     [r13+24Ch], esi
0x18002949b  mov     rcx, [rbp+80h+var_70]; struct _NL_DC_CACHE_ENTRY *
0x18002949f  test    rcx, rcx
0x1800294a2  jz      short loc_1800294A9
0x1800294a4  call    ?NetpDcDerefCacheEntry@@YAXPEAU_NL_DC_CACHE_ENTRY@@@Z; NetpDcDerefCacheEntry(_NL_DC_CACHE_ENTRY *)
0x1800294a9  test    r12, r12
0x1800294ac  jz      short loc_1800294C7
0x1800294ae  lea     rcx, [r12-8]
0x1800294b3  cmp     dword ptr [rcx], 70616548h
0x1800294b9  jnz     short loc_1800294C7
0x1800294bb  mov     rax, cs:g_pfnFree
0x1800294c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294c7  mov     eax, dword ptr [rbp+80h+var_80]
0x1800294ca  mov     rcx, [rbp+80h+var_48]
0x1800294ce  xor     rcx, rbp; StackCookie
0x1800294d1  call    __security_check_cookie
0x1800294d6  lea     rsp, [rbp+48h]
0x1800294da  pop     r15
0x1800294dc  pop     r14
0x1800294de  pop     r13
0x1800294e0  pop     r12
0x1800294e2  pop     rdi
0x1800294e3  pop     rsi
0x1800294e4  pop     rbx
0x1800294e5  pop     rbp
0x1800294e6  retn
0x1800294e8  mov     rcx, rdi; CriticalSection
0x1800294eb  call    cs:__imp_RtlLeaveCriticalSection
0x1800294f2  nop     dword ptr [rax+rax+00h]
0x1800294f7  cmp     dword ptr [r13+24Ch], 1
0x1800294ff  jnz     short loc_180029559
0x180029501  mov     rcx, rdi; CriticalSection
0x180029504  call    cs:__imp_RtlEnterCriticalSection
0x18002950b  nop     dword ptr [rax+rax+00h]
0x180029510  lea     rbx, [r13+280h]
0x180029517  mov     rcx, [rbx]; hMem
0x18002951a  cmp     rcx, rbx
0x18002951d  jz      short loc_18002954A
0x18002951f  cmp     [rcx+8], rbx
0x180029523  jnz     short loc_180029543
0x180029525  mov     rax, [rcx]
0x180029528  cmp     [rax+8], rcx
0x18002952c  jnz     short loc_180029543
0x18002952e  mov     [rbx], rax
0x180029531  mov     [rax+8], rbx
0x180029535  call    cs:__imp_LocalFree
0x18002953c  nop     dword ptr [rax+rax+00h]
0x180029541  jmp     short loc_180029517
0x180029543  mov     ecx, 3
0x180029548  int     29h; Win8: RtlFailFast(ecx)
0x18002954a  mov     rcx, rdi; CriticalSection
0x18002954d  call    cs:__imp_RtlLeaveCriticalSection
0x180029554  nop     dword ptr [rax+rax+00h]
0x180029559  mov     edx, [r13+24Ch]; unsigned int
0x180029560  lea     r15, [r12+200h]
0x180029568  mov     rcx, r13; struct _DOMAIN_INFO *
0x18002956b  call    ?NlBrowserUpdate@@YAXPEAU_DOMAIN_INFO@@K@Z; NlBrowserUpdate(_DOMAIN_INFO *,ulong)
0x180029570  lea     r8, [rbp+80h+var_58]; struct _GUID *
0x180029574  mov     rdx, r12; unsigned __int16 *
0x180029577  mov     rcx, r13; struct _DOMAIN_INFO *
0x18002957a  call    ?NlCaptureDomainInfo@@YAPEAU_GUID@@PEAU_DOMAIN_INFO@@QEAGPEAU1@@Z; NlCaptureDomainInfo(_DOMAIN_INFO *,ushort * const,_GUID *)
0x18002957f  mov     rcx, r15; unsigned __int16 *
0x180029582  mov     r14, rax
0x180029585  call    ?NlCaptureDnsForestName@@YAXQEAG@Z; NlCaptureDnsForestName(ushort * const)
0x18002958a  mov     ecx, cs:?NlGlobalCDC@@3HA; int NlGlobalCDC
0x180029590  mov     rdi, [r13+0B8h]
0x180029597  neg     ecx
0x180029599  mov     ecx, cs:dword_1800F8134
0x18002959f  sbb     esi, esi
0x1800295a1  add     ecx, 0Fh
0x1800295a4  and     esi, 0C0F80h
0x1800295aa  imul    ebx, ecx, 3E8h
0x1800295b0  add     esi, 4081h
0x1800295b6  call    ?NlDnsHasDnsServers@@YAEXZ; NlDnsHasDnsServers(void)
0x1800295bb  mov     r8, [r13+118h]; unsigned __int16 *
0x1800295c2  lea     rdx, [rbp+80h+var_70]
0x1800295c6  mov     [rsp+730h+var_6B0], rdx; struct _NL_DC_CACHE_ENTRY **
0x1800295ce  neg     al
0x1800295d0  mov     rdx, [r13+108h]; unsigned __int16 *
0x1800295d7  lea     rax, [r13+48h]
0x1800295db  mov     [rsp+730h+var_6B8], 0; struct _DOMAIN_CONTROLLER_INFOW **
0x1800295e4  sbb     rcx, rcx
0x1800295e7  mov     [rsp+730h+var_6C0], 2; unsigned int
0x1800295ef  and     rcx, r12
0x1800295f2  mov     [rsp+730h+var_6C8], ebx; unsigned int
0x1800295f6  xor     r9d, r9d; unsigned __int16 *
0x1800295f9  mov     [rsp+730h+var_6D0], 0; unsigned int
0x180029601  mov     [rsp+730h+var_6D8], esi; unsigned int
0x180029605  xor     esi, esi
0x180029607  mov     [rsp+730h+var_6E0], rsi; unsigned __int16 *
0x18002960c  mov     [rsp+730h+Buf1], r14; Buf1
0x180029611  mov     [rsp+730h+var_6F0], rdi; void *
0x180029616  mov     [rsp+730h+hMem], r15; hMem
0x18002961b  mov     [rsp+730h+lpWideCharStr], rcx; lpWideCharStr
0x180029620  mov     rcx, r13; void *
0x180029623  mov     [rsp+730h+SourceString], rax; SourceString
0x180029628  mov     [rsp+730h+var_710], esi; unsigned int
0x18002962c  call    ?NetpDcGetName@@YAKPEAXPEBG11K1110PEAU_GUID@@1KKKKPEAPEAU_DOMAIN_CONTROLLER_INFOW@@PEAPEAU_NL_DC_CACHE_ENTRY@@@Z; NetpDcGetName(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ulong,ulong,ulong,ulong,_DOMAIN_CONTROLLER_INFOW * *,_NL_DC_CACHE_ENTRY * *)
0x180029631  test    byte ptr [r13+250h], 40h
0x180029639  mov     ecx, eax
0x18002963b  mov     dword ptr [rbp+80h+var_80], eax
0x18002963e  jnz     loc_180029821
0x180029644  cmp     cs:?NlGlobalTerminate@@3HA, esi; int NlGlobalTerminate
0x18002964a  jnz     loc_180029821
0x180029650  cmp     cs:?NlGlobalCDC@@3HA, esi; int NlGlobalCDC
0x180029656  jz      short loc_180029663
0x180029658  test    eax, eax
0x18002965a  jnz     short loc_180029663
0x18002965c  mov     edi, 1
0x180029661  jmp     short loc_180029698
0x180029663  mov     eax, [r13+24Ch]
0x18002966a  test    ecx, ecx
0x18002966c  jz      loc_1800297AA
0x180029672  cmp     eax, 2
0x180029675  jnz     short loc_180029696
0x180029677  mov     dword ptr [rsp+730h+lpWideCharStr], esi; unsigned int
0x18002967b  xor     r9d, r9d; unsigned __int16 **
0x18002967e  mov     [rsp+730h+SourceString], rsi; unsigned __int8 *
0x180029683  mov     edx, eax; unsigned int
0x180029685  mov     [rsp+730h+var_710], esi; unsigned int
0x180029689  mov     ecx, 0C18h; unsigned int
0x18002968e  xor     r8d, r8d; unsigned int
0x180029691  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180029696  mov     edi, esi
0x180029698  test    dword ptr [r13+250h], 1000h
0x1800296a3  jnz     short loc_1800296BE
0x1800296a5  mov     r8d, 0A27h; unsigned int
0x1800296ab  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800296b2  lea     rcx, aIsprimarydomai; "ISPRIMARYDOMAIN( DomainInfo )"
0x1800296b9  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800296be  cmp     dword ptr [r13+24Ch], 2
0x1800296c6  jz      short loc_1800296D4
0x1800296c8  cmp     cs:?NlGlobalCDC@@3HA, esi; int NlGlobalCDC
0x1800296ce  jz      loc_18002977C
0x1800296d4  test    edi, edi
0x1800296d6  jz      loc_18002977C
0x1800296dc  mov     rcx, r13; struct _DOMAIN_INFO *
0x1800296df  call    ?NlRefDomClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@@Z; NlRefDomClientSession(_DOMAIN_INFO *)
0x1800296e4  mov     rbx, rax
0x1800296e7  test    rax, rax
0x1800296ea  jz      loc_18002977C
0x1800296f0  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x1800296f6  mov     rcx, rax; struct _CLIENT_SESSION *
0x1800296f9  call    ?NlTimeoutSetWriterClientSession@@YAHPEAU_CLIENT_SESSION@@K@Z; NlTimeoutSetWriterClientSession(_CLIENT_SESSION *,ulong)
0x1800296fe  test    eax, eax
0x180029700  jz      short loc_180029774
0x180029702  cmp     dword ptr [rbx+11Ch], 2
0x180029709  jz      short loc_18002976C
0x18002970b  mov     edx, 0C000005Eh; int
0x180029710  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180029713  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x180029718  mov     rdx, [rbp+80h+var_70]; struct _NL_DC_CACHE_ENTRY *
0x18002971c  xor     r9d, r9d; int
  ... truncated ...
```
