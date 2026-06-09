# _CatDBInitConfigPara(void)

- ea: `0x180019e84`
- end: `0x180019fda`
- name: `?_CatDBInitConfigPara@@YAXXZ`
- size: `342`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ad54`

## callees

- `0x18000be40`
- `0x180019e84`
- `0x18001a5e4`
- `0x18001c9a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019ef3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019ef3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019fc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019fc2`

## string_xrefs

- `0x180019f0c`: `MaxEnumJetOpenMilliseconds`
- `0x180019f23`: `MaxFreezeJetOpenMilliseconds`
- `0x180019f3a`: `JetOpenAfterBootMilliseconds`
- `0x180019f6e`: `DontRemoveCatalogsDuringSync`

## pseudocode

```c
void _CatDBInitConfigPara(void)
{
  int v0; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF

  hKey = 0;
  g_CatDBConfigPara = 5000;
  dword_180032704 = 30000;
  qword_180032708 = 120000;
  dword_180032710 = CatDBIsSystemSetupInProgress();
  dword_180032714 = dword_180032710;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\CatalogDB", 0, 0x20019u, &hKey) )
  {
    CatDBUpdateConfigParaFromRegistry(hKey, L"MaxEnumJetOpenMilliseconds", &g_CatDBConfigPara);
    CatDBUpdateConfigParaFromRegistry(hKey, L"MaxFreezeJetOpenMilliseconds", &dword_180032704);
    CatDBUpdateConfigParaFromRegistry(hKey, L"JetOpenAfterBootMilliseconds", &qword_180032708);
    CatDBUpdateConfigParaFromRegistry(hKey, L"EnablePerformanceCounters", (char *)&qword_180032708 + 4);
    if ( !dword_180032714 )
    {
      v0 = 0;
      CatDBUpdateConfigParaFromRegistry(hKey, L"DontRemoveCatalogsDuringSync", &v0);
      dword_180032714 = v0 != 0;
    }
    v0 = 0;
    CatDBUpdateConfigParaFromRegistry(hKey, L"SyncIgnoreCatalogTimeChangesOnce", &v0);
    dword_180032718 = v0 != 0;
    dword_18003271C = v0 != 0;
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x180019e84  push    rbp
0x180019e86  mov     rbp, rsp
0x180019e89  sub     rsp, 50h
0x180019e8d  mov     rax, cs:__security_cookie
0x180019e94  xor     rax, rsp
0x180019e97  mov     [rbp+var_10], rax
0x180019e9b  mov     [rbp+hKey], 0
0x180019ea3  mov     cs:?g_CatDBConfigPara@@3U_CATDB_CONFIG_PARA@@A, 1388h; _CATDB_CONFIG_PARA g_CatDBConfigPara
0x180019ead  mov     cs:dword_180032704, 7530h
0x180019eb7  mov     cs:qword_180032708, 1D4C0h
0x180019ec2  call    _CatDBIsSystemSetupInProgress
0x180019ec7  mov     cs:dword_180032710, eax
0x180019ecd  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Cryptography\\Cata"...
0x180019ed4  mov     cs:dword_180032714, eax
0x180019eda  mov     r9d, 20019h; samDesired
0x180019ee0  lea     rax, [rbp+hKey]
0x180019ee4  xor     r8d, r8d; ulOptions
0x180019ee7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019eee  mov     [rsp+50h+phkResult], rax; phkResult
0x180019ef3  call    cs:__imp_RegOpenKeyExW
0x180019ef9  test    eax, eax
0x180019efb  jnz     loc_180019FC8
0x180019f01  mov     rcx, [rbp+hKey]
0x180019f05  lea     r8, ?g_CatDBConfigPara@@3U_CATDB_CONFIG_PARA@@A; _CATDB_CONFIG_PARA g_CatDBConfigPara
0x180019f0c  lea     rdx, aMaxenumjetopen; "MaxEnumJetOpenMilliseconds"
0x180019f13  call    _CatDBUpdateConfigParaFromRegistry
0x180019f18  mov     rcx, [rbp+hKey]
0x180019f1c  lea     r8, dword_180032704
0x180019f23  lea     rdx, aMaxfreezejetop; "MaxFreezeJetOpenMilliseconds"
0x180019f2a  call    _CatDBUpdateConfigParaFromRegistry
0x180019f2f  mov     rcx, [rbp+hKey]
0x180019f33  lea     r8, qword_180032708
0x180019f3a  lea     rdx, aJetopenafterbo; "JetOpenAfterBootMilliseconds"
0x180019f41  call    _CatDBUpdateConfigParaFromRegistry
0x180019f46  mov     rcx, [rbp+hKey]
0x180019f4a  lea     r8, qword_180032708+4
0x180019f51  lea     rdx, aEnableperforma; "EnablePerformanceCounters"
0x180019f58  call    _CatDBUpdateConfigParaFromRegistry
0x180019f5d  cmp     cs:dword_180032714, 0
0x180019f64  jnz     short loc_180019F8F
0x180019f66  mov     rcx, [rbp+hKey]
0x180019f6a  lea     r8, [rbp+var_20]
0x180019f6e  lea     rdx, aDontremovecata; "DontRemoveCatalogsDuringSync"
0x180019f75  mov     [rbp+var_20], 0
0x180019f7c  call    _CatDBUpdateConfigParaFromRegistry
0x180019f81  xor     eax, eax
0x180019f83  cmp     [rbp+var_20], eax
0x180019f86  setnz   al
0x180019f89  mov     cs:dword_180032714, eax
0x180019f8f  mov     rcx, [rbp+hKey]
0x180019f93  lea     r8, [rbp+var_20]
0x180019f97  lea     rdx, aSyncignorecata; "SyncIgnoreCatalogTimeChangesOnce"
0x180019f9e  mov     [rbp+var_20], 0
0x180019fa5  call    _CatDBUpdateConfigParaFromRegistry
0x180019faa  mov     rcx, [rbp+hKey]; hKey
0x180019fae  xor     eax, eax
0x180019fb0  cmp     [rbp+var_20], eax
0x180019fb3  setnz   al
0x180019fb6  mov     cs:dword_180032718, eax
0x180019fbc  mov     cs:dword_18003271C, eax
0x180019fc2  call    cs:__imp_RegCloseKey
0x180019fc8  mov     rcx, [rbp+var_10]
0x180019fcc  xor     rcx, rsp; StackCookie
0x180019fcf  call    __security_check_cookie
0x180019fd4  add     rsp, 50h
0x180019fd8  pop     rbp
0x180019fd9  retn
```
