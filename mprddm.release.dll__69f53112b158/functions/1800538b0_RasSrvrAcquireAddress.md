# RasSrvrAcquireAddress

- ea: `0x1800538b0`
- end: `0x1800540e3`
- name: `RasSrvrAcquireAddress`
- size: `2099`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x180027efc`
- `0x180050d54`
- `0x1800538b0`
- `0x1800597d4`
- `0x18005a844`
- `0x18005aa10`
- `0x18005ad18`
- `0x18005e620`
- `0x180060b00`
- `0x1800755b8`
- `0x1800771b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180053d89`
- `msvcrt!_wcsdup` at `0x180053e45`
- `msvcrt!_wcsdup` at `0x180053d89`
- `msvcrt!_wcsdup` at `0x180053e45`
- `msvcrt!free` at `0x180054083`
- `msvcrt!free` at `0x180054093`
- `msvcrt!free` at `0x180054083`
- `msvcrt!free` at `0x180054093`
- `KERNEL32!GetLastError` at `0x180053eca`
- `KERNEL32!GetLastError` at `0x180053eca`
- `KERNEL32!LeaveCriticalSection` at `0x1800540a6`
- `KERNEL32!LeaveCriticalSection` at `0x1800540a6`
- `KERNEL32!LocalAlloc` at `0x180053eb4`
- `KERNEL32!LocalAlloc` at `0x180053eb4`
- `KERNEL32!EnterCriticalSection` at `0x180053a24`
- `KERNEL32!EnterCriticalSection` at `0x180053a24`

## string_xrefs

- `0x1800539d9`: `RasSrvrAcquireAddress for RD: %ws(hPort: 0x%x, IP address: 0x%x, UserName: %ws, PortName: %ws)`
- `0x180053a56`: `RasSrvrAcquireAddress: IsVpnEnabledForRoutingDomain failed with error %d.`
- `0x180053ac1`: `RasSrvrAcquireAddress: rasSrvrGetAddressForServerAdapter failed with error %d.`
- `0x180053af1`: `RasSrvrAcquireAddress: rasSrvrAcquiring Address... nboIpAddr : %x%x`
- `0x180053b63`: `RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:1: failed with error %d.`
- `0x180053bde`: `RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:2: failed with error %d.`
- `0x180053c58`: `RasSrvrAcquireAddress: MprAdminGetIpAddressForUser(%ws, %ws, 0x%x) failed and returned %d`
- `0x180053dfc`: `RasSrvrAcquireAddress: 3rd party DLL wants to hand out bad address 0x%x`
- `0x180053ccb`: `RasSrvrAcquireAddress: 3rd party DLL wants to hand out address 0x%x`
- `0x180053d71`: `RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:3: failed with error %d.`
- `0x180053db7`: `RasSrvrAcquireAddress: _strdup failed and returned %d`
- `0x180053e6e`: `RasSrvrAcquireAddress: _strdup failed and returned %d`
- `0x180053eea`: `RasSrvrAcquireAddress: LocalAlloc failed and returned %d`
- `0x180053fdc`: `RasSrvrAcquireAddress: RasReleaseRoutingDomainAddressPool failed to release lock and returned %d`

## pseudocode

```c
__int64 __fastcall RasSrvrAcquireAddress(
        struct _GUID *a1,
        __int64 a2,
        u_long a3,
        u_long *a4,
        wchar_t *a5,
        wchar_t *a6,
        int a7)
{
  u_long v10; // r12d
  unsigned int RoutingDomainAddressPool; // r15d
  int NboServerIpv4Address; // r14d
  bool v13; // zf
  __int64 v14; // rax
  BOOL v15; // ebx
  __int64 v16; // rdx
  unsigned int AddressForServerAdapter; // ebx
  wchar_t *v18; // rax
  const wchar_t *v19; // rdx
  wchar_t *v20; // r13
  struct _GUID v21; // xmm0
  u_long v22; // edi
  wchar_t *v23; // r14
  wchar_t *v24; // rdi
  struct _GUID v25; // xmm0
  _QWORD *v26; // r14
  BOOL v27; // r8d
  bool v28; // cf
  __int64 v29; // rcx
  u_long *v30; // rax
  __int64 v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+28h] [rbp-D8h]
  char v34[8]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String; // [rsp+48h] [rbp-B8h]
  wchar_t *v36; // [rsp+50h] [rbp-B0h]
  wchar_t *v37; // [rsp+58h] [rbp-A8h]
  u_long netlong; // [rsp+60h] [rbp-A0h] BYREF
  u_long v39; // [rsp+64h] [rbp-9Ch] BYREF
  int v40; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+6Ch] [rbp-94h] BYREF
  int v42[4]; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v43; // [rsp+80h] [rbp-80h] BYREF
  void *Block; // [rsp+90h] [rbp-70h]
  __int64 v45; // [rsp+98h] [rbp-68h] BYREF
  u_long *v46; // [rsp+A0h] [rbp-60h]
  _OWORD v47[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v48; // [rsp+F0h] [rbp-10h]
  int v49; // [rsp+F8h] [rbp-8h]
  wchar_t v50; // [rsp+FCh] [rbp-4h]
  __int16 v51; // [rsp+FEh] [rbp-2h]
  int v52; // [rsp+100h] [rbp+0h] BYREF
  char v53[2044]; // [rsp+104h] [rbp+4h] BYREF

  String = a5;
  v10 = 0;
  v37 = a6;
  RoutingDomainAddressPool = 0;
  NboServerIpv4Address = 0;
  v49 = *(_DWORD *)L"0}";
  v50 = a00000000000000[38];
  v47[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v51 = 0;
  v14 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  v13 = *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_NULL.Data1;
  v47[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v47[2] = *(_OWORD *)L"000-0000-000000000000}";
  v46 = a4;
  v41 = 0;
  v39 = 0;
  v42[0] = 0;
  v40 = 0;
  Block = 0;
  v45 = 0;
  v47[3] = *(_OWORD *)L"-000000000000}";
  v48 = *(_QWORD *)L"00000}";
  v34[0] = 0;
  if ( v13 )
    v14 = *(_QWORD *)a1->Data4 - *(_QWORD *)GUID_NULL.Data4;
  v52 = 0;
  v15 = v14 == 0;
  memset_0(v53, 0, sizeof(v53));
  if ( !v15 )
    MprConvertGuidToString(a1, v16, v47);
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v52) = 0;
    FormatRRASErrorString(
      &v52,
      L"RasSrvrAcquireAddress for RD: %ws(hPort: 0x%x, IP address: 0x%x, UserName: %ws, PortName: %ws)",
      v47,
      a2,
      a3,
      String,
      v37);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v52);
  }
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( v15 )
    goto LABEL_14;
  AddressForServerAdapter = IsVpnEnabledForRoutingDomain(a1, v34);
  LODWORD(v18) = 0;
  if ( AddressForServerAdapter )
  {
    if ( (_QWORD)xmmword_1800D0740 )
    {
      v19 = L"RasSrvrAcquireAddress: IsVpnEnabledForRoutingDomain failed with error %d.";
LABEL_11:
      LOWORD(v52) = 0;
      FormatRRASErrorString(&v52, v19, AddressForServerAdapter);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v52);
      v20 = 0;
LABEL_12:
      LODWORD(v18) = 0;
      goto LABEL_74;
    }
    goto LABEL_69;
  }
  if ( v34[0] )
  {
LABEL_14:
    v43 = *a1;
    AddressForServerAdapter = rasSrvrGetAddressForServerAdapter(&v43);
    LODWORD(v18) = 0;
    if ( AddressForServerAdapter )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        v19 = L"RasSrvrAcquireAddress: rasSrvrGetAddressForServerAdapter failed with error %d.";
        goto LABEL_11;
      }
