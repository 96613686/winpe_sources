# RasIpv6SrvrStop

- ea: `0x180052d5c`
- end: `0x180053439`
- name: `RasIpv6SrvrStop`
- size: `1757`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b520`
- `0x1800205b0`
- `0x1800521b0`

## callees

- `0x180027ec0`
- `0x18004e540`
- `0x18004f8c4`
- `0x18005015c`
- `0x180052d5c`
- `0x180057220`
- `0x1800586e0`
- `0x18005a844`
- `0x18005aa44`
- `0x18005aa98`
- `0x18005ab2c`
- `0x18005ad18`
- `0x18005adcc`
- `0x18005af78`
- `0x18005d498`
- `0x1800755b8`
- `0x1800771b8`
- `0x1800785b8`
- `0x18007f1c8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180053329`
- `KERNEL32!DeviceIoControl` at `0x180053329`
- `KERNEL32!GetLastError` at `0x180053339`
- `KERNEL32!GetLastError` at `0x180053339`
- `KERNEL32!LeaveCriticalSection` at `0x1800533e9`
- `KERNEL32!LeaveCriticalSection` at `0x1800533e9`
- `KERNEL32!EnterCriticalSection` at `0x180052f5a`
- `KERNEL32!EnterCriticalSection` at `0x180052f5a`
- `ntdll!RtlIpv6AddressToStringA` at `0x180052fd2`
- `ntdll!RtlIpv6AddressToStringA` at `0x180052fd2`
- `rtutils!LogEventA` at `0x180052ffa`
- `rtutils!LogEventA` at `0x180052ffa`

## string_xrefs

- `0x180052eb4`: `RasSrvrStop: GetRoutingDomainConfigData (compartmentId) failed and returned %d`
- `0x1800531fe`: `AddOrRemoveIpv6Prefix completes with 0x%x`
- `0x1800532bb`: `SetIpv6InterfaceProperties completes with 0x%x`

## pseudocode

```c
void __fastcall RasIpv6SrvrStop(struct in6_addr *a1, char a2, int a3)
{
  int v6; // esi
  __int64 NboServerIpv6Address; // rax
  __int64 v8; // rax
  BOOL v9; // r15d
  int v10; // r14d
  int v11; // edi
  unsigned int RoutingDomainConfigData; // eax
  __int64 v13; // rdx
  int v14; // r12d
  int RoutingDomainAddressPool; // ecx
  __int64 v16; // rdi
  struct in6_addr *v17; // rax
  struct _GUID v18; // xmm1
  unsigned int v19; // eax
  __int64 ServerAdapterIPv6IfId; // rax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  DWORD LastError; // eax
  int lpOutBuffer; // [rsp+28h] [rbp-E0h]
  unsigned int v26; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int plpwsSubStrings; // [rsp+50h] [rbp-B8h] BYREF
  struct in6_addr plpwsSubStrings_8; // [rsp+58h] [rbp-B0h] BYREF
  struct in6_addr v29; // [rsp+68h] [rbp-A0h] BYREF
  DWORD BytesReturned[4]; // [rsp+78h] [rbp-90h] BYREF
  struct in6_addr v31; // [rsp+88h] [rbp-80h] BYREF
  _OWORD v32[3]; // [rsp+98h] [rbp-70h] BYREF
  int v33; // [rsp+C8h] [rbp-40h]
  __int128 v34; // [rsp+D8h] [rbp-30h]
  __int128 v35; // [rsp+E8h] [rbp-20h]
  struct in6_addr Addr; // [rsp+F8h] [rbp-10h] BYREF
  int v37; // [rsp+108h] [rbp+0h]
  __int128 OutBuffer; // [rsp+110h] [rbp+8h] BYREF
  int v39; // [rsp+120h] [rbp+18h]
  _OWORD v40[4]; // [rsp+128h] [rbp+20h] BYREF
  __int64 v41; // [rsp+168h] [rbp+60h]
  int v42; // [rsp+170h] [rbp+68h]
  wchar_t v43; // [rsp+174h] [rbp+6Ch]
  __int16 v44; // [rsp+176h] [rbp+6Eh]
  CHAR S[128]; // [rsp+178h] [rbp+70h] BYREF
  int v46; // [rsp+1F8h] [rbp+F0h] BYREF
  _BYTE v47[2044]; // [rsp+1FCh] [rbp+F4h] BYREF

  v40[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  OutBuffer = 0;
  v39 = 0;
  v40[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v42 = *(_DWORD *)L"0}";
  v6 = 0;
  v40[2] = *(_OWORD *)L"000-0000-000000000000}";
  v43 = a00000000000000[38];
  v41 = *(_QWORD *)L"00000}";
  BytesReturned[0] = 0;
  *(_QWORD *)v29.u.Byte = 0;
  v40[3] = *(_OWORD *)L"-000000000000}";
  v44 = 0;
  NboServerIpv6Address = RasRdGetNboServerIpv6Address(v32, a1);
  v34 = *(_OWORD *)NboServerIpv6Address;
  v35 = *(_OWORD *)(NboServerIpv6Address + 16);
  Addr = *(struct in6_addr *)(NboServerIpv6Address + 32);
  v37 = *(_DWORD *)(NboServerIpv6Address + 48);
  v8 = *(_QWORD *)a1->u.Byte - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)a1->u.Byte == *(_QWORD *)&GUID_NULL.Data1 )
    v8 = *(_QWORD *)&a1->u.Word[4] - *(_QWORD *)GUID_NULL.Data4;
  plpwsSubStrings = 1;
  v46 = 0;
  v9 = v8 == 0;
  v10 = a2 & 8;
  v11 = a2 & 0x20;
  memset_0(v47, 0, sizeof(v47));
  if ( !v9 )
  {
    RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &plpwsSubStrings);
    if ( RoutingDomainConfigData && (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v46) = 0;
      FormatRRASErrorString(
        &v46,
        L"RasSrvrStop: GetRoutingDomainConfigData (compartmentId) failed and returned %d",
        RoutingDomainConfigData);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v46);
    }
    MprConvertGuidToString(a1, v13, v40);
  }
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString(&v46, L"RasIpv6SrvrStop - RDID:%ws", v40);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v46);
  }
  v14 = dword_1800CF650;
  if ( !dword_1800CF650 || v9 )
    RasDhcpIpv6Uninitialize();
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( !v10 && !v11 )
  {
    v26 = 0;
    RasRoutingDomainSetConfigParam(a1, 3, 4, &v26);
  }
  if ( (!v14 || v9)
    && a3
    && (Addr.u.Word[0]
     || __PAIR32__(Addr.u.Word[1], 0) != Addr.u.Word[2]
     || __PAIR32__(Addr.u.Word[3], 0) != Addr.u.Word[4]
     || __PAIR32__(Addr.u.Word[5], 0) != Addr.u.Word[6]
     || Addr.u.Word[7]) )
  {
    RtlIpv6AddressToStringA(&Addr, S);
    *(_QWORD *)plpwsSubStrings_8.u.Byte = S;
    LogEventA(2u, 0x4E74u, 1u, (LPSTR *)&plpwsSubStrings_8);
  }
  if ( !v10 )
  {
    if ( !v11 && !a3 )
    {
      v31 = *a1;
      RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v31, 2, &v29);
      LOBYTE(v6) = RoutingDomainAddressPool == 0;
      if ( !RoutingDomainAddressPool
        && (v16 = *(_QWORD *)v29.u.Byte) != 0
        && (v17 = *(struct in6_addr **)(*(_QWORD *)v29.u.Byte + 16LL)) != 0 )
      {
        do
        {
          v18 = (struct _GUID)*a1;
          v31 = v17[1];
          plpwsSubStrings_8 = (struct in6_addr)v18;
          RasSrvrReleaseIpv6Address((struct _GUID *)&plpwsSubStrings_8, &v31);
          v17 = *(struct in6_addr **)(v16 + 16);
        }
        while ( v17 );
      }
      else if ( RoutingDomainAddressPool )
      {
        goto LABEL_38;
      }
      v31 = *a1;
      v19 = RasReleaseRoutingDomainAddressPool(&v31);
      if ( v19 )
      {
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v46) = 0;
          FormatRRASErrorString(&v46, L"RasReleaseRoutingDomainAddressPool failed and returned %d", v19);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v46);
        }
      }
      else
      {
        v6 = 0;
      }
    }
