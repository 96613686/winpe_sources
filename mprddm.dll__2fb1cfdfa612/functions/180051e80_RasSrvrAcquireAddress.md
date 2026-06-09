# RasSrvrAcquireAddress

- ea: `0x180051e80`
- end: `0x180052667`
- name: `RasSrvrAcquireAddress`
- size: `2023`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting`

## callees

- `0x180002bbe`
- `0x180025cd4`
- `0x18004f4e4`
- `0x180051e80`
- `0x1800578ec`
- `0x1800588f4`
- `0x180058ab0`
- `0x180058dc4`
- `0x18005c3ec`
- `0x18005e6a0`
- `0x180071cec`
- `0x180073664`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_wcsdup` at `0x180052211`
- `msvcrt!_wcsdup` at `0x180052456`
- `msvcrt!_wcsdup` at `0x180052211`
- `msvcrt!_wcsdup` at `0x180052456`
- `msvcrt!free` at `0x18005261b`
- `msvcrt!free` at `0x180052624`
- `msvcrt!free` at `0x18005261b`
- `msvcrt!free` at `0x180052624`
- `KERNEL32!GetLastError` at `0x1800524cb`
- `KERNEL32!GetLastError` at `0x1800524cb`
- `KERNEL32!LeaveCriticalSection` at `0x180052631`
- `KERNEL32!LeaveCriticalSection` at `0x180052631`
- `KERNEL32!LocalAlloc` at `0x1800524bd`
- `KERNEL32!LocalAlloc` at `0x1800524bd`
- `KERNEL32!EnterCriticalSection` at `0x180051fd0`
- `KERNEL32!EnterCriticalSection` at `0x180051fd0`

## string_xrefs

