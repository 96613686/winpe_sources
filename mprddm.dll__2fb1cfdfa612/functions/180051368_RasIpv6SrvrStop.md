# RasIpv6SrvrStop

- ea: `0x180051368`
- end: `0x1800519e4`
- name: `RasIpv6SrvrStop`
- size: `1660`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `3`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001abb0`
- `0x18001f8e0`
- `0x180050870`

## callees

- `0x180002bbe`
- `0x180025c98`
- `0x18004cf58`
- `0x18004e19c`
- `0x18004e9b8`
- `0x180051368`
- `0x180055410`
- `0x1800568d0`
- `0x1800588f4`
- `0x180058ae4`
- `0x180058b34`
- `0x180058bcc`
- `0x180058dc4`
- `0x180058e78`
- `0x180059030`
- `0x18005b360`
- `0x180071cec`
- `0x180073664`
- `0x1800748c8`
- `0x18007a34c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1800518f4`
- `KERNEL32!DeviceIoControl` at `0x1800518f4`
- `KERNEL32!GetLastError` at `0x1800518fe`
- `KERNEL32!GetLastError` at `0x1800518fe`
- `KERNEL32!LeaveCriticalSection` at `0x1800519a8`
- `KERNEL32!LeaveCriticalSection` at `0x1800519a8`
- `KERNEL32!EnterCriticalSection` at `0x18005153a`
- `KERNEL32!EnterCriticalSection` at `0x18005153a`
- `ntdll!RtlIpv6AddressToStringA` at `0x1800515b5`
- `ntdll!RtlIpv6AddressToStringA` at `0x1800515b5`
- `rtutils!LogEventA` at `0x1800515d7`
- `rtutils!LogEventA` at `0x1800515d7`

## string_xrefs

- `0x18005148c`: `RasSrvrStop: GetRoutingDomainConfigData (compartmentId) failed and returned %d`
- `0x1800517be`: `AddOrRemoveIpv6Prefix completes with 0x%x`
- `0x180051882`: `SetIpv6InterfaceProperties completes with 0x%x`

## pseudocode

```c
void __fastcall RasIpv6SrvrStop(struct in6_addr *a1, char a2, int a3)
{
  __int64 NboServerIpv6Address; // rax
  int v7; // eax
  BOOL v8; // r12d
  unsigned int RoutingDomainConfigData; // eax
  __int64 v10; // rdx
  int v11; // r14d
  int v12; // edi
  int v13; // esi
  int v14; // edi
  int RoutingDomainAddressPool; // eax
  __int64 v16; // rsi
  struct in6_addr v17; // xmm1
  struct in6_addr *v18; // rax
  unsigned int v19; // eax
  __int64 ServerAdapterIPv6IfId; // rax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  DWORD LastError; // eax
  int lpOutBuffer; // [rsp+20h] [rbp-E0h]
  NET_IFINDEX InterfaceIndex; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+48h] [rbp-B8h] BYREF
  LPSTR plpwsSubStrings[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct in6_addr Buf1; // [rsp+60h] [rbp-A0h] BYREF
  DWORD BytesReturned[4]; // [rsp+70h] [rbp-90h] BYREF
  struct in6_addr v31; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v32[3]; // [rsp+90h] [rbp-70h] BYREF
  int v33; // [rsp+C0h] [rbp-40h]
  __int128 v34; // [rsp+D0h] [rbp-30h]
  __int128 v35; // [rsp+E0h] [rbp-20h]
  struct in6_addr Addr; // [rsp+F0h] [rbp-10h] BYREF
  int v37; // [rsp+100h] [rbp+0h]
  __int128 OutBuffer; // [rsp+108h] [rbp+8h] BYREF
  int v39; // [rsp+118h] [rbp+18h]
  _OWORD v40[3]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v41[30]; // [rsp+150h] [rbp+50h]
  __int16 v42; // [rsp+16Eh] [rbp+6Eh]
  CHAR S[128]; // [rsp+170h] [rbp+70h] BYREF
  int v44; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v45[2044]; // [rsp+1F4h] [rbp+F4h] BYREF

  OutBuffer = 0;
  v40[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v40[2] = *(_OWORD *)L"000-0000-000000000000}";
  v39 = 0;
  v40[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  *(_OWORD *)v41 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v41[14] = *(_OWORD *)L"000000}";
  BytesReturned[0] = 0;
  *(_QWORD *)Buf1.u.Byte = 0;
  v42 = 0;
  NboServerIpv6Address = RasRdGetNboServerIpv6Address(v32, a1);
  v34 = *(_OWORD *)NboServerIpv6Address;
  v35 = *(_OWORD *)(NboServerIpv6Address + 16);
  Addr = *(struct in6_addr *)(NboServerIpv6Address + 32);
  v37 = *(_DWORD *)(NboServerIpv6Address + 48);
  v7 = memcmp_0(a1, &GUID_NULL, 0x10u);
  v27 = 1;
  v44 = 0;
  v8 = v7 == 0;
  memset_0(v45, 0, sizeof(v45));
  if ( !v8 )
  {
    RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &v27);
    if ( RoutingDomainConfigData && (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v44) = 0;
      FormatRRASErrorString(
        &v44,
        L"RasSrvrStop: GetRoutingDomainConfigData (compartmentId) failed and returned %d",
        RoutingDomainConfigData);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v44);
    }
    MprConvertGuidToString(a1, v10, v40);
  }
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v44) = 0;
    FormatRRASErrorString(&v44, L"RasIpv6SrvrStop - RDID:%ws", v40);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v44);
  }
  v11 = dword_1800C8650;
  v12 = a2 & 8;
  v13 = a2 & 0x20;
  if ( !dword_1800C8650 || v8 )
    RasDhcpIpv6Uninitialize();
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( !v12 && !v13 )
  {
    InterfaceIndex = 0;
    RasRoutingDomainSetConfigParam(a1, 3, 4, &InterfaceIndex);
  }
  if ( (!v11 || v8)
    && a3
    && (Addr.u.Word[0]
     || __PAIR32__(Addr.u.Word[1], 0) != Addr.u.Word[2]
     || __PAIR32__(Addr.u.Word[3], 0) != Addr.u.Word[4]
     || __PAIR32__(Addr.u.Word[5], 0) != Addr.u.Word[6]
     || Addr.u.Word[7]) )
  {
    plpwsSubStrings[0] = 0;
    RtlIpv6AddressToStringA(&Addr, S);
    plpwsSubStrings[0] = S;
    LogEventA(2u, 0x4E74u, 1u, plpwsSubStrings);
  }
  if ( !v12 )
  {
    v14 = 0;
    if ( !v13 && !a3 )
    {
      v31 = *a1;
      RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v31, 2, &Buf1);
      LOBYTE(v14) = RoutingDomainAddressPool == 0;
      if ( !RoutingDomainAddressPool )
      {
        v16 = *(_QWORD *)Buf1.u.Byte;
        if ( *(_QWORD *)Buf1.u.Byte )
        {
          while ( 1 )
          {
            v18 = *(struct in6_addr **)(v16 + 16);
            if ( !v18 )
              break;
            v17 = *a1;
            v31 = v18[1];
            *(struct in6_addr *)plpwsSubStrings = v17;
            RasSrvrReleaseIpv6Address((struct _GUID *)plpwsSubStrings, &v31);
          }
        }
        v31 = *a1;
        v19 = RasReleaseRoutingDomainAddressPool(&v31);
        if ( v19 )
        {
          if ( (_QWORD)xmmword_1800C9740 )
          {
            LOWORD(v44) = 0;
            FormatRRASErrorString(&v44, L"RasReleaseRoutingDomainAddressPool failed and returned %d", v19);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800C9740,
              &v44);
          }
        }
        else
        {
          v14 = 0;
        }
      }
    }
    RasSrvrSetProxyArpV6(&Addr, 0, &Addr, v27, (const struct _GUID *)a1);
    CleanupIpv6ProxyArpSocket((const struct _GUID *)a1);
    v33 = v37;
    v32[0] = v34;
    v32[1] = v35;
    Addr = 0;
    v32[2] = 0;
    RasRdSetNboServerIpv6Address(a1, v32);
    InterfaceIndex = 0;
    LODWORD(plpwsSubStrings[0]) = 4;
    RasRoutingDomainGetConfigParam(a1, 5, plpwsSubStrings, &InterfaceIndex);
    if ( InterfaceIndex )
    {
      InterfaceIndex = 0;
      LODWORD(plpwsSubStrings[0]) = 4;
      RasRoutingDomainGetConfigParam(a1, 8, plpwsSubStrings, &InterfaceIndex);
      ServerAdapterIPv6IfId = RasRdGetServerAdapterIPv6IfId(a1);
      *(struct in6_addr *)plpwsSubStrings = *a1;
      *(_QWORD *)v31.u.Byte = ServerAdapterIPv6IfId;
      if ( (unsigned int)RasGetRoutingDomainAddressPool(plpwsSubStrings, 2, &Buf1) )
      {
        if ( v14 != 1 )
        {
LABEL_44:
          v23 = SetIpv6InterfaceProperties(InterfaceIndex, lpOutBuffer, 0);
          if ( (_QWORD)xmmword_1800C9740 )
          {
            LOWORD(v44) = 0;
            FormatRRASErrorString(&v44, L"SetIpv6InterfaceProperties completes with 0x%x", v23);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800C9740,
              &v44);
          }
          DWORD2(OutBuffer) = v27;
          LODWORD(OutBuffer) = 0;
          if ( !DeviceIoControl(
                  HelperWanArpv6Handle,
                  0x90018014,
                  &OutBuffer,
                  0x14u,
                  &OutBuffer,
                  0x14u,
                  BytesReturned,
                  0) )
          {
            LastError = GetLastError();
            if ( (_QWORD)xmmword_1800C9740 )
            {
              LOWORD(v44) = 0;
              FormatRRASErrorString(&v44, L"Error %d unmapping Ipv6 server adapter", LastError);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
                gRasIpAddrMgmtEtwContext,
                xmmword_1800C9740,
                &v44);
            }
          }
          if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              *((_QWORD *)&xmmword_1800C9740 + 1),
              L"RasSrvrIpv6AdapterUnMapped");
          LODWORD(plpwsSubStrings[0]) = 0;
          RasRoutingDomainSetConfigParam(a1, 5, 4, plpwsSubStrings);
          Buf1 = *a1;
          RasSrvrInterfaceIdDelete(&Buf1);
          goto LABEL_52;
        }
      }
      else if ( *(_QWORD *)Buf1.u.Byte )
      {
        v21 = AddOrRemoveIpv6PrefixForAdvertisement(*(_QWORD *)Buf1.u.Byte, InterfaceIndex, 1, 0);
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v44) = 0;
          FormatRRASErrorString(&v44, L"AddOrRemoveIpv6Prefix completes with 0x%x", v21);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v44);
        }
      }
      Buf1 = *a1;
      v22 = RasReleaseRoutingDomainAddressPool(&Buf1);
      if ( v22 && (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v44) = 0;
        FormatRRASErrorString(&v44, L"RasReleaseRoutingDomainAddressPool failed and returned %d", v22);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v44);
      }
      goto LABEL_44;
    }
  }