LABEL_38:
    RasSrvrSetProxyArpV6(&Addr, 0, &Addr, plpwsSubStrings, (const struct _GUID *)a1);
    CleanupIpv6ProxyArpSocket((const struct _GUID *)a1);
    v33 = v37;
    v32[0] = v34;
    v32[1] = v35;
    Addr = 0;
    v32[2] = 0;
    RasRdSetNboServerIpv6Address(a1, v32);
    v26 = 0;
    *(_DWORD *)plpwsSubStrings_8.u.Byte = 4;
    RasRoutingDomainGetConfigParam(a1, 5, &plpwsSubStrings_8, &v26);
    if ( !v26 )
      goto LABEL_56;
    v26 = 0;
    *(_DWORD *)plpwsSubStrings_8.u.Byte = 4;
    RasRoutingDomainGetConfigParam(a1, 8, &plpwsSubStrings_8, &v26);
    ServerAdapterIPv6IfId = RasRdGetServerAdapterIPv6IfId(a1);
    plpwsSubStrings_8 = *a1;
    *(_QWORD *)v31.u.Byte = ServerAdapterIPv6IfId;
    if ( (unsigned int)RasGetRoutingDomainAddressPool(&plpwsSubStrings_8, 2, &v29) )
    {
      if ( v6 != 1 )
      {
LABEL_48:
        v23 = SetIpv6InterfaceProperties(v26, 0, 0, 0, lpOutBuffer, 0);
        if ( (_QWORD)xmmword_1800D0740 )
        {
          LOWORD(v46) = 0;
          FormatRRASErrorString(&v46, L"SetIpv6InterfaceProperties completes with 0x%x", v23);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800D0740,
            &v46);
        }
        DWORD2(OutBuffer) = plpwsSubStrings;
        if ( !DeviceIoControl(HelperWanArpv6Handle, 0x90018014, &OutBuffer, 0x14u, &OutBuffer, 0x14u, BytesReturned, 0) )
        {
          LastError = GetLastError();
          if ( (_QWORD)xmmword_1800D0740 )
          {
            LOWORD(v46) = 0;
            FormatRRASErrorString(&v46, L"Error %d unmapping Ipv6 server adapter", LastError);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800D0740,
              &v46);
          }
        }
        if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            *((_QWORD *)&xmmword_1800D0740 + 1),
            L"RasSrvrIpv6AdapterUnMapped");
        *(_DWORD *)plpwsSubStrings_8.u.Byte = 0;
        RasRoutingDomainSetConfigParam(a1, 5, 4, &plpwsSubStrings_8);
        v29 = *a1;
        RasSrvrInterfaceIdDelete(&v29, &v31);
        goto LABEL_56;
      }
    }
    else if ( *(_QWORD *)v29.u.Byte )
    {
      v21 = AddOrRemoveIpv6PrefixForAdvertisement(*(_QWORD *)v29.u.Byte, v26, 1, 0);
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(&v46, L"AddOrRemoveIpv6Prefix completes with 0x%x", v21);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v46);
      }
    }
    v29 = *a1;
    v22 = RasReleaseRoutingDomainAddressPool(&v29);
    if ( v22 && (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, L"RasReleaseRoutingDomainAddressPool failed and returned %d", v22);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v46);
    }
    goto LABEL_48;
  }
