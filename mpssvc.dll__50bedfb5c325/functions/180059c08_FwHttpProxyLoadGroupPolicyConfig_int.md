# FwHttpProxyLoadGroupPolicyConfig(int)

- ea: `0x180059c08`
- end: `0x18005a2f7`
- name: `?FwHttpProxyLoadGroupPolicyConfig@@YAKH@Z`
- size: `1775`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006e92c`
- `0x1800abe24`

## callees

- `0x18000a710`
- `0x18004573c`
- `0x180045c58`
- `0x180045e40`
- `0x180059c08`
- `0x18005d468`
- `0x18006f208`
- `0x1800729c0`
- `0x180073488`
- `0x180074ad4`
- `0x1800abf7c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18005a0a8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18005a1d4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18005a0a8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18005a1d4`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180059d0b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180059e63`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180059d0b`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180059e63`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180059d84`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180059edc`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180059d84`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180059edc`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180059fb8`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180059fb8`
- `fwbase!FwHResultToWindowsError` at `0x180059ca2`
- `fwbase!FwHResultToWindowsError` at `0x180059d19`
- `fwbase!FwHResultToWindowsError` at `0x180059d97`
- `fwbase!FwHResultToWindowsError` at `0x180059dff`
- `fwbase!FwHResultToWindowsError` at `0x180059e71`
- `fwbase!FwHResultToWindowsError` at `0x180059eef`
- `fwbase!FwHResultToWindowsError` at `0x180059f56`
- `fwbase!FwHResultToWindowsError` at `0x180059fc6`
- `fwbase!FwHResultToWindowsError` at `0x18005a2a4`
- `fwbase!FwHResultToWindowsError` at `0x180059ca2`
- `fwbase!FwHResultToWindowsError` at `0x180059d19`
- `fwbase!FwHResultToWindowsError` at `0x180059d97`
- `fwbase!FwHResultToWindowsError` at `0x180059dff`
- `fwbase!FwHResultToWindowsError` at `0x180059e71`
- `fwbase!FwHResultToWindowsError` at `0x180059eef`
- `fwbase!FwHResultToWindowsError` at `0x180059f56`
- `fwbase!FwHResultToWindowsError` at `0x180059fc6`
- `fwbase!FwHResultToWindowsError` at `0x18005a2a4`
- `fwbase!FwRegQueryString` at `0x180059c94`
- `fwbase!FwRegQueryString` at `0x180059df1`
- `fwbase!FwRegQueryString` at `0x180059c94`
- `fwbase!FwRegQueryString` at `0x180059df1`
- `fwbase!FwRegQueryDWord` at `0x180059f48`
- `fwbase!FwRegQueryDWord` at `0x180059f48`
- `fwbase!FwStringCopy` at `0x180059d68`
- `fwbase!FwStringCopy` at `0x180059ec0`
- `fwbase!FwStringCopy` at `0x180059d68`
- `fwbase!FwStringCopy` at `0x180059ec0`
- `fwbase!FwCriticalSectionEnter` at `0x18005a027`
- `fwbase!FwCriticalSectionEnter` at `0x18005a027`
- `fwbase!FwCriticalSectionLeave` at `0x18005a120`
- `fwbase!FwCriticalSectionLeave` at `0x18005a27a`
- `fwbase!FwCriticalSectionLeave` at `0x18005a120`
- `fwbase!FwCriticalSectionLeave` at `0x18005a27a`
- `fwbase!FwFree` at `0x18005a131`
- `fwbase!FwFree` at `0x18005a142`
- `fwbase!FwFree` at `0x18005a131`
- `fwbase!FwFree` at `0x18005a142`

## pseudocode

