# RasSrvrDhcpCallback

- ea: `0x180053e5c`
- end: `0x180054265`
- name: `RasSrvrDhcpCallback`
- size: `1033`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x18005cfc4`
- `0x18005dbb0`

## callees

- `0x18004f39c`
- `0x180053e5c`
- `0x1800564e0`
- `0x1800588f4`
- `0x180058ab0`
- `0x180058b94`
- `0x180058dc4`
- `0x180058e78`
- `0x180059030`
- `0x1800689f0`
- `0x180071cec`
- `0x18007a104`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!free` at `0x180054220`
- `msvcrt!free` at `0x18005422a`
- `msvcrt!free` at `0x180054220`
- `msvcrt!free` at `0x18005422a`
- `KERNEL32!LocalFree` at `0x180054233`
- `KERNEL32!LocalFree` at `0x180054233`
- `KERNEL32!LeaveCriticalSection` at `0x180054211`
- `KERNEL32!LeaveCriticalSection` at `0x180054211`
- `KERNEL32!EnterCriticalSection` at `0x180053f1b`
- `KERNEL32!EnterCriticalSection` at `0x180053f1b`
- `ntdll!RtlIpv4AddressToStringA` at `0x180053f92`
- `ntdll!RtlIpv4AddressToStringA` at `0x180054078`
- `ntdll!RtlIpv4AddressToStringA` at `0x180053f92`
- `ntdll!RtlIpv4AddressToStringA` at `0x180054078`
- `rtutils!LogEventA` at `0x180053fb8`
- `rtutils!LogEventA` at `0x180054099`
- `rtutils!LogEventA` at `0x180053fb8`
- `rtutils!LogEventA` at `0x180054099`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x1800541a0`
- `dhcpcsvc!DhcpNotifyConfigChange` at `0x1800541a0`

## string_xrefs

- `0x1800541c0`: `DhcpNotifyConfigChange(%ws) failed and returned 0x%x`

## pseudocode

```c
void __fastcall RasSrvrDhcpCallback(unsigned int a1)
{
  DWORD NboServerIpv4Address; // esi
  void **AiNode; // rbx
  __int128 v4; // xmm6
  __int64 v5; // rdi
  __int128 v6; // xmm6
  void *v7; // r9
  void *v8; // r8
  __int64 v9; // r9
  __int64 v10; // r8
  int v11; // edx
  __int64 v12; // rax
  unsigned int v13; // eax
  unsigned int ServerAdapterLuidIndex; // eax
  unsigned int v15; // eax
  struct in_addr Addr; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v17[3]; // [rsp+50h] [rbp-B8h] BYREF
  LPSTR plpwsSubStrings; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v19[3]; // [rsp+70h] [rbp-98h] BYREF
  CHAR S[32]; // [rsp+88h] [rbp-80h] BYREF
  int v21; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v22[2044]; // [rsp+ACh] [rbp-5Ch] BYREF
  _BYTE v23[528]; // [rsp+8A8h] [rbp+7A0h] BYREF

  plpwsSubStrings = 0;
  v19[0] = 0;
  *(GUID *)&v17[1] = GUID_NULL;
  NboServerIpv4Address = RasRdGetNboServerIpv4Address(&v17[1]);
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v21) = 0;
    FormatRRASErrorString(&v21, L"RasSrvrDhcpCallback(0x%x)", a1);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v21);
  }
  AiNode = 0;
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( !a1 )
  {
    if ( !NboServerIpv4Address )
      goto LABEL_24;
    goto LABEL_5;
  }
  if ( a1 == NboServerIpv4Address )
  {
LABEL_5:
    memset_0(v23, 0, 0x204u);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"******** SERVER ADDRESS (0x%x) LEASE EXPIRED ********", NboServerIpv4Address);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v21);
    }
    Addr = (struct in_addr)NboServerIpv4Address;
    RtlIpv4AddressToStringA(&Addr, S);
    plpwsSubStrings = S;
    LogEventA(2u, 0x4E74u, 1u, &plpwsSubStrings);
    v4 = *(_OWORD *)&v17[1];
    *(_OWORD *)&v19[1] = *(_OWORD *)&v17[1];
    if ( !(unsigned int)RasGetRoutingDomainAddressPool(&v19[1], 1, v19) )
    {
      v5 = v19[0];
      if ( v19[0] )
      {
        while ( 1 )
        {
          v12 = *(_QWORD *)(v5 + 24);
          if ( !v12 )
            break;
          v9 = *(_QWORD *)(v12 + 32);
          v10 = *(_QWORD *)(v12 + 24);
          v11 = *(_DWORD *)(v12 + 16);
          *(_OWORD *)&v19[1] = v4;
          RasSrvrReleaseAddress((unsigned int)&v19[1], v11, v10, v9, 1);
        }
      }
      *(_OWORD *)&v19[1] = v4;
      v13 = RasReleaseRoutingDomainAddressPool(&v19[1]);
      if ( v13 && (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v21) = 0;
        FormatRRASErrorString(&v21, L"RasReleaseRoutingDomainAddressPool failed and returned %d", v13);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v21);
      }
    }
    RasTcpSetProxyArp(NboServerIpv4Address, 0, NboServerIpv4Address, 1u);
    ServerAdapterLuidIndex = RasRdGetServerAdapterLuidIndex(&v17[1]);
    ResetIpAddressOnInterface(ServerAdapterLuidIndex, NboServerIpv4Address);
    Addr = (struct in_addr)516;
    RasRoutingDomainGetConfigParam(&v17[1], 6, &Addr, v23);
    v15 = DhcpNotifyConfigChange(0, v23, 0, 0, 0, 0, 0);
    if ( v15 && (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"DhcpNotifyConfigChange(%ws) failed and returned 0x%x", v23, v15);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v21);
    }
    Addr = 0;
    RasRoutingDomainSetConfigParam(&v17[1], 0, 4, &Addr);
    goto LABEL_24;
  }
  v6 = *(_OWORD *)&v17[1];
  AiNode = (void **)rasSrvrFindAiNode((struct _GUID *)&v17[1], a1, 1);
  if ( AiNode )
  {
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(&v21, L"******** CLIENT ADDRESS (0x%x) LEASE EXPIRED ********", a1);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v21);
    }
    Addr = (struct in_addr)a1;
    RtlIpv4AddressToStringA(&Addr, S);
    plpwsSubStrings = S;
    LogEventA(2u, 0x4E75u, 1u, &plpwsSubStrings);
    v7 = AiNode[4];
    v8 = AiNode[3];
    *(_OWORD *)&v17[1] = v6;
    RasSrvrReleaseAddress((unsigned int)&v17[1], a1, (_DWORD)v8, (_DWORD)v7, 1);
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
0x180053e5c  mov     rax, rsp
0x180053e5f  mov     [rax+10h], rbx
0x180053e63  mov     [rax+18h], rsi
0x180053e67  push    rbp
0x180053e68  push    rdi
0x180053e69  push    r14
0x180053e6b  lea     rbp, [rax-9E8h]
0x180053e72  sub     rsp, 0AD0h
0x180053e79  movaps  xmmword ptr [rax-28h], xmm6
0x180053e7d  mov     rax, cs:__security_cookie
0x180053e84  xor     rax, rsp
0x180053e87  mov     [rbp+9E0h+var_30], rax
0x180053e8e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180053e95  mov     edi, ecx
0x180053e97  mov     [rsp+0AE0h+plpwsSubStrings], 0
0x180053ea0  lea     rcx, [rsp+0AE0h+var_A98+8]
0x180053ea5  mov     qword ptr [rsp+0AE0h+var_A78], 0
0x180053eae  movdqu  xmmword ptr [rsp+0AE0h+var_A98+8], xmm0
0x180053eb4  call    RasRdGetNboServerIpv4Address
0x180053eb9  mov     esi, eax
0x180053ebb  lea     rcx, [rbp+9E0h+var_A3C]; void *
0x180053ebf  xor     eax, eax
0x180053ec1  xor     edx, edx; Val
0x180053ec3  mov     r8d, 7FCh; Size
0x180053ec9  mov     [rbp+9E0h+var_A40], eax
0x180053ecc  call    memset_0
0x180053ed1  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180053ed9  jz      short loc_180053F12
0x180053edb  xor     eax, eax
0x180053edd  lea     rdx, aRassrvrdhcpcal; "RasSrvrDhcpCallback(0x%x)"
0x180053ee4  mov     r8d, edi
0x180053ee7  mov     word ptr [rbp+9E0h+var_A40], ax
0x180053eeb  lea     rcx, [rbp+9E0h+var_A40]
0x180053eef  call    FormatRRASErrorString
0x180053ef4  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053efb  lea     r8, [rbp+9E0h+var_A40]
0x180053eff  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053f06  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f12  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180053f19  xor     ebx, ebx
0x180053f1b  call    cs:__imp_EnterCriticalSection
0x180053f21  test    edi, edi
0x180053f23  jnz     loc_180053FF6
0x180053f29  test    esi, esi
0x180053f2b  jz      loc_18005420A
0x180053f31  xor     edx, edx; Val
0x180053f33  lea     rcx, [rbp+9E0h+var_240]; void *
0x180053f3a  mov     r8d, 204h; Size
0x180053f40  call    memset_0
0x180053f45  cmp     qword ptr cs:xmmword_1800C9740, rbx
0x180053f4c  jz      short loc_180053F85
0x180053f4e  xor     eax, eax
0x180053f50  lea     rdx, aServerAddress0; "******** SERVER ADDRESS (0x%x) LEASE EX"...
0x180053f57  mov     r8d, esi
0x180053f5a  mov     word ptr [rbp+9E0h+var_A40], ax
0x180053f5e  lea     rcx, [rbp+9E0h+var_A40]
0x180053f62  call    FormatRRASErrorString
0x180053f67  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180053f6e  lea     r8, [rbp+9E0h+var_A40]
0x180053f72  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053f79  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053f85  lea     rdx, [rbp+9E0h+S]; S
0x180053f89  mov     dword ptr [rsp+0AE0h+Addr.S_un], esi
0x180053f8d  lea     rcx, [rsp+0AE0h+Addr]; Addr
0x180053f92  call    cs:__imp_RtlIpv4AddressToStringA
0x180053f98  mov     r14d, 1
0x180053f9e  lea     rax, [rbp+9E0h+S]
0x180053fa2  lea     r9, [rsp+0AE0h+plpwsSubStrings]; plpwsSubStrings
0x180053fa7  mov     [rsp+0AE0h+plpwsSubStrings], rax
0x180053fac  mov     r8d, r14d; cNumberOfSubStrings
0x180053faf  mov     edx, 4E74h; dwMessageId
0x180053fb4  lea     ecx, [r14+1]; wEventType
0x180053fb8  call    cs:__imp_LogEventA
0x180053fbe  movaps  xmm6, xmmword ptr [rsp+0AE0h+var_A98+8]
0x180053fc3  lea     r8, [rsp+0AE0h+var_A78]
0x180053fc8  mov     edx, r14d
0x180053fcb  movdqa  xmmword ptr [rsp+0AE0h+var_A78+8], xmm6
0x180053fd1  lea     rcx, [rsp+0AE0h+var_A78+8]
0x180053fd6  call    RasGetRoutingDomainAddressPool
0x180053fdb  test    eax, eax
0x180053fdd  jnz     loc_180054140
0x180053fe3  mov     rdi, qword ptr [rsp+0AE0h+var_A78]
0x180053fe8  test    rdi, rdi
0x180053feb  jz      loc_1800540EC
0x180053ff1  jmp     loc_1800540E3
0x180053ff6  cmp     edi, esi
0x180053ff8  jz      loc_180053F31
0x180053ffe  movaps  xmm6, xmmword ptr [rsp+0AE0h+var_A98+8]
0x180054003  lea     rcx, [rsp+0AE0h+var_A98+8]; struct _GUID
0x180054008  mov     r14d, 1
0x18005400e  movdqa  xmmword ptr [rsp+0AE0h+var_A98+8], xmm6
0x180054014  mov     r8d, r14d; int
0x180054017  mov     edx, edi; unsigned int
0x180054019  call    ?rasSrvrFindAiNode@@YAPEAU_ACQUIRED_IPADDR@@U_GUID@@KH@Z; rasSrvrFindAiNode(_GUID,ulong,int)
0x18005401e  mov     rbx, rax
0x180054021  test    rax, rax
0x180054024  jz      loc_18005420A
0x18005402a  cmp     qword ptr cs:xmmword_1800C9740, 0
0x180054032  jz      short loc_18005406B
0x180054034  xor     ecx, ecx
0x180054036  lea     rdx, aClientAddress0; "******** CLIENT ADDRESS (0x%x) LEASE EX"...
0x18005403d  mov     word ptr [rbp+9E0h+var_A40], cx
0x180054041  mov     r8d, edi
0x180054044  lea     rcx, [rbp+9E0h+var_A40]
0x180054048  call    FormatRRASErrorString
0x18005404d  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180054054  lea     r8, [rbp+9E0h+var_A40]
0x180054058  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005405f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180054066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005406b  lea     rdx, [rbp+9E0h+S]; S
0x18005406f  mov     dword ptr [rsp+0AE0h+Addr.S_un], edi
0x180054073  lea     rcx, [rsp+0AE0h+Addr]; Addr
0x180054078  call    cs:__imp_RtlIpv4AddressToStringA
0x18005407e  lea     rax, [rbp+9E0h+S]
0x180054082  mov     r8d, r14d; cNumberOfSubStrings
0x180054085  lea     r9, [rsp+0AE0h+plpwsSubStrings]; plpwsSubStrings
0x18005408a  mov     [rsp+0AE0h+plpwsSubStrings], rax
0x18005408f  mov     edx, 4E75h; dwMessageId
0x180054094  mov     ecx, 2; wEventType
0x180054099  call    cs:__imp_LogEventA
0x18005409f  mov     r9, [rbx+20h]
0x1800540a3  lea     rcx, [rsp+0AE0h+var_A98+8]
0x1800540a8  mov     r8, [rbx+18h]
0x1800540ac  mov     edx, edi
0x1800540ae  movdqa  xmmword ptr [rsp+0AE0h+var_A98+8], xmm6
0x1800540b4  mov     [rsp+0AE0h+var_AC0], r14d
0x1800540b9  call    RasSrvrReleaseAddress
0x1800540be  jmp     loc_18005420A
0x1800540c3  mov     r9, [rax+20h]
0x1800540c7  lea     rcx, [rsp+0AE0h+var_A78+8]
0x1800540cc  mov     r8, [rax+18h]
0x1800540d0  mov     edx, [rax+10h]
0x1800540d3  movdqa  xmmword ptr [rsp+0AE0h+var_A78+8], xmm6
0x1800540d9  mov     [rsp+0AE0h+var_AC0], r14d
0x1800540de  call    RasSrvrReleaseAddress
0x1800540e3  mov     rax, [rdi+18h]
0x1800540e7  test    rax, rax
0x1800540ea  jnz     short loc_1800540C3
0x1800540ec  lea     rcx, [rsp+0AE0h+var_A78+8]
0x1800540f1  movdqa  xmmword ptr [rsp+0AE0h+var_A78+8], xmm6
0x1800540f7  call    RasReleaseRoutingDomainAddressPool
0x1800540fc  test    eax, eax
0x1800540fe  jz      short loc_180054140
0x180054100  cmp     qword ptr cs:xmmword_1800C9740, rbx
0x180054107  jz      short loc_180054140
0x180054109  xor     ecx, ecx
0x18005410b  lea     rdx, aRasreleaserout_0; "RasReleaseRoutingDomainAddressPool fail"...
0x180054112  mov     word ptr [rbp+9E0h+var_A40], cx
0x180054116  mov     r8d, eax
0x180054119  lea     rcx, [rbp+9E0h+var_A40]
0x18005411d  call    FormatRRASErrorString
0x180054122  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180054129  lea     r8, [rbp+9E0h+var_A40]
0x18005412d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180054134  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005413b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054140  mov     r9d, r14d
0x180054143  mov     r8d, esi
0x180054146  xor     edx, edx
0x180054148  mov     ecx, esi; dwAddress
0x18005414a  call    RasTcpSetProxyArp
0x18005414f  lea     rcx, [rsp+0AE0h+var_A98+8]
0x180054154  call    RasRdGetServerAdapterLuidIndex
0x180054159  mov     ecx, eax
0x18005415b  mov     edx, esi
0x18005415d  call    ResetIpAddressOnInterface
0x180054162  lea     r9, [rbp+9E0h+var_240]
0x180054169  mov     dword ptr [rsp+0AE0h+Addr.S_un], 204h
0x180054171  lea     r8, [rsp+0AE0h+Addr]
0x180054176  mov     edx, 6
0x18005417b  lea     rcx, [rsp+0AE0h+var_A98+8]
0x180054180  call    RasRoutingDomainGetConfigParam
0x180054185  mov     [rsp+0AE0h+var_AB0], ebx
0x180054189  lea     rdx, [rbp+9E0h+var_240]
0x180054190  mov     [rsp+0AE0h+var_AB8], ebx
0x180054194  xor     r9d, r9d
0x180054197  xor     r8d, r8d
0x18005419a  mov     [rsp+0AE0h+var_AC0], ebx
0x18005419e  xor     ecx, ecx
0x1800541a0  call    cs:__imp_DhcpNotifyConfigChange
0x1800541a6  test    eax, eax
0x1800541a8  jz      short loc_1800541F1
0x1800541aa  cmp     qword ptr cs:xmmword_1800C9740, rbx
0x1800541b1  jz      short loc_1800541F1
0x1800541b3  xor     ecx, ecx
0x1800541b5  lea     r8, [rbp+9E0h+var_240]
0x1800541bc  mov     word ptr [rbp+9E0h+var_A40], cx
0x1800541c0  lea     rdx, aDhcpnotifyconf; "DhcpNotifyConfigChange(%ws) failed and "...
0x1800541c7  lea     rcx, [rbp+9E0h+var_A40]
0x1800541cb  mov     r9d, eax
0x1800541ce  call    FormatRRASErrorString
0x1800541d3  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800541da  lea     r8, [rbp+9E0h+var_A40]
0x1800541de  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800541e5  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800541ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800541f1  xor     edx, edx
0x1800541f3  mov     dword ptr [rsp+0AE0h+Addr.S_un], ebx
0x1800541f7  lea     r9, [rsp+0AE0h+Addr]
0x1800541fc  lea     rcx, [rsp+0AE0h+var_A98+8]
0x180054201  lea     r8d, [rdx+4]
0x180054205  call    RasRoutingDomainSetConfigParam
0x18005420a  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180054211  call    cs:__imp_LeaveCriticalSection
0x180054217  test    rbx, rbx
0x18005421a  jz      short loc_180054239
0x18005421c  mov     rcx, [rbx+18h]; Block
0x180054220  call    cs:__imp_free
0x180054226  mov     rcx, [rbx+20h]; Block
0x18005422a  call    cs:__imp_free
0x180054230  mov     rcx, rbx; hMem
0x180054233  call    cs:__imp_LocalFree
0x180054239  mov     rcx, [rbp+9E0h+var_30]
0x180054240  xor     rcx, rsp; StackCookie
0x180054243  call    __security_check_cookie
0x180054248  lea     r11, [rsp+0AE0h+var_10]
0x180054250  mov     rbx, [r11+28h]
0x180054254  mov     rsi, [r11+30h]
0x180054258  movaps  xmm6, xmmword ptr [r11-10h]
0x18005425d  mov     rsp, r11
0x180054260  pop     r14
0x180054262  pop     rdi
0x180054263  pop     rbp
0x180054264  retn
```
