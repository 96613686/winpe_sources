# RasSrvrDhcpCallback

- ea: `0x180055a04`
- end: `0x180055e4c`
- name: `RasSrvrDhcpCallback`
- size: `1096`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x18005f264`
- `0x18005ff60`

## callees

- `0x180050bfc`
- `0x180055a04`
- `0x1800582b0`
- `0x18005a844`
- `0x18005aa10`
- `0x18005aaf8`
- `0x18005ad18`
- `0x18005adcc`
- `0x18005af78`
- `0x18006b414`
- `0x1800755b8`
- `0x18007ef74`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!free` at `0x180055def`
- `msvcrt!free` at `0x180055dff`
- `msvcrt!free` at `0x180055def`
- `msvcrt!free` at `0x180055dff`
- `KERNEL32!LocalFree` at `0x180055e0e`
- `KERNEL32!LocalFree` at `0x180055e0e`
- `KERNEL32!LeaveCriticalSection` at `0x180055dda`
- `KERNEL32!LeaveCriticalSection` at `0x180055dda`
- `KERNEL32!EnterCriticalSection` at `0x180055ac1`
- `KERNEL32!EnterCriticalSection` at `0x180055ac1`
- `ntdll!RtlIpv4AddressToStringA` at `0x180055b3d`
- `ntdll!RtlIpv4AddressToStringA` at `0x180055c2d`
- `ntdll!RtlIpv4AddressToStringA` at `0x180055b3d`
- `ntdll!RtlIpv4AddressToStringA` at `0x180055c2d`
- `rtutils!LogEventA` at `0x180055b69`
- `rtutils!LogEventA` at `0x180055c54`
- `rtutils!LogEventA` at `0x180055b69`
- `rtutils!LogEventA` at `0x180055c54`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x180055d63`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x180055d63`

## string_xrefs

- `0x180055d8b`: `DhcpNotifyConfigChange(%ws) failed and returned 0x%x`

## pseudocode