LABEL_56:
  LeaveCriticalSection(&RasSrvrCriticalSection);
  if ( !v14 || v9 )
    WriteDialinInterfaceIndexIntoRegistry(0, 0);
}

```

## disassembly

```asm
0x180052d5c  mov     rax, rsp
0x180052d5f  mov     [rax+10h], rbx
0x180052d63  mov     [rax+18h], rsi
0x180052d67  mov     [rax+20h], rdi
0x180052d6b  push    rbp
0x180052d6c  push    r12
0x180052d6e  push    r13
0x180052d70  push    r14
0x180052d72  push    r15
0x180052d74  lea     rbp, [rax-928h]
0x180052d7b  sub     rsp, 0A00h
0x180052d82  mov     rax, cs:__security_cookie
0x180052d89  xor     rax, rsp
0x180052d8c  mov     [rbp+920h+var_30], rax
0x180052d93  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180052d9a  xorps   xmm0, xmm0
0x180052d9d  xor     eax, eax
0x180052d9f  movaps  [rbp+920h+var_8F0], xmm1
0x180052da3  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180052daa  xor     r12d, r12d
0x180052dad  movups  [rbp+920h+OutBuffer], xmm0
0x180052db1  mov     edi, edx
0x180052db3  mov     [rbp+920h+var_908], eax
0x180052db6  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180052dbd  mov     rbx, rcx
0x180052dc0  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x180052dc6  mov     rdx, rcx
0x180052dc9  movaps  [rbp+920h+var_900], xmm0
0x180052dcd  lea     rcx, [rbp+920h+var_990]
0x180052dd1  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180052dd8  mov     r13d, r8d
0x180052ddb  mov     [rbp+920h+var_8B8], eax
0x180052dde  mov     esi, r12d
0x180052de1  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x180052de8  movaps  [rbp+920h+var_8E0], xmm0
0x180052dec  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x180052df4  mov     [rbp+920h+var_8B4], ax
0x180052df8  xor     eax, eax
0x180052dfa  movsd   [rbp+920h+var_8C0], xmm0
0x180052dff  mov     [rsp+0A20h+BytesReturned], r12d
0x180052e04  mov     qword ptr [rsp+0A20h+var_9C8+8], r12
0x180052e09  movaps  [rbp+920h+var_8D0], xmm1
0x180052e0d  mov     [rbp+920h+var_8B2], ax
0x180052e11  call    RasRdGetNboServerIpv6Address
0x180052e16  movups  xmm0, xmmword ptr [rax]
0x180052e19  movups  [rbp+920h+var_950], xmm0
0x180052e1d  movups  xmm1, xmmword ptr [rax+10h]
0x180052e21  movups  [rbp+920h+var_940], xmm1
0x180052e25  movups  xmm0, xmmword ptr [rax+20h]
0x180052e29  movups  xmmword ptr [rbp+920h+Addr.u], xmm0
0x180052e2d  mov     eax, [rax+30h]
0x180052e30  mov     [rbp+920h+var_920], eax
0x180052e33  mov     rax, [rbx]
0x180052e36  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180052e3d  jnz     short loc_180052E4A
0x180052e3f  mov     rax, [rbx+8]
0x180052e43  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180052e4a  test    rax, rax
0x180052e4d  mov     dword ptr [rsp+0A20h+plpwsSubStrings], 1
0x180052e55  mov     r14d, edi
0x180052e58  mov     [rbp+920h+var_830], r12d
0x180052e5f  mov     r15d, r12d
0x180052e62  lea     rcx, [rbp+920h+var_82C]; void *
0x180052e69  setz    r15b
0x180052e6d  mov     r8d, 7FCh; Size
0x180052e73  xor     edx, edx; Val
0x180052e75  and     r14d, 8
0x180052e79  and     edi, 20h
0x180052e7c  call    memset_0
0x180052e81  test    r15d, r15d
0x180052e84  jnz     short loc_180052EF4
0x180052e86  lea     r9, [rsp+0A20h+plpwsSubStrings]
0x180052e8b  mov     edx, 100h
0x180052e90  lea     r8d, [r15+4]
0x180052e94  mov     rcx, rbx
0x180052e97  call    GetRoutingDomainConfigData
0x180052e9c  test    eax, eax
0x180052e9e  jz      short loc_180052EE8
0x180052ea0  cmp     qword ptr cs:xmmword_1800D0740, r12
0x180052ea7  jz      short loc_180052EE8
0x180052ea9  mov     r8d, eax
0x180052eac  mov     word ptr [rbp+920h+var_830], r12w
0x180052eb4  lea     rdx, aRassrvrstopGet; "RasSrvrStop: GetRoutingDomainConfigData"...
0x180052ebb  lea     rcx, [rbp+920h+var_830]
0x180052ec2  call    FormatRRASErrorString
0x180052ec7  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180052ece  lea     r8, [rbp+920h+var_830]
0x180052ed5  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180052edc  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180052ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ee8  lea     r8, [rbp+920h+var_900]
0x180052eec  mov     rcx, rbx
0x180052eef  call    MprConvertGuidToString
0x180052ef4  cmp     qword ptr cs:xmmword_1800D0740, r12
0x180052efb  jz      short loc_180052F3D
0x180052efd  lea     r8, [rbp+920h+var_900]
0x180052f01  mov     word ptr [rbp+920h+var_830], r12w
0x180052f09  lea     rdx, aRasipv6srvrsto; "RasIpv6SrvrStop - RDID:%ws"
0x180052f10  lea     rcx, [rbp+920h+var_830]
0x180052f17  call    FormatRRASErrorString
0x180052f1c  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180052f23  lea     r8, [rbp+920h+var_830]
0x180052f2a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180052f31  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180052f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f3d  mov     r12d, cs:dword_1800CF650
0x180052f44  test    r12d, r12d
0x180052f47  jz      short loc_180052F4E
0x180052f49  test    r15d, r15d
0x180052f4c  jz      short loc_180052F53
0x180052f4e  call    ?RasDhcpIpv6Uninitialize@@YAXXZ; RasDhcpIpv6Uninitialize(void)
0x180052f53  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180052f5a  call    cs:__imp_EnterCriticalSection
0x180052f61  nop     dword ptr [rax+rax+00h]
0x180052f66  xor     eax, eax
0x180052f68  test    r14d, r14d
0x180052f6b  jnz     short loc_180052F8B
0x180052f6d  test    edi, edi
0x180052f6f  jnz     short loc_180052F8B
0x180052f71  lea     r9, [rsp+0A20h+var_9E0]
0x180052f76  mov     [rsp+0A20h+var_9E0], eax
0x180052f7a  lea     edx, [rax+3]
0x180052f7d  mov     rcx, rbx
0x180052f80  lea     r8d, [rax+4]
0x180052f84  call    RasRoutingDomainSetConfigParam
0x180052f89  xor     eax, eax
0x180052f8b  test    r12d, r12d
0x180052f8e  jz      short loc_180052F95
0x180052f90  test    r15d, r15d
0x180052f93  jz      short loc_180053006
0x180052f95  test    r13d, r13d
0x180052f98  jz      short loc_180053006
0x180052f9a  cmp     word ptr [rbp+920h+Addr.u], ax
0x180052f9e  jnz     short loc_180052FCA
0x180052fa0  cmp     word ptr [rbp+920h+Addr.u+2], ax
0x180052fa4  jnz     short loc_180052FCA
0x180052fa6  cmp     word ptr [rbp+920h+Addr.u+4], ax
0x180052faa  jnz     short loc_180052FCA
0x180052fac  cmp     word ptr [rbp+920h+Addr.u+6], ax
0x180052fb0  jnz     short loc_180052FCA
0x180052fb2  cmp     word ptr [rbp+920h+Addr.u+8], ax
0x180052fb6  jnz     short loc_180052FCA
0x180052fb8  cmp     word ptr [rbp+920h+Addr.u+0Ah], ax
0x180052fbc  jnz     short loc_180052FCA
0x180052fbe  cmp     word ptr [rbp+920h+Addr.u+0Ch], ax
0x180052fc2  jnz     short loc_180052FCA
0x180052fc4  cmp     word ptr [rbp+920h+Addr.u+0Eh], ax
0x180052fc8  jz      short loc_180053006
0x180052fca  lea     rdx, [rbp+920h+S]; S
0x180052fce  lea     rcx, [rbp+920h+Addr]; Addr
0x180052fd2  call    cs:__imp_RtlIpv6AddressToStringA
0x180052fd9  nop     dword ptr [rax+rax+00h]
0x180052fde  mov     ecx, 2; wEventType
0x180052fe3  lea     rax, [rbp+920h+S]
0x180052fe7  lea     r9, [rsp+0A20h+plpwsSubStrings+8]; plpwsSubStrings
0x180052fec  mov     [rsp+0A20h+plpwsSubStrings+8], rax
0x180052ff1  mov     edx, 4E74h; dwMessageId
0x180052ff6  lea     r8d, [rcx-1]; cNumberOfSubStrings
0x180052ffa  call    cs:__imp_LogEventA
0x180053001  nop     dword ptr [rax+rax+00h]
0x180053006  test    r14d, r14d
0x180053009  jnz     loc_1800533E2
0x18005300f  xor     r14d, r14d
0x180053012  test    edi, edi
0x180053014  jnz     loc_1800530FC
0x18005301a  test    r13d, r13d
0x18005301d  jnz     loc_1800530FC
0x180053023  movaps  xmm0, xmmword ptr [rbx]
0x180053026  lea     r8, [rsp+0A20h+var_9C8+8]
0x18005302b  lea     edx, [rdi+2]
0x18005302e  movdqa  xmmword ptr [rbp+920h+var_9A0.u], xmm0
0x180053033  lea     rcx, [rbp+920h+var_9A0]
0x180053037  call    RasGetRoutingDomainAddressPool
0x18005303c  test    eax, eax
0x18005303e  mov     ecx, eax
0x180053040  setz    sil
0x180053044  test    eax, eax
0x180053046  jnz     short loc_180053096
0x180053048  mov     rdi, qword ptr [rsp+0A20h+var_9C8+8]
0x18005304d  test    rdi, rdi
0x180053050  jz      short loc_180053096
0x180053052  mov     rax, [rdi+10h]
0x180053056  test    rax, rax
0x180053059  jz      short loc_180053096
0x18005305b  movups  xmm0, xmmword ptr [rax+10h]
0x18005305f  lea     rdx, [rbp+920h+var_9A0]; Addr
0x180053063  mov     r9, [rax+28h]
0x180053067  movaps  xmm1, xmmword ptr [rbx]
0x18005306a  lea     rcx, [rsp+0A20h+plpwsSubStrings+8]; struct _GUID *
0x18005306f  mov     r8, [rax+20h]
0x180053073  movdqu  xmmword ptr [rbp+920h+var_9A0.u], xmm0
0x180053078  mov     dword ptr [rsp+0A20h+lpOutBuffer], 1
0x180053080  movdqa  xmmword ptr [rsp+0A20h+plpwsSubStrings+8], xmm1
0x180053086  call    RasSrvrReleaseIpv6Address
0x18005308b  mov     rax, [rdi+10h]
0x18005308f  test    rax, rax
0x180053092  jnz     short loc_18005305B
0x180053094  jmp     short loc_18005309A
0x180053096  test    ecx, ecx
0x180053098  jnz     short loc_1800530FC
0x18005309a  movaps  xmm0, xmmword ptr [rbx]
0x18005309d  lea     rcx, [rbp+920h+var_9A0]
0x1800530a1  movdqa  xmmword ptr [rbp+920h+var_9A0.u], xmm0
0x1800530a6  call    RasReleaseRoutingDomainAddressPool
0x1800530ab  test    eax, eax
0x1800530ad  jz      short loc_1800530F9
0x1800530af  cmp     qword ptr cs:xmmword_1800D0740, r14
0x1800530b6  jz      short loc_1800530FC
0x1800530b8  mov     r8d, eax
0x1800530bb  mov     word ptr [rbp+920h+var_830], r14w
0x1800530c3  lea     rdx, aRasreleaserout_0; "RasReleaseRoutingDomainAddressPool fail"...
0x1800530ca  lea     rcx, [rbp+920h+var_830]
0x1800530d1  call    FormatRRASErrorString
0x1800530d6  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800530dd  lea     r8, [rbp+920h+var_830]
0x1800530e4  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800530eb  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800530f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800530f7  jmp     short loc_1800530FC
0x1800530f9  mov     esi, r14d
0x1800530fc  mov     r9d, dword ptr [rsp+0A20h+plpwsSubStrings]; unsigned int
0x180053101  lea     r8, [rbp+920h+Addr]; struct in6_addr *
0x180053105  xor     edx, edx; int
0x180053107  mov     [rsp+0A20h+lpOutBuffer], rbx; struct _GUID *
0x18005310c  lea     rcx, [rbp+920h+Addr]; Addr
0x180053110  call    ?RasSrvrSetProxyArpV6@@YAXPEBUin6_addr@@H0IPEBU_GUID@@@Z; RasSrvrSetProxyArpV6(in6_addr const *,int,in6_addr const *,uint,_GUID const *)
0x180053115  mov     rcx, rbx; struct _GUID *
0x180053118  call    ?CleanupIpv6ProxyArpSocket@@YAXPEBU_GUID@@@Z; CleanupIpv6ProxyArpSocket(_GUID const *)
0x18005311d  movups  xmm0, [rbp+920h+var_950]
0x180053121  mov     eax, [rbp+920h+var_920]
0x180053124  lea     rdx, [rbp+920h+var_990]
0x180053128  movups  xmm1, [rbp+920h+var_940]
0x18005312c  mov     rcx, rbx
0x18005312f  mov     [rbp+920h+var_960], eax
0x180053132  xorps   xmm2, xmm2
0x180053135  movaps  [rbp+920h+var_990], xmm0
0x180053139  movaps  [rbp+920h+var_980], xmm1
0x18005313d  movups  xmmword ptr [rbp+920h+Addr.u], xmm2
0x180053141  movaps  [rbp+920h+var_970], xmm2
0x180053145  call    RasRdSetNboServerIpv6Address
0x18005314a  mov     edi, 4
0x18005314f  mov     [rsp+0A20h+var_9E0], r14d
0x180053154  lea     r9, [rsp+0A20h+var_9E0]
0x180053159  mov     dword ptr [rsp+0A20h+plpwsSubStrings+8], edi
0x18005315d  lea     r8, [rsp+0A20h+plpwsSubStrings+8]
0x180053162  mov     rcx, rbx
0x180053165  lea     r13d, [rdi+1]
0x180053169  mov     edx, r13d
0x18005316c  call    RasRoutingDomainGetConfigParam
0x180053171  cmp     [rsp+0A20h+var_9E0], r14d
0x180053176  jz      loc_1800533E2
0x18005317c  lea     r9, [rsp+0A20h+var_9E0]
0x180053181  mov     [rsp+0A20h+var_9E0], r14d
0x180053186  lea     r8, [rsp+0A20h+plpwsSubStrings+8]
0x18005318b  mov     dword ptr [rsp+0A20h+plpwsSubStrings+8], edi
0x18005318f  lea     edx, [rdi+4]
0x180053192  mov     rcx, rbx
0x180053195  call    RasRoutingDomainGetConfigParam
0x18005319a  mov     rcx, rbx
0x18005319d  call    RasRdGetServerAdapterIPv6IfId
0x1800531a2  movaps  xmm0, xmmword ptr [rbx]
0x1800531a5  lea     r8, [rsp+0A20h+var_9C8+8]
0x1800531aa  lea     edx, [rdi-2]
0x1800531ad  movdqa  xmmword ptr [rsp+0A20h+plpwsSubStrings+8], xmm0
0x1800531b3  lea     rcx, [rsp+0A20h+plpwsSubStrings+8]
0x1800531b8  mov     qword ptr [rbp+920h+var_9A0.u], rax
0x1800531bc  call    RasGetRoutingDomainAddressPool
0x1800531c1  test    eax, eax
0x1800531c3  jz      short loc_1800531D0
0x1800531c5  cmp     esi, 1
0x1800531c8  jnz     loc_180053291
0x1800531ce  jmp     short loc_180053232
0x1800531d0  mov     rcx, qword ptr [rsp+0A20h+var_9C8+8]
0x1800531d5  test    rcx, rcx
0x1800531d8  jz      short loc_180053232
0x1800531da  mov     edx, [rsp+0A20h+var_9E0]
0x1800531de  xor     r9d, r9d
0x1800531e1  lea     r8d, [r9+1]
0x1800531e5  call    AddOrRemoveIpv6PrefixForAdvertisement
0x1800531ea  cmp     qword ptr cs:xmmword_1800D0740, r14
0x1800531f1  jz      short loc_180053232
0x1800531f3  mov     r8d, eax
0x1800531f6  mov     word ptr [rbp+920h+var_830], r14w
0x1800531fe  lea     rdx, aAddorremoveipv_0; "AddOrRemoveIpv6Prefix completes with 0x"...
0x180053205  lea     rcx, [rbp+920h+var_830]
0x18005320c  call    FormatRRASErrorString
0x180053211  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180053218  lea     r8, [rbp+920h+var_830]
0x18005321f  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053226  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005322d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053232  movaps  xmm0, xmmword ptr [rbx]
0x180053235  lea     rcx, [rsp+0A20h+var_9C8+8]
0x18005323a  movdqa  xmmword ptr [rsp+0A20h+var_9C8+8], xmm0
0x180053240  call    RasReleaseRoutingDomainAddressPool
0x180053245  test    eax, eax
0x180053247  jz      short loc_180053291
0x180053249  cmp     qword ptr cs:xmmword_1800D0740, r14
0x180053250  jz      short loc_180053291
0x180053252  mov     r8d, eax
  ... truncated ...
```
