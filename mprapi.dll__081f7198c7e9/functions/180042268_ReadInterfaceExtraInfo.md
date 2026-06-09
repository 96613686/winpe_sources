# ReadInterfaceExtraInfo

- ea: `0x180042268`
- end: `0x180042bbc`
- name: `ReadInterfaceExtraInfo`
- size: `2388`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180022324`

## callees

- `0x180040740`
- `0x180041f30`
- `0x180042268`
- `0x180042bc4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!malloc` at `0x180042990`
- `msvcrt!malloc` at `0x180042990`
- `msvcrt!free` at `0x1800429ec`
- `msvcrt!free` at `0x1800429ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800423ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042587`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042632`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004272b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800427cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042826`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042961`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800429c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042a29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800423ba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042587`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042632`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004272b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800427cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042826`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042961`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800429c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042a29`
- `ntdll!RtlGUIDFromString` at `0x18004246d`
- `ntdll!RtlGUIDFromString` at `0x18004246d`
- `ntdll!RtlIpv6StringToAddressW` at `0x18004288f`
- `ntdll!RtlIpv6StringToAddressW` at `0x18004288f`
- `ntdll!RtlIpv4StringToAddressW` at `0x18004286b`
- `ntdll!RtlIpv4StringToAddressW` at `0x18004286b`

## string_xrefs

- `0x18004233e`: `ReadInterfaceExtraInfo`
- `0x1800423e0`: `ReadInterfaceExtraInfo`
- `0x18004248e`: `ReadInterfaceExtraInfo`
- `0x1800424e2`: `ReadInterfaceExtraInfo`
- `0x1800425bb`: `ReadInterfaceExtraInfo`
- `0x180042686`: `ReadInterfaceExtraInfo`
- `0x18004276b`: `ReadInterfaceExtraInfo`
- `0x1800428d0`: `ReadInterfaceExtraInfo`
- `0x180042a52`: `ReadInterfaceExtraInfo`
- `0x180042aa4`: `ReadInterfaceExtraInfo`
- `0x180042b2b`: `ReadInterfaceExtraInfo`
- `0x180042691`: `%s: Registry key for routing domain ID is invalid`
- `0x180042580`: `VsidOrVlanTag`
- `0x1800425b0`: `VsidOrVlanTag`
- `0x1800425c7`: `%s: Registry key for %s is not valid %d`
- `0x18004266d`: `%s: Registry key for %s is not valid %d`
- `0x1800424ee`: `%s: ReadQoSPoliciesFromRegistry failed with error %d`
- `0x180042778`: `%s: Registry value for RadiusAttributeClass is not valid %d`
- `0x1800427c2`: `InitiateConfigPayload`
- `0x180042b16`: `InitiateConfigPayload`
- `0x180042b1d`: `%s: Registry value for %s is not valid %d`
- `0x1800428dd`: `%s: Invalid SourceIpAddress in the registry %d`
- `0x180042a59`: `%s: Invalid Value of S2S_PBK_INFO in Registry %d .`
- `0x180042aab`: `%s: Invalid Value of S2S_PBK_INFO in Registry %d .`

## pseudocode

```c
__int64 __fastcall ReadInterfaceExtraInfo(HKEY hKey, int a2, int a3, __int64 a4)
{
  unsigned int v8; // ebx
  int v10; // r15d
  LSTATUS v11; // eax
  __int64 v12; // rax
  unsigned int QoSPoliciesFromRegistry; // eax
  struct _UNICODE_STRING *v14; // r9
  LSTATUS v15; // eax
  struct _UNICODE_STRING *p_GuidString; // r9
  LSTATUS v17; // eax
  const WCHAR *v18; // r9
  const wchar_t *v19; // rdx
  unsigned int v20; // eax
  bool v21; // zf
  struct _UNICODE_STRING *v22; // r9
  unsigned int v23; // eax
  BYTE *v24; // rbx
  unsigned int v25; // eax
  unsigned int v26; // r12d
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPBYTE lpDataa; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  int v31; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v32[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  LPCWSTR Terminator; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+58h] [rbp-A8h] BYREF
  int v35; // [rsp+68h] [rbp-98h] BYREF
  __int128 v36; // [rsp+6Ch] [rbp-94h]
  __int128 v37; // [rsp+7Ch] [rbp-84h]
  int v38; // [rsp+8Ch] [rbp-74h]
  _WORD Data[40]; // [rsp+90h] [rbp-70h] BYREF
  BYTE v40[2]; // [rsp+E0h] [rbp-20h] BYREF
  int v41; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v42[2044]; // [rsp+154h] [rbp+54h] BYREF

  cbData = 0;
  Type = 0;
  memset_0(Data, 0, sizeof(Data));
  memset_0(v40, 0, 0x64u);
  Terminator = 0;
  v31 = 0;
  *(_DWORD *)v32 = 0;
  v41 = 0;
  memset_0(v42, 0, sizeof(v42));
  v35 = 0;
  v38 = 0;
  v36 = 0;
  v37 = 0;
  if ( !a4 || !hKey )
    return 87;
  memset_0((void *)a4, 0, 0x2C8u);
  v8 = IsModernStackEnabled(&v31);
  if ( v8 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      return v8;
    LOWORD(v41) = 0;
    FormatRRASErrorString(
      &v41,
      L"%s: IsModernStackEnabled returned an error.Exiting the function .",
      L"ReadInterfaceExtraInfo");
LABEL_6:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v41);
    return v8;
  }
  v10 = 1;
  if ( !a3 )
  {
    if ( a2 != 2 )
    {
      cbData = 4;
      return v8;
    }
    goto LABEL_22;
  }
  cbData = 80;
  v11 = RegQueryValueExW(hKey, L"RoutingDomainId", 0, &Type, (LPBYTE)Data, &cbData);
  if ( v11 != 2 )
  {
    if ( v11 || Type != 1 )
    {
      if ( !(_QWORD)xmmword_180078C50 )
        return 87;
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v41, L"%s: Registry key for routing domain ID is invalid", L"ReadInterfaceExtraInfo");
    }
    else
    {
      Data[39] = 0;
      GuidString = 0;
      v12 = -1;
      do
        ++v12;
      while ( Data[v12] );
      GuidString.MaximumLength = 2 * v12;
      GuidString.Length = 2 * v12;
      GuidString.Buffer = Data;
      if ( !RtlGUIDFromString(&GuidString, (GUID *)(a4 + 28)) )
      {
        if ( a2 == 2 )
          goto LABEL_22;
        goto LABEL_27;
      }
      if ( !(_QWORD)xmmword_180078C50 )
        return 87;
      LOWORD(v41) = 0;
      FormatRRASErrorString(
        &v41,
        L"%s: Failed to convert Routing domain ID from string to GUID format: %d",
        L"ReadInterfaceExtraInfo",
        87);
    }
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v41);
    return 87;
  }
  if ( a2 != 2 )
  {
LABEL_27:
    if ( a2 != 4 )
    {
      cbData = 4;
      v15 = RegQueryValueExW(hKey, L"VsidOrVlanTag", 0, &Type, (LPBYTE)(a4 + 44), &cbData);
      if ( v15 != 2 && (v15 || Type != 4) )
      {
        if ( (_QWORD)xmmword_180078C60 )
        {
          LOWORD(v41) = 0;
          LOWORD(v35) = 0;
          LODWORD(lpData) = v15;
          GuidString = (struct _UNICODE_STRING)GUID_NULL;
          FormatRRASErrorString(
            &v41,
            L"%s: Registry key for %s is not valid %d",
            L"ReadInterfaceExtraInfo",
            L"VsidOrVlanTag",
            lpData);
          p_GuidString = &GuidString;
          if ( a4 != -28 )
            p_GuidString = (struct _UNICODE_STRING *)(a4 + 28);
LABEL_104:
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _UNICODE_STRING *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180078C60,
            &v41,
            p_GuidString,
            0,
            &v35);
        }
        return 87;
      }
      cbData = 8;
      v17 = RegQueryValueExW(hKey, L"MultiTenantIfLuid", 0, &Type, (LPBYTE)(a4 + 48), &cbData);
      v8 = v17;
      if ( v17 == 2 )
        return 0;
      if ( v17 || Type != 3 )
      {
        if ( !(_QWORD)xmmword_180078C60 )
          return 87;
        v18 = L"MultiTenantIfLuid";
        v19 = L"%s: Registry key for %s is not valid %d";
        goto LABEL_101;
      }
      goto LABEL_54;
    }
