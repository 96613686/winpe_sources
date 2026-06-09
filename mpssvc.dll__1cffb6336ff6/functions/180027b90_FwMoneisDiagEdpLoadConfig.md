# FwMoneisDiagEdpLoadConfig

- ea: `0x180027b90`
- end: `0x180027fb8`
- name: `FwMoneisDiagEdpLoadConfig`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066704`

## callees

- `0x180006ce0`
- `0x18000af3c`
- `0x180027b90`
- `0x180027fc0`
- `0x1800291a4`
- `0x180062394`
- `0x18006c854`
- `0x18006f520`
- `0x180071624`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180027c87`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180027ca2`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180027ce6`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180027d60`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180027c87`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180027ca2`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180027ce6`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180027d60`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180027d01`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180027d7b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180027d01`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180027d7b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180027d1c`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180027d1c`
- `fwbase!FwRegQueryString` at `0x180027cc9`
- `fwbase!FwRegQueryString` at `0x180027d43`
- `fwbase!FwRegQueryString` at `0x180027cc9`
- `fwbase!FwRegQueryString` at `0x180027d43`
- `fwbase!FwRegQueryDWord` at `0x180027e06`
- `fwbase!FwRegQueryDWord` at `0x180027e06`
- `fwbase!FwStringCopy` at `0x180027c33`
- `fwbase!FwStringCopy` at `0x180027c44`
- `fwbase!FwStringCopy` at `0x180027c55`
- `fwbase!FwStringCopy` at `0x180027c66`
- `fwbase!FwStringCopy` at `0x180027cf7`
- `fwbase!FwStringCopy` at `0x180027d71`
- `fwbase!FwStringCopy` at `0x180027c33`
- `fwbase!FwStringCopy` at `0x180027c44`
- `fwbase!FwStringCopy` at `0x180027c55`
- `fwbase!FwStringCopy` at `0x180027c66`
- `fwbase!FwStringCopy` at `0x180027cf7`
- `fwbase!FwStringCopy` at `0x180027d71`
- `fwbase!FwCriticalSectionLeave` at `0x180027f69`
- `fwbase!FwCriticalSectionLeave` at `0x180027f69`
- `fwbase!FwFree` at `0x180027e39`
- `fwbase!FwFree` at `0x180027e53`
- `fwbase!FwFree` at `0x180027e9c`
- `fwbase!FwFree` at `0x180027eb6`
- `fwbase!FwFree` at `0x180027eff`
- `fwbase!FwFree` at `0x180027f19`
- `fwbase!FwFree` at `0x180027f73`
- `fwbase!FwFree` at `0x180027f7d`
- `fwbase!FwFree` at `0x180027f87`
- `fwbase!FwFree` at `0x180027f91`
- `fwbase!FwFree` at `0x180027e39`
- `fwbase!FwFree` at `0x180027e53`
- `fwbase!FwFree` at `0x180027e9c`
- `fwbase!FwFree` at `0x180027eb6`
- `fwbase!FwFree` at `0x180027eff`
- `fwbase!FwFree` at `0x180027f19`
- `fwbase!FwFree` at `0x180027f73`
- `fwbase!FwFree` at `0x180027f7d`
- `fwbase!FwFree` at `0x180027f87`
- `fwbase!FwFree` at `0x180027f91`

## string_xrefs

- `0x180027dff`: `SYSTEM\CurrentControlSet\Services\MpsSvc\Parameters`

## pseudocode

```c
__int64 __fastcall FwMoneisDiagEdpLoadConfig(_DWORD *a1)
{
  int v2; // eax
  int v3; // edi
  __int64 v4; // rax
  unsigned int i; // ebx
  __int64 v6; // rax
  unsigned int j; // ebx
  __int64 v8; // rax
  unsigned int k; // ebx
  __int64 v11; // [rsp+30h] [rbp-40h] BYREF
  __int64 v12; // [rsp+38h] [rbp-38h] BYREF
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+48h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h] BYREF
  int v16; // [rsp+58h] [rbp-18h] BYREF

  v11 = 0;
  v16 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v2 = EdpFieldsLock();
  if ( v2 >= 0 )
  {
    if ( (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
    {
      FwStringCopy(qword_18012C778, &v12);
      FwStringCopy(qword_18012C790, &v13);
      FwStringCopy(qword_18012C7C0, &v14);
      FwStringCopy(qword_18012C7A8, &v15);
      v3 = dword_18012C7E8;
      PolicyManager_GetPolicyString(L"NetworkIsolation", L"EnterpriseNetworkDomainNames", &qword_18012C778);
      PolicyManager_GetPolicyString(L"DataProtection", L"EnterpriseProtectedDomainNames", &qword_18012C790);
      FwRegQueryString(
        -2147483646,
        L"Software\\Policies\\Microsoft\\Windows\\NetworkIsolation",
        L"CloudResources",
        &qword_18012C7C0,
        &v16);
      if ( !v16 )
      {
        PolicyManager_GetPolicyString(L"NetworkIsolation", L"EnterpriseCloudResources", &v11);
        FwStringCopy(v11, &qword_18012C7C0);
        PolicyManager_FreeStringValue(v11);
      }
      PolicyManager_GetPolicyInt(L"DataProtection", L"EDPEnforcementLevel", &dword_18012C7E8);
      FwRegQueryString(
        -2147483646,
        L"Software\\Policies\\Microsoft\\Windows\\NetworkIsolation",
        L"NeutralResources",
        &qword_18012C7A8,
        &v16);
      if ( !v16 )
      {
        PolicyManager_GetPolicyString(L"NetworkIsolation", L"NeutralResources", &v11);
        FwStringCopy(v11, &qword_18012C7A8);
        PolicyManager_FreeStringValue(v11);
      }
      if ( v3 != dword_18012C7E8
        || !(unsigned int)FwMoneisComparePolicy(v12, qword_18012C778)
        || !(unsigned int)FwMoneisComparePolicy(v13, qword_18012C790)
        || !(unsigned int)FwMoneisComparePolicy(v14, qword_18012C7C0)
        || !(unsigned int)FwMoneisComparePolicy(v15, qword_18012C7A8) )
      {
        *a1 = 1;
      }
    }
    dword_18012C804 = 0;
    FwRegQueryDWord(
      -2147483646,
      L"SYSTEM\\CurrentControlSet\\Services\\MpsSvc\\Parameters",
      L"ProxyDetectionType",
      &dword_18012C804,
      &v16);
    if ( !v16 )
      dword_18012C804 = 0;
    v4 = qword_18012C788;
    dword_18012C800 = 0;
    if ( qword_18012C788 )
    {
      for ( i = 0; i < dword_18012C780; ++i )
      {
        FwFree(*(_QWORD *)(v4 + 8LL * i));
        v4 = qword_18012C788;
      }
      FwFree(v4);
      qword_18012C788 = 0;
      dword_18012C780 = 0;
    }
    FwMoneisEdpNamesStringToNetNames(qword_18012C778, L",", &dword_18012C780);
    v6 = qword_18012C7A0;
    if ( qword_18012C7A0 )
    {
      for ( j = 0; j < dword_18012C798; ++j )
      {
        FwFree(*(_QWORD *)(v6 + 8LL * j));
        v6 = qword_18012C7A0;
      }
      FwFree(v6);
      qword_18012C7A0 = 0;
      dword_18012C798 = 0;
    }
    FwMoneisEdpNamesStringToNetNames(qword_18012C790, L"|", &dword_18012C798);
    v8 = qword_18012C7B8;
    if ( qword_18012C7B8 )
    {
      for ( k = 0; k < dword_18012C7B0; ++k )
      {
        FwFree(*(_QWORD *)(v8 + 8LL * k));
        v8 = qword_18012C7B8;
      }
      FwFree(v8);
      qword_18012C7B8 = 0;
      dword_18012C7B0 = 0;
    }
    FwMoneisEdpNamesStringToNetNames(qword_18012C7A8, L",", &dword_18012C7B0);
    FwMoneisComputeEnterpriseInterfaces();
    if ( qword_18012C790 && qword_18012C778 )
      FwMoneisDiagEdpTelemetryEventWriteCensus();
    FwCriticalSectionLeave(qword_18012C740);
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      66,
      WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids,
      (unsigned int)v2);
  }
  FwFree(v12);
  FwFree(v13);
  FwFree(v14);
  return FwFree(v15);
}

