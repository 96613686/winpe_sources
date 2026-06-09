# InitializePlugins(void)

- ea: `0x180019e48`
- end: `0x18001a5c2`
- name: `?InitializePlugins@@YAJXZ`
- size: `1914`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048d70`
- `0x18004b1e0`

## callees

- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x180019e48`
- `0x18001a5d0`
- `0x18001a624`
- `0x18001b4c0`
- `0x180042410`
- `0x18004317c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a300`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a560`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a56f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a597`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a300`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a560`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a56f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a597`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001a08d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001a08d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a003`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a003`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001a250`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001a250`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019ec4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a326`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019ec4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a326`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180019f8d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180019fc3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180019f8d`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180019fc3`

## string_xrefs

- `0x180019f07`: `RegOpenKeyEx`
- `0x18001a20e`: `RegOpenKeyEx`
- `0x180019fb9`: `Software\Microsoft\IdentityStore\LogonCache`
- `0x180019fae`: `IDStoreLogonCache`
- `0x180019edb`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a01a`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a0a4`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a10c`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a185`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a1cc`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a200`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a4d8`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a516`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18001a035`: `RegCreateKeyEx`
- `0x18001a4aa`: `RtlStringCchCopyNW`
- `0x18001a406`: `LoadPlugin`

## pseudocode

