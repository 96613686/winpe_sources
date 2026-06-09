# RasSrvrReleaseIpv6Address

- ea: `0x1800586e0`
- end: `0x180058bcd`
- name: `RasSrvrReleaseIpv6Address`
- size: `1261`
- prototype: `__int64 __fastcall(struct _GUID *, struct in6_addr *Addr)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x180052d5c`
- `0x180062ae0`

## callees

- `0x180027ec0`
- `0x18004eb54`
- `0x18004f8c4`
- `0x1800586e0`
- `0x18005aa44`
- `0x18005aaf8`
- `0x18005c360`
- `0x18005d770`
- `0x1800755b8`
- `0x1800771b8`
- `0x180079428`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!free` at `0x180058b6b`
- `msvcrt!free` at `0x180058b7b`
- `msvcrt!free` at `0x180058b6b`
- `msvcrt!free` at `0x180058b7b`
- `KERNEL32!LocalFree` at `0x180058b8a`
- `KERNEL32!LocalFree` at `0x180058b8a`
- `KERNEL32!LeaveCriticalSection` at `0x180058b9d`
- `KERNEL32!LeaveCriticalSection` at `0x180058b9d`
- `KERNEL32!EnterCriticalSection` at `0x180058808`
- `KERNEL32!EnterCriticalSection` at `0x180058808`
- `ntdll!RtlIpv6AddressToStringA` at `0x1800587f5`
- `ntdll!RtlIpv6AddressToStringA` at `0x1800587f5`

## string_xrefs

- `0x1800589ca`: `RasSrvrReleaseIpv6Address: GetRoutingDomainConfigData failed: 0x%x`
- `0x180058a29`: `Create Ipv6 Neighbor for Global addr: 0x%x`
- `0x180058a93`: `Create Ipv6 Neighbor for link-local addr: 0x%x`

## pseudocode

```c
void __fastcall RasSrvrReleaseIpv6Address(struct _GUID *a1, struct in6_addr *Addr, __int64 a3, __int64 a4)
{
  __int64 v7; // rdx
  bool v8; // zf
  int v9; // r15d
  int v10; // r12d
  __int64 v11; // rbx
  struct _GUID v12; // xmm1
  struct _ACQUIRED_IPv6ADDR *Aipv6Node; // rdi
  __int64 NboServerIpv6Address; // rax
  __int128 v15; // xmm1
  struct in6_addr v16; // xmm0
  unsigned int RoutingDomainConfigData; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h]
  struct _GUID v25; // [rsp+60h] [rbp-A0h] BYREF
  struct in6_addr v26; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[56]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+B8h] [rbp-48h]
  __int128 v29; // [rsp+C8h] [rbp-38h]
  struct in6_addr v30; // [rsp+D8h] [rbp-28h] BYREF
  int v31; // [rsp+E8h] [rbp-18h]
  _OWORD v32[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v33; // [rsp+130h] [rbp+30h]
  int v34; // [rsp+138h] [rbp+38h]
  wchar_t v35; // [rsp+13Ch] [rbp+3Ch]
  __int16 v36; // [rsp+13Eh] [rbp+3Eh]
  CHAR S[128]; // [rsp+140h] [rbp+40h] BYREF
  int v38; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v39[2044]; // [rsp+1C4h] [rbp+C4h] BYREF

  v32[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v34 = *(_DWORD *)L"0}";
  v32[2] = *(_OWORD *)L"000-0000-000000000000}";
  v32[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v35 = a00000000000000[38];
  v33 = *(_QWORD *)L"00000}";
  v24 = a4;
  v23[0] = 33022;
  v32[3] = *(_OWORD *)L"-000000000000}";
  v36 = 0;
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v8 = *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_NULL.Data1;
  v22 = 1;
  if ( v8 && *(_QWORD *)a1->Data4 == *(_QWORD *)GUID_NULL.Data4 )
  {
    v9 = 1;
  }
  else
  {
    v9 = 0;
    MprConvertGuidToString(a1, v7, v32);
  }
  v10 = dword_1800CF650;
  v11 = (RasRdGetServerAdapterLuidIndex(a1) & 0xFFFFFF | 0x17000000) << 24;
  v21 = v11;
  RtlIpv6AddressToStringA(Addr, S);
  EnterCriticalSection(&RasSrvrCriticalSection);
  v12 = *a1;
  v26 = *Addr;
  v25 = v12;
  Aipv6Node = RasSrvrFindAipv6Node(&v25, &v26, 1);
  if ( Aipv6Node )
  {
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v38) = 0;
      FormatRRASErrorString(&v38, L"RasSrvrReleaseIpv6Address: RDID = %ws Address = %hs", v32, S);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v38);
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v38) = 0;
        FormatRRASErrorString(
          &v38,
          L"RasSrvrReleaseIpv6Address: InterfaceLuid %I64u Subinterface Luid %I64u",
          v11,
          *((_QWORD *)Aipv6Node + 6));
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v38);
      }
    }
    if ( !dword_1800D0930 || v10 )
    {
      v25 = *a1;
      RasStatReleaseIpv6Prefix(&v25, Addr);
    }
    else
    {
      RasDhcpReleaseIpv6Prefix(Addr);
    }
    if ( (*((_BYTE *)Aipv6Node + 56) & 2) != 0 )
    {
      NboServerIpv6Address = RasRdGetNboServerIpv6Address(v27, a1);
      v15 = *(_OWORD *)(NboServerIpv6Address + 16);
      v28 = *(_OWORD *)NboServerIpv6Address;
      v16 = *(struct in6_addr *)(NboServerIpv6Address + 32);
      v31 = *(_DWORD *)(NboServerIpv6Address + 48);
      v30 = v16;
      v29 = v15;
      if ( !v9 )
      {
        RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &v22);
        if ( RoutingDomainConfigData )
        {
          if ( (_QWORD)xmmword_1800D0740 )
          {
            LOWORD(v38) = 0;
            FormatRRASErrorString(
              &v38,
              L"RasSrvrReleaseIpv6Address: GetRoutingDomainConfigData failed: 0x%x",
              RoutingDomainConfigData);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800D0740,
              &v38);
          }
        }
      }
      v18 = CreateOrSetOrDeleteIpv6NeighborEntry(&v21, (char *)Aipv6Node + 48, 1, Addr);
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v38) = 0;
        FormatRRASErrorString(&v38, L"Create Ipv6 Neighbor for Global addr: 0x%x", v18);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v38);
      }
      v23[1] = *(_QWORD *)&Addr->u.Word[4];
      v19 = CreateOrSetOrDeleteIpv6NeighborEntry(&v21, (char *)Aipv6Node + 48, 1, v23);
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v38) = 0;
        FormatRRASErrorString(&v38, L"Create Ipv6 Neighbor for link-local addr: 0x%x", v19);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v38);
      }
      RasSrvrSetProxyArpV6(Addr, 0, &v30, v22, a1);
    }
    if ( (*((_BYTE *)Aipv6Node + 56) & 1) != 0 )
    {
      v20 = v24;
      v21 = 0;
      *((_QWORD *)Aipv6Node + 2) = 0;
      ((void (__fastcall *)(__int64, __int64))pfnMprAdminReleaseIpv6AddressForUser)(a3, v20);
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v38) = 0;
        FormatRRASErrorString(
          &v38,
          L"RasSrvrReleaseIpv6Address: pfnMprAdminReleaseIpv6Identifier flag=%d",
          *((unsigned int *)Aipv6Node + 14));
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v38);
      }
    }
    free(*((void **)Aipv6Node + 4));
    free(*((void **)Aipv6Node + 5));
    LocalFree(Aipv6Node);
  }
  else if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v38) = 0;
    FormatRRASErrorString(&v38, L"Couldn't find address %hs in Acquired Ip Addresses list", S);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v38);
  }
  LeaveCriticalSection(&RasSrvrCriticalSection);
}

