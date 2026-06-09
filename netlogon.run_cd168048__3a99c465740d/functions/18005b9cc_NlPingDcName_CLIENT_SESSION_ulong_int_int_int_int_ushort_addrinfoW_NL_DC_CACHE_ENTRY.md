# NlPingDcName(_CLIENT_SESSION *,ulong,int,int,int,int,ushort *,addrinfoW *,_NL_DC_CACHE_ENTRY * *)

- ea: `0x18005b9cc`
- end: `0x18005c146`
- name: `?NlPingDcName@@YAKPEAU_CLIENT_SESSION@@KHHHHPEAGPEAUaddrinfoW@@PEAPEAU_NL_DC_CACHE_ENTRY@@@Z`
- size: `1914`
- prototype: `unsigned int __usercall@<eax>(struct _CLIENT_SESSION *@<rcx>, unsigned int@<edx>, int@<r8d>, int@<r9d>, int, int, unsigned __int16 *, struct addrinfoW *, struct _NL_DC_CACHE_ENTRY **)`
- caller_count: `3`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180038944`
- `0x18005ae88`
- `0x18005fa30`

## callees

- `0x180004540`
- `0x18000a564`
- `0x18000af78`
- `0x18000b7bc`
- `0x18000c4e8`
- `0x18000ca88`
- `0x18000dd00`
- `0x18000e910`
- `0x18000f3e4`
- `0x18001fdb4`
- `0x180040f18`
- `0x18005aab0`
- `0x18005b9cc`
- `0x180068c10`
- `0x18006cbc4`
- `0x18007e9a8`
- `0x180082a84`
- `0x18008919c`
- `0x1800901f8`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bb89`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005bb89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c0b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c0ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c0b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c0ff`
- `ntdll!RtlLeaveCriticalSection` at `0x18005bc06`
- `ntdll!RtlLeaveCriticalSection` at `0x18005bd07`
- `ntdll!RtlLeaveCriticalSection` at `0x18005be31`
- `ntdll!RtlLeaveCriticalSection` at `0x18005be4c`
- `ntdll!RtlLeaveCriticalSection` at `0x18005bc06`
- `ntdll!RtlLeaveCriticalSection` at `0x18005bd07`
- `ntdll!RtlLeaveCriticalSection` at `0x18005be31`
- `ntdll!RtlLeaveCriticalSection` at `0x18005be4c`
- `ntdll!RtlEnterCriticalSection` at `0x18005bbb8`
- `ntdll!RtlEnterCriticalSection` at `0x18005bbb8`
- `netutils!NetApiBufferFree` at `0x18005c0cb`
- `netutils!NetApiBufferFree` at `0x18005c0cb`
- `netutils!NetpIsComputerNameValid` at `0x18005bb04`
- `netutils!NetpIsComputerNameValid` at `0x18005bb04`
- `WS2_32!GetAddrInfoW` at `0x18005baa1`
- `WS2_32!GetAddrInfoW` at `0x18005bef2`
- `WS2_32!GetAddrInfoW` at `0x18005baa1`
- `WS2_32!GetAddrInfoW` at `0x18005bef2`
- `WS2_32!FreeAddrInfoW` at `0x18005baea`
- `WS2_32!FreeAddrInfoW` at `0x18005c114`
- `WS2_32!FreeAddrInfoW` at `0x18005baea`
- `WS2_32!FreeAddrInfoW` at `0x18005c114`

## string_xrefs

- `0x18005bc5f`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`

## pseudocode

