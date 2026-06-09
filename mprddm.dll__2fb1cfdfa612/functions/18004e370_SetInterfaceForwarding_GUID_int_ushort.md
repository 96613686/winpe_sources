# SetInterfaceForwarding(_GUID,int,ushort)

- ea: `0x18004e370`
- end: `0x18004e90f`
- name: `?SetInterfaceForwarding@@YAKU_GUID@@HG@Z`
- size: `1439`
- prototype: `unsigned int __fastcall(struct _GUID *Buf1, int, unsigned __int16)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005426c`
- `0x180054408`

## callees

- `0x180002bbe`
- `0x180025c98`
- `0x18004e370`
- `0x1800680dc`
- `0x180071cec`
- `0x180073664`
- `0x18007cb3c`
- `0x18007ccd0`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!free` at `0x18004e8b2`
- `msvcrt!free` at `0x18004e8cd`
- `msvcrt!free` at `0x18004e8b2`
- `msvcrt!free` at `0x18004e8cd`
- `KERNEL32!LocalFree` at `0x18004e8c5`
- `KERNEL32!LocalFree` at `0x18004e8c5`
- `ADVAPI32!RegCloseKey` at `0x18004e8dd`
- `ADVAPI32!RegCloseKey` at `0x18004e8dd`
- `ADVAPI32!RegOpenKeyExA` at `0x18004e5b9`
- `ADVAPI32!RegOpenKeyExA` at `0x18004e5b9`
- `RPCRT4!UuidFromStringW` at `0x18004e6ae`
- `RPCRT4!UuidFromStringW` at `0x18004e6ae`
- `rtutils!LogEventW` at `0x18004e778`
- `rtutils!LogEventW` at `0x18004e778`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x18004e72b`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x18004e72b`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18004e6e3`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18004e6e3`
- `IPHLPAPI!SetIpStatisticsEx` at `0x18004e82f`
- `IPHLPAPI!SetIpStatisticsEx` at `0x18004e82f`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18004e7fe`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18004e8a2`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18004e7fe`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18004e8a2`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x18004e70c`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x18004e70c`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18004e7ae`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18004e7ae`

## string_xrefs

- `0x18004e491`: `SetInterfaceForwarding: DirectAccess registry keys not found. Continuing in normal mode.`
- `0x18004e4ed`: `SetInterfaceForwarding: IsDirectAccessConfigured failed with error 0x%x`
- `0x18004e4d5`: `SetInterfaceForwarding: DirectAccess is deployed. No need to change the IPv6 forwarding settings.`
- `0x18004e55e`: `SetInterfaceForwarding: GetDirectAccessInterfaces failed with error 0x%x, trying to read remoteaccess service registry`
- `0x18004e5a5`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x18004e5d8`: `SetInterfaceForwarding: Opening remoteaccess service registry failed with error 0x%x`
- `0x18004e642`: `SetInterfaceForwarding: Querying remoteaccess service registry failed with error 0x%x`
- `0x18004e817`: `SetInterfaceForwarding: SetCompartmentThreadId failed with error 0x%x.`
- `0x18004e881`: `SetInterfaceForwarding completes successfully`

## pseudocode