LABEL_22:
    QoSPoliciesFromRegistry = ReadQoSPoliciesFromRegistry(hKey);
    v8 = QoSPoliciesFromRegistry;
    if ( QoSPoliciesFromRegistry )
    {
      if ( (_QWORD)xmmword_180078C60 )
      {
        LOWORD(v41) = 0;
        LOWORD(v35) = 0;
        GuidString = (struct _UNICODE_STRING)GUID_NULL;
        FormatRRASErrorString(
          &v41,
          L"%s: ReadQoSPoliciesFromRegistry failed with error %d",
          L"ReadInterfaceExtraInfo",
          QoSPoliciesFromRegistry);
        v14 = &GuidString;
        if ( a4 != -28 )
          v14 = (struct _UNICODE_STRING *)(a4 + 28);
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _UNICODE_STRING *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
          gCfgStoreEtwContext,
          xmmword_180078C60,
          &v41,
          v14,
          0,
          &v35);
      }
      return v8;
    }
    if ( a2 == 2 && a3 )
    {
      cbData = 514;
      memset_0((void *)(a4 + 56), 0, 0x202u);
      v20 = RegQueryValueExW(hKey, L"RadiusAttributeClass", 0, &Type, (LPBYTE)(a4 + 56), &cbData);
      v8 = v20;
      if ( v20 == 2 )
      {
        cbData = 4;
        goto LABEL_55;
      }
      if ( v20 || Type != 1 )
      {
        if ( !(_QWORD)xmmword_180078C60 )
          return 87;
        LOWORD(v41) = 0;
        LOWORD(v35) = 0;
        GuidString = (struct _UNICODE_STRING)GUID_NULL;
        FormatRRASErrorString(
          &v41,
          L"%s: Registry value for RadiusAttributeClass is not valid %d",
          L"ReadInterfaceExtraInfo",
          v20);
LABEL_102:
        p_GuidString = &GuidString;
        if ( a4 != -28 )
          p_GuidString = (struct _UNICODE_STRING *)(a4 + 28);
        goto LABEL_104;
      }
    }
