# ReadInterfaceExtraInfo

- ea: `0x180036a40`
- end: `0x180037300`
- name: `ReadInterfaceExtraInfo`
- size: `2240`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800091dc`
- `0x180015ad4`

## callees

- `0x180033f28`
- `0x180034b10`
- `0x180036320`
- `0x180036a40`
- `0x180037308`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!malloc` at `0x1800370eb`
- `msvcrt!malloc` at `0x1800370eb`
- `msvcrt!free` at `0x180037147`
- `msvcrt!free` at `0x180037147`
- `ntdll!RtlIpv6StringToAddressW` at `0x180036fea`
- `ntdll!RtlIpv6StringToAddressW` at `0x180036fea`
- `ntdll!RtlIpv4StringToAddressW` at `0x180036fc6`
- `ntdll!RtlIpv4StringToAddressW` at `0x180036fc6`
- `ADVAPI32!RegQueryValueExW` at `0x180036b92`
- `ADVAPI32!RegQueryValueExW` at `0x180036ca3`
- `ADVAPI32!RegQueryValueExW` at `0x180036d08`
- `ADVAPI32!RegQueryValueExW` at `0x180036e86`
- `ADVAPI32!RegQueryValueExW` at `0x180036f27`
- `ADVAPI32!RegQueryValueExW` at `0x180036f81`
- `ADVAPI32!RegQueryValueExW` at `0x1800370bc`
- `ADVAPI32!RegQueryValueExW` at `0x180037122`
- `ADVAPI32!RegQueryValueExW` at `0x180037184`
- `ADVAPI32!RegQueryValueExW` at `0x180036b92`
- `ADVAPI32!RegQueryValueExW` at `0x180036ca3`
- `ADVAPI32!RegQueryValueExW` at `0x180036d08`
- `ADVAPI32!RegQueryValueExW` at `0x180036e86`
- `ADVAPI32!RegQueryValueExW` at `0x180036f27`
- `ADVAPI32!RegQueryValueExW` at `0x180036f81`
- `ADVAPI32!RegQueryValueExW` at `0x1800370bc`
- `ADVAPI32!RegQueryValueExW` at `0x180037122`
- `ADVAPI32!RegQueryValueExW` at `0x180037184`

## string_xrefs

- `0x180036c9c`: `VsidOrVlanTag`
- `0x180036cc8`: `VsidOrVlanTag`
- `0x180036b16`: `ReadInterfaceExtraInfo`
- `0x180036bb8`: `ReadInterfaceExtraInfo`
- `0x180036c4b`: `ReadInterfaceExtraInfo`
- `0x180036d5a`: `ReadInterfaceExtraInfo`
- `0x180036dd1`: `ReadInterfaceExtraInfo`
- `0x180036ec6`: `ReadInterfaceExtraInfo`
- `0x18003702b`: `ReadInterfaceExtraInfo`
- `0x1800371a9`: `ReadInterfaceExtraInfo`
- `0x18003726f`: `ReadInterfaceExtraInfo`
- `0x180036d65`: `%s: Registry key for routing domain ID is invalid`
- `0x180036ccf`: `%s: Registry key for %s is not valid %d`
- `0x180036ddd`: `%s: ReadQoSPoliciesFromRegistry failed with error %d`
- `0x180036ed3`: `%s: Registry value for RadiusAttributeClass is not valid %d`
- `0x180036f1d`: `InitiateConfigPayload`
- `0x18003725a`: `InitiateConfigPayload`
- `0x180037261`: `%s: Registry value for %s is not valid %d`
- `0x180037038`: `%s: Invalid SourceIpAddress in the registry %d`
- `0x1800371b0`: `%s: Invalid Value of S2S_PBK_INFO in Registry %d .`
- `0x1800371f8`: `%s: Invalid Value of S2S_PBK_INFO in Registry %d .`

## pseudocode