```c
__int64 __fastcall SetInterfaceForwarding(struct _GUID *Buf1, int a2, unsigned __int16 a3)
{
  int v3; // r13d
  ULONG v4; // r15d
  WCHAR *v7; // rdi
  int v8; // esi
  __int64 v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  const wchar_t *v14; // r8
  const wchar_t *v15; // rdx
  unsigned int DirectAccessInterfaces; // eax
  unsigned int v17; // eax
  unsigned int ValueWithAllocW; // eax
  const wchar_t *v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // rdx
  DWORD v23; // edx
  int v24; // esi
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r14d
  unsigned int RoutingDomainConfigData; // eax
  NET_IF_COMPARTMENT_ID v27; // ecx
  ULONG v28; // eax
  __int64 v29; // rdx
  const wchar_t *v30; // r8
  int v32; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  NET_LUID InterfaceLuid; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR plpwsSubStrings[2]; // [rsp+60h] [rbp-A0h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-90h] BYREF
  MIB_IPSTATS_LH Statistics; // [rsp+80h] [rbp-80h] BYREF
  _MIB_IPINTERFACE_ROW Row; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v42[3]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v43[30]; // [rsp+1C0h] [rbp+C0h]
  __int16 v44; // [rsp+1DEh] [rbp+DEh]
  int v45; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v46[2044]; // [rsp+1E4h] [rbp+E4h] BYREF

  v3 = 0;
  v4 = a3;
  v34 = 0;
  Block = 0;
  hMem = 0;
  hKey = 0;
  v7 = 0;
  memset_0(&Statistics, 0, sizeof(Statistics));
  InterfaceLuid.Value = 0;
  memset_0(&Row, 0, sizeof(Row));
  v8 = dword_1800C8650;
  v42[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  *(_OWORD *)plpwsSubStrings = 0;
  v32 = 0;
  v42[2] = *(_OWORD *)L"000-0000-000000000000}";
  v44 = 0;
  v42[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  *(_OWORD *)v43 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v43[14] = *(_OWORD *)L"000000}";
  v45 = 0;
  memset_0(v46, 0, sizeof(v46));
  v10 = IsDirectAccessConfigured(v9, &v34);
  v12 = v10;
  if ( !v10 )
    goto LABEL_5;
  if ( v10 != 2 )
  {
    if ( !(_QWORD)xmmword_1800C9740 )
      goto LABEL_66;
    v15 = L"SetInterfaceForwarding: IsDirectAccessConfigured failed with error 0x%x";
    goto LABEL_13;
  }
  v13 = *((_QWORD *)&xmmword_1800C9740 + 1);
  v12 = 0;
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
  {
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"SetInterfaceForwarding: DirectAccess registry keys not found. Continuing in normal mode.");
LABEL_5:
    v13 = *((_QWORD *)&xmmword_1800C9740 + 1);
  }
  if ( v34 != 1 || v8 )
  {
    v24 = 0;
    Statistics.dwDefaultTTL = -1;
    Statistics.dwForwarding = 2 - (a2 != 0);
    CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
    if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
    {
      v27 = 1;
      v32 = 1;
    }
    else
    {
      RoutingDomainConfigData = GetRoutingDomainConfigData(Buf1, 256, 4, &v32);
      v27 = v32;
      v12 = RoutingDomainConfigData;
    }
    if ( !v12 && CurrentThreadCompartmentId != v27 )
    {
      v10 = SetCurrentThreadCompartmentId(v27);
      v12 = v10;
      if ( v10 )
      {
        if ( !(_QWORD)xmmword_1800C9740 )
          goto LABEL_66;
        v15 = L"SetInterfaceForwarding: SetCompartmentThreadId failed with error 0x%x.";
LABEL_13:
        LOWORD(v45) = 0;
        FormatRRASErrorString(&v45, v15, v10);
        v13 = xmmword_1800C9740;
        v14 = (const wchar_t *)&v45;
LABEL_14:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          v13,
          v14);
        goto LABEL_66;
      }
      v24 = 1;
    }
    v28 = SetIpStatisticsEx(&Statistics, v4);
    v12 = v28;
    if ( v28 )
    {
      if ( (_QWORD)xmmword_1800C9740 )
      {
        LOWORD(v45) = 0;
        FormatRRASErrorString(&v45, L"SetInterfaceForwarding: SetIpStatisticsEx failed with error 0x%x", v28);
        v29 = xmmword_1800C9740;
        v30 = (const wchar_t *)&v45;
LABEL_57:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          v29,
          v30);
      }
    }
    else
    {
      v29 = *((_QWORD *)&xmmword_1800C9740 + 1);
      if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
      {
        v30 = L"SetInterfaceForwarding completes successfully";
        goto LABEL_57;
      }
    }
    if ( !v24 )
      goto LABEL_66;
    SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
    goto LABEL_60;
  }
  Uuid = 0;
  if ( v4 == 23 )
  {
    if ( !v13 )
      goto LABEL_66;
    v14 = L"SetInterfaceForwarding: DirectAccess is deployed. No need to change the IPv6 forwarding settings.";
    goto LABEL_14;
  }
  DirectAccessInterfaces = GetDirectAccessInterfaces(v11, &Block, &hMem);
  v12 = DirectAccessInterfaces;
  if ( !DirectAccessInterfaces )
  {
    v7 = (WCHAR *)hMem;
LABEL_29:
    v21 = -1;
    do
      ++v21;
    while ( v7[v21] );
    if ( !(_DWORD)v21 )
      goto LABEL_60;
    v7[(unsigned int)(v21 - 1)] = 0;
    if ( UuidFromStringW(v7 + 1, &Uuid) )
    {
      v12 = 1003;
      if ( !(_QWORD)xmmword_1800C9740 )
        goto LABEL_60;
      v20 = 1003;
      v19 = L"SetInterfaceForwarding: UuidFromStringW failed with error 0x%x";
      goto LABEL_27;
    }
    ValueWithAllocW = ConvertInterfaceGuidToLuid(&Uuid, &InterfaceLuid);
    v12 = ValueWithAllocW;
    if ( !ValueWithAllocW )
    {
      InitializeIpInterfaceEntry(&Row);
      Row.InterfaceLuid = InterfaceLuid;
      Row.Family = v4;
      Row.ForwardingEnabled = a2 != 0;
      v12 = SetIpInterfaceEntry(&Row);
      if ( !v12 )
        goto LABEL_60;
      MprConvertGuidToString(Buf1, v22, v42);
      plpwsSubStrings[1] = v7;
      v23 = 20282;
      plpwsSubStrings[0] = (LPWSTR)v42;
      if ( !a2 )
        v23 = 20283;
      LogEventW(1u, v23, 2u, plpwsSubStrings);
      if ( !(_QWORD)xmmword_1800C9740 )
        goto LABEL_60;
      v20 = v12;
      v19 = L"SetInterfaceForwarding: SetIpInterfaceEntry failed with error 0x%x";
      goto LABEL_27;
    }
    if ( !(_QWORD)xmmword_1800C9740 )
      goto LABEL_60;
    v19 = L"SetInterfaceForwarding: ConvertInterfaceGuidToLuid failed with error 0x%x";
LABEL_26:
    v20 = ValueWithAllocW;
LABEL_27:
    LOWORD(v45) = 0;
    FormatRRASErrorString(&v45, v19, v20);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v45);
    goto LABEL_60;
  }
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LOWORD(v45) = 0;
    FormatRRASErrorString(
      &v45,
      L"SetInterfaceForwarding: GetDirectAccessInterfaces failed with error 0x%x, trying to read remoteaccess service registry",
      DirectAccessInterfaces);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v45);
  }
  v3 = 1;
  v17 = RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
          0,
          0x20019u,
          &hKey);
  v12 = v17;
  if ( v17 )
  {
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LOWORD(v45) = 0;
      FormatRRASErrorString(
        &v45,
        L"SetInterfaceForwarding: Opening remoteaccess service registry failed with error 0x%x",
        v17);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v45);
    }
    v7 = (WCHAR *)hMem;
    goto LABEL_60;
  }
  ValueWithAllocW = RegQueryValueWithAllocW(hKey);
  v7 = (WCHAR *)hMem;
  v12 = ValueWithAllocW;
  if ( !ValueWithAllocW && hMem )
    goto LABEL_29;
  if ( (_QWORD)xmmword_1800C9740 )
  {
    v19 = L"SetInterfaceForwarding: Querying remoteaccess service registry failed with error 0x%x";
    goto LABEL_26;
  }
LABEL_60:
  if ( Block )
    free(Block);
  if ( v7 )
  {
    if ( v3 )
      LocalFree(v7);
    else
      free(v7);
  }
LABEL_66:
  if ( hKey )
    RegCloseKey(hKey);
  return v12;
}

```