- `0x180051f89`: `RasSrvrAcquireAddress for RD: %ws(hPort: 0x%x, IP address: 0x%x, UserName: %ws, PortName: %ws)`
- `0x180051ff7`: `RasSrvrAcquireAddress: IsVpnEnabledForRoutingDomain failed with error %d.`
- `0x180052065`: `RasSrvrAcquireAddress: rasSrvrGetAddressForServerAdapter failed with error %d.`
- `0x18005208f`: `RasSrvrAcquireAddress: rasSrvrAcquiring Address... nboIpAddr : %x%x`
- `0x18005210d`: `RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:1: failed with error %d.`
- `0x180052184`: `RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:2: failed with error %d.`
- `0x1800521f6`: `RasSrvrAcquireAddress: MprAdminGetIpAddressForUserL: Skipping calling version 1 admin dll for IKEv2 connection.`
- `0x1800522a5`: `RasSrvrAcquireAddress: MprAdminGetIpAddressForUser(%ws, %ws, 0x%x) failed and returned %d`
- `0x180052410`: `RasSrvrAcquireAddress: 3rd party DLL wants to hand out bad address 0x%x`
- `0x180052321`: `RasSrvrAcquireAddress: 3rd party DLL wants to hand out address 0x%x`
- `0x1800523c0`: `RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:3: failed with error %d.`
- `0x180052235`: `RasSrvrAcquireAddress: _strdup failed and returned %d`
- `0x18005247b`: `RasSrvrAcquireAddress: _strdup failed and returned %d`
- `0x1800524e2`: `RasSrvrAcquireAddress: LocalAlloc failed and returned %d`
- `0x180052587`: `RasSrvrAcquireAddress: RasReleaseRoutingDomainAddressPool failed to release lock and returned %d`

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
  int NboServerIpv4Address; // r12d
  BOOL v11; // r13d
  __int64 v12; // rdx
  u_long v13; // edi
  DWORD RoutingDomainAddressPool; // r15d
  DWORD AddressForServerAdapter; // eax
  DWORD LastError; // ebx
  const wchar_t *v17; // rdx
  wchar_t *v18; // r12
  wchar_t *v19; // rsi
  __int64 v20; // r13
  DWORD v21; // eax
  struct _GUID v22; // xmm0
  DWORD v23; // eax
  wchar_t *v24; // rsi
  unsigned int IpAddressForUser; // eax
  wchar_t *v26; // r13
  struct _GUID v27; // xmm0
  _QWORD *v28; // rax
  _QWORD *v29; // rsi
  int v30; // eax
  BOOL v31; // r8d
  __int64 v32; // rcx
  u_long *v33; // rax
  DWORD v34; // eax
  __int64 v36; // [rsp+20h] [rbp-E0h]
  __int64 v37; // [rsp+28h] [rbp-D8h]
  char v38[8]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String; // [rsp+48h] [rbp-B8h]
  u_long netlong; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v41; // [rsp+58h] [rbp-A8h]
  u_long v42; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v43[3]; // [rsp+64h] [rbp-9Ch] BYREF
  int v44; // [rsp+70h] [rbp-90h] BYREF
  int v45[3]; // [rsp+74h] [rbp-8Ch] BYREF
  struct _GUID Buf1; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-60h]
  u_long *v50; // [rsp+A8h] [rbp-58h]
  _OWORD v51[3]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v52[30]; // [rsp+E0h] [rbp-20h]
  __int16 v53; // [rsp+FEh] [rbp-2h]
  int v54; // [rsp+100h] [rbp+0h] BYREF
  char v55[2044]; // [rsp+104h] [rbp+4h] BYREF

  NboServerIpv4Address = 0;
  v51[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v51[2] = *(_OWORD *)L"000-0000-000000000000}";
  v49 = a2;
  v51[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  *(_OWORD *)v52 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v52[14] = *(_OWORD *)L"000000}";
  v50 = a4;
  String = a5;
  v47 = a6;
  v44 = 0;
  v42 = 0;
  v45[0] = 0;
  v43[0] = 0;
  v48 = 0;
  v53 = 0;
  v38[0] = 0;
  v54 = 0;
  v11 = memcmp_0(a1, &GUID_NULL, 0x10u) == 0;
  memset_0(v55, 0, sizeof(v55));
  if ( !v11 )
    MprConvertGuidToString(a1, v12, v51);
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v54) = 0;
    FormatRRASErrorString(
      &v54,
      L"RasSrvrAcquireAddress for RD: %ws(hPort: 0x%x, IP address: 0x%x, UserName: %ws, PortName: %ws)",
      v51,
      a2,
      a3,
      a5,
      a6);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v54);
  }
  v13 = 0;
  RoutingDomainAddressPool = 0;
  EnterCriticalSection(&RasSrvrCriticalSection);
  if ( v11 )
    goto LABEL_12;
  AddressForServerAdapter = IsVpnEnabledForRoutingDomain(a1, v38);
  LastError = AddressForServerAdapter;
  if ( AddressForServerAdapter )
  {
    if ( !(_QWORD)xmmword_1800C9740 )
    {
LABEL_10:
      v18 = 0;
      v19 = 0;
LABEL_73:
      v26 = String;
      goto LABEL_74;
    }
    v17 = L"RasSrvrAcquireAddress: IsVpnEnabledForRoutingDomain failed with error %d.";
LABEL_9:
    LOWORD(v54) = 0;
    FormatRRASErrorString(&v54, v17, AddressForServerAdapter);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v54);
    goto LABEL_10;
  }
  if ( v38[0] )
  {
LABEL_12:
    Buf1 = *a1;
    AddressForServerAdapter = rasSrvrGetAddressForServerAdapter(&Buf1);
    LastError = AddressForServerAdapter;
    if ( AddressForServerAdapter )
    {
      if ( !(_QWORD)xmmword_1800C9740 )
        goto LABEL_10;
      v17 = L"RasSrvrAcquireAddress: rasSrvrGetAddressForServerAdapter failed with error %d.";
      goto LABEL_9;
    }
    NboServerIpv4Address = RasRdGetNboServerIpv4Address(a1);
    if ( a3 == NboServerIpv4Address )
      a3 = 0;
  }
  netlong = a3;
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v54) = 0;
    FormatRRASErrorString(&v54, L"RasSrvrAcquireAddress: rasSrvrAcquiring Address... nboIpAddr : %x%x", a3);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v54);
  }
  v20 = v49;
  Buf1 = *a1;
  v21 = rasSrvrAcquireAddressEx((unsigned int)&Buf1, v49, (unsigned int)&netlong, (unsigned int)&v44, (__int64)v43);
  v19 = 0;
  LastError = v21;
  if ( v21 )
  {
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v54) = 0;
      FormatRRASErrorString(&v54, L"RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:1: failed with error %d.", v21);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v54);
    }
    if ( !netlong )
      goto LABEL_26;
    v22 = *a1;
    netlong = 0;
    Buf1 = v22;
    v23 = rasSrvrAcquireAddressEx((unsigned int)&Buf1, v20, (unsigned int)&netlong, (unsigned int)&v44, (__int64)v43);
    LastError = v23;
    if ( v23 )
    {
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v54) = 0;
        FormatRRASErrorString(&v54, L"RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:2: failed with error %d.", v23);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800C9740,
          &v54);
      }
