# NlPingDcName(_CLIENT_SESSION *,ulong,int,int,int,int,ushort *,addrinfoW *,_NL_DC_CACHE_ENTRY * *)

- ea: `0x180057aec`
- end: `0x180058211`
- name: `?NlPingDcName@@YAKPEAU_CLIENT_SESSION@@KHHHHPEAGPEAUaddrinfoW@@PEAPEAU_NL_DC_CACHE_ENTRY@@@Z`
- size: `1829`
- prototype: `unsigned int __usercall@<eax>(struct _CLIENT_SESSION *@<rcx>, unsigned int@<edx>, int@<r8d>, int@<r9d>, int, int, unsigned __int16 *, struct addrinfoW *, struct _NL_DC_CACHE_ENTRY **)`
- caller_count: `3`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003682c`
- `0x18005703c`
- `0x18005b7e0`

## callees

- `0x1800042b0`
- `0x180009fb0`
- `0x18000a9ac`
- `0x18000b1c4`
- `0x18000be30`
- `0x18000c3ac`
- `0x18000d710`
- `0x18000e270`
- `0x18000ed34`
- `0x18001ef7c`
- `0x18003e71c`
- `0x180056cb4`
- `0x180057aec`
- `0x180064228`
- `0x180067df0`
- `0x180078e6c`
- `0x18007cdf8`
- `0x180083018`
- `0x180089aa8`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180057c97`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180057c97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058195`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800581d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058195`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800581d7`
- `ntdll!RtlLeaveCriticalSection` at `0x180057d08`
- `ntdll!RtlLeaveCriticalSection` at `0x180057e03`
- `ntdll!RtlLeaveCriticalSection` at `0x180057f27`
- `ntdll!RtlLeaveCriticalSection` at `0x180057f3c`
- `ntdll!RtlLeaveCriticalSection` at `0x180057d08`
- `ntdll!RtlLeaveCriticalSection` at `0x180057e03`
- `ntdll!RtlLeaveCriticalSection` at `0x180057f27`
- `ntdll!RtlLeaveCriticalSection` at `0x180057f3c`
- `ntdll!RtlEnterCriticalSection` at `0x180057cc0`
- `ntdll!RtlEnterCriticalSection` at `0x180057cc0`
- `netutils!NetApiBufferFree` at `0x1800581a9`
- `netutils!NetApiBufferFree` at `0x1800581a9`
- `netutils!NetpIsComputerNameValid` at `0x180057c18`
- `netutils!NetpIsComputerNameValid` at `0x180057c18`
- `WS2_32!GetAddrInfoW` at `0x180057bc1`
- `WS2_32!GetAddrInfoW` at `0x180057fdc`
- `WS2_32!GetAddrInfoW` at `0x180057bc1`
- `WS2_32!GetAddrInfoW` at `0x180057fdc`
- `WS2_32!FreeAddrInfoW` at `0x180057c04`
- `WS2_32!FreeAddrInfoW` at `0x1800581e6`
- `WS2_32!FreeAddrInfoW` at `0x180057c04`
- `WS2_32!FreeAddrInfoW` at `0x1800581e6`

## string_xrefs

- `0x180057d5b`: `onecore\ds\netapi\svcdlls\logonsrv\server\ssiapi.cxx`

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
  char *v20; // r9
  int v21; // eax
  char *v22; // r9
  int v23; // r14d
  int v24; // esi
  char v25; // r14
  const void *v26; // rdx
  size_t v27; // r8
  int v28; // edx
  int v29; // r15d
  unsigned __int16 *v30; // rax
  const unsigned __int16 *v31; // r9
  struct _SOCKET_ADDRESS *v32; // r15
  unsigned int v33; // eax
  unsigned int v34; // r14d
  unsigned int v35; // eax
  int v36; // edi
  unsigned int v37; // r14d
  unsigned int v38; // r12d
  _OWORD *v39; // rax
  __int64 v40; // rcx
  unsigned int v42; // [rsp+70h] [rbp-A0h]
  unsigned int v43; // [rsp+90h] [rbp-80h] BYREF
  unsigned int v44; // [rsp+94h] [rbp-7Ch]
  unsigned __int16 *v45; // [rsp+98h] [rbp-78h]
  HLOCAL v46; // [rsp+A0h] [rbp-70h] BYREF
  struct _NL_DC_CACHE_ENTRY *v47; // [rsp+A8h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp-60h] BYREF
  signed __int32 v49; // [rsp+B8h] [rbp-58h] BYREF
  PADDRINFOW ppResult; // [rsp+C0h] [rbp-50h] BYREF
  int v51; // [rsp+C8h] [rbp-48h]
  unsigned __int16 *v52; // [rsp+D0h] [rbp-40h] BYREF
  struct _SOCKET_ADDRESS *v53; // [rsp+D8h] [rbp-38h]
  int v54; // [rsp+E0h] [rbp-30h]
  void *Buf2[2]; // [rsp+E8h] [rbp-28h] BYREF
  ADDRINFOW *pHints; // [rsp+F8h] [rbp-18h]
  unsigned __int16 *v57; // [rsp+100h] [rbp-10h]
  struct _CLIENT_SESSION *v58; // [rsp+108h] [rbp-8h]
  struct _NL_DC_CACHE_ENTRY **v59; // [rsp+110h] [rbp+0h]
  _BYTE v60[128]; // [rsp+120h] [rbp+10h] BYREF

  v9 = pNodeName;
  pHints = a8;
  v11 = a1;
  v54 = a3;
  v58 = a1;
  v59 = a9;
  v49 = a4;
  v12 = 0;
  v57 = pNodeName;
  v13 = 0;
  v52 = 0;
  v45 = 0;
  v51 = 0;
  v53 = 0;
  hMem = 0;
  *(_OWORD *)Buf2 = 0;
  memset_0(v60, 0, sizeof(v60));
  v44 = 0;
  v43 = 0;
  v47 = 0;
  ppResult = 0;
  v46 = 0;
  if ( pNodeName )
  {
    AddrInfoW = 1210;
    if ( (a2 & 0x200) == 0 && (unsigned int)NetpDcValidDnsDomain(pNodeName) )
    {
      AddrInfoW = GetAddrInfoW(pNodeName, 0, pHints, &ppResult);
      if ( !AddrInfoW )
      {
        AddrInfoW = NetpSrvProcessAllRecords(ppResult, &v43, &hMem);
        v44 = v43;
        if ( !AddrInfoW )
        {
          if ( v43 )
          {
            v13 = 1280;
            v53 = (struct _SOCKET_ADDRESS *)hMem;
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
    v52 = pNodeName;
  }
  v18 = 64;
  if ( NlGlobalMemberWorkstation || (*((_DWORD *)v11 + 73) & 0x4000) != 0 )
  {
    v19 = (unsigned __int16 *)LocalAlloc(0x40u, 0x200u);
    v45 = v19;
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
    v43 = 0;
    v21 = NlCaptureServerClientSession(v11, (LPVOID *)&v52, &v43, v20);
    v23 = v21;
    if ( v21 < 0 )
    {
      NlPrintCsRoutine(0x100u, v11, L"NlPingDcName: Cannot NlCaptureServerClientSession %ld\n", (unsigned int)v21);
      RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
      v12 = v52;
      v24 = 8;
      if ( v23 != -1073741801 )
        v24 = 1311;
      v16 = v24;
      goto LABEL_89;
    }
    v25 = v43;
    if ( (v43 & 0x100) != 0 )
      v13 |= 0x100u;
    else
      v13 |= 0x200u;
    if ( (v43 & 0x40) != 0 )
    {
      v13 |= 0x400u;
      if ( !*((_DWORD *)v11 + 130) )
        NlAssertFailed(
          "ClientSession->CsServerSockAddr.iSockaddrLength != 0",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ssiapi.cxx",
          6997,
          v22);
      v26 = (const void *)*((_QWORD *)v11 + 64);
      v27 = *((int *)v11 + 130);
      Buf2[0] = v60;
      LODWORD(Buf2[1]) = v27;
      memcpy_0(v60, v26, v27);
      v44 = 1;
      v53 = (struct _SOCKET_ADDRESS *)Buf2;
    }
    v12 = v52;
    if ( (v25 & 0x20) != 0 )
      v13 |= 0x800u;
  }
  v28 = 0;
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
      v28 = 128;
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
      v28 = 790528;
    }
    goto LABEL_50;
  }
LABEL_51:
  v51 = 1;
  v29 = v28 | 0x200;
  v30 = v12 + 2;
  if ( !v49 )
    v29 = v28;
  v49 = v29;
  if ( pNodeName )
    v30 = v12;
  if ( a5 )
  {
    v31 = (const unsigned __int16 *)*((_QWORD *)v11 + 25);
  }
  else
  {
    v31 = 0;
    v18 = 0;
  }
  v17 = v45;
  v42 = v29;
  v32 = v53;
  v33 = NetpDcInitializeContext(
          *((void **)v11 + 34),
          *(const unsigned __int16 **)(*((_QWORD *)v11 + 34) + 264LL),
          *(const unsigned __int16 **)(*((_QWORD *)v11 + 34) + 280LL),
          v31,
          v18,
          *((const unsigned __int16 **)v11 + 15),
          *((const unsigned __int16 **)v11 + 20),
          v45,
          *((void **)v11 + 33),
          *((struct _GUID **)v11 + 22),
          0,
          v30,
          v53,
          v44,
          v42,
          v13,
          3,
          (struct _NL_GETDC_CONTEXT **)&v46);
  v16 = v33;
  if ( v33 )
  {
    NlPrintCsRoutine(0x100u, v11, L"NlPingDcName: Cannot NetpDcInitializeContext 0x%lx\n", v33);
    RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
    goto LABEL_90;
  }
  RtlLeaveCriticalSection(&NlGlobalDcDiscoveryCritSect);
  v34 = 0;
  v44 = 0;
LABEL_61:
  v43 = 0;
  if ( v47 )
  {
    NetpDcDerefCacheEntry(v47);
    v47 = 0;
  }
  v35 = NlPingDcNameWithContext((struct _NL_GETDC_CONTEXT *)v46, 2u, 1u, 1000 * (dword_1800F1134 + 15), 0, &v47);
  v16 = v35;
  if ( v35 )
  {
    if ( v35 == 8
      || !v32
      || v9
      || v34 == 1
      || GetAddrInfoW(v12 + 2, 0, pHints, &ppResult)
      || (unsigned int)NetpSrvProcessAllRecords(ppResult, &v43, &hMem)
      || !v43 )
    {
      goto LABEL_89;
    }
    v36 = (int)Buf2[1];
    v37 = 0;
    v38 = 0;
    while ( 1 )
    {
      v39 = hMem;
      if ( *((_DWORD *)hMem + 4 * v38 + 2) != v36 )
        goto LABEL_75;
      if ( memcmp_0(*((const void **)hMem + 2 * v38), Buf2[0], v36) )
        break;
LABEL_76:
      if ( ++v38 >= v43 )
      {
        v11 = v58;
        if ( !v37 )
          goto LABEL_89;
        NetpDcFreeAddressList((struct _NL_GETDC_CONTEXT *)v46);
        if ( NetpDcProcessAddressList(
               (struct _NL_GETDC_CONTEXT *)v46,
               v12 + 2,
               (struct _SOCKET_ADDRESS *)hMem,
               v37,
               0,
               0) )
        {
          goto LABEL_89;
        }
        NlPrintCsRoutine(0x100u, v11, L"NlPingDcName: Retry DC ping for %lu new addresses\n", v37);
        v9 = v57;
        v34 = v44 + 1;
        v32 = v53;
        v44 = v34;
        if ( v34 >= 2 )
          goto LABEL_89;
        goto LABEL_61;
      }
    }
    v39 = hMem;
LABEL_75:
    v40 = 2LL * v37++;
    *(_OWORD *)((char *)hMem + 8 * v40) = v39[v38];
    v36 = (int)Buf2[1];
    goto LABEL_76;
  }
  if ( ((*((_BYTE *)v47 + 264) >= 0) & _bittest(&v49, 0x12u)) != 0 )
    NlCheckPingedDcNextSiteCloseness((struct _NL_GETDC_CONTEXT *)v46, (unsigned __int16 **)v47);
  if ( v54 )
  {
    *((_DWORD *)v46 + 3) |= 1u;
    NetpDcInsertCacheEntry((struct _NL_GETDC_CONTEXT *)v46, v47);
    NlPrintCsRoutine(
      2u,
      v11,
      L"NlPingDcName: %ws: %ws: Caching pinged DC info for %ws\n",
      *((_QWORD *)v46 + 14) + 36LL,
      *(_QWORD *)(*((_QWORD *)v46 + 14) + 72LL),
      v12);
  }
  if ( !a6 || (v16 = NlSetServerClientSession(v11, v47, a5, (char *)1)) == 0 )
  {
    if ( v59 )
    {
      *v59 = v47;
      v47 = 0;
    }
  }
LABEL_89:
  v17 = v45;
LABEL_90:
  if ( hMem )
    LocalFree(hMem);
  if ( !v57 && v12 )
    NetApiBufferFree(v12);
  if ( v51 )
    NetpDcUninitializeContext(v46);
  if ( v47 )
    NetpDcDerefCacheEntry(v47);
  if ( v17 )
    LocalFree(v17);
  if ( ppResult )
    FreeAddrInfoW(ppResult);
  return v16;
}

```