```c
__int64 __fastcall ReadInterfaceExtraInfo(HKEY hKey, int a2, int a3, struct in_addr *a4)
{
  unsigned int v8; // ebx
  int v10; // r15d
  LSTATUS v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  LSTATUS v14; // eax
  const WCHAR *v15; // r9
  const wchar_t *v16; // rdx
  unsigned int QoSPoliciesFromRegistry; // eax
  GUID *v18; // r9
  unsigned int v19; // eax
  bool v20; // zf
  GUID *v21; // r9
  unsigned int v22; // eax
  BYTE *v23; // rbx
  unsigned int v24; // eax
  unsigned int v25; // r12d
  GUID *v26; // r9
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  int v30; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v31[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  LPCWSTR Terminator; // [rsp+50h] [rbp-B0h] BYREF
  GUID v33; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+68h] [rbp-98h] BYREF
  __int128 v35; // [rsp+6Ch] [rbp-94h]
  __int128 v36; // [rsp+7Ch] [rbp-84h]
  int v37; // [rsp+8Ch] [rbp-74h]
  _WORD Data[40]; // [rsp+90h] [rbp-70h] BYREF
  BYTE v39[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v40; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v41[2044]; // [rsp+154h] [rbp+54h] BYREF

  cbData = 0;
  Type = 0;
  memset_0(Data, 0, sizeof(Data));
  memset_0(v39, 0, 0x64u);
  Terminator = 0;
  v30 = 0;
  *(_DWORD *)v31 = 0;
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  v34 = 0;
  v37 = 0;
  v35 = 0;
  v36 = 0;
  if ( !a4 || !hKey )
    return 87;
  memset_0(a4, 0, 0x2C8u);
  v8 = IsModernStackEnabled(&v30);
  if ( v8 )
  {
    if ( !(_QWORD)xmmword_180071090 )
      return v8;
    LOWORD(v40) = 0;
    FormatRRASErrorString(
      &v40,
      L"%s: IsModernStackEnabled returned an error.Exiting the function .",
      L"ReadInterfaceExtraInfo");
LABEL_6:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v40);
    return v8;
  }
  v10 = 1;
  if ( !a3 )
  {
    if ( a2 != 2 )
      goto LABEL_32;
    goto LABEL_40;
  }
  cbData = 80;
  v11 = RegQueryValueExW(hKey, L"RoutingDomainId", 0, &Type, (LPBYTE)Data, &cbData);
  if ( v11 != 2 )
  {
    if ( v11 || Type != 1 )
    {
      if ( (_QWORD)xmmword_180071090 )
      {
        LOWORD(v40) = 0;
        FormatRRASErrorString(&v40, L"%s: Registry key for routing domain ID is invalid", L"ReadInterfaceExtraInfo");
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180071090,
          &v40);
      }
      return 87;
    }
    Data[39] = 0;
    v13 = -1;
    do
      ++v13;
    while ( Data[v13] );
    v8 = MprConvertStringToGuid(Data, v13, &a4[7], v12);
    if ( v8 )
    {
      if ( !(_QWORD)xmmword_180071090 )
        return v8;
      LOWORD(v40) = 0;
      FormatRRASErrorString(
        &v40,
        L"%s: Failed to convert Routing domain ID from string to GUID format: %d",
        L"ReadInterfaceExtraInfo",
        v8);
      goto LABEL_6;
    }
    if ( a2 == 2 )
      goto LABEL_40;
    goto LABEL_23;
  }
  if ( a2 != 2 )
  {
LABEL_23:
    if ( a2 != 4 )
    {
      cbData = 4;
      v14 = RegQueryValueExW(hKey, L"VsidOrVlanTag", 0, &Type, &a4[11].S_un.S_un_b.s_b1, &cbData);
      if ( v14 != 2 && (v14 || Type != 4) )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          v15 = L"VsidOrVlanTag";
LABEL_29:
          v16 = L"%s: Registry key for %s is not valid %d";
LABEL_100:
          LODWORD(lpData) = v14;
          LOWORD(v34) = 0;
          v33 = GUID_NULL;
          LOWORD(v40) = 0;
          FormatRRASErrorString(&v40, v16, L"ReadInterfaceExtraInfo", v15, lpData);
          goto LABEL_101;
        }
        return 87;
      }
      cbData = 8;
      v14 = RegQueryValueExW(hKey, L"MultiTenantIfLuid", 0, &Type, &a4[12].S_un.S_un_b.s_b1, &cbData);
      v8 = v14;
      if ( v14 == 2 )
      {
        v8 = 0;
LABEL_32:
        cbData = 4;
        return v8;
      }
      if ( v14 || Type != 3 )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          v15 = L"MultiTenantIfLuid";
          goto LABEL_29;
        }
        return 87;
      }
      goto LABEL_53;
    }
LABEL_40:
    QoSPoliciesFromRegistry = ReadQoSPoliciesFromRegistry(hKey);
    v8 = QoSPoliciesFromRegistry;
    if ( QoSPoliciesFromRegistry )
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v40) = 0;
        LOWORD(v34) = 0;
        v33 = GUID_NULL;
        FormatRRASErrorString(
          &v40,
          L"%s: ReadQoSPoliciesFromRegistry failed with error %d",
          L"ReadInterfaceExtraInfo",
          QoSPoliciesFromRegistry);
        v18 = &v33;
        if ( a4 != (struct in_addr *)-28LL )
          v18 = (GUID *)&a4[7];
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_1800710A0,
          &v40,
          v18,
          0,
          &v34);
      }
      return v8;
    }
    if ( a2 == 2 && a3 )
    {
      cbData = 514;
      memset_0(&a4[14], 0, 0x202u);
      v19 = RegQueryValueExW(hKey, L"RadiusAttributeClass", 0, &Type, &a4[14].S_un.S_un_b.s_b1, &cbData);
      v8 = v19;
      if ( v19 == 2 )
      {
        cbData = 4;
        goto LABEL_54;
      }
      if ( v19 || Type != 1 )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          LOWORD(v40) = 0;
          LOWORD(v34) = 0;
          v33 = GUID_NULL;
          FormatRRASErrorString(
            &v40,
            L"%s: Registry value for RadiusAttributeClass is not valid %d",
            L"ReadInterfaceExtraInfo",
            v19);
LABEL_101:
          v26 = &v33;
          if ( a4 != (struct in_addr *)-28LL )
            v26 = (GUID *)&a4[7];
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_1800710A0,
            &v40,
            v26,
            0,
            &v34);
          return 87;
        }
        return 87;
      }
    }
LABEL_53:
    cbData = 4;
    if ( a2 != 2 )
      return v8;
LABEL_54:
    v14 = RegQueryValueExW(hKey, L"InitiateConfigPayload", 0, &Type, &a4[143].S_un.S_un_b.s_b1, &cbData);
    if ( v14 == 2 )
    {
      a4[143].S_un.S_addr = 1;
    }
    else if ( v14 || Type != 4 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        return 87;
      v15 = L"InitiateConfigPayload";
      goto LABEL_99;
    }
    cbData = 100;
    a4[144].S_un.S_un_w.s_w1 = 0;
    v14 = RegQueryValueExW(hKey, L"SourceIpAddress", 0, &Type, v39, &cbData);
    v8 = v14;
    if ( v14 == 2 )
    {
      v8 = 0;
    }
    else if ( v14 || Type != 1 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        return 87;
      v15 = L"SourceIpAddress";
      goto LABEL_99;
    }
    if ( *(_WORD *)v39 )
    {
      v8 = RtlIpv4StringToAddressW((PCWSTR)v39, 1u, &Terminator, a4 + 145);
      if ( v8 )
      {
        v8 = RtlIpv6StringToAddressW((PCWSTR)v39, &Terminator, (struct in6_addr *)&a4[145]);
        if ( v8 )
        {
          v20 = (_QWORD)xmmword_1800710A0 == 0;
          v8 = 87;
          a4[144].S_un.S_un_w.s_w1 = 0;
          if ( !v20 )
          {
            LOWORD(v40) = 0;
            LOWORD(v34) = 0;
            v33 = GUID_NULL;
            FormatRRASErrorString(
              &v40,
              L"%s: Invalid SourceIpAddress in the registry %d",
              L"ReadInterfaceExtraInfo",
              87);
            v21 = &v33;
            if ( a4 != (struct in_addr *)-28LL )
              v21 = (GUID *)&a4[7];
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
              gCfgStoreEtwContext,
              xmmword_1800710A0,
              &v40,
              v21,
              0,
              &v34);
          }
        }
        else
        {
          a4[144].S_un.S_un_w.s_w1 = 23;
        }
      }
      else
      {
        a4[144].S_un.S_un_w.s_w1 = 2;
      }
    }
    if ( !v30 )
    {
LABEL_92:
      if ( *(_DWORD *)v31 )
      {
LABEL_94:
        a4[176].S_un.S_addr = v10;
        return v8;
      }
LABEL_93:
      v10 = 0;
      goto LABEL_94;
    }
    cbData = 0;
    v22 = RegQueryValueExW(hKey, L"InterfaceInfoPbk", 0, &Type, 0, &cbData);
    v8 = v22;
    if ( v22 != 2 )
    {
      if ( v22 || Type != 3 || !cbData )
      {
        if ( !(_QWORD)xmmword_180071090 )
          return v8;
        LOWORD(v40) = 0;
        FormatRRASErrorString(
          &v40,
          L"%s: Invalid Value of S2S_PBK_INFO in Registry %d .",
          L"ReadInterfaceExtraInfo",
          v22);
        goto LABEL_6;
      }
      v23 = (BYTE *)malloc(cbData);
      if ( !v23 )
        return 8;
      v24 = RegQueryValueExW(hKey, L"InterfaceInfoPbk", 0, &Type, v23, &cbData);
      v25 = v24;
      if ( v24 || Type != 3 )
      {
        if ( (_QWORD)xmmword_180071090 )
        {
          LOWORD(v40) = 0;
          FormatRRASErrorString(
            &v40,
            L"%s: Invalid Value of S2S_PBK_INFO in Registry %d .",
            L"ReadInterfaceExtraInfo",
            v24);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180071090,
            &v40);
        }
      }
      else
      {
        v25 = ConvertPbkRegistryEntryToPbkInfo(
                (struct _S2S_PBK_REGISTRY_INFO *)v23,
                (struct _DIM_INTERFACE_OBJECT_EXTRA_INFO *)a4);
        free(v23);
        if ( !v25 )
          goto LABEL_81;
      }
      return v25;
    }
LABEL_81:
    cbData = 4;
    v14 = RegQueryValueExW(hKey, L"AutoConnectEnabled", 0, &Type, v31, &cbData);
    v8 = v14;
    if ( v14 == 2 )
    {
      v8 = 0;
      goto LABEL_93;
    }
    if ( v14 || Type != 4 )
    {
      if ( !(_QWORD)xmmword_1800710A0 )
        return 87;
      v15 = L"AutoConnectEnabled";
LABEL_99:
      v16 = L"%s: Registry value for %s is not valid %d";
      goto LABEL_100;
    }
    goto LABEL_92;
  }
  if ( (_QWORD)xmmword_180071090 )
  {
    LOWORD(v40) = 0;
    FormatRRASErrorString(&v40, L"%s: Routing domain ID key is absent for S2S interface.", L"ReadInterfaceExtraInfo");
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v40);
  }
  return 2;
}

```

