# FwMoneisDiagEdpLoadConfig

- ea: `0x18002b18c`
- end: `0x18002b657`
- name: `FwMoneisDiagEdpLoadConfig`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180069dd0`

## callees

- `0x18000a710`
- `0x18002ad78`
- `0x18002b18c`
- `0x18002b660`
- `0x18002c93c`
- `0x18006682c`
- `0x18006fa08`
- `0x1800729c0`
- `0x180074ad4`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18002b29b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18002b2bc`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18002b30c`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18002b3a4`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18002b29b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18002b2bc`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18002b30c`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x18002b3a4`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x18002b333`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x18002b3cb`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x18002b333`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x18002b3cb`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18002b354`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18002b354`
- `fwbase!FwRegQueryString` at `0x18002b2e9`
- `fwbase!FwRegQueryString` at `0x18002b381`
- `fwbase!FwRegQueryString` at `0x18002b2e9`
- `fwbase!FwRegQueryString` at `0x18002b381`
- `fwbase!FwRegQueryDWord` at `0x18002b45c`
- `fwbase!FwRegQueryDWord` at `0x18002b45c`
- `fwbase!FwStringCopy` at `0x18002b22f`
- `fwbase!FwStringCopy` at `0x18002b246`
- `fwbase!FwStringCopy` at `0x18002b25d`
- `fwbase!FwStringCopy` at `0x18002b274`
- `fwbase!FwStringCopy` at `0x18002b323`
- `fwbase!FwStringCopy` at `0x18002b3bb`
- `fwbase!FwStringCopy` at `0x18002b22f`
- `fwbase!FwStringCopy` at `0x18002b246`
- `fwbase!FwStringCopy` at `0x18002b25d`
- `fwbase!FwStringCopy` at `0x18002b274`
- `fwbase!FwStringCopy` at `0x18002b323`
- `fwbase!FwStringCopy` at `0x18002b3bb`
- `fwbase!FwCriticalSectionLeave` at `0x18002b5e9`
- `fwbase!FwCriticalSectionLeave` at `0x18002b5e9`
- `fwbase!FwFree` at `0x18002b495`
- `fwbase!FwFree` at `0x18002b4b5`
- `fwbase!FwFree` at `0x18002b504`
- `fwbase!FwFree` at `0x18002b524`
- `fwbase!FwFree` at `0x18002b573`
- `fwbase!FwFree` at `0x18002b593`
- `fwbase!FwFree` at `0x18002b5f9`
- `fwbase!FwFree` at `0x18002b609`
- `fwbase!FwFree` at `0x18002b619`
- `fwbase!FwFree` at `0x18002b629`
- `fwbase!FwFree` at `0x18002b495`
- `fwbase!FwFree` at `0x18002b4b5`
- `fwbase!FwFree` at `0x18002b504`
- `fwbase!FwFree` at `0x18002b524`
- `fwbase!FwFree` at `0x18002b573`
- `fwbase!FwFree` at `0x18002b593`
- `fwbase!FwFree` at `0x18002b5f9`
- `fwbase!FwFree` at `0x18002b609`
- `fwbase!FwFree` at `0x18002b619`
- `fwbase!FwFree` at `0x18002b629`

## string_xrefs

- `0x18002b455`: `SYSTEM\CurrentControlSet\Services\MpsSvc\Parameters`

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
      FwStringCopy(qword_180132948, &v12);
      FwStringCopy(qword_180132960, &v13);
      FwStringCopy(qword_180132990, &v14);
      FwStringCopy(qword_180132978, &v15);
      v3 = dword_1801329B8;
      PolicyManager_GetPolicyString(L"NetworkIsolation", L"EnterpriseNetworkDomainNames", &qword_180132948);
      PolicyManager_GetPolicyString(L"DataProtection", L"EnterpriseProtectedDomainNames", &qword_180132960);
      FwRegQueryString(
        -2147483646,
        L"Software\\Policies\\Microsoft\\Windows\\NetworkIsolation",
        L"CloudResources",
        &qword_180132990,
        &v16);
      if ( !v16 )
      {
        PolicyManager_GetPolicyString(L"NetworkIsolation", L"EnterpriseCloudResources", &v11);
        FwStringCopy(v11, &qword_180132990);
        PolicyManager_FreeStringValue(v11);
      }
      PolicyManager_GetPolicyInt(L"DataProtection", L"EDPEnforcementLevel", &dword_1801329B8);
      FwRegQueryString(
        -2147483646,
        L"Software\\Policies\\Microsoft\\Windows\\NetworkIsolation",
        L"NeutralResources",
        &qword_180132978,
        &v16);
      if ( !v16 )
      {
        PolicyManager_GetPolicyString(L"NetworkIsolation", L"NeutralResources", &v11);
        FwStringCopy(v11, &qword_180132978);
        PolicyManager_FreeStringValue(v11);
      }
      if ( v3 != dword_1801329B8
        || !(unsigned int)FwMoneisComparePolicy(v12, qword_180132948)
        || !(unsigned int)FwMoneisComparePolicy(v13, qword_180132960)
        || !(unsigned int)FwMoneisComparePolicy(v14, qword_180132990)
        || !(unsigned int)FwMoneisComparePolicy(v15, qword_180132978) )
      {
        *a1 = 1;
      }
    }
    dword_1801329D4 = 0;
    FwRegQueryDWord(
      -2147483646,
      L"SYSTEM\\CurrentControlSet\\Services\\MpsSvc\\Parameters",
      L"ProxyDetectionType",
      &dword_1801329D4,
      &v16);
    if ( !v16 )
      dword_1801329D4 = 0;
    v4 = qword_180132958;
    dword_1801329D0 = 0;
    if ( qword_180132958 )
    {
      for ( i = 0; i < dword_180132950; ++i )
      {
        FwFree(*(_QWORD *)(v4 + 8LL * i));
        v4 = qword_180132958;
      }
      FwFree(v4);
      qword_180132958 = 0;
      dword_180132950 = 0;
    }
    FwMoneisEdpNamesStringToNetNames(qword_180132948, L",", &dword_180132950);
    v6 = qword_180132970;
    if ( qword_180132970 )
    {
      for ( j = 0; j < dword_180132968; ++j )
      {
        FwFree(*(_QWORD *)(v6 + 8LL * j));
        v6 = qword_180132970;
      }
      FwFree(v6);
      qword_180132970 = 0;
      dword_180132968 = 0;
    }
    FwMoneisEdpNamesStringToNetNames(qword_180132960, L"|", &dword_180132968);
    v8 = qword_180132988;
    if ( qword_180132988 )
    {
      for ( k = 0; k < dword_180132980; ++k )
      {
        FwFree(*(_QWORD *)(v8 + 8LL * k));
        v8 = qword_180132988;
      }
      FwFree(v8);
      qword_180132988 = 0;
      dword_180132980 = 0;
    }
    FwMoneisEdpNamesStringToNetNames(qword_180132978, L",", &dword_180132980);
    FwMoneisComputeEnterpriseInterfaces();
    if ( qword_180132960 && qword_180132948 )
      FwMoneisDiagEdpTelemetryEventWriteCensus();
    FwCriticalSectionLeave(qword_180132910);
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      66,
      WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids,
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
0x18002b18c  mov     [rsp-18h+arg_8], rbx
0x18002b191  mov     [rsp-18h+arg_10], rsi
0x18002b196  push    rbp
0x18002b197  push    rdi
0x18002b198  push    r14
0x18002b19a  mov     rbp, rsp
0x18002b19d  sub     rsp, 70h
0x18002b1a1  mov     rax, cs:__security_cookie
0x18002b1a8  xor     rax, rsp
0x18002b1ab  mov     [rbp+var_10], rax
0x18002b1af  xor     esi, esi
0x18002b1b1  mov     rbx, rcx
0x18002b1b4  mov     [rbp+var_40], rsi
0x18002b1b8  mov     [rbp+var_18], esi
0x18002b1bb  mov     [rbp+var_38], rsi
0x18002b1bf  mov     [rbp+var_30], rsi
0x18002b1c3  mov     [rbp+var_28], rsi
0x18002b1c7  mov     [rbp+var_20], rsi
0x18002b1cb  call    EdpFieldsLock
0x18002b1d0  test    eax, eax
0x18002b1d2  jns     short loc_18002B210
0x18002b1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b1db  lea     rdx, WPP_GLOBAL_Control
0x18002b1e2  cmp     rcx, rdx
0x18002b1e5  jz      loc_18002B5F5
0x18002b1eb  test    byte ptr [rcx+1Ch], 1
0x18002b1ef  jz      loc_18002B5F5
0x18002b1f5  mov     rcx, [rcx+10h]
0x18002b1f9  lea     edx, [rsi+42h]
0x18002b1fc  mov     r9d, eax
0x18002b1ff  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x18002b206  call    WPP_SF_d
0x18002b20b  jmp     loc_18002B5F5
0x18002b210  call    IsPolicyManager_GetPolicyIntPresent
0x18002b215  mov     r14, 0FFFFFFFF80000002h
0x18002b21c  test    al, al
0x18002b21e  jz      loc_18002B435
0x18002b224  mov     rcx, cs:qword_180132948
0x18002b22b  lea     rdx, [rbp+var_38]
0x18002b22f  call    cs:__imp_FwStringCopy
0x18002b236  nop     dword ptr [rax+rax+00h]
0x18002b23b  mov     rcx, cs:qword_180132960
0x18002b242  lea     rdx, [rbp+var_30]
0x18002b246  call    cs:__imp_FwStringCopy
0x18002b24d  nop     dword ptr [rax+rax+00h]
0x18002b252  mov     rcx, cs:qword_180132990
0x18002b259  lea     rdx, [rbp+var_28]
0x18002b25d  call    cs:__imp_FwStringCopy
0x18002b264  nop     dword ptr [rax+rax+00h]
0x18002b269  mov     rcx, cs:qword_180132978
0x18002b270  lea     rdx, [rbp+var_20]
0x18002b274  call    cs:__imp_FwStringCopy
0x18002b27b  nop     dword ptr [rax+rax+00h]
0x18002b280  mov     edi, cs:dword_1801329B8
0x18002b286  lea     r8, qword_180132948
0x18002b28d  lea     rdx, aEnterprisenetw; "EnterpriseNetworkDomainNames"
0x18002b294  lea     rcx, aNetworkisolati_2; "NetworkIsolation"
0x18002b29b  call    cs:__imp_PolicyManager_GetPolicyString
0x18002b2a2  nop     dword ptr [rax+rax+00h]
0x18002b2a7  lea     r8, qword_180132960
0x18002b2ae  lea     rdx, aEnterpriseprot; "EnterpriseProtectedDomainNames"
0x18002b2b5  lea     rcx, aDataprotection; "DataProtection"
0x18002b2bc  call    cs:__imp_PolicyManager_GetPolicyString
0x18002b2c3  nop     dword ptr [rax+rax+00h]
0x18002b2c8  lea     rax, [rbp+var_18]
0x18002b2cc  mov     rcx, r14
0x18002b2cf  lea     r9, qword_180132990
0x18002b2d6  mov     [rsp+70h+var_50], rax
0x18002b2db  lea     r8, aCloudresources; "CloudResources"
0x18002b2e2  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18002b2e9  call    cs:__imp_FwRegQueryString
0x18002b2f0  nop     dword ptr [rax+rax+00h]
0x18002b2f5  cmp     [rbp+var_18], esi
0x18002b2f8  jnz     short loc_18002B33F
0x18002b2fa  lea     r8, [rbp+var_40]
0x18002b2fe  lea     rdx, aEnterpriseclou; "EnterpriseCloudResources"
0x18002b305  lea     rcx, aNetworkisolati_2; "NetworkIsolation"
0x18002b30c  call    cs:__imp_PolicyManager_GetPolicyString
0x18002b313  nop     dword ptr [rax+rax+00h]
0x18002b318  mov     rcx, [rbp+var_40]
0x18002b31c  lea     rdx, qword_180132990
0x18002b323  call    cs:__imp_FwStringCopy
0x18002b32a  nop     dword ptr [rax+rax+00h]
0x18002b32f  mov     rcx, [rbp+var_40]
0x18002b333  call    cs:__imp_PolicyManager_FreeStringValue
0x18002b33a  nop     dword ptr [rax+rax+00h]
0x18002b33f  lea     r8, dword_1801329B8
0x18002b346  lea     rdx, aEdpenforcement; "EDPEnforcementLevel"
0x18002b34d  lea     rcx, aDataprotection; "DataProtection"
0x18002b354  call    cs:__imp_PolicyManager_GetPolicyInt
0x18002b35b  nop     dword ptr [rax+rax+00h]
0x18002b360  lea     rax, [rbp+var_18]
0x18002b364  mov     rcx, r14
0x18002b367  lea     r9, qword_180132978
0x18002b36e  mov     [rsp+70h+var_50], rax
0x18002b373  lea     r8, aNeutralresourc; "NeutralResources"
0x18002b37a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18002b381  call    cs:__imp_FwRegQueryString
0x18002b388  nop     dword ptr [rax+rax+00h]
0x18002b38d  cmp     [rbp+var_18], esi
0x18002b390  jnz     short loc_18002B3D7
0x18002b392  lea     r8, [rbp+var_40]
0x18002b396  lea     rdx, aNeutralresourc; "NeutralResources"
0x18002b39d  lea     rcx, aNetworkisolati_2; "NetworkIsolation"
0x18002b3a4  call    cs:__imp_PolicyManager_GetPolicyString
0x18002b3ab  nop     dword ptr [rax+rax+00h]
0x18002b3b0  mov     rcx, [rbp+var_40]
0x18002b3b4  lea     rdx, qword_180132978
0x18002b3bb  call    cs:__imp_FwStringCopy
0x18002b3c2  nop     dword ptr [rax+rax+00h]
0x18002b3c7  mov     rcx, [rbp+var_40]
0x18002b3cb  call    cs:__imp_PolicyManager_FreeStringValue
0x18002b3d2  nop     dword ptr [rax+rax+00h]
0x18002b3d7  cmp     edi, cs:dword_1801329B8
0x18002b3dd  jnz     short loc_18002B42F
0x18002b3df  mov     rdx, cs:qword_180132948
0x18002b3e6  mov     rcx, [rbp+var_38]
0x18002b3ea  call    FwMoneisComparePolicy
0x18002b3ef  test    eax, eax
0x18002b3f1  jz      short loc_18002B42F
0x18002b3f3  mov     rdx, cs:qword_180132960
0x18002b3fa  mov     rcx, [rbp+var_30]
0x18002b3fe  call    FwMoneisComparePolicy
0x18002b403  test    eax, eax
0x18002b405  jz      short loc_18002B42F
0x18002b407  mov     rdx, cs:qword_180132990
0x18002b40e  mov     rcx, [rbp+var_28]
0x18002b412  call    FwMoneisComparePolicy
0x18002b417  test    eax, eax
0x18002b419  jz      short loc_18002B42F
0x18002b41b  mov     rdx, cs:qword_180132978
0x18002b422  mov     rcx, [rbp+var_20]
0x18002b426  call    FwMoneisComparePolicy
0x18002b42b  test    eax, eax
0x18002b42d  jnz     short loc_18002B435
0x18002b42f  mov     dword ptr [rbx], 1
0x18002b435  lea     rax, [rbp+var_18]
0x18002b439  mov     cs:dword_1801329D4, esi
0x18002b43f  lea     r9, dword_1801329D4
0x18002b446  mov     [rsp+70h+var_50], rax
0x18002b44b  lea     r8, aProxydetection; "ProxyDetectionType"
0x18002b452  mov     rcx, r14
0x18002b455  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Mp"...
0x18002b45c  call    cs:__imp_FwRegQueryDWord
0x18002b463  nop     dword ptr [rax+rax+00h]
0x18002b468  cmp     [rbp+var_18], esi
0x18002b46b  jnz     short loc_18002B473
0x18002b46d  mov     cs:dword_1801329D4, esi
0x18002b473  mov     rax, cs:qword_180132958
0x18002b47a  mov     cs:dword_1801329D0, esi
0x18002b480  test    rax, rax
0x18002b483  jz      short loc_18002B4CE
0x18002b485  cmp     cs:dword_180132950, esi
0x18002b48b  mov     ebx, esi
0x18002b48d  jbe     short loc_18002B4B2
0x18002b48f  mov     ecx, ebx
0x18002b491  mov     rcx, [rax+rcx*8]
0x18002b495  call    cs:__imp_FwFree
0x18002b49c  nop     dword ptr [rax+rax+00h]
0x18002b4a1  mov     rax, cs:qword_180132958
0x18002b4a8  inc     ebx
0x18002b4aa  cmp     ebx, cs:dword_180132950
0x18002b4b0  jb      short loc_18002B48F
0x18002b4b2  mov     rcx, rax
0x18002b4b5  call    cs:__imp_FwFree
0x18002b4bc  nop     dword ptr [rax+rax+00h]
0x18002b4c1  mov     cs:qword_180132958, rsi
0x18002b4c8  mov     cs:dword_180132950, esi
0x18002b4ce  mov     rcx, cs:qword_180132948
0x18002b4d5  lea     r8, dword_180132950
0x18002b4dc  lea     rdx, asc_1800FDD80; ","
0x18002b4e3  call    FwMoneisEdpNamesStringToNetNames
0x18002b4e8  mov     rax, cs:qword_180132970
0x18002b4ef  test    rax, rax
0x18002b4f2  jz      short loc_18002B53D
0x18002b4f4  cmp     cs:dword_180132968, esi
0x18002b4fa  mov     ebx, esi
0x18002b4fc  jbe     short loc_18002B521
0x18002b4fe  mov     ecx, ebx
0x18002b500  mov     rcx, [rax+rcx*8]
0x18002b504  call    cs:__imp_FwFree
0x18002b50b  nop     dword ptr [rax+rax+00h]
0x18002b510  mov     rax, cs:qword_180132970
0x18002b517  inc     ebx
0x18002b519  cmp     ebx, cs:dword_180132968
0x18002b51f  jb      short loc_18002B4FE
0x18002b521  mov     rcx, rax
0x18002b524  call    cs:__imp_FwFree
0x18002b52b  nop     dword ptr [rax+rax+00h]
0x18002b530  mov     cs:qword_180132970, rsi
0x18002b537  mov     cs:dword_180132968, esi
0x18002b53d  mov     rcx, cs:qword_180132960
0x18002b544  lea     r8, dword_180132968
0x18002b54b  lea     rdx, asc_1800FDF30; "|"
0x18002b552  call    FwMoneisEdpNamesStringToNetNames
0x18002b557  mov     rax, cs:qword_180132988
0x18002b55e  test    rax, rax
0x18002b561  jz      short loc_18002B5AC
0x18002b563  cmp     cs:dword_180132980, esi
0x18002b569  mov     ebx, esi
0x18002b56b  jbe     short loc_18002B590
0x18002b56d  mov     ecx, ebx
0x18002b56f  mov     rcx, [rax+rcx*8]
0x18002b573  call    cs:__imp_FwFree
0x18002b57a  nop     dword ptr [rax+rax+00h]
0x18002b57f  mov     rax, cs:qword_180132988
0x18002b586  inc     ebx
0x18002b588  cmp     ebx, cs:dword_180132980
0x18002b58e  jb      short loc_18002B56D
0x18002b590  mov     rcx, rax
0x18002b593  call    cs:__imp_FwFree
0x18002b59a  nop     dword ptr [rax+rax+00h]
0x18002b59f  mov     cs:qword_180132988, rsi
0x18002b5a6  mov     cs:dword_180132980, esi
0x18002b5ac  mov     rcx, cs:qword_180132978
0x18002b5b3  lea     r8, dword_180132980
0x18002b5ba  lea     rdx, asc_1800FDD80; ","
0x18002b5c1  call    FwMoneisEdpNamesStringToNetNames
0x18002b5c6  call    FwMoneisComputeEnterpriseInterfaces
0x18002b5cb  cmp     cs:qword_180132960, rsi
0x18002b5d2  jz      short loc_18002B5E2
0x18002b5d4  cmp     cs:qword_180132948, rsi
0x18002b5db  jz      short loc_18002B5E2
0x18002b5dd  call    FwMoneisDiagEdpTelemetryEventWriteCensus
0x18002b5e2  lea     rcx, qword_180132910
0x18002b5e9  call    cs:__imp_FwCriticalSectionLeave
0x18002b5f0  nop     dword ptr [rax+rax+00h]
0x18002b5f5  mov     rcx, [rbp+var_38]
0x18002b5f9  call    cs:__imp_FwFree
0x18002b600  nop     dword ptr [rax+rax+00h]
0x18002b605  mov     rcx, [rbp+var_30]
0x18002b609  call    cs:__imp_FwFree
0x18002b610  nop     dword ptr [rax+rax+00h]
0x18002b615  mov     rcx, [rbp+var_28]
0x18002b619  call    cs:__imp_FwFree
0x18002b620  nop     dword ptr [rax+rax+00h]
0x18002b625  mov     rcx, [rbp+var_20]
0x18002b629  call    cs:__imp_FwFree
0x18002b630  nop     dword ptr [rax+rax+00h]
0x18002b635  mov     rcx, [rbp+var_10]
0x18002b639  xor     rcx, rsp; StackCookie
0x18002b63c  call    __security_check_cookie
0x18002b641  lea     r11, [rsp+70h+var_s0]
0x18002b646  mov     rbx, [r11+28h]
0x18002b64a  mov     rsi, [r11+30h]
0x18002b64e  mov     rsp, r11
0x18002b651  pop     r14
0x18002b653  pop     rdi
0x18002b654  pop     rbp
0x18002b655  retn
```