LABEL_54:
    cbData = 4;
    if ( a2 != 2 )
      return v8;
LABEL_55:
    v17 = RegQueryValueExW(hKey, L"InitiateConfigPayload", 0, &Type, (LPBYTE)(a4 + 572), &cbData);
    if ( v17 == 2 )
    {
      *(_DWORD *)(a4 + 572) = 1;
    }
    else if ( v17 || Type != 4 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        return 87;
      v18 = L"InitiateConfigPayload";
      goto LABEL_100;
    }
    cbData = 100;
    *(_WORD *)(a4 + 576) = 0;
    v17 = RegQueryValueExW(hKey, L"SourceIpAddress", 0, &Type, v40, &cbData);
    v8 = v17;
    if ( v17 == 2 )
    {
      v8 = 0;
      goto LABEL_63;
    }
    if ( !v17 && Type == 1 )
    {
LABEL_63:
      if ( *(_WORD *)v40 )
      {
        v8 = RtlIpv4StringToAddressW((PCWSTR)v40, 1u, &Terminator, (struct in_addr *)(a4 + 580));
        if ( v8 )
        {
          v8 = RtlIpv6StringToAddressW((PCWSTR)v40, &Terminator, (struct in6_addr *)(a4 + 580));
          if ( v8 )
          {
            v21 = (_QWORD)xmmword_180078C60 == 0;
            v8 = 87;
            *(_WORD *)(a4 + 576) = 0;
            if ( !v21 )
            {
              LOWORD(v41) = 0;
              LOWORD(v35) = 0;
              GuidString = (struct _UNICODE_STRING)GUID_NULL;
              FormatRRASErrorString(
                &v41,
                L"%s: Invalid SourceIpAddress in the registry %d",
                L"ReadInterfaceExtraInfo",
                87);
              v22 = &GuidString;
              if ( a4 != -28 )
                v22 = (struct _UNICODE_STRING *)(a4 + 28);
              ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, struct _UNICODE_STRING *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
                gCfgStoreEtwContext,
                xmmword_180078C60,
                &v41,
                v22,
                0,
                &v35);
            }
          }
          else
          {
            *(_WORD *)(a4 + 576) = 23;
          }
        }
        else
        {
          *(_WORD *)(a4 + 576) = 2;
        }
      }
      if ( !v31 )
        goto LABEL_93;
      cbData = 0;
      v23 = RegQueryValueExW(hKey, L"InterfaceInfoPbk", 0, &Type, 0, &cbData);
      v8 = v23;
      if ( v23 != 2 )
      {
        if ( v23 || Type != 3 || !cbData )
        {
          if ( !(_QWORD)xmmword_180078C50 )
            return v8;
          LOWORD(v41) = 0;
          FormatRRASErrorString(
            &v41,
            L"%s: Invalid Value of S2S_PBK_INFO in Registry %d .",
            L"ReadInterfaceExtraInfo",
            v23);
          goto LABEL_6;
        }
        v24 = (BYTE *)malloc(cbData);
        if ( !v24 )
          return 8;
        v25 = RegQueryValueExW(hKey, L"InterfaceInfoPbk", 0, &Type, v24, &cbData);
        v26 = v25;
        if ( v25 || Type != 3 )
        {
          if ( (_QWORD)xmmword_180078C50 )
          {
            LOWORD(v41) = 0;
            FormatRRASErrorString(
              &v41,
              L"%s: Invalid Value of S2S_PBK_INFO in Registry %d .",
              L"ReadInterfaceExtraInfo",
              v25);
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
              gCfgStoreEtwContext,
              xmmword_180078C50,
              &v41);
          }
        }
        else
        {
          v26 = ConvertPbkRegistryEntryToPbkInfo(
                  (struct _S2S_PBK_REGISTRY_INFO *)v24,
                  (struct _DIM_INTERFACE_OBJECT_EXTRA_INFO *)a4);
          free(v24);
          if ( !v26 )
            goto LABEL_82;
        }
        return v26;
      }
