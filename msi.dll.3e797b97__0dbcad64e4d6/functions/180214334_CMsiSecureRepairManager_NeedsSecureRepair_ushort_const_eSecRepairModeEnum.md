# CMsiSecureRepairManager::NeedsSecureRepair(ushort const *,eSecRepairModeEnum &)

- ea: `0x180214334`
- end: `0x1802148d2`
- name: `?NeedsSecureRepair@CMsiSecureRepairManager@@SA_NPEBGAEAW4eSecRepairModeEnum@@@Z`
- size: `1438`
- prototype: `bool __fastcall(const unsigned __int16 *, enum eSecRepairModeEnum *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800be418`
- `0x18017d490`

## callees

- `0x1800012d8`
- `0x1800013ac`
- `0x18000c4bc`
- `0x180040908`
- `0x18008c93c`
- `0x1802142a4`
- `0x180214334`
- `0x1802154b0`
- `0x1802154ec`
- `0x180266010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1802143cc`
- `ADVAPI32!RegQueryValueExW` at `0x18021443d`
- `ADVAPI32!RegQueryValueExW` at `0x1802144c5`
- `ADVAPI32!RegQueryValueExW` at `0x180214586`
- `ADVAPI32!RegQueryValueExW` at `0x1802147b3`
- `ADVAPI32!RegQueryValueExW` at `0x1802143cc`
- `ADVAPI32!RegQueryValueExW` at `0x18021443d`
- `ADVAPI32!RegQueryValueExW` at `0x1802144c5`
- `ADVAPI32!RegQueryValueExW` at `0x180214586`
- `ADVAPI32!RegQueryValueExW` at `0x1802147b3`
- `ADVAPI32!RegCloseKey` at `0x180214871`
- `ADVAPI32!RegCloseKey` at `0x18021488a`
- `ADVAPI32!RegCloseKey` at `0x180214871`
- `ADVAPI32!RegCloseKey` at `0x18021488a`

## string_xrefs

- `0x18021437f`: `SOFTWARE\Policies\Microsoft\Windows\Installer`
- `0x1802143b0`: `SecureRepairPolicy`
- `0x180214461`: `SECREPAIR:  Block Behaviour for repair using AllowList registry is set`
- `0x180214658`: `SOFTWARE\Policies\Microsoft\Windows\Installer\SecureRepairAllowList`
- `0x180214507`: `SECREPAIR:  Block Behaviour for repair using old AllowList registry is set`
- `0x1802145c4`: `SECREPAIR:  Block Behaviour for repair using old AllowList registry is set`
- `0x1802146dc`: `SOFTWARE\Policies\Microsoft\Windows\Installer\SecureRepairWhiteList`
- `0x18021476c`: `SOFTWARE\Policies\Microsoft\Windows\Installer\SecureRepairWhiteList`
- `0x180214688`: `SECREPAIR: product found in AllowList registry: %s`
- `0x180214756`: `SECREPAIR: product found in old registry: %s`
- `0x180214830`: `SECREPAIR: product found in old registry: %s`

## pseudocode