## disassembly

```asm
0x18004e370  mov     [rsp-8+arg_8], rbx
0x18004e375  push    rbp
0x18004e376  push    rsi
0x18004e377  push    rdi
0x18004e378  push    r12
0x18004e37a  push    r13
0x18004e37c  push    r14
0x18004e37e  push    r15
0x18004e380  lea     rbp, [rsp-8F0h]
0x18004e388  sub     rsp, 9F0h
0x18004e38f  mov     rax, cs:__security_cookie
0x18004e396  xor     rax, rsp
0x18004e399  mov     [rbp+920h+var_40], rax
0x18004e3a0  xor     r13d, r13d
0x18004e3a3  movzx   r15d, r8w
0x18004e3a7  mov     r14d, edx
0x18004e3aa  mov     [rsp+0A20h+var_9E0], r13d
0x18004e3af  mov     r12, rcx
0x18004e3b2  mov     [rsp+0A20h+Block], r13
0x18004e3b7  xor     edx, edx; Val
0x18004e3b9  mov     [rsp+0A20h+hMem], r13
0x18004e3be  lea     r8d, [r13+5Ch]; Size
0x18004e3c2  mov     [rsp+0A20h+hKey], r13
0x18004e3c7  lea     rcx, [rbp+920h+Statistics]; void *
0x18004e3cb  mov     edi, r13d
0x18004e3ce  call    memset_0
0x18004e3d3  xor     edx, edx; Val
0x18004e3d5  mov     qword ptr [rsp+0A20h+InterfaceLuid], r13
0x18004e3da  mov     r8d, 0A8h; Size
0x18004e3e0  lea     rcx, [rbp+920h+Row]; void *
0x18004e3e4  call    memset_0
0x18004e3e9  movaps  xmm1, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18004e3f0  lea     rcx, [rbp+920h+var_83C]; void *
0x18004e3f7  mov     esi, cs:dword_1800C8650
0x18004e3fd  xorps   xmm0, xmm0
0x18004e400  movaps  [rbp+920h+var_890], xmm1
0x18004e407  xor     eax, eax
0x18004e409  movaps  xmm1, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18004e410  xor     edx, edx; Val
0x18004e412  movups  xmmword ptr [rsp+0A20h+plpwsSubStrings], xmm0
0x18004e417  mov     r8d, 7FCh; Size
0x18004e41d  mov     [rsp+0A20h+var_9F0], r13d
0x18004e422  movaps  xmm0, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18004e429  movaps  [rbp+920h+var_870], xmm1
0x18004e430  movups  xmm1, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x18004e437  mov     [rbp+920h+var_842], ax
0x18004e43e  movaps  [rbp+920h+var_880], xmm0
0x18004e445  movaps  xmm0, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x18004e44c  movaps  xmmword ptr [rbp+920h+var_860], xmm0
0x18004e453  movups  xmmword ptr [rbp+920h+var_860+0Eh], xmm1
0x18004e45a  mov     [rbp+920h+var_840], r13d
0x18004e461  call    memset_0
0x18004e466  lea     rdx, [rsp+0A20h+var_9E0]
0x18004e46b  call    IsDirectAccessConfigured
0x18004e470  mov     ebx, eax
0x18004e472  test    eax, eax
0x18004e474  jz      short loc_18004E4A4
0x18004e476  cmp     eax, 2
0x18004e479  jnz     short loc_18004E4DE
0x18004e47b  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18004e482  mov     ebx, r13d
0x18004e485  test    rdx, rdx
0x18004e488  jz      short loc_18004E4AB
0x18004e48a  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004e491  lea     r8, aSetinterfacefo_5; "SetInterfaceForwarding: DirectAccess re"...
0x18004e498  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004e49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4a4  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18004e4ab  cmp     [rsp+0A20h+var_9E0], 1
0x18004e4b0  jnz     loc_18004E79A
0x18004e4b6  test    esi, esi
0x18004e4b8  jnz     loc_18004E79A
0x18004e4be  xorps   xmm0, xmm0
0x18004e4c1  movups  xmmword ptr [rsp+0A20h+Uuid.Data1], xmm0
0x18004e4c6  cmp     r15d, 17h
0x18004e4ca  jnz     short loc_18004E530
0x18004e4cc  test    rdx, rdx
0x18004e4cf  jz      loc_18004E8D3
0x18004e4d5  lea     r8, aSetinterfacefo_1; "SetInterfaceForwarding: DirectAccess is"...
0x18004e4dc  jmp     short loc_18004E518
0x18004e4de  xor     esi, esi
0x18004e4e0  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18004e4e7  jz      loc_18004E8D3
0x18004e4ed  lea     rdx, aSetinterfacefo_7; "SetInterfaceForwarding: IsDirectAccessC"...
0x18004e4f4  mov     r8d, eax
0x18004e4f7  mov     word ptr [rbp+920h+var_840], si
0x18004e4fe  lea     rcx, [rbp+920h+var_840]
0x18004e505  call    FormatRRASErrorString
0x18004e50a  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004e511  lea     r8, [rbp+920h+var_840]
0x18004e518  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004e51f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004e526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e52b  jmp     loc_18004E8D3
0x18004e530  lea     r8, [rsp+0A20h+hMem]
0x18004e535  lea     rdx, [rsp+0A20h+Block]
0x18004e53a  call    GetDirectAccessInterfaces
0x18004e53f  xor     esi, esi
0x18004e541  mov     ebx, eax
0x18004e543  test    eax, eax
0x18004e545  jz      loc_18004E685
0x18004e54b  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18004e552  jz      short loc_18004E592
0x18004e554  mov     r8d, eax
0x18004e557  mov     word ptr [rbp+920h+var_840], si
0x18004e55e  lea     rdx, aSetinterfacefo_3; "SetInterfaceForwarding: GetDirectAccess"...
0x18004e565  lea     rcx, [rbp+920h+var_840]
0x18004e56c  call    FormatRRASErrorString
0x18004e571  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004e578  lea     r8, [rbp+920h+var_840]
0x18004e57f  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004e586  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004e58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e592  lea     rax, [rsp+0A20h+hKey]
0x18004e597  mov     r9d, 20019h; samDesired
0x18004e59d  xor     r8d, r8d; ulOptions
0x18004e5a0  mov     [rsp+0A20h+phkResult], rax; phkResult
0x18004e5a5  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x18004e5ac  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004e5b3  mov     r13d, 1
0x18004e5b9  call    cs:__imp_RegOpenKeyExA
0x18004e5bf  mov     ebx, eax
0x18004e5c1  test    eax, eax
0x18004e5c3  jz      short loc_18004E616
0x18004e5c5  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18004e5cc  jz      short loc_18004E60C
0x18004e5ce  mov     r8d, eax
0x18004e5d1  mov     word ptr [rbp+920h+var_840], si
0x18004e5d8  lea     rdx, aSetinterfacefo_6; "SetInterfaceForwarding: Opening remotea"...
0x18004e5df  lea     rcx, [rbp+920h+var_840]
0x18004e5e6  call    FormatRRASErrorString
0x18004e5eb  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004e5f2  lea     r8, [rbp+920h+var_840]
0x18004e5f9  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004e600  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004e607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e60c  mov     rdi, [rsp+0A20h+hMem]
0x18004e611  jmp     loc_18004E8A8
0x18004e616  mov     rcx, [rsp+0A20h+hKey]; hKey
0x18004e61b  lea     r9, [rsp+0A20h+hMem]
0x18004e620  call    RegQueryValueWithAllocW
0x18004e625  mov     rdi, [rsp+0A20h+hMem]
0x18004e62a  mov     ebx, eax
0x18004e62c  test    eax, eax
0x18004e62e  jnz     short loc_18004E635
0x18004e630  test    rdi, rdi
0x18004e633  jnz     short loc_18004E68A
0x18004e635  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18004e63c  jz      loc_18004E8A8
0x18004e642  lea     rdx, aSetinterfacefo_8; "SetInterfaceForwarding: Querying remote"...
0x18004e649  mov     r8d, eax
0x18004e64c  lea     rcx, [rbp+920h+var_840]
0x18004e653  mov     word ptr [rbp+920h+var_840], si
0x18004e65a  call    FormatRRASErrorString
0x18004e65f  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004e666  lea     r8, [rbp+920h+var_840]
0x18004e66d  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004e674  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004e67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e680  jmp     loc_18004E8A8
0x18004e685  mov     rdi, [rsp+0A20h+hMem]
0x18004e68a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004e68e  inc     rax
0x18004e691  cmp     [rdi+rax*2], si
0x18004e695  jnz     short loc_18004E68E
0x18004e697  test    eax, eax
0x18004e699  jz      loc_18004E8A8
0x18004e69f  dec     eax
0x18004e6a1  lea     rcx, [rdi+2]; StringUuid
0x18004e6a5  lea     rdx, [rsp+0A20h+Uuid]; Uuid
0x18004e6aa  mov     [rdi+rax*2], si
0x18004e6ae  call    cs:__imp_UuidFromStringW
0x18004e6b4  test    eax, eax
0x18004e6b6  jz      short loc_18004E6D9
0x18004e6b8  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18004e6bf  mov     ebx, 3EBh
0x18004e6c4  jz      loc_18004E8A8
0x18004e6ca  mov     r8d, ebx
0x18004e6cd  lea     rdx, aSetinterfacefo_0; "SetInterfaceForwarding: UuidFromStringW"...
0x18004e6d4  jmp     loc_18004E64C
0x18004e6d9  lea     rdx, [rsp+0A20h+InterfaceLuid]; InterfaceLuid
0x18004e6de  lea     rcx, [rsp+0A20h+Uuid]; InterfaceGuid
0x18004e6e3  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18004e6e9  mov     ebx, eax
0x18004e6eb  test    eax, eax
0x18004e6ed  jz      short loc_18004E708
0x18004e6ef  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18004e6f6  jz      loc_18004E8A8
0x18004e6fc  lea     rdx, aSetinterfacefo; "SetInterfaceForwarding: ConvertInterfac"...
0x18004e703  jmp     loc_18004E649
0x18004e708  lea     rcx, [rbp+920h+Row]; Row
0x18004e70c  call    cs:__imp_InitializeIpInterfaceEntry
0x18004e712  mov     rax, qword ptr [rsp+0A20h+InterfaceLuid]
0x18004e717  lea     rcx, [rbp+920h+Row]; Row
0x18004e71b  test    r14d, r14d
0x18004e71e  mov     qword ptr [rbp+920h+Row.InterfaceLuid], rax
0x18004e722  mov     [rbp+920h+Row.Family], r15w
0x18004e727  setnz   [rbp+920h+Row.ForwardingEnabled]
0x18004e72b  call    cs:__imp_SetIpInterfaceEntry
0x18004e731  mov     ebx, eax
0x18004e733  test    eax, eax
0x18004e735  jz      loc_18004E8A8
0x18004e73b  lea     r8, [rbp+920h+var_890]
0x18004e742  mov     rcx, r12
0x18004e745  call    MprConvertGuidToString
0x18004e74a  mov     [rsp+0A20h+plpwsSubStrings+8], rdi
0x18004e74f  mov     ecx, 1; wEventType
0x18004e754  lea     rax, [rbp+920h+var_890]
0x18004e75b  mov     edx, 4F3Ah
0x18004e760  mov     [rsp+0A20h+plpwsSubStrings], rax
0x18004e765  lea     r9, [rsp+0A20h+plpwsSubStrings]; plpwsSubStrings
0x18004e76a  lea     r8d, [rcx+1]; cNumberOfSubStrings
0x18004e76e  test    r14d, r14d
0x18004e771  jnz     short loc_18004E778
0x18004e773  mov     edx, 4F3Bh; dwMessageId
0x18004e778  call    cs:__imp_LogEventW
0x18004e77e  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18004e785  jz      loc_18004E8A8
0x18004e78b  mov     r8d, ebx
0x18004e78e  lea     rdx, aSetinterfacefo_2; "SetInterfaceForwarding: SetIpInterfaceE"...
0x18004e795  jmp     loc_18004E64C
0x18004e79a  xor     esi, esi
0x18004e79c  mov     [rbp+920h+Statistics.dwDefaultTTL], 0FFFFFFFFh
0x18004e7a3  neg     r14d
0x18004e7a6  sbb     eax, eax
0x18004e7a8  add     eax, 2
0x18004e7ab  mov     dword ptr [rbp+920h+Statistics], eax
0x18004e7ae  call    cs:__imp_GetCurrentThreadCompartmentId
0x18004e7b4  lea     r8d, [rsi+10h]; Size
0x18004e7b8  mov     rcx, r12; Buf1
0x18004e7bb  lea     rdx, GUID_NULL; Buf2
0x18004e7c2  mov     r14d, eax
0x18004e7c5  call    memcmp_0
0x18004e7ca  test    eax, eax
0x18004e7cc  jz      short loc_18004E7EC
0x18004e7ce  lea     r9, [rsp+0A20h+var_9F0]
0x18004e7d3  mov     edx, 100h
0x18004e7d8  lea     r8d, [rsi+4]
0x18004e7dc  mov     rcx, r12
0x18004e7df  call    GetRoutingDomainConfigData
0x18004e7e4  mov     ecx, [rsp+0A20h+var_9F0]
0x18004e7e8  mov     ebx, eax
0x18004e7ea  jmp     short loc_18004E7F5
0x18004e7ec  mov     ecx, 1; CompartmentId
0x18004e7f1  mov     [rsp+0A20h+var_9F0], ecx
0x18004e7f5  test    ebx, ebx
0x18004e7f7  jnz     short loc_18004E828
0x18004e7f9  cmp     r14d, ecx
0x18004e7fc  jz      short loc_18004E828
0x18004e7fe  call    cs:__imp_SetCurrentThreadCompartmentId
0x18004e804  mov     ebx, eax
0x18004e806  test    eax, eax
0x18004e808  jz      short loc_18004E823
0x18004e80a  cmp     qword ptr cs:xmmword_1800C9740, rsi
0x18004e811  jz      loc_18004E8D3
0x18004e817  lea     rdx, aSetinterfacefo_10; "SetInterfaceForwarding: SetCompartmentT"...
0x18004e81e  jmp     loc_18004E4F4
0x18004e823  mov     esi, 1
0x18004e828  mov     edx, r15d; Family
0x18004e82b  lea     rcx, [rbp+920h+Statistics]; Statistics
0x18004e82f  call    cs:__imp_SetIpStatisticsEx
0x18004e835  xor     r15d, r15d
0x18004e838  mov     ebx, eax
0x18004e83a  test    eax, eax
0x18004e83c  jz      short loc_18004E875
0x18004e83e  cmp     qword ptr cs:xmmword_1800C9740, r15
0x18004e845  jz      short loc_18004E89B
0x18004e847  mov     r8d, eax
0x18004e84a  mov     word ptr [rbp+920h+var_840], r15w
0x18004e852  lea     rdx, aSetinterfacefo_4; "SetInterfaceForwarding: SetIpStatistics"...
0x18004e859  lea     rcx, [rbp+920h+var_840]
0x18004e860  call    FormatRRASErrorString
0x18004e865  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004e86c  lea     r8, [rbp+920h+var_840]
0x18004e873  jmp     short loc_18004E888
0x18004e875  mov     rdx, qword ptr cs:xmmword_1800C9740+8
0x18004e87c  test    rdx, rdx
0x18004e87f  jz      short loc_18004E89B
0x18004e881  lea     r8, aSetinterfacefo_9; "SetInterfaceForwarding completes succes"...
0x18004e888  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004e88f  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004e896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e89b  test    esi, esi
0x18004e89d  jz      short loc_18004E8D3
0x18004e89f  mov     ecx, r14d; CompartmentId
0x18004e8a2  call    cs:__imp_SetCurrentThreadCompartmentId
0x18004e8a8  mov     rcx, [rsp+0A20h+Block]; Block
0x18004e8ad  test    rcx, rcx
0x18004e8b0  jz      short loc_18004E8B8
0x18004e8b2  call    cs:__imp_free
0x18004e8b8  test    rdi, rdi
0x18004e8bb  jz      short loc_18004E8D3
0x18004e8bd  mov     rcx, rdi; Block
0x18004e8c0  test    r13d, r13d
0x18004e8c3  jz      short loc_18004E8CD
0x18004e8c5  call    cs:__imp_LocalFree
0x18004e8cb  jmp     short loc_18004E8D3
0x18004e8cd  call    cs:__imp_free
0x18004e8d3  mov     rcx, [rsp+0A20h+hKey]; hKey
0x18004e8d8  test    rcx, rcx
  ... truncated ...
```