```c
void __fastcall RasSrvrDhcpCallback(unsigned int a1)
{
  void **AiNode; // rbx
  ULONG NboServerIpv4Address; // eax
  ULONG v4; // esi
  struct _GUID v5; // xmm6
  __int64 v6; // rdi
  struct _GUID v7; // xmm6
  void *v8; // r9
  void *v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  int v12; // edx
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int ServerAdapterLuidIndex; // eax
  unsigned int v16; // eax
  struct in_addr Addr[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPSTR plpwsSubStrings; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+58h] [rbp-B0h] BYREF
  struct _GUID v20; // [rsp+68h] [rbp-A0h] BYREF
  GUID v21; // [rsp+78h] [rbp-90h] BYREF
  CHAR S[32]; // [rsp+88h] [rbp-80h] BYREF
  int v23; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v24[2044]; // [rsp+ACh] [rbp-5Ch] BYREF
  _BYTE v25[528]; // [rsp+8A8h] [rbp+7A0h] BYREF

  plpwsSubStrings = 0;
  v21 = GUID_NULL;
  AiNode = 0;
  v19 = 0;
  NboServerIpv4Address = RasRdGetNboServerIpv4Address(&v21);
  v23 = 0;
  v4 = NboServerIpv4Address;
  memset_0(v24, 0, sizeof(v24));
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(&v23, L"RasSrvrDhcpCallback(0x%x)", a1);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v23);
  }
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( !a1 )
  {
    if ( !v4 )
      goto LABEL_24;
    goto LABEL_5;
  }
  if ( a1 == v4 )
  {
LABEL_5:
    memset_0(v25, 0, 0x204u);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"******** SERVER ADDRESS (0x%x) LEASE EXPIRED ********", v4);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v23);
    }
    Addr[0].S_un.S_addr = v4;
    RtlIpv4AddressToStringA(Addr, S);
    plpwsSubStrings = S;
    LogEventA(2u, 0x4E74u, 1u, &plpwsSubStrings);
    v5 = v21;
    v20 = v21;
    if ( !(unsigned int)RasGetRoutingDomainAddressPool(&v20, 1, &v19) )
    {
      v6 = v19;
      if ( v19 )
      {
        while ( 1 )
        {
          v13 = *(_QWORD *)(v6 + 24);
          if ( !v13 )
            break;
          v10 = *(_QWORD *)(v13 + 32);
          v11 = *(_QWORD *)(v13 + 24);
          v12 = *(_DWORD *)(v13 + 16);
          v20 = v5;
          RasSrvrReleaseAddress((unsigned int)&v20, v12, v11, v10, 1);
        }
      }
      v20 = v5;
      v14 = RasReleaseRoutingDomainAddressPool(&v20);
      if ( v14 && (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v23) = 0;
        FormatRRASErrorString(&v23, L"RasReleaseRoutingDomainAddressPool failed and returned %d", v14);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v23);
      }
    }
    RasTcpSetProxyArp(v4, 0, v4, 1u);
    ServerAdapterLuidIndex = RasRdGetServerAdapterLuidIndex(&v21);
    ResetIpAddressOnInterface(ServerAdapterLuidIndex, v4);
    Addr[0].S_un.S_addr = 516;
    RasRoutingDomainGetConfigParam(&v21, 6, Addr, v25);
    v16 = DhcpNotifyConfigChange(0, v25, 0, 0, 0, 0, 0);
    if ( v16 && (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"DhcpNotifyConfigChange(%ws) failed and returned 0x%x", v25, v16);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v23);
    }
    Addr[0].S_un.S_addr = 0;
    RasRoutingDomainSetConfigParam(&v21, 0, 4, Addr);
    goto LABEL_24;
  }
  v7 = v21;
  AiNode = (void **)rasSrvrFindAiNode(&v21, a1, 1);
  if ( AiNode )
  {
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(&v23, L"******** CLIENT ADDRESS (0x%x) LEASE EXPIRED ********", a1);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v23);
    }
    Addr[0].S_un.S_addr = a1;
    RtlIpv4AddressToStringA(Addr, S);
    plpwsSubStrings = S;
    LogEventA(2u, 0x4E75u, 1u, &plpwsSubStrings);
    v8 = AiNode[4];
    v9 = AiNode[3];
    v21 = v7;
    RasSrvrReleaseAddress((unsigned int)&v21, a1, (_DWORD)v9, (_DWORD)v8, 1);
  }
LABEL_24:
  LeaveCriticalSection(&RasSrvrCriticalSection);
  if ( AiNode )
  {
    free(AiNode[3]);
    free(AiNode[4]);
    LocalFree(AiNode);
  }
}

```

## disassembly