LABEL_26:
      v18 = 0;
      goto LABEL_73;
    }
  }
  v13 = netlong;
  if ( !pfnMprAdminGetIpAddressForUser )
    goto LABEL_32;
  if ( a7 && dwMprAdminGetIpAddressAdminCallbackVersion == 1 )
  {
    if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        *((_QWORD *)&xmmword_1800C9740 + 1),
        L"RasSrvrAcquireAddress: MprAdminGetIpAddressForUserL: Skipping calling version 1 admin dll for IKEv2 connection.");
LABEL_32:
    v24 = String;
    goto LABEL_33;
  }
  v24 = String;
  v42 = netlong;
  IpAddressForUser = pfnMprAdminGetIpAddressForUser(String, v47, &v42, v45);
  LastError = IpAddressForUser;
  if ( !IpAddressForUser )
  {
    if ( v42 && NboServerIpv4Address != v42 )
    {
      if ( v13 != v42 )
      {
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v54) = 0;
          FormatRRASErrorString(&v54, L"RasSrvrAcquireAddress: 3rd party DLL wants to hand out address 0x%x");
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v54);
        }
        if ( dword_1800C98DC )
        {
          RasDhcpReleaseAddress(v13);
        }
        else
        {
          Buf1 = *a1;
          RasStatReleaseAddress(&Buf1, v13);
        }
        v27 = *a1;
        netlong = v42;
        v43[0] = 0;
        Buf1 = v27;
        LastError = rasSrvrAcquireAddressEx(
                      (unsigned int)&Buf1,
                      v20,
                      (unsigned int)&netlong,
                      (unsigned int)&v44,
                      (__int64)v43);
        if ( LastError )
        {
          if ( (_QWORD)xmmword_1800C9740 )
          {
            LOWORD(v54) = 0;
            FormatRRASErrorString(
              &v54,
              L"RasSrvrAcquireAddress: rasSrvrAcquireAddressEx:3: failed with error %d.",
              LastError);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
              gRasIpAddrMgmtEtwContext,
              xmmword_1800C9740,
              &v54);
          }
          v13 = 0;
          goto LABEL_10;
        }
        v13 = netlong;
      }