LABEL_52:
  LeaveCriticalSection(&RasSrvrCriticalSection);
  if ( !v11 || v8 )
    WriteDialinInterfaceIndexIntoRegistry(0, 0);
}

```

## disassembly

```asm
0x180051368  push    rbp
0x18005136a  push    rbx
0x18005136b  push    rsi
0x18005136c  push    rdi
0x18005136d  push    r12
0x18005136f  push    r13
0x180051371  push    r14
0x180051373  push    r15
0x180051375  lea     rbp, [rsp-908h]
0x18005137d  sub     rsp, 0A08h
0x180051384  mov     rax, cs:__security_cookie
0x18005138b  xor     rax, rsp
0x18005138e  mov     [rbp+940h+var_50], rax
0x180051395  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18005139c  xorps   xmm0, xmm0
0x18005139f  movups  [rbp+940h+OutBuffer], xmm0
0x1800513a3  xor     eax, eax
0x1800513a5  mov     esi, edx
0x1800513a7  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800513ae  mov     rbx, rcx
0x1800513b1  movaps  [rbp+940h+var_920], xmm0
0x1800513b5  xor     r13d, r13d
0x1800513b8  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x1800513bf  mov     rdx, rcx
0x1800513c2  movaps  [rbp+940h+var_900], xmm0
0x1800513c6  lea     rcx, [rbp+940h+var_9B0]
0x1800513ca  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x1800513d1  mov     r15d, r8d
0x1800513d4  mov     [rbp+940h+var_928], eax
0x1800513d7  movaps  [rbp+940h+var_910], xmm1
0x1800513db  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x1800513e2  movaps  xmmword ptr [rbp+940h+var_8F0], xmm1
0x1800513e6  movups  xmmword ptr [rbp+940h+var_8F0+0Eh], xmm0
0x1800513ea  mov     [rsp+0A40h+BytesReturned], r13d
0x1800513ef  mov     qword ptr [rsp+0A40h+Buf1], r13
0x1800513f4  mov     [rbp+940h+var_8D2], ax
0x1800513f8  call    RasRdGetNboServerIpv6Address
0x1800513fd  lea     r8d, [r13+10h]; Size
0x180051401  mov     rcx, rbx; Buf1
0x180051404  lea     rdx, GUID_NULL; Buf2
0x18005140b  movups  xmm0, xmmword ptr [rax]
0x18005140e  movups  [rbp+940h+var_970], xmm0
0x180051412  movups  xmm1, xmmword ptr [rax+10h]
0x180051416  movups  [rbp+940h+var_960], xmm1
0x18005141a  movups  xmm0, xmmword ptr [rax+20h]
0x18005141e  movups  xmmword ptr [rbp+940h+Addr.u], xmm0
0x180051422  mov     eax, [rax+30h]
0x180051425  mov     [rbp+940h+var_940], eax
0x180051428  call    memcmp_0
0x18005142d  test    eax, eax
0x18005142f  mov     [rsp+0A40h+var_9F8], 1
0x180051437  mov     r12d, r13d
0x18005143a  mov     [rbp+940h+var_850], r13d
0x180051441  setz    r12b
0x180051445  lea     rcx, [rbp+940h+var_84C]; void *
0x18005144c  xor     edx, edx; Val
0x18005144e  mov     r8d, 7FCh; Size
0x180051454  call    memset_0
0x180051459  test    r12d, r12d
0x18005145c  jnz     short loc_1800514CC
0x18005145e  lea     r9, [rsp+0A40h+var_9F8]
0x180051463  mov     edx, 100h
0x180051468  lea     r8d, [r13+4]
0x18005146c  mov     rcx, rbx
0x18005146f  call    GetRoutingDomainConfigData
0x180051474  test    eax, eax
0x180051476  jz      short loc_1800514C0
0x180051478  cmp     qword ptr cs:xmmword_1800C9740, r13
0x18005147f  jz      short loc_1800514C0
0x180051481  mov     r8d, eax
0x180051484  mov     word ptr [rbp+940h+var_850], r13w
0x18005148c  lea     rdx, aRassrvrstopGet; "RasSrvrStop: GetRoutingDomainConfigData"...
0x180051493  lea     rcx, [rbp+940h+var_850]
0x18005149a  call    FormatRRASErrorString
0x18005149f  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800514a6  lea     r8, [rbp+940h+var_850]
0x1800514ad  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800514b4  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800514bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800514c0  lea     r8, [rbp+940h+var_920]
0x1800514c4  mov     rcx, rbx
0x1800514c7  call    MprConvertGuidToString
0x1800514cc  cmp     qword ptr cs:xmmword_1800C9740, r13
0x1800514d3  jz      short loc_180051515
0x1800514d5  lea     r8, [rbp+940h+var_920]
0x1800514d9  mov     word ptr [rbp+940h+var_850], r13w
0x1800514e1  lea     rdx, aRasipv6srvrsto; "RasIpv6SrvrStop - RDID:%ws"
0x1800514e8  lea     rcx, [rbp+940h+var_850]
0x1800514ef  call    FormatRRASErrorString
0x1800514f4  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800514fb  lea     r8, [rbp+940h+var_850]
0x180051502  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180051509  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180051510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051515  mov     r14d, cs:dword_1800C8650
0x18005151c  mov     edi, esi
0x18005151e  and     edi, 8
0x180051521  and     esi, 20h
0x180051524  test    r14d, r14d
0x180051527  jz      short loc_18005152E
0x180051529  test    r12d, r12d
0x18005152c  jz      short loc_180051533
0x18005152e  call    ?RasDhcpIpv6Uninitialize@@YAXXZ; RasDhcpIpv6Uninitialize(void)
0x180051533  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005153a  call    cs:__imp_EnterCriticalSection
0x180051540  test    edi, edi
0x180051542  jnz     short loc_180051561
0x180051544  test    esi, esi
0x180051546  jnz     short loc_180051561
0x180051548  lea     r9, [rsp+0A40h+InterfaceIndex]
0x18005154d  mov     [rsp+0A40h+InterfaceIndex], r13d
0x180051552  lea     edx, [rdi+3]
0x180051555  mov     rcx, rbx
0x180051558  lea     r8d, [rdi+4]
0x18005155c  call    RasRoutingDomainSetConfigParam
0x180051561  test    r14d, r14d
0x180051564  jz      short loc_18005156B
0x180051566  test    r12d, r12d
0x180051569  jz      short loc_1800515DD
0x18005156b  test    r15d, r15d
0x18005156e  jz      short loc_1800515DD
0x180051570  cmp     word ptr [rbp+940h+Addr.u], r13w
0x180051575  jnz     short loc_1800515A8
0x180051577  cmp     word ptr [rbp+940h+Addr.u+2], r13w
0x18005157c  jnz     short loc_1800515A8
0x18005157e  cmp     word ptr [rbp+940h+Addr.u+4], r13w
0x180051583  jnz     short loc_1800515A8
0x180051585  cmp     word ptr [rbp+940h+Addr.u+6], r13w
0x18005158a  jnz     short loc_1800515A8
0x18005158c  cmp     word ptr [rbp+940h+Addr.u+8], r13w
0x180051591  jnz     short loc_1800515A8
0x180051593  cmp     word ptr [rbp+940h+Addr.u+0Ah], r13w
0x180051598  jnz     short loc_1800515A8
0x18005159a  cmp     word ptr [rbp+940h+Addr.u+0Ch], r13w
0x18005159f  jnz     short loc_1800515A8
0x1800515a1  cmp     word ptr [rbp+940h+Addr.u+0Eh], r13w
0x1800515a6  jz      short loc_1800515DD
0x1800515a8  lea     rdx, [rbp+940h+S]; S
0x1800515ac  mov     [rsp+0A40h+plpwsSubStrings], r13
0x1800515b1  lea     rcx, [rbp+940h+Addr]; Addr
0x1800515b5  call    cs:__imp_RtlIpv6AddressToStringA
0x1800515bb  mov     ecx, 2; wEventType
0x1800515c0  lea     rax, [rbp+940h+S]
0x1800515c4  lea     r9, [rsp+0A40h+plpwsSubStrings]; plpwsSubStrings
0x1800515c9  mov     [rsp+0A40h+plpwsSubStrings], rax
0x1800515ce  mov     edx, 4E74h; dwMessageId
0x1800515d3  lea     r8d, [rcx-1]; cNumberOfSubStrings
0x1800515d7  call    cs:__imp_LogEventA
0x1800515dd  test    edi, edi
0x1800515df  jnz     loc_1800519A1
0x1800515e5  mov     edi, r13d
0x1800515e8  test    esi, esi
0x1800515ea  jnz     loc_1800516C7
0x1800515f0  test    r15d, r15d
0x1800515f3  jnz     loc_1800516C7
0x1800515f9  movaps  xmm0, xmmword ptr [rbx]
0x1800515fc  lea     r8, [rsp+0A40h+Buf1]
0x180051601  lea     edx, [rsi+2]
0x180051604  movdqa  xmmword ptr [rbp+940h+var_9C0.u], xmm0
0x180051609  lea     rcx, [rbp+940h+var_9C0]
0x18005160d  call    RasGetRoutingDomainAddressPool
0x180051612  test    eax, eax
0x180051614  setz    dil
0x180051618  test    eax, eax
0x18005161a  jnz     loc_1800516C7
0x180051620  mov     rsi, qword ptr [rsp+0A40h+Buf1]
0x180051625  test    rsi, rsi
0x180051628  jz      short loc_180051665
0x18005162a  jmp     short loc_18005165C
0x18005162c  movups  xmm0, xmmword ptr [rax+10h]
0x180051630  lea     rdx, [rbp+940h+var_9C0]; Addr
0x180051634  mov     r9, [rax+28h]
0x180051638  movaps  xmm1, xmmword ptr [rbx]
0x18005163b  lea     rcx, [rsp+0A40h+plpwsSubStrings]; struct _GUID *
0x180051640  mov     r8, [rax+20h]
0x180051644  movdqu  xmmword ptr [rbp+940h+var_9C0.u], xmm0
0x180051649  mov     dword ptr [rsp+0A40h+lpOutBuffer], 1
0x180051651  movdqa  xmmword ptr [rsp+0A40h+plpwsSubStrings], xmm1
0x180051657  call    RasSrvrReleaseIpv6Address
0x18005165c  mov     rax, [rsi+10h]
0x180051660  test    rax, rax
0x180051663  jnz     short loc_18005162C
0x180051665  movaps  xmm0, xmmword ptr [rbx]
0x180051668  lea     rcx, [rbp+940h+var_9C0]
0x18005166c  movdqa  xmmword ptr [rbp+940h+var_9C0.u], xmm0
0x180051671  call    RasReleaseRoutingDomainAddressPool
0x180051676  test    eax, eax
0x180051678  jz      short loc_1800516C4
0x18005167a  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180051681  jz      short loc_1800516C7
0x180051683  mov     r8d, eax
0x180051686  mov     word ptr [rbp+940h+var_850], r13w
0x18005168e  lea     rdx, aRasreleaserout_0; "RasReleaseRoutingDomainAddressPool fail"...
0x180051695  lea     rcx, [rbp+940h+var_850]
0x18005169c  call    FormatRRASErrorString
0x1800516a1  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800516a8  lea     r8, [rbp+940h+var_850]
0x1800516af  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800516b6  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800516bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516c2  jmp     short loc_1800516C7
0x1800516c4  mov     edi, r13d
0x1800516c7  mov     r9d, [rsp+0A40h+var_9F8]; unsigned int
0x1800516cc  lea     r8, [rbp+940h+Addr]; struct in6_addr *
0x1800516d0  xor     edx, edx; int
0x1800516d2  mov     [rsp+0A40h+lpOutBuffer], rbx; int
0x1800516d7  lea     rcx, [rbp+940h+Addr]; Addr
0x1800516db  call    ?RasSrvrSetProxyArpV6@@YAXPEBUin6_addr@@H0IPEBU_GUID@@@Z; RasSrvrSetProxyArpV6(in6_addr const *,int,in6_addr const *,uint,_GUID const *)
0x1800516e0  mov     rcx, rbx; struct _GUID *
0x1800516e3  call    ?CleanupIpv6ProxyArpSocket@@YAXPEBU_GUID@@@Z; CleanupIpv6ProxyArpSocket(_GUID const *)
0x1800516e8  movups  xmm0, [rbp+940h+var_970]
0x1800516ec  mov     eax, [rbp+940h+var_940]
0x1800516ef  lea     rdx, [rbp+940h+var_9B0]
0x1800516f3  movups  xmm1, [rbp+940h+var_960]
0x1800516f7  mov     rcx, rbx
0x1800516fa  mov     [rbp+940h+var_980], eax
0x1800516fd  xorps   xmm2, xmm2
0x180051700  movaps  [rbp+940h+var_9B0], xmm0
0x180051704  movaps  [rbp+940h+var_9A0], xmm1
0x180051708  movups  xmmword ptr [rbp+940h+Addr.u], xmm2
0x18005170c  movaps  [rbp+940h+var_990], xmm2
0x180051710  call    RasRdSetNboServerIpv6Address
0x180051715  mov     esi, 4
0x18005171a  mov     [rsp+0A40h+InterfaceIndex], r13d
0x18005171f  lea     r9, [rsp+0A40h+InterfaceIndex]
0x180051724  mov     dword ptr [rsp+0A40h+plpwsSubStrings], esi
0x180051728  lea     r8, [rsp+0A40h+plpwsSubStrings]
0x18005172d  mov     rcx, rbx
0x180051730  lea     r15d, [rsi+1]
0x180051734  mov     edx, r15d
0x180051737  call    RasRoutingDomainGetConfigParam
0x18005173c  cmp     [rsp+0A40h+InterfaceIndex], r13d
0x180051741  jz      loc_1800519A1
0x180051747  lea     r9, [rsp+0A40h+InterfaceIndex]
0x18005174c  mov     [rsp+0A40h+InterfaceIndex], r13d
0x180051751  lea     r8, [rsp+0A40h+plpwsSubStrings]
0x180051756  mov     dword ptr [rsp+0A40h+plpwsSubStrings], esi
0x18005175a  lea     edx, [rsi+4]
0x18005175d  mov     rcx, rbx
0x180051760  call    RasRoutingDomainGetConfigParam
0x180051765  mov     rcx, rbx
0x180051768  call    RasRdGetServerAdapterIPv6IfId
0x18005176d  movaps  xmm0, xmmword ptr [rbx]
0x180051770  lea     r8, [rsp+0A40h+Buf1]
0x180051775  lea     edx, [rsi-2]
0x180051778  movdqa  xmmword ptr [rsp+0A40h+plpwsSubStrings], xmm0
0x18005177e  lea     rcx, [rsp+0A40h+plpwsSubStrings]
0x180051783  mov     qword ptr [rbp+940h+var_9C0.u], rax
0x180051787  call    RasGetRoutingDomainAddressPool
0x18005178c  test    eax, eax
0x18005178e  jnz     short loc_1800517F4
0x180051790  mov     rcx, qword ptr [rsp+0A40h+Buf1]
0x180051795  test    rcx, rcx
0x180051798  jz      short loc_1800517F9
0x18005179a  mov     edx, [rsp+0A40h+InterfaceIndex]
0x18005179e  lea     r8d, [rsi-3]
0x1800517a2  xor     r9d, r9d
0x1800517a5  call    AddOrRemoveIpv6PrefixForAdvertisement
0x1800517aa  cmp     qword ptr cs:xmmword_1800C9740, r13
0x1800517b1  jz      short loc_1800517F9
0x1800517b3  mov     r8d, eax
0x1800517b6  mov     word ptr [rbp+940h+var_850], r13w
0x1800517be  lea     rdx, aAddorremoveipv_0; "AddOrRemoveIpv6Prefix completes with 0x"...
0x1800517c5  lea     rcx, [rbp+940h+var_850]
0x1800517cc  call    FormatRRASErrorString
0x1800517d1  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800517d8  lea     r8, [rbp+940h+var_850]
0x1800517df  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800517e6  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800517ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800517f2  jmp     short loc_1800517F9
0x1800517f4  cmp     edi, 1
0x1800517f7  jnz     short loc_180051858
0x1800517f9  movaps  xmm0, xmmword ptr [rbx]
0x1800517fc  lea     rcx, [rsp+0A40h+Buf1]
0x180051801  movdqa  [rsp+0A40h+Buf1], xmm0
0x180051807  call    RasReleaseRoutingDomainAddressPool
0x18005180c  test    eax, eax
0x18005180e  jz      short loc_180051858
0x180051810  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180051817  jz      short loc_180051858
0x180051819  mov     r8d, eax
0x18005181c  mov     word ptr [rbp+940h+var_850], r13w
0x180051824  lea     rdx, aRasreleaserout_0; "RasReleaseRoutingDomainAddressPool fail"...
0x18005182b  lea     rcx, [rbp+940h+var_850]
0x180051832  call    FormatRRASErrorString
0x180051837  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005183e  lea     r8, [rbp+940h+var_850]
0x180051845  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005184c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180051853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051858  mov     ecx, [rsp+0A40h+InterfaceIndex]; InterfaceIndex
0x18005185c  xor     r9d, r9d
0x18005185f  xor     r8d, r8d
0x180051862  mov     byte ptr [rsp+0A40h+nOutBufferSize], r13b; char
0x180051867  xor     edx, edx
0x180051869  call    SetIpv6InterfaceProperties
0x18005186e  cmp     qword ptr cs:xmmword_1800C9740, r13
0x180051875  jz      short loc_1800518B6
0x180051877  mov     r8d, eax
  ... truncated ...
```