## disassembly

```asm
0x180057aec  push    rbp
0x180057aee  push    rbx
0x180057aef  push    rsi
0x180057af0  push    rdi
0x180057af1  push    r12
0x180057af3  push    r13
0x180057af5  push    r14
0x180057af7  push    r15
0x180057af9  lea     rbp, [rsp-0A8h]
0x180057b01  sub     rsp, 1B8h
0x180057b08  mov     rax, cs:__security_cookie
0x180057b0f  xor     rax, rsp
0x180057b12  mov     [rbp+0E0h+var_50], rax
0x180057b19  mov     rax, [rbp+0E0h+arg_38]
0x180057b20  xor     esi, esi
0x180057b22  mov     r12, [rbp+0E0h+pNodeName]
0x180057b29  mov     r14d, edx
0x180057b2c  mov     [rbp+0E0h+pHints], rax
0x180057b30  mov     rdi, rcx
0x180057b33  mov     rax, [rbp+0E0h+arg_40]
0x180057b3a  xorps   xmm0, xmm0
0x180057b3d  mov     [rbp+0E0h+var_110], r8d
0x180057b41  xor     edx, edx; Val
0x180057b43  mov     [rbp+0E0h+var_E8], rcx
0x180057b47  mov     r8d, 80h; Size
0x180057b4d  lea     rcx, [rbp+0E0h+var_D0]; void *
0x180057b51  mov     [rbp+0E0h+var_E0], rax
0x180057b55  mov     [rbp+0E0h+var_138], r9d
0x180057b59  mov     r13d, esi
0x180057b5c  mov     [rbp+0E0h+var_F0], r12
0x180057b60  mov     ebx, esi
0x180057b62  mov     [rbp+0E0h+var_120], rsi
0x180057b66  mov     [rbp+0E0h+var_158], rsi
0x180057b6a  mov     [rbp+0E0h+var_128], esi
0x180057b6d  mov     [rbp+0E0h+var_118], rsi
0x180057b71  mov     [rbp+0E0h+hMem], rsi
0x180057b75  movups  xmmword ptr [rbp+0E0h+Buf2], xmm0
0x180057b79  call    memset_0
0x180057b7e  xor     r15d, r15d
0x180057b81  mov     [rbp+0E0h+var_15C], esi
0x180057b84  mov     [rbp+0E0h+var_160], esi
0x180057b87  mov     [rbp+0E0h+var_148], r15
0x180057b8b  mov     [rbp+0E0h+ppResult], r15
0x180057b8f  mov     [rbp+0E0h+var_150], r15
0x180057b93  test    r12, r12
0x180057b96  jz      loc_180057C76
0x180057b9c  mov     esi, 4BAh
0x180057ba1  bt      r14d, 9
0x180057ba6  jb      short loc_180057C0E
0x180057ba8  mov     rcx, r12; unsigned __int16 *
0x180057bab  call    ?NetpDcValidDnsDomain@@YAHPEBG@Z; NetpDcValidDnsDomain(ushort const *)
0x180057bb0  test    eax, eax
0x180057bb2  jz      short loc_180057C0E
0x180057bb4  mov     r8, [rbp+0E0h+pHints]; pHints
0x180057bb8  lea     r9, [rbp+0E0h+ppResult]; ppResult
0x180057bbc  xor     edx, edx; pServiceName
0x180057bbe  mov     rcx, r12; pNodeName
0x180057bc1  call    cs:__imp_GetAddrInfoW
0x180057bc7  mov     esi, eax
0x180057bc9  test    eax, eax
0x180057bcb  jnz     short loc_180057BFB
0x180057bcd  mov     rcx, [rbp+0E0h+ppResult]
0x180057bd1  lea     r8, [rbp+0E0h+hMem]
0x180057bd5  lea     rdx, [rbp+0E0h+var_160]
0x180057bd9  call    NetpSrvProcessAllRecords
0x180057bde  mov     esi, eax
0x180057be0  test    eax, eax
0x180057be2  mov     eax, [rbp+0E0h+var_160]
0x180057be5  mov     [rbp+0E0h+var_15C], eax
0x180057be8  jnz     short loc_180057BFB
0x180057bea  test    eax, eax
0x180057bec  jz      short loc_180057BFB
0x180057bee  mov     rax, [rbp+0E0h+hMem]
0x180057bf2  mov     ebx, 500h
0x180057bf7  mov     [rbp+0E0h+var_118], rax
0x180057bfb  mov     rcx, [rbp+0E0h+ppResult]; pAddrInfo
0x180057bff  test    rcx, rcx
0x180057c02  jz      short loc_180057C0E
0x180057c04  call    cs:__imp_FreeAddrInfoW
0x180057c0a  mov     [rbp+0E0h+ppResult], r15
0x180057c0e  bt      r14d, 8
0x180057c13  jb      short loc_180057C3F
0x180057c15  mov     rcx, r12
0x180057c18  call    cs:__imp_NetpIsComputerNameValid
0x180057c1e  test    eax, eax
0x180057c20  jz      short loc_180057C3F
0x180057c22  or      rax, 0FFFFFFFFFFFFFFFFh
0x180057c26  inc     rax
0x180057c29  cmp     [r12+rax*2], r15w
0x180057c2e  jnz     short loc_180057C26
0x180057c30  cmp     rax, 0Fh
0x180057c34  ja      short loc_180057C3F
0x180057c36  mov     esi, r15d
0x180057c39  or      ebx, 0A00h
0x180057c3f  test    ebx, 0C00h
0x180057c45  jnz     short loc_180057C6F
0x180057c47  mov     r9, r12
0x180057c4a  mov     dword ptr [rsp+1F0h+var_1D0], esi
0x180057c4e  lea     r8, aNlpingdcnameNo; "NlPingDcName: No ping mechanism for %ws"...
0x180057c55  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180057c58  mov     ecx, 100h; unsigned int
0x180057c5d  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180057c62  mov     ebx, 51Fh
0x180057c67  mov     r14, r13
0x180057c6a  jmp     loc_18005818C
0x180057c6f  mov     r13, r12
0x180057c72  mov     [rbp+0E0h+var_120], r12
0x180057c76  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r15d; int NlGlobalMemberWorkstation
0x180057c7d  mov     esi, 40h ; '@'
0x180057c82  jnz     short loc_180057C90
0x180057c84  test    dword ptr [rdi+124h], 4000h
0x180057c8e  jz      short loc_180057CB9
0x180057c90  mov     edx, 200h; uBytes
0x180057c95  mov     ecx, esi; uFlags
0x180057c97  call    cs:__imp_LocalAlloc
0x180057c9d  mov     [rbp+0E0h+var_158], rax
0x180057ca1  mov     r14, rax
0x180057ca4  test    rax, rax
0x180057ca7  jnz     short loc_180057CB1
0x180057ca9  lea     ebx, [rax+8]
0x180057cac  jmp     loc_18005818C
0x180057cb1  mov     rcx, rax; unsigned __int16 *
0x180057cb4  call    ?NlCaptureDnsForestName@@YAXQEAG@Z; NlCaptureDnsForestName(ushort * const)
0x180057cb9  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180057cc0  call    cs:__imp_RtlEnterCriticalSection
0x180057cc6  test    r12, r12
0x180057cc9  jnz     loc_180057DB0
0x180057ccf  lea     r8, [rbp+0E0h+var_160]; unsigned int *
0x180057cd3  mov     [rbp+0E0h+var_160], r15d
0x180057cd7  lea     rdx, [rbp+0E0h+var_120]; unsigned __int16 **
0x180057cdb  mov     rcx, rdi; struct _CLIENT_SESSION *
0x180057cde  call    ?NlCaptureServerClientSession@@YAJPEAU_CLIENT_SESSION@@PEAPEAGPEAK@Z; NlCaptureServerClientSession(_CLIENT_SESSION *,ushort * *,ulong *)
0x180057ce3  mov     r14d, eax
0x180057ce6  test    eax, eax
0x180057ce8  jns     short loc_180057D2D
0x180057cea  mov     r9d, eax
0x180057ced  lea     r8, aNlpingdcnameCa; "NlPingDcName: Cannot NlCaptureServerCli"...
0x180057cf4  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180057cf7  mov     ecx, 100h; unsigned int
0x180057cfc  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180057d01  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180057d08  call    cs:__imp_RtlLeaveCriticalSection
0x180057d0e  mov     r13, [rbp+0E0h+var_120]
0x180057d12  lea     esi, [r12+8]
0x180057d17  mov     ebx, 51Fh
0x180057d1c  cmp     r14d, 0C0000017h
0x180057d23  cmovnz  esi, ebx
0x180057d26  mov     ebx, esi
0x180057d28  jmp     loc_180058188
0x180057d2d  mov     r14d, [rbp+0E0h+var_160]
0x180057d31  mov     eax, 100h
0x180057d36  test    eax, r14d
0x180057d39  jz      short loc_180057D3F
0x180057d3b  or      ebx, eax
0x180057d3d  jmp     short loc_180057D43
0x180057d3f  bts     ebx, 9
0x180057d43  test    sil, r14b
0x180057d46  jz      short loc_180057DA2
0x180057d48  bts     ebx, 0Ah
0x180057d4c  cmp     [rdi+208h], r15d
0x180057d53  jnz     short loc_180057D6E
0x180057d55  mov     r8d, 1B55h; unsigned int
0x180057d5b  lea     rdx, aOnecoreDsNetap_27; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180057d62  lea     rcx, aClientsessionC_9; "ClientSession->CsServerSockAddr.iSockad"...
0x180057d69  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180057d6e  movsxd  rax, dword ptr [rdi+208h]
0x180057d75  lea     rcx, [rbp+0E0h+var_D0]
0x180057d79  mov     rdx, [rdi+200h]; Src
0x180057d80  mov     r8, rax; Size
0x180057d83  mov     [rbp+0E0h+Buf2], rcx
0x180057d87  lea     rcx, [rbp+0E0h+var_D0]; void *
0x180057d8b  mov     dword ptr [rbp+0E0h+Buf2+8], eax
0x180057d8e  call    memcpy_0
0x180057d93  lea     rax, [rbp+0E0h+Buf2]
0x180057d97  mov     [rbp+0E0h+var_15C], 1
0x180057d9e  mov     [rbp+0E0h+var_118], rax
0x180057da2  mov     r13, [rbp+0E0h+var_120]
0x180057da6  test    r14b, 20h
0x180057daa  jz      short loc_180057DB0
0x180057dac  bts     ebx, 0Bh
0x180057db0  test    byte ptr [rdi+124h], 4
0x180057db7  mov     edx, r15d
0x180057dba  jz      short loc_180057DC0
0x180057dbc  bts     ebx, 0Ch
0x180057dc0  mov     r9d, [rdi+118h]
0x180057dc7  mov     ecx, r9d
0x180057dca  sub     ecx, 2
0x180057dcd  jz      short loc_180057E2B
0x180057dcf  sub     ecx, 1
0x180057dd2  jz      short loc_180057E24
0x180057dd4  sub     ecx, 1
0x180057dd7  jz      short loc_180057E33
0x180057dd9  sub     ecx, 2
0x180057ddc  jz      short loc_180057E1A
0x180057dde  cmp     ecx, 1
0x180057de1  jz      short loc_180057E0E
0x180057de3  lea     r8, aNlpingdcnameIn; "NlPingDcName: invalid SecureChannelType"...
0x180057dea  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180057ded  mov     ecx, 100h; unsigned int
0x180057df2  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180057df7  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180057dfe  mov     ebx, 51Fh
0x180057e03  call    cs:__imp_RtlLeaveCriticalSection
0x180057e09  jmp     loc_180058188
0x180057e0e  mov     esi, 100080h
0x180057e13  mov     edx, 0C1000h
0x180057e18  jmp     short loc_180057E30
0x180057e1a  mov     esi, 100h
0x180057e1f  lea     edx, [rsi-80h]
0x180057e22  jmp     short loc_180057E30
0x180057e24  mov     esi, 400h
0x180057e29  jmp     short loc_180057E33
0x180057e2b  mov     esi, 80h
0x180057e30  or      ebx, 1
0x180057e33  mov     r15d, edx
0x180057e36  mov     [rbp+0E0h+var_128], 1
0x180057e3d  bts     r15d, 9
0x180057e42  lea     rax, [r13+4]
0x180057e46  cmp     [rbp+0E0h+var_138], 0
0x180057e4a  cmovz   r15d, edx
0x180057e4e  mov     [rbp+0E0h+var_138], r15d
0x180057e52  test    r12, r12
0x180057e55  jz      short loc_180057E5A
0x180057e57  mov     rax, r13
0x180057e5a  cmp     [rbp+0E0h+arg_20], 0
0x180057e61  mov     rdx, [rdi+0B0h]
0x180057e68  mov     r8, [rdi+108h]
0x180057e6f  mov     r10, [rdi+0A0h]
0x180057e76  mov     r11, [rdi+78h]
0x180057e7a  jz      short loc_180057E85
0x180057e7c  mov     r9, [rdi+0C8h]
0x180057e83  jmp     short loc_180057E8A
0x180057e85  xor     r9d, r9d; unsigned __int16 *
0x180057e88  xor     esi, esi
0x180057e8a  mov     rcx, [rdi+110h]; void *
0x180057e91  lea     r14, [rbp+0E0h+var_150]
0x180057e95  mov     [rsp+1F0h+var_168], r14; struct _NL_GETDC_CONTEXT **
0x180057e9d  mov     r14, [rbp+0E0h+var_158]
0x180057ea1  mov     dword ptr [rsp+1F0h+var_170], 3; char
0x180057eac  mov     [rsp+1F0h+var_178], ebx; unsigned int
0x180057eb0  mov     ebx, [rbp+0E0h+var_15C]
0x180057eb3  mov     [rsp+1F0h+var_180], r15d; unsigned int
0x180057eb8  mov     r15, [rbp+0E0h+var_118]
0x180057ebc  mov     [rsp+1F0h+var_188], ebx; unsigned int
0x180057ec0  mov     [rsp+1F0h+var_190], r15; struct _SOCKET_ADDRESS *
0x180057ec5  mov     [rsp+1F0h+var_198], rax; unsigned __int16 *
0x180057eca  mov     [rsp+1F0h+var_1A0], 0; unsigned __int16 *
0x180057ed3  mov     [rsp+1F0h+var_1A8], rdx; struct _GUID *
0x180057ed8  mov     rdx, [rcx+108h]; unsigned __int16 *
0x180057edf  mov     [rsp+1F0h+var_1B0], r8; void *
0x180057ee4  mov     r8, [rcx+118h]; unsigned __int16 *
0x180057eeb  mov     [rsp+1F0h+var_1B8], r14; unsigned __int16 *
0x180057ef0  mov     [rsp+1F0h+var_1C0], r10; unsigned __int16 *
0x180057ef5  mov     [rsp+1F0h+var_1C8], r11; unsigned __int16 *
0x180057efa  mov     dword ptr [rsp+1F0h+var_1D0], esi; unsigned int
0x180057efe  call    ?NetpDcInitializeContext@@YAKPEAXPEBG11K1110PEAU_GUID@@11PEAU_SOCKET_ADDRESS@@KKKKPEAPEAU_NL_GETDC_CONTEXT@@@Z; NetpDcInitializeContext(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ushort const *,_SOCKET_ADDRESS *,ulong,ulong,ulong,ulong,_NL_GETDC_CONTEXT * *)
0x180057f03  mov     ebx, eax
0x180057f05  test    eax, eax
0x180057f07  jz      short loc_180057F35
0x180057f09  mov     r9d, eax
0x180057f0c  lea     r8, aNlpingdcnameCa_0; "NlPingDcName: Cannot NetpDcInitializeCo"...
0x180057f13  mov     rdx, rdi; struct _CLIENT_SESSION *
0x180057f16  mov     ecx, 100h; unsigned int
0x180057f1b  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x180057f20  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180057f27  call    cs:__imp_RtlLeaveCriticalSection
0x180057f2d  xor     r15d, r15d
0x180057f30  jmp     loc_18005818C
0x180057f35  lea     rcx, ?NlGlobalDcDiscoveryCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180057f3c  call    cs:__imp_RtlLeaveCriticalSection
0x180057f42  xor     r14d, r14d
0x180057f45  mov     [rbp+0E0h+var_15C], r14d
0x180057f49  lea     esi, [r14+8]
0x180057f4d  mov     rcx, [rbp+0E0h+var_148]; struct _NL_DC_CACHE_ENTRY *
0x180057f51  mov     [rbp+0E0h+var_160], 0
0x180057f58  test    rcx, rcx
0x180057f5b  jz      short loc_180057F6A
0x180057f5d  call    ?NetpDcDerefCacheEntry@@YAXPEAU_NL_DC_CACHE_ENTRY@@@Z; NetpDcDerefCacheEntry(_NL_DC_CACHE_ENTRY *)
0x180057f62  mov     [rbp+0E0h+var_148], 0
0x180057f6a  mov     eax, cs:dword_1800F1134
0x180057f70  mov     r8b, 1; unsigned __int8
0x180057f73  mov     rcx, [rbp+0E0h+var_150]; struct _NL_GETDC_CONTEXT *
0x180057f77  add     eax, 0Fh
0x180057f7a  imul    r9d, eax, 3E8h; unsigned int
0x180057f81  mov     edx, 2; unsigned int
0x180057f86  lea     rax, [rbp+0E0h+var_148]
0x180057f8a  mov     [rsp+1F0h+var_1C8], rax; struct _NL_DC_CACHE_ENTRY **
0x180057f8f  mov     [rsp+1F0h+var_1D0], 0; int *
0x180057f98  call    ?NlPingDcNameWithContext@@YAKPEAU_NL_GETDC_CONTEXT@@KEKPEAHPEAPEAU_NL_DC_CACHE_ENTRY@@@Z; NlPingDcNameWithContext(_NL_GETDC_CONTEXT *,ulong,uchar,ulong,int *,_NL_DC_CACHE_ENTRY * *)
0x180057f9d  mov     ebx, eax
0x180057f9f  test    eax, eax
0x180057fa1  jz      loc_1800580DE
0x180057fa7  cmp     eax, esi
0x180057fa9  jz      loc_1800580D6
0x180057faf  test    r15, r15
0x180057fb2  jz      loc_1800580D6
0x180057fb8  xor     r15d, r15d
0x180057fbb  test    r12, r12
0x180057fbe  jnz     loc_180058188
0x180057fc4  cmp     r14d, 1
  ... truncated ...
```