LABEL_33:
      v18 = _wcsdup(v24);
      if ( !v18 )
      {
        LastError = 14;
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v54) = 0;
          FormatRRASErrorString(&v54, L"RasSrvrAcquireAddress: _strdup failed and returned %d", 14);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v54);
        }
        goto LABEL_56;
      }
      v41 = _wcsdup(v47);
      v19 = v41;
      if ( !v41 )
      {
        LastError = 14;
        if ( (_QWORD)xmmword_1800C9740 )
        {
          LOWORD(v54) = 0;
          FormatRRASErrorString(&v54, L"RasSrvrAcquireAddress: _strdup failed and returned %d", 14);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            xmmword_1800C9740,
            &v54);
        }
        goto LABEL_73;
      }
      v28 = LocalAlloc(0x40u, 0x30u);
      v29 = v28;
      if ( v28 )
      {
        v28[1] = v20;
        v30 = v43[0];
        v31 = v45[0] != 0;
        v29[3] = v18;
        v29[4] = v41;
        *((_DWORD *)v29 + 10) = v31 | (v30 != 0 ? 4 : 0);
        Buf1 = *a1;
        RoutingDomainAddressPool = RasGetRoutingDomainAddressPool(&Buf1, 1, &v48);
        if ( RoutingDomainAddressPool )
          goto LABEL_70;
        v32 = v48;
        if ( v48 )
        {
          *v29 = *(_QWORD *)(v48 + 24);
          v33 = v50;
          *(_QWORD *)(v32 + 24) = v29;
          *v33 = v13;
          *((_DWORD *)v29 + 4) = v13;
        }
        Buf1 = *a1;
        v34 = RasReleaseRoutingDomainAddressPool(&Buf1);
        RoutingDomainAddressPool = v34;
        if ( !v34 || !(_QWORD)xmmword_1800C9740 )
          goto LABEL_70;
        LOWORD(v54) = 0;
        FormatRRASErrorString(
          &v54,
          L"RasSrvrAcquireAddress: RasReleaseRoutingDomainAddressPool failed to release lock and returned %d",
          v34);
      }
      else
      {
        LastError = GetLastError();
        if ( !(_QWORD)xmmword_1800C9740 )
          goto LABEL_70;
        LOWORD(v54) = 0;
        FormatRRASErrorString(&v54, L"RasSrvrAcquireAddress: LocalAlloc failed and returned %d", LastError);
      }
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v54);
LABEL_70:
      if ( !LastError && !RoutingDomainAddressPool )
        goto LABEL_81;
      v19 = v41;
      goto LABEL_73;
    }
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v54) = 0;
      FormatRRASErrorString(&v54, L"RasSrvrAcquireAddress: 3rd party DLL wants to hand out bad address 0x%x");
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v54);
    }
    LastError = 1168;
LABEL_55:
    v18 = 0;
LABEL_56:
    v19 = 0;
    goto LABEL_73;
  }
  if ( !(_QWORD)xmmword_1800C9740 )
    goto LABEL_55;
  LODWORD(v37) = IpAddressForUser;
  LOWORD(v54) = 0;
  LODWORD(v36) = v42;
  v26 = v24;
  FormatRRASErrorString(
    &v54,
    L"RasSrvrAcquireAddress: MprAdminGetIpAddressForUser(%ws, %ws, 0x%x) failed and returned %d",
    v24,
    v47,
    v36,
    v37);
  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
    gRasIpAddrMgmtEtwContext,
    xmmword_1800C9740,
    &v54);
  v18 = 0;
  v19 = 0;
LABEL_74:
  if ( v45[0] )
    ((void (__fastcall *)(wchar_t *, wchar_t *, u_long *))pfnMprAdminReleaseIpAddress)(v26, v47, &v42);
  if ( v13 )
  {
    if ( dword_1800C98DC )
    {
      RasDhcpReleaseAddress(v13);
    }
    else
    {
      Buf1 = *a1;
      RasStatReleaseAddress(&Buf1, v13);
    }
  }
  free(v18);
  free(v19);
LABEL_81:
  LeaveCriticalSection(&RasSrvrCriticalSection);
  if ( !LastError && RoutingDomainAddressPool )
    return RoutingDomainAddressPool;
  return LastError;
}

