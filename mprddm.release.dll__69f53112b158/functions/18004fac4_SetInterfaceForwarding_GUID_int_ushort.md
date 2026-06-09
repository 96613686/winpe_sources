# SetInterfaceForwarding(_GUID,int,ushort)

- ea: `0x18004fac4`
- end: `0x1800500b4`
- name: `?SetInterfaceForwarding@@YAKU_GUID@@HG@Z`
- size: `1520`
- prototype: `unsigned int __fastcall(struct _GUID *__struct_ptr, int, unsigned __int16)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180055e54`
- `0x180056024`

## callees

- `0x180027ec0`
- `0x18004fac4`
- `0x18006aa20`
- `0x1800755b8`
- `0x1800771b8`
- `0x180081b88`
- `0x180081d58`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `msvcrt!free` at `0x18005003c`
- `msvcrt!free` at `0x180050065`
- `msvcrt!free` at `0x18005003c`
- `msvcrt!free` at `0x180050065`
- `KERNEL32!LocalFree` at `0x180050057`
- `KERNEL32!LocalFree` at `0x180050057`
- `ADVAPI32!RegCloseKey` at `0x18005007b`
- `ADVAPI32!RegCloseKey` at `0x18005007b`
- `ADVAPI32!RegOpenKeyExA` at `0x18004fd37`
- `ADVAPI32!RegOpenKeyExA` at `0x18004fd37`
- `RPCRT4!UuidFromStringW` at `0x18004fe01`
- `RPCRT4!UuidFromStringW` at `0x18004fe01`
- `rtutils!LogEventW` at `0x18004fee3`
- `rtutils!LogEventW` at `0x18004fee3`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x18004fe90`
- `IPHLPAPI!SetIpInterfaceEntry` at `0x18004fe90`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18004fe39`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18004fe39`
- `IPHLPAPI!SetIpStatisticsEx` at `0x18004ffaf`
- `IPHLPAPI!SetIpStatisticsEx` at `0x18004ffaf`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18004ff74`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180050026`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18004ff74`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180050026`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x18004fe6b`
- `IPHLPAPI!InitializeIpInterfaceEntry` at `0x18004fe6b`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18004ff17`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18004ff17`

## string_xrefs

