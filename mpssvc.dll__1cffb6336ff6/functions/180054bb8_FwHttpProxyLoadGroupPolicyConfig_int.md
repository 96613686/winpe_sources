# FwHttpProxyLoadGroupPolicyConfig(int)

- ea: `0x180054bb8`
- end: `0x1800551fe`
- name: `?FwHttpProxyLoadGroupPolicyConfig@@YAKH@Z`
- size: `1606`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006b84c`
- `0x1800a62d8`

## callees

- `0x18000af3c`
- `0x18004462c`
- `0x180044aec`
- `0x180044ca4`
- `0x180054bb8`
- `0x180058430`
- `0x18006c318`
- `0x18006f520`
- `0x18006ffc8`
- `0x180071624`
- `0x1800a641c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180054fde`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800550ed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180054fde`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800550ed`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180054caf`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180054ddd`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180054caf`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyString` at `0x180054ddd`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180054d16`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180054e44`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180054d16`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_FreeStringValue` at `0x180054e44`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180054f08`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x180054f08`
- `fwbase!FwRegQueryString` at `0x180054c44`
- `fwbase!FwRegQueryString` at `0x180054d77`
- `fwbase!FwRegQueryString` at `0x180054c44`
- `fwbase!FwRegQueryString` at `0x180054d77`
- `fwbase!FwRegQueryDWord` at `0x180054ea4`
- `fwbase!FwRegQueryDWord` at `0x180054ea4`
- `fwbase!FwHResultToWindowsError` at `0x180054c4c`
- `fwbase!FwHResultToWindowsError` at `0x180054cb7`
- `fwbase!FwHResultToWindowsError` at `0x180054d23`
- `fwbase!FwHResultToWindowsError` at `0x180054d7f`
- `fwbase!FwHResultToWindowsError` at `0x180054de5`
- `fwbase!FwHResultToWindowsError` at `0x180054e51`
- `fwbase!FwHResultToWindowsError` at `0x180054eac`
- `fwbase!FwHResultToWindowsError` at `0x180054f10`
- `fwbase!FwHResultToWindowsError` at `0x1800551b1`
- `fwbase!FwHResultToWindowsError` at `0x180054c4c`
- `fwbase!FwHResultToWindowsError` at `0x180054cb7`
- `fwbase!FwHResultToWindowsError` at `0x180054d23`
- `fwbase!FwHResultToWindowsError` at `0x180054d7f`
- `fwbase!FwHResultToWindowsError` at `0x180054de5`
- `fwbase!FwHResultToWindowsError` at `0x180054e51`
- `fwbase!FwHResultToWindowsError` at `0x180054eac`
- `fwbase!FwHResultToWindowsError` at `0x180054f10`
- `fwbase!FwHResultToWindowsError` at `0x1800551b1`
- `fwbase!FwStringCopy` at `0x180054d00`
- `fwbase!FwStringCopy` at `0x180054e2e`
- `fwbase!FwStringCopy` at `0x180054d00`
- `fwbase!FwStringCopy` at `0x180054e2e`
- `fwbase!FwCriticalSectionEnter` at `0x180054f6b`
- `fwbase!FwCriticalSectionEnter` at `0x180054f6b`
- `fwbase!FwCriticalSectionLeave` at `0x18005504c`
- `fwbase!FwCriticalSectionLeave` at `0x18005518d`
- `fwbase!FwCriticalSectionLeave` at `0x18005504c`
- `fwbase!FwCriticalSectionLeave` at `0x18005518d`
- `fwbase!FwFree` at `0x180055057`
- `fwbase!FwFree` at `0x180055062`
- `fwbase!FwFree` at `0x180055057`
- `fwbase!FwFree` at `0x180055062`

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
      WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_4fbb26be2b1a31d69c3c15e2f1ed7fd2_Traceguids, v4);
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
    FwCriticalSectionEnter(qword_18012C4F0);
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
          if ( dword_18012C524 != v18 )
          {
            dword_18012C524 = v18;
            v2 = 1;
          }
          if ( !dword_18012C520 )
            v2 = 1;
          if ( a1 == 1 && v2 == 1 )
          {
            FwHttpProxyConglomerateProxyAddresses(0, 0);
            FwCriticalSectionLeave(qword_18012C4F0);
            v24 = FwDynDataInterIntraAddressUpdate(0x7FFFFFFF, 2);
            dword_18012C520 = v24 == 0;
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
          FwCriticalSectionLeave(qword_18012C4F0);
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
        WPP_SF_d(*(_QWORD *)(v21 + 16), v22, WPP_4fbb26be2b1a31d69c3c15e2f1ed7fd2_Traceguids, v4);
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
0x180054bb8  push    rbp
0x180054bba  push    rbx
0x180054bbb  push    rsi
0x180054bbc  push    rdi
0x180054bbd  push    r12
0x180054bbf  push    r13
0x180054bc1  push    r14
0x180054bc3  push    r15
0x180054bc5  lea     rbp, [rsp-68h]
0x180054bca  sub     rsp, 168h
0x180054bd1  mov     rax, cs:__security_cookie
0x180054bd8  xor     rax, rsp
0x180054bdb  mov     [rbp+0A0h+var_48], rax
0x180054bdf  mov     r12d, ecx
0x180054be2  mov     ebx, 78h ; 'x'
0x180054be7  mov     r8d, ebx; Size
0x180054bea  lea     rcx, [rsp+1A0h+var_150]; void *
0x180054bef  xor     edx, edx; Val
0x180054bf1  call    memset_0
0x180054bf6  mov     r8d, ebx; Size
0x180054bf9  lea     rcx, [rbp+0A0h+var_D0]; void *
0x180054bfd  xor     edx, edx; Val
0x180054bff  call    memset_0
0x180054c04  xor     esi, esi
0x180054c06  lea     rax, [rbp+0A0h+var_50]
0x180054c0a  lea     r15, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180054c11  mov     [rsp+1A0h+var_180], rax
0x180054c16  mov     r13, 0FFFFFFFF80000002h
0x180054c1d  mov     [rbp+0A0h+var_50], esi
0x180054c20  mov     rdx, r15
0x180054c23  mov     [rsp+1A0h+lpString2], rsi
0x180054c28  mov     rcx, r13
0x180054c2b  mov     [rsp+1A0h+var_160], rsi
0x180054c30  lea     r9, [rsp+1A0h+lpString2]
0x180054c35  mov     [rsp+1A0h+var_170], rsi
0x180054c3a  lea     r8, aDomainproxies; "DomainProxies"
0x180054c41  mov     [rbp+0A0h+var_4C], esi
0x180054c44  call    cs:__imp_FwRegQueryString
0x180054c4a  mov     ecx, eax
0x180054c4c  call    cs:__imp_FwHResultToWindowsError
0x180054c52  mov     edi, eax
0x180054c54  test    eax, eax
0x180054c56  jz      short loc_180054C83
0x180054c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180054c5f  lea     rax, WPP_GLOBAL_Control
0x180054c66  cmp     rcx, rax
0x180054c69  jz      loc_180055052
0x180054c6f  lea     ebx, [rsi+1]
0x180054c72  test    [rcx+1Ch], bl
0x180054c75  jz      loc_180055052
0x180054c7b  lea     edx, [rsi+20h]
0x180054c7e  jmp     loc_1800551E6
0x180054c83  lea     r14, aNetworkisolati_2; "NetworkIsolation"
0x180054c8a  cmp     [rbp+0A0h+var_50], esi
0x180054c8d  jnz     loc_180054D5C
0x180054c93  call    IsPolicyManager_GetPolicyIntPresent
0x180054c98  test    al, al
0x180054c9a  jz      loc_180054D5C
0x180054ca0  lea     r8, [rsp+1A0h+var_170]
0x180054ca5  mov     rcx, r14
0x180054ca8  lea     rdx, aEnterpriseprox_0; "EnterpriseProxyServers"
0x180054caf  call    cs:__imp_PolicyManager_GetPolicyString
0x180054cb5  mov     ecx, eax
0x180054cb7  call    cs:__imp_FwHResultToWindowsError
0x180054cbd  cmp     eax, 7Fh
0x180054cc0  mov     edi, esi
0x180054cc2  cmovnz  edi, eax
0x180054cc5  test    edi, edi
0x180054cc7  jz      short loc_180054CF6
0x180054cc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180054cd0  lea     rax, WPP_GLOBAL_Control
0x180054cd7  cmp     rcx, rax
0x180054cda  jz      loc_180055052
0x180054ce0  mov     ebx, 1
0x180054ce5  test    [rcx+1Ch], bl
0x180054ce8  jz      loc_180055052
0x180054cee  lea     edx, [rbx+20h]
0x180054cf1  jmp     loc_1800551E6
0x180054cf6  mov     rcx, [rsp+1A0h+var_170]
0x180054cfb  lea     rdx, [rsp+1A0h+lpString2]
0x180054d00  call    cs:__imp_FwStringCopy
0x180054d06  mov     ebx, eax
0x180054d08  call    IsPolicyManager_GetPolicyIntPresent
0x180054d0d  test    al, al
0x180054d0f  jz      short loc_180054D21
0x180054d11  mov     rcx, [rsp+1A0h+var_170]
0x180054d16  call    cs:__imp_PolicyManager_FreeStringValue
0x180054d1c  mov     [rsp+1A0h+var_170], rsi
0x180054d21  mov     ecx, ebx
0x180054d23  call    cs:__imp_FwHResultToWindowsError
0x180054d29  mov     edi, eax
0x180054d2b  test    eax, eax
0x180054d2d  jz      short loc_180054D5C
0x180054d2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d36  lea     rax, WPP_GLOBAL_Control
0x180054d3d  cmp     rcx, rax
0x180054d40  jz      loc_180055052
0x180054d46  mov     ebx, 1
0x180054d4b  test    [rcx+1Ch], bl
0x180054d4e  jz      loc_180055052
0x180054d54  lea     edx, [rbx+21h]
0x180054d57  jmp     loc_1800551E6
0x180054d5c  lea     rax, [rbp+0A0h+var_50]
0x180054d60  mov     rdx, r15
0x180054d63  lea     r9, [rsp+1A0h+var_160]
0x180054d68  mov     [rsp+1A0h+var_180], rax
0x180054d6d  lea     r8, aDomainlocalpro; "DomainLocalProxies"
0x180054d74  mov     rcx, r13
0x180054d77  call    cs:__imp_FwRegQueryString
0x180054d7d  mov     ecx, eax
0x180054d7f  call    cs:__imp_FwHResultToWindowsError
0x180054d85  mov     edi, eax
0x180054d87  test    eax, eax
0x180054d89  jz      short loc_180054DB8
0x180054d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d92  lea     rax, WPP_GLOBAL_Control
0x180054d99  cmp     rcx, rax
0x180054d9c  jz      loc_180055052
0x180054da2  mov     ebx, 1
0x180054da7  test    [rcx+1Ch], bl
0x180054daa  jz      loc_180055052
0x180054db0  lea     edx, [rbx+22h]
0x180054db3  jmp     loc_1800551E6
0x180054db8  cmp     [rbp+0A0h+var_50], esi
0x180054dbb  jnz     loc_180054E8A
0x180054dc1  call    IsPolicyManager_GetPolicyIntPresent
0x180054dc6  test    al, al
0x180054dc8  jz      loc_180054E8A
0x180054dce  lea     r8, [rsp+1A0h+var_170]
0x180054dd3  mov     rcx, r14
0x180054dd6  lea     rdx, aEnterpriseinte; "EnterpriseInternalProxyServers"
0x180054ddd  call    cs:__imp_PolicyManager_GetPolicyString
0x180054de3  mov     ecx, eax
0x180054de5  call    cs:__imp_FwHResultToWindowsError
0x180054deb  cmp     eax, 7Fh
0x180054dee  mov     edi, esi
0x180054df0  cmovnz  edi, eax
0x180054df3  test    edi, edi
0x180054df5  jz      short loc_180054E24
0x180054df7  mov     rcx, cs:WPP_GLOBAL_Control
0x180054dfe  lea     rax, WPP_GLOBAL_Control
0x180054e05  cmp     rcx, rax
0x180054e08  jz      loc_180055052
0x180054e0e  mov     ebx, 1
0x180054e13  test    [rcx+1Ch], bl
0x180054e16  jz      loc_180055052
0x180054e1c  lea     edx, [rbx+23h]
0x180054e1f  jmp     loc_1800551E6
0x180054e24  mov     rcx, [rsp+1A0h+var_170]
0x180054e29  lea     rdx, [rsp+1A0h+var_160]
0x180054e2e  call    cs:__imp_FwStringCopy
0x180054e34  mov     ebx, eax
0x180054e36  call    IsPolicyManager_GetPolicyIntPresent
0x180054e3b  test    al, al
0x180054e3d  jz      short loc_180054E4F
0x180054e3f  mov     rcx, [rsp+1A0h+var_170]
0x180054e44  call    cs:__imp_PolicyManager_FreeStringValue
0x180054e4a  mov     [rsp+1A0h+var_170], rsi
0x180054e4f  mov     ecx, ebx
0x180054e51  call    cs:__imp_FwHResultToWindowsError
0x180054e57  mov     edi, eax
0x180054e59  test    eax, eax
0x180054e5b  jz      short loc_180054E8A
0x180054e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180054e64  lea     rax, WPP_GLOBAL_Control
0x180054e6b  cmp     rcx, rax
0x180054e6e  jz      loc_180055052
0x180054e74  mov     ebx, 1
0x180054e79  test    [rcx+1Ch], bl
0x180054e7c  jz      loc_180055052
0x180054e82  lea     edx, [rbx+24h]
0x180054e85  jmp     loc_1800551E6
0x180054e8a  lea     rax, [rbp+0A0h+var_50]
0x180054e8e  mov     rdx, r15
0x180054e91  lea     r9, [rbp+0A0h+var_4C]
0x180054e95  mov     [rsp+1A0h+var_180], rax
0x180054e9a  lea     r8, aDproxiesauthor; "DProxiesAuthoritive"
0x180054ea1  mov     rcx, r13
0x180054ea4  call    cs:__imp_FwRegQueryDWord
0x180054eaa  mov     ecx, eax
0x180054eac  call    cs:__imp_FwHResultToWindowsError
0x180054eb2  mov     edi, eax
0x180054eb4  test    eax, eax
0x180054eb6  jz      short loc_180054EE5
0x180054eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ebf  lea     rax, WPP_GLOBAL_Control
0x180054ec6  cmp     rcx, rax
0x180054ec9  jz      loc_180055052
0x180054ecf  mov     ebx, 1
0x180054ed4  test    [rcx+1Ch], bl
0x180054ed7  jz      loc_180055052
0x180054edd  lea     edx, [rbx+25h]
0x180054ee0  jmp     loc_1800551E6
0x180054ee5  mov     eax, [rbp+0A0h+var_50]
0x180054ee8  mov     ebx, 1
0x180054eed  test    eax, eax
0x180054eef  jnz     short loc_180054F56
0x180054ef1  call    IsPolicyManager_GetPolicyIntPresent
0x180054ef6  test    al, al
0x180054ef8  jz      short loc_180054F53
0x180054efa  lea     r8, [rbp+0A0h+var_4C]
0x180054efe  mov     rcx, r14
0x180054f01  lea     rdx, aEnterpriseprox; "EnterpriseProxyServersAreAuthoritative"
0x180054f08  call    cs:__imp_PolicyManager_GetPolicyInt
0x180054f0e  mov     ecx, eax
0x180054f10  call    cs:__imp_FwHResultToWindowsError
0x180054f16  cmp     eax, 7Fh
0x180054f19  mov     edi, esi
0x180054f1b  cmovnz  edi, eax
0x180054f1e  test    edi, edi
0x180054f20  jz      short loc_180054F4A
0x180054f22  mov     rcx, cs:WPP_GLOBAL_Control
0x180054f29  lea     rax, WPP_GLOBAL_Control
0x180054f30  cmp     rcx, rax
0x180054f33  jz      loc_180055052
0x180054f39  test    [rcx+1Ch], bl
0x180054f3c  jz      loc_180055052
0x180054f42  lea     edx, [rbx+26h]
0x180054f45  jmp     loc_1800551E6
0x180054f4a  mov     eax, ebx
0x180054f4c  mov     [rbp+0A0h+var_50], ebx
0x180054f4f  mov     edi, esi
0x180054f51  jmp     short loc_180054F56
0x180054f53  mov     eax, [rbp+0A0h+var_50]
0x180054f56  mov     r14d, esi
0x180054f59  test    eax, eax
0x180054f5b  jz      short loc_180054F64
0x180054f5d  cmp     [rbp+0A0h+var_4C], esi
0x180054f60  cmova   r14d, ebx
0x180054f64  lea     rcx, qword_18012C4F0
0x180054f6b  call    cs:__imp_FwCriticalSectionEnter
0x180054f71  mov     ecx, 8; unsigned int
0x180054f76  call    ?FwHttpProxyFindInUpaTableByFlag@@YAPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@K@Z; FwHttpProxyFindInUpaTableByFlag(ulong)
0x180054f7b  mov     ecx, 10h; unsigned int
0x180054f80  mov     r13, rax
0x180054f83  call    ?FwHttpProxyFindInUpaTableByFlag@@YAPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@K@Z; FwHttpProxyFindInUpaTableByFlag(ulong)
0x180054f88  mov     r15, rax
0x180054f8b  test    r13, r13
0x180054f8e  jnz     short loc_180054FD5
0x180054f90  mov     rcx, [rsp+1A0h+lpString2]
0x180054f95  or      [rbp+0A0h+var_E8], 8
0x180054f99  mov     [rsp+1A0h+var_148], rcx
0x180054f9e  lea     rcx, [rsp+1A0h+var_150]; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x180054fa3  mov     [rsp+1A0h+lpString2], rsi
0x180054fa8  call    ?FwHttpProxyUrlProxyAddressTableAddEntry@@YAKPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyUrlProxyAddressTableAddEntry(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x180054fad  mov     edi, eax
0x180054faf  test    eax, eax
0x180054fb1  jz      loc_18005508A
0x180054fb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180054fbe  lea     rax, WPP_GLOBAL_Control
0x180054fc5  cmp     rcx, rax
0x180054fc8  jz      short loc_180055045
0x180054fca  test    [rcx+1Ch], bl
0x180054fcd  jz      short loc_180055045
0x180054fcf  lea     edx, [r13+28h]
0x180054fd3  jmp     short loc_180055032
0x180054fd5  mov     rdx, [rsp+1A0h+lpString2]; lpString2
0x180054fda  mov     rcx, [r13+8]; lpString1
0x180054fde  call    cs:__imp_lstrcmpiW
0x180054fe4  test    eax, eax
0x180054fe6  jz      loc_18005508C
0x180054fec  mov     rcx, r13; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x180054fef  call    ?FwHttpProxyEmptyUpaEntry@@YAXPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyEmptyUpaEntry(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x180054ff4  or      dword ptr [r13+68h], 8
0x180054ff9  mov     rcx, r13; struct _FW_HTTP_URL_PROXY_ADDRESS_ENTRY *
0x180054ffc  mov     rax, [rsp+1A0h+lpString2]
0x180055001  mov     [r13+8], rax
0x180055005  mov     [rsp+1A0h+lpString2], rsi
0x18005500a  call    ?FwHttpProxyResolveProxyNames@@YAKPEAU_FW_HTTP_URL_PROXY_ADDRESS_ENTRY@@@Z; FwHttpProxyResolveProxyNames(_FW_HTTP_URL_PROXY_ADDRESS_ENTRY *)
0x18005500f  mov     edi, eax
0x180055011  test    eax, eax
0x180055013  jz      short loc_18005508A
0x180055015  mov     rcx, cs:WPP_GLOBAL_Control
0x18005501c  lea     rax, WPP_GLOBAL_Control
0x180055023  cmp     rcx, rax
0x180055026  jz      short loc_180055045
0x180055028  test    [rcx+1Ch], bl
0x18005502b  jz      short loc_180055045
0x18005502d  mov     edx, 29h ; ')'
0x180055032  mov     rcx, [rcx+10h]
0x180055036  lea     r8, WPP_4fbb26be2b1a31d69c3c15e2f1ed7fd2_Traceguids
0x18005503d  mov     r9d, edi
0x180055040  call    WPP_SF_d
0x180055045  lea     rcx, qword_18012C4F0
0x18005504c  call    cs:__imp_FwCriticalSectionLeave
0x180055052  mov     rcx, [rsp+1A0h+lpString2]
0x180055057  call    cs:__imp_FwFree
0x18005505d  mov     rcx, [rsp+1A0h+var_160]
0x180055062  call    cs:__imp_FwFree
0x180055068  mov     eax, edi
0x18005506a  mov     rcx, [rbp+0A0h+var_48]
0x18005506e  xor     rcx, rsp; StackCookie
0x180055071  call    __security_check_cookie
0x180055076  add     rsp, 168h
0x18005507d  pop     r15
0x18005507f  pop     r14
0x180055081  pop     r13
0x180055083  pop     r12
0x180055085  pop     rdi
0x180055086  pop     rsi
  ... truncated ...
```
