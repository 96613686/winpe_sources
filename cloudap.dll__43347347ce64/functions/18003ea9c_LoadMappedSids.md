# LoadMappedSids

- ea: `0x18003ea9c`
- end: `0x18003f0c6`
- name: `LoadMappedSids`
- size: `1578`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ac40`
- `0x18000db68`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x18002b260`
- `0x18003ea9c`
- `0x18005e94c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003edcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003edd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ede4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003edcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003edd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ede4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef57`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003edc5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003ef38`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003edc5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18003ef38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f09c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f0ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f09c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f0ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003ec0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003ec0f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003ed4e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003ed4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eb81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ee4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eb81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ee4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003edb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ef23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f057`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f07e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f08d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003edb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ef23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f057`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f07e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f08d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ecc3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003ecc3`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003eb34`
- `ntdll!RtlAcquireResourceExclusive` at `0x18003eb34`
- `ntdll!RtlReleaseResource` at `0x18003f049`
- `ntdll!RtlReleaseResource` at `0x18003f049`

## string_xrefs

- `0x18003eade`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003eb9b`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003ec26`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003ec87`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003ecd1`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003ed68`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003edf5`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003ee68`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003eedb`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003ef68`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003efa9`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003efee`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18003ee7c`: `RegOpenKeyEx`
- `0x18003eb6c`: `SidMap`
- `0x18003ebaf`: `RegOpenKeyEx`
- `0x18003ee09`: `ConvertStringSidToSidW`
- `0x18003ef7c`: `ConvertStringSidToSidW`
- `0x18003ed1e`: `InternetSid`
- `0x18003efbd`: `AddSidMapIntoCache`

## pseudocode

```c
__int64 __fastcall LoadMappedSids(HKEY hKey)
{
  LPCWSTR v2; // r14
  unsigned int v3; // ebx
  const char *v4; // rax
  WCHAR *v5; // r15
  const char *v6; // rax
  __int64 v7; // r8
  LSTATUS v8; // eax
  const char *v9; // r9
  __int64 v10; // rcx
  const char *v11; // r9
  const char *v12; // r9
  DWORD i; // ebx
  const char *v14; // r9
  __int64 v15; // r8
  const char *v16; // r9
  __int64 v17; // r8
  unsigned int v18; // eax
  __int64 v19; // rdx
  const char *v20; // r9
  __int64 v21; // r8
  const char *v22; // rax
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // r8
  const char *v28; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-49h]
  PHKEY phkResulta; // [rsp+20h] [rbp-49h]
  PHKEY phkResultb; // [rsp+20h] [rbp-49h]
  PHKEY phkResultc; // [rsp+20h] [rbp-49h]
  PHKEY phkResultd; // [rsp+20h] [rbp-49h]
  HLOCAL hMem; // [rsp+60h] [rbp-9h] BYREF
  HLOCAL Sid; // [rsp+68h] [rbp-1h] BYREF
  HKEY hkey; // [rsp+70h] [rbp+7h] BYREF
  HKEY hKeya; // [rsp+78h] [rbp+Fh] BYREF
  LPCWSTR StringSid; // [rsp+80h] [rbp+17h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+D0h] [rbp+67h] BYREF
  DWORD cSubKeys; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD cchName; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v43; // [rsp+E8h] [rbp+7Fh] BYREF

  cSubKeys = 0;
  v2 = 0;
  cbMaxSubKeyLen = 0;
  StringSid = 0;
  hMem = 0;
  Sid = 0;
  hKeya = 0;
  hkey = 0;
  if ( !hKey )
  {
    v3 = -1073741811;
    v4 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v4, 68, "Invalid Arg(s)", &Class);
    goto LABEL_46;
  }
  v5 = 0;
  RtlAcquireResourceExclusive(&g_AadConnectMapLock, 1u);
  _m_prefetchw((const void *)&g_lAccountCacheLoaded);
  if ( !_InterlockedAnd(&g_lAccountCacheLoaded, 1u) )
  {
    if ( RegOpenKeyExW(hKey, L"SidMap", 0, 0x20019u, &hKeya) )
    {
      v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
      LODWORD(phkResult) = 89;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v6, phkResult, L"RegOpenKeyEx", L"SidMap");
    }
    else
    {
      v8 = RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      v3 = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          v3 = (unsigned __int16)v8 | 0xC0070000;
        v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
        LODWORD(phkResulta) = 110;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v3, v9, phkResulta, "RegQueryInfoKey", &Class);
        goto LABEL_42;
      }
      if ( cSubKeys )
      {
        v10 = cbMaxSubKeyLen + 1;
        if ( (unsigned int)v10 < cbMaxSubKeyLen )
        {
          cbMaxSubKeyLen = -1;
          v3 = -1073741675;
          v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
          LODWORD(phkResulta) = 120;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v28, phkResulta, "RtlDWordAdd", &Class);
          goto LABEL_42;
        }
        ++cbMaxSubKeyLen;
        v3 = RtlULongLongToULong(2 * v10, &cbMaxSubKeyLen);
        if ( v3 )
        {
          v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
          LODWORD(phkResulta) = 123;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v3, v11, phkResulta, "RtlDWordMult", &Class);
          goto LABEL_42;
        }
        v5 = (WCHAR *)LocalAlloc(0x40u, cbMaxSubKeyLen);
        if ( !v5 )
        {
          v3 = -1073741801;
          v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
          LODWORD(phkResulta) = 129;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v12, phkResulta, "LocalAlloc", &Class);
          goto LABEL_42;
        }
        for ( i = 0; i < cSubKeys; ++i )
        {
          cchName = cbMaxSubKeyLen >> 1;
          if ( RegEnumKeyExW(hKeya, i, v5, &cchName, 0, 0, 0, 0) )
          {
            v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
            LODWORD(phkResultb) = 149;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v15, v14, phkResultb, "RegEnumKeyEx", &Class);
          }
          else
          {
            v5[cchName] = 0;
            if ( hMem )
            {
              LocalFree(hMem);
              hMem = 0;
            }
            if ( ConvertStringSidToSidW(v5, &hMem) )
            {
              if ( hkey )
              {
                RegCloseKey(hkey);
                hkey = 0;
              }
              v18 = RegOpenKeyExW(hKeya, v5, 0, 0x20019u, &hkey);
              if ( v18 )
              {
                v20 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
                LODWORD(phkResultc) = 180;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v21, v20, phkResultc, "RegOpenKeyEx", v5);
              }
              else
              {
                if ( v2 )
                {
                  ((void (__fastcall *)(LPCWSTR, __int64, _QWORD))g_pLsaFunctionTable->FreeLsaHeap)(v2, v19, v18);
                  StringSid = 0;
                }
                v43 = 0;
                if ( (int)GetRegVal(hkey, L"InternetSid", 6u, &v43, (void **)&StringSid) >= 0 )
                {
                  if ( Sid )
                  {
                    LocalFree(Sid);
                    Sid = 0;
                  }
                  v2 = StringSid;
                  if ( ConvertStringSidToSidW(StringSid, &Sid) )
                  {
                    if ( (int)AddSidMapIntoCache(hMem, Sid) >= 0 )
                    {
                      hMem = 0;
                      Sid = 0;
                    }
                    else
                    {
                      v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
                      LODWORD(phkResultd) = 214;
                      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v27, v26, phkResultd, "AddSidMapIntoCache", &Class);
                    }
                  }
                  else
                  {
                    GetLastError();
                    GetLastError();
                    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
                    LODWORD(phkResultd) = 207;
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v25, v24, phkResultd, "ConvertStringSidToSidW", &Class);
                  }
                }
                else
                {
                  v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
                  LODWORD(phkResultd) = 195;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v23, v22, phkResultd, "GetStringRegVal", L"InternetSid");
                  v2 = StringSid;
                }
              }
            }
            else
            {
              GetLastError();
              GetLastError();
              v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
              LODWORD(phkResultb) = 162;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v17, v16, phkResultb, "ConvertStringSidToSidW", &Class);
            }
          }
        }
      }
    }
  }
  v3 = 0;