```c
__int64 __fastcall NlPingDcName(
        struct _CLIENT_SESSION *a1,
        __int16 a2,
        int a3,
        signed __int32 a4,
        int a5,
        int a6,
        unsigned __int16 *pNodeName,
        struct addrinfoW *a8,
        struct _NL_DC_CACHE_ENTRY **a9)
{
  unsigned __int16 *v9; // r12
  struct _CLIENT_SESSION *v11; // rdi
  unsigned __int16 *v12; // r13
  unsigned int v13; // ebx
  INT AddrInfoW; // esi
  unsigned __int64 v15; // rax
  unsigned int v16; // ebx
  unsigned __int16 *v17; // r14
  unsigned int v18; // esi
  unsigned __int16 *v19; // rax
  int v20; // eax
  char *v21; // r9
  int v22; // r14d
  int v23; // esi
  char v24; // r14
  const void *v25; // rdx
  size_t v26; // r8
  int v27; // edx
  int v28; // r15d
  const unsigned __int16 *v29; // rax
  const unsigned __int16 *v30; // r9
  struct _SOCKET_ADDRESS *v31; // r15
  unsigned int v32; // eax
  unsigned int v33; // r14d
  unsigned int v34; // eax
  int v35; // edi
  unsigned int v36; // r14d
  unsigned int v37; // r12d
  _OWORD *v38; // rax
  __int64 v39; // rcx
  unsigned int v41; // [rsp+70h] [rbp-A0h]
  unsigned int v42; // [rsp+90h] [rbp-80h] BYREF
  unsigned int v43; // [rsp+94h] [rbp-7Ch]
  unsigned __int16 *v44; // [rsp+98h] [rbp-78h]
  HLOCAL v45; // [rsp+A0h] [rbp-70h] BYREF
  struct _NL_DC_CACHE_ENTRY *v46; // [rsp+A8h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-60h] BYREF
  signed __int32 v48; // [rsp+B8h] [rbp-58h] BYREF
  PADDRINFOW ppResult; // [rsp+C0h] [rbp-50h] BYREF
  int v50; // [rsp+C8h] [rbp-48h]
  unsigned __int16 *v51; // [rsp+D0h] [rbp-40h] BYREF
  struct _SOCKET_ADDRESS *v52; // [rsp+D8h] [rbp-38h]
  int v53; // [rsp+E0h] [rbp-30h]
  void *Buf2[2]; // [rsp+E8h] [rbp-28h] BYREF
  ADDRINFOW *pHints; // [rsp+F8h] [rbp-18h]
  unsigned __int16 *v56; // [rsp+100h] [rbp-10h]
  struct _CLIENT_SESSION *v57; // [rsp+108h] [rbp-8h]
  struct _NL_DC_CACHE_ENTRY **v58; // [rsp+110h] [rbp+0h]
  _BYTE v59[128]; // [rsp+120h] [rbp+10h] BYREF

  v9 = pNodeName;
  pHints = a8;
  v11 = a1;
  v53 = a3;
  v57 = a1;
  v58 = a9;
  v48 = a4;
  v12 = 0;
  v56 = pNodeName;
  v13 = 0;
  v51 = 0;
  v44 = 0;
  v50 = 0;
  v52 = 0;
  hMem = 0;
  *(_OWORD *)Buf2 = 0;
  memset_0(v59, 0, sizeof(v59));
  v43 = 0;
  v42 = 0;
  v46 = 0;
  ppResult = 0;
  v45 = 0;
  if ( pNodeName )
  {
    AddrInfoW = 1210;
    if ( (a2 & 0x200) == 0 && (unsigned int)NetpDcValidDnsDomain(pNodeName) )
    {
      AddrInfoW = GetAddrInfoW(pNodeName, 0, pHints, &ppResult);
      if ( !AddrInfoW )
      {
        AddrInfoW = NetpSrvProcessAllRecords(ppResult, &v42, &hMem);
        v43 = v42;
        if ( !AddrInfoW )
        {
          if ( v42 )
          {
            v13 = 1280;
            v52 = (struct _SOCKET_ADDRESS *)hMem;
          }
        }
      }
      if ( ppResult )
      {
        FreeAddrInfoW(ppResult);
        ppResult = 0;
      }
    }
    if ( (a2 & 0x100) == 0 )
    {
      if ( (unsigned int)NetpIsComputerNameValid(pNodeName) )
      {
        v15 = -1;
        do
          ++v15;
        while ( pNodeName[v15] );
        if ( v15 <= 0xF )
        {
          AddrInfoW = 0;
          v13 |= 0xA00u;
        }
      }
    }
    if ( (v13 & 0xC00) == 0 )
    {
      NlPrintCsRoutine(0x100u, v11, L"NlPingDcName: No ping mechanism for %ws 0x%lx\n", pNodeName, AddrInfoW);
      v16 = 1311;
      v17 = 0;
      goto LABEL_90;
    }
    v12 = pNodeName;
    v51 = pNodeName;
  }
  v18 = 64;
  if ( NlGlobalMemberWorkstation || (*((_DWORD *)v11 + 73) & 0x4000) != 0 )
  {
    v19 = (unsigned __int16 *)LocalAlloc(0x40u, 0x200u);
    v44 = v19;
    v17 = v19;
    if ( !v19 )
    {
      v16 = 8;
      goto LABEL_90;
    }
    NlCaptureDnsForestName(v19);
  }
  RtlEnterCriticalSection(&NlGlobalDcDiscoveryCritSect);
  if ( !pNodeName )
  {
    v42 = 0;
    v20 = NlCaptureServerClientSession(v11, &v51, &v42);
    v22 = v20;
    if ( v20 < 0 )
    {
      NlPrintCsRoutine(0x100u, v11, L"NlPingDcName: Cannot NlCaptureServerClientSession %ld\n", (unsigned int)v20);
      RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
      v12 = v51;
      v23 = 8;
      if ( v22 != -1073741801 )
        v23 = 1311;
      v16 = v23;
      goto LABEL_89;
    }
    v24 = v42;
    if ( (v42 & 0x100) != 0 )
      v13 |= 0x100u;
    else
      v13 |= 0x200u;
    if ( (v42 & 0x40) != 0 )
    {
      v13 |= 0x400u;
      if ( !*((_DWORD *)v11 + 130) )
        NlAssertFailed(
          "ClientSession->CsServerSockAddr.iSockaddrLength != 0",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
          0x1B57u,
          v21);
      v25 = (const void *)*((_QWORD *)v11 + 64);
      v26 = *((int *)v11 + 130);
      Buf2[0] = v59;
      LODWORD(Buf2[1]) = v26;
      memcpy_0(v59, v25, v26);
      v43 = 1;
      v52 = (struct _SOCKET_ADDRESS *)Buf2;
    }
    v12 = v51;
    if ( (v24 & 0x20) != 0 )
      v13 |= 0x800u;
  }
  v27 = 0;
  if ( (*((_BYTE *)v11 + 292) & 4) != 0 )
    v13 |= 0x1000u;
  if ( *((_DWORD *)v11 + 70) == 2 )
  {
    v18 = 128;
LABEL_50:
    v13 |= 1u;
    goto LABEL_51;
  }
  if ( *((_DWORD *)v11 + 70) == 3 )
  {
    v18 = 1024;
  }
  else if ( *((_DWORD *)v11 + 70) != 4 )
  {
    if ( *((_DWORD *)v11 + 70) == 6 )
    {
      v18 = 256;
      v27 = 128;
    }
    else
    {
      if ( *((_DWORD *)v11 + 70) != 7 )
      {
        NlPrintCsRoutine(0x100u, v11, L"NlPingDcName: invalid SecureChannelType %ld\n");
        v16 = 1311;
        RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
        goto LABEL_89;
      }
      v18 = 1048704;
      v27 = 790528;
    }
    goto LABEL_50;
  }
LABEL_51:
  v50 = 1;
  v28 = v27 | 0x200;
  v29 = v12 + 2;
  if ( !v48 )
    v28 = v27;
  v48 = v28;
  if ( pNodeName )
    v29 = v12;
  if ( a5 )
  {
    v30 = (const unsigned __int16 *)*((_QWORD *)v11 + 25);
  }
  else
  {
    v30 = 0;
    v18 = 0;
  }
  v17 = v44;
  v41 = v28;
  v31 = v52;
  v32 = NetpDcInitializeContext(
          *((void **)v11 + 34),
          *(const unsigned __int16 **)(*((_QWORD *)v11 + 34) + 264LL),
          *(const unsigned __int16 **)(*((_QWORD *)v11 + 34) + 280LL),
          v30,
          v18,
          *((const unsigned __int16 **)v11 + 15),
          *((const unsigned __int16 **)v11 + 20),
          v44,
          *((void **)v11 + 33),
          *((struct _GUID **)v11 + 22),
          0,
          v29,
          v52,
          v43,
          v41,
          v13,
          3,
          (struct _NL_GETDC_CONTEXT **)&v45);
  v16 = v32;
  if ( v32 )
  {
    NlPrintCsRoutine(0x100u, v11, L"NlPingDcName: Cannot NetpDcInitializeContext 0x%lx\n", v32);
    RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
    goto LABEL_90;
  }
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  v33 = 0;
  v43 = 0;
LABEL_61:
  v42 = 0;
  if ( v46 )
  {
    NetpDcDerefCacheEntry(v46);
    v46 = 0;
  }
  v34 = NlPingDcNameWithContext((struct _NL_GETDC_CONTEXT *)v45, 2u, 1u, 1000 * (dword_1800F8134 + 15), 0, &v46);
  v16 = v34;
  if ( v34 )
  {
    if ( v34 == 8
      || !v31
      || v9
      || v33 == 1
      || GetAddrInfoW(v12 + 2, 0, pHints, &ppResult)
      || (unsigned int)NetpSrvProcessAllRecords(ppResult, &v42, &hMem)
      || !v42 )
    {
      goto LABEL_89;
    }
    v35 = (int)Buf2[1];
    v36 = 0;
    v37 = 0;
    while ( 1 )
    {
      v38 = hMem;
      if ( *((_DWORD *)hMem + 4 * v37 + 2) != v35 )
        goto LABEL_75;
      if ( memcmp_0(*((const void **)hMem + 2 * v37), Buf2[0], v35) )
        break;
LABEL_76:
      if ( ++v37 >= v42 )
      {
        v11 = v57;
        if ( !v36 )
          goto LABEL_89;
        NetpDcFreeAddressList((struct _NL_GETDC_CONTEXT *)v45);
        if ( NetpDcProcessAddressList(
               (struct _NL_GETDC_CONTEXT *)v45,
               v12 + 2,
               (struct _SOCKET_ADDRESS *)hMem,
               v36,
               0,
               0) )
        {
          goto LABEL_89;
        }
        NlPrintCsRoutine(0x100u, v11, L"NlPingDcName: Retry DC ping for %lu new addresses\n", v36);
        v9 = v56;
        v33 = v43 + 1;
        v31 = v52;
        v43 = v33;
        if ( v33 >= 2 )
          goto LABEL_89;
        goto LABEL_61;
      }
    }
    v38 = hMem;
LABEL_75:
    v39 = 2LL * v36++;
    *(_OWORD *)((char *)hMem + 8 * v39) = v38[v37];
    v35 = (int)Buf2[1];
    goto LABEL_76;
  }
  if ( ((*((_BYTE *)v46 + 264) >= 0) & _bittest(&v48, 0x12u)) != 0 )
    NlCheckPingedDcNextSiteCloseness((struct _NL_GETDC_CONTEXT *)v45, v46);
  if ( v53 )
  {
    *((_DWORD *)v45 + 3) |= 1u;
    NetpDcInsertCacheEntry((struct _NL_GETDC_CONTEXT *)v45, v46);
    NlPrintCsRoutine(
      2u,
      v11,
      L"NlPingDcName: %ws: %ws: Caching pinged DC info for %ws\n",
      *((_QWORD *)v45 + 14) + 36LL,
      *(_QWORD *)(*((_QWORD *)v45 + 14) + 72LL),
      v12);
  }
  if ( !a6 || (v16 = NlSetServerClientSession(v11, v46, a5, (char *)1)) == 0 )
  {
    if ( v58 )
    {
      *v58 = v46;
      v46 = 0;
    }
  }
LABEL_89:
  v17 = v44;
LABEL_90:
  if ( hMem )
    LocalFree(hMem);
  if ( !v56 && v12 )
    NetApiBufferFree(v12);
  if ( v50 )
    NetpDcUninitializeContext(v45);
  if ( v46 )
    NetpDcDerefCacheEntry(v46);
  if ( v17 )
    LocalFree(v17);
  if ( ppResult )
    FreeAddrInfoW(ppResult);
  return v16;
}

```