LABEL_82:
      cbData = 4;
      v17 = RegQueryValueExW(hKey, L"AutoConnectEnabled", 0, &Type, v32, &cbData);
      v8 = v17;
      if ( v17 == 2 )
      {
        v8 = 0;
        goto LABEL_94;
      }
      if ( v17 || Type != 4 )
      {
        if ( !(_QWORD)xmmword_180078C60 )
          return 87;
        v18 = L"AutoConnectEnabled";
        goto LABEL_100;
      }
LABEL_93:
      if ( *(_DWORD *)v32 )
      {
LABEL_95:
        *(_DWORD *)(a4 + 704) = v10;
        return v8;
      }
LABEL_94:
      v10 = 0;
      goto LABEL_95;
    }
    if ( !(_QWORD)xmmword_180078C60 )
      return 87;
    v18 = L"SourceIpAddress";
LABEL_100:
    v19 = L"%s: Registry value for %s is not valid %d";
LABEL_101:
    LODWORD(lpDataa) = v17;
    LOWORD(v35) = 0;
    GuidString = (struct _UNICODE_STRING)GUID_NULL;
    LOWORD(v41) = 0;
    FormatRRASErrorString(&v41, v19, L"ReadInterfaceExtraInfo", v18, lpDataa);
    goto LABEL_102;
  }
  if ( (_QWORD)xmmword_180078C50 )
  {
    LOWORD(v41) = 0;
    FormatRRASErrorString(&v41, L"%s: Routing domain ID key is absent for S2S interface.", L"ReadInterfaceExtraInfo");
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v41);
  }
  return 2;
}