```asm
0x180055a04  mov     rax, rsp
0x180055a07  mov     [rax+10h], rbx
0x180055a0b  mov     [rax+18h], rsi
0x180055a0f  mov     [rax+20h], rdi
0x180055a13  push    rbp
0x180055a14  push    r14
0x180055a16  push    r15
0x180055a18  lea     rbp, [rax-9E8h]
0x180055a1f  sub     rsp, 0AD0h
0x180055a26  movaps  xmmword ptr [rax-28h], xmm6
0x180055a2a  mov     rax, cs:__security_cookie
0x180055a31  xor     rax, rsp
0x180055a34  mov     [rbp+9E0h+var_30], rax
0x180055a3b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180055a42  xor     r15d, r15d
0x180055a45  mov     edi, ecx
0x180055a47  lea     rcx, [rsp+0AE0h+var_A78+8]
0x180055a4c  mov     [rsp+0AE0h+plpwsSubStrings], r15
0x180055a51  movdqu  xmmword ptr [rsp+0AE0h+var_A78+8], xmm0
0x180055a57  mov     ebx, r15d
0x180055a5a  mov     [rsp+0AE0h+var_A90], r15
0x180055a5f  call    RasRdGetNboServerIpv4Address
0x180055a64  xor     edx, edx; Val
0x180055a66  mov     [rbp+9E0h+var_A40], r15d
0x180055a6a  mov     r8d, 7FCh; Size
0x180055a70  lea     rcx, [rbp+9E0h+var_A3C]; void *
0x180055a74  mov     esi, eax
0x180055a76  call    memset_0
0x180055a7b  cmp     qword ptr cs:xmmword_1800D0740, r15
0x180055a82  jz      short loc_180055ABA
0x180055a84  mov     r8d, edi
0x180055a87  mov     word ptr [rbp+9E0h+var_A40], r15w
0x180055a8c  lea     rdx, aRassrvrdhcpcal; "RasSrvrDhcpCallback(0x%x)"
0x180055a93  lea     rcx, [rbp+9E0h+var_A40]
0x180055a97  call    FormatRRASErrorString
0x180055a9c  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055aa3  lea     r8, [rbp+9E0h+var_A40]
0x180055aa7  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055aae  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055aba  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180055ac1  call    cs:__imp_EnterCriticalSection
0x180055ac8  nop     dword ptr [rax+rax+00h]
0x180055acd  test    edi, edi
0x180055acf  jnz     loc_180055BAD
0x180055ad5  test    esi, esi
0x180055ad7  jz      loc_180055DD3
0x180055add  xor     edx, edx; Val
0x180055adf  lea     rcx, [rbp+9E0h+var_240]; void *
0x180055ae6  mov     r8d, 204h; Size
0x180055aec  call    memset_0
0x180055af1  cmp     qword ptr cs:xmmword_1800D0740, r15
0x180055af8  jz      short loc_180055B30
0x180055afa  mov     r8d, esi
0x180055afd  mov     word ptr [rbp+9E0h+var_A40], r15w
0x180055b02  lea     rdx, aServerAddress0; "******** SERVER ADDRESS (0x%x) LEASE EX"...
0x180055b09  lea     rcx, [rbp+9E0h+var_A40]
0x180055b0d  call    FormatRRASErrorString
0x180055b12  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055b19  lea     r8, [rbp+9E0h+var_A40]
0x180055b1d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055b24  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b30  lea     rdx, [rbp+9E0h+S]; S
0x180055b34  mov     dword ptr [rsp+0AE0h+Addr.S_un], esi
0x180055b38  lea     rcx, [rsp+0AE0h+Addr]; Addr
0x180055b3d  call    cs:__imp_RtlIpv4AddressToStringA
0x180055b44  nop     dword ptr [rax+rax+00h]
0x180055b49  mov     r14d, 1
0x180055b4f  lea     rax, [rbp+9E0h+S]
0x180055b53  lea     r9, [rsp+0AE0h+plpwsSubStrings]; plpwsSubStrings
0x180055b58  mov     [rsp+0AE0h+plpwsSubStrings], rax
0x180055b5d  mov     r8d, r14d; cNumberOfSubStrings
0x180055b60  mov     edx, 4E74h; dwMessageId
0x180055b65  lea     ecx, [r14+1]; wEventType
0x180055b69  call    cs:__imp_LogEventA
0x180055b70  nop     dword ptr [rax+rax+00h]
0x180055b75  movaps  xmm6, xmmword ptr [rsp+0AE0h+var_A78+8]
0x180055b7a  lea     r8, [rsp+0AE0h+var_A90]
0x180055b7f  mov     edx, r14d
0x180055b82  movdqa  [rsp+0AE0h+var_A88+8], xmm6
0x180055b88  lea     rcx, [rsp+0AE0h+var_A88+8]
0x180055b8d  call    RasGetRoutingDomainAddressPool
0x180055b92  test    eax, eax
0x180055b94  jnz     loc_180055D00
0x180055b9a  mov     rdi, [rsp+0AE0h+var_A90]
0x180055b9f  test    rdi, rdi
0x180055ba2  jz      loc_180055CAD
0x180055ba8  jmp     loc_180055CA4
0x180055bad  cmp     edi, esi
0x180055baf  jz      loc_180055ADD
0x180055bb5  movaps  xmm6, xmmword ptr [rsp+0AE0h+var_A78+8]
0x180055bba  lea     rcx, [rsp+0AE0h+var_A78+8]; struct _GUID
0x180055bbf  mov     r14d, 1
0x180055bc5  movdqa  xmmword ptr [rsp+0AE0h+var_A78+8], xmm6
0x180055bcb  mov     r8d, r14d; int
0x180055bce  mov     edx, edi; unsigned int
0x180055bd0  call    ?rasSrvrFindAiNode@@YAPEAU_ACQUIRED_IPADDR@@U_GUID@@KH@Z; rasSrvrFindAiNode(_GUID,ulong,int)
0x180055bd5  mov     rbx, rax
0x180055bd8  test    rax, rax
0x180055bdb  jz      loc_180055DD3
0x180055be1  cmp     qword ptr cs:xmmword_1800D0740, r15
0x180055be8  jz      short loc_180055C20
0x180055bea  mov     r8d, edi
0x180055bed  mov     word ptr [rbp+9E0h+var_A40], r15w
0x180055bf2  lea     rdx, aClientAddress0; "******** CLIENT ADDRESS (0x%x) LEASE EX"...
0x180055bf9  lea     rcx, [rbp+9E0h+var_A40]
0x180055bfd  call    FormatRRASErrorString
0x180055c02  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055c09  lea     r8, [rbp+9E0h+var_A40]
0x180055c0d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055c14  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c20  lea     rdx, [rbp+9E0h+S]; S
0x180055c24  mov     dword ptr [rsp+0AE0h+Addr.S_un], edi
0x180055c28  lea     rcx, [rsp+0AE0h+Addr]; Addr
0x180055c2d  call    cs:__imp_RtlIpv4AddressToStringA
0x180055c34  nop     dword ptr [rax+rax+00h]
0x180055c39  lea     rax, [rbp+9E0h+S]
0x180055c3d  mov     r8d, r14d; cNumberOfSubStrings
0x180055c40  lea     r9, [rsp+0AE0h+plpwsSubStrings]; plpwsSubStrings
0x180055c45  mov     [rsp+0AE0h+plpwsSubStrings], rax
0x180055c4a  mov     edx, 4E75h; dwMessageId
0x180055c4f  mov     ecx, 2; wEventType
0x180055c54  call    cs:__imp_LogEventA
0x180055c5b  nop     dword ptr [rax+rax+00h]
0x180055c60  mov     r9, [rbx+20h]
0x180055c64  lea     rcx, [rsp+0AE0h+var_A78+8]
0x180055c69  mov     r8, [rbx+18h]
0x180055c6d  mov     edx, edi
0x180055c6f  movdqa  xmmword ptr [rsp+0AE0h+var_A78+8], xmm6
0x180055c75  mov     [rsp+0AE0h+var_AC0], r14d
0x180055c7a  call    RasSrvrReleaseAddress
0x180055c7f  jmp     loc_180055DD3
0x180055c84  mov     r9, [rax+20h]
0x180055c88  lea     rcx, [rsp+0AE0h+var_A88+8]
0x180055c8d  mov     r8, [rax+18h]
0x180055c91  mov     edx, [rax+10h]
0x180055c94  movdqa  [rsp+0AE0h+var_A88+8], xmm6
0x180055c9a  mov     [rsp+0AE0h+var_AC0], r14d
0x180055c9f  call    RasSrvrReleaseAddress
0x180055ca4  mov     rax, [rdi+18h]
0x180055ca8  test    rax, rax
0x180055cab  jnz     short loc_180055C84
0x180055cad  lea     rcx, [rsp+0AE0h+var_A88+8]
0x180055cb2  movdqa  [rsp+0AE0h+var_A88+8], xmm6
0x180055cb8  call    RasReleaseRoutingDomainAddressPool
0x180055cbd  test    eax, eax
0x180055cbf  jz      short loc_180055D00
0x180055cc1  cmp     qword ptr cs:xmmword_1800D0740, r15
0x180055cc8  jz      short loc_180055D00
0x180055cca  mov     r8d, eax
0x180055ccd  mov     word ptr [rbp+9E0h+var_A40], r15w
0x180055cd2  lea     rdx, aRasreleaserout_0; "RasReleaseRoutingDomainAddressPool fail"...
0x180055cd9  lea     rcx, [rbp+9E0h+var_A40]
0x180055cdd  call    FormatRRASErrorString
0x180055ce2  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055ce9  lea     r8, [rbp+9E0h+var_A40]
0x180055ced  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055cf4  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d00  mov     r9d, r14d
0x180055d03  mov     r8d, esi
0x180055d06  xor     edx, edx
0x180055d08  mov     ecx, esi; dwAddress
0x180055d0a  call    RasTcpSetProxyArp
0x180055d0f  lea     rcx, [rsp+0AE0h+var_A78+8]
0x180055d14  call    RasRdGetServerAdapterLuidIndex
0x180055d19  mov     ecx, eax
0x180055d1b  mov     edx, esi
0x180055d1d  call    ResetIpAddressOnInterface
0x180055d22  lea     r9, [rbp+9E0h+var_240]
0x180055d29  mov     dword ptr [rsp+0AE0h+Addr.S_un], 204h
0x180055d31  lea     r8, [rsp+0AE0h+Addr]
0x180055d36  mov     edx, 6
0x180055d3b  lea     rcx, [rsp+0AE0h+var_A78+8]
0x180055d40  call    RasRoutingDomainGetConfigParam
0x180055d45  mov     [rsp+0AE0h+var_AB0], r15d
0x180055d4a  lea     rdx, [rbp+9E0h+var_240]
0x180055d51  mov     [rsp+0AE0h+var_AB8], r15d
0x180055d56  xor     r9d, r9d
0x180055d59  xor     r8d, r8d
0x180055d5c  mov     [rsp+0AE0h+var_AC0], r15d
0x180055d61  xor     ecx, ecx
0x180055d63  call    cs:__imp_DhcpNotifyConfigChange
0x180055d6a  nop     dword ptr [rax+rax+00h]
0x180055d6f  test    eax, eax
0x180055d71  jz      short loc_180055DB9
0x180055d73  cmp     qword ptr cs:xmmword_1800D0740, r15
0x180055d7a  jz      short loc_180055DB9
0x180055d7c  mov     r9d, eax
0x180055d7f  mov     word ptr [rbp+9E0h+var_A40], r15w
0x180055d84  lea     r8, [rbp+9E0h+var_240]
0x180055d8b  lea     rdx, aDhcpnotifyconf; "DhcpNotifyConfigChange(%ws) failed and "...
0x180055d92  lea     rcx, [rbp+9E0h+var_A40]
0x180055d96  call    FormatRRASErrorString
0x180055d9b  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180055da2  lea     r8, [rbp+9E0h+var_A40]
0x180055da6  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180055dad  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180055db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055db9  xor     edx, edx
0x180055dbb  mov     dword ptr [rsp+0AE0h+Addr.S_un], r15d
0x180055dc0  lea     r9, [rsp+0AE0h+Addr]
0x180055dc5  lea     rcx, [rsp+0AE0h+var_A78+8]
0x180055dca  lea     r8d, [rdx+4]
0x180055dce  call    RasRoutingDomainSetConfigParam
0x180055dd3  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180055dda  call    cs:__imp_LeaveCriticalSection
0x180055de1  nop     dword ptr [rax+rax+00h]
0x180055de6  test    rbx, rbx
0x180055de9  jz      short loc_180055E1A
0x180055deb  mov     rcx, [rbx+18h]; Block
0x180055def  call    cs:__imp_free
0x180055df6  nop     dword ptr [rax+rax+00h]
0x180055dfb  mov     rcx, [rbx+20h]; Block
0x180055dff  call    cs:__imp_free
0x180055e06  nop     dword ptr [rax+rax+00h]
0x180055e0b  mov     rcx, rbx; hMem
0x180055e0e  call    cs:__imp_LocalFree
0x180055e15  nop     dword ptr [rax+rax+00h]
0x180055e1a  mov     rcx, [rbp+9E0h+var_30]
0x180055e21  xor     rcx, rsp; StackCookie
0x180055e24  call    __security_check_cookie
0x180055e29  lea     r11, [rsp+0AE0h+var_10]
0x180055e31  mov     rbx, [r11+28h]
0x180055e35  mov     rsi, [r11+30h]
0x180055e39  mov     rdi, [r11+38h]
0x180055e3d  movaps  xmm6, xmmword ptr [r11-10h]
0x180055e42  mov     rsp, r11
0x180055e45  pop     r15
0x180055e47  pop     r14
0x180055e49  pop     rbp
0x180055e4a  retn
```
