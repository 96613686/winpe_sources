# NlUpdateRole(_DOMAIN_INFO *)

- ea: `0x180027d78`
- end: `0x18002837b`
- name: `?NlUpdateRole@@YAKPEAU_DOMAIN_INFO@@@Z`
- size: `1539`
- prototype: `unsigned int __fastcall(struct _DOMAIN_INFO *)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002545c`
- `0x180025bc0`

## callees

- `0x180003220`
- `0x18000bd98`
- `0x18000c3ac`
- `0x18000d710`
- `0x18000da94`
- `0x18000e270`
- `0x18001ef7c`
- `0x18001efcc`
- `0x180020620`
- `0x1800208ac`
- `0x180024e80`
- `0x18002707c`
- `0x180027d78`
- `0x1800286ac`
- `0x1800382f8`
- `0x18003ada4`
- `0x18003f648`
- `0x180063f6c`
- `0x1800675c0`
- `0x180067df0`
- `0x180068458`
- `0x1800694d0`
- `0x180078f00`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002807c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002807c`
- `ntdll!RtlLeaveCriticalSection` at `0x180027f6d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002803e`
- `ntdll!RtlLeaveCriticalSection` at `0x18002808e`
- `ntdll!RtlLeaveCriticalSection` at `0x180028284`
- `ntdll!RtlLeaveCriticalSection` at `0x180027f6d`
- `ntdll!RtlLeaveCriticalSection` at `0x18002803e`
- `ntdll!RtlLeaveCriticalSection` at `0x18002808e`
- `ntdll!RtlLeaveCriticalSection` at `0x180028284`
- `ntdll!RtlEnterCriticalSection` at `0x180027eef`
- `ntdll!RtlEnterCriticalSection` at `0x180028051`
- `ntdll!RtlEnterCriticalSection` at `0x180028270`
- `ntdll!RtlEnterCriticalSection` at `0x180027eef`
- `ntdll!RtlEnterCriticalSection` at `0x180028051`
- `ntdll!RtlEnterCriticalSection` at `0x180028270`
- `netutils!NetpwNameCompare` at `0x180028301`
- `netutils!NetpwNameCompare` at `0x180028301`

## string_xrefs

- `0x1800281e6`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`
- `0x18002834a`: `Domain thread asked to terminate\n`
- `0x180027e55`: `NlUpdateRole: Failed to NlGetRoleInformation. %ld\n`
- `0x1800282cd`: `NlUpdateRole: Couldn't register DNS names %ld\n`
- `0x180027f92`: `NlUpdateRole Failed %ld`

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
    v19 = 1000 * (dword_1800F1134 + 15);
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
      2599,
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
0x180027d78  push    rbp
0x180027d7a  push    rbx
0x180027d7b  push    rsi
0x180027d7c  push    rdi
0x180027d7d  push    r12
0x180027d7f  push    r13
0x180027d81  push    r14
0x180027d83  push    r15
0x180027d85  sub     rsp, 0D8h
0x180027d8c  lea     rbp, [rsp+90h]
0x180027d94  mov     rax, cs:__security_cookie
0x180027d9b  xor     rax, rbp
0x180027d9e  mov     [rbp+80h+var_48], rax
0x180027da2  xor     esi, esi
0x180027da4  mov     edx, 60Ah
0x180027da9  cmp     cs:g_ulMaxStackAllocSize, rdx
0x180027db0  xorps   xmm0, xmm0
0x180027db3  mov     r13, rcx
0x180027db6  mov     dword ptr [rbp+80h+var_80], esi
0x180027db9  movups  xmmword ptr [rbp+80h+var_58.Data1], xmm0
0x180027dbd  mov     [rbp+80h+var_70], rsi
0x180027dc1  mov     [rbp+80h+var_7C], sil
0x180027dc5  mov     [rbp+80h+var_7B], sil
0x180027dc9  jb      short loc_180027E11
0x180027dcb  mov     rcx, cs:g_ulAdditionalProbeSize
0x180027dd2  add     rcx, 612h
0x180027dd9  cmp     rcx, rdx
0x180027ddc  jb      short loc_180027E11
0x180027dde  call    VerifyStackAvailable
0x180027de3  test    eax, eax
0x180027de5  jz      short loc_180027E11
0x180027de7  mov     eax, [rsp+110h+var_110]
0x180027dea  mov     eax, 620h
0x180027def  sub     rsp, rax
0x180027df2  lea     r12, [rsp+730h+var_6A0]
0x180027dfa  mov     eax, [r12]
0x180027dfe  test    r12, r12
0x180027e01  jz      short loc_180027E11
0x180027e03  mov     dword ptr [r12], 6B637453h
0x180027e0b  add     r12, 8
0x180027e0f  jnz     short loc_180027E3E
0x180027e11  mov     rax, cs:g_pfnAllocate
0x180027e18  mov     ecx, 612h
0x180027e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e22  mov     r12, rax
0x180027e25  test    rax, rax
0x180027e28  jz      loc_180027F87
0x180027e2e  mov     dword ptr [rax], 70616548h
0x180027e34  add     r12, 8
0x180027e38  jz      loc_180027F87
0x180027e3e  lea     r8, [rbp+80h+var_7B]; unsigned __int8 *
0x180027e42  mov     rcx, r13; struct _DOMAIN_INFO *
0x180027e45  lea     rdx, [rbp+80h+var_7C]; unsigned __int8 *
0x180027e49  call    ?NlGetRoleInformation@@YAKPEAU_DOMAIN_INFO@@PEAE1@Z; NlGetRoleInformation(_DOMAIN_INFO *,uchar *,uchar *)
0x180027e4e  mov     dword ptr [rbp+80h+var_80], eax
0x180027e51  test    eax, eax
0x180027e53  jz      short loc_180027E71
0x180027e55  lea     r8, aNlupdateroleFa_0; "NlUpdateRole: Failed to NlGetRoleInform"...
0x180027e5c  mov     r9d, eax
0x180027e5f  mov     rdx, r13; struct _DOMAIN_INFO *
0x180027e62  mov     ecx, 100h; unsigned int
0x180027e67  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180027e6c  jmp     loc_180027F8E
0x180027e71  mov     al, [rbp+80h+var_7C]
0x180027e74  mov     edi, esi
0x180027e76  mov     ecx, [r13+24Ch]
0x180027e7d  neg     al
0x180027e7f  sbb     ebx, ebx
0x180027e81  add     ebx, 2
0x180027e84  cmp     ecx, ebx
0x180027e86  jz      loc_1800281D3
0x180027e8c  lea     rdx, aNone_1; "NONE"
0x180027e93  lea     r9, aPdc; "PDC"
0x180027e9a  cmp     ebx, 1
0x180027e9d  jnz     short loc_180027EA4
0x180027e9f  mov     rax, r9
0x180027ea2  jmp     short loc_180027EB2
0x180027ea4  cmp     ebx, 2
0x180027ea7  lea     rax, aBdc; "BDC"
0x180027eae  cmovnz  rax, rdx
0x180027eb2  cmp     ecx, 1
0x180027eb5  jz      short loc_180027EC5
0x180027eb7  cmp     ecx, 2
0x180027eba  lea     r9, aBdc; "BDC"
0x180027ec1  cmovnz  r9, rdx
0x180027ec5  lea     r8, aChangingRoleFr; "Changing role from %hs to %hs.\n"
0x180027ecc  mov     qword ptr [rsp+730h+var_710], rax
0x180027ed1  mov     rdx, r13; struct _DOMAIN_INFO *
0x180027ed4  mov     ecx, 400h; unsigned int
0x180027ed9  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180027ede  lea     rdi, [r13+190h]
0x180027ee5  mov     [r13+24Ch], ebx
0x180027eec  mov     rcx, rdi; CriticalSection
0x180027eef  call    cs:__imp_RtlEnterCriticalSection
0x180027ef5  cmp     [r13+1E8h], rsi
0x180027efc  jnz     loc_18002803B
0x180027f02  mov     eax, cs:?NlGlobalCDC@@3HA; int NlGlobalCDC
0x180027f08  lea     r8, [r13+80h]
0x180027f0f  neg     eax
0x180027f11  mov     dword ptr [rsp+730h+hMem], esi
0x180027f15  movzx   eax, word ptr [r8]
0x180027f19  lea     rdx, [r13+38h]
0x180027f1d  sbb     r10d, r10d
0x180027f20  mov     rcx, r13
0x180027f23  neg     r10d
0x180027f26  add     r10d, 6
0x180027f2a  neg     ax
0x180027f2d  mov     dword ptr [rsp+730h+lpWideCharStr], r10d
0x180027f32  mov     rax, [r13+0D0h]
0x180027f39  sbb     r9d, r9d
0x180027f3c  and     r9d, 4
0x180027f40  add     r9d, 10h
0x180027f44  mov     dword ptr [rsp+730h+SourceString], r9d
0x180027f49  mov     r9, [r13+0B8h]
0x180027f50  mov     qword ptr [rsp+730h+var_710], rax
0x180027f55  call    ?NlAllocateClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@KW4_NETLOGON_SECURE_CHANNEL_TYPE@@K@Z; NlAllocateClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *,ulong,_NETLOGON_SECURE_CHANNEL_TYPE,ulong)
0x180027f5a  mov     [r13+1E8h], rax
0x180027f61  test    rax, rax
0x180027f64  jnz     loc_18002803B
0x180027f6a  mov     rcx, rdi; CriticalSection
0x180027f6d  call    cs:__imp_RtlLeaveCriticalSection
0x180027f73  lea     r8, aCannotAllocate; "Cannot allocate PDC ClientSession\n"
0x180027f7a  mov     rdx, r13; struct _DOMAIN_INFO *
0x180027f7d  mov     ecx, 100h; unsigned int
0x180027f82  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180027f87  mov     dword ptr [rbp+80h+var_80], 8
0x180027f8e  mov     r9d, dword ptr [rbp+80h+var_80]
0x180027f92  lea     r8, aNlupdateroleFa; "NlUpdateRole Failed %ld"
0x180027f99  mov     rdx, r13; struct _DOMAIN_INFO *
0x180027f9c  mov     [rbp+80h+var_78], rsi
0x180027fa0  mov     ecx, 100h; unsigned int
0x180027fa5  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180027faa  mov     eax, dword ptr [rbp+80h+var_80]
0x180027fad  lea     r9, [rbp+80h+var_78]; unsigned __int16 **
0x180027fb1  mov     [rbp+80h+var_78], rax
0x180027fb5  mov     edx, 1; unsigned int
0x180027fba  lea     rax, [rbp+80h+var_80]
0x180027fbe  mov     dword ptr [rsp+730h+lpWideCharStr], 4; unsigned int
0x180027fc6  mov     [rsp+730h+SourceString], rax; unsigned __int8 *
0x180027fcb  mov     ecx, 1669h; unsigned int
0x180027fd0  mov     r8d, 40000000h; unsigned int
0x180027fd6  mov     [rsp+730h+var_710], 1; unsigned int
0x180027fde  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180027fe3  cmp     dword ptr [rbp+80h+var_80], esi
0x180027fe6  jz      short loc_180027FEF
0x180027fe8  mov     [r13+24Ch], esi
0x180027fef  mov     rcx, [rbp+80h+var_70]; struct _NL_DC_CACHE_ENTRY *
0x180027ff3  test    rcx, rcx
0x180027ff6  jz      short loc_180027FFD
0x180027ff8  call    ?NetpDcDerefCacheEntry@@YAXPEAU_NL_DC_CACHE_ENTRY@@@Z; NetpDcDerefCacheEntry(_NL_DC_CACHE_ENTRY *)
0x180027ffd  test    r12, r12
0x180028000  jz      short loc_18002801B
0x180028002  lea     rcx, [r12-8]
0x180028007  cmp     dword ptr [rcx], 70616548h
0x18002800d  jnz     short loc_18002801B
0x18002800f  mov     rax, cs:g_pfnFree
0x180028016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002801b  mov     eax, dword ptr [rbp+80h+var_80]
0x18002801e  mov     rcx, [rbp+80h+var_48]
0x180028022  xor     rcx, rbp; StackCookie
0x180028025  call    __security_check_cookie
0x18002802a  lea     rsp, [rbp+48h]
0x18002802e  pop     r15
0x180028030  pop     r14
0x180028032  pop     r13
0x180028034  pop     r12
0x180028036  pop     rdi
0x180028037  pop     rsi
0x180028038  pop     rbx
0x180028039  pop     rbp
0x18002803a  retn
0x18002803b  mov     rcx, rdi; CriticalSection
0x18002803e  call    cs:__imp_RtlLeaveCriticalSection
0x180028044  cmp     dword ptr [r13+24Ch], 1
0x18002804c  jnz     short loc_180028094
0x18002804e  mov     rcx, rdi; CriticalSection
0x180028051  call    cs:__imp_RtlEnterCriticalSection
0x180028057  lea     rbx, [r13+280h]
0x18002805e  mov     rcx, [rbx]; hMem
0x180028061  cmp     rcx, rbx
0x180028064  jz      short loc_18002808B
0x180028066  cmp     [rcx+8], rbx
0x18002806a  jnz     short loc_180028084
0x18002806c  mov     rax, [rcx]
0x18002806f  cmp     [rax+8], rcx
0x180028073  jnz     short loc_180028084
0x180028075  mov     [rbx], rax
0x180028078  mov     [rax+8], rbx
0x18002807c  call    cs:__imp_LocalFree
0x180028082  jmp     short loc_18002805E
0x180028084  mov     ecx, 3
0x180028089  int     29h; Win8: RtlFailFast(ecx)
0x18002808b  mov     rcx, rdi; CriticalSection
0x18002808e  call    cs:__imp_RtlLeaveCriticalSection
0x180028094  mov     edx, [r13+24Ch]; unsigned int
0x18002809b  lea     r15, [r12+200h]
0x1800280a3  mov     rcx, r13; struct _DOMAIN_INFO *
0x1800280a6  call    ?NlBrowserUpdate@@YAXPEAU_DOMAIN_INFO@@K@Z; NlBrowserUpdate(_DOMAIN_INFO *,ulong)
0x1800280ab  lea     r8, [rbp+80h+var_58]; struct _GUID *
0x1800280af  mov     rdx, r12; unsigned __int16 *
0x1800280b2  mov     rcx, r13; struct _DOMAIN_INFO *
0x1800280b5  call    ?NlCaptureDomainInfo@@YAPEAU_GUID@@PEAU_DOMAIN_INFO@@QEAGPEAU1@@Z; NlCaptureDomainInfo(_DOMAIN_INFO *,ushort * const,_GUID *)
0x1800280ba  mov     rcx, r15; unsigned __int16 *
0x1800280bd  mov     r14, rax
0x1800280c0  call    ?NlCaptureDnsForestName@@YAXQEAG@Z; NlCaptureDnsForestName(ushort * const)
0x1800280c5  mov     ecx, cs:?NlGlobalCDC@@3HA; int NlGlobalCDC
0x1800280cb  mov     rdi, [r13+0B8h]
0x1800280d2  neg     ecx
0x1800280d4  mov     ecx, cs:dword_1800F1134
0x1800280da  sbb     esi, esi
0x1800280dc  add     ecx, 0Fh
0x1800280df  and     esi, 0C0F80h
0x1800280e5  imul    ebx, ecx, 3E8h
0x1800280eb  add     esi, 4081h
0x1800280f1  call    ?NlDnsHasDnsServers@@YAEXZ; NlDnsHasDnsServers(void)
0x1800280f6  mov     r8, [r13+118h]; unsigned __int16 *
0x1800280fd  lea     rdx, [rbp+80h+var_70]
0x180028101  mov     [rsp+730h+var_6B0], rdx; struct _NL_DC_CACHE_ENTRY **
0x180028109  neg     al
0x18002810b  mov     rdx, [r13+108h]; unsigned __int16 *
0x180028112  lea     rax, [r13+48h]
0x180028116  mov     [rsp+730h+var_6B8], 0; struct _DOMAIN_CONTROLLER_INFOW **
0x18002811f  sbb     rcx, rcx
0x180028122  mov     [rsp+730h+var_6C0], 2; unsigned int
0x18002812a  and     rcx, r12
0x18002812d  mov     [rsp+730h+var_6C8], ebx; unsigned int
0x180028131  xor     r9d, r9d; unsigned __int16 *
0x180028134  mov     [rsp+730h+var_6D0], 0; unsigned int
0x18002813c  mov     [rsp+730h+var_6D8], esi; unsigned int
0x180028140  xor     esi, esi
0x180028142  mov     [rsp+730h+var_6E0], rsi; unsigned __int16 *
0x180028147  mov     [rsp+730h+Buf1], r14; Buf1
0x18002814c  mov     [rsp+730h+var_6F0], rdi; void *
0x180028151  mov     [rsp+730h+hMem], r15; hMem
0x180028156  mov     [rsp+730h+lpWideCharStr], rcx; lpWideCharStr
0x18002815b  mov     rcx, r13; void *
0x18002815e  mov     [rsp+730h+SourceString], rax; SourceString
0x180028163  mov     [rsp+730h+var_710], esi; unsigned int
0x180028167  call    ?NetpDcGetName@@YAKPEAXPEBG11K1110PEAU_GUID@@1KKKKPEAPEAU_DOMAIN_CONTROLLER_INFOW@@PEAPEAU_NL_DC_CACHE_ENTRY@@@Z; NetpDcGetName(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ulong,ulong,ulong,ulong,_DOMAIN_CONTROLLER_INFOW * *,_NL_DC_CACHE_ENTRY * *)
0x18002816c  test    byte ptr [r13+250h], 40h
0x180028174  mov     ecx, eax
0x180028176  mov     dword ptr [rbp+80h+var_80], eax
0x180028179  jnz     loc_18002834A
0x18002817f  cmp     cs:?NlGlobalTerminate@@3HA, esi; int NlGlobalTerminate
0x180028185  jnz     loc_18002834A
0x18002818b  cmp     cs:?NlGlobalCDC@@3HA, esi; int NlGlobalCDC
0x180028191  jz      short loc_18002819E
0x180028193  test    eax, eax
0x180028195  jnz     short loc_18002819E
0x180028197  mov     edi, 1
0x18002819c  jmp     short loc_1800281D3
0x18002819e  mov     eax, [r13+24Ch]
0x1800281a5  test    ecx, ecx
0x1800281a7  jz      loc_1800282D9
0x1800281ad  cmp     eax, 2
0x1800281b0  jnz     short loc_1800281D1
0x1800281b2  mov     dword ptr [rsp+730h+lpWideCharStr], esi; unsigned int
0x1800281b6  xor     r9d, r9d; unsigned __int16 **
0x1800281b9  mov     [rsp+730h+SourceString], rsi; unsigned __int8 *
0x1800281be  mov     edx, eax; unsigned int
0x1800281c0  mov     [rsp+730h+var_710], esi; unsigned int
0x1800281c4  mov     ecx, 0C18h; unsigned int
0x1800281c9  xor     r8d, r8d; unsigned int
0x1800281cc  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x1800281d1  mov     edi, esi
0x1800281d3  test    dword ptr [r13+250h], 1000h
0x1800281de  jnz     short loc_1800281F9
0x1800281e0  mov     r8d, 0A27h; unsigned int
0x1800281e6  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800281ed  lea     rcx, aIsprimarydomai; "ISPRIMARYDOMAIN( DomainInfo )"
0x1800281f4  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800281f9  cmp     dword ptr [r13+24Ch], 2
0x180028201  jz      short loc_18002820F
0x180028203  cmp     cs:?NlGlobalCDC@@3HA, esi; int NlGlobalCDC
0x180028209  jz      loc_1800282AB
0x18002820f  test    edi, edi
0x180028211  jz      loc_1800282AB
0x180028217  mov     rcx, r13; struct _DOMAIN_INFO *
0x18002821a  call    ?NlRefDomClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@@Z; NlRefDomClientSession(_DOMAIN_INFO *)
0x18002821f  mov     rbx, rax
0x180028222  test    rax, rax
0x180028225  jz      loc_1800282AB
0x18002822b  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x180028231  mov     rcx, rax; struct _CLIENT_SESSION *
0x180028234  call    ?NlTimeoutSetWriterClientSession@@YAHPEAU_CLIENT_SESSION@@K@Z; NlTimeoutSetWriterClientSession(_CLIENT_SESSION *,ulong)
0x180028239  test    eax, eax
0x18002823b  jz      short loc_1800282A3
0x18002823d  cmp     dword ptr [rbx+11Ch], 2
0x180028244  jz      short loc_18002829B
0x180028246  mov     edx, 0C000005Eh; int
0x18002824b  mov     rcx, rbx; struct _CLIENT_SESSION *
0x18002824e  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x180028253  mov     rdx, [rbp+80h+var_70]; struct _NL_DC_CACHE_ENTRY *
0x180028257  xor     r9d, r9d; int
0x18002825a  xor     r8d, r8d; int
0x18002825d  mov     rcx, rbx; struct _CLIENT_SESSION *
0x180028260  call    ?NlSetServerClientSession@@YAKPEAU_CLIENT_SESSION@@PEAU_NL_DC_CACHE_ENTRY@@HH@Z; NlSetServerClientSession(_CLIENT_SESSION *,_NL_DC_CACHE_ENTRY *,int,int)
0x180028265  test    eax, eax
0x180028267  jnz     short loc_18002829B
0x180028269  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
  ... truncated ...
```
