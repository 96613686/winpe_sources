# LoadPolicyDataCallback

- ea: `0x1800cdfb0`
- end: `0x1800ce644`
- name: `LoadPolicyDataCallback`
- size: `1684`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000fab0`
- `0x180010340`
- `0x180014fb0`
- `0x180015650`
- `0x18001c994`
- `0x180035c74`
- `0x18003b250`
- `0x18003f96c`
- `0x18004068c`
- `0x18005f5d8`
- `0x1800a1768`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800aba25`
- `0x1800cd700`
- `0x1800cdd70`
- `0x1800cdfb0`
- `0x1800ce8e8`
- `0x1800cf5a8`
- `0x1800cf768`
- `0x180136d80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ce219`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ce24f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ce219`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ce24f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce590`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce5a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce5b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce590`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce5a2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ce5b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce5ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ce5ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce4bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce4bb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ce151`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ce151`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce0dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce0dd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ce1ba`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ce1ba`
- `api-ms-win-security-grouppolicy-l1-1-0!EnterCriticalPolicySectionInternal` at `0x1800ce01a`
- `api-ms-win-security-grouppolicy-l1-1-0!EnterCriticalPolicySectionInternal` at `0x1800ce01a`
- `api-ms-win-security-grouppolicy-l1-1-0!LeaveCriticalPolicySectionInternal` at `0x1800ce53c`
- `api-ms-win-security-grouppolicy-l1-1-0!LeaveCriticalPolicySectionInternal` at `0x1800ce53c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 LoadPolicyDataCallback()
{
  __int64 v0; // r14
  int v1; // eax
  WCHAR *v2; // rbx
  DWORD v3; // edi
  LSTATUS v4; // eax
  LSTATUS v5; // ecx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  char *v8; // rdx
  __int64 v9; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  signed int LastError; // eax
  __int64 result; // rax
  LPCRITICAL_SECTION v17; // [rsp+60h] [rbp-A0h] BYREF
  char v18; // [rsp+68h] [rbp-98h] BYREF
  char v19; // [rsp+70h] [rbp-90h] BYREF
  char v20; // [rsp+78h] [rbp-88h] BYREF
  char v21; // [rsp+80h] [rbp-80h] BYREF
  GUID v22; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[7312]; // [rsp+A0h] [rbp-60h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+1D30h] [rbp+1C30h] BYREF
  HKEY hKey; // [rsp+1D38h] [rbp+1C38h] BYREF
  LPCRITICAL_SECTION v26[2]; // [rsp+1D40h] [rbp+1C40h] BYREF
  DWORD cchName; // [rsp+1D50h] [rbp+1C50h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+1D58h] [rbp+1C58h] BYREF
  _BYTE Src[7236]; // [rsp+1D70h] [rbp+1C70h] BYREF
  GUID v30; // [rsp+39B4h] [rbp+38B4h]
  unsigned __int8 v31[8]; // [rsp+3A00h] [rbp+3900h] BYREF
  int v32; // [rsp+3A08h] [rbp+3908h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids);
  v0 = EnterCriticalPolicySectionInternal(1);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids);
    v17 = 0;
    NetworkPropertyMaps::LockProfileStore(&v17);
    *(_OWORD *)v26 = 0;
    PolicyManagement::LoadPolicyLock(g_serverPolicy, v26);
    *(_OWORD *)lpCriticalSection = 0;
    PolicyManagement::LoadPolicyLock(&g_clientPolicy, lpCriticalSection);
    std::_Tree<std::_Tmap_traits<_GUID,GROUP_POLICY_ENTRY,std::less<_GUID>,std::allocator<std::pair<_GUID const,GROUP_POLICY_ENTRY>>,1>>::clear(v26[1]);
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\CurrentVersion\\NetworkList\\Signatures",
           0,
           0x20019u,
           &hKey) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids);
      cbMaxSubKeyLen = 0;
      v1 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      if ( v1 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( v1 > 0 )
            v1 = (unsigned __int16)v1 | 0x80070000;
          v13 = 25;
          v14 = (unsigned int)v1;
          goto LABEL_71;
        }
      }
      else
      {
        v2 = (WCHAR *)CoTaskMemAlloc(2LL * ++cbMaxSubKeyLen);
        if ( v2 )
        {
          v3 = 0;
          while ( 1 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                while ( 1 )
                {
                  while ( 1 )
                  {
                    while ( 1 )
                    {
                      cchName = cbMaxSubKeyLen;
                      v4 = RegEnumKeyExW(hKey, v3, v2, &cchName, 0, 0, 0, 0);
                      v5 = 0;
                      if ( v4 != 234 )
                        v5 = v4;
                      if ( v5 )
                      {
                        CoTaskMemFree(v2);
                        goto LABEL_75;
                      }
                      ++v3;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          17,
                          &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids,
                          v2);
                      memset_0(Src, 0, 0x1C88u);
                      if ( (unsigned int)_o__wcsicmp(v2, L"FirstNetwork") )
                        break;
                      v6 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      {
                        v7 = 18;
                        goto LABEL_61;
                      }
                    }
                    if ( (unsigned int)_o__wcsicmp(v2, L"EveryNetwork") )
                      break;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        19,
                        &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids,
                        v2);
                    if ( (int)LoadEveryNetworkPolicy(hKey, v2) >= 0 )
                    {
                      v22 = (GUID)c_everyNetworkGuid;
                      memcpy_0(v23, Src, 0x1C88u);
                      v8 = &v18;
                      goto LABEL_31;
                    }
                  }
                  v9 = -1;
                  do
                    ++v9;
                  while ( v2[v9] );
                  if ( v9 == 96 )
                    break;
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v7 = 23;
LABEL_61:
                    WPP_SF_(v6[2], v7, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids);
                  }
                }
                if ( SignatureFromString(v2, v31) < 0 || !(v32 & 1) )
                  break;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    20,
                    &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids,
                    v2);
                if ( (int)LoadUnidentifiedNetworkPolicy(hKey, v2) >= 0 )
                {
                  v22 = g_unidentifiedGuid;
                  memcpy_0(v23, Src, 0x1C88u);
                  v8 = &v19;
                  goto LABEL_31;
                }
              }
              if ( SignatureFromString(v2, v31) < 0 || (v32 & 2) == 0 )
                break;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids, v2);
              if ( (int)LoadIdentifyingNetworkPolicy(hKey, v2) >= 0 )
              {
                v22 = g_identifyingGuid;
                memcpy_0(v23, Src, 0x1C88u);
                v8 = &v20;
                goto LABEL_31;
              }
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids, v2);
            if ( (int)LoadSignaturePolicy(hKey, v2) >= 0 )
            {
              v22 = v30;
              memcpy_0(v23, Src, 0x1C88u);
              v8 = &v21;
LABEL_31:
              std::_Tree<std::_Tmap_traits<_GUID,GROUP_POLICY_ENTRY,std::less<_GUID>,std::allocator<std::pair<_GUID const,GROUP_POLICY_ENTRY>>,1>>::insert<1,0>(
                v26[1],
                v8,
                &v22);
            }
          }
        }
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v13 = 24;
          v14 = 2147942408LL;