```c
__int64 InitializePlugins(void)
{
  DWORD v0; // r15d
  WCHAR *v1; // r14
  unsigned int v2; // ebx
  const char *v3; // r9
  const char *v4; // rax
  bool v5; // zf
  const char *v6; // r9
  __int64 v7; // r8
  const wchar_t *v8; // r13
  int PersistedRegistryLocationW; // eax
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  const char *v13; // r9
  __int64 v14; // r8
  __int64 v15; // rcx
  unsigned __int64 v16; // rcx
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r8
  const char *v21; // r9
  __int64 v22; // r8
  char *v23; // rbx
  const char *v24; // r9
  __int64 v25; // r8
  const char *v26; // r9
  const char *v27; // r9
  __int64 v28; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+20h] [rbp-E0h]
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  bool v35; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY v40; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v42; // [rsp+84h] [rbp-7Ch] BYREF
  HKEY v43; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v44[40]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v45[264]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v46[528]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v47[528]; // [rsp+500h] [rbp+400h] BYREF

  v0 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  dwDisposition = 0;
  v42 = 0;
  v35 = 0;
  hKey = 0;
  v1 = 0;
  v40 = 0;
  v43 = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\IdentityStore\\Providers", 0, 0x20019u, &hKey);
  if ( v2 )
  {
    v3 = "";
    while ( 1 )
    {
      v4 = v3--;
      v5 = *v3 == 92;
      if ( *v3 == 92 )
        break;
      if ( v3 <= "onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp" )
      {
        v5 = *v3 == 92;
        break;
      }
    }
    if ( v5 )
      v3 = v4;
    LODWORD(phkResult) = 777;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v2, v3, phkResult, "RegOpenKeyEx", &Class);
    if ( v2 - 2 > 1 )
    {
      if ( (int)v2 > 0 )
        v2 = (unsigned __int16)v2 | 0xC0070000;
      v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      samDesired = "RegOpenKeyEx";
      LODWORD(phkResulta) = 785;
      goto LABEL_12;
    }
LABEL_55:
    v2 = 0;
    goto LABEL_59;
  }
  v8 = (const wchar_t *)v46;
  if ( (unsigned int)GetPersistedRegistryLocationW(
                       L"IDStoreLoadParameters",
                       L"Software\\Microsoft\\IdentityStore\\LoadParameters",
                       v46,
                       520,
                       0) )
    v8 = L"Software\\Microsoft\\IdentityStore\\LoadParameters";
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"IDStoreLogonCache",
                                 L"Software\\Microsoft\\IdentityStore\\LogonCache",
                                 v47,
                                 520,
                                 0);
  v10 = (const WCHAR *)v47;
  if ( PersistedRegistryLocationW )
    v10 = L"Software\\Microsoft\\IdentityStore\\LogonCache";
  v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0, 0, 0xF003Fu, 0, &v43, &dwDisposition);
  v2 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v2 = (unsigned __int16)v11 | 0xC0070000;
    v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    samDesired = (const char *)L"RegCreateKeyEx";
    LODWORD(phkResulta) = 833;
    goto LABEL_12;
  }
  v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v2 = v12;
  if ( v12 )
  {
    if ( v12 > 0 )
      v2 = (unsigned __int16)v12 | 0xC0070000;
    v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    samDesired = "RegQueryInfoKey";
    LODWORD(phkResulta) = 853;
    goto LABEL_12;
  }
  if ( !cSubKeys )
    goto LABEL_55;
  g_pPlugins = (struct _ApPluginPkg *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(392 * cSubKeys);
  if ( !g_pPlugins )
  {
    v2 = -1073741801;
    v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    LODWORD(phkResulta) = 866;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v13, phkResulta, "AllocateLsaHeap", &Class);
    goto LABEL_59;
  }
  v15 = cbMaxSubKeyLen + 1;
  if ( (unsigned int)v15 < cbMaxSubKeyLen )
  {
    cbMaxSubKeyLen = -1;
    v2 = -1073741675;
    v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    samDesired = "RtlDWordAdd";
    LODWORD(phkResulta) = 870;
    goto LABEL_58;
  }
  v16 = 2 * v15;
  if ( v16 > 0xFFFFFFFF )
  {
    cbMaxSubKeyLen = -1;
    v2 = -1073741675;
    v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    LODWORD(phkResulta) = 873;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v28, v27, phkResulta, "RtlDWordMult", &Class);
    goto LABEL_59;
  }
  cbMaxSubKeyLen = v16;
  v1 = (WCHAR *)((__int64 (*)(void))g_pLsaFunctionTable->AllocateLsaHeap)();
  if ( !v1 )
  {
    v2 = -1073741801;
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
    LODWORD(phkResulta) = 879;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v18, v17, phkResulta, "AllocateLsaHeap", &Class);
    goto LABEL_59;
  }
  v2 = IsDomainJoined(&v35);
  if ( !v2 )
  {
    while ( v0 < cSubKeys )
    {
      cchName = cbMaxSubKeyLen >> 1;
      if ( RegEnumKeyExW(hKey, v0, v1, &cchName, 0, 0, 0, 0) )
      {
        v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
        LODWORD(phkResulta) = 903;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v19, phkResulta, "RegEnumKeyEx", &Class);
      }
      else
      {
        v1[cchName] = 0;
        if ( cchName >= 0x26 && *v1 == 123 && v1[cchName - 1] == 125 )
        {
          if ( cchName - 2 > 0x7FFFFFFEuLL )
          {
            v2 = -1073741811;
            v44[0] = 0;
LABEL_54:
            v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
            samDesired = "RtlStringCchCopyNW";
            LODWORD(phkResulta) = 918;
            goto LABEL_12;
          }
          v2 = RtlStringCopyWorkerW((unsigned int)v44, 37, 0, (int)v1 + 2, cchName - 2);
          if ( v2 )
            goto LABEL_54;
          if ( v40 )
          {
            RegCloseKey(v40);
            v40 = 0;
          }
          if ( RegOpenKeyExW(hKey, v1, 0, 0x20019u, &v40) )
          {
            v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
            LODWORD(phkResultb) = 935;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v22, v21, phkResultb, "RegOpenKeyEx", &Class);
          }
          else
          {
            memset_0(v45, 0, 0x208u);
            v2 = RtlStringCchPrintfW(v45, 0x104u, L"%ws\\%ws", v8, v1);
            if ( v2 )
            {
              v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
              samDesired = "RtlStringCchPrintfW";
              LODWORD(phkResulta) = 942;
              goto LABEL_12;
            }
            v23 = (char *)g_pPlugins + 392 * g_cPlugins;
            memset_0(v23, 0, 0x188u);
            if ( (unsigned int)LoadPlugin(v35, v40, v43, v44, v45, (struct _ApPluginPkg *)v23, &v42) )
            {
              v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
              LODWORD(phkResultc) = 956;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v25, v24, phkResultc, "LoadPlugin", v44);
            }
            else
            {
              ++g_cPlugins;
            }
          }
        }
        else
        {
          v26 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
          LODWORD(phkResulta) = 913;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221227787LL, v26, phkResulta, "Bad GUID", v1);
        }
      }
      ++v0;
    }
    goto LABEL_55;
  }
  v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
  samDesired = "IsDomainJoined";
  LODWORD(phkResulta) = 883;
LABEL_12:
  v7 = v2;
LABEL_58:
  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v6, phkResulta, samDesired, &Class);
LABEL_59:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v43 )
    RegCloseKey(v43);
  if ( v1 )
    ((void (__fastcall *)(WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v1);
  if ( v40 )
    RegCloseKey(v40);
  return v2;
}

```