```c
char __fastcall CMsiSecureRepairManager::NeedsSecureRepair(const unsigned __int16 *a1, enum eSecRepairModeEnum *a2)
{
  unsigned int v3; // r8d
  char v4; // bl
  char v5; // r14
  bool v6; // si
  __int64 v7; // rcx
  __int64 v8; // rcx
  unsigned int v9; // r8d
  const WCHAR *v10; // rax
  const unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // r9
  const WCHAR *v13; // rax
  __int64 v14; // rcx
  const WCHAR *v15; // rax
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rax
  __int64 v19; // [rsp+60h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-18h] BYREF
  HKEY v21; // [rsp+70h] [rbp-10h] BYREF
  int Data; // [rsp+C0h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+C8h] [rbp+48h] BYREF

  cbData = 4;
  hKey = 0;
  v21 = 0;
  Data = 0;
  MsiString::MsiString((MsiString *)&v19, a1);
  v4 = 1;
  if ( MsiRegOpen64bitKey(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\Windows\\Installer", v3, 0x20019u, &hKey) )
    goto LABEL_63;
  v5 = 0;
  v6 = 0;
  if ( !RegQueryValueExW(hKey, L"SecureRepairPolicy", 0, 0, (LPBYTE)&Data, &cbData) )
  {
    if ( !Data )
    {
      *(_DWORD *)a2 = 1;
      goto LABEL_60;
    }
    if ( Data == 1 )
    {
      v5 = 1;
      goto LABEL_60;
    }
    if ( Data != 2 )
    {
      *(_DWORD *)a2 = 0;
      goto LABEL_60;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::GetImpl'::`2'::impl) )
    {
      if ( !RegQueryValueExW(hKey, L"BlockBehaviourWithAllowList", 0, 0, (LPBYTE)&Data, &cbData) && !Data )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR:  Block Behaviour for repair using AllowList registry is set",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        *(_DWORD *)a2 = 1;
      }
      if ( *(_DWORD *)a2 != 1
        && !RegQueryValueExW(hKey, L"BlockBehaviourWithWhiteList", 0, 0, (LPBYTE)&Data, &cbData)
        && !Data )
      {
        *(_DWORD *)a2 = 1;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl'::`2'::impl) )
        {
          if ( g_dmDiagnosticMode )
            DebugString(
              9,
              0,
              0,
              L"SECREPAIR:  Block Behaviour for repair using old AllowList registry is set",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              L"(NULL)",
              0,
              0);
          if ( !byte_180314589 )
          {
            if ( (unsigned int)dword_18030F8D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18030F8D0) )
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                v7,
                byte_1802FE07B);
LABEL_32:
            byte_180314589 = 1;
          }
        }
      }
    }
    else if ( !RegQueryValueExW(hKey, L"BlockBehaviourWithWhiteList", 0, 0, (LPBYTE)&Data, &cbData) && !Data )
    {
      *(_DWORD *)a2 = 1;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl'::`2'::impl) )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"SECREPAIR:  Block Behaviour for repair using old AllowList registry is set",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        if ( !byte_180314589 )
        {
          if ( (unsigned int)dword_18030F8D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18030F8D0) )
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
              v8,
              qword_1802FE048);
          goto LABEL_32;
        }
      }
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::GetImpl'::`2'::impl) )
    {
      if ( !MsiRegOpen64bitKey(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\\SecureRepairWhiteList",
              v9,
              0x20019u,
              &v21) )
      {
        v15 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
        if ( !RegQueryValueExW(v21, v15, 0, 0, 0, 0) )
        {
          v6 = 1;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl'::`2'::impl) )
          {
            if ( !byte_180314588 )
            {
              if ( (unsigned int)dword_18030F8D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18030F8D0) )
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  v16,
                  byte_1802FE01D);
              if ( g_dmDiagnosticMode )
              {
                v17 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
                DebugString(
                  9,
                  0,
                  0,
                  L"SECREPAIR: product found in old registry: %s",
                  v17,
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  L"(NULL)",
                  0,
                  0);
              }
              byte_180314588 = 1;
            }
          }
        }
        RegCloseKey(v21);
      }
      goto LABEL_60;
    }
    v10 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
    v6 = IsProductInSecureRepairList(L"SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\\SecureRepairAllowList", v10);
    if ( v6 )
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_60;
      v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
      v12 = L"SECREPAIR: product found in AllowList registry: %s";
    }
    else
    {
      v13 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
      v6 = IsProductInSecureRepairList(L"SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\\SecureRepairWhiteList", v13);
      if ( !v6 )
        goto LABEL_60;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl'::`2'::impl)
        && !byte_180314588 )
      {
        if ( (unsigned int)dword_18030F8D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18030F8D0) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v14,
            word_1802FDFF2);
        byte_180314588 = 1;
      }
      if ( !g_dmDiagnosticMode )
        goto LABEL_60;
      v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 80LL))(v19);
      v12 = L"SECREPAIR: product found in old registry: %s";
    }
    DebugString(9, 0, 0, v12, v11, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
  }
