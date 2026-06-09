# RasSrvrReleaseIpv6Address

- ea: `0x1800568d0`
- end: `0x180056d81`
- name: `RasSrvrReleaseIpv6Address`
- size: `1201`
- prototype: `__int64 __fastcall(struct _GUID *, struct in6_addr *Addr)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x180051368`
- `0x1800604bc`

## callees

- `0x180002bbe`
- `0x180025c98`
- `0x18004d430`
- `0x18004e19c`
- `0x1800568d0`
- `0x180058ae4`
- `0x180058b94`
- `0x18005a3f4`
- `0x18005b5d8`
- `0x180071cec`
- `0x180073664`
- `0x180075668`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!free` at `0x180056d38`
- `msvcrt!free` at `0x180056d42`
- `msvcrt!free` at `0x180056d38`
- `msvcrt!free` at `0x180056d42`
- `KERNEL32!LocalFree` at `0x180056d4b`
- `KERNEL32!LocalFree` at `0x180056d4b`
- `KERNEL32!LeaveCriticalSection` at `0x180056d58`
- `KERNEL32!LeaveCriticalSection` at `0x180056d58`
- `KERNEL32!EnterCriticalSection` at `0x1800569da`
- `KERNEL32!EnterCriticalSection` at `0x1800569da`
- `ntdll!RtlIpv6AddressToStringA` at `0x1800569cd`
- `ntdll!RtlIpv6AddressToStringA` at `0x1800569cd`

## string_xrefs

- `0x180056b97`: `RasSrvrReleaseIpv6Address: GetRoutingDomainConfigData failed: 0x%x`
- `0x180056bf6`: `Create Ipv6 Neighbor for Global addr: 0x%x`
- `0x180056c60`: `Create Ipv6 Neighbor for link-local addr: 0x%x`

## pseudocode

```c
void __fastcall RasSrvrReleaseIpv6Address(struct _GUID *a1, struct in6_addr *Addr, __int64 a3, __int64 a4)
{
  __int64 v7; // rdx
  int v8; // r15d
  int v9; // r12d
  __int64 v10; // rbx
  struct _GUID v11; // xmm1
  struct _ACQUIRED_IPv6ADDR *Aipv6Node; // rdi
  __int64 NboServerIpv6Address; // rax
  __int128 v14; // xmm1
  struct in6_addr v15; // xmm0
  unsigned int RoutingDomainConfigData; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h]
  struct _GUID Buf1; // [rsp+60h] [rbp-A0h] BYREF
  struct in6_addr v25; // [rsp+70h] [rbp-90h] BYREF
  __int128 v26; // [rsp+80h] [rbp-80h]
  __int128 v27; // [rsp+90h] [rbp-70h]
  struct in6_addr v28; // [rsp+A0h] [rbp-60h] BYREF
  int v29; // [rsp+B0h] [rbp-50h]
  _BYTE v30[56]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v31[3]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v32[30]; // [rsp+120h] [rbp+20h]
  __int16 v33; // [rsp+13Eh] [rbp+3Eh]
  CHAR S[128]; // [rsp+140h] [rbp+40h] BYREF
  int v35; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v36[2044]; // [rsp+1C4h] [rbp+C4h] BYREF

  v31[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v31[2] = *(_OWORD *)L"000-0000-000000000000}";
  v31[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  *(_OWORD *)v32 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v32[14] = *(_OWORD *)L"000000}";
  v23 = a4;
  v22[0] = 33022;
  v33 = 0;
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v21 = 1;
  if ( !memcmp_0(a1, &GUID_NULL, 0x10u) )
  {
    v8 = 1;
  }
  else
  {
    v8 = 0;
    MprConvertGuidToString(a1, v7, v31);
  }
  v9 = dword_1800C8650;
  v10 = (RasRdGetServerAdapterLuidIndex(a1) & 0xFFFFFF | 0x17000000) << 24;
  v20 = v10;
  RtlIpv6AddressToStringA(Addr, S);
  EnterCriticalSection(&RasSrvrCriticalSection);
  v11 = *a1;
  v25 = *Addr;
  Buf1 = v11;
  Aipv6Node = RasSrvrFindAipv6Node(&Buf1, &v25, 1);
  if ( Aipv6Node )
  {
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v35) = 0;
      FormatRRASErrorString(&v35, L"RasSrvrReleaseIpv6Address: RDID = %ws Address = %hs", v31, S);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v35);
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v35) = 0;
        FormatRRASErrorString(
          &v35,
          L"RasSrvrReleaseIpv6Address: InterfaceLuid %I64u Subinterface Luid %I64u",
          v10,
          *((_QWORD *)Aipv6Node + 6));
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v35);
      }
    }
    if ( !dword_1800C9930 || v9 )
    {
      Buf1 = *a1;
      RasStatReleaseIpv6Prefix(&Buf1, Addr);
    }
    else
    {
      RasDhcpReleaseIpv6Prefix(Addr);
    }
    if ( (*((_BYTE *)Aipv6Node + 56) & 2) != 0 )
    {
      NboServerIpv6Address = RasRdGetNboServerIpv6Address(v30, a1);
      v14 = *(_OWORD *)(NboServerIpv6Address + 16);
      v26 = *(_OWORD *)NboServerIpv6Address;
      v15 = *(struct in6_addr *)(NboServerIpv6Address + 32);
      v29 = *(_DWORD *)(NboServerIpv6Address + 48);
      v28 = v15;
      v27 = v14;
      if ( !v8 )
      {
        RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &v21);
        if ( RoutingDomainConfigData )
        {
          if ( (_QWORD)xmmword_1800C9740 )
          {
            LOWORD(v35) = 0;
            FormatRRASErrorString(
              &v35,
              L"RasSrvrReleaseIpv6Address: GetRoutingDomainConfigData failed: 0x%x",
              RoutingDomainConfigData);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800C9740,
              &v35);
          }
        }
      }
      v17 = CreateOrSetOrDeleteIpv6NeighborEntry(&v20, (char *)Aipv6Node + 48, 1, Addr);
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, L"Create Ipv6 Neighbor for Global addr: 0x%x", v17);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v35);
      }
      v22[1] = *(_QWORD *)&Addr->u.Word[4];
      v18 = CreateOrSetOrDeleteIpv6NeighborEntry(&v20, (char *)Aipv6Node + 48, 1, v22);
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v35, L"Create Ipv6 Neighbor for link-local addr: 0x%x", v18);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v35);
      }
      RasSrvrSetProxyArpV6(Addr, 0, &v28, v21, a1);
    }
    if ( (*((_BYTE *)Aipv6Node + 56) & 1) != 0 )
    {
      v19 = v23;
      v20 = 0;
      *((_QWORD *)Aipv6Node + 2) = 0;
      ((void (__fastcall *)(__int64, __int64))pfnMprAdminReleaseIpv6AddressForUser)(a3, v19);
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v35) = 0;
        FormatRRASErrorString(
          &v35,
          L"RasSrvrReleaseIpv6Address: pfnMprAdminReleaseIpv6Identifier flag=%d",
          *((unsigned int *)Aipv6Node + 14));
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v35);
      }
    }
    free(*((void **)Aipv6Node + 4));
    free(*((void **)Aipv6Node + 5));
    LocalFree(Aipv6Node);
  }
  else if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v35) = 0;
    FormatRRASErrorString(&v35, L"Couldn't find address %hs in Acquired Ip Addresses list", S);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v35);
  }
  LeaveCriticalSection(&RasSrvrCriticalSection);
}