```

## disassembly

```asm
0x180027b90  mov     [rsp-18h+arg_8], rbx
0x180027b95  mov     [rsp-18h+arg_10], rsi
0x180027b9a  push    rbp
0x180027b9b  push    rdi
0x180027b9c  push    r14
0x180027b9e  mov     rbp, rsp
0x180027ba1  sub     rsp, 70h
0x180027ba5  mov     rax, cs:__security_cookie
0x180027bac  xor     rax, rsp
0x180027baf  mov     [rbp+var_10], rax
0x180027bb3  xor     esi, esi
0x180027bb5  mov     rbx, rcx
0x180027bb8  mov     [rbp+var_40], rsi
0x180027bbc  mov     [rbp+var_18], esi
0x180027bbf  mov     [rbp+var_38], rsi
0x180027bc3  mov     [rbp+var_30], rsi
0x180027bc7  mov     [rbp+var_28], rsi
0x180027bcb  mov     [rbp+var_20], rsi
0x180027bcf  call    EdpFieldsLock
0x180027bd4  test    eax, eax
0x180027bd6  jns     short loc_180027C14
0x180027bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bdf  lea     rdx, WPP_GLOBAL_Control
0x180027be6  cmp     rcx, rdx
0x180027be9  jz      loc_180027F6F
0x180027bef  test    byte ptr [rcx+1Ch], 1
0x180027bf3  jz      loc_180027F6F
0x180027bf9  mov     rcx, [rcx+10h]
0x180027bfd  lea     edx, [rsi+42h]
0x180027c00  mov     r9d, eax
0x180027c03  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x180027c0a  call    WPP_SF_d
0x180027c0f  jmp     loc_180027F6F
0x180027c14  call    IsPolicyManager_GetPolicyIntPresent
0x180027c19  mov     r14, 0FFFFFFFF80000002h
0x180027c20  test    al, al
0x180027c22  jz      loc_180027DDF
0x180027c28  mov     rcx, cs:qword_18012C778
0x180027c2f  lea     rdx, [rbp+var_38]
0x180027c33  call    cs:__imp_FwStringCopy
0x180027c39  mov     rcx, cs:qword_18012C790
0x180027c40  lea     rdx, [rbp+var_30]
0x180027c44  call    cs:__imp_FwStringCopy
0x180027c4a  mov     rcx, cs:qword_18012C7C0
0x180027c51  lea     rdx, [rbp+var_28]
0x180027c55  call    cs:__imp_FwStringCopy
0x180027c5b  mov     rcx, cs:qword_18012C7A8
0x180027c62  lea     rdx, [rbp+var_20]
0x180027c66  call    cs:__imp_FwStringCopy
0x180027c6c  mov     edi, cs:dword_18012C7E8
0x180027c72  lea     r8, qword_18012C778
0x180027c79  lea     rdx, aEnterprisenetw; "EnterpriseNetworkDomainNames"
0x180027c80  lea     rcx, aNetworkisolati_2; "NetworkIsolation"
0x180027c87  call    cs:__imp_PolicyManager_GetPolicyString
0x180027c8d  lea     r8, qword_18012C790
0x180027c94  lea     rdx, aEnterpriseprot; "EnterpriseProtectedDomainNames"
0x180027c9b  lea     rcx, aDataprotection; "DataProtection"
0x180027ca2  call    cs:__imp_PolicyManager_GetPolicyString
0x180027ca8  lea     rax, [rbp+var_18]
0x180027cac  mov     rcx, r14
0x180027caf  lea     r9, qword_18012C7C0
0x180027cb6  mov     [rsp+70h+var_50], rax
0x180027cbb  lea     r8, aCloudresources; "CloudResources"
0x180027cc2  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180027cc9  call    cs:__imp_FwRegQueryString
0x180027ccf  cmp     [rbp+var_18], esi
0x180027cd2  jnz     short loc_180027D07
0x180027cd4  lea     r8, [rbp+var_40]
0x180027cd8  lea     rdx, aEnterpriseclou; "EnterpriseCloudResources"
0x180027cdf  lea     rcx, aNetworkisolati_2; "NetworkIsolation"
0x180027ce6  call    cs:__imp_PolicyManager_GetPolicyString
0x180027cec  mov     rcx, [rbp+var_40]
0x180027cf0  lea     rdx, qword_18012C7C0
0x180027cf7  call    cs:__imp_FwStringCopy
0x180027cfd  mov     rcx, [rbp+var_40]
0x180027d01  call    cs:__imp_PolicyManager_FreeStringValue
0x180027d07  lea     r8, dword_18012C7E8
0x180027d0e  lea     rdx, aEdpenforcement; "EDPEnforcementLevel"
0x180027d15  lea     rcx, aDataprotection; "DataProtection"
0x180027d1c  call    cs:__imp_PolicyManager_GetPolicyInt
0x180027d22  lea     rax, [rbp+var_18]
0x180027d26  mov     rcx, r14
0x180027d29  lea     r9, qword_18012C7A8
0x180027d30  mov     [rsp+70h+var_50], rax
0x180027d35  lea     r8, aNeutralresourc; "NeutralResources"
0x180027d3c  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180027d43  call    cs:__imp_FwRegQueryString
0x180027d49  cmp     [rbp+var_18], esi
0x180027d4c  jnz     short loc_180027D81
0x180027d4e  lea     r8, [rbp+var_40]
0x180027d52  lea     rdx, aNeutralresourc; "NeutralResources"
0x180027d59  lea     rcx, aNetworkisolati_2; "NetworkIsolation"
0x180027d60  call    cs:__imp_PolicyManager_GetPolicyString
0x180027d66  mov     rcx, [rbp+var_40]
0x180027d6a  lea     rdx, qword_18012C7A8
0x180027d71  call    cs:__imp_FwStringCopy
0x180027d77  mov     rcx, [rbp+var_40]
0x180027d7b  call    cs:__imp_PolicyManager_FreeStringValue
0x180027d81  cmp     edi, cs:dword_18012C7E8
0x180027d87  jnz     short loc_180027DD9
0x180027d89  mov     rdx, cs:qword_18012C778
0x180027d90  mov     rcx, [rbp+var_38]
0x180027d94  call    FwMoneisComparePolicy
0x180027d99  test    eax, eax
0x180027d9b  jz      short loc_180027DD9
0x180027d9d  mov     rdx, cs:qword_18012C790
0x180027da4  mov     rcx, [rbp+var_30]
0x180027da8  call    FwMoneisComparePolicy
0x180027dad  test    eax, eax
0x180027daf  jz      short loc_180027DD9
0x180027db1  mov     rdx, cs:qword_18012C7C0
0x180027db8  mov     rcx, [rbp+var_28]
0x180027dbc  call    FwMoneisComparePolicy
0x180027dc1  test    eax, eax
0x180027dc3  jz      short loc_180027DD9
0x180027dc5  mov     rdx, cs:qword_18012C7A8
0x180027dcc  mov     rcx, [rbp+var_20]
0x180027dd0  call    FwMoneisComparePolicy
0x180027dd5  test    eax, eax
0x180027dd7  jnz     short loc_180027DDF
0x180027dd9  mov     dword ptr [rbx], 1
0x180027ddf  lea     rax, [rbp+var_18]
0x180027de3  mov     cs:dword_18012C804, esi
0x180027de9  lea     r9, dword_18012C804
0x180027df0  mov     [rsp+70h+var_50], rax
0x180027df5  lea     r8, aProxydetection; "ProxyDetectionType"
0x180027dfc  mov     rcx, r14
0x180027dff  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Mp"...
0x180027e06  call    cs:__imp_FwRegQueryDWord
0x180027e0c  cmp     [rbp+var_18], esi
0x180027e0f  jnz     short loc_180027E17
0x180027e11  mov     cs:dword_18012C804, esi
0x180027e17  mov     rax, cs:qword_18012C788
0x180027e1e  mov     cs:dword_18012C800, esi
0x180027e24  test    rax, rax
0x180027e27  jz      short loc_180027E66
0x180027e29  cmp     cs:dword_18012C780, esi
0x180027e2f  mov     ebx, esi
0x180027e31  jbe     short loc_180027E50
0x180027e33  mov     ecx, ebx
0x180027e35  mov     rcx, [rax+rcx*8]
0x180027e39  call    cs:__imp_FwFree
0x180027e3f  mov     rax, cs:qword_18012C788
0x180027e46  inc     ebx
0x180027e48  cmp     ebx, cs:dword_18012C780
0x180027e4e  jb      short loc_180027E33
0x180027e50  mov     rcx, rax
0x180027e53  call    cs:__imp_FwFree
0x180027e59  mov     cs:qword_18012C788, rsi
0x180027e60  mov     cs:dword_18012C780, esi
0x180027e66  mov     rcx, cs:qword_18012C778
0x180027e6d  lea     r8, dword_18012C780
0x180027e74  lea     rdx, asc_1800F7CB0; ","
0x180027e7b  call    FwMoneisEdpNamesStringToNetNames
0x180027e80  mov     rax, cs:qword_18012C7A0
0x180027e87  test    rax, rax
0x180027e8a  jz      short loc_180027EC9
0x180027e8c  cmp     cs:dword_18012C798, esi
0x180027e92  mov     ebx, esi
0x180027e94  jbe     short loc_180027EB3
0x180027e96  mov     ecx, ebx
0x180027e98  mov     rcx, [rax+rcx*8]
0x180027e9c  call    cs:__imp_FwFree
0x180027ea2  mov     rax, cs:qword_18012C7A0
0x180027ea9  inc     ebx
0x180027eab  cmp     ebx, cs:dword_18012C798
0x180027eb1  jb      short loc_180027E96
0x180027eb3  mov     rcx, rax
0x180027eb6  call    cs:__imp_FwFree
0x180027ebc  mov     cs:qword_18012C7A0, rsi
0x180027ec3  mov     cs:dword_18012C798, esi
0x180027ec9  mov     rcx, cs:qword_18012C790
0x180027ed0  lea     r8, dword_18012C798
0x180027ed7  lea     rdx, asc_1800F7E60; "|"
0x180027ede  call    FwMoneisEdpNamesStringToNetNames
0x180027ee3  mov     rax, cs:qword_18012C7B8
0x180027eea  test    rax, rax
0x180027eed  jz      short loc_180027F2C
0x180027eef  cmp     cs:dword_18012C7B0, esi
0x180027ef5  mov     ebx, esi
0x180027ef7  jbe     short loc_180027F16
0x180027ef9  mov     ecx, ebx
0x180027efb  mov     rcx, [rax+rcx*8]
0x180027eff  call    cs:__imp_FwFree
0x180027f05  mov     rax, cs:qword_18012C7B8
0x180027f0c  inc     ebx
0x180027f0e  cmp     ebx, cs:dword_18012C7B0
0x180027f14  jb      short loc_180027EF9
0x180027f16  mov     rcx, rax
0x180027f19  call    cs:__imp_FwFree
0x180027f1f  mov     cs:qword_18012C7B8, rsi
0x180027f26  mov     cs:dword_18012C7B0, esi
0x180027f2c  mov     rcx, cs:qword_18012C7A8
0x180027f33  lea     r8, dword_18012C7B0
0x180027f3a  lea     rdx, asc_1800F7CB0; ","
0x180027f41  call    FwMoneisEdpNamesStringToNetNames
0x180027f46  call    FwMoneisComputeEnterpriseInterfaces
0x180027f4b  cmp     cs:qword_18012C790, rsi
0x180027f52  jz      short loc_180027F62
0x180027f54  cmp     cs:qword_18012C778, rsi
0x180027f5b  jz      short loc_180027F62
0x180027f5d  call    FwMoneisDiagEdpTelemetryEventWriteCensus
0x180027f62  lea     rcx, qword_18012C740
0x180027f69  call    cs:__imp_FwCriticalSectionLeave
0x180027f6f  mov     rcx, [rbp+var_38]
0x180027f73  call    cs:__imp_FwFree
0x180027f79  mov     rcx, [rbp+var_30]
0x180027f7d  call    cs:__imp_FwFree
0x180027f83  mov     rcx, [rbp+var_28]
0x180027f87  call    cs:__imp_FwFree
0x180027f8d  mov     rcx, [rbp+var_20]
0x180027f91  call    cs:__imp_FwFree
0x180027f97  mov     rcx, [rbp+var_10]
0x180027f9b  xor     rcx, rsp; StackCookie
0x180027f9e  call    __security_check_cookie
0x180027fa3  lea     r11, [rsp+70h+var_s0]
0x180027fa8  mov     rbx, [r11+28h]
0x180027fac  mov     rsi, [r11+30h]
0x180027fb0  mov     rsp, r11
0x180027fb3  pop     r14
0x180027fb5  pop     rdi
0x180027fb6  pop     rbp
0x180027fb7  retn
```