```c
__int64 __fastcall FwHttpProxyLoadGroupPolicyConfig(int a1)
{
  int v2; // esi
  unsigned int v3; // eax
  unsigned int v4; // edi
  __int64 v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int PolicyString; // eax
  unsigned int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  int v15; // eax
  unsigned int PolicyInt; // eax
  unsigned int v17; // eax
  int v18; // r14d
  struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *v19; // r13
  struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *v20; // r15
  __int64 v21; // rcx
  __int64 v22; // rdx
  unsigned int v24; // eax
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpString2; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR v27[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v28[8]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+B8h] [rbp-48h]
  _BYTE v31[8]; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR v32; // [rsp+D8h] [rbp-28h]
  int v33; // [rsp+138h] [rbp+38h]
  int v34; // [rsp+150h] [rbp+50h] BYREF
  int v35; // [rsp+154h] [rbp+54h] BYREF

  memset_0(v28, 0, 0x78u);
  memset_0(v31, 0, 0x78u);
  v2 = 0;
  v34 = 0;
  lpString2 = 0;
  v27[0] = 0;
  v25 = 0;
  v35 = 0;
  v3 = FwRegQueryString(
         -2147483646,
         L"Software\\Policies\\Microsoft\\Windows\\NetworkIsolation",
         L"DomainProxies",
         &lpString2,
         &v34);
  v4 = FwHResultToWindowsError(v3);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v6 = 32;
LABEL_89:
      WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_beda3cd07d663dfecc8ed25415b6e23b_Traceguids, v4);
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  if ( v34 || !(unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
  {
LABEL_19:
    v10 = FwRegQueryString(
            -2147483646,
            L"Software\\Policies\\Microsoft\\Windows\\NetworkIsolation",
            L"DomainLocalProxies",
            v27,
            &v34);
    v4 = FwHResultToWindowsError(v10);
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v6 = 35;
        goto LABEL_89;
      }
      goto LABEL_65;
    }
    if ( !v34 && (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
    {
      PolicyString = PolicyManager_GetPolicyString(L"NetworkIsolation", L"EnterpriseInternalProxyServers", &v25);
      v12 = FwHResultToWindowsError(PolicyString);
      v4 = 0;
      if ( v12 != 127 )
        v4 = v12;
      if ( v4 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v6 = 36;
          goto LABEL_89;
        }
        goto LABEL_65;
      }
      v13 = FwStringCopy(v25, v27);
      if ( (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
      {
        PolicyManager_FreeStringValue(v25);
        v25 = 0;
      }
      v4 = FwHResultToWindowsError(v13);
      if ( v4 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v6 = 37;
          goto LABEL_89;
        }
        goto LABEL_65;
      }
    }
    v14 = FwRegQueryDWord(
            -2147483646,
            L"Software\\Policies\\Microsoft\\Windows\\NetworkIsolation",
            L"DProxiesAuthoritive",
            &v35,
            &v34);
    v4 = FwHResultToWindowsError(v14);
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v6 = 38;
        goto LABEL_89;
      }
      goto LABEL_65;
    }
    v15 = v34;
    if ( !v34 )
    {
      if ( (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
      {
        PolicyInt = PolicyManager_GetPolicyInt(L"NetworkIsolation", L"EnterpriseProxyServersAreAuthoritative", &v35);
        v17 = FwHResultToWindowsError(PolicyInt);
        v4 = 0;
        if ( v17 != 127 )
          v4 = v17;
        if ( v4 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v6 = 39;
            goto LABEL_89;
          }
          goto LABEL_65;
        }
        v15 = 1;
        v34 = 1;
        v4 = 0;
      }
      else
      {
        v15 = v34;
      }
    }
    v18 = 0;
    if ( v15 )
      v18 = v35 != 0;
    FwCriticalSectionEnter(qword_1801326C0);
    v19 = FwHttpProxyFindInUpaTableByFlag(8u);
    v20 = FwHttpProxyFindInUpaTableByFlag(0x10u);
    if ( v19 )
    {
      if ( !lstrcmpiW(*((LPCWSTR *)v19 + 1), lpString2) )
      {
LABEL_67:
        if ( !v20 )
        {
          v33 |= 0x10u;
          v32 = v27[0];
          v27[0] = 0;
          v4 = FwHttpProxyUrlProxyAddressTableAddEntry((struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)v31);
          if ( v4 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            {
              goto LABEL_64;
            }
            v22 = 42;
            goto LABEL_63;
          }
          goto LABEL_78;
        }
        if ( !a1 && !lstrcmpiW(*((LPCWSTR *)v20 + 1), v27[0]) )
        {
LABEL_79:
          if ( dword_1801326F4 != v18 )
          {
            dword_1801326F4 = v18;
            v2 = 1;
          }
          if ( !dword_1801326F0 )
            v2 = 1;
          if ( a1 == 1 && v2 == 1 )
          {
            FwHttpProxyConglomerateProxyAddresses(0, 0);
            FwCriticalSectionLeave(qword_1801326C0);
            v24 = FwDynDataInterIntraAddressUpdate(0x7FFFFFFF, 2);
            dword_1801326F0 = v24 == 0;
            v4 = FwHResultToWindowsError(v24);
            if ( v4 )
            {
              v5 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v6 = 44;
                goto LABEL_89;
              }
            }
            goto LABEL_65;
          }
LABEL_64:
          FwCriticalSectionLeave(qword_1801326C0);
          goto LABEL_65;
        }
        FwHttpProxyEmptyUpaEntry(v20);
        *((_DWORD *)v20 + 26) |= 0x10u;
        *((LPCWSTR *)v20 + 1) = v27[0];
        v27[0] = 0;
        v4 = FwHttpProxyResolveProxyNames(v20);
        if ( !v4 )
        {
LABEL_78:
          v2 = 1;
          goto LABEL_79;
        }
        v21 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_64;
        v22 = 43;
LABEL_63:
        WPP_SF_d(*(_QWORD *)(v21 + 16), v22, WPP_beda3cd07d663dfecc8ed25415b6e23b_Traceguids, v4);
        goto LABEL_64;
      }
      FwHttpProxyEmptyUpaEntry(v19);
      *((_DWORD *)v19 + 26) |= 8u;
      *((_QWORD *)v19 + 1) = lpString2;
      lpString2 = 0;
      v4 = FwHttpProxyResolveProxyNames(v19);
      if ( v4 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_64;
        v22 = 41;
        goto LABEL_63;
      }
    }
    else
    {
      v30 |= 8u;
      v29 = lpString2;
      lpString2 = 0;
      v4 = FwHttpProxyUrlProxyAddressTableAddEntry((struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)v28);
      if ( v4 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_64;
        v22 = 40;
        goto LABEL_63;
      }
    }
    v2 = 1;
    goto LABEL_67;
  }
  v7 = PolicyManager_GetPolicyString(L"NetworkIsolation", L"EnterpriseProxyServers", &v25);
  v8 = FwHResultToWindowsError(v7);
  v4 = 0;
  if ( v8 != 127 )
    v4 = v8;
  if ( !v4 )
  {
    v9 = FwStringCopy(v25, &lpString2);
    if ( (unsigned __int8)IsPolicyManager_GetPolicyIntPresent() )
    {
      PolicyManager_FreeStringValue(v25);
      v25 = 0;
    }
    v4 = FwHResultToWindowsError(v9);
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v6 = 34;
        goto LABEL_89;
      }
      goto LABEL_65;
    }
    goto LABEL_19;
  }
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v6 = 33;
    goto LABEL_89;
  }
LABEL_65:
  FwFree(lpString2);
  FwFree(v27[0]);
  return v4;
}

```