## disassembly

```asm
0x18005b9cc  push    rbp
0x18005b9ce  push    rbx
0x18005b9cf  push    rsi
0x18005b9d0  push    rdi
0x18005b9d1  push    r12
0x18005b9d3  push    r13
0x18005b9d5  push    r14
0x18005b9d7  push    r15
0x18005b9d9  lea     rbp, [rsp-0A8h]
0x18005b9e1  sub     rsp, 1B8h
0x18005b9e8  mov     rax, cs:__security_cookie
0x18005b9ef  xor     rax, rsp
0x18005b9f2  mov     [rbp+0E0h+var_50], rax
0x18005b9f9  mov     rax, [rbp+0E0h+arg_38]
0x18005ba00  xor     esi, esi
0x18005ba02  mov     r12, [rbp+0E0h+pNodeName]
0x18005ba09  mov     r14d, edx
0x18005ba0c  mov     [rbp+0E0h+pHints], rax
0x18005ba10  mov     rdi, rcx
0x18005ba13  mov     rax, [rbp+0E0h+arg_40]
0x18005ba1a  xorps   xmm0, xmm0
0x18005ba1d  mov     [rbp+0E0h+var_110], r8d
0x18005ba21  xor     edx, edx; Val
0x18005ba23  mov     [rbp+0E0h+var_E8], rcx
0x18005ba27  mov     r8d, 80h; Size
0x18005ba2d  lea     rcx, [rbp+0E0h+var_D0]; void *
0x18005ba31  mov     [rbp+0E0h+var_E0], rax
0x18005ba35  mov     [rbp+0E0h+var_138], r9d
0x18005ba39  mov     r13d, esi
0x18005ba3c  mov     [rbp+0E0h+var_F0], r12
0x18005ba40  mov     ebx, esi
0x18005ba42  mov     [rbp+0E0h+var_120], rsi
0x18005ba46  mov     [rbp+0E0h+var_158], rsi
0x18005ba4a  mov     [rbp+0E0h+var_128], esi
0x18005ba4d  mov     [rbp+0E0h+var_118], rsi
0x18005ba51  mov     [rbp+0E0h+hMem], rsi
0x18005ba55  movups  xmmword ptr [rbp+0E0h+Buf2], xmm0
0x18005ba59  call    memset_0
0x18005ba5e  xor     r15d, r15d
0x18005ba61  mov     [rbp+0E0h+var_15C], esi
0x18005ba64  mov     [rbp+0E0h+var_160], esi
0x18005ba67  mov     [rbp+0E0h+var_148], r15
0x18005ba6b  mov     [rbp+0E0h+ppResult], r15
0x18005ba6f  mov     [rbp+0E0h+var_150], r15
0x18005ba73  test    r12, r12
0x18005ba76  jz      loc_18005BB68
0x18005ba7c  mov     esi, 4BAh
0x18005ba81  bt      r14d, 9
0x18005ba86  jb      short loc_18005BAFA
0x18005ba88  mov     rcx, r12; unsigned __int16 *
0x18005ba8b  call    ?NetpDcValidDnsDomain@@YAHPEBG@Z; NetpDcValidDnsDomain(ushort const *)
0x18005ba90  test    eax, eax
0x18005ba92  jz      short loc_18005BAFA
0x18005ba94  mov     r8, [rbp+0E0h+pHints]; pHints
0x18005ba98  lea     r9, [rbp+0E0h+ppResult]; ppResult
0x18005ba9c  xor     edx, edx; pServiceName
0x18005ba9e  mov     rcx, r12; pNodeName
0x18005baa1  call    cs:__imp_GetAddrInfoW
0x18005baa8  nop     dword ptr [rax+rax+00h]
0x18005baad  mov     esi, eax
0x18005baaf  test    eax, eax
0x18005bab1  jnz     short loc_18005BAE1
0x18005bab3  mov     rcx, [rbp+0E0h+ppResult]
0x18005bab7  lea     r8, [rbp+0E0h+hMem]
0x18005babb  lea     rdx, [rbp+0E0h+var_160]
0x18005babf  call    NetpSrvProcessAllRecords
0x18005bac4  mov     esi, eax
0x18005bac6  test    eax, eax
0x18005bac8  mov     eax, [rbp+0E0h+var_160]
0x18005bacb  mov     [rbp+0E0h+var_15C], eax
0x18005bace  jnz     short loc_18005BAE1
0x18005bad0  test    eax, eax
0x18005bad2  jz      short loc_18005BAE1
0x18005bad4  mov     rax, [rbp+0E0h+hMem]
0x18005bad8  mov     ebx, 500h
0x18005badd  mov     [rbp+0E0h+var_118], rax
0x18005bae1  mov     rcx, [rbp+0E0h+ppResult]; pAddrInfo
0x18005bae5  test    rcx, rcx
0x18005bae8  jz      short loc_18005BAFA
0x18005baea  call    cs:__imp_FreeAddrInfoW
0x18005baf1  nop     dword ptr [rax+rax+00h]
0x18005baf6  mov     [rbp+0E0h+ppResult], r15
0x18005bafa  bt      r14d, 8
0x18005baff  jb      short loc_18005BB31
0x18005bb01  mov     rcx, r12
0x18005bb04  call    cs:__imp_NetpIsComputerNameValid
0x18005bb0b  nop     dword ptr [rax+rax+00h]
0x18005bb10  test    eax, eax
0x18005bb12  jz      short loc_18005BB31
0x18005bb14  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005bb18  inc     rax
0x18005bb1b  cmp     [r12+rax*2], r15w
0x18005bb20  jnz     short loc_18005BB18
0x18005bb22  cmp     rax, 0Fh
0x18005bb26  ja      short loc_18005BB31
0x18005bb28  mov     esi, r15d
0x18005bb2b  or      ebx, 0A00h
0x18005bb31  test    ebx, 0C00h
0x18005bb37  jnz     short loc_18005BB61
0x18005bb39  mov     r9, r12
0x18005bb3c  mov     dword ptr [rsp+1F0h+var_1D0], esi
0x18005bb40  lea     r8, aNlpingdcnameNo; "NlPingDcName: No ping mechanism for %ws"...
0x18005bb47  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18005bb4a  mov     ecx, 100h; unsigned int
0x18005bb4f  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18005bb54  mov     ebx, 51Fh
0x18005bb59  mov     r14, r13
0x18005bb5c  jmp     loc_18005C0A8
0x18005bb61  mov     r13, r12
0x18005bb64  mov     [rbp+0E0h+var_120], r12
0x18005bb68  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r15d; int NlGlobalMemberWorkstation
0x18005bb6f  mov     esi, 40h ; '@'
0x18005bb74  jnz     short loc_18005BB82
0x18005bb76  test    dword ptr [rdi+124h], 4000h
0x18005bb80  jz      short loc_18005BBB1
0x18005bb82  mov     edx, 200h; uBytes
0x18005bb87  mov     ecx, esi; uFlags
0x18005bb89  call    cs:__imp_LocalAlloc
0x18005bb90  nop     dword ptr [rax+rax+00h]
0x18005bb95  mov     [rbp+0E0h+var_158], rax
0x18005bb99  mov     r14, rax
0x18005bb9c  test    rax, rax
0x18005bb9f  jnz     short loc_18005BBA9
0x18005bba1  lea     ebx, [rax+8]
0x18005bba4  jmp     loc_18005C0A8
0x18005bba9  mov     rcx, rax; unsigned __int16 *
0x18005bbac  call    ?NlCaptureDnsForestName@@YAXQEAG@Z; NlCaptureDnsForestName(ushort * const)
0x18005bbb1  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005bbb8  call    cs:__imp_RtlEnterCriticalSection
0x18005bbbf  nop     dword ptr [rax+rax+00h]
0x18005bbc4  test    r12, r12
0x18005bbc7  jnz     loc_18005BCB4
0x18005bbcd  lea     r8, [rbp+0E0h+var_160]; unsigned int *
0x18005bbd1  mov     [rbp+0E0h+var_160], r15d
0x18005bbd5  lea     rdx, [rbp+0E0h+var_120]; unsigned __int16 **
0x18005bbd9  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18005bbdc  call    ?NlCaptureServerClientSession@@YAJPEAU_CLIENT_SESSION@@PEAPEAGPEAK@Z; NlCaptureServerClientSession(_CLIENT_SESSION *,ushort * *,ulong *)
0x18005bbe1  mov     r14d, eax
0x18005bbe4  test    eax, eax
0x18005bbe6  jns     short loc_18005BC31
0x18005bbe8  mov     r9d, eax
0x18005bbeb  lea     r8, aNlpingdcnameCa; "NlPingDcName: Cannot NlCaptureServerCli"...
0x18005bbf2  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18005bbf5  mov     ecx, 100h; unsigned int
0x18005bbfa  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18005bbff  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005bc06  call    cs:__imp_RtlLeaveCriticalSection
0x18005bc0d  nop     dword ptr [rax+rax+00h]
0x18005bc12  mov     r13, [rbp+0E0h+var_120]
0x18005bc16  lea     esi, [r12+8]
0x18005bc1b  mov     ebx, 51Fh
0x18005bc20  cmp     r14d, 0C0000017h
0x18005bc27  cmovnz  esi, ebx
0x18005bc2a  mov     ebx, esi
0x18005bc2c  jmp     loc_18005C0A4
0x18005bc31  mov     r14d, [rbp+0E0h+var_160]
0x18005bc35  mov     eax, 100h
0x18005bc3a  test    eax, r14d
0x18005bc3d  jz      short loc_18005BC43
0x18005bc3f  or      ebx, eax
0x18005bc41  jmp     short loc_18005BC47
0x18005bc43  bts     ebx, 9
0x18005bc47  test    sil, r14b
0x18005bc4a  jz      short loc_18005BCA6
0x18005bc4c  bts     ebx, 0Ah
0x18005bc50  cmp     [rdi+208h], r15d
0x18005bc57  jnz     short loc_18005BC72
0x18005bc59  mov     r8d, 1B57h; unsigned int
0x18005bc5f  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18005bc66  lea     rcx, aClientsessionC_9; "ClientSession->CsServerSockAddr.iSockad"...
0x18005bc6d  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18005bc72  movsxd  rax, dword ptr [rdi+208h]
0x18005bc79  lea     rcx, [rbp+0E0h+var_D0]
0x18005bc7d  mov     rdx, [rdi+200h]; Src
0x18005bc84  mov     r8, rax; Size
0x18005bc87  mov     [rbp+0E0h+Buf2], rcx
0x18005bc8b  lea     rcx, [rbp+0E0h+var_D0]; void *
0x18005bc8f  mov     dword ptr [rbp+0E0h+Buf2+8], eax
0x18005bc92  call    memcpy_0
0x18005bc97  lea     rax, [rbp+0E0h+Buf2]
0x18005bc9b  mov     [rbp+0E0h+var_15C], 1
0x18005bca2  mov     [rbp+0E0h+var_118], rax
0x18005bca6  mov     r13, [rbp+0E0h+var_120]
0x18005bcaa  test    r14b, 20h
0x18005bcae  jz      short loc_18005BCB4
0x18005bcb0  bts     ebx, 0Bh
0x18005bcb4  test    byte ptr [rdi+124h], 4
0x18005bcbb  mov     edx, r15d
0x18005bcbe  jz      short loc_18005BCC4
0x18005bcc0  bts     ebx, 0Ch
0x18005bcc4  mov     r9d, [rdi+118h]
0x18005bccb  mov     ecx, r9d
0x18005bcce  sub     ecx, 2
0x18005bcd1  jz      short loc_18005BD35
0x18005bcd3  sub     ecx, 1
0x18005bcd6  jz      short loc_18005BD2E
0x18005bcd8  sub     ecx, 1
0x18005bcdb  jz      short loc_18005BD3D
0x18005bcdd  sub     ecx, 2
0x18005bce0  jz      short loc_18005BD24
0x18005bce2  cmp     ecx, 1
0x18005bce5  jz      short loc_18005BD18
0x18005bce7  lea     r8, aNlpingdcnameIn; "NlPingDcName: invalid SecureChannelType"...
0x18005bcee  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18005bcf1  mov     ecx, 100h; unsigned int
0x18005bcf6  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18005bcfb  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005bd02  mov     ebx, 51Fh
0x18005bd07  call    cs:__imp_RtlLeaveCriticalSection
0x18005bd0e  nop     dword ptr [rax+rax+00h]
0x18005bd13  jmp     loc_18005C0A4
0x18005bd18  mov     esi, 100080h
0x18005bd1d  mov     edx, 0C1000h
0x18005bd22  jmp     short loc_18005BD3A
0x18005bd24  mov     esi, 100h
0x18005bd29  lea     edx, [rsi-80h]
0x18005bd2c  jmp     short loc_18005BD3A
0x18005bd2e  mov     esi, 400h
0x18005bd33  jmp     short loc_18005BD3D
0x18005bd35  mov     esi, 80h
0x18005bd3a  or      ebx, 1
0x18005bd3d  mov     r15d, edx
0x18005bd40  mov     [rbp+0E0h+var_128], 1
0x18005bd47  bts     r15d, 9
0x18005bd4c  lea     rax, [r13+4]
0x18005bd50  cmp     [rbp+0E0h+var_138], 0
0x18005bd54  cmovz   r15d, edx
0x18005bd58  mov     [rbp+0E0h+var_138], r15d
0x18005bd5c  test    r12, r12
0x18005bd5f  jz      short loc_18005BD64
0x18005bd61  mov     rax, r13
0x18005bd64  cmp     [rbp+0E0h+arg_20], 0
0x18005bd6b  mov     rdx, [rdi+0B0h]
0x18005bd72  mov     r8, [rdi+108h]
0x18005bd79  mov     r10, [rdi+0A0h]
0x18005bd80  mov     r11, [rdi+78h]
0x18005bd84  jz      short loc_18005BD8F
0x18005bd86  mov     r9, [rdi+0C8h]
0x18005bd8d  jmp     short loc_18005BD94
0x18005bd8f  xor     r9d, r9d; unsigned __int16 *
0x18005bd92  xor     esi, esi
0x18005bd94  mov     rcx, [rdi+110h]; void *
0x18005bd9b  lea     r14, [rbp+0E0h+var_150]
0x18005bd9f  mov     [rsp+1F0h+var_168], r14; struct _NL_GETDC_CONTEXT **
0x18005bda7  mov     r14, [rbp+0E0h+var_158]
0x18005bdab  mov     dword ptr [rsp+1F0h+var_170], 3; char
0x18005bdb6  mov     [rsp+1F0h+var_178], ebx; unsigned int
0x18005bdba  mov     ebx, [rbp+0E0h+var_15C]
0x18005bdbd  mov     [rsp+1F0h+var_180], r15d; unsigned int
0x18005bdc2  mov     r15, [rbp+0E0h+var_118]
0x18005bdc6  mov     [rsp+1F0h+var_188], ebx; unsigned int
0x18005bdca  mov     [rsp+1F0h+var_190], r15; struct _SOCKET_ADDRESS *
0x18005bdcf  mov     [rsp+1F0h+var_198], rax; unsigned __int16 *
0x18005bdd4  mov     [rsp+1F0h+var_1A0], 0; unsigned __int16 *
0x18005bddd  mov     [rsp+1F0h+var_1A8], rdx; struct _GUID *
0x18005bde2  mov     rdx, [rcx+108h]; unsigned __int16 *
0x18005bde9  mov     [rsp+1F0h+var_1B0], r8; void *
0x18005bdee  mov     r8, [rcx+118h]; unsigned __int16 *
0x18005bdf5  mov     [rsp+1F0h+var_1B8], r14; unsigned __int16 *
0x18005bdfa  mov     [rsp+1F0h+var_1C0], r10; unsigned __int16 *
0x18005bdff  mov     [rsp+1F0h+var_1C8], r11; unsigned __int16 *
0x18005be04  mov     dword ptr [rsp+1F0h+var_1D0], esi; unsigned int
0x18005be08  call    ?NetpDcInitializeContext@@YAKPEAXPEBG11K1110PEAU_GUID@@11PEAU_SOCKET_ADDRESS@@KKKKPEAPEAU_NL_GETDC_CONTEXT@@@Z; NetpDcInitializeContext(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ushort const *,_SOCKET_ADDRESS *,ulong,ulong,ulong,ulong,_NL_GETDC_CONTEXT * *)
0x18005be0d  mov     ebx, eax
0x18005be0f  test    eax, eax
0x18005be11  jz      short loc_18005BE45
0x18005be13  mov     r9d, eax
0x18005be16  lea     r8, aNlpingdcnameCa_0; "NlPingDcName: Cannot NetpDcInitializeCo"...
0x18005be1d  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18005be20  mov     ecx, 100h; unsigned int
0x18005be25  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18005be2a  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005be31  call    cs:__imp_RtlLeaveCriticalSection
0x18005be38  nop     dword ptr [rax+rax+00h]
0x18005be3d  xor     r15d, r15d
0x18005be40  jmp     loc_18005C0A8
0x18005be45  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005be4c  call    cs:__imp_RtlLeaveCriticalSection
0x18005be53  nop     dword ptr [rax+rax+00h]
0x18005be58  xor     r14d, r14d
0x18005be5b  mov     [rbp+0E0h+var_15C], r14d
0x18005be5f  lea     esi, [r14+8]
0x18005be63  mov     rcx, [rbp+0E0h+var_148]; struct _NL_DC_CACHE_ENTRY *
0x18005be67  mov     [rbp+0E0h+var_160], 0
0x18005be6e  test    rcx, rcx
0x18005be71  jz      short loc_18005BE80
0x18005be73  call    ?NetpDcDerefCacheEntry@@YAXPEAU_NL_DC_CACHE_ENTRY@@@Z; NetpDcDerefCacheEntry(_NL_DC_CACHE_ENTRY *)
0x18005be78  mov     [rbp+0E0h+var_148], 0
0x18005be80  mov     eax, cs:dword_1800F8134
0x18005be86  mov     r8b, 1; unsigned __int8
0x18005be89  mov     rcx, [rbp+0E0h+var_150]; struct _NL_GETDC_CONTEXT *
0x18005be8d  add     eax, 0Fh
0x18005be90  imul    r9d, eax, 3E8h; unsigned int
0x18005be97  mov     edx, 2; unsigned int
0x18005be9c  lea     rax, [rbp+0E0h+var_148]
0x18005bea0  mov     [rsp+1F0h+var_1C8], rax; struct _NL_DC_CACHE_ENTRY **
0x18005bea5  mov     [rsp+1F0h+var_1D0], 0; int *
0x18005beae  call    ?NlPingDcNameWithContext@@YAKPEAU_NL_GETDC_CONTEXT@@KEKPEAHPEAPEAU_NL_DC_CACHE_ENTRY@@@Z; NlPingDcNameWithContext(_NL_GETDC_CONTEXT *,ulong,uchar,ulong,int *,_NL_DC_CACHE_ENTRY * *)
0x18005beb3  mov     ebx, eax
0x18005beb5  test    eax, eax
  ... truncated ...
```