LABEL_71:
          WPP_SF_d(v12[2], v13, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids, v14);
        }
      }
    }
LABEL_75:
    LeaveCriticalPolicySectionInternal(v0);
    UpdateClientPolicyCache(v26[1], lpCriticalSection[1]);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
    if ( v26[0] )
      LeaveCriticalSection(v26[0]);
    if ( v17 )
      LeaveCriticalSection(v17);
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids,
        (unsigned int)LastError);
    }
  }
  result = _SetEvent___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ(&g_policyDataInitialized);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1800cdfb0  push    rbp
0x1800cdfb2  push    rbx
0x1800cdfb3  push    rdi
0x1800cdfb4  push    r12
0x1800cdfb6  push    r13
0x1800cdfb8  push    r14
0x1800cdfba  push    r15
0x1800cdfbc  lea     rbp, [rsp-3940h]
0x1800cdfc4  mov     eax, 3A40h
0x1800cdfc9  call    _alloca_probe
0x1800cdfce  sub     rsp, rax
0x1800cdfd1  mov     rax, cs:__security_cookie
0x1800cdfd8  xor     rax, rsp
0x1800cdfdb  mov     [rbp+3970h+var_40], rax
0x1800cdfe2  lea     r12, WPP_GLOBAL_Control
0x1800cdfe9  lea     r13, WPP_f2772fdd912d3509ee8b88ebd698cff0_Traceguids
0x1800cdff0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cdff7  cmp     rcx, r12
0x1800cdffa  jz      short loc_1800CE013
0x1800cdffc  test    byte ptr [rcx+1Ch], 8
0x1800ce000  jz      short loc_1800CE013
0x1800ce002  mov     edx, 0Eh
0x1800ce007  mov     r8, r13
0x1800ce00a  mov     rcx, [rcx+10h]
0x1800ce00e  call    WPP_SF_
0x1800ce013  mov     edi, 1
0x1800ce018  mov     ecx, edi
0x1800ce01a  call    cs:__imp_EnterCriticalPolicySectionInternal
0x1800ce020  mov     r14, rax
0x1800ce023  xor     r15d, r15d
0x1800ce026  test    rax, rax
0x1800ce029  jz      loc_1800CE5BA
0x1800ce02f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce036  cmp     rcx, r12
0x1800ce039  jz      short loc_1800CE050
0x1800ce03b  test    byte ptr [rcx+1Ch], 8
0x1800ce03f  jz      short loc_1800CE050
0x1800ce041  lea     edx, [rdi+0Eh]
0x1800ce044  mov     r8, r13
0x1800ce047  mov     rcx, [rcx+10h]
0x1800ce04b  call    WPP_SF_
0x1800ce050  mov     [rsp+3A70h+var_3A10], r15
0x1800ce055  lea     rcx, [rsp+3A70h+var_3A10]
0x1800ce05a  call    ?LockProfileStore@NetworkPropertyMaps@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; NetworkPropertyMaps::LockProfileStore(void)
0x1800ce05f  xorps   xmm0, xmm0
0x1800ce062  movups  xmmword ptr [rbp+3970h+var_1D30], xmm0
0x1800ce069  lea     rdx, [rbp+3970h+var_1D30]
0x1800ce070  lea     rcx, ?g_serverPolicy@@3VPolicyManagement@@A; PolicyManagement g_serverPolicy
0x1800ce077  call    ?LoadPolicyLock@PolicyManagement@@QEAA?AVPolicyAccess@1@XZ; PolicyManagement::LoadPolicyLock(void)
0x1800ce07c  xorps   xmm0, xmm0
0x1800ce07f  movups  xmmword ptr [rbp+3970h+lpCriticalSection], xmm0
0x1800ce086  lea     rdx, [rbp+3970h+lpCriticalSection]
0x1800ce08d  lea     rcx, ?g_clientPolicy@@3VPolicyManagement@@A; PolicyManagement g_clientPolicy
0x1800ce094  call    ?LoadPolicyLock@PolicyManagement@@QEAA?AVPolicyAccess@1@XZ; PolicyManagement::LoadPolicyLock(void)
0x1800ce099  mov     rcx, [rbp+3970h+var_1D30+8]
0x1800ce0a0  call    ?clear@?$_Tree@V?$_Tmap_traits@U_GUID@@UGROUP_POLICY_ENTRY@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UGROUP_POLICY_ENTRY@@@std@@@4@$00@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,GROUP_POLICY_ENTRY,std::less<_GUID>,std::allocator<std::pair<_GUID const,GROUP_POLICY_ENTRY>>,1>>::clear(void)
0x1800ce0a5  mov     [rbp+3970h+hKey], r15
0x1800ce0ac  xor     edx, edx
0x1800ce0ae  lea     rcx, [rbp+3970h+hKey]
0x1800ce0b5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ce0ba  lea     rax, [rbp+3970h+hKey]
0x1800ce0c1  mov     [rsp+3A70h+phkResult], rax; phkResult
0x1800ce0c6  mov     r9d, 20019h; samDesired
0x1800ce0cc  xor     r8d, r8d; ulOptions
0x1800ce0cf  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x1800ce0d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ce0dd  call    cs:__imp_RegOpenKeyExW
0x1800ce0e3  test    eax, eax
0x1800ce0e5  jnz     loc_1800CE516
0x1800ce0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce0f2  cmp     rcx, r12
0x1800ce0f5  jz      short loc_1800CE10C
0x1800ce0f7  test    byte ptr [rcx+1Ch], 4
0x1800ce0fb  jz      short loc_1800CE10C
0x1800ce0fd  lea     edx, [rax+10h]
0x1800ce100  mov     r8, r13
0x1800ce103  mov     rcx, [rcx+10h]
0x1800ce107  call    WPP_SF_
0x1800ce10c  mov     [rbp+3970h+cbMaxSubKeyLen], r15d
0x1800ce113  mov     [rsp+3A70h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800ce118  mov     [rsp+3A70h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800ce11d  mov     [rsp+3A70h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800ce122  mov     [rsp+3A70h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800ce127  mov     [rsp+3A70h+lpcValues], r15; lpcValues
0x1800ce12c  mov     [rsp+3A70h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800ce131  lea     rax, [rbp+3970h+cbMaxSubKeyLen]
0x1800ce138  mov     [rsp+3A70h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800ce13d  mov     [rsp+3A70h+phkResult], r15; lpcSubKeys
0x1800ce142  xor     r9d, r9d; lpReserved
0x1800ce145  xor     r8d, r8d; lpcchClass
0x1800ce148  xor     edx, edx; lpClass
0x1800ce14a  mov     rcx, [rbp+3970h+hKey]; hKey
0x1800ce151  call    cs:__imp_RegQueryInfoKeyW
0x1800ce157  test    eax, eax
0x1800ce159  jnz     loc_1800CE4E2
0x1800ce15f  mov     eax, [rbp+3970h+cbMaxSubKeyLen]
0x1800ce165  add     eax, edi
0x1800ce167  mov     [rbp+3970h+cbMaxSubKeyLen], eax
0x1800ce16d  mov     ecx, eax
0x1800ce16f  add     rcx, rcx; cb
0x1800ce172  call    cs:__imp_CoTaskMemAlloc
0x1800ce178  mov     rbx, rax
0x1800ce17b  test    rax, rax
0x1800ce17e  jz      loc_1800CE4C3
0x1800ce184  mov     edi, r15d
0x1800ce187  mov     ecx, [rbp+3970h+cbMaxSubKeyLen]
0x1800ce18d  mov     [rbp+3970h+cchName], ecx
0x1800ce193  mov     [rsp+3A70h+lpcValues], r15; lpftLastWriteTime
0x1800ce198  mov     [rsp+3A70h+lpcbMaxClassLen], r15; lpcchClass
0x1800ce19d  mov     [rsp+3A70h+lpcbMaxSubKeyLen], r15; lpClass
0x1800ce1a2  mov     [rsp+3A70h+phkResult], r15; lpReserved
0x1800ce1a7  lea     r9, [rbp+3970h+cchName]; lpcchName
0x1800ce1ae  mov     r8, rbx; lpName
0x1800ce1b1  mov     edx, edi; dwIndex
0x1800ce1b3  mov     rcx, [rbp+3970h+hKey]; hKey
0x1800ce1ba  call    cs:__imp_RegEnumKeyExW
0x1800ce1c0  mov     ecx, r15d
0x1800ce1c3  cmp     eax, 0EAh
0x1800ce1c8  cmovnz  ecx, eax
0x1800ce1cb  test    ecx, ecx
0x1800ce1cd  jnz     loc_1800CE4B8
0x1800ce1d3  inc     edi
0x1800ce1d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce1dc  cmp     rcx, r12
0x1800ce1df  jz      short loc_1800CE1FB
0x1800ce1e1  test    byte ptr [rcx+1Ch], 8
0x1800ce1e5  jz      short loc_1800CE1FB
0x1800ce1e7  mov     edx, 11h
0x1800ce1ec  mov     r9, rbx
0x1800ce1ef  mov     r8, r13
0x1800ce1f2  mov     rcx, [rcx+10h]
0x1800ce1f6  call    WPP_SF_S
0x1800ce1fb  xor     edx, edx; Val
0x1800ce1fd  mov     r8d, 1C88h; Size
0x1800ce203  lea     rcx, [rbp+3970h+Src]; void *
0x1800ce20a  call    memset_0
0x1800ce20f  lea     rdx, aFirstnetwork; "FirstNetwork"
0x1800ce216  mov     rcx, rbx
0x1800ce219  call    cs:__imp__o__wcsicmp
0x1800ce21f  test    eax, eax
0x1800ce221  jnz     short loc_1800CE245
0x1800ce223  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce22a  cmp     rcx, r12
0x1800ce22d  jz      loc_1800CE187
0x1800ce233  test    byte ptr [rcx+1Ch], 8
0x1800ce237  jz      loc_1800CE187
0x1800ce23d  lea     edx, [rax+12h]
0x1800ce240  jmp     loc_1800CE4A7
0x1800ce245  lea     rdx, aEverynetwork; "EveryNetwork"
0x1800ce24c  mov     rcx, rbx
0x1800ce24f  call    cs:__imp__o__wcsicmp
0x1800ce255  test    eax, eax
0x1800ce257  jnz     short loc_1800CE2D7
0x1800ce259  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce260  cmp     rcx, r12
0x1800ce263  jz      short loc_1800CE27D
0x1800ce265  test    byte ptr [rcx+1Ch], 8
0x1800ce269  jz      short loc_1800CE27D
0x1800ce26b  lea     edx, [rax+13h]
0x1800ce26e  mov     r9, rbx
0x1800ce271  mov     r8, r13
0x1800ce274  mov     rcx, [rcx+10h]
0x1800ce278  call    WPP_SF_S
0x1800ce27d  lea     r8, [rbp+3970h+Src]
0x1800ce284  mov     rdx, rbx; lpSubKey
0x1800ce287  mov     rcx, [rbp+3970h+hKey]; hKey
0x1800ce28e  call    LoadEveryNetworkPolicy
0x1800ce293  test    eax, eax
0x1800ce295  js      loc_1800CE187
0x1800ce29b  movups  xmm0, cs:c_everyNetworkGuid
0x1800ce2a2  movdqu  [rbp+3970h+var_39E0], xmm0
0x1800ce2a7  mov     r8d, 1C88h; Size
0x1800ce2ad  lea     rdx, [rbp+3970h+Src]; Src
0x1800ce2b4  lea     rcx, [rbp+3970h+var_39D0]; void *
0x1800ce2b8  call    memcpy_0
0x1800ce2bd  lea     rdx, [rsp+3A70h+var_3A08]
0x1800ce2c2  lea     r8, [rbp+3970h+var_39E0]
0x1800ce2c6  mov     rcx, [rbp+3970h+var_1D30+8]
0x1800ce2cd  call    ??$insert@$00$0A@@?$_Tree@V?$_Tmap_traits@U_GUID@@UGROUP_POLICY_ENTRY@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UGROUP_POLICY_ENTRY@@@std@@@4@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UGROUP_POLICY_ENTRY@@@std@@@std@@@std@@@1@$$QEAU?$pair@$$CBU_GUID@@UGROUP_POLICY_ENTRY@@@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,GROUP_POLICY_ENTRY,std::less<_GUID>,std::allocator<std::pair<_GUID const,GROUP_POLICY_ENTRY>>,1>>::insert<1,0>(std::pair<_GUID const,GROUP_POLICY_ENTRY> &&)
0x1800ce2d2  jmp     loc_1800CE187
0x1800ce2d7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ce2db  inc     rax
0x1800ce2de  cmp     [rbx+rax*2], r15w
0x1800ce2e3  jnz     short loc_1800CE2DB
0x1800ce2e5  cmp     rax, 60h ; '`'
0x1800ce2e9  jnz     loc_1800CE488
0x1800ce2ef  lea     rdx, [rbp+3970h+var_70]; unsigned __int8 *
0x1800ce2f6  mov     rcx, rbx; wchar_t *
0x1800ce2f9  call    ?SignatureFromString@@YAJPEB_WQEAE@Z; SignatureFromString(wchar_t const *,uchar * const)
0x1800ce2fe  test    eax, eax
0x1800ce300  js      short loc_1800CE30C
0x1800ce302  mov     al, byte ptr [rbp+3970h+var_68]
0x1800ce308  and     al, 1
0x1800ce30a  jmp     short loc_1800CE30F
0x1800ce30c  mov     al, r15b
0x1800ce30f  test    al, al
0x1800ce311  jz      short loc_1800CE383
0x1800ce313  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce31a  cmp     rcx, r12
0x1800ce31d  jz      short loc_1800CE339
0x1800ce31f  test    byte ptr [rcx+1Ch], 8
0x1800ce323  jz      short loc_1800CE339
0x1800ce325  mov     edx, 14h
0x1800ce32a  mov     r9, rbx
0x1800ce32d  mov     r8, r13
0x1800ce330  mov     rcx, [rcx+10h]
0x1800ce334  call    WPP_SF_S
0x1800ce339  lea     r8, [rbp+3970h+Src]
0x1800ce340  mov     rdx, rbx; wchar_t *
0x1800ce343  mov     rcx, [rbp+3970h+hKey]; hKey
0x1800ce34a  call    LoadUnidentifiedNetworkPolicy
0x1800ce34f  test    eax, eax
0x1800ce351  js      loc_1800CE187
0x1800ce357  movups  xmm0, xmmword ptr cs:?g_unidentifiedGuid@@3U_GUID@@A.Data1; _GUID g_unidentifiedGuid ...
0x1800ce35e  movdqu  [rbp+3970h+var_39E0], xmm0
0x1800ce363  mov     r8d, 1C88h; Size
0x1800ce369  lea     rdx, [rbp+3970h+Src]; Src
0x1800ce370  lea     rcx, [rbp+3970h+var_39D0]; void *
0x1800ce374  call    memcpy_0
0x1800ce379  lea     rdx, [rsp+3A70h+var_3A00]
0x1800ce37e  jmp     loc_1800CE2C2
0x1800ce383  lea     rdx, [rbp+3970h+var_70]; unsigned __int8 *
0x1800ce38a  mov     rcx, rbx; wchar_t *
0x1800ce38d  call    ?SignatureFromString@@YAJPEB_WQEAE@Z; SignatureFromString(wchar_t const *,uchar * const)
0x1800ce392  test    eax, eax
0x1800ce394  js      short loc_1800CE3A2
0x1800ce396  mov     eax, [rbp+3970h+var_68]
0x1800ce39c  shr     eax, 1
0x1800ce39e  and     al, 1
0x1800ce3a0  jmp     short loc_1800CE3A5
0x1800ce3a2  mov     al, r15b
0x1800ce3a5  test    al, al
0x1800ce3a7  jz      short loc_1800CE419
0x1800ce3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce3b0  cmp     rcx, r12
0x1800ce3b3  jz      short loc_1800CE3CF
0x1800ce3b5  test    byte ptr [rcx+1Ch], 8
0x1800ce3b9  jz      short loc_1800CE3CF
0x1800ce3bb  mov     edx, 15h
0x1800ce3c0  mov     r9, rbx
0x1800ce3c3  mov     r8, r13
0x1800ce3c6  mov     rcx, [rcx+10h]
0x1800ce3ca  call    WPP_SF_S
0x1800ce3cf  lea     r8, [rbp+3970h+Src]
0x1800ce3d6  mov     rdx, rbx; wchar_t *
0x1800ce3d9  mov     rcx, [rbp+3970h+hKey]; hKey
0x1800ce3e0  call    LoadIdentifyingNetworkPolicy
0x1800ce3e5  test    eax, eax
0x1800ce3e7  js      loc_1800CE187
0x1800ce3ed  movups  xmm0, xmmword ptr cs:?g_identifyingGuid@@3U_GUID@@A.Data1; _GUID g_identifyingGuid ...
0x1800ce3f4  movdqu  [rbp+3970h+var_39E0], xmm0
0x1800ce3f9  mov     r8d, 1C88h; Size
0x1800ce3ff  lea     rdx, [rbp+3970h+Src]; Src
0x1800ce406  lea     rcx, [rbp+3970h+var_39D0]; void *
0x1800ce40a  call    memcpy_0
0x1800ce40f  lea     rdx, [rsp+3A70h+var_39F8]
0x1800ce414  jmp     loc_1800CE2C2
0x1800ce419  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce420  cmp     rcx, r12
0x1800ce423  jz      short loc_1800CE43F
0x1800ce425  test    byte ptr [rcx+1Ch], 8
0x1800ce429  jz      short loc_1800CE43F
0x1800ce42b  mov     edx, 16h
0x1800ce430  mov     r9, rbx
0x1800ce433  mov     r8, r13
0x1800ce436  mov     rcx, [rcx+10h]
0x1800ce43a  call    WPP_SF_S
0x1800ce43f  lea     r8, [rbp+3970h+Src]
0x1800ce446  mov     rdx, rbx; wchar_t *
0x1800ce449  mov     rcx, [rbp+3970h+hKey]; hKey
0x1800ce450  call    LoadSignaturePolicy
0x1800ce455  test    eax, eax
0x1800ce457  js      loc_1800CE187
0x1800ce45d  movups  xmm0, [rbp+3970h+var_BC]
0x1800ce464  movdqu  [rbp+3970h+var_39E0], xmm0
0x1800ce469  mov     r8d, 1C88h; Size
0x1800ce46f  lea     rdx, [rbp+3970h+Src]; Src
0x1800ce476  lea     rcx, [rbp+3970h+var_39D0]; void *
0x1800ce47a  call    memcpy_0
0x1800ce47f  lea     rdx, [rbp+3970h+var_39F0]
0x1800ce483  jmp     loc_1800CE2C2
0x1800ce488  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce48f  cmp     rcx, r12
0x1800ce492  jz      loc_1800CE187
0x1800ce498  test    byte ptr [rcx+1Ch], 1
0x1800ce49c  jz      loc_1800CE187
0x1800ce4a2  mov     edx, 17h
0x1800ce4a7  mov     r8, r13
0x1800ce4aa  mov     rcx, [rcx+10h]
0x1800ce4ae  call    WPP_SF_
0x1800ce4b3  jmp     loc_1800CE187
0x1800ce4b8  mov     rcx, rbx; pv
0x1800ce4bb  call    cs:__imp_CoTaskMemFree
0x1800ce4c1  jmp     short loc_1800CE539
0x1800ce4c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ce4ca  cmp     rcx, r12
0x1800ce4cd  jz      short loc_1800CE539
0x1800ce4cf  test    [rcx+1Ch], dil
0x1800ce4d3  jz      short loc_1800CE539
0x1800ce4d5  mov     edx, 18h
  ... truncated ...
```