## disassembly

```asm
0x180059c08  push    rbp
0x180059c0a  push    rbx
0x180059c0b  push    rsi
0x180059c0c  push    rdi
0x180059c0d  push    r12
0x180059c0f  push    r13
0x180059c11  push    r14
0x180059c13  push    r15
0x180059c15  lea     rbp, [rsp-68h]
0x180059c1a  sub     rsp, 168h
0x180059c21  mov     rax, cs:__security_cookie
0x180059c28  xor     rax, rsp
0x180059c2b  mov     [rbp+0A0h+var_48], rax
0x180059c2f  mov     r12d, ecx
0x180059c32  mov     ebx, 78h ; 'x'
0x180059c37  mov     r8d, ebx; Size
0x180059c3a  lea     rcx, [rsp+1A0h+var_150]; void *
0x180059c3f  xor     edx, edx; Val
0x180059c41  call    memset_0
0x180059c46  mov     r8d, ebx; Size
0x180059c49  lea     rcx, [rbp+0A0h+var_D0]; void *
0x180059c4d  xor     edx, edx; Val
0x180059c4f  call    memset_0
0x180059c54  xor     esi, esi
0x180059c56  lea     rax, [rbp+0A0h+var_50]
0x180059c5a  lea     r15, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180059c61  mov     [rsp+1A0h+var_180], rax
0x180059c66  mov     r13, 0FFFFFFFF80000002h
0x180059c6d  mov     [rbp+0A0h+var_50], esi
0x180059c70  mov     rdx, r15
0x180059c73  mov     [rsp+1A0h+lpString2], rsi
0x180059c78  mov     rcx, r13
0x180059c7b  mov     [rsp+1A0h+var_160], rsi
0x180059c80  lea     r9, [rsp+1A0h+lpString2]
0x180059c85  mov     [rsp+1A0h+var_170], rsi
0x180059c8a  lea     r8, aDomainproxies; "DomainProxies"
0x180059c91  mov     [rbp+0A0h+var_4C], esi
0x180059c94  call    cs:__imp_FwRegQueryString
0x180059c9b  nop     dword ptr [rax+rax+00h]
0x180059ca0  mov     ecx, eax
0x180059ca2  call    cs:__imp_FwHResultToWindowsError
0x180059ca9  nop     dword ptr [rax+rax+00h]
0x180059cae  mov     edi, eax
0x180059cb0  test    eax, eax
0x180059cb2  jz      short loc_180059CDF
0x180059cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180059cbb  lea     rax, WPP_GLOBAL_Control
0x180059cc2  cmp     rcx, rax
0x180059cc5  jz      loc_18005A12C
0x180059ccb  lea     ebx, [rsi+1]
0x180059cce  test    [rcx+1Ch], bl
0x180059cd1  jz      loc_18005A12C
0x180059cd7  lea     edx, [rsi+20h]
0x180059cda  jmp     loc_18005A2DF
0x180059cdf  lea     r14, aNetworkisolati_2; "NetworkIsolation"
0x180059ce6  cmp     [rbp+0A0h+var_50], esi
0x180059ce9  jnz     loc_180059DD6
0x180059cef  call    IsPolicyManager_GetPolicyIntPresent
0x180059cf4  test    al, al
0x180059cf6  jz      loc_180059DD6
0x180059cfc  lea     r8, [rsp+1A0h+var_170]
0x180059d01  mov     rcx, r14
0x180059d04  lea     rdx, aEnterpriseprox_0; "EnterpriseProxyServers"
0x180059d0b  call    cs:__imp_PolicyManager_GetPolicyString
0x180059d12  nop     dword ptr [rax+rax+00h]
0x180059d17  mov     ecx, eax
0x180059d19  call    cs:__imp_FwHResultToWindowsError
0x180059d20  nop     dword ptr [rax+rax+00h]
0x180059d25  cmp     eax, 7Fh
0x180059d28  mov     edi, esi
0x180059d2a  cmovnz  edi, eax
0x180059d2d  test    edi, edi
0x180059d2f  jz      short loc_180059D5E
0x180059d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d38  lea     rax, WPP_GLOBAL_Control
0x180059d3f  cmp     rcx, rax
0x180059d42  jz      loc_18005A12C
0x180059d48  mov     ebx, 1
0x180059d4d  test    [rcx+1Ch], bl
0x180059d50  jz      loc_18005A12C
0x180059d56  lea     edx, [rbx+20h]
0x180059d59  jmp     loc_18005A2DF
0x180059d5e  mov     rcx, [rsp+1A0h+var_170]
0x180059d63  lea     rdx, [rsp+1A0h+lpString2]
0x180059d68  call    cs:__imp_FwStringCopy
0x180059d6f  nop     dword ptr [rax+rax+00h]
0x180059d74  mov     ebx, eax
0x180059d76  call    IsPolicyManager_GetPolicyIntPresent
0x180059d7b  test    al, al
0x180059d7d  jz      short loc_180059D95
0x180059d7f  mov     rcx, [rsp+1A0h+var_170]
0x180059d84  call    cs:__imp_PolicyManager_FreeStringValue
0x180059d8b  nop     dword ptr [rax+rax+00h]
0x180059d90  mov     [rsp+1A0h+var_170], rsi
0x180059d95  mov     ecx, ebx
0x180059d97  call    cs:__imp_FwHResultToWindowsError
0x180059d9e  nop     dword ptr [rax+rax+00h]
0x180059da3  mov     edi, eax
0x180059da5  test    eax, eax
0x180059da7  jz      short loc_180059DD6
0x180059da9  mov     rcx, cs:WPP_GLOBAL_Control
0x180059db0  lea     rax, WPP_GLOBAL_Control
0x180059db7  cmp     rcx, rax
0x180059dba  jz      loc_18005A12C
0x180059dc0  mov     ebx, 1
0x180059dc5  test    [rcx+1Ch], bl
0x180059dc8  jz      loc_18005A12C
0x180059dce  lea     edx, [rbx+21h]
0x180059dd1  jmp     loc_18005A2DF
0x180059dd6  lea     rax, [rbp+0A0h+var_50]
0x180059dda  mov     rdx, r15
0x180059ddd  lea     r9, [rsp+1A0h+var_160]
0x180059de2  mov     [rsp+1A0h+var_180], rax
0x180059de7  lea     r8, aDomainlocalpro; "DomainLocalProxies"
0x180059dee  mov     rcx, r13
0x180059df1  call    cs:__imp_FwRegQueryString
0x180059df8  nop     dword ptr [rax+rax+00h]
0x180059dfd  mov     ecx, eax
0x180059dff  call    cs:__imp_FwHResultToWindowsError
0x180059e06  nop     dword ptr [rax+rax+00h]
0x180059e0b  mov     edi, eax
0x180059e0d  test    eax, eax
0x180059e0f  jz      short loc_180059E3E
0x180059e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180059e18  lea     rax, WPP_GLOBAL_Control
0x180059e1f  cmp     rcx, rax
0x180059e22  jz      loc_18005A12C
0x180059e28  mov     ebx, 1
0x180059e2d  test    [rcx+1Ch], bl
0x180059e30  jz      loc_18005A12C
0x180059e36  lea     edx, [rbx+22h]
0x180059e39  jmp     loc_18005A2DF
0x180059e3e  cmp     [rbp+0A0h+var_50], esi
0x180059e41  jnz     loc_180059F2E
0x180059e47  call    IsPolicyManager_GetPolicyIntPresent
0x180059e4c  test    al, al
0x180059e4e  jz      loc_180059F2E
0x180059e54  lea     r8, [rsp+1A0h+var_170]
0x180059e59  mov     rcx, r14
0x180059e5c  lea     rdx, aEnterpriseinte; "EnterpriseInternalProxyServers"
0x180059e63  call    cs:__imp_PolicyManager_GetPolicyString
0x180059e6a  nop     dword ptr [rax+rax+00h]
0x180059e6f  mov     ecx, eax
0x180059e71  call    cs:__imp_FwHResultToWindowsError
0x180059e78  nop     dword ptr [rax+rax+00h]
0x180059e7d  cmp     eax, 7Fh
0x180059e80  mov     edi, esi
0x180059e82  cmovnz  edi, eax
0x180059e85  test    edi, edi
0x180059e87  jz      short loc_180059EB6
0x180059e89  mov     rcx, cs:WPP_GLOBAL_Control
0x180059e90  lea     rax, WPP_GLOBAL_Control
0x180059e97  cmp     rcx, rax
0x180059e9a  jz      loc_18005A12C
0x180059ea0  mov     ebx, 1
0x180059ea5  test    [rcx+1Ch], bl
0x180059ea8  jz      loc_18005A12C
0x180059eae  lea     edx, [rbx+23h]
0x180059eb1  jmp     loc_18005A2DF
0x180059eb6  mov     rcx, [rsp+1A0h+var_170]
0x180059ebb  lea     rdx, [rsp+1A0h+var_160]
0x180059ec0  call    cs:__imp_FwStringCopy
0x180059ec7  nop     dword ptr [rax+rax+00h]
0x180059ecc  mov     ebx, eax
0x180059ece  call    IsPolicyManager_GetPolicyIntPresent
0x180059ed3  test    al, al
0x180059ed5  jz      short loc_180059EED
0x180059ed7  mov     rcx, [rsp+1A0h+var_170]
0x180059edc  call    cs:__imp_PolicyManager_FreeStringValue
0x180059ee3  nop     dword ptr [rax+rax+00h]
0x180059ee8  mov     [rsp+1A0h+var_170], rsi
0x180059eed  mov     ecx, ebx
0x180059eef  call    cs:__imp_FwHResultToWindowsError
0x180059ef6  nop     dword ptr [rax+rax+00h]
0x180059efb  mov     edi, eax
0x180059efd  test    eax, eax
0x180059eff  jz      short loc_180059F2E
0x180059f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f08  lea     rax, WPP_GLOBAL_Control
0x180059f0f  cmp     rcx, rax
0x180059f12  jz      loc_18005A12C
0x180059f18  mov     ebx, 1
0x180059f1d  test    [rcx+1Ch], bl
0x180059f20  jz      loc_18005A12C
0x180059f26  lea     edx, [rbx+24h]
0x180059f29  jmp     loc_18005A2DF
0x180059f2e  lea     rax, [rbp+0A0h+var_50]
0x180059f32  mov     rdx, r15
0x180059f35  lea     r9, [rbp+0A0h+var_4C]
0x180059f39  mov     [rsp+1A0h+var_180], rax
0x180059f3e  lea     r8, aDproxiesauthor; "DProxiesAuthoritive"
0x180059f45  mov     rcx, r13
0x180059f48  call    cs:__imp_FwRegQueryDWord
0x180059f4f  nop     dword ptr [rax+rax+00h]
0x180059f54  mov     ecx, eax
0x180059f56  call    cs:__imp_FwHResultToWindowsError
0x180059f5d  nop     dword ptr [rax+rax+00h]
0x180059f62  mov     edi, eax
0x180059f64  test    eax, eax
0x180059f66  jz      short loc_180059F95
0x180059f68  mov     rcx, cs:WPP_GLOBAL_Control
0x180059f6f  lea     rax, WPP_GLOBAL_Control
0x180059f76  cmp     rcx, rax
0x180059f79  jz      loc_18005A12C
0x180059f7f  mov     ebx, 1
0x180059f84  test    [rcx+1Ch], bl
0x180059f87  jz      loc_18005A12C
0x180059f8d  lea     edx, [rbx+25h]
0x180059f90  jmp     loc_18005A2DF
0x180059f95  mov     eax, [rbp+0A0h+var_50]
0x180059f98  mov     ebx, 1
0x180059f9d  test    eax, eax
0x180059f9f  jnz     short loc_18005A012
0x180059fa1  call    IsPolicyManager_GetPolicyIntPresent
0x180059fa6  test    al, al
0x180059fa8  jz      short loc_18005A00F
0x180059faa  lea     r8, [rbp+0A0h+var_4C]
0x180059fae  mov     rcx, r14
0x180059fb1  lea     rdx, aEnterpriseprox; "EnterpriseProxyServersAreAuthoritative"
0x180059fb8  call    cs:__imp_PolicyManager_GetPolicyInt
0x180059fbf  nop     dword ptr [rax+rax+00h]
0x180059fc4  mov     ecx, eax
0x180059fc6  call    cs:__imp_FwHResultToWindowsError
0x180059fcd  nop     dword ptr [rax+rax+00h]
0x180059fd2  cmp     eax, 7Fh
0x180059fd5  mov     edi, esi
0x180059fd7  cmovnz  edi, eax
0x180059fda  test    edi, edi
0x180059fdc  jz      short loc_18005A006
0x180059fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180059fe5  lea     rax, WPP_GLOBAL_Control
0x180059fec  cmp     rcx, rax
0x180059fef  jz      loc_18005A12C
0x180059ff5  test    [rcx+1Ch], bl
0x180059ff8  jz      loc_18005A12C
0x180059ffe  lea     edx, [rbx+26h]
0x18005a001  jmp     loc_18005A2DF
0x18005a006  mov     eax, ebx
0x18005a008  mov     [rbp+0A0h+var_50], ebx
0x18005a00b  mov     edi, esi
0x18005a00d  jmp     short loc_18005A012
0x18005a00f  mov     eax, [rbp+0A0h+var_50]
0x18005a012  mov     r14d, esi
0x18005a015  test    eax, eax
0x18005a017  jz      short loc_18005A020
0x18005a019  cmp     [rbp+0A0h+var_4C], esi
0x18005a01c  cmova   r14d, ebx
0x18005a020  lea     rcx, qword_1801326C0
0x18005a027  call    cs:__imp_FwCriticalSectionEnter
0x18005a02e  nop     dword ptr [rax+rax+00h]
0x18005a033  mov     ecx, 8; unsigned int
0x18005a038  call    ?FwHttpProxyFindInUpaTableByFlag@@YAPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@K@Z; FwHttpProxyFindInUpaTableByFlag(ulong)
0x18005a03d  mov     ecx, 10h; unsigned int
0x18005a042  mov     r13, rax
0x18005a045  call    ?FwHttpProxyFindInUpaTableByFlag@@YAPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@K@Z; FwHttpProxyFindInUpaTableByFlag(ulong)
0x18005a04a  mov     r15, rax
0x18005a04d  test    r13, r13
0x18005a050  jnz     short loc_18005A09F
0x18005a052  mov     rcx, [rsp+1A0h+lpString2]
0x18005a057  or      [rbp+0A0h+var_E8], 8
0x18005a05b  mov     [rsp+1A0h+var_148], rcx
0x18005a060  lea     rcx, [rsp+1A0h+var_150]; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x18005a065  mov     [rsp+1A0h+lpString2], rsi
0x18005a06a  call    ?FwHttpProxyUrlProxyAddressTableAddEntry@@YAKPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyUrlProxyAddressTableAddEntry(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x18005a06f  mov     edi, eax
0x18005a071  test    eax, eax
0x18005a073  jz      loc_18005A171
0x18005a079  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a080  lea     rax, WPP_GLOBAL_Control
0x18005a087  cmp     rcx, rax
0x18005a08a  jz      loc_18005A119
0x18005a090  test    [rcx+1Ch], bl
0x18005a093  jz      loc_18005A119
0x18005a099  lea     edx, [r13+28h]
0x18005a09d  jmp     short loc_18005A106
0x18005a09f  mov     rdx, [rsp+1A0h+lpString2]; lpString2
0x18005a0a4  mov     rcx, [r13+8]; lpString1
0x18005a0a8  call    cs:__imp_lstrcmpiW
0x18005a0af  nop     dword ptr [rax+rax+00h]
0x18005a0b4  test    eax, eax
0x18005a0b6  jz      loc_18005A173
0x18005a0bc  mov     rcx, r13; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x18005a0bf  call    ?FwHttpProxyEmptyUpaEntry@@YAXPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyEmptyUpaEntry(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x18005a0c4  or      dword ptr [r13+68h], 8
0x18005a0c9  mov     rcx, r13; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x18005a0cc  mov     rax, [rsp+1A0h+lpString2]
0x18005a0d1  mov     [r13+8], rax
0x18005a0d5  mov     [rsp+1A0h+lpString2], rsi
0x18005a0da  call    ?FwHttpProxyResolveProxyNames@@YAKPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyResolveProxyNames(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x18005a0df  mov     edi, eax
0x18005a0e1  test    eax, eax
0x18005a0e3  jz      loc_18005A171
0x18005a0e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a0f0  lea     rax, WPP_GLOBAL_Control
0x18005a0f7  cmp     rcx, rax
0x18005a0fa  jz      short loc_18005A119
0x18005a0fc  test    [rcx+1Ch], bl
0x18005a0ff  jz      short loc_18005A119
0x18005a101  mov     edx, 29h ; ')'
0x18005a106  mov     rcx, [rcx+10h]
  ... truncated ...
```