- `0x18004fc05`: `SetInterfaceForwarding: DirectAccess registry keys not found. Continuing in normal mode.`
- `0x18004fc66`: `SetInterfaceForwarding: IsDirectAccessConfigured failed with error 0x%x`
- `0x18004fc4d`: `SetInterfaceForwarding: DirectAccess is deployed. No need to change the IPv6 forwarding settings.`
- `0x18004fce2`: `SetInterfaceForwarding: GetDirectAccessInterfaces failed with error 0x%x, trying to read remoteaccess service registry`
- `0x18004fd29`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x18004fd5d`: `SetInterfaceForwarding: Opening remoteaccess service registry failed with error 0x%x`
- `0x18004fdca`: `SetInterfaceForwarding: Querying remoteaccess service registry failed with error 0x%x`
- `0x18004ff96`: `SetInterfaceForwarding: SetCompartmentThreadId failed with error 0x%x.`
- `0x180050004`: `SetInterfaceForwarding completes successfully`

## pseudocode

```c
__int64 __fastcall SetInterfaceForwarding(struct _GUID *a1, int a2, unsigned __int16 a3)
{
  ULONG v3; // r15d
  WCHAR *v6; // rdi
  int v7; // r13d
  int v8; // r12d
  __int64 v9; // rcx
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  const wchar_t *v13; // r8
  const wchar_t *v14; // rdx
  __int64 v15; // r8
  unsigned int DirectAccessInterfaces; // eax
  unsigned int v17; // eax
  unsigned int ValueWithAllocW; // eax
  __int64 v19; // rax
  unsigned int v20; // eax
  __int64 v21; // rdx
  DWORD v22; // edx
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r14d
  NET_IF_COMPARTMENT_ID v24; // ecx
  unsigned int RoutingDomainConfigData; // eax
  unsigned int v26; // eax
  ULONG v27; // eax
  __int64 v28; // rdx
  const wchar_t *v29; // r8
  NET_IF_COMPARTMENT_ID CompartmentId; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR *v32; // [rsp+38h] [rbp-C8h] BYREF
  int v33; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+44h] [rbp-BCh]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  NET_LUID InterfaceLuid; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR plpwsSubStrings[2]; // [rsp+60h] [rbp-A0h] BYREF
  UUID Uuid; // [rsp+70h] [rbp-90h] BYREF
  MIB_IPSTATS_LH Statistics; // [rsp+80h] [rbp-80h] BYREF
  _MIB_IPINTERFACE_ROW Row; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v42[4]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v43; // [rsp+1D0h] [rbp+D0h]
  int v44; // [rsp+1D8h] [rbp+D8h]
  wchar_t v45; // [rsp+1DCh] [rbp+DCh]
  __int16 v46; // [rsp+1DEh] [rbp+DEh]
  int v47; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v48[2044]; // [rsp+1E4h] [rbp+E4h] BYREF

  v3 = a3;
  v33 = 0;
  Block = 0;
  v32 = 0;
  hKey = 0;
  v6 = 0;
  memset_0(&Statistics, 0, sizeof(Statistics));
  InterfaceLuid.Value = 0;
  memset_0(&Row, 0, sizeof(Row));
  v7 = dword_1800CF650;
  *(_OWORD *)plpwsSubStrings = 0;
  v44 = *(_DWORD *)L"0}";
  v8 = 0;
  v42[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v42[3] = *(_OWORD *)L"-000000000000}";
  v42[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v45 = a00000000000000[38];
  v43 = *(_QWORD *)L"00000}";
  v34 = 0;
  CompartmentId = 0;
  v42[2] = *(_OWORD *)L"000-0000-000000000000}";
  v46 = 0;
  v47 = 0;
  memset_0(v48, 0, sizeof(v48));
  v11 = IsDirectAccessConfigured(v9, &v33);
  if ( !v11 )
    goto LABEL_5;
  if ( v11 != 2 )
  {
    if ( !(_QWORD)xmmword_1800D0740 )
      goto LABEL_60;
    v14 = L"SetInterfaceForwarding: IsDirectAccessConfigured failed with error 0x%x";
    goto LABEL_13;
  }
  v12 = *((_QWORD *)&xmmword_1800D0740 + 1);
  v11 = 0;
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
  {
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"SetInterfaceForwarding: DirectAccess registry keys not found. Continuing in normal mode.");
LABEL_5:
    v12 = *((_QWORD *)&xmmword_1800D0740 + 1);
  }
  if ( v33 != 1 || v7 )
  {
    Statistics.dwDefaultTTL = -1;
    Statistics.dwForwarding = 2 - (a2 != 0);
    CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
    if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a1->Data4 == *(_QWORD *)GUID_NULL.Data4 )
    {
      v24 = 1;
      CompartmentId = 1;
    }
    else
    {
      RoutingDomainConfigData = GetRoutingDomainConfigData(a1, 256, 4, &CompartmentId);
      v24 = CompartmentId;
      v11 = RoutingDomainConfigData;
    }
    if ( !v11 && CurrentThreadCompartmentId != v24 )
    {
      v26 = SetCurrentThreadCompartmentId(v24);
      v11 = v26;
      if ( v26 )
      {
        if ( !(_QWORD)xmmword_1800D0740 )
          goto LABEL_60;
        v15 = v26;
        v14 = L"SetInterfaceForwarding: SetCompartmentThreadId failed with error 0x%x.";
LABEL_14:
        LOWORD(v47) = 0;
        FormatRRASErrorString(&v47, v14, v15);
        v12 = xmmword_1800D0740;
        v13 = (const wchar_t *)&v47;
LABEL_15:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          v12,
          v13);
        goto LABEL_60;
      }
      v8 = 1;
    }
    v27 = SetIpStatisticsEx(&Statistics, v3);
    v11 = v27;
    if ( v27 )
    {
      if ( !(_QWORD)xmmword_1800D0740 )
        goto LABEL_58;
      LOWORD(v47) = 0;
      FormatRRASErrorString(&v47, L"SetInterfaceForwarding: SetIpStatisticsEx failed with error 0x%x", v27);
      v28 = xmmword_1800D0740;
      v29 = (const wchar_t *)&v47;
    }
    else
    {
      v28 = *((_QWORD *)&xmmword_1800D0740 + 1);
      if ( !*((_QWORD *)&xmmword_1800D0740 + 1) )
        goto LABEL_58;
      v29 = L"SetInterfaceForwarding completes successfully";
    }
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      v28,
      v29);