```

## disassembly

```asm
0x180042268  mov     [rsp-8+arg_8], rbx
0x18004226d  push    rbp
0x18004226e  push    rsi
0x18004226f  push    rdi
0x180042270  push    r12
0x180042272  push    r13
0x180042274  push    r14
0x180042276  push    r15
0x180042278  lea     rbp, [rsp-860h]
0x180042280  sub     rsp, 960h
0x180042287  mov     rax, cs:__security_cookie
0x18004228e  xor     rax, rsp
0x180042291  mov     [rbp+890h+var_40], rax
0x180042298  xor     esi, esi
0x18004229a  mov     r13d, r8d
0x18004229d  mov     r12d, edx
0x1800422a0  mov     [rsp+990h+cbData], esi
0x1800422a4  mov     r14, rcx
0x1800422a7  mov     [rsp+990h+Type], esi
0x1800422ab  xor     edx, edx; Val
0x1800422ad  lea     rcx, [rbp+890h+Data]; void *
0x1800422b1  lea     r8d, [rsi+50h]; Size
0x1800422b5  mov     rdi, r9
0x1800422b8  call    memset_0
0x1800422bd  xor     edx, edx; Val
0x1800422bf  lea     r8d, [rsi+64h]; Size
0x1800422c3  lea     rcx, [rbp+890h+var_8B0]; void *
0x1800422c7  call    memset_0
0x1800422cc  xor     edx, edx; Val
0x1800422ce  mov     [rsp+990h+Terminator], rsi
0x1800422d3  mov     r8d, 7FCh; Size
0x1800422d9  mov     [rsp+990h+var_948], esi
0x1800422dd  lea     rcx, [rbp+890h+var_83C]; void *
0x1800422e1  mov     dword ptr [rsp+990h+var_944], esi
0x1800422e5  mov     [rbp+890h+var_840], esi
0x1800422e8  call    memset_0
0x1800422ed  xor     eax, eax
0x1800422ef  mov     [rsp+990h+var_928], esi
0x1800422f3  mov     [rbp+890h+var_904], eax
0x1800422f6  xorps   xmm0, xmm0
0x1800422f9  movups  [rsp+990h+var_924], xmm0
0x1800422fe  movups  [rsp+990h+var_914], xmm0
0x180042303  test    rdi, rdi
0x180042306  jz      loc_180042B8D
0x18004230c  test    r14, r14
0x18004230f  jz      loc_180042B8D
0x180042315  xor     edx, edx; Val
0x180042317  mov     r8d, 2C8h; Size
0x18004231d  mov     rcx, rdi; void *
0x180042320  call    memset_0
0x180042325  lea     rcx, [rsp+990h+var_948]; int *
0x18004232a  call    IsModernStackEnabled
0x18004232f  mov     ebx, eax
0x180042331  test    eax, eax
0x180042333  jz      short loc_18004237E
0x180042335  cmp     qword ptr cs:xmmword_180078C50, rsi
0x18004233c  jz      short loc_180042377
0x18004233e  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x180042345  mov     word ptr [rbp+890h+var_840], si
0x180042349  lea     rdx, aSIsmodernstack; "%s: IsModernStackEnabled returned an er"...
0x180042350  lea     rcx, [rbp+890h+var_840]
0x180042354  call    FormatRRASErrorString
0x180042359  mov     rdx, qword ptr cs:xmmword_180078C50
0x180042360  lea     r8, [rbp+890h+var_840]
0x180042364  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004236b  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180042372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042377  mov     eax, ebx
0x180042379  jmp     loc_180042B92
0x18004237e  mov     r15d, 1
0x180042384  test    r13d, r13d
0x180042387  jz      loc_1800426C4
0x18004238d  lea     rax, [rsp+990h+cbData]
0x180042392  mov     [rsp+990h+cbData], 50h ; 'P'
0x18004239a  mov     [rsp+990h+lpcbData], rax; lpcbData
0x18004239f  lea     r9, [rsp+990h+Type]; lpType
0x1800423a4  lea     rax, [rbp+890h+Data]
0x1800423a8  xor     r8d, r8d; lpReserved
0x1800423ab  lea     rdx, aRoutingdomaini; "RoutingDomainId"
0x1800423b2  mov     [rsp+990h+lpData], rax; lpData
0x1800423b7  mov     rcx, r14; hKey
0x1800423ba  call    cs:__imp_RegQueryValueExW
0x1800423c0  lea     esi, [r15+1]
0x1800423c4  cmp     eax, esi
0x1800423c6  jnz     short loc_18004241C
0x1800423c8  cmp     r12d, esi
0x1800423cb  jnz     loc_18004254B
0x1800423d1  xor     ecx, ecx
0x1800423d3  cmp     qword ptr cs:xmmword_180078C50, rcx
0x1800423da  jz      short loc_180042415
0x1800423dc  mov     word ptr [rbp+890h+var_840], cx
0x1800423e0  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x1800423e7  lea     rcx, [rbp+890h+var_840]
0x1800423eb  lea     rdx, aSRoutingDomain_0; "%s: Routing domain ID key is absent for"...
0x1800423f2  call    FormatRRASErrorString
0x1800423f7  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800423fe  lea     r8, [rbp+890h+var_840]
0x180042402  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042409  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180042410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042415  mov     eax, esi
0x180042417  jmp     loc_180042B92
0x18004241c  xor     ebx, ebx
0x18004241e  test    eax, eax
0x180042420  jnz     loc_180042679
0x180042426  cmp     [rsp+990h+Type], r15d
0x18004242b  jnz     loc_180042679
0x180042431  xorps   xmm0, xmm0
0x180042434  mov     [rbp+890h+var_8B2], bx
0x180042438  movups  xmmword ptr [rsp+990h+GuidString.Length], xmm0
0x18004243d  lea     rcx, [rbp+890h+Data]
0x180042441  or      rax, 0FFFFFFFFFFFFFFFFh
0x180042445  inc     rax
0x180042448  cmp     [rcx+rax*2], bx
0x18004244c  jnz     short loc_180042445
0x18004244e  add     ax, ax
0x180042451  lea     rdx, [rdi+1Ch]; Guid
0x180042455  mov     [rsp+990h+GuidString.MaximumLength], ax
0x18004245a  lea     rcx, [rsp+990h+GuidString]; GuidString
0x18004245f  mov     [rsp+990h+GuidString.Length], ax
0x180042464  lea     rax, [rbp+890h+Data]
0x180042468  mov     [rsp+990h+GuidString.Buffer], rax
0x18004246d  call    cs:__imp_RtlGUIDFromString
0x180042473  test    eax, eax
0x180042475  jz      short loc_1800424AA
0x180042477  cmp     qword ptr cs:xmmword_180078C50, rbx
0x18004247e  jz      loc_180042B8D
0x180042484  mov     r9d, 57h ; 'W'
0x18004248a  mov     word ptr [rbp+890h+var_840], bx
0x18004248e  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x180042495  lea     rdx, aSFailedToConve_0; "%s: Failed to convert Routing domain ID"...
0x18004249c  lea     rcx, [rbp+890h+var_840]
0x1800424a0  call    FormatRRASErrorString
0x1800424a5  jmp     loc_1800426A1
0x1800424aa  cmp     r12d, esi
0x1800424ad  jnz     loc_18004254D
0x1800424b3  mov     rdx, rdi
0x1800424b6  mov     rcx, r14; hKey
0x1800424b9  call    ReadQoSPoliciesFromRegistry
0x1800424be  xor     ecx, ecx
0x1800424c0  mov     ebx, eax
0x1800424c2  test    eax, eax
0x1800424c4  jz      loc_1800426DF
0x1800424ca  cmp     qword ptr cs:xmmword_180078C60, rcx
0x1800424d1  jz      loc_180042377
0x1800424d7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800424de  mov     word ptr [rbp+890h+var_840], cx
0x1800424e2  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x1800424e9  mov     word ptr [rsp+990h+var_928], cx
0x1800424ee  lea     rdx, aSReadqospolici_0; "%s: ReadQoSPoliciesFromRegistry failed "...
0x1800424f5  mov     r9d, eax
0x1800424f8  lea     rcx, [rbp+890h+var_840]
0x1800424fc  movdqu  xmmword ptr [rsp+990h+GuidString.Length], xmm0
0x180042502  call    FormatRRASErrorString
0x180042507  mov     rdx, qword ptr cs:xmmword_180078C60
0x18004250e  lea     rax, [rdi+1Ch]
0x180042512  xor     ecx, ecx
0x180042514  lea     r9, [rsp+990h+GuidString]
0x180042519  test    rax, rax
0x18004251c  lea     r8, [rbp+890h+var_840]
0x180042520  cmovnz  r9, rax
0x180042524  lea     rax, [rsp+990h+var_928]
0x180042529  mov     [rsp+990h+lpcbData], rax
0x18004252e  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180042535  mov     [rsp+990h+lpData], rcx
0x18004253a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180042541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042546  jmp     loc_180042377
0x18004254b  xor     ebx, ebx
0x18004254d  cmp     r12d, 4
0x180042551  jz      loc_1800424B3
0x180042557  lea     rcx, [rsp+990h+cbData]
0x18004255c  mov     r13d, 4
0x180042562  mov     [rsp+990h+lpcbData], rcx; lpcbData
0x180042567  lea     rax, [rdi+2Ch]
0x18004256b  mov     rcx, r14; hKey
0x18004256e  mov     [rsp+990h+cbData], r13d
0x180042573  lea     r9, [rsp+990h+Type]; lpType
0x180042578  mov     [rsp+990h+lpData], rax; lpData
0x18004257d  xor     r8d, r8d; lpReserved
0x180042580  lea     rdx, aVsidorvlantag; "VsidOrVlanTag"
0x180042587  call    cs:__imp_RegQueryValueExW
0x18004258d  cmp     eax, esi
0x18004258f  jz      short loc_180042605
0x180042591  test    eax, eax
0x180042593  jnz     short loc_18004259C
0x180042595  cmp     [rsp+990h+Type], r13d
0x18004259a  jz      short loc_180042605
0x18004259c  cmp     qword ptr cs:xmmword_180078C60, rbx
0x1800425a3  jz      loc_180042B8D
0x1800425a9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800425b0  lea     r9, aVsidorvlantag; "VsidOrVlanTag"
0x1800425b7  mov     word ptr [rbp+890h+var_840], bx
0x1800425bb  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x1800425c2  mov     word ptr [rsp+990h+var_928], bx
0x1800425c7  lea     rdx, aSRegistryKeyFo_0; "%s: Registry key for %s is not valid %d"
0x1800425ce  mov     dword ptr [rsp+990h+lpData], eax
0x1800425d2  lea     rcx, [rbp+890h+var_840]
0x1800425d6  movdqu  xmmword ptr [rsp+990h+GuidString.Length], xmm0
0x1800425dc  call    FormatRRASErrorString
0x1800425e1  lea     rax, [rdi+1Ch]
0x1800425e5  test    rax, rax
0x1800425e8  lea     r9, [rsp+990h+GuidString]
0x1800425ed  cmovnz  r9, rax
0x1800425f1  lea     rax, [rsp+990h+var_928]
0x1800425f6  mov     [rsp+990h+lpcbData], rax
0x1800425fb  mov     [rsp+990h+lpData], rbx
0x180042600  jmp     loc_180042B6F
0x180042605  lea     rcx, [rsp+990h+cbData]
0x18004260a  mov     [rsp+990h+cbData], 8
0x180042612  mov     [rsp+990h+lpcbData], rcx; lpcbData
0x180042617  lea     rax, [rdi+30h]
0x18004261b  mov     rcx, r14; hKey
0x18004261e  mov     [rsp+990h+lpData], rax; lpData
0x180042623  lea     r9, [rsp+990h+Type]; lpType
0x180042628  xor     r8d, r8d; lpReserved
0x18004262b  lea     rdx, aMultitenantifl; "MultiTenantIfLuid"
0x180042632  call    cs:__imp_RegQueryValueExW
0x180042638  mov     ebx, eax
0x18004263a  cmp     eax, esi
0x18004263c  jnz     short loc_180042647
0x18004263e  xor     ecx, ecx
0x180042640  mov     ebx, ecx
0x180042642  jmp     loc_180042377
0x180042647  xor     r13d, r13d
0x18004264a  test    eax, eax
0x18004264c  jnz     short loc_180042659
0x18004264e  cmp     [rsp+990h+Type], 3
0x180042653  jz      loc_180042793
0x180042659  cmp     qword ptr cs:xmmword_180078C60, r13
0x180042660  jz      loc_180042B8D
0x180042666  lea     r9, aMultitenantifl; "MultiTenantIfLuid"
0x18004266d  lea     rdx, aSRegistryKeyFo_0; "%s: Registry key for %s is not valid %d"
0x180042674  jmp     loc_180042B24
0x180042679  cmp     qword ptr cs:xmmword_180078C50, rbx
0x180042680  jz      loc_180042B8D
0x180042686  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x18004268d  mov     word ptr [rbp+890h+var_840], bx
0x180042691  lea     rdx, aSRegistryKeyFo; "%s: Registry key for routing domain ID "...
0x180042698  lea     rcx, [rbp+890h+var_840]
0x18004269c  call    FormatRRASErrorString
0x1800426a1  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800426a8  lea     r8, [rbp+890h+var_840]
0x1800426ac  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800426b3  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800426ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800426bf  jmp     loc_180042B8D
0x1800426c4  mov     esi, 2
0x1800426c9  cmp     r12d, esi
0x1800426cc  jz      loc_1800424B3
0x1800426d2  mov     [rsp+990h+cbData], 4
0x1800426da  jmp     loc_180042377
0x1800426df  cmp     r12d, esi
0x1800426e2  jnz     loc_180042793
0x1800426e8  test    r13d, r13d
0x1800426eb  jz      loc_180042793
0x1800426f1  mov     r8d, 202h; Size
0x1800426f7  lea     rbx, [rdi+38h]
0x1800426fb  mov     rcx, rbx; void *
0x1800426fe  mov     [rsp+990h+cbData], r8d
0x180042703  xor     edx, edx; Val
0x180042705  call    memset_0
0x18004270a  lea     rax, [rsp+990h+cbData]
0x18004270f  xor     r8d, r8d; lpReserved
0x180042712  mov     [rsp+990h+lpcbData], rax; lpcbData
0x180042717  lea     r9, [rsp+990h+Type]; lpType
0x18004271c  lea     rdx, aRadiusattribut; "RadiusAttributeClass"
0x180042723  mov     [rsp+990h+lpData], rbx; lpData
0x180042728  mov     rcx, r14; hKey
0x18004272b  call    cs:__imp_RegQueryValueExW
0x180042731  mov     ebx, eax
0x180042733  cmp     eax, esi
0x180042735  jnz     short loc_180042741
0x180042737  mov     [rsp+990h+cbData], 4
0x18004273f  jmp     short loc_1800427A4
0x180042741  xor     r13d, r13d
0x180042744  test    eax, eax
0x180042746  jnz     short loc_18004274F
0x180042748  cmp     [rsp+990h+Type], r15d
0x18004274d  jz      short loc_180042793
0x18004274f  cmp     qword ptr cs:xmmword_180078C60, r13
0x180042756  jz      loc_180042B8D
0x18004275c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180042763  mov     r9d, eax
0x180042766  mov     word ptr [rbp+890h+var_840], r13w
0x18004276b  lea     r8, aReadinterfacee; "ReadInterfaceExtraInfo"
0x180042772  mov     word ptr [rsp+990h+var_928], r13w
0x180042778  lea     rdx, aSRegistryValue; "%s: Registry value for RadiusAttributeC"...
0x18004277f  lea     rcx, [rbp+890h+var_840]
0x180042783  movdqu  xmmword ptr [rsp+990h+GuidString.Length], xmm0
0x180042789  call    FormatRRASErrorString
0x18004278e  jmp     loc_180042B50
0x180042793  mov     [rsp+990h+cbData], 4
0x18004279b  cmp     r12d, esi
0x18004279e  jnz     loc_180042377
0x1800427a4  lea     rax, [rsp+990h+cbData]
0x1800427a9  xor     r8d, r8d; lpReserved
0x1800427ac  mov     [rsp+990h+lpcbData], rax; lpcbData
0x1800427b1  lea     rbx, [rdi+23Ch]
0x1800427b8  lea     r9, [rsp+990h+Type]; lpType
  ... truncated ...
```