LABEL_42:
  _InterlockedOr(&g_lAccountCacheLoaded, 1u);
  RtlReleaseResource(&g_AadConnectMapLock);
  if ( v5 )
    LocalFree(v5);
  if ( v2 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v2);
LABEL_46:
  if ( hMem )
    LocalFree(hMem);
  if ( Sid )
    LocalFree(Sid);
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKeya )
    RegCloseKey(hKeya);
  return v3;
}

```

## disassembly

```asm
0x18003ea9c  push    rbp
0x18003ea9e  push    rbx
0x18003ea9f  push    rdi
0x18003eaa0  push    r12
0x18003eaa2  push    r13
0x18003eaa4  push    r14
0x18003eaa6  push    r15
0x18003eaa8  lea     rbp, [rsp-27h]
0x18003eaad  sub     rsp, 90h
0x18003eab4  xor     r12d, r12d
0x18003eab7  mov     rbx, rcx
0x18003eaba  mov     [rbp+57h+cSubKeys], r12d
0x18003eabe  mov     r14d, r12d
0x18003eac1  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x18003eac5  mov     [rbp+57h+StringSid], r12
0x18003eac9  mov     [rbp+57h+hMem], r12
0x18003eacd  mov     [rbp+57h+Sid], r12
0x18003ead1  mov     [rbp+57h+hKey], r12
0x18003ead5  mov     [rbp+57h+hkey], r12
0x18003ead9  test    rcx, rcx
0x18003eadc  jnz     short loc_18003EB28
0x18003eade  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003eae5  mov     ebx, 0C000000Dh
0x18003eaea  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003eaef  mov     r9, rax
0x18003eaf2  lea     rdi, Class
0x18003eaf9  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18003eb00  mov     [rsp+0C0h+lpcbMaxClassLen], rdi
0x18003eb05  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x18003eb0a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003eb11  mov     r8d, ebx
0x18003eb14  mov     dword ptr [rsp+0C0h+phkResult], 44h ; 'D'
0x18003eb1c  xor     ecx, ecx
0x18003eb1e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003eb23  jmp     loc_18003F075
0x18003eb28  mov     dl, 1; Wait
0x18003eb2a  lea     rcx, ?g_AadConnectMapLock@@3U_RTL_RESOURCE@@A; Resource
0x18003eb31  mov     r15, r12
0x18003eb34  call    cs:__imp_RtlAcquireResourceExclusive
0x18003eb3a  prefetchw byte ptr cs:?g_lAccountCacheLoaded@@3JC; long volatile g_lAccountCacheLoaded
0x18003eb41  mov     eax, cs:?g_lAccountCacheLoaded@@3JC; long volatile g_lAccountCacheLoaded
0x18003eb47  mov     ecx, eax
0x18003eb49  and     ecx, 1
0x18003eb4c  lock cmpxchg cs:?g_lAccountCacheLoaded@@3JC, ecx; long volatile g_lAccountCacheLoaded
0x18003eb54  jnz     short loc_18003EB47
0x18003eb56  test    eax, eax
0x18003eb58  jz      short loc_18003EB62
0x18003eb5a  mov     ebx, r12d
0x18003eb5d  jmp     loc_18003F03A
0x18003eb62  lea     rax, [rbp+57h+hKey]
0x18003eb66  mov     r9d, 20019h; samDesired
0x18003eb6c  lea     rdi, SubKey; "SidMap"
0x18003eb73  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18003eb78  mov     rdx, rdi; lpSubKey
0x18003eb7b  xor     r8d, r8d; ulOptions
0x18003eb7e  mov     rcx, rbx; hKey
0x18003eb81  call    cs:__imp_RegOpenKeyExW
0x18003eb87  mov     r8d, eax
0x18003eb8a  test    eax, eax
0x18003eb8c  jz      short loc_18003EBD3
0x18003eb8e  jle     short loc_18003EB9B
0x18003eb90  movzx   r8d, ax
0x18003eb94  or      r8d, 0C0070000h
0x18003eb9b  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003eba2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003eba7  mov     r9, rax
0x18003ebaa  mov     [rsp+0C0h+lpcbMaxClassLen], rdi
0x18003ebaf  lea     rax, aRegopenkeyex; "RegOpenKeyEx"
0x18003ebb6  xor     ecx, ecx
0x18003ebb8  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x18003ebbd  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003ebc4  mov     dword ptr [rsp+0C0h+phkResult], 59h ; 'Y'
0x18003ebcc  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003ebd1  jmp     short loc_18003EB5A
0x18003ebd3  mov     rcx, [rbp+57h+hKey]; hKey
0x18003ebd7  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18003ebdb  mov     [rsp+0C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18003ebe0  xor     r9d, r9d; lpReserved
0x18003ebe3  mov     [rsp+0C0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18003ebe8  xor     r8d, r8d; lpcchClass
0x18003ebeb  mov     [rsp+0C0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18003ebf0  xor     edx, edx; lpClass
0x18003ebf2  mov     [rsp+0C0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x18003ebf7  mov     [rsp+0C0h+lpcValues], r12; lpcValues
0x18003ebfc  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18003ec01  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18003ec06  lea     rax, [rbp+57h+cSubKeys]
0x18003ec0a  mov     [rsp+0C0h+phkResult], rax; lpcSubKeys
0x18003ec0f  call    cs:__imp_RegQueryInfoKeyW
0x18003ec15  mov     ebx, eax
0x18003ec17  test    eax, eax
0x18003ec19  jz      short loc_18003EC5A
0x18003ec1b  jle     short loc_18003EC26
0x18003ec1d  movzx   ebx, ax
0x18003ec20  or      ebx, 0C0070000h
0x18003ec26  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003ec2d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003ec32  mov     r9, rax
0x18003ec35  lea     rdi, Class
0x18003ec3c  mov     [rsp+0C0h+lpcbMaxClassLen], rdi
0x18003ec41  lea     rax, aRegqueryinfoke; "RegQueryInfoKey"
0x18003ec48  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x18003ec4d  mov     dword ptr [rsp+0C0h+phkResult], 6Eh ; 'n'
0x18003ec55  jmp     loc_18003F029
0x18003ec5a  cmp     [rbp+57h+cSubKeys], r12d
0x18003ec5e  jz      loc_18003EB5A
0x18003ec64  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18003ec67  lea     ecx, [rax+1]
0x18003ec6a  cmp     ecx, eax
0x18003ec6c  jb      loc_18003EFEE
0x18003ec72  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x18003ec75  lea     rdx, [rbp+57h+cbMaxSubKeyLen]; unsigned int *
0x18003ec79  add     rcx, rcx; unsigned __int64
0x18003ec7c  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x18003ec81  mov     ebx, eax
0x18003ec83  test    eax, eax
0x18003ec85  jz      short loc_18003ECBB
0x18003ec87  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003ec8e  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003ec93  mov     r9, rax
0x18003ec96  lea     rdi, Class
0x18003ec9d  mov     [rsp+0C0h+lpcbMaxClassLen], rdi
0x18003eca2  lea     rax, aRtldwordmult; "RtlDWordMult"
0x18003eca9  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x18003ecae  mov     dword ptr [rsp+0C0h+phkResult], 7Bh ; '{'
0x18003ecb6  jmp     loc_18003F029
0x18003ecbb  mov     edx, [rbp+57h+cbMaxSubKeyLen]; uBytes
0x18003ecbe  mov     ecx, 40h ; '@'; uFlags
0x18003ecc3  call    cs:__imp_LocalAlloc
0x18003ecc9  mov     r15, rax
0x18003eccc  test    rax, rax
0x18003eccf  jnz     short loc_18003ED0A
0x18003ecd1  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003ecd8  mov     ebx, 0C0000017h
0x18003ecdd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003ece2  mov     r9, rax
0x18003ece5  lea     rdi, Class
0x18003ecec  mov     [rsp+0C0h+lpcbMaxClassLen], rdi
0x18003ecf1  lea     rax, aLocalalloc; "LocalAlloc"
0x18003ecf8  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x18003ecfd  mov     dword ptr [rsp+0C0h+phkResult], 81h
0x18003ed05  jmp     loc_18003F029
0x18003ed0a  mov     ebx, r12d
0x18003ed0d  cmp     [rbp+57h+cSubKeys], r12d
0x18003ed11  jbe     loc_18003EB5A
0x18003ed17  lea     rdi, Class
0x18003ed1e  lea     r13, aInternetsid; "InternetSid"
0x18003ed25  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18003ed28  lea     r9, [rbp+57h+cchName]; lpcchName
0x18003ed2c  mov     rcx, [rbp+57h+hKey]; hKey
0x18003ed30  mov     r8, r15; lpName
0x18003ed33  mov     [rsp+0C0h+lpcValues], r12; lpftLastWriteTime
0x18003ed38  mov     edx, ebx; dwIndex
0x18003ed3a  shr     eax, 1
0x18003ed3c  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcchClass
0x18003ed41  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r12; lpClass
0x18003ed46  mov     [rbp+57h+cchName], eax
0x18003ed49  mov     [rsp+0C0h+phkResult], r12; lpReserved
0x18003ed4e  call    cs:__imp_RegEnumKeyExW
0x18003ed54  mov     r8d, eax
0x18003ed57  test    eax, eax
0x18003ed59  jz      short loc_18003EDA3
0x18003ed5b  jle     short loc_18003ED68
0x18003ed5d  movzx   r8d, ax
0x18003ed61  or      r8d, 0C0070000h
0x18003ed68  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003ed6f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003ed74  mov     [rsp+0C0h+lpcbMaxClassLen], rdi
0x18003ed79  mov     r9, rax
0x18003ed7c  lea     rax, aRegenumkeyex; "RegEnumKeyEx"
0x18003ed83  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x18003ed88  mov     dword ptr [rsp+0C0h+phkResult], 95h
0x18003ed90  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003ed97  xor     ecx, ecx
0x18003ed99  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003ed9e  jmp     loc_18003EFDE
0x18003eda3  mov     ecx, [rbp+57h+cchName]
0x18003eda6  mov     [r15+rcx*2], r12w
0x18003edab  mov     rcx, [rbp+57h+hMem]; hMem
0x18003edaf  test    rcx, rcx
0x18003edb2  jz      short loc_18003EDBE
0x18003edb4  call    cs:__imp_LocalFree
0x18003edba  mov     [rbp+57h+hMem], r12
0x18003edbe  lea     rdx, [rbp+57h+hMem]; Sid
0x18003edc2  mov     rcx, r15; StringSid
0x18003edc5  call    cs:__imp_ConvertStringSidToSidW
0x18003edcb  test    eax, eax
0x18003edcd  jnz     short loc_18003EE22
0x18003edcf  call    cs:__imp_GetLastError
0x18003edd5  test    eax, eax
0x18003edd7  jg      short loc_18003EDE4
0x18003edd9  call    cs:__imp_GetLastError
0x18003eddf  mov     r8d, eax
0x18003ede2  jmp     short loc_18003EDF5
0x18003ede4  call    cs:__imp_GetLastError
0x18003edea  movzx   r8d, ax
0x18003edee  or      r8d, 0C0070000h
0x18003edf5  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003edfc  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003ee01  mov     [rsp+0C0h+lpcbMaxClassLen], rdi
0x18003ee06  mov     r9, rax
0x18003ee09  lea     rax, aConvertstrings_1; "ConvertStringSidToSidW"
0x18003ee10  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x18003ee15  mov     dword ptr [rsp+0C0h+phkResult], 0A2h
0x18003ee1d  jmp     loc_18003ED90
0x18003ee22  mov     rcx, [rbp+57h+hkey]; hKey
0x18003ee26  test    rcx, rcx
0x18003ee29  jz      short loc_18003EE35
0x18003ee2b  call    cs:__imp_RegCloseKey
0x18003ee31  mov     [rbp+57h+hkey], r12
0x18003ee35  mov     rcx, [rbp+57h+hKey]; hKey
0x18003ee39  lea     rax, [rbp+57h+hkey]
0x18003ee3d  mov     r9d, 20019h; samDesired
0x18003ee43  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18003ee48  xor     r8d, r8d; ulOptions
0x18003ee4b  mov     rdx, r15; lpSubKey
0x18003ee4e  call    cs:__imp_RegOpenKeyExW
0x18003ee54  mov     r8d, eax
0x18003ee57  test    eax, eax
0x18003ee59  jz      short loc_18003EE95
0x18003ee5b  jle     short loc_18003EE68
0x18003ee5d  movzx   r8d, ax
0x18003ee61  or      r8d, 0C0070000h
0x18003ee68  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003ee6f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003ee74  mov     [rsp+0C0h+lpcbMaxClassLen], r15
0x18003ee79  mov     r9, rax
0x18003ee7c  lea     rax, aRegopenkeyex_0; "RegOpenKeyEx"
0x18003ee83  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x18003ee88  mov     dword ptr [rsp+0C0h+phkResult], 0B4h
0x18003ee90  jmp     loc_18003ED90
0x18003ee95  test    r14, r14
0x18003ee98  jz      short loc_18003EEB1
0x18003ee9a  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18003eea1  mov     rcx, r14
0x18003eea4  mov     rax, [rax+30h]
0x18003eea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eead  mov     [rbp+57h+StringSid], r12
0x18003eeb1  mov     rcx, [rbp+57h+hkey]; hkey
0x18003eeb5  lea     rax, [rbp+57h+StringSid]
0x18003eeb9  lea     r9, [rbp+57h+arg_18]; unsigned int *
0x18003eebd  mov     [rsp+0C0h+phkResult], rax; void **
0x18003eec2  mov     r8d, 6; dwFlags
0x18003eec8  mov     [rbp+57h+arg_18], r12d
0x18003eecc  mov     rdx, r13; lpValue
0x18003eecf  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x18003eed4  mov     r8d, eax
0x18003eed7  test    eax, eax
0x18003eed9  jns     short loc_18003EF1A
0x18003eedb  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003eee2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003eee7  mov     r9, rax
0x18003eeea  mov     [rsp+0C0h+lpcbMaxClassLen], r13
0x18003eeef  lea     rax, aGetstringregva_3; "GetStringRegVal"
0x18003eef6  xor     ecx, ecx
0x18003eef8  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x18003eefd  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003ef04  mov     dword ptr [rsp+0C0h+phkResult], 0C3h
0x18003ef0c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003ef11  mov     r14, [rbp+57h+StringSid]
0x18003ef15  jmp     loc_18003EFDE
0x18003ef1a  mov     rcx, [rbp+57h+Sid]; hMem
0x18003ef1e  test    rcx, rcx
0x18003ef21  jz      short loc_18003EF2D
0x18003ef23  call    cs:__imp_LocalFree
0x18003ef29  mov     [rbp+57h+Sid], r12
0x18003ef2d  mov     r14, [rbp+57h+StringSid]
0x18003ef31  lea     rdx, [rbp+57h+Sid]; Sid
0x18003ef35  mov     rcx, r14; StringSid
0x18003ef38  call    cs:__imp_ConvertStringSidToSidW
0x18003ef3e  test    eax, eax
0x18003ef40  jnz     short loc_18003EF95
0x18003ef42  call    cs:__imp_GetLastError
0x18003ef48  test    eax, eax
0x18003ef4a  jg      short loc_18003EF57
0x18003ef4c  call    cs:__imp_GetLastError
0x18003ef52  mov     r8d, eax
0x18003ef55  jmp     short loc_18003EF68
0x18003ef57  call    cs:__imp_GetLastError
0x18003ef5d  movzx   r8d, ax
0x18003ef61  or      r8d, 0C0070000h
0x18003ef68  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003ef6f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003ef74  mov     [rsp+0C0h+lpcbMaxClassLen], rdi
0x18003ef79  mov     r9, rax
0x18003ef7c  lea     rax, aConvertstrings_1; "ConvertStringSidToSidW"
0x18003ef83  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax
0x18003ef88  mov     dword ptr [rsp+0C0h+phkResult], 0CFh
0x18003ef90  jmp     loc_18003ED90
0x18003ef95  mov     rdx, [rbp+57h+Sid]
0x18003ef99  mov     rcx, [rbp+57h+hMem]
0x18003ef9d  call    AddSidMapIntoCache
0x18003efa2  mov     r8d, eax
0x18003efa5  test    eax, eax
0x18003efa7  jns     short loc_18003EFD6
0x18003efa9  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18003efb0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003efb5  mov     [rsp+0C0h+lpcbMaxClassLen], rdi
0x18003efba  mov     r9, rax
0x18003efbd  lea     rax, aAddsidmapintoc; "AddSidMapIntoCache"
  ... truncated ...
```