LABEL_58:
    if ( v8 )
      SetCurrentThreadCompartmentId(CurrentThreadCompartmentId);
    goto LABEL_60;
  }
  Uuid = 0;
  if ( v3 == 23 )
  {
    if ( !v12 )
      goto LABEL_60;
    v13 = L"SetInterfaceForwarding: DirectAccess is deployed. No need to change the IPv6 forwarding settings.";
    goto LABEL_15;
  }
  DirectAccessInterfaces = GetDirectAccessInterfaces(v10, &Block, &v32);
  v11 = DirectAccessInterfaces;
  if ( DirectAccessInterfaces )
  {
    v34 = 1;
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LOWORD(v47) = 0;
      FormatRRASErrorString(
        &v47,
        L"SetInterfaceForwarding: GetDirectAccessInterfaces failed with error 0x%x, trying to read remoteaccess service registry",
        DirectAccessInterfaces);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v47);
    }
    v17 = RegOpenKeyExA(
            HKEY_LOCAL_MACHINE,
            "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
            0,
            0x20019u,
            &hKey);
    v11 = v17;
    if ( v17 )
    {
      if ( (_QWORD)xmmword_1800D0740 )
      {
        LOWORD(v47) = 0;
        FormatRRASErrorString(
          &v47,
          L"SetInterfaceForwarding: Opening remoteaccess service registry failed with error 0x%x",
          v17);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
          gRasIpAddrMgmtEtwContext,
          xmmword_1800D0740,
          &v47);
      }
      v6 = v32;
      goto LABEL_60;
    }
    ValueWithAllocW = RegQueryValueWithAllocW(hKey);
    v6 = v32;
    v11 = ValueWithAllocW;
    if ( ValueWithAllocW || !v32 )
    {
      if ( !(_QWORD)xmmword_1800D0740 )
        goto LABEL_60;
      v15 = ValueWithAllocW;
      v14 = L"SetInterfaceForwarding: Querying remoteaccess service registry failed with error 0x%x";
      goto LABEL_14;
    }
  }
  else
  {
    v6 = v32;
  }
  v19 = -1;
  do
    ++v19;
  while ( v6[v19] );
  if ( !(_DWORD)v19 )
    goto LABEL_60;
  v6[(unsigned int)(v19 - 1)] = 0;
  if ( UuidFromStringW(v6 + 1, &Uuid) )
  {
    v11 = 1003;
    if ( !(_QWORD)xmmword_1800D0740 )
      goto LABEL_60;
    v14 = L"SetInterfaceForwarding: UuidFromStringW failed with error 0x%x";
    goto LABEL_13;
  }
  v20 = ConvertInterfaceGuidToLuid(&Uuid, &InterfaceLuid);
  v11 = v20;
  if ( v20 )
  {
    if ( !(_QWORD)xmmword_1800D0740 )
      goto LABEL_60;
    v15 = v20;
    v14 = L"SetInterfaceForwarding: ConvertInterfaceGuidToLuid failed with error 0x%x";
    goto LABEL_14;
  }
  InitializeIpInterfaceEntry(&Row);
  Row.InterfaceLuid = InterfaceLuid;
  Row.Family = v3;
  Row.ForwardingEnabled = a2 != 0;
  v11 = SetIpInterfaceEntry(&Row);
  if ( v11 )
  {
    MprConvertGuidToString(a1, v21, v42);
    plpwsSubStrings[1] = v6;
    v22 = 20282;
    plpwsSubStrings[0] = (LPWSTR)v42;
    if ( !a2 )
      v22 = 20283;
    LogEventW(1u, v22, 2u, plpwsSubStrings);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      v14 = L"SetInterfaceForwarding: SetIpInterfaceEntry failed with error 0x%x";
LABEL_13:
      v15 = v11;
      goto LABEL_14;
    }
  }
LABEL_60:
  if ( Block )
    free(Block);
  if ( v6 )
  {
    if ( v34 )
      LocalFree(v6);
    else
      free(v6);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v11;
}

