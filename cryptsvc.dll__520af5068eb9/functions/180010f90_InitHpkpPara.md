# InitHpkpPara

- ea: `0x180010f90`
- end: `0x1800110ab`
- name: `InitHpkpPara`
- size: `283`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d548`

## callees

- `0x18000c370`
- `0x180010f90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001109f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001109f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010ff3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010ff3`

## string_xrefs

- `0x180010fbd`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`
- `0x180011033`: `HpkpMinDeltaUpdateSeconds`

## pseudocode

```c
LSTATUS InitHpkpPara()
{
  LSTATUS result; // eax
  int v1; // [rsp+40h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+18h] BYREF

  hKey = 0;
  dword_18002033C = 86400;
  dword_180020340 = 604800;
  dword_180020344 = 2592000;
  dword_180020348 = 100;
  dword_18002034C = 1000;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config",
             0,
             0x20119u,
             &hKey);
  if ( !result )
  {
    v1 = 0;
    UpdatePreFetchParaFromRegistry(hKey, L"HpkpDisable", &v1);
    if ( v1 )
      g_HpkpPara = 1;
    UpdatePreFetchParaFromRegistry(hKey, L"HpkpMinDeltaUpdateSeconds", &dword_18002033C);
    UpdatePreFetchParaFromRegistry(hKey, L"HpkpMinMaxAgeSeconds", &dword_180020340);
    UpdatePreFetchParaFromRegistry(hKey, L"HpkpMaxMaxAgeSeconds", &dword_180020344);
    UpdatePreFetchParaFromRegistry(hKey, L"HpkpMaxPendingCount", &dword_180020348);
    UpdatePreFetchParaFromRegistry(hKey, L"HpkpMaxDomainCount", &dword_18002034C);
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x180010f90  push    rbp
0x180010f92  mov     rbp, rsp
0x180010f95  sub     rsp, 30h
0x180010f99  lea     rax, [rbp+hKey]
0x180010f9d  mov     [rbp+hKey], 0
0x180010fa5  mov     r9d, 20119h; samDesired
0x180010fab  mov     [rsp+30h+phkResult], rax; phkResult
0x180010fb0  xor     r8d, r8d; ulOptions
0x180010fb3  mov     cs:dword_18002033C, 15180h
0x180010fbd  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\OID"...
0x180010fc4  mov     cs:dword_180020340, 93A80h
0x180010fce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010fd5  mov     cs:dword_180020344, 278D00h
0x180010fdf  mov     cs:dword_180020348, 64h ; 'd'
0x180010fe9  mov     cs:dword_18002034C, 3E8h
0x180010ff3  call    cs:__imp_RegOpenKeyExW
0x180010ff9  test    eax, eax
0x180010ffb  jnz     loc_1800110A5
0x180011001  mov     rcx, [rbp+hKey]
0x180011005  lea     r8, [rbp+arg_0]
0x180011009  lea     rdx, aHpkpdisable; "HpkpDisable"
0x180011010  mov     [rbp+arg_0], eax
0x180011013  call    UpdatePreFetchParaFromRegistry
0x180011018  cmp     [rbp+arg_0], 0
0x18001101c  jz      short loc_180011028
0x18001101e  mov     cs:g_HpkpPara, 1
0x180011028  mov     rcx, [rbp+hKey]
0x18001102c  lea     r8, dword_18002033C
0x180011033  lea     rdx, aHpkpmindeltaup; "HpkpMinDeltaUpdateSeconds"
0x18001103a  call    UpdatePreFetchParaFromRegistry
0x18001103f  mov     rcx, [rbp+hKey]
0x180011043  lea     r8, dword_180020340
0x18001104a  lea     rdx, aHpkpminmaxages; "HpkpMinMaxAgeSeconds"
0x180011051  call    UpdatePreFetchParaFromRegistry
0x180011056  mov     rcx, [rbp+hKey]
0x18001105a  lea     r8, dword_180020344
0x180011061  lea     rdx, aHpkpmaxmaxages; "HpkpMaxMaxAgeSeconds"
0x180011068  call    UpdatePreFetchParaFromRegistry
0x18001106d  mov     rcx, [rbp+hKey]
0x180011071  lea     r8, dword_180020348
0x180011078  lea     rdx, aHpkpmaxpending; "HpkpMaxPendingCount"
0x18001107f  call    UpdatePreFetchParaFromRegistry
0x180011084  mov     rcx, [rbp+hKey]
0x180011088  lea     r8, dword_18002034C
0x18001108f  lea     rdx, aHpkpmaxdomainc; "HpkpMaxDomainCount"
0x180011096  call    UpdatePreFetchParaFromRegistry
0x18001109b  mov     rcx, [rbp+hKey]; hKey
0x18001109f  call    cs:__imp_RegCloseKey
0x1800110a5  add     rsp, 30h
0x1800110a9  pop     rbp
0x1800110aa  retn
```