## disassembly

```asm
0x180019e48  push    rbp
0x180019e4a  push    rbx
0x180019e4b  push    rsi
0x180019e4c  push    rdi
0x180019e4d  push    r12
0x180019e4f  push    r13
0x180019e51  push    r14
0x180019e53  push    r15
0x180019e55  lea     rbp, [rsp-628h]
0x180019e5d  sub     rsp, 728h
0x180019e64  mov     rax, cs:__security_cookie
0x180019e6b  xor     rax, rsp
0x180019e6e  mov     [rbp+660h+var_50], rax
0x180019e75  xor     r15d, r15d
0x180019e78  lea     rax, [rsp+760h+hKey]
0x180019e7d  mov     rdi, 0FFFFFFFF80000002h
0x180019e84  mov     [rsp+760h+cSubKeys], r15d
0x180019e89  mov     rcx, rdi; hKey
0x180019e8c  mov     [rsp+760h+cbMaxSubKeyLen], r15d
0x180019e91  mov     r9d, 20019h; samDesired
0x180019e97  mov     [rbp+660h+dwDisposition], r15d
0x180019e9b  xor     r8d, r8d; ulOptions
0x180019e9e  mov     [rbp+660h+var_6DC], r15d
0x180019ea2  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\IdentityStore\\Pro"...
0x180019ea9  mov     [rsp+760h+var_700], r15b
0x180019eae  mov     [rsp+760h+hKey], r15
0x180019eb3  mov     r14d, r15d
0x180019eb6  mov     [rsp+760h+var_6E8], r15
0x180019ebb  mov     [rbp+660h+var_6D8], r15
0x180019ebf  mov     [rsp+760h+phkResult], rax; phkResult
0x180019ec4  call    cs:__imp_RegOpenKeyExW
0x180019eca  mov     ebx, eax
0x180019ecc  test    eax, eax
0x180019ece  jz      loc_180019F6A
0x180019ed4  lea     r9, aOnecoreDsExtCl+2Eh; ""
0x180019edb  lea     rdi, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x180019ee2  mov     rax, r9
0x180019ee5  dec     r9
0x180019ee8  cmp     byte ptr [r9], 5Ch ; '\'
0x180019eec  jz      short loc_180019EF7
0x180019eee  cmp     r9, rdi
0x180019ef1  ja      short loc_180019EE2
0x180019ef3  cmp     byte ptr [r9], 5Ch ; '\'
0x180019ef7  cmovz   r9, rax
0x180019efb  lea     rsi, Class
0x180019f02  mov     [rsp+760h+lpSecurityAttributes], rsi
0x180019f07  lea     r12, aRegopenkeyex_0; "RegOpenKeyEx"
0x180019f0e  mov     qword ptr [rsp+760h+samDesired], r12
0x180019f13  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180019f1a  mov     r8d, ebx
0x180019f1d  mov     dword ptr [rsp+760h+phkResult], 309h
0x180019f25  xor     ecx, ecx
0x180019f27  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180019f2c  lea     eax, [rbx-2]
0x180019f2f  cmp     eax, 1
0x180019f32  jbe     loc_18001A4C6
0x180019f38  test    ebx, ebx
0x180019f3a  jle     short loc_180019F45
0x180019f3c  movzx   ebx, bx
0x180019f3f  or      ebx, 0C0070000h
0x180019f45  mov     rcx, rdi; char *
0x180019f48  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180019f4d  mov     [rsp+760h+lpSecurityAttributes], rsi
0x180019f52  mov     r9, rax
0x180019f55  mov     qword ptr [rsp+760h+samDesired], r12
0x180019f5a  mov     dword ptr [rsp+760h+phkResult], 311h
0x180019f62  mov     r8d, ebx
0x180019f65  jmp     loc_18001A548
0x180019f6a  lea     rbx, aSoftwareMicros_3; "Software\\Microsoft\\IdentityStore\\Loa"...
0x180019f71  mov     [rsp+760h+phkResult], r15
0x180019f76  mov     rdx, rbx
0x180019f79  lea     r8, [rbp+660h+var_470]
0x180019f80  mov     r9d, 208h
0x180019f86  lea     rcx, aIdstoreloadpar; "IDStoreLoadParameters"
0x180019f8d  call    cs:__imp_GetPersistedRegistryLocationW
0x180019f93  lea     r13, [rbp+660h+var_470]
0x180019f9a  mov     [rsp+760h+phkResult], r15
0x180019f9f  test    eax, eax
0x180019fa1  lea     r8, [rbp+660h+var_260]
0x180019fa8  mov     r9d, 208h
0x180019fae  lea     rcx, aIdstorelogonca; "IDStoreLogonCache"
0x180019fb5  cmovnz  r13, rbx
0x180019fb9  lea     rbx, aSoftwareMicros_1; "Software\\Microsoft\\IdentityStore\\Log"...
0x180019fc0  mov     rdx, rbx
0x180019fc3  call    cs:__imp_GetPersistedRegistryLocationW
0x180019fc9  lea     rdx, [rbp+660h+var_260]
0x180019fd0  mov     rcx, rdi; hKey
0x180019fd3  test    eax, eax
0x180019fd5  lea     rax, [rbp+660h+dwDisposition]
0x180019fd9  mov     [rsp+760h+lpdwDisposition], rax; lpdwDisposition
0x180019fde  lea     rax, [rbp+660h+var_6D8]
0x180019fe2  mov     [rsp+760h+var_728], rax; phkResult
0x180019fe7  cmovnz  rdx, rbx; lpSubKey
0x180019feb  mov     [rsp+760h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180019ff0  xor     r9d, r9d; lpClass
0x180019ff3  mov     [rsp+760h+samDesired], 0F003Fh; samDesired
0x180019ffb  xor     r8d, r8d; Reserved
0x180019ffe  mov     dword ptr [rsp+760h+phkResult], r15d; dwOptions
0x18001a003  call    cs:__imp_RegCreateKeyExW
0x18001a009  mov     ebx, eax
0x18001a00b  test    eax, eax
0x18001a00d  jz      short loc_18001A04E
0x18001a00f  jle     short loc_18001A01A
0x18001a011  movzx   ebx, ax
0x18001a014  or      ebx, 0C0070000h
0x18001a01a  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a021  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a026  mov     r9, rax
0x18001a029  lea     rsi, Class
0x18001a030  mov     [rsp+760h+lpSecurityAttributes], rsi
0x18001a035  lea     rax, aRegcreatekeyex_0; "RegCreateKeyEx"
0x18001a03c  mov     qword ptr [rsp+760h+samDesired], rax
0x18001a041  mov     dword ptr [rsp+760h+phkResult], 341h
0x18001a049  jmp     loc_180019F62
0x18001a04e  mov     rcx, [rsp+760h+hKey]; hKey
0x18001a053  lea     rax, [rsp+760h+cbMaxSubKeyLen]
0x18001a058  mov     [rsp+760h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18001a05d  xor     r9d, r9d; lpReserved
0x18001a060  mov     [rsp+760h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001a065  xor     r8d, r8d; lpcchClass
0x18001a068  mov     [rsp+760h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001a06d  xor     edx, edx; lpClass
0x18001a06f  mov     [rsp+760h+lpdwDisposition], r15; lpcbMaxValueNameLen
0x18001a074  mov     [rsp+760h+var_728], r15; lpcValues
0x18001a079  mov     [rsp+760h+lpSecurityAttributes], r15; lpcbMaxClassLen
0x18001a07e  mov     qword ptr [rsp+760h+samDesired], rax; lpcbMaxSubKeyLen
0x18001a083  lea     rax, [rsp+760h+cSubKeys]
0x18001a088  mov     [rsp+760h+phkResult], rax; lpcSubKeys
0x18001a08d  call    cs:__imp_RegQueryInfoKeyW
0x18001a093  mov     ebx, eax
0x18001a095  test    eax, eax
0x18001a097  jz      short loc_18001A0D8
0x18001a099  jle     short loc_18001A0A4
0x18001a09b  movzx   ebx, ax
0x18001a09e  or      ebx, 0C0070000h
0x18001a0a4  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a0ab  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a0b0  mov     r9, rax
0x18001a0b3  lea     rsi, Class
0x18001a0ba  mov     [rsp+760h+lpSecurityAttributes], rsi
0x18001a0bf  lea     rax, aRegqueryinfoke; "RegQueryInfoKey"
0x18001a0c6  mov     qword ptr [rsp+760h+samDesired], rax
0x18001a0cb  mov     dword ptr [rsp+760h+phkResult], 355h
0x18001a0d3  jmp     loc_180019F62
0x18001a0d8  mov     eax, [rsp+760h+cSubKeys]
0x18001a0dc  test    eax, eax
0x18001a0de  jz      loc_18001A4C6
0x18001a0e4  imul    ecx, eax, 188h
0x18001a0ea  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001a0f1  mov     rax, [rax+28h]
0x18001a0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0fa  mov     cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA, rax; _ApPluginPkg * g_pPlugins
0x18001a101  test    rax, rax
0x18001a104  jnz     short loc_18001A143
0x18001a106  mov     r8d, 0C0000017h
0x18001a10c  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a113  mov     ebx, r8d
0x18001a116  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a11b  mov     r9, rax
0x18001a11e  lea     rsi, Class
0x18001a125  mov     [rsp+760h+lpSecurityAttributes], rsi
0x18001a12a  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18001a131  mov     qword ptr [rsp+760h+samDesired], rax
0x18001a136  mov     dword ptr [rsp+760h+phkResult], 362h
0x18001a13e  jmp     loc_18001A548
0x18001a143  mov     eax, [rsp+760h+cbMaxSubKeyLen]
0x18001a147  lea     ecx, [rax+1]
0x18001a14a  cmp     ecx, eax
0x18001a14c  mov     eax, 0FFFFFFFFh
0x18001a151  jb      loc_18001A50C
0x18001a157  add     rcx, rcx
0x18001a15a  cmp     rcx, rax
0x18001a15d  ja      loc_18001A4CE
0x18001a163  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18001a16a  mov     [rsp+760h+cbMaxSubKeyLen], ecx
0x18001a16e  mov     rax, [rax+28h]
0x18001a172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a177  mov     r14, rax
0x18001a17a  test    rax, rax
0x18001a17d  jnz     short loc_18001A1BC
0x18001a17f  mov     r8d, 0C0000017h
0x18001a185  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a18c  mov     ebx, r8d
0x18001a18f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a194  mov     r9, rax
0x18001a197  lea     rsi, Class
0x18001a19e  mov     [rsp+760h+lpSecurityAttributes], rsi
0x18001a1a3  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18001a1aa  mov     qword ptr [rsp+760h+samDesired], rax
0x18001a1af  mov     dword ptr [rsp+760h+phkResult], 36Fh
0x18001a1b7  jmp     loc_18001A548
0x18001a1bc  lea     rcx, [rsp+760h+var_700]; bool *
0x18001a1c1  call    ?IsDomainJoined@@YAJPEA_N@Z; IsDomainJoined(bool *)
0x18001a1c6  mov     ebx, eax
0x18001a1c8  test    eax, eax
0x18001a1ca  jz      short loc_18001A200
0x18001a1cc  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a1d3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a1d8  mov     r9, rax
0x18001a1db  lea     rsi, Class
0x18001a1e2  mov     [rsp+760h+lpSecurityAttributes], rsi
0x18001a1e7  lea     rax, aIsdomainjoined; "IsDomainJoined"
0x18001a1ee  mov     qword ptr [rsp+760h+samDesired], rax
0x18001a1f3  mov     dword ptr [rsp+760h+phkResult], 373h
0x18001a1fb  jmp     loc_180019F62
0x18001a200  lea     rdi, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18001a207  lea     rsi, Class
0x18001a20e  lea     r12, aRegopenkeyex_0; "RegOpenKeyEx"
0x18001a215  cmp     r15d, [rsp+760h+cSubKeys]
0x18001a21a  jnb     loc_18001A4C3
0x18001a220  mov     eax, [rsp+760h+cbMaxSubKeyLen]
0x18001a224  lea     r9, [rsp+760h+cchName]; lpcchName
0x18001a229  mov     rcx, [rsp+760h+hKey]; hKey
0x18001a22e  xor     ebx, ebx
0x18001a230  mov     [rsp+760h+var_728], rbx; lpftLastWriteTime
0x18001a235  mov     r8, r14; lpName
0x18001a238  mov     [rsp+760h+lpSecurityAttributes], rbx; lpcchClass
0x18001a23d  mov     edx, r15d; dwIndex
0x18001a240  shr     eax, 1
0x18001a242  mov     qword ptr [rsp+760h+samDesired], rbx; lpClass
0x18001a247  mov     [rsp+760h+phkResult], rbx; lpReserved
0x18001a24c  mov     [rsp+760h+cchName], eax
0x18001a250  call    cs:__imp_RegEnumKeyExW
0x18001a256  mov     r8d, eax
0x18001a259  test    eax, eax
0x18001a25b  jz      short loc_18001A293
0x18001a25d  jle     short loc_18001A26A
0x18001a25f  movzx   r8d, ax
0x18001a263  or      r8d, 0C0070000h
0x18001a26a  mov     rcx, rdi; char *
0x18001a26d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a272  mov     [rsp+760h+lpSecurityAttributes], rsi
0x18001a277  mov     r9, rax
0x18001a27a  lea     rax, aRegenumkeyex; "RegEnumKeyEx"
0x18001a281  mov     qword ptr [rsp+760h+samDesired], rax
0x18001a286  mov     dword ptr [rsp+760h+phkResult], 387h
0x18001a28e  jmp     loc_18001A44E
0x18001a293  mov     ecx, [rsp+760h+cchName]
0x18001a297  mov     [r14+rcx*2], bx
0x18001a29c  mov     edx, [rsp+760h+cchName]
0x18001a2a0  cmp     edx, 26h ; '&'
0x18001a2a3  jb      loc_18001A424
0x18001a2a9  cmp     word ptr [r14], 7Bh ; '{'
0x18001a2ae  jnz     loc_18001A424
0x18001a2b4  lea     eax, [rdx-1]
0x18001a2b7  cmp     word ptr [r14+rax*2], 7Dh ; '}'
0x18001a2bd  jnz     loc_18001A424
0x18001a2c3  lea     ecx, [rdx-2]
0x18001a2c6  cmp     rcx, 7FFFFFFEh
0x18001a2cd  ja      loc_18001A48D
0x18001a2d3  mov     [rsp+760h+phkResult], rcx
0x18001a2d8  lea     r9, [r14+2]
0x18001a2dc  lea     rcx, [rbp+660h+var_6D0]
0x18001a2e0  mov     edx, 25h ; '%'
0x18001a2e5  call    RtlStringCopyWorkerW
0x18001a2ea  mov     ebx, eax
0x18001a2ec  test    eax, eax
0x18001a2ee  jnz     loc_18001A49A
0x18001a2f4  mov     rcx, [rsp+760h+var_6E8]; hKey
0x18001a2f9  xor     ebx, ebx
0x18001a2fb  test    rcx, rcx
0x18001a2fe  jz      short loc_18001A30B
0x18001a300  call    cs:__imp_RegCloseKey
0x18001a306  mov     [rsp+760h+var_6E8], rbx
0x18001a30b  mov     rcx, [rsp+760h+hKey]; hKey
0x18001a310  lea     rax, [rsp+760h+var_6E8]
0x18001a315  mov     r9d, 20019h; samDesired
0x18001a31b  mov     [rsp+760h+phkResult], rax; phkResult
0x18001a320  xor     r8d, r8d; ulOptions
0x18001a323  mov     rdx, r14; lpSubKey
0x18001a326  call    cs:__imp_RegOpenKeyExW
0x18001a32c  mov     r8d, eax
0x18001a32f  test    eax, eax
0x18001a331  jz      short loc_18001A362
0x18001a333  jle     short loc_18001A340
0x18001a335  movzx   r8d, ax
0x18001a339  or      r8d, 0C0070000h
0x18001a340  mov     rcx, rdi; char *
0x18001a343  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001a348  mov     [rsp+760h+lpSecurityAttributes], rsi
0x18001a34d  mov     r9, rax
0x18001a350  mov     qword ptr [rsp+760h+samDesired], r12
0x18001a355  mov     dword ptr [rsp+760h+phkResult], 3A7h
0x18001a35d  jmp     loc_18001A44E
0x18001a362  xor     edx, edx; Val
0x18001a364  lea     rcx, [rbp+660h+var_680]; void *
0x18001a368  mov     r8d, 208h; Size
0x18001a36e  call    memset_0
0x18001a373  mov     r9, r13
0x18001a376  mov     [rsp+760h+phkResult], r14
0x18001a37b  lea     r8, aWsWs_1; "%ws\\%ws"
0x18001a382  mov     edx, 104h; unsigned __int64
0x18001a387  lea     rcx, [rbp+660h+var_680]; unsigned __int16 *
0x18001a38b  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a390  mov     ebx, eax
0x18001a392  test    eax, eax
0x18001a394  jnz     loc_18001A464
0x18001a39a  mov     eax, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x18001a3a0  xor     edx, edx; Val
0x18001a3a2  imul    rbx, rax, 188h
  ... truncated ...
```