LABEL_60:
  RegCloseKey(hKey);
  if ( v6 || v5 )
    v4 = 0;
LABEL_63:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return v4;
}

```

## disassembly

```asm
0x180214334  mov     [rsp-28h+arg_0], rbx
0x180214339  mov     [rsp-28h+arg_8], rsi
0x18021433e  push    rbp
0x18021433f  push    rdi
0x180214340  push    r12
0x180214342  push    r14
0x180214344  push    r15
0x180214346  mov     rbp, rsp
0x180214349  sub     rsp, 80h
0x180214350  xor     r15d, r15d
0x180214353  mov     [rbp+cbData], 4
0x18021435a  mov     rdi, rdx
0x18021435d  mov     [rbp+hKey], r15
0x180214361  mov     rdx, rcx; unsigned __int16 *
0x180214364  mov     [rbp+var_10], r15
0x180214368  lea     rcx, [rbp+var_20]; this
0x18021436c  mov     [rbp+Data], r15d
0x180214370  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x180214375  lea     rax, [rbp+hKey]
0x180214379  mov     r9d, 20019h; unsigned int
0x18021437f  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180214386  mov     [rsp+80h+lpData], rax; HKEY *
0x18021438b  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180214392  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180214397  lea     ebx, [r15+1]
0x18021439b  test    eax, eax
0x18021439d  jnz     loc_1802148A3
0x1802143a3  mov     rcx, [rbp+hKey]; hKey
0x1802143a7  lea     rax, [rbp+cbData]
0x1802143ab  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1802143b0  lea     rdx, aSecurerepairpo; "SecureRepairPolicy"
0x1802143b7  lea     rax, [rbp+Data]
0x1802143bb  xor     r9d, r9d; lpType
0x1802143be  xor     r8d, r8d; lpReserved
0x1802143c1  mov     [rsp+80h+lpData], rax; lpData
0x1802143c6  mov     r14b, r15b
0x1802143c9  mov     sil, r15b
0x1802143cc  call    cs:__imp_RegQueryValueExW
0x1802143d3  nop     dword ptr [rax+rax+00h]
0x1802143d8  test    eax, eax
0x1802143da  jnz     loc_180214886
0x1802143e0  mov     eax, [rbp+Data]
0x1802143e3  test    eax, eax
0x1802143e5  jz      loc_180214884
0x1802143eb  sub     eax, ebx
0x1802143ed  jz      loc_18021487F
0x1802143f3  sub     eax, ebx
0x1802143f5  jz      short loc_1802143FF
0x1802143f7  mov     [rdi], r15d
0x1802143fa  jmp     loc_180214886
0x1802143ff  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::GetImpl(void)'::`2'::impl
0x180214406  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::__private_IsEnabled(void)
0x18021440b  mov     rcx, [rbp+hKey]; hKey
0x18021440f  lea     r12, aNull; "(NULL)"
0x180214416  xor     r9d, r9d; lpType
0x180214419  xor     r8d, r8d; lpReserved
0x18021441c  test    al, al
0x18021441e  lea     rax, [rbp+cbData]
0x180214422  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180214427  lea     rax, [rbp+Data]
0x18021442b  mov     [rsp+80h+lpData], rax; lpData
0x180214430  jz      loc_18021457F
0x180214436  lea     rdx, aBlockbehaviour; "BlockBehaviourWithAllowList"
0x18021443d  call    cs:__imp_RegQueryValueExW
0x180214444  nop     dword ptr [rax+rax+00h]
0x180214449  test    eax, eax
0x18021444b  jnz     short loc_18021449A
0x18021444d  cmp     [rbp+Data], r15d
0x180214451  jnz     short loc_18021449A
0x180214453  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18021445a  jz      short loc_180214498
0x18021445c  mov     [rsp+80h+var_28], r15; void *
0x180214461  lea     r9, aSecrepairBlock; "SECREPAIR:  Block Behaviour for repair "...
0x180214468  mov     [rsp+80h+var_30], r15d; unsigned int
0x18021446d  lea     ecx, [rax+9]; int
0x180214470  mov     [rsp+80h+var_38], r12; unsigned __int16 *
0x180214475  xor     edx, edx; unsigned __int16
0x180214477  mov     [rsp+80h+var_40], r12; unsigned __int16 *
0x18021447c  xor     r8d, r8d; int
0x18021447f  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x180214484  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x180214489  mov     [rsp+80h+lpcbData], r12; unsigned __int16 *
0x18021448e  mov     [rsp+80h+lpData], r12; unsigned __int16 *
0x180214493  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180214498  mov     [rdi], ebx
0x18021449a  cmp     [rdi], ebx
0x18021449c  jz      loc_180214631
0x1802144a2  mov     rcx, [rbp+hKey]; hKey
0x1802144a6  lea     rax, [rbp+cbData]
0x1802144aa  mov     [rsp+80h+lpcbData], rax; lpcbData
0x1802144af  lea     rdx, aBlockbehaviour_0; "BlockBehaviourWithWhiteList"
0x1802144b6  lea     rax, [rbp+Data]
0x1802144ba  xor     r9d, r9d; lpType
0x1802144bd  xor     r8d, r8d; lpReserved
0x1802144c0  mov     [rsp+80h+lpData], rax; lpData
0x1802144c5  call    cs:__imp_RegQueryValueExW
0x1802144cc  nop     dword ptr [rax+rax+00h]
0x1802144d1  test    eax, eax
0x1802144d3  jnz     loc_180214631
0x1802144d9  cmp     [rbp+Data], r15d
0x1802144dd  jnz     loc_180214631
0x1802144e3  mov     [rdi], ebx
0x1802144e5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl(void)'::`2'::impl
0x1802144ec  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(void)
0x1802144f1  test    al, al
0x1802144f3  jz      loc_180214631
0x1802144f9  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x180214500  jz      short loc_18021453E
0x180214502  mov     [rsp+80h+var_28], r15; void *
0x180214507  lea     r9, aSecrepairBlock_0; "SECREPAIR:  Block Behaviour for repair "...
0x18021450e  mov     [rsp+80h+var_30], r15d; unsigned int
0x180214513  xor     edx, edx; unsigned __int16
0x180214515  mov     [rsp+80h+var_38], r12; unsigned __int16 *
0x18021451a  xor     r8d, r8d; int
0x18021451d  mov     [rsp+80h+var_40], r12; unsigned __int16 *
0x180214522  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x180214527  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x18021452c  lea     ecx, [rdx+9]; int
0x18021452f  mov     [rsp+80h+lpcbData], r12; unsigned __int16 *
0x180214534  mov     [rsp+80h+lpData], r12; unsigned __int16 *
0x180214539  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18021453e  cmp     cs:byte_180314589, r15b
0x180214545  jnz     loc_180214631
0x18021454b  mov     eax, cs:dword_18030F8D0
0x180214551  cmp     eax, 4
0x180214554  jbe     loc_18021462B
0x18021455a  lea     rcx, dword_18030F8D0
0x180214561  call    _tlgKeywordOn
0x180214566  test    al, al
0x180214568  jz      loc_18021462B
0x18021456e  lea     rdx, byte_1802FE07B
0x180214575  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18021457a  jmp     loc_18021462B
0x18021457f  lea     rdx, aBlockbehaviour_0; "BlockBehaviourWithWhiteList"
0x180214586  call    cs:__imp_RegQueryValueExW
0x18021458d  nop     dword ptr [rax+rax+00h]
0x180214592  test    eax, eax
0x180214594  jnz     loc_180214631
0x18021459a  cmp     [rbp+Data], r15d
0x18021459e  jnz     loc_180214631
0x1802145a4  mov     [rdi], ebx
0x1802145a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl(void)'::`2'::impl
0x1802145ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(void)
0x1802145b2  test    al, al
0x1802145b4  jz      short loc_180214631
0x1802145b6  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x1802145bd  jz      short loc_1802145FB
0x1802145bf  mov     [rsp+80h+var_28], r15; void *
0x1802145c4  lea     r9, aSecrepairBlock_0; "SECREPAIR:  Block Behaviour for repair "...
0x1802145cb  mov     [rsp+80h+var_30], r15d; unsigned int
0x1802145d0  xor     edx, edx; unsigned __int16
0x1802145d2  mov     [rsp+80h+var_38], r12; unsigned __int16 *
0x1802145d7  xor     r8d, r8d; int
0x1802145da  mov     [rsp+80h+var_40], r12; unsigned __int16 *
0x1802145df  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x1802145e4  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x1802145e9  lea     ecx, [rdx+9]; int
0x1802145ec  mov     [rsp+80h+lpcbData], r12; unsigned __int16 *
0x1802145f1  mov     [rsp+80h+lpData], r12; unsigned __int16 *
0x1802145f6  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1802145fb  cmp     cs:byte_180314589, r15b
0x180214602  jnz     short loc_180214631
0x180214604  mov     eax, cs:dword_18030F8D0
0x18021460a  cmp     eax, 4
0x18021460d  jbe     short loc_18021462B
0x18021460f  lea     rcx, dword_18030F8D0
0x180214616  call    _tlgKeywordOn
0x18021461b  test    al, al
0x18021461d  jz      short loc_18021462B
0x18021461f  lea     rdx, qword_1802FE048
0x180214626  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18021462b  mov     cs:byte_180314589, bl
0x180214631  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::GetImpl(void)'::`2'::impl
0x180214638  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairRegistryRename>::__private_IsEnabled(void)
0x18021463d  test    al, al
0x18021463f  jz      loc_180214762
0x180214645  mov     rcx, [rbp+var_20]
0x180214649  mov     rax, [rcx]
0x18021464c  mov     rax, [rax+50h]
0x180214650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180214655  mov     rdx, rax; lpValueName
0x180214658  lea     rcx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18021465f  call    ?IsProductInSecureRepairList@@YA_NPEBG0@Z; IsProductInSecureRepairList(ushort const *,ushort const *)
0x180214664  mov     sil, al
0x180214667  test    al, al
0x180214669  jz      short loc_1802146C9
0x18021466b  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x180214672  jz      loc_180214886
0x180214678  mov     rcx, [rbp+var_20]
0x18021467c  mov     rdx, [rcx]
0x18021467f  mov     rax, [rdx+50h]
0x180214683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180214688  lea     r9, aSecrepairProdu; "SECREPAIR: product found in AllowList r"...
0x18021468f  mov     [rsp+80h+var_28], r15; void *
0x180214694  xor     edx, edx; unsigned __int16
0x180214696  mov     [rsp+80h+var_30], r15d; unsigned int
0x18021469b  xor     r8d, r8d; int
0x18021469e  mov     [rsp+80h+var_38], r12; unsigned __int16 *
0x1802146a3  mov     [rsp+80h+var_40], r12; unsigned __int16 *
0x1802146a8  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x1802146ad  lea     ecx, [rdx+9]; int
0x1802146b0  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x1802146b5  mov     [rsp+80h+lpcbData], r12; unsigned __int16 *
0x1802146ba  mov     [rsp+80h+lpData], rax; unsigned __int16 *
0x1802146bf  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1802146c4  jmp     loc_180214886
0x1802146c9  mov     rcx, [rbp+var_20]
0x1802146cd  mov     rax, [rcx]
0x1802146d0  mov     rax, [rax+50h]
0x1802146d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802146d9  mov     rdx, rax; lpValueName
0x1802146dc  lea     rcx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1802146e3  call    ?IsProductInSecureRepairList@@YA_NPEBG0@Z; IsProductInSecureRepairList(ushort const *,ushort const *)
0x1802146e8  mov     sil, al
0x1802146eb  test    al, al
0x1802146ed  jz      loc_180214886
0x1802146f3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl(void)'::`2'::impl
0x1802146fa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(void)
0x1802146ff  test    al, al
0x180214701  jz      short loc_180214739
0x180214703  cmp     cs:byte_180314588, r15b
0x18021470a  jnz     short loc_180214739
0x18021470c  mov     eax, cs:dword_18030F8D0
0x180214712  cmp     eax, 4
0x180214715  jbe     short loc_180214733
0x180214717  lea     rcx, dword_18030F8D0
0x18021471e  call    _tlgKeywordOn
0x180214723  test    al, al
0x180214725  jz      short loc_180214733
0x180214727  lea     rdx, word_1802FDFF2
0x18021472e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180214733  mov     cs:byte_180314588, bl
0x180214739  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x180214740  jz      loc_180214886
0x180214746  mov     rcx, [rbp+var_20]
0x18021474a  mov     rax, [rcx]
0x18021474d  mov     rax, [rax+50h]
0x180214751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180214756  lea     r9, aSecrepairProdu_0; "SECREPAIR: product found in old registr"...
0x18021475d  jmp     loc_18021468F
0x180214762  lea     rax, [rbp+var_10]
0x180214766  mov     r9d, 20019h; unsigned int
0x18021476c  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180214773  mov     [rsp+80h+lpData], rax; HKEY *
0x180214778  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18021477f  call    ?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180214784  test    eax, eax
0x180214786  jnz     loc_180214886
0x18021478c  mov     rcx, [rbp+var_20]
0x180214790  mov     rax, [rcx]
0x180214793  mov     rax, [rax+50h]
0x180214797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021479c  mov     rcx, [rbp+var_10]; hKey
0x1802147a0  xor     r9d, r9d; lpType
0x1802147a3  xor     r8d, r8d; lpReserved
0x1802147a6  mov     [rsp+80h+lpcbData], r15; lpcbData
0x1802147ab  mov     rdx, rax; lpValueName
0x1802147ae  mov     [rsp+80h+lpData], r15; lpData
0x1802147b3  call    cs:__imp_RegQueryValueExW
0x1802147ba  nop     dword ptr [rax+rax+00h]
0x1802147bf  test    eax, eax
0x1802147c1  jnz     loc_18021486D
0x1802147c7  mov     sil, bl
0x1802147ca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::GetImpl(void)'::`2'::impl
0x1802147d1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SecureRepairAllowlistTelemetryAddition>::__private_IsEnabled(void)
0x1802147d6  test    al, al
0x1802147d8  jz      loc_18021486D
0x1802147de  cmp     cs:byte_180314588, r15b
0x1802147e5  jnz     loc_18021486D
0x1802147eb  mov     eax, cs:dword_18030F8D0
0x1802147f1  cmp     eax, 4
0x1802147f4  jbe     short loc_180214812
0x1802147f6  lea     rcx, dword_18030F8D0
0x1802147fd  call    _tlgKeywordOn
0x180214802  test    al, al
0x180214804  jz      short loc_180214812
0x180214806  lea     rdx, byte_1802FE01D
0x18021480d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180214812  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x180214819  jz      short loc_180214867
0x18021481b  mov     rcx, [rbp+var_20]
0x18021481f  mov     rax, [rcx]
0x180214822  mov     rax, [rax+50h]
0x180214826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021482b  mov     [rsp+80h+var_28], r15; void *
0x180214830  lea     r9, aSecrepairProdu_0; "SECREPAIR: product found in old registr"...
0x180214837  mov     [rsp+80h+var_30], r15d; unsigned int
0x18021483c  xor     edx, edx; unsigned __int16
0x18021483e  mov     [rsp+80h+var_38], r12; unsigned __int16 *
0x180214843  xor     r8d, r8d; int
0x180214846  mov     [rsp+80h+var_40], r12; unsigned __int16 *
0x18021484b  mov     [rsp+80h+var_48], r12; unsigned __int16 *
0x180214850  mov     [rsp+80h+var_50], r12; unsigned __int16 *
0x180214855  lea     ecx, [rdx+9]; int
0x180214858  mov     [rsp+80h+lpcbData], r12; unsigned __int16 *
0x18021485d  mov     [rsp+80h+lpData], rax; unsigned __int16 *
0x180214862  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180214867  mov     cs:byte_180314588, bl
0x18021486d  mov     rcx, [rbp+var_10]; hKey
0x180214871  call    cs:__imp_RegCloseKey
  ... truncated ...
```