LABEL_69:
      v20 = 0;
      goto LABEL_74;
    }
    NboServerIpv4Address = RasRdGetNboServerIpv4Address(a1);
    if ( a3 == NboServerIpv4Address )
      a3 = 0;
  }
  netlong = a3;
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LOWORD(v52) = 0;
    FormatRRASErrorString(&v52, L"RasSrvrAcquireAddress: rasSrvrAcquiring Address... nboIpAddr : %x%x", a3);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v52);
  }
  v43 = *a1;
  AddressForServerAdapter = rasSrvrAcquireAddressEx(
                              (unsigned int)&v43,
                              a2,
                              (unsigned int)&netlong,
                              (unsigned int)&v41,
                              (__int64)&v40);
  LODWORD(v18) = 0;
  if ( AddressForServerAdapter )
  {
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v52) = 0;
      FormatRRASErrorString(
        &v52,
        L"RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:1: failed with error %d.",
        AddressForServerAdapter);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v52);
      LODWORD(v18) = 0;
    }
    if ( !netlong )
    {
      v20 = 0;
      goto LABEL_74;
    }
    v21 = *a1;
    netlong = 0;
    v43 = v21;
    AddressForServerAdapter = rasSrvrAcquireAddressEx(
                                (unsigned int)&v43,
                                a2,
                                (unsigned int)&netlong,
                                (unsigned int)&v41,
                                (__int64)&v40);
    LODWORD(v18) = 0;
    if ( AddressForServerAdapter )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        v19 = L"RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:2: failed with error %d.";
        goto LABEL_11;
      }
      goto LABEL_69;
    }
  }
  v22 = netlong;
  v10 = netlong;
  if ( pfnMprAdminGetIpAddressForUser && (!a7 || dwMprAdminGetIpAddressAdminCallbackVersion != 1) )
  {
    v39 = netlong;
    AddressForServerAdapter = pfnMprAdminGetIpAddressForUser(String, v37, &v39, v42);
    LODWORD(v18) = 0;
    if ( AddressForServerAdapter )
    {
      v23 = v37;
      v24 = String;
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v52) = 0;
        LODWORD(v33) = AddressForServerAdapter;
        LODWORD(v32) = v39;
        FormatRRASErrorString(
          &v52,
          L"RasSrvrAcquireAddress: MprAdminGetIpAddressForUser(%ws, %ws, 0x%x) failed and returned %d",
          String,
          v37,
          v32,
          v33);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v52);
        LODWORD(v18) = 0;
      }
      v20 = 0;
      goto LABEL_76;
    }
    if ( !v39 || NboServerIpv4Address == v39 )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v52) = 0;
        FormatRRASErrorString(&v52, L"RasSrvrAcquireAddress: 3rd party DLL wants to hand out bad address 0x%x");
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v52);
        LODWORD(v18) = 0;
      }
      AddressForServerAdapter = 1168;
      v20 = 0;
      goto LABEL_74;
    }
    if ( v22 != v39 )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v52) = 0;
        FormatRRASErrorString(&v52, L"RasSrvrAcquireAddress: 3rd party DLL wants to hand out address 0x%x");
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v52);
      }
      if ( dword_1800D08DC )
      {
        RasDhcpReleaseAddress(v22);
      }
      else
      {
        v43 = *a1;
        RasStatReleaseAddress(&v43, v22);
      }
      v25 = *a1;
      v10 = 0;
      v40 = 0;
      netlong = v39;
      v43 = v25;
      AddressForServerAdapter = rasSrvrAcquireAddressEx(
                                  (unsigned int)&v43,
                                  a2,
                                  (unsigned int)&netlong,
                                  (unsigned int)&v41,
                                  (__int64)&v40);
      LODWORD(v18) = 0;
      if ( AddressForServerAdapter )
      {
        if ( (_QWORD)xmmword_1800D0740 )
        {
          v19 = L"RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:3: failed with error %d.";
          goto LABEL_11;
        }
        goto LABEL_69;
      }
      v22 = netlong;
      v10 = netlong;
    }
  }
  v18 = _wcsdup(String);
  v36 = v18;
  if ( !v18 )
  {
    AddressForServerAdapter = 14;
    if ( !(_QWORD)xmmword_1800D0740 )
    {
      v20 = v36;
      goto LABEL_74;
    }
    LOWORD(v52) = 0;
    FormatRRASErrorString(&v52, L"RasSrvrAcquireAddress: _strdup failed and returned %d");
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v52);
    v20 = v36;
    goto LABEL_12;
  }
  v23 = v37;
  v18 = _wcsdup(v37);
  Block = v18;
  if ( !v18 )
  {
    AddressForServerAdapter = 14;
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v52) = 0;
      FormatRRASErrorString(&v52, L"RasSrvrAcquireAddress: _strdup failed and returned %d");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v52);
      v20 = v36;
      LODWORD(v18) = 0;
    }
    else
    {
      v20 = v36;
    }
    goto LABEL_75;
  }
  v26 = LocalAlloc(0x40u, 0x30u);
  if ( v26 )
  {
    v26[1] = a2;
    v20 = v36;
    v27 = v42[0] != 0;
    v28 = v40 != 0;
    v26[3] = v36;
    v26[4] = Block;
    *((_DWORD *)v26 + 10) = v27 | (v28 ? 4 : 0);
    v43 = *a1;
    RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&v43, 1, &v45);
    LODWORD(v18) = 0;
    if ( !RoutingDomainAddressPool )
    {
      v29 = v45;
      if ( v45 )
      {
        *v26 = *(_QWORD *)(v45 + 24);
        v30 = v46;
        *(_QWORD *)(v29 + 24) = v26;
        *v30 = v22;
        *((_DWORD *)v26 + 4) = v22;
      }
      v43 = *a1;
      RoutingDomainAddressPool = RasReleaseRoutingDomainAddressPool(&v43);
      LODWORD(v18) = 0;
      if ( RoutingDomainAddressPool && (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v52) = 0;
        FormatRRASErrorString(
          &v52,
          L"RasSrvrAcquireAddress: RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
          RoutingDomainAddressPool);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v52);
        LODWORD(v18) = 0;
      }
    }
  }
  else
  {
    AddressForServerAdapter = GetLastError();
    LODWORD(v18) = 0;
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v52) = 0;
      FormatRRASErrorString(&v52, L"RasSrvrAcquireAddress: LocalAlloc failed and returned %d", AddressForServerAdapter);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v52);
      LODWORD(v18) = 0;
    }
    v20 = v36;
  }
  if ( AddressForServerAdapter || RoutingDomainAddressPool )
  {
LABEL_74:
    v23 = v37;
LABEL_75:
    v24 = String;
LABEL_76:
    if ( v42[0] != (_DWORD)v18 )
    {
      ((void (__fastcall *)(wchar_t *, wchar_t *, u_long *))pfnMprAdminReleaseIpAddress)(v24, v23, &v39);
      LODWORD(v18) = 0;
    }
    if ( v10 )
    {
      if ( dword_1800D08DC == (_DWORD)v18 )
      {
        v43 = *a1;
        RasStatReleaseAddress(&v43, v10);
      }
      else
      {
        RasDhcpReleaseAddress(v10);
      }
    }
    free(v20);
    free(Block);
  }
  LeaveCriticalSection(&RasSrvrCriticalSection);
  if ( !AddressForServerAdapter && RoutingDomainAddressPool )
    return RoutingDomainAddressPool;
  return AddressForServerAdapter;
}