## disassembly

```asm
0x180036a40  mov     [rsp-8+arg_8], rbx
0x180036a45  push    rbp
0x180036a46  push    rsi
0x180036a47  push    rdi
0x180036a48  push    r12
0x180036a4a  push    r13
0x180036a4c  push    r14
0x180036a4e  push    r15
0x180036a50  lea     rbp, [rsp-860h]
0x180036a58  sub     rsp, 960h
0x180036a5f  mov     rax, cs:__security_cookie
0x180036a66  xor     rax, rsp
0x180036a69  mov     [rbp+890h+var_40], rax
0x180036a70  xor     esi, esi
0x180036a72  mov     r13d, r8d
0x180036a75  mov     r12d, edx
0x180036a78  mov     [rsp+990h+cbData], esi
0x180036a7c  mov     r14, rcx
0x180036a7f  mov     [rsp+990h+Type], esi
0x180036a83  xor     edx, edx; Val
0x180036a85  lea     rcx, [rbp+890h+Data]; void *
0x180036a89  lea     r8d, [rsi+50h]; Size
0x180036a8d  mov     rdi, r9
0x180036a90  call    memset_0
0x180036a95  xor     edx, edx; Val
0x180036a97  lea     r8d, [rsi+64h]; Size
0x180036a9b  lea     rcx, [rbp+890h+var_8B0]; void *
0x180036a9f  call    memset_0
0x180036aa4  xor     edx, edx; Val
0x180036aa6  mov     [rsp+990h+Terminator], rsi
0x180036aab  mov     r8d, 7FCh; Size
0x180036ab1  mov     [rsp+990h+var_948], esi
0x180036ab5  lea     rcx, [rbp+890h+var_83C]; void *
0x180036ab9  mov     dword ptr [rsp+990h+var_944], esi
0x180036abd  mov     [rbp+890h+var_840], esi
0x180036ac0  call    memset_0
0x180036ac5  xor     eax, eax
0x180036ac7  mov     [rsp+990h+var_928], esi
0x180036acb  mov     [rbp+890h+var_904], eax
0x180036ace  xorps   xmm0, xmm0
0x180036ad1  movups  [rsp+990h+var_924], xmm0
0x180036ad6  movups  [rsp+990h+var_914], xmm0
0x180036adb  test    rdi, rdi
0x180036ade  jz      loc_1800372D1
0x180036ae4  test    r14, r14
0x180036ae7  jz      loc_1800372D1
0x180036aed  xor     edx, edx; Val
0x180036aef  mov     r8d, 2C8h; Size
0x180036af5  mov     rcx, rdi; void *
0x180036af8  call    memset_0
0x180036afd  lea     rcx, [rsp+990h+var_948]; int *
0x180036b02  call    IsModernStackEnabled
0x180036b07  mov     ebx, eax
0x180036b09  test    eax, eax
0x180036b0b  jz      short loc_180036B56
0x180036b0d  cmp     qword ptr cs:xmmword_180071090, rsi
0x180036b14  jz      short loc_180036B4F
0x180036b16  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x180036b1d  mov     word ptr [rbp+890h+var_840], si
0x180036b21  lea     rdx, aSIsmodernstack; "%s: IsModernStackEnabled returned an er"...
0x180036b28  lea     rcx, [rbp+890h+var_840]
0x180036b2c  call    FormatRRASErrorString
0x180036b31  mov     rdx, qword ptr cs:xmmword_180071090
0x180036b38  lea     r8, [rbp+890h+var_840]
0x180036b3c  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180036b43  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180036b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b4f  mov     eax, ebx
0x180036b51  jmp     loc_1800372D6
0x180036b56  mov     r15d, 1
0x180036b5c  test    r13d, r13d
0x180036b5f  jz      loc_180036D94
0x180036b65  lea     rax, [rsp+990h+cbData]
0x180036b6a  mov     [rsp+990h+cbData], 50h ; 'P'
0x180036b72  mov     [rsp+990h+lpcbData], rax; lpcbData
0x180036b77  lea     r9, [rsp+990h+Type]; lpType
0x180036b7c  lea     rax, [rbp+890h+Data]
0x180036b80  xor     r8d, r8d; lpReserved
0x180036b83  lea     rdx, aRoutingdomaini; "RoutingDomainId"
0x180036b8a  mov     [rsp+990h+lpData], rax; lpData
0x180036b8f  mov     rcx, r14; hKey
0x180036b92  call    cs:__imp_RegQueryValueExW
0x180036b98  lea     esi, [r15+1]
0x180036b9c  cmp     eax, esi
0x180036b9e  jnz     short loc_180036BF4
0x180036ba0  cmp     r12d, esi
0x180036ba3  jnz     loc_180036C6C
0x180036ba9  xor     ecx, ecx
0x180036bab  cmp     qword ptr cs:xmmword_180071090, rcx
0x180036bb2  jz      short loc_180036BED
0x180036bb4  mov     word ptr [rbp+890h+var_840], cx
0x180036bb8  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x180036bbf  lea     rcx, [rbp+890h+var_840]
0x180036bc3  lea     rdx, aSRoutingDomain_0; "%s: Routing domain ID key is absent for"...
0x180036bca  call    FormatRRASErrorString
0x180036bcf  mov     rdx, qword ptr cs:xmmword_180071090
0x180036bd6  lea     r8, [rbp+890h+var_840]
0x180036bda  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180036be1  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180036be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036bed  mov     eax, esi
0x180036bef  jmp     loc_1800372D6
0x180036bf4  xor     ecx, ecx
0x180036bf6  test    eax, eax
0x180036bf8  jnz     loc_180036D49
0x180036bfe  cmp     [rsp+990h+Type], r15d
0x180036c03  jnz     loc_180036D49
0x180036c09  mov     [rbp+890h+var_8B2], cx
0x180036c0d  lea     rax, [rbp+890h+Data]
0x180036c11  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180036c15  inc     rdx
0x180036c18  cmp     [rax+rdx*2], cx
0x180036c1c  jnz     short loc_180036C15
0x180036c1e  lea     r8, [rdi+1Ch]
0x180036c22  lea     rcx, [rbp+890h+Data]
0x180036c26  call    MprConvertStringToGuid
0x180036c2b  xor     ecx, ecx
0x180036c2d  mov     ebx, eax
0x180036c2f  test    eax, eax
0x180036c31  jz      short loc_180036C63
0x180036c33  cmp     qword ptr cs:xmmword_180071090, rcx
0x180036c3a  jz      loc_180036B4F
0x180036c40  mov     word ptr [rbp+890h+var_840], cx
0x180036c44  lea     rdx, aSFailedToConve_0; "%s: Failed to convert Routing domain ID"...
0x180036c4b  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x180036c52  mov     r9d, ebx
0x180036c55  lea     rcx, [rbp+890h+var_840]
0x180036c59  call    FormatRRASErrorString
0x180036c5e  jmp     loc_180036B31
0x180036c63  cmp     r12d, esi
0x180036c66  jz      loc_180036DA2
0x180036c6c  cmp     r12d, 4
0x180036c70  jz      loc_180036DA2
0x180036c76  lea     rcx, [rsp+990h+cbData]
0x180036c7b  mov     [rsp+990h+cbData], 4
0x180036c83  mov     [rsp+990h+lpcbData], rcx; lpcbData
0x180036c88  lea     rax, [rdi+2Ch]
0x180036c8c  mov     rcx, r14; hKey
0x180036c8f  mov     [rsp+990h+lpData], rax; lpData
0x180036c94  lea     r9, [rsp+990h+Type]; lpType
0x180036c99  xor     r8d, r8d; lpReserved
0x180036c9c  lea     rdx, aVsidorvlantag; "VsidOrVlanTag"
0x180036ca3  call    cs:__imp_RegQueryValueExW
0x180036ca9  xor     r13d, r13d
0x180036cac  cmp     eax, esi
0x180036cae  jz      short loc_180036CDB
0x180036cb0  test    eax, eax
0x180036cb2  jnz     short loc_180036CBB
0x180036cb4  cmp     [rsp+990h+Type], 4
0x180036cb9  jz      short loc_180036CDB
0x180036cbb  cmp     qword ptr cs:xmmword_1800710A0, r13
0x180036cc2  jz      loc_1800372D1
0x180036cc8  lea     r9, aVsidorvlantag; "VsidOrVlanTag"
0x180036ccf  lea     rdx, aSRegistryKeyFo_0; "%s: Registry key for %s is not valid %d"
0x180036cd6  jmp     loc_180037268
0x180036cdb  lea     rcx, [rsp+990h+cbData]
0x180036ce0  mov     [rsp+990h+cbData], 8
0x180036ce8  mov     [rsp+990h+lpcbData], rcx; lpcbData
0x180036ced  lea     rax, [rdi+30h]
0x180036cf1  mov     rcx, r14; hKey
0x180036cf4  mov     [rsp+990h+lpData], rax; lpData
0x180036cf9  lea     r9, [rsp+990h+Type]; lpType
0x180036cfe  xor     r8d, r8d; lpReserved
0x180036d01  lea     rdx, aMultitenantifl; "MultiTenantIfLuid"
0x180036d08  call    cs:__imp_RegQueryValueExW
0x180036d0e  mov     ebx, eax
0x180036d10  cmp     eax, esi
0x180036d12  jnz     short loc_180036D24
0x180036d14  mov     ebx, r13d
0x180036d17  mov     [rsp+990h+cbData], 4
0x180036d1f  jmp     loc_180036B4F
0x180036d24  test    eax, eax
0x180036d26  jnz     short loc_180036D33
0x180036d28  cmp     [rsp+990h+Type], 3
0x180036d2d  jz      loc_180036EEE
0x180036d33  cmp     qword ptr cs:xmmword_1800710A0, r13
0x180036d3a  jz      loc_1800372D1
0x180036d40  lea     r9, aMultitenantifl; "MultiTenantIfLuid"
0x180036d47  jmp     short loc_180036CCF
0x180036d49  cmp     qword ptr cs:xmmword_180071090, rcx
0x180036d50  jz      loc_1800372D1
0x180036d56  mov     word ptr [rbp+890h+var_840], cx
0x180036d5a  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x180036d61  lea     rcx, [rbp+890h+var_840]
0x180036d65  lea     rdx, aSRegistryKeyFo; "%s: Registry key for routing domain ID "...
0x180036d6c  call    FormatRRASErrorString
0x180036d71  mov     rdx, qword ptr cs:xmmword_180071090
0x180036d78  lea     r8, [rbp+890h+var_840]
0x180036d7c  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180036d83  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180036d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d8f  jmp     loc_1800372D1
0x180036d94  mov     esi, 2
0x180036d99  cmp     r12d, esi
0x180036d9c  jnz     loc_180036D17
0x180036da2  mov     rdx, rdi
0x180036da5  mov     rcx, r14; hKey
0x180036da8  call    ReadQoSPoliciesFromRegistry
0x180036dad  xor     ecx, ecx
0x180036daf  mov     ebx, eax
0x180036db1  test    eax, eax
0x180036db3  jz      loc_180036E3A
0x180036db9  cmp     qword ptr cs:xmmword_1800710A0, rcx
0x180036dc0  jz      loc_180036B4F
0x180036dc6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180036dcd  mov     word ptr [rbp+890h+var_840], cx
0x180036dd1  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x180036dd8  mov     word ptr [rsp+990h+var_928], cx
0x180036ddd  lea     rdx, aSReadqospolici_0; "%s: ReadQoSPoliciesFromRegistry failed "...
0x180036de4  mov     r9d, eax
0x180036de7  lea     rcx, [rbp+890h+var_840]
0x180036deb  movdqu  [rsp+990h+var_938], xmm0
0x180036df1  call    FormatRRASErrorString
0x180036df6  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180036dfd  lea     rax, [rdi+1Ch]
0x180036e01  xor     ecx, ecx
0x180036e03  lea     r9, [rsp+990h+var_938]
0x180036e08  test    rax, rax
0x180036e0b  lea     r8, [rbp+890h+var_840]
0x180036e0f  cmovnz  r9, rax
0x180036e13  lea     rax, [rsp+990h+var_928]
0x180036e18  mov     [rsp+990h+lpcbData], rax
0x180036e1d  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180036e24  mov     [rsp+990h+lpData], rcx
0x180036e29  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180036e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036e35  jmp     loc_180036B4F
0x180036e3a  cmp     r12d, esi
0x180036e3d  jnz     loc_180036EEE
0x180036e43  test    r13d, r13d
0x180036e46  jz      loc_180036EEE
0x180036e4c  mov     r8d, 202h; Size
0x180036e52  lea     rbx, [rdi+38h]
0x180036e56  mov     rcx, rbx; void *
0x180036e59  mov     [rsp+990h+cbData], r8d
0x180036e5e  xor     edx, edx; Val
0x180036e60  call    memset_0
0x180036e65  lea     rax, [rsp+990h+cbData]
0x180036e6a  xor     r8d, r8d; lpReserved
0x180036e6d  mov     [rsp+990h+lpcbData], rax; lpcbData
0x180036e72  lea     r9, [rsp+990h+Type]; lpType
0x180036e77  lea     rdx, aRadiusattribut; "RadiusAttributeClass"
0x180036e7e  mov     [rsp+990h+lpData], rbx; lpData
0x180036e83  mov     rcx, r14; hKey
0x180036e86  call    cs:__imp_RegQueryValueExW
0x180036e8c  mov     ebx, eax
0x180036e8e  cmp     eax, esi
0x180036e90  jnz     short loc_180036E9C
0x180036e92  mov     [rsp+990h+cbData], 4
0x180036e9a  jmp     short loc_180036EFF
0x180036e9c  xor     r13d, r13d
0x180036e9f  test    eax, eax
0x180036ea1  jnz     short loc_180036EAA
0x180036ea3  cmp     [rsp+990h+Type], r15d
0x180036ea8  jz      short loc_180036EEE
0x180036eaa  cmp     qword ptr cs:xmmword_1800710A0, r13
0x180036eb1  jz      loc_1800372D1
0x180036eb7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180036ebe  mov     r9d, eax
0x180036ec1  mov     word ptr [rbp+890h+var_840], r13w
0x180036ec6  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x180036ecd  mov     word ptr [rsp+990h+var_928], r13w
0x180036ed3  lea     rdx, aSRegistryValue; "%s: Registry value for RadiusAttributeC"...
0x180036eda  lea     rcx, [rbp+890h+var_840]
0x180036ede  movdqu  [rsp+990h+var_938], xmm0
0x180036ee4  call    FormatRRASErrorString
0x180036ee9  jmp     loc_180037294
0x180036eee  mov     [rsp+990h+cbData], 4
0x180036ef6  cmp     r12d, esi
0x180036ef9  jnz     loc_180036B4F
0x180036eff  lea     rax, [rsp+990h+cbData]
0x180036f04  xor     r8d, r8d; lpReserved
0x180036f07  mov     [rsp+990h+lpcbData], rax; lpcbData
0x180036f0c  lea     rbx, [rdi+23Ch]
0x180036f13  lea     r9, [rsp+990h+Type]; lpType
0x180036f18  mov     [rsp+990h+lpData], rbx; lpData
0x180036f1d  lea     rdx, aInitiateconfig; "InitiateConfigPayload"
0x180036f24  mov     rcx, r14; hKey
0x180036f27  call    cs:__imp_RegQueryValueExW
0x180036f2d  xor     r13d, r13d
0x180036f30  cmp     eax, esi
0x180036f32  jnz     short loc_180036F39
0x180036f34  mov     [rbx], r15d
0x180036f37  jmp     short loc_180036F4C
0x180036f39  test    eax, eax
0x180036f3b  jnz     loc_180037251
0x180036f41  cmp     [rsp+990h+Type], 4
0x180036f46  jnz     loc_180037251
0x180036f4c  lea     rax, [rsp+990h+cbData]
0x180036f51  mov     [rsp+990h+cbData], 64h ; 'd'
0x180036f59  mov     [rsp+990h+lpcbData], rax; lpcbData
0x180036f5e  lea     r9, [rsp+990h+Type]; lpType
0x180036f63  lea     rax, [rbp+890h+var_8B0]
0x180036f67  mov     [rdi+240h], r13w
0x180036f6f  xor     r8d, r8d; lpReserved
0x180036f72  mov     [rsp+990h+lpData], rax; lpData
0x180036f77  lea     rdx, aSourceipaddres; "SourceIpAddress"
0x180036f7e  mov     rcx, r14; hKey
0x180036f81  call    cs:__imp_RegQueryValueExW
0x180036f87  mov     ebx, eax
  ... truncated ...
```