```

## disassembly

```asm
0x180051e80  push    rbp
0x180051e82  push    rbx
0x180051e83  push    rsi
0x180051e84  push    rdi
0x180051e85  push    r12
0x180051e87  push    r13
0x180051e89  push    r14
0x180051e8b  push    r15
0x180051e8d  lea     rbp, [rsp-818h]
0x180051e95  sub     rsp, 918h
0x180051e9c  mov     rax, cs:__security_cookie
0x180051ea3  xor     rax, rsp
0x180051ea6  mov     [rbp+850h+var_50], rax
0x180051ead  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180051eb4  xor     r12d, r12d
0x180051eb7  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180051ebe  mov     esi, r8d
0x180051ec1  mov     rdi, [rbp+850h+arg_20]
0x180051ec8  mov     rbx, rdx
0x180051ecb  mov     r15, [rbp+850h+arg_28]
0x180051ed2  xor     eax, eax
0x180051ed4  movaps  [rbp+850h+var_8A0], xmm0
0x180051ed8  lea     r8d, [r12+10h]; Size
0x180051edd  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180051ee4  mov     r14, rcx
0x180051ee7  movaps  [rbp+850h+var_880], xmm0
0x180051eeb  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x180051ef2  mov     [rbp+850h+var_8B0], rdx
0x180051ef6  lea     rdx, GUID_NULL; Buf2
0x180051efd  movaps  [rbp+850h+var_890], xmm1
0x180051f01  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180051f08  movaps  xmmword ptr [rbp+850h+var_870], xmm1
0x180051f0c  movups  xmmword ptr [rbp+850h+var_870+0Eh], xmm0
0x180051f10  mov     [rbp+850h+var_8A8], r9
0x180051f14  mov     [rsp+950h+String], rdi
0x180051f19  mov     [rbp+850h+var_8C0], r15
0x180051f1d  mov     [rsp+950h+var_8E0], r12d
0x180051f22  mov     [rsp+950h+var_8F0], r12d
0x180051f27  mov     [rsp+950h+var_8DC], r12d
0x180051f2c  mov     [rsp+950h+var_8EC], r12d
0x180051f31  mov     [rbp+850h+var_8B8], r12
0x180051f35  mov     [rbp+850h+var_852], ax
0x180051f39  mov     [rsp+950h+var_910], r12b
0x180051f3e  call    memcmp_0
0x180051f43  test    eax, eax
0x180051f45  mov     [rbp+850h+var_850], r12d
0x180051f49  mov     r13d, r12d
0x180051f4c  lea     rcx, [rbp+850h+var_84C]; void *
0x180051f50  setz    r13b
0x180051f54  mov     r8d, 7FCh; Size
0x180051f5a  xor     edx, edx; Val
0x180051f5c  call    memset_0
0x180051f61  test    r13d, r13d
0x180051f64  jnz     short loc_180051F72
0x180051f66  lea     r8, [rbp+850h+var_8A0]
0x180051f6a  mov     rcx, r14
0x180051f6d  call    MprConvertGuidToString
0x180051f72  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180051f79  jz      short loc_180051FC3
0x180051f7b  mov     [rsp+950h+var_920], r15
0x180051f80  lea     r8, [rbp+850h+var_8A0]
0x180051f84  mov     [rsp+950h+var_928], rdi
0x180051f89  lea     rdx, aRassrvracquire_6; "RasSrvrAcquireAddress for RD: %ws(hPort"...
0x180051f90  mov     r9, rbx
0x180051f93  mov     dword ptr [rsp+950h+var_930], esi
0x180051f97  lea     rcx, [rbp+850h+var_850]
0x180051f9b  mov     word ptr [rbp+850h+var_850], r12w
0x180051fa0  call    FormatRRASErrorString
0x180051fa5  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180051fac  lea     r8, [rbp+850h+var_850]
0x180051fb0  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180051fb7  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180051fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fc3  lea     rcx, ?RasSrvrCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180051fca  mov     edi, r12d
0x180051fcd  mov     r15d, r12d
0x180051fd0  call    cs:__imp_EnterCriticalSection
0x180051fd6  test    r13d, r13d
0x180051fd9  jnz     short loc_180052044
0x180051fdb  lea     rdx, [rsp+950h+var_910]
0x180051fe0  mov     rcx, r14
0x180051fe3  call    IsVpnEnabledForRoutingDomain
0x180051fe8  mov     ebx, eax
0x180051fea  test    eax, eax
0x180051fec  jz      short loc_180052038
0x180051fee  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180051ff5  jz      short loc_18005202D
0x180051ff7  lea     rdx, aRassrvracquire_9; "RasSrvrAcquireAddress: IsVpnEnabledForR"...
0x180051ffe  mov     r8d, eax
0x180052001  mov     word ptr [rbp+850h+var_850], r12w
0x180052006  lea     rcx, [rbp+850h+var_850]
0x18005200a  call    FormatRRASErrorString
0x18005200f  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180052016  lea     r8, [rbp+850h+var_850]
0x18005201a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180052021  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180052028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005202d  mov     r12, rdi
0x180052030  mov     rsi, rdi
0x180052033  jmp     loc_1800525CA
0x180052038  cmp     [rsp+950h+var_910], r12b
0x18005203d  jnz     short loc_180052044
0x18005203f  test    r13d, r13d
0x180052042  jz      short loc_180052080
0x180052044  movups  xmm0, xmmword ptr [r14]
0x180052048  lea     rcx, [rbp+850h+Buf1]; Buf1
0x18005204c  movdqu  xmmword ptr [rbp+850h+Buf1.Data1], xmm0
0x180052051  call    ?rasSrvrGetAddressForServerAdapter@@YAKU_GUID@@@Z; rasSrvrGetAddressForServerAdapter(_GUID)
0x180052056  mov     ebx, eax
0x180052058  test    eax, eax
0x18005205a  jz      short loc_18005206E
0x18005205c  cmp     qword ptr cs:xmmword_1800C9740, r12
0x180052063  jz      short loc_18005202D
0x180052065  lea     rdx, aRassrvracquire_2; "RasSrvrAcquireAddress: rasSrvrGetAddres"...
0x18005206c  jmp     short loc_180051FFE
0x18005206e  mov     rcx, r14
0x180052071  call    RasRdGetNboServerIpv4Address
0x180052076  xor     ecx, ecx
0x180052078  mov     r12d, eax
0x18005207b  cmp     esi, eax
0x18005207d  cmovz   esi, ecx
0x180052080  cmp     qword ptr cs:xmmword_1800C9740, rdi
0x180052087  mov     [rsp+950h+netlong], esi
0x18005208b  jz      short loc_1800520C4
0x18005208d  xor     ecx, ecx
0x18005208f  lea     rdx, aRassrvracquire_5; "RasSrvrAcquireAddress: rasSrvrAcquiring"...
0x180052096  mov     word ptr [rbp+850h+var_850], cx
0x18005209a  mov     r8d, esi
0x18005209d  lea     rcx, [rbp+850h+var_850]
0x1800520a1  call    FormatRRASErrorString
0x1800520a6  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800520ad  lea     r8, [rbp+850h+var_850]
0x1800520b1  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800520b8  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800520bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800520c4  movups  xmm0, xmmword ptr [r14]
0x1800520c8  mov     r13, [rbp+850h+var_8B0]
0x1800520cc  lea     rax, [rsp+950h+var_8EC]
0x1800520d1  lea     r9, [rsp+950h+var_8E0]
0x1800520d6  mov     [rsp+950h+var_930], rax
0x1800520db  lea     r8, [rsp+950h+netlong]
0x1800520e0  mov     rdx, r13
0x1800520e3  lea     rcx, [rbp+850h+Buf1]
0x1800520e7  movdqu  xmmword ptr [rbp+850h+Buf1.Data1], xmm0
0x1800520ec  call    rasSrvrAcquireAddressEx
0x1800520f1  xor     esi, esi
0x1800520f3  mov     ebx, eax
0x1800520f5  test    eax, eax
0x1800520f7  jz      loc_1800521BA
0x1800520fd  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x180052104  jz      short loc_18005213B
0x180052106  mov     r8d, eax
0x180052109  mov     word ptr [rbp+850h+var_850], si
0x18005210d  lea     rdx, aRassrvracquire_12; "RasSrvrAcquireAddress: rasSrvrAcquireAd"...
0x180052114  lea     rcx, [rbp+850h+var_850]
0x180052118  call    FormatRRASErrorString
0x18005211d  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180052124  lea     r8, [rbp+850h+var_850]
0x180052128  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005212f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180052136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005213b  cmp     [rsp+950h+netlong], esi
0x18005213f  jz      short loc_1800521B2
0x180052141  movups  xmm0, xmmword ptr [r14]
0x180052145  lea     rax, [rsp+950h+var_8EC]
0x18005214a  mov     [rsp+950h+netlong], esi
0x18005214e  lea     r9, [rsp+950h+var_8E0]
0x180052153  mov     [rsp+950h+var_930], rax
0x180052158  lea     r8, [rsp+950h+netlong]
0x18005215d  mov     rdx, r13
0x180052160  lea     rcx, [rbp+850h+Buf1]
0x180052164  movdqu  xmmword ptr [rbp+850h+Buf1.Data1], xmm0
0x180052169  call    rasSrvrAcquireAddressEx
0x18005216e  mov     ebx, eax
0x180052170  test    eax, eax
0x180052172  jz      short loc_1800521BA
0x180052174  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18005217b  jz      short loc_1800521B2
0x18005217d  mov     r8d, eax
0x180052180  mov     word ptr [rbp+850h+var_850], si
0x180052184  lea     rdx, aRassrvracquire_15; "RasSrvrAcquireAddress: rasSrvrAcquireAd"...
0x18005218b  lea     rcx, [rbp+850h+var_850]
0x18005218f  call    FormatRRASErrorString
0x180052194  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005219b  lea     r8, [rbp+850h+var_850]
0x18005219f  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800521a6  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800521ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521b2  mov     r12, rsi
0x1800521b5  jmp     loc_1800525CA
0x1800521ba  mov     rax, cs:?pfnMprAdminGetIpAddressForUser@@3P6AKPEAG0PEAKPEAH@ZEA; ulong (*pfnMprAdminGetIpAddressForUser)(ushort *,ushort *,ulong *,int *)
0x1800521c1  mov     edi, [rsp+950h+netlong]
0x1800521c5  test    rax, rax
0x1800521c8  jz      short loc_180052209
0x1800521ca  cmp     [rbp+850h+arg_30], esi
0x1800521d0  jz      loc_18005226F
0x1800521d6  cmp     cs:?dwMprAdminGetIpAddressAdminCallbackVersion@@3KA, 1; ulong dwMprAdminGetIpAddressAdminCallbackVersion
0x1800521dd  jnz     loc_18005226F
0x1800521e3  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x1800521ea  test    rdx, rdx
0x1800521ed  jz      short loc_180052209
0x1800521ef  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800521f6  lea     r8, aRassrvracquire_18; "RasSrvrAcquireAddress: MprAdminGetIpAdd"...
0x1800521fd  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180052204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052209  mov     rsi, [rsp+950h+String]
0x18005220e  mov     rcx, rsi; String
0x180052211  call    cs:__imp__wcsdup
0x180052217  mov     r12, rax
0x18005221a  test    rax, rax
0x18005221d  jnz     loc_180052452
0x180052223  cmp     qword ptr cs:xmmword_1800C9740, r15
0x18005222a  lea     ebx, [rax+0Eh]
0x18005222d  jz      loc_18005244A
0x180052233  xor     ecx, ecx
0x180052235  lea     rdx, aRassrvracquire; "RasSrvrAcquireAddress: _strdup failed a"...
0x18005223c  mov     word ptr [rbp+850h+var_850], cx
0x180052240  mov     r8d, ebx
0x180052243  lea     rcx, [rbp+850h+var_850]
0x180052247  call    FormatRRASErrorString
0x18005224c  mov     rdx, qword ptr cs:xmmword_1800C9740
0x180052253  lea     r8, [rbp+850h+var_850]
0x180052257  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005225e  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180052265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005226a  jmp     loc_18005244A
0x18005226f  mov     rsi, [rsp+950h+String]
0x180052274  lea     r9, [rsp+950h+var_8DC]
0x180052279  mov     rdx, [rbp+850h+var_8C0]
0x18005227d  lea     r8, [rsp+950h+var_8F0]
0x180052282  mov     rcx, rsi
0x180052285  mov     [rsp+950h+var_8F0], edi
0x180052289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005228e  mov     ebx, eax
0x180052290  test    eax, eax
0x180052292  jz      short loc_1800522F6
0x180052294  cmp     qword ptr cs:xmmword_1800C9740, r15
0x18005229b  jz      loc_180052447
0x1800522a1  mov     r9, [rbp+850h+var_8C0]
0x1800522a5  lea     rdx, aRassrvracquire_22; "RasSrvrAcquireAddress: MprAdminGetIpAdd"...
0x1800522ac  xor     eax, eax
0x1800522ae  mov     dword ptr [rsp+950h+var_928], ebx
0x1800522b2  mov     word ptr [rbp+850h+var_850], ax
0x1800522b6  lea     rcx, [rbp+850h+var_850]
0x1800522ba  mov     eax, [rsp+950h+var_8F0]
0x1800522be  mov     r8, rsi
0x1800522c1  mov     dword ptr [rsp+950h+var_930], eax
0x1800522c5  mov     r13, rsi
0x1800522c8  call    FormatRRASErrorString
0x1800522cd  mov     rdx, qword ptr cs:xmmword_1800C9740
0x1800522d4  lea     r8, [rbp+850h+var_850]
0x1800522d8  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800522df  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800522e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522eb  mov     r12, r15
0x1800522ee  mov     rsi, r15
0x1800522f1  jmp     loc_1800525CF
0x1800522f6  mov     r8d, [rsp+950h+var_8F0]
0x1800522fb  test    r8d, r8d
0x1800522fe  jz      loc_180052405
0x180052304  cmp     r12d, r8d
0x180052307  jz      loc_180052405
0x18005230d  cmp     edi, r8d
0x180052310  jz      loc_18005220E
0x180052316  cmp     qword ptr cs:xmmword_1800C9740, r15
0x18005231d  jz      short loc_180052353
0x18005231f  xor     eax, eax
0x180052321  lea     rdx, aRassrvracquire_13; "RasSrvrAcquireAddress: 3rd party DLL wa"...
0x180052328  lea     rcx, [rbp+850h+var_850]
0x18005232c  mov     word ptr [rbp+850h+var_850], ax
0x180052330  call    FormatRRASErrorString
0x180052335  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18005233c  lea     r8, [rbp+850h+var_850]
0x180052340  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180052347  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18005234e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052353  cmp     cs:dword_1800C98DC, r15d
0x18005235a  jz      short loc_180052365
0x18005235c  mov     ecx, edi; netlong
0x18005235e  call    RasDhcpReleaseAddress
0x180052363  jmp     short loc_180052379
0x180052365  movups  xmm0, xmmword ptr [r14]
0x180052369  mov     edx, edi
0x18005236b  lea     rcx, [rbp+850h+Buf1]
0x18005236f  movdqu  xmmword ptr [rbp+850h+Buf1.Data1], xmm0
0x180052374  call    RasStatReleaseAddress
0x180052379  mov     eax, [rsp+950h+var_8F0]
0x18005237d  lea     r9, [rsp+950h+var_8E0]
0x180052382  movups  xmm0, xmmword ptr [r14]
0x180052386  mov     [rsp+950h+netlong], eax
0x18005238a  lea     r8, [rsp+950h+netlong]
0x18005238f  lea     rax, [rsp+950h+var_8EC]
0x180052394  mov     [rsp+950h+var_8EC], r15d
0x180052399  mov     rdx, r13
0x18005239c  mov     [rsp+950h+var_930], rax
0x1800523a1  lea     rcx, [rbp+850h+Buf1]
0x1800523a5  movdqu  xmmword ptr [rbp+850h+Buf1.Data1], xmm0
0x1800523aa  call    rasSrvrAcquireAddressEx
0x1800523af  mov     ebx, eax
0x1800523b1  test    eax, eax
  ... truncated ...
```