```

## disassembly

```asm
0x18004fac4  mov     [rsp-8+arg_8], rbx
0x18004fac9  push    rbp
0x18004faca  push    rsi
0x18004facb  push    rdi
0x18004facc  push    r12
0x18004face  push    r13
0x18004fad0  push    r14
0x18004fad2  push    r15
0x18004fad4  lea     rbp, [rsp-8F0h]
0x18004fadc  sub     rsp, 9F0h
0x18004fae3  mov     rax, cs:__security_cookie
0x18004faea  xor     rax, rsp
0x18004faed  mov     [rbp+920h+var_40], rax
0x18004faf4  xor     ebx, ebx
0x18004faf6  movzx   r15d, r8w
0x18004fafa  mov     r14d, edx
0x18004fafd  mov     [rsp+0A20h+var_9E0], ebx
0x18004fb01  mov     rsi, rcx
0x18004fb04  mov     [rsp+0A20h+Block], rbx
0x18004fb09  xor     edx, edx; Val
0x18004fb0b  mov     [rsp+0A20h+var_9E8], rbx
0x18004fb10  lea     r8d, [rbx+5Ch]; Size
0x18004fb14  mov     [rsp+0A20h+hKey], rbx
0x18004fb19  lea     rcx, [rbp+920h+Statistics]; void *
0x18004fb1d  mov     edi, ebx
0x18004fb1f  call    memset_0
0x18004fb24  xor     edx, edx; Val
0x18004fb26  mov     qword ptr [rsp+0A20h+InterfaceLuid], rbx
0x18004fb2b  mov     r8d, 0A8h; Size
0x18004fb31  lea     rcx, [rbp+920h+Row]; void *
0x18004fb35  call    memset_0
0x18004fb3a  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x18004fb40  lea     rcx, [rbp+920h+var_83C]; void *
0x18004fb47  movaps  xmm1, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18004fb4e  xorps   xmm0, xmm0
0x18004fb51  mov     r13d, cs:dword_1800CF650
0x18004fb58  xor     edx, edx; Val
0x18004fb5a  movups  xmmword ptr [rsp+0A20h+plpwsSubStrings], xmm0
0x18004fb5f  mov     r8d, 7FCh; Size
0x18004fb65  mov     [rbp+920h+var_848], eax
0x18004fb6b  movaps  xmm0, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18004fb72  mov     r12d, ebx
0x18004fb75  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x18004fb7c  movaps  [rbp+920h+var_880], xmm0
0x18004fb83  movaps  xmm0, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x18004fb8a  movaps  [rbp+920h+var_860], xmm0
0x18004fb91  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x18004fb99  movaps  [rbp+920h+var_890], xmm1
0x18004fba0  movaps  xmm1, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18004fba7  mov     [rbp+920h+var_844], ax
0x18004fbae  xor     eax, eax
0x18004fbb0  movsd   [rbp+920h+var_850], xmm0
0x18004fbb8  mov     [rsp+0A20h+var_9DC], ebx
0x18004fbbc  mov     [rsp+0A20h+CompartmentId], ebx
0x18004fbc0  movaps  [rbp+920h+var_870], xmm1
0x18004fbc7  mov     [rbp+920h+var_842], ax
0x18004fbce  mov     [rbp+920h+var_840], ebx
0x18004fbd4  call    memset_0
0x18004fbd9  lea     rdx, [rsp+0A20h+var_9E0]
0x18004fbde  call    IsDirectAccessConfigured
0x18004fbe3  mov     ebx, eax
0x18004fbe5  xor     eax, eax
0x18004fbe7  test    ebx, ebx
0x18004fbe9  jz      short loc_18004FC18
0x18004fbeb  cmp     ebx, 2
0x18004fbee  jnz     short loc_18004FC56
0x18004fbf0  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18004fbf7  mov     ebx, eax
0x18004fbf9  test    rdx, rdx
0x18004fbfc  jz      short loc_18004FC1F
0x18004fbfe  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004fc05  lea     r8, aSetinterfacefo_5; "SetInterfaceForwarding: DirectAccess re"...
0x18004fc0c  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004fc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc18  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18004fc1f  cmp     [rsp+0A20h+var_9E0], 1
0x18004fc24  jnz     loc_18004FF08
0x18004fc2a  test    r13d, r13d
0x18004fc2d  jnz     loc_18004FF08
0x18004fc33  xorps   xmm0, xmm0
0x18004fc36  movups  xmmword ptr [rsp+0A20h+Uuid.Data1], xmm0
0x18004fc3b  cmp     r15d, 17h
0x18004fc3f  jnz     short loc_18004FCAA
0x18004fc41  xor     r13d, r13d
0x18004fc44  test    rdx, rdx
0x18004fc47  jz      loc_180050032
0x18004fc4d  lea     r8, aSetinterfacefo_1; "SetInterfaceForwarding: DirectAccess is"...
0x18004fc54  jmp     short loc_18004FC92
0x18004fc56  xor     r13d, r13d
0x18004fc59  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18004fc60  jz      loc_180050032
0x18004fc66  lea     rdx, aSetinterfacefo_7; "SetInterfaceForwarding: IsDirectAccessC"...
0x18004fc6d  mov     r8d, ebx
0x18004fc70  lea     rcx, [rbp+920h+var_840]
0x18004fc77  mov     word ptr [rbp+920h+var_840], r13w
0x18004fc7f  call    FormatRRASErrorString
0x18004fc84  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004fc8b  lea     r8, [rbp+920h+var_840]
0x18004fc92  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004fc99  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004fca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fca5  jmp     loc_180050032
0x18004fcaa  lea     r8, [rsp+0A20h+var_9E8]
0x18004fcaf  lea     rdx, [rsp+0A20h+Block]
0x18004fcb4  call    GetDirectAccessInterfaces
0x18004fcb9  xor     r13d, r13d
0x18004fcbc  mov     ebx, eax
0x18004fcbe  test    eax, eax
0x18004fcc0  jz      loc_18004FDD6
0x18004fcc6  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18004fccd  mov     [rsp+0A20h+var_9DC], 1
0x18004fcd5  jz      short loc_18004FD16
0x18004fcd7  mov     r8d, eax
0x18004fcda  mov     word ptr [rbp+920h+var_840], r13w
0x18004fce2  lea     rdx, aSetinterfacefo_3; "SetInterfaceForwarding: GetDirectAccess"...
0x18004fce9  lea     rcx, [rbp+920h+var_840]
0x18004fcf0  call    FormatRRASErrorString
0x18004fcf5  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004fcfc  lea     r8, [rbp+920h+var_840]
0x18004fd03  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004fd0a  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004fd11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd16  lea     rax, [rsp+0A20h+hKey]
0x18004fd1b  mov     r9d, 20019h; samDesired
0x18004fd21  xor     r8d, r8d; ulOptions
0x18004fd24  mov     [rsp+0A20h+phkResult], rax; phkResult
0x18004fd29  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x18004fd30  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004fd37  call    cs:__imp_RegOpenKeyExA
0x18004fd3e  nop     dword ptr [rax+rax+00h]
0x18004fd43  mov     ebx, eax
0x18004fd45  test    eax, eax
0x18004fd47  jz      short loc_18004FD9B
0x18004fd49  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18004fd50  jz      short loc_18004FD91
0x18004fd52  mov     r8d, eax
0x18004fd55  mov     word ptr [rbp+920h+var_840], r13w
0x18004fd5d  lea     rdx, aSetinterfacefo_6; "SetInterfaceForwarding: Opening remotea"...
0x18004fd64  lea     rcx, [rbp+920h+var_840]
0x18004fd6b  call    FormatRRASErrorString
0x18004fd70  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004fd77  lea     r8, [rbp+920h+var_840]
0x18004fd7e  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004fd85  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004fd8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd91  mov     rdi, [rsp+0A20h+var_9E8]
0x18004fd96  jmp     loc_180050032
0x18004fd9b  mov     rcx, [rsp+0A20h+hKey]; hKey
0x18004fda0  lea     r9, [rsp+0A20h+var_9E8]
0x18004fda5  call    RegQueryValueWithAllocW
0x18004fdaa  mov     rdi, [rsp+0A20h+var_9E8]
0x18004fdaf  mov     ebx, eax
0x18004fdb1  test    eax, eax
0x18004fdb3  jnz     short loc_18004FDBA
0x18004fdb5  test    rdi, rdi
0x18004fdb8  jnz     short loc_18004FDDB
0x18004fdba  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18004fdc1  jz      loc_180050032
0x18004fdc7  mov     r8d, eax
0x18004fdca  lea     rdx, aSetinterfacefo_8; "SetInterfaceForwarding: Querying remote"...
0x18004fdd1  jmp     loc_18004FC70
0x18004fdd6  mov     rdi, [rsp+0A20h+var_9E8]
0x18004fddb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004fddf  inc     rax
0x18004fde2  cmp     [rdi+rax*2], r13w
0x18004fde7  jnz     short loc_18004FDDF
0x18004fde9  test    eax, eax
0x18004fdeb  jz      loc_180050032
0x18004fdf1  dec     eax
0x18004fdf3  lea     rcx, [rdi+2]; StringUuid
0x18004fdf7  lea     rdx, [rsp+0A20h+Uuid]; Uuid
0x18004fdfc  mov     [rdi+rax*2], r13w
0x18004fe01  call    cs:__imp_UuidFromStringW
0x18004fe08  nop     dword ptr [rax+rax+00h]
0x18004fe0d  test    eax, eax
0x18004fe0f  jz      short loc_18004FE2F
0x18004fe11  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18004fe18  mov     ebx, 3EBh
0x18004fe1d  jz      loc_180050032
0x18004fe23  lea     rdx, aSetinterfacefo_0; "SetInterfaceForwarding: UuidFromStringW"...
0x18004fe2a  jmp     loc_18004FC6D
0x18004fe2f  lea     rdx, [rsp+0A20h+InterfaceLuid]; InterfaceLuid
0x18004fe34  lea     rcx, [rsp+0A20h+Uuid]; InterfaceGuid
0x18004fe39  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18004fe40  nop     dword ptr [rax+rax+00h]
0x18004fe45  mov     ebx, eax
0x18004fe47  test    eax, eax
0x18004fe49  jz      short loc_18004FE67
0x18004fe4b  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18004fe52  jz      loc_180050032
0x18004fe58  mov     r8d, eax
0x18004fe5b  lea     rdx, aSetinterfacefo; "SetInterfaceForwarding: ConvertInterfac"...
0x18004fe62  jmp     loc_18004FC70
0x18004fe67  lea     rcx, [rbp+920h+Row]; Row
0x18004fe6b  call    cs:__imp_InitializeIpInterfaceEntry
0x18004fe72  nop     dword ptr [rax+rax+00h]
0x18004fe77  mov     rax, qword ptr [rsp+0A20h+InterfaceLuid]
0x18004fe7c  lea     rcx, [rbp+920h+Row]; Row
0x18004fe80  test    r14d, r14d
0x18004fe83  mov     qword ptr [rbp+920h+Row.InterfaceLuid], rax
0x18004fe87  mov     [rbp+920h+Row.Family], r15w
0x18004fe8c  setnz   [rbp+920h+Row.ForwardingEnabled]
0x18004fe90  call    cs:__imp_SetIpInterfaceEntry
0x18004fe97  nop     dword ptr [rax+rax+00h]
0x18004fe9c  mov     ebx, eax
0x18004fe9e  test    eax, eax
0x18004fea0  jz      loc_180050032
0x18004fea6  lea     r8, [rbp+920h+var_890]
0x18004fead  mov     rcx, rsi
0x18004feb0  call    MprConvertGuidToString
0x18004feb5  mov     [rsp+0A20h+plpwsSubStrings+8], rdi
0x18004feba  mov     ecx, 1; wEventType
0x18004febf  lea     rax, [rbp+920h+var_890]
0x18004fec6  mov     edx, 4F3Ah
0x18004fecb  mov     [rsp+0A20h+plpwsSubStrings], rax
0x18004fed0  lea     r9, [rsp+0A20h+plpwsSubStrings]; plpwsSubStrings
0x18004fed5  lea     r8d, [rcx+1]; cNumberOfSubStrings
0x18004fed9  test    r14d, r14d
0x18004fedc  jnz     short loc_18004FEE3
0x18004fede  mov     edx, 4F3Bh; dwMessageId
0x18004fee3  call    cs:__imp_LogEventW
0x18004feea  nop     dword ptr [rax+rax+00h]
0x18004feef  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18004fef6  jz      loc_180050032
0x18004fefc  lea     rdx, aSetinterfacefo_2; "SetInterfaceForwarding: SetIpInterfaceE"...
0x18004ff03  jmp     loc_18004FC6D
0x18004ff08  neg     r14d
0x18004ff0b  sbb     eax, eax
0x18004ff0d  or      [rbp+920h+Statistics.dwDefaultTTL], 0FFFFFFFFh
0x18004ff11  add     eax, 2
0x18004ff14  mov     dword ptr [rbp+920h+Statistics], eax
0x18004ff17  call    cs:__imp_GetCurrentThreadCompartmentId
0x18004ff1e  nop     dword ptr [rax+rax+00h]
0x18004ff23  mov     rcx, [rsi]
0x18004ff26  mov     r14d, eax
0x18004ff29  cmp     rcx, qword ptr cs:GUID_NULL.Data1
0x18004ff30  jnz     short loc_18004FF4A
0x18004ff32  mov     rcx, [rsi+8]
0x18004ff36  cmp     rcx, qword ptr cs:GUID_NULL.Data4
0x18004ff3d  jnz     short loc_18004FF4A
0x18004ff3f  mov     ecx, 1
0x18004ff44  mov     [rsp+0A20h+CompartmentId], ecx
0x18004ff48  jmp     short loc_18004FF68
0x18004ff4a  lea     r9, [rsp+0A20h+CompartmentId]
0x18004ff4f  mov     edx, 100h
0x18004ff54  mov     r8d, 4
0x18004ff5a  mov     rcx, rsi
0x18004ff5d  call    GetRoutingDomainConfigData
0x18004ff62  mov     ecx, [rsp+0A20h+CompartmentId]; CompartmentId
0x18004ff66  mov     ebx, eax
0x18004ff68  xor     r13d, r13d
0x18004ff6b  test    ebx, ebx
0x18004ff6d  jnz     short loc_18004FFA8
0x18004ff6f  cmp     r14d, ecx
0x18004ff72  jz      short loc_18004FFA8
0x18004ff74  call    cs:__imp_SetCurrentThreadCompartmentId
0x18004ff7b  nop     dword ptr [rax+rax+00h]
0x18004ff80  mov     ebx, eax
0x18004ff82  test    eax, eax
0x18004ff84  jz      short loc_18004FFA2
0x18004ff86  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18004ff8d  jz      loc_180050032
0x18004ff93  mov     r8d, eax
0x18004ff96  lea     rdx, aSetinterfacefo_10; "SetInterfaceForwarding: SetCompartmentT"...
0x18004ff9d  jmp     loc_18004FC70
0x18004ffa2  mov     r12d, 1
0x18004ffa8  mov     edx, r15d; Family
0x18004ffab  lea     rcx, [rbp+920h+Statistics]; Statistics
0x18004ffaf  call    cs:__imp_SetIpStatisticsEx
0x18004ffb6  nop     dword ptr [rax+rax+00h]
0x18004ffbb  mov     ebx, eax
0x18004ffbd  test    eax, eax
0x18004ffbf  jz      short loc_18004FFF8
0x18004ffc1  cmp     qword ptr cs:xmmword_1800D0740, r13
0x18004ffc8  jz      short loc_18005001E
0x18004ffca  mov     r8d, eax
0x18004ffcd  mov     word ptr [rbp+920h+var_840], r13w
0x18004ffd5  lea     rdx, aSetinterfacefo_4; "SetInterfaceForwarding: SetIpStatistics"...
0x18004ffdc  lea     rcx, [rbp+920h+var_840]
0x18004ffe3  call    FormatRRASErrorString
0x18004ffe8  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18004ffef  lea     r8, [rbp+920h+var_840]
0x18004fff6  jmp     short loc_18005000B
0x18004fff8  mov     rdx, qword ptr cs:xmmword_1800D0740+8
0x18004ffff  test    rdx, rdx
0x180050002  jz      short loc_18005001E
0x180050004  lea     r8, aSetinterfacefo_9; "SetInterfaceForwarding completes succes"...
0x18005000b  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050012  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005001e  test    r12d, r12d
0x180050021  jz      short loc_180050032
0x180050023  mov     ecx, r14d; CompartmentId
0x180050026  call    cs:__imp_SetCurrentThreadCompartmentId
0x18005002d  nop     dword ptr [rax+rax+00h]
0x180050032  mov     rcx, [rsp+0A20h+Block]; Block
0x180050037  test    rcx, rcx
0x18005003a  jz      short loc_180050048
0x18005003c  call    cs:__imp_free
0x180050043  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