```

## disassembly

```asm
0x1800538b0  push    rbp
0x1800538b2  push    rbx
0x1800538b3  push    rsi
0x1800538b4  push    rdi
0x1800538b5  push    r12
0x1800538b7  push    r13
0x1800538b9  push    r14
0x1800538bb  push    r15
0x1800538bd  lea     rbp, [rsp-818h]
0x1800538c5  sub     rsp, 918h
0x1800538cc  mov     rax, cs:__security_cookie
0x1800538d3  xor     rax, rsp
0x1800538d6  mov     [rbp+850h+var_50], rax
0x1800538dd  mov     rax, [rbp+850h+arg_20]
0x1800538e4  mov     rsi, rcx
0x1800538e7  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800538ee  xor     ecx, ecx
0x1800538f0  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x1800538f7  mov     edi, r8d
0x1800538fa  mov     [rsp+950h+String], rax
0x1800538ff  mov     r13, rdx
0x180053902  mov     rax, [rbp+850h+arg_28]
0x180053909  mov     r12d, ecx
0x18005390c  mov     [rsp+950h+var_8F8], rax
0x180053911  mov     r15d, ecx
0x180053914  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x18005391a  mov     r14d, ecx
0x18005391d  mov     [rbp+850h+var_858], eax
0x180053920  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x180053927  mov     [rbp+850h+var_854], ax
0x18005392b  xor     eax, eax
0x18005392d  movaps  [rbp+850h+var_8A0], xmm0
0x180053931  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180053938  mov     [rbp+850h+var_852], ax
0x18005393c  mov     rax, [rsi]
0x18005393f  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180053946  movaps  [rbp+850h+var_890], xmm1
0x18005394a  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180053951  movaps  [rbp+850h+var_880], xmm0
0x180053955  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x18005395d  mov     [rbp+850h+var_8B0], r9
0x180053961  mov     [rsp+950h+var_8E4], ecx
0x180053965  mov     [rsp+950h+var_8EC], ecx
0x180053969  mov     [rsp+950h+var_8E0], ecx
0x18005396d  mov     [rsp+950h+var_8E8], ecx
0x180053971  mov     [rbp+850h+Block], rcx
0x180053975  mov     [rbp+850h+var_8B8], rcx
0x180053979  movaps  [rbp+850h+var_870], xmm1
0x18005397d  movsd   [rbp+850h+var_860], xmm0
0x180053982  mov     [rsp+950h+var_910], cl
0x180053986  jnz     short loc_180053993
0x180053988  mov     rax, [rsi+8]
0x18005398c  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180053993  mov     ebx, ecx
0x180053995  mov     [rbp+850h+var_850], ecx
0x180053998  test    rax, rax
0x18005399b  lea     rcx, [rbp+850h+var_84C]; void *
0x18005399f  mov     r8d, 7FCh; Size
0x1800539a5  setz    bl
0x1800539a8  xor     edx, edx; Val
0x1800539aa  call    memset_0
0x1800539af  xor     eax, eax
0x1800539b1  test    ebx, ebx
0x1800539b3  jnz     short loc_1800539C3
0x1800539b5  lea     r8, [rbp+850h+var_8A0]
0x1800539b9  mov     rcx, rsi
0x1800539bc  call    MprConvertGuidToString
0x1800539c1  xor     eax, eax
0x1800539c3  cmp     qword ptr cs:xmmword_1800D0740, rax
0x1800539ca  jz      short loc_180053A1D
0x1800539cc  mov     word ptr [rbp+850h+var_850], ax
0x1800539d0  lea     r8, [rbp+850h+var_8A0]
0x1800539d4  mov     rax, [rsp+950h+var_8F8]
0x1800539d9  lea     rdx, aRassrvracquire_6; "RasSrvrAcquireAddress for RD: %ws(hPort"...
0x1800539e0  mov     [rsp+950h+var_920], rax
0x1800539e5  lea     rcx, [rbp+850h+var_850]
0x1800539e9  mov     rax, [rsp+950h+String]
0x1800539ee  mov     r9, r13
0x1800539f1  mov     [rsp+950h+var_928], rax
0x1800539f6  mov     dword ptr [rsp+950h+var_930], edi
0x1800539fa  call    FormatRRASErrorString
0x1800539ff  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180053a06  lea     r8, [rbp+850h+var_850]
0x180053a0a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053a11  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a1d  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180053a24  call    cs:__imp_EnterCriticalSection
0x180053a2b  nop     dword ptr [rax+rax+00h]
0x180053a30  test    ebx, ebx
0x180053a32  jnz     short loc_180053A9B
0x180053a34  lea     rdx, [rsp+950h+var_910]
0x180053a39  mov     rcx, rsi
0x180053a3c  call    IsVpnEnabledForRoutingDomain
0x180053a41  mov     ebx, eax
0x180053a43  xor     eax, eax
0x180053a45  test    ebx, ebx
0x180053a47  jz      short loc_180053A95
0x180053a49  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180053a50  jz      loc_180054011
0x180053a56  lea     rdx, aRassrvracquire_9; "RasSrvrAcquireAddress: IsVpnEnabledForR"...
0x180053a5d  mov     r8d, ebx
0x180053a60  mov     word ptr [rbp+850h+var_850], ax
0x180053a64  lea     rcx, [rbp+850h+var_850]
0x180053a68  call    FormatRRASErrorString
0x180053a6d  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180053a74  lea     r8, [rbp+850h+var_850]
0x180053a78  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053a7f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a8b  mov     r13, r12
0x180053a8e  xor     eax, eax
0x180053a90  jmp     loc_18005402C
0x180053a95  cmp     [rsp+950h+var_910], al
0x180053a99  jz      short loc_180053ADD
0x180053a9b  movups  xmm0, xmmword ptr [rsi]
0x180053a9e  lea     rcx, [rbp+850h+var_8D0]; struct _GUID
0x180053aa2  movdqu  xmmword ptr [rbp+850h+var_8D0.Data1], xmm0
0x180053aa7  call    ?rasSrvrGetAddressForServerAdapter@@YAKU_GUID@@@Z; rasSrvrGetAddressForServerAdapter(_GUID)
0x180053aac  mov     ebx, eax
0x180053aae  xor     eax, eax
0x180053ab0  test    ebx, ebx
0x180053ab2  jz      short loc_180053ACA
0x180053ab4  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180053abb  jz      loc_180054011
0x180053ac1  lea     rdx, aRassrvracquire_2; "RasSrvrAcquireAddress: rasSrvrGetAddres"...
0x180053ac8  jmp     short loc_180053A5D
0x180053aca  mov     rcx, rsi
0x180053acd  call    RasRdGetNboServerIpv4Address
0x180053ad2  cmp     edi, eax
0x180053ad4  mov     r14d, eax
0x180053ad7  mov     rax, r12
0x180053ada  cmovz   edi, eax
0x180053add  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180053ae4  mov     [rsp+950h+netlong], edi
0x180053ae8  jz      short loc_180053B1F
0x180053aea  mov     r8d, edi
0x180053aed  mov     word ptr [rbp+850h+var_850], ax
0x180053af1  lea     rdx, aRassrvracquire_5; "RasSrvrAcquireAddress: rasSrvrAcquiring"...
0x180053af8  lea     rcx, [rbp+850h+var_850]
0x180053afc  call    FormatRRASErrorString
0x180053b01  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180053b08  lea     r8, [rbp+850h+var_850]
0x180053b0c  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053b13  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b1f  movups  xmm0, xmmword ptr [rsi]
0x180053b22  lea     rax, [rsp+950h+var_8E8]
0x180053b27  mov     rdx, r13
0x180053b2a  lea     r9, [rsp+950h+var_8E4]
0x180053b2f  mov     [rsp+950h+var_930], rax
0x180053b34  lea     r8, [rsp+950h+netlong]
0x180053b39  lea     rcx, [rbp+850h+var_8D0]
0x180053b3d  movdqu  xmmword ptr [rbp+850h+var_8D0.Data1], xmm0
0x180053b42  call    rasSrvrAcquireAddressEx
0x180053b47  mov     ebx, eax
0x180053b49  xor     eax, eax
0x180053b4b  test    ebx, ebx
0x180053b4d  jz      loc_180053BEA
0x180053b53  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180053b5a  jz      short loc_180053B93
0x180053b5c  mov     r8d, ebx
0x180053b5f  mov     word ptr [rbp+850h+var_850], ax
0x180053b63  lea     rdx, aRassrvracquire_12; "RasSrvrAcquireAddress: rasSrvrAcquireAd"...
0x180053b6a  lea     rcx, [rbp+850h+var_850]
0x180053b6e  call    FormatRRASErrorString
0x180053b73  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180053b7a  lea     r8, [rbp+850h+var_850]
0x180053b7e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053b85  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b91  xor     eax, eax
0x180053b93  cmp     [rsp+950h+netlong], eax
0x180053b97  jz      loc_18005401B
0x180053b9d  movups  xmm0, xmmword ptr [rsi]
0x180053ba0  mov     [rsp+950h+netlong], eax
0x180053ba4  lea     r9, [rsp+950h+var_8E4]
0x180053ba9  lea     rax, [rsp+950h+var_8E8]
0x180053bae  mov     rdx, r13
0x180053bb1  lea     r8, [rsp+950h+netlong]
0x180053bb6  mov     [rsp+950h+var_930], rax
0x180053bbb  lea     rcx, [rbp+850h+var_8D0]
0x180053bbf  movdqu  xmmword ptr [rbp+850h+var_8D0.Data1], xmm0
0x180053bc4  call    rasSrvrAcquireAddressEx
0x180053bc9  mov     ebx, eax
0x180053bcb  xor     eax, eax
0x180053bcd  test    ebx, ebx
0x180053bcf  jz      short loc_180053BEA
0x180053bd1  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180053bd8  jz      loc_180054011
0x180053bde  lea     rdx, aRassrvracquire_15; "RasSrvrAcquireAddress: rasSrvrAcquireAd"...
0x180053be5  jmp     loc_180053A5D
0x180053bea  mov     rax, cs:?pfnMprAdminGetIpAddressForUser@@3P6AKPEAG0PEAKPEAH@ZEA; ulong (*pfnMprAdminGetIpAddressForUser)(ushort *,ushort *,ulong *,int *)
0x180053bf1  xor     ecx, ecx
0x180053bf3  mov     edi, [rsp+950h+netlong]
0x180053bf7  mov     r12d, edi
0x180053bfa  test    rax, rax
0x180053bfd  jz      loc_180053D84
0x180053c03  cmp     [rbp+850h+arg_30], ecx
0x180053c09  jz      short loc_180053C18
0x180053c0b  cmp     cs:?dwMprAdminGetIpAddressAdminCallbackVersion@@3KA, 1; ulong dwMprAdminGetIpAddressAdminCallbackVersion
0x180053c12  jz      loc_180053D84
0x180053c18  mov     rdx, [rsp+950h+var_8F8]
0x180053c1d  lea     r9, [rsp+950h+var_8E0]
0x180053c22  mov     rcx, [rsp+950h+String]
0x180053c27  lea     r8, [rsp+950h+var_8EC]
0x180053c2c  mov     [rsp+950h+var_8EC], edi
0x180053c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c35  mov     ebx, eax
0x180053c37  xor     eax, eax
0x180053c39  test    ebx, ebx
0x180053c3b  jz      short loc_180053CA2
0x180053c3d  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180053c44  mov     r14, [rsp+950h+var_8F8]
0x180053c49  mov     rdi, [rsp+950h+String]
0x180053c4e  jz      loc_180054016
0x180053c54  mov     word ptr [rbp+850h+var_850], ax
0x180053c58  lea     rdx, aRassrvracquire_21; "RasSrvrAcquireAddress: MprAdminGetIpAdd"...
0x180053c5f  mov     eax, [rsp+950h+var_8EC]
0x180053c63  lea     rcx, [rbp+850h+var_850]
0x180053c67  mov     dword ptr [rsp+950h+var_928], ebx
0x180053c6b  mov     r9, r14
0x180053c6e  mov     r8, rdi
0x180053c71  mov     dword ptr [rsp+950h+var_930], eax
0x180053c75  call    FormatRRASErrorString
0x180053c7a  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180053c81  lea     r8, [rbp+850h+var_850]
0x180053c85  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053c8c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c98  xor     eax, eax
0x180053c9a  mov     r13, r15
0x180053c9d  jmp     loc_180054036
0x180053ca2  mov     r8d, [rsp+950h+var_8EC]
0x180053ca7  test    r8d, r8d
0x180053caa  jz      loc_180053DF3
0x180053cb0  cmp     r14d, r8d
0x180053cb3  jz      loc_180053DF3
0x180053cb9  cmp     edi, r8d
0x180053cbc  jz      loc_180053D84
0x180053cc2  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180053cc9  jz      short loc_180053CFF
0x180053ccb  lea     rdx, aRassrvracquire_13; "RasSrvrAcquireAddress: 3rd party DLL wa"...
0x180053cd2  mov     word ptr [rbp+850h+var_850], ax
0x180053cd6  lea     rcx, [rbp+850h+var_850]
0x180053cda  call    FormatRRASErrorString
0x180053cdf  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180053ce6  lea     r8, [rbp+850h+var_850]
0x180053cea  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180053cf1  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180053cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cfd  xor     eax, eax
0x180053cff  cmp     cs:dword_1800D08DC, eax
0x180053d05  jz      short loc_180053D10
0x180053d07  mov     ecx, edi; netlong
0x180053d09  call    RasDhcpReleaseAddress
0x180053d0e  jmp     short loc_180053D23
0x180053d10  movups  xmm0, xmmword ptr [rsi]
0x180053d13  mov     edx, edi
0x180053d15  lea     rcx, [rbp+850h+var_8D0]
0x180053d19  movdqu  xmmword ptr [rbp+850h+var_8D0.Data1], xmm0
0x180053d1e  call    RasStatReleaseAddress
0x180053d23  movups  xmm0, xmmword ptr [rsi]
0x180053d26  xor     eax, eax
0x180053d28  lea     r9, [rsp+950h+var_8E4]
0x180053d2d  mov     r12d, eax
0x180053d30  mov     [rsp+950h+var_8E8], eax
0x180053d34  mov     eax, [rsp+950h+var_8EC]
0x180053d38  lea     r8, [rsp+950h+netlong]
0x180053d3d  mov     [rsp+950h+netlong], eax
0x180053d41  lea     rcx, [rbp+850h+var_8D0]
0x180053d45  lea     rax, [rsp+950h+var_8E8]
0x180053d4a  mov     rdx, r13
0x180053d4d  mov     [rsp+950h+var_930], rax
0x180053d52  movdqu  xmmword ptr [rbp+850h+var_8D0.Data1], xmm0
0x180053d57  call    rasSrvrAcquireAddressEx
0x180053d5c  mov     ebx, eax
0x180053d5e  xor     eax, eax
0x180053d60  test    ebx, ebx
0x180053d62  jz      short loc_180053D7D
0x180053d64  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180053d6b  jz      loc_180054011
0x180053d71  lea     rdx, aRassrvracquire_3; "RasSrvrAcquireAddress: rasSrvrAcquireAd"...
0x180053d78  jmp     loc_180053A5D
0x180053d7d  mov     edi, [rsp+950h+netlong]
0x180053d81  mov     r12d, edi
0x180053d84  mov     rcx, [rsp+950h+String]; String
0x180053d89  call    cs:__imp__wcsdup
0x180053d90  nop     dword ptr [rax+rax+00h]
0x180053d95  mov     [rsp+950h+var_900], rax
0x180053d9a  test    rax, rax
0x180053d9d  jnz     loc_180053E3D
0x180053da3  cmp     qword ptr cs:xmmword_1800D0740, rax
0x180053daa  lea     r8d, [rax+0Eh]
0x180053dae  mov     ebx, r8d
0x180053db1  jz      loc_180054027
0x180053db7  lea     rdx, aRassrvracquire; "RasSrvrAcquireAddress: _strdup failed a"...
0x180053dbe  mov     word ptr [rbp+850h+var_850], ax
0x180053dc2  lea     rcx, [rbp+850h+var_850]
0x180053dc6  call    FormatRRASErrorString
  ... truncated ...
```