```

## disassembly

```asm
0x1800586e0  push    rbp
0x1800586e2  push    rbx
0x1800586e3  push    rsi
0x1800586e4  push    rdi
0x1800586e5  push    r12
0x1800586e7  push    r13
0x1800586e9  push    r14
0x1800586eb  push    r15
0x1800586ed  lea     rbp, [rsp-8D8h]
0x1800586f5  sub     rsp, 9D8h
0x1800586fc  mov     rax, cs:__security_cookie
0x180058703  xor     rax, rsp
0x180058706  mov     [rbp+910h+var_50], rax
0x18005870d  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180058714  mov     r13, r8
0x180058717  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x18005871d  mov     r14, rdx
0x180058720  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180058727  mov     rsi, rcx
0x18005872a  movaps  [rbp+910h+var_920], xmm0
0x18005872e  lea     rcx, [rbp+910h+var_84C]; void *
0x180058735  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18005873c  xor     ebx, ebx
0x18005873e  mov     [rbp+910h+var_8D8], eax
0x180058741  xor     edx, edx; Val
0x180058743  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x18005874a  mov     r8d, 7FCh; Size
0x180058750  movaps  [rbp+910h+var_900], xmm0
0x180058754  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x18005875c  movaps  [rbp+910h+var_910], xmm1
0x180058760  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180058767  mov     [rbp+910h+var_8D4], ax
0x18005876b  xor     eax, eax
0x18005876d  movsd   [rbp+910h+var_8E0], xmm0
0x180058772  mov     [rsp+0A10h+var_9C0], r9
0x180058777  mov     [rsp+0A10h+var_9D0], 80FEh
0x180058780  movaps  [rbp+910h+var_8F0], xmm1
0x180058784  mov     [rbp+910h+var_8D2], ax
0x180058788  mov     [rbp+910h+var_850], ebx
0x18005878e  call    memset_0
0x180058793  mov     rax, [rsi]
0x180058796  lea     edi, [rbx+1]
0x180058799  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x1800587a0  mov     [rsp+0A10h+var_9D8], edi
0x1800587a4  jnz     short loc_1800587B8
0x1800587a6  mov     rax, [rsi+8]
0x1800587aa  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x1800587b1  jnz     short loc_1800587B8
0x1800587b3  mov     r15d, edi
0x1800587b6  jmp     short loc_1800587C7
0x1800587b8  lea     r8, [rbp+910h+var_920]
0x1800587bc  mov     rcx, rsi
0x1800587bf  mov     r15d, ebx
0x1800587c2  call    MprConvertGuidToString
0x1800587c7  mov     r12d, cs:dword_1800CF650
0x1800587ce  mov     rcx, rsi
0x1800587d1  call    RasRdGetServerAdapterLuidIndex
0x1800587d6  mov     ebx, eax
0x1800587d8  lea     rdx, [rbp+910h+S]; S
0x1800587dc  and     ebx, 0FFFFFFh
0x1800587e2  mov     rcx, r14; Addr
0x1800587e5  or      rbx, 17000000h
0x1800587ec  shl     rbx, 18h
0x1800587f0  mov     [rsp+0A10h+var_9E0], rbx
0x1800587f5  call    cs:__imp_RtlIpv6AddressToStringA
0x1800587fc  nop     dword ptr [rax+rax+00h]
0x180058801  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180058808  call    cs:__imp_EnterCriticalSection
0x18005880f  nop     dword ptr [rax+rax+00h]
0x180058814  movups  xmm0, xmmword ptr [r14]
0x180058818  mov     r8d, edi; int
0x18005881b  lea     rdx, [rsp+0A10h+var_9A0]; struct in6_addr
0x180058820  movups  xmm1, xmmword ptr [rsi]
0x180058823  lea     rcx, [rsp+0A10h+var_9B0]; struct _GUID
0x180058828  movdqu  xmmword ptr [rsp+0A10h+var_9A0.u], xmm0
0x18005882e  movdqu  xmmword ptr [rsp+0A10h+var_9B0.Data1], xmm1
0x180058834  call    ?RasSrvrFindAipv6Node@@YAPEAU_ACQUIRED_IPv6ADDR@@U_GUID@@Uin6_addr@@H@Z; RasSrvrFindAipv6Node(_GUID,in6_addr,int)
0x180058839  mov     rdi, rax
0x18005883c  xor     eax, eax
0x18005883e  test    rdi, rdi
0x180058841  jnz     short loc_180058894
0x180058843  cmp     qword ptr cs:xmmword_1800D0740, rax
0x18005884a  jz      loc_180058B96
0x180058850  lea     r8, [rbp+910h+S]
0x180058854  mov     word ptr [rbp+910h+var_850], ax
0x18005885b  lea     rdx, aCouldnTFindAdd; "Couldn't find address %hs in Acquired I"...
0x180058862  lea     rcx, [rbp+910h+var_850]
0x180058869  call    FormatRRASErrorString
0x18005886e  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180058875  lea     r8, [rbp+910h+var_850]
0x18005887c  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180058883  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005888a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005888f  jmp     loc_180058B96
0x180058894  cmp     qword ptr cs:xmmword_1800D0740, rax
0x18005889b  jz      loc_180058933
0x1800588a1  lea     r9, [rbp+910h+S]
0x1800588a5  mov     word ptr [rbp+910h+var_850], ax
0x1800588ac  lea     r8, [rbp+910h+var_920]
0x1800588b0  lea     rdx, aRassrvrrelease; "RasSrvrReleaseIpv6Address: RDID = %ws A"...
0x1800588b7  lea     rcx, [rbp+910h+var_850]
0x1800588be  call    FormatRRASErrorString
0x1800588c3  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800588ca  lea     r8, [rbp+910h+var_850]
0x1800588d1  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800588d8  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800588df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588e4  xor     eax, eax
0x1800588e6  cmp     qword ptr cs:xmmword_1800D0740, rax
0x1800588ed  jz      short loc_180058933
0x1800588ef  mov     word ptr [rbp+910h+var_850], ax
0x1800588f6  lea     rdx, aRassrvrrelease_2; "RasSrvrReleaseIpv6Address: InterfaceLui"...
0x1800588fd  mov     r9, [rdi+30h]
0x180058901  lea     rcx, [rbp+910h+var_850]
0x180058908  mov     r8, rbx
0x18005890b  call    FormatRRASErrorString
0x180058910  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180058917  lea     r8, [rbp+910h+var_850]
0x18005891e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180058925  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005892c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058931  xor     eax, eax
0x180058933  cmp     cs:dword_1800D0930, eax
0x180058939  jz      short loc_18005894A
0x18005893b  test    r12d, r12d
0x18005893e  jnz     short loc_18005894A
0x180058940  mov     rcx, r14; Addr
0x180058943  call    ?RasDhcpReleaseIpv6Prefix@@YAXPEAUin6_addr@@@Z; RasDhcpReleaseIpv6Prefix(in6_addr *)
0x180058948  jmp     short loc_180058960
0x18005894a  movups  xmm0, xmmword ptr [rsi]
0x18005894d  mov     rdx, r14
0x180058950  lea     rcx, [rsp+0A10h+var_9B0]
0x180058955  movdqu  xmmword ptr [rsp+0A10h+var_9B0.Data1], xmm0
0x18005895b  call    RasStatReleaseIpv6Prefix
0x180058960  test    byte ptr [rdi+38h], 2
0x180058964  jz      loc_180058AE1
0x18005896a  mov     rdx, rsi
0x18005896d  lea     rcx, [rbp+910h+var_990]
0x180058971  call    RasRdGetNboServerIpv6Address
0x180058976  xor     r12d, r12d
0x180058979  movups  xmm0, xmmword ptr [rax]
0x18005897c  movups  xmm1, xmmword ptr [rax+10h]
0x180058980  movups  [rbp+910h+var_958], xmm0
0x180058984  movups  xmm0, xmmword ptr [rax+20h]
0x180058988  mov     eax, [rax+30h]
0x18005898b  mov     [rbp+910h+var_928], eax
0x18005898e  movups  xmmword ptr [rbp+910h+var_938.u], xmm0
0x180058992  movups  [rbp+910h+var_948], xmm1
0x180058996  test    r15d, r15d
0x180058999  jnz     short loc_1800589FE
0x18005899b  lea     r9, [rsp+0A10h+var_9D8]
0x1800589a0  mov     edx, 100h
0x1800589a5  lea     r8d, [r12+4]
0x1800589aa  mov     rcx, rsi
0x1800589ad  call    GetRoutingDomainConfigData
0x1800589b2  test    eax, eax
0x1800589b4  jz      short loc_1800589FE
0x1800589b6  cmp     qword ptr cs:xmmword_1800D0740, r12
0x1800589bd  jz      short loc_1800589FE
0x1800589bf  mov     r8d, eax
0x1800589c2  mov     word ptr [rbp+910h+var_850], r12w
0x1800589ca  lea     rdx, aRassrvrrelease_1; "RasSrvrReleaseIpv6Address: GetRoutingDo"...
0x1800589d1  lea     rcx, [rbp+910h+var_850]
0x1800589d8  call    FormatRRASErrorString
0x1800589dd  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800589e4  lea     r8, [rbp+910h+var_850]
0x1800589eb  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800589f2  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800589f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589fe  mov     r9, r14
0x180058a01  lea     rdx, [rdi+30h]
0x180058a05  mov     r8d, 1
0x180058a0b  lea     rcx, [rsp+0A10h+var_9E0]
0x180058a10  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x180058a15  cmp     qword ptr cs:xmmword_1800D0740, r12
0x180058a1c  jz      short loc_180058A5D
0x180058a1e  mov     r8d, eax
0x180058a21  mov     word ptr [rbp+910h+var_850], r12w
0x180058a29  lea     rdx, aCreateIpv6Neig_0; "Create Ipv6 Neighbor for Global addr: 0"...
0x180058a30  lea     rcx, [rbp+910h+var_850]
0x180058a37  call    FormatRRASErrorString
0x180058a3c  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180058a43  lea     r8, [rbp+910h+var_850]
0x180058a4a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180058a51  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180058a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a5d  mov     rax, [r14+8]
0x180058a61  lea     r9, [rsp+0A10h+var_9D0]
0x180058a66  mov     r8d, 1
0x180058a6c  mov     [rsp+0A10h+var_9C8], rax
0x180058a71  lea     rdx, [rdi+30h]
0x180058a75  lea     rcx, [rsp+0A10h+var_9E0]
0x180058a7a  call    CreateOrSetOrDeleteIpv6NeighborEntry
0x180058a7f  cmp     qword ptr cs:xmmword_1800D0740, r12
0x180058a86  jz      short loc_180058AC7
0x180058a88  mov     r8d, eax
0x180058a8b  mov     word ptr [rbp+910h+var_850], r12w
0x180058a93  lea     rdx, aCreateIpv6Neig; "Create Ipv6 Neighbor for link-local add"...
0x180058a9a  lea     rcx, [rbp+910h+var_850]
0x180058aa1  call    FormatRRASErrorString
0x180058aa6  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180058aad  lea     r8, [rbp+910h+var_850]
0x180058ab4  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180058abb  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180058ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ac7  mov     r9d, [rsp+0A10h+var_9D8]; unsigned int
0x180058acc  lea     r8, [rbp+910h+var_938]; struct in6_addr *
0x180058ad0  xor     edx, edx; int
0x180058ad2  mov     [rsp+0A10h+var_9F0], rsi; struct _GUID *
0x180058ad7  mov     rcx, r14; Addr
0x180058ada  call    ?RasSrvrSetProxyArpV6@@YAXPEBUin6_addr@@H0IPEBU_GUID@@@Z; RasSrvrSetProxyArpV6(in6_addr const *,int,in6_addr const *,uint,_GUID const *)
0x180058adf  jmp     short loc_180058AE4
0x180058ae1  xor     r12d, r12d
0x180058ae4  test    byte ptr [rdi+38h], 1
0x180058ae8  jz      short loc_180058B67
0x180058aea  mov     rdx, [rsp+0A10h+var_9C0]
0x180058aef  lea     r8, [rdi+10h]
0x180058af3  xor     eax, eax
0x180058af5  mov     byte ptr [rsp+0A10h+var_9E0], r12b
0x180058afa  mov     dword ptr [rsp+0A10h+var_9E0+1], eax
0x180058afe  mov     rcx, r13
0x180058b01  mov     word ptr [rsp+0A10h+var_9E0+5], ax
0x180058b06  mov     byte ptr [rsp+0A10h+var_9E0+7], al
0x180058b0a  mov     rax, [rsp+0A10h+var_9E0]
0x180058b0f  mov     [r8], rax
0x180058b12  mov     rax, cs:?pfnMprAdminReleaseIpv6AddressForUser@@3P6AXPEAG0PEAUin6_addr@@@ZEA; void (*pfnMprAdminReleaseIpv6AddressForUser)(ushort *,ushort *,in6_addr *)
0x180058b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b1e  cmp     qword ptr cs:xmmword_1800D0740, r12
0x180058b25  jz      short loc_180058B67
0x180058b27  mov     word ptr [rbp+910h+var_850], r12w
0x180058b2f  lea     rdx, aRassrvrrelease_0; "RasSrvrReleaseIpv6Address: pfnMprAdminR"...
0x180058b36  mov     r8d, [rdi+38h]
0x180058b3a  lea     rcx, [rbp+910h+var_850]
0x180058b41  call    FormatRRASErrorString
0x180058b46  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180058b4d  lea     r8, [rbp+910h+var_850]
0x180058b54  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180058b5b  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180058b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b67  mov     rcx, [rdi+20h]; Block
0x180058b6b  call    cs:__imp_free
0x180058b72  nop     dword ptr [rax+rax+00h]
0x180058b77  mov     rcx, [rdi+28h]; Block
0x180058b7b  call    cs:__imp_free
0x180058b82  nop     dword ptr [rax+rax+00h]
0x180058b87  mov     rcx, rdi; hMem
0x180058b8a  call    cs:__imp_LocalFree
0x180058b91  nop     dword ptr [rax+rax+00h]
0x180058b96  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180058b9d  call    cs:__imp_LeaveCriticalSection
0x180058ba4  nop     dword ptr [rax+rax+00h]
0x180058ba9  mov     rcx, [rbp+910h+var_50]
0x180058bb0  xor     rcx, rsp; StackCookie
0x180058bb3  call    __security_check_cookie
0x180058bb8  add     rsp, 9D8h
0x180058bbf  pop     r15
0x180058bc1  pop     r14
0x180058bc3  pop     r13
0x180058bc5  pop     r12
0x180058bc7  pop     rdi
0x180058bc8  pop     rsi
0x180058bc9  pop     rbx
0x180058bca  pop     rbp
0x180058bcb  retn
```