```

## disassembly

```asm
0x1800568d0  push    rbp
0x1800568d2  push    rbx
0x1800568d3  push    rsi
0x1800568d4  push    rdi
0x1800568d5  push    r12
0x1800568d7  push    r13
0x1800568d9  push    r14
0x1800568db  push    r15
0x1800568dd  lea     rbp, [rsp-8D8h]
0x1800568e5  sub     rsp, 9D8h
0x1800568ec  mov     rax, cs:__security_cookie
0x1800568f3  xor     rax, rsp
0x1800568f6  mov     [rbp+910h+var_50], rax
0x1800568fd  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180056904  mov     r13, r8
0x180056907  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18005690e  mov     r14, rdx
0x180056911  movaps  [rbp+910h+var_920], xmm0
0x180056915  mov     rsi, rcx
0x180056918  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18005691f  lea     rcx, [rbp+910h+var_84C]; void *
0x180056926  movaps  [rbp+910h+var_900], xmm0
0x18005692a  xor     eax, eax
0x18005692c  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x180056933  xor     ebx, ebx
0x180056935  xor     edx, edx; Val
0x180056937  movaps  [rbp+910h+var_910], xmm1
0x18005693b  mov     r8d, 7FCh; Size
0x180056941  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180056948  movaps  xmmword ptr [rbp+910h+var_8F0], xmm1
0x18005694c  movups  xmmword ptr [rbp+910h+var_8F0+0Eh], xmm0
0x180056950  mov     [rsp+0A10h+var_9C0], r9
0x180056955  mov     [rsp+0A10h+var_9D0], 80FEh
0x18005695e  mov     [rbp+910h+var_8D2], ax
0x180056962  mov     [rbp+910h+var_850], ebx
0x180056968  call    memset_0
0x18005696d  lea     r8d, [rbx+10h]; Size
0x180056971  mov     rcx, rsi; Buf1
0x180056974  lea     rdx, GUID_NULL; Buf2
0x18005697b  call    memcmp_0
0x180056980  lea     edi, [rbx+1]
0x180056983  mov     [rsp+0A10h+var_9D8], edi
0x180056987  test    eax, eax
0x180056989  jnz     short loc_180056990
0x18005698b  mov     r15d, edi
0x18005698e  jmp     short loc_18005699F
0x180056990  lea     r8, [rbp+910h+var_920]
0x180056994  mov     rcx, rsi
0x180056997  mov     r15d, ebx
0x18005699a  call    MprConvertGuidToString
0x18005699f  mov     r12d, cs:dword_1800C8650
0x1800569a6  mov     rcx, rsi
0x1800569a9  call    RasRdGetServerAdapterLuidIndex
0x1800569ae  mov     ebx, eax
0x1800569b0  lea     rdx, [rbp+910h+S]; S
0x1800569b4  and     ebx, 0FFFFFFh
0x1800569ba  mov     rcx, r14; Addr
0x1800569bd  or      rbx, 17000000h
0x1800569c4  shl     rbx, 18h
0x1800569c8  mov     [rsp+0A10h+var_9E0], rbx
0x1800569cd  call    cs:__imp_RtlIpv6AddressToStringA
0x1800569d3  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800569da  call    cs:__imp_EnterCriticalSection
0x1800569e0  movups  xmm0, xmmword ptr [r14]
0x1800569e4  mov     r8d, edi; int
0x1800569e7  lea     rdx, [rsp+0A10h+var_9A0]; struct in6_addr
0x1800569ec  movups  xmm1, xmmword ptr [rsi]
0x1800569ef  lea     rcx, [rsp+0A10h+Buf1]; struct _GUID
0x1800569f4  movdqu  xmmword ptr [rsp+0A10h+var_9A0.u], xmm0
0x1800569fa  movdqu  [rsp+0A10h+Buf1], xmm1
0x180056a00  call    ?RasSrvrFindAipv6Node@@YAPEAU_ACQUIRED_IPv6ADDR@@U_GUID@@Uin6_addr@@H@Z; RasSrvrFindAipv6Node(_GUID,in6_addr,int)
0x180056a05  mov     rdi, rax
0x180056a08  test    rax, rax
0x180056a0b  jnz     short loc_180056A5E
0x180056a0d  cmp     qword ptr cs:xmmword_1800C9740, rax
0x180056a14  jz      loc_180056D51
0x180056a1a  lea     r8, [rbp+910h+S]
0x180056a1e  mov     word ptr [rbp+910h+var_850], ax
0x180056a25  lea     rdx, aCouldnTFindAdd; "Couldn't find address %hs in Acquired I"...
0x180056a2c  lea     rcx, [rbp+910h+var_850]
0x180056a33  call    FormatRRASErrorString
0x180056a38  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180056a3f  lea     r8, [rbp+910h+var_850]
0x180056a46  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180056a4d  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180056a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a59  jmp     loc_180056D51
0x180056a5e  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180056a66  jz      loc_180056AFF
0x180056a6c  xor     eax, eax
0x180056a6e  lea     r9, [rbp+910h+S]
0x180056a72  lea     r8, [rbp+910h+var_920]
0x180056a76  mov     word ptr [rbp+910h+var_850], ax
0x180056a7d  lea     rdx, aRassrvrrelease; "RasSrvrReleaseIpv6Address: RDID = %ws A"...
0x180056a84  lea     rcx, [rbp+910h+var_850]
0x180056a8b  call    FormatRRASErrorString
0x180056a90  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180056a97  lea     r8, [rbp+910h+var_850]
0x180056a9e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180056aa5  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180056aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ab1  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180056ab9  jz      short loc_180056AFF
0x180056abb  xor     eax, eax
0x180056abd  lea     rdx, aRassrvrrelease_2; "RasSrvrReleaseIpv6Address: InterfaceLui"...
0x180056ac4  mov     word ptr [rbp+910h+var_850], ax
0x180056acb  lea     rcx, [rbp+910h+var_850]
0x180056ad2  mov     r9, [rdi+30h]
0x180056ad6  mov     r8, rbx
0x180056ad9  call    FormatRRASErrorString
0x180056ade  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180056ae5  lea     r8, [rbp+910h+var_850]
0x180056aec  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180056af3  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180056afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056aff  cmp     cs:dword_1800C9930, 0
0x180056b06  jz      short loc_180056B17
0x180056b08  test    r12d, r12d
0x180056b0b  jnz     short loc_180056B17
0x180056b0d  mov     rcx, r14; Addr
0x180056b10  call    ?RasDhcpReleaseIpv6Prefix@@YAXPEAUin6_addr@@@Z; RasDhcpReleaseIpv6Prefix(in6_addr *)
0x180056b15  jmp     short loc_180056B2D
0x180056b17  movups  xmm0, xmmword ptr [rsi]
0x180056b1a  mov     rdx, r14; Addr
0x180056b1d  lea     rcx, [rsp+0A10h+Buf1]; Buf1
0x180056b22  movdqu  [rsp+0A10h+Buf1], xmm0
0x180056b28  call    RasStatReleaseIpv6Prefix
0x180056b2d  test    byte ptr [rdi+38h], 2
0x180056b31  jz      loc_180056CAE
0x180056b37  mov     rdx, rsi
0x180056b3a  lea     rcx, [rbp+910h+var_958]
0x180056b3e  call    RasRdGetNboServerIpv6Address
0x180056b43  xor     r12d, r12d
0x180056b46  movups  xmm0, xmmword ptr [rax]
0x180056b49  movups  xmm1, xmmword ptr [rax+10h]
0x180056b4d  movups  [rbp+910h+var_990], xmm0
0x180056b51  movups  xmm0, xmmword ptr [rax+20h]
0x180056b55  mov     eax, [rax+30h]
0x180056b58  mov     [rbp+910h+var_960], eax
0x180056b5b  movups  xmmword ptr [rbp+910h+var_970.u], xmm0
0x180056b5f  movups  [rbp+910h+var_980], xmm1
0x180056b63  test    r15d, r15d
0x180056b66  jnz     short loc_180056BCB
0x180056b68  lea     r9, [rsp+0A10h+var_9D8]
0x180056b6d  mov     edx, 100h
0x180056b72  lea     r8d, [r12+4]
0x180056b77  mov     rcx, rsi
0x180056b7a  call    GetRoutingDomainConfigData
0x180056b7f  test    eax, eax
0x180056b81  jz      short loc_180056BCB
0x180056b83  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180056b8a  jz      short loc_180056BCB
0x180056b8c  mov     r8d, eax
0x180056b8f  mov     word ptr [rbp+910h+var_850], r12w
0x180056b97  lea     rdx, aRassrvrrelease_1; "RasSrvrReleaseIpv6Address: GetRoutingDo"...
0x180056b9e  lea     rcx, [rbp+910h+var_850]
0x180056ba5  call    FormatRRASErrorString
0x180056baa  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180056bb1  lea     r8, [rbp+910h+var_850]
0x180056bb8  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180056bbf  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180056bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056bcb  mov     r9, r14
0x180056bce  lea     rdx, [rdi+30h]
0x180056bd2  mov     r8d, 1
0x180056bd8  lea     rcx, [rsp+0A10h+var_9E0]
0x180056bdd  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x180056be2  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180056be9  jz      short loc_180056C2A
0x180056beb  mov     r8d, eax
0x180056bee  mov     word ptr [rbp+910h+var_850], r12w
0x180056bf6  lea     rdx, aCreateIpv6Neig_0; "Create Ipv6 Neighbor for Global addr: 0"...
0x180056bfd  lea     rcx, [rbp+910h+var_850]
0x180056c04  call    FormatRRASErrorString
0x180056c09  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180056c10  lea     r8, [rbp+910h+var_850]
0x180056c17  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180056c1e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180056c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c2a  mov     rax, [r14+8]
0x180056c2e  lea     r9, [rsp+0A10h+var_9D0]
0x180056c33  mov     r8d, 1
0x180056c39  mov     [rsp+0A10h+var_9C8], rax
0x180056c3e  lea     rdx, [rdi+30h]
0x180056c42  lea     rcx, [rsp+0A10h+var_9E0]
0x180056c47  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x180056c4c  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180056c53  jz      short loc_180056C94
0x180056c55  mov     r8d, eax
0x180056c58  mov     word ptr [rbp+910h+var_850], r12w
0x180056c60  lea     rdx, aCreateIpv6Neig; "Create Ipv6 Neighbor for link-local add"...
0x180056c67  lea     rcx, [rbp+910h+var_850]
0x180056c6e  call    FormatRRASErrorString
0x180056c73  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180056c7a  lea     r8, [rbp+910h+var_850]
0x180056c81  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180056c88  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180056c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c94  mov     r9d, [rsp+0A10h+var_9D8]; unsigned int
0x180056c99  lea     r8, [rbp+910h+var_970]; struct in6_addr *
0x180056c9d  xor     edx, edx; int
0x180056c9f  mov     [rsp+0A10h+var_9F0], rsi; struct _GUID *
0x180056ca4  mov     rcx, r14; Addr
0x180056ca7  call    ?RasSrvrSetProxyArpV6@@YAXPEBUin6_addr@@H0IPEBU_GUID@@@Z; RasSrvrSetProxyArpV6(in6_addr const *,int,in6_addr const *,uint,_GUID const *)
0x180056cac  jmp     short loc_180056CB1
0x180056cae  xor     r12d, r12d
0x180056cb1  test    byte ptr [rdi+38h], 1
0x180056cb5  jz      short loc_180056D34
0x180056cb7  mov     rdx, [rsp+0A10h+var_9C0]
0x180056cbc  lea     r8, [rdi+10h]
0x180056cc0  xor     eax, eax
0x180056cc2  mov     byte ptr [rsp+0A10h+var_9E0], r12b
0x180056cc7  mov     dword ptr [rsp+0A10h+var_9E0+1], eax
0x180056ccb  mov     rcx, r13
0x180056cce  mov     word ptr [rsp+0A10h+var_9E0+5], ax
0x180056cd3  mov     byte ptr [rsp+0A10h+var_9E0+7], al
0x180056cd7  mov     rax, [rsp+0A10h+var_9E0]
0x180056cdc  mov     [r8], rax
0x180056cdf  mov     rax, cs:?pfnMprAdminReleaseIpv6AddressForUser@@3P6AXPEAG0PEAUin6_addr@@@ZEA; void (*pfnMprAdminReleaseIpv6AddressForUser)(ushort *,ushort *,in6_addr *)
0x180056ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ceb  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180056cf2  jz      short loc_180056D34
0x180056cf4  mov     word ptr [rbp+910h+var_850], r12w
0x180056cfc  lea     rdx, aRassrvrrelease_0; "RasSrvrReleaseIpv6Address: pfnMprAdminR"...
0x180056d03  mov     r8d, [rdi+38h]
0x180056d07  lea     rcx, [rbp+910h+var_850]
0x180056d0e  call    FormatRRASErrorString
0x180056d13  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180056d1a  lea     r8, [rbp+910h+var_850]
0x180056d21  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180056d28  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180056d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d34  mov     rcx, [rdi+20h]; Block
0x180056d38  call    cs:__imp_free
0x180056d3e  mov     rcx, [rdi+28h]; Block
0x180056d42  call    cs:__imp_free
0x180056d48  mov     rcx, rdi; hMem
0x180056d4b  call    cs:__imp_LocalFree
0x180056d51  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180056d58  call    cs:__imp_LeaveCriticalSection
0x180056d5e  mov     rcx, [rbp+910h+var_50]
0x180056d65  xor     rcx, rsp; StackCookie
0x180056d68  call    __security_check_cookie
0x180056d6d  add     rsp, 9D8h
0x180056d74  pop     r15
0x180056d76  pop     r14
0x180056d78  pop     r13
0x180056d7a  pop     r12
0x180056d7c  pop     rdi
0x180056d7d  pop     rsi
0x180056d7e  pop     rbx
0x180056d7f  pop     rbp
0x180056d80  retn
```
