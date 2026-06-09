# CertificateGetOcspCrlUrlOrder(_CERT_CONTEXT const *,ulong)

- ea: `0x180005f10`
- end: `0x18000628a`
- name: `?CertificateGetOcspCrlUrlOrder@@YAKPEBU_CERT_CONTEXT@@K@Z`
- size: `890`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005bd0`
- `0x180007cc0`

## callees

- `0x1800052d0`
- `0x180005f10`
- `0x1800063b0`
- `0x180007a40`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005fe9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006142`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006275`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005fe9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006142`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000612f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000612f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006262`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180005f44`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180005f44`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x180005f91`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x180005f91`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180005fe1`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180005fe1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800060ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800061c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800060ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800061c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006045`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800060f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006045`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800060f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006083`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800060b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000619a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006083`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800060b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000619a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000613a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000626d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000613a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000626d`

## string_xrefs

- `0x18000601d`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`
- `0x1800060e2`: `Software\Policies\Microsoft\SystemCertificates\ChainEngine\Config`
- `0x180006076`: `CryptnetCachedOcspSwitchToCrlCount`
- `0x18000618d`: `CryptnetCachedOcspSwitchToCrlCount`
- `0x1800060b1`: `CryptnetMaxCachedOcspPerCrlCount`

## pseudocode

```c
__int64 __fastcall CertificateGetOcspCrlUrlOrder(PCCERT_CONTEXT pCertContext, int a2)
{
  char v2; // r13d^3
  int v4; // edi
  DWORD LastError; // ebx
  unsigned __int16 *OcspCacheFileNamePrefix; // r14
  unsigned int v7; // r15d
  unsigned int v8; // r12d
  unsigned int v9; // ebx
  unsigned __int16 *CryptnetUrlCacheDir; // rsi
  DWORD v11; // edi
  DWORD v13; // edi
  BYTE Data[4]; // [rsp+50h] [rbp+7h] BYREF
  unsigned int v15; // [rsp+54h] [rbp+Bh]
  DWORD pcbData; // [rsp+58h] [rbp+Fh] BYREF
  int v17; // [rsp+5Ch] [rbp+13h] BYREF
  HKEY phkResult[2]; // [rsp+60h] [rbp+17h] BYREF
  __int64 (__fastcall *cbData)(__int64, PCCERT_CONTEXT, __int64, _QWORD, int *, _QWORD, _QWORD, _QWORD); // [rsp+C0h] [rbp+77h] BYREF
  HCRYPTOIDFUNCADDR hFuncAddr; // [rsp+C8h] [rbp+7Fh] BYREF

  v2 = HIBYTE(a2);
  pcbData = 0;
  v17 = 0;
  v15 = 0;
  if ( CertGetCertificateContextProperty(pCertContext, 0x56u, 0, &pcbData) )
    return 1;
  hFuncAddr = 0;
  cbData = 0;
  if ( !CryptGetOIDFunctionAddress(hGetObjectUrlFuncSet, 1u, (LPCSTR)9, 0, (void **)&cbData, &hFuncAddr) )
    return 2;
  v4 = cbData(9, pCertContext, 15, 0, &v17, 0, 0, 0);
  LastError = GetLastError();
  CryptFreeOIDFunctionAddress(hFuncAddr, 0);
  SetLastError(LastError);
  if ( !v4 )
    return 2;
  OcspCacheFileNamePrefix = CertificateGetOcspCacheFileNamePrefix(pCertContext);
  if ( !OcspCacheFileNamePrefix )
    return 1;
  phkResult[0] = 0;
  v7 = 50;
  v8 = 500;
  v9 = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config",
          0,
          0x20119u,
          phkResult) )
  {
    LODWORD(hFuncAddr) = 0;
    *(_DWORD *)Data = 0;
    LODWORD(cbData) = 4;
    if ( !RegQueryValueExW(
            phkResult[0],
            L"CryptnetCachedOcspSwitchToCrlCount",
            0,
            (LPDWORD)&hFuncAddr,
            Data,
            (LPDWORD)&cbData)
      && (_DWORD)hFuncAddr == 4
      && (_DWORD)cbData == 4 )
    {
      if ( *(_DWORD *)Data )
      {
        v7 = *(_DWORD *)Data;
        if ( *(_DWORD *)Data == -1 )
          v7 = 0;
      }
    }
    LODWORD(cbData) = 4;
    if ( !RegQueryValueExW(
            phkResult[0],
            L"CryptnetMaxCachedOcspPerCrlCount",
            0,
            (LPDWORD)&hFuncAddr,
            Data,
            (LPDWORD)&cbData)
      && (_DWORD)hFuncAddr == 4
      && (_DWORD)cbData == 4 )
    {
      if ( *(_DWORD *)Data )
      {
        v8 = *(_DWORD *)Data;
        if ( *(_DWORD *)Data == -1 )
          v8 = 0;
      }
    }
    RegCloseKey(phkResult[0]);
  }
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\SystemCertificates\\ChainEngine\\Config",
          0,
          0x20019u,
          phkResult) )
  {
    LODWORD(cbData) = 0;
    *(_DWORD *)Data = 0;
    LODWORD(hFuncAddr) = 4;
    if ( !RegQueryValueExW(
            phkResult[0],
            L"CryptnetCachedOcspSwitchToCrlCount",
            0,
            (LPDWORD)&cbData,
            Data,
            (LPDWORD)&hFuncAddr)
      && (_DWORD)cbData == 4
      && (_DWORD)hFuncAddr == 4 )
    {
      if ( *(_DWORD *)Data )
      {
        v7 = *(_DWORD *)Data;
        if ( *(_DWORD *)Data == -1 )
          v7 = 0;
      }
    }
    RegCloseKey(phkResult[0]);
  }
  CryptnetUrlCacheDir = I_SchemeGetCryptnetUrlCacheDir();
  if ( CryptnetUrlCacheDir )
  {
    I_UrlCacheEnum(CryptnetUrlCacheDir, OcspCacheFileNamePrefix, (__int64)I_CountCachedOcspCallback);
    v13 = GetLastError();
    LocalFree(CryptnetUrlCacheDir);
    SetLastError(v13);
  }
  if ( v15 >= v8 )
  {
    v9 = 2;
  }
  else if ( v15 < v7 )
  {
    v9 = ~v2 & 2 | 1;
  }
  v11 = GetLastError();
  LocalFree(OcspCacheFileNamePrefix);
  SetLastError(v11);
  return v9;
}

```

## disassembly

```asm
0x180005f10  push    rbp
0x180005f12  push    rsi
0x180005f13  push    r13
0x180005f15  push    r15
0x180005f17  lea     rbp, [rsp-3Fh]
0x180005f1c  sub     rsp, 88h
0x180005f23  xor     r15d, r15d
0x180005f26  lea     r9, [rbp+57h+pcbData]; pcbData
0x180005f2a  mov     r13d, edx
0x180005f2d  mov     [rbp+57h+pcbData], r15d
0x180005f31  mov     edx, 56h ; 'V'; dwPropId
0x180005f36  mov     [rbp+57h+var_44], r15d
0x180005f3a  xor     r8d, r8d; pvData
0x180005f3d  mov     [rbp+57h+var_4C], r15d
0x180005f41  mov     rsi, rcx
0x180005f44  call    cs:__imp_CertGetCertificateContextProperty
0x180005f4a  test    eax, eax
0x180005f4c  jnz     loc_1800061D8
0x180005f52  mov     rcx, cs:hGetObjectUrlFuncSet; hFuncSet
0x180005f59  lea     rax, [rbp+57h+hFuncAddr]
0x180005f5d  mov     [rsp+0A0h+phFuncAddr], rax; phFuncAddr
0x180005f62  xor     r9d, r9d; dwFlags
0x180005f65  lea     rax, [rbp+57h+cbData]
0x180005f69  mov     [rsp+0A0h+arg_0], rbx
0x180005f71  mov     edx, 1; dwEncodingType
0x180005f76  mov     [rsp+0A0h+ppvFuncAddr], rax; ppvFuncAddr
0x180005f7b  mov     r8d, 9; pszOID
0x180005f81  mov     [rsp+0A0h+var_20], rdi
0x180005f89  mov     [rbp+57h+hFuncAddr], r15
0x180005f8d  mov     [rbp+57h+cbData], r15
0x180005f91  call    cs:__imp_CryptGetOIDFunctionAddress
0x180005f97  test    eax, eax
0x180005f99  jz      loc_1800061CE
0x180005f9f  mov     [rsp+0A0h+var_68], r15
0x180005fa4  lea     rax, [rbp+57h+var_44]
0x180005fa8  mov     [rsp+0A0h+var_70], r15
0x180005fad  xor     r9d, r9d
0x180005fb0  mov     [rsp+0A0h+phFuncAddr], r15
0x180005fb5  mov     r8d, 0Fh
0x180005fbb  mov     [rsp+0A0h+ppvFuncAddr], rax
0x180005fc0  mov     rdx, rsi
0x180005fc3  mov     rax, [rbp+57h+cbData]
0x180005fc7  mov     ecx, 9
0x180005fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd1  mov     edi, eax
0x180005fd3  call    cs:__imp_GetLastError
0x180005fd9  mov     rcx, [rbp+57h+hFuncAddr]; hFuncAddr
0x180005fdd  xor     edx, edx; dwFlags
0x180005fdf  mov     ebx, eax
0x180005fe1  call    cs:__imp_CryptFreeOIDFunctionAddress
0x180005fe7  mov     ecx, ebx; dwErrCode
0x180005fe9  call    cs:__imp_SetLastError
0x180005fef  test    edi, edi
0x180005ff1  jz      loc_1800061CE
0x180005ff7  mov     rcx, rsi; pCertContext
0x180005ffa  mov     [rsp+0A0h+var_30], r14
0x180005fff  call    ?CertificateGetOcspCacheFileNamePrefix@@YAPEAGPEBU_CERT_CONTEXT@@@Z; CertificateGetOcspCacheFileNamePrefix(_CERT_CONTEXT const *)
0x180006004  mov     r14, rax
0x180006007  test    rax, rax
0x18000600a  jz      loc_1800061DF
0x180006010  lea     rax, [rbp+57h+phkResult]
0x180006014  mov     [rbp+57h+phkResult], r15
0x180006018  mov     [rsp+0A0h+var_28], r12
0x18000601d  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\OID"...
0x180006024  mov     r9d, 20119h; samDesired
0x18000602a  mov     [rsp+0A0h+ppvFuncAddr], rax; phkResult
0x18000602f  xor     r8d, r8d; ulOptions
0x180006032  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006039  mov     r15d, 32h ; '2'
0x18000603f  mov     r12d, 1F4h
0x180006045  call    cs:__imp_RegOpenKeyExW
0x18000604b  xor     edi, edi
0x18000604d  mov     ebx, 4
0x180006052  test    eax, eax
0x180006054  jnz     short loc_1800060D0
0x180006056  mov     rcx, [rbp+57h+phkResult]; hKey
0x18000605a  lea     rax, [rbp+57h+cbData]
0x18000605e  mov     [rsp+0A0h+phFuncAddr], rax; lpcbData
0x180006063  lea     r9, [rbp+57h+hFuncAddr]; lpType
0x180006067  lea     rax, [rbp+57h+Data]
0x18000606b  mov     dword ptr [rbp+57h+hFuncAddr], edi
0x18000606e  xor     r8d, r8d; lpReserved
0x180006071  mov     [rsp+0A0h+ppvFuncAddr], rax; lpData
0x180006076  lea     rdx, ValueName; "CryptnetCachedOcspSwitchToCrlCount"
0x18000607d  mov     dword ptr [rbp+57h+Data], edi
0x180006080  mov     dword ptr [rbp+57h+cbData], ebx
0x180006083  call    cs:__imp_RegQueryValueExW
0x180006089  test    eax, eax
0x18000608b  jz      loc_1800061E9
0x180006091  mov     rcx, [rbp+57h+phkResult]; hKey
0x180006095  lea     rax, [rbp+57h+cbData]
0x180006099  mov     [rsp+0A0h+phFuncAddr], rax; lpcbData
0x18000609e  lea     r9, [rbp+57h+hFuncAddr]; lpType
0x1800060a2  lea     rax, [rbp+57h+Data]
0x1800060a6  mov     dword ptr [rbp+57h+cbData], ebx
0x1800060a9  xor     r8d, r8d; lpReserved
0x1800060ac  mov     [rsp+0A0h+ppvFuncAddr], rax; lpData
0x1800060b1  lea     rdx, aCryptnetmaxcac; "CryptnetMaxCachedOcspPerCrlCount"
0x1800060b8  call    cs:__imp_RegQueryValueExW
0x1800060be  test    eax, eax
0x1800060c0  jz      loc_180006215
0x1800060c6  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800060ca  call    cs:__imp_RegCloseKey
0x1800060d0  lea     rax, [rbp+57h+phkResult]
0x1800060d4  mov     r9d, 20019h; samDesired
0x1800060da  xor     r8d, r8d; ulOptions
0x1800060dd  mov     [rsp+0A0h+ppvFuncAddr], rax; phkResult
0x1800060e2  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\SystemCe"...
0x1800060e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800060f0  call    cs:__imp_RegOpenKeyExW
0x1800060f6  test    eax, eax
0x1800060f8  jz      short loc_18000616D
0x1800060fa  call    ?I_SchemeGetCryptnetUrlCacheDir@@YAPEAGXZ; I_SchemeGetCryptnetUrlCacheDir(void)
0x1800060ff  mov     rsi, rax
0x180006102  test    rax, rax
0x180006105  jnz     loc_180006241
0x18000610b  mov     eax, [rbp+57h+var_4C]
0x18000610e  cmp     eax, r12d
0x180006111  mov     r12, [rsp+0A0h+var_28]
0x180006116  jnb     loc_180006280
0x18000611c  cmp     eax, r15d
0x18000611f  jnb     short loc_18000612F
0x180006121  mov     ebx, r13d
0x180006124  shr     ebx, 18h
0x180006127  not     ebx
0x180006129  and     ebx, 2
0x18000612c  or      ebx, 1
0x18000612f  call    cs:__imp_GetLastError
0x180006135  mov     rcx, r14; hMem
0x180006138  mov     edi, eax
0x18000613a  call    cs:__imp_LocalFree
0x180006140  mov     ecx, edi; dwErrCode
0x180006142  call    cs:__imp_SetLastError
0x180006148  mov     eax, ebx
0x18000614a  mov     r14, [rsp+0A0h+var_30]
0x18000614f  mov     rbx, [rsp+0A0h+arg_0]
0x180006157  mov     rdi, [rsp+0A0h+var_20]
0x18000615f  add     rsp, 88h
0x180006166  pop     r15
0x180006168  pop     r13
0x18000616a  pop     rsi
0x18000616b  pop     rbp
0x18000616c  retn
0x18000616d  mov     rcx, [rbp+57h+phkResult]; hKey
0x180006171  lea     rax, [rbp+57h+hFuncAddr]
0x180006175  mov     [rsp+0A0h+phFuncAddr], rax; lpcbData
0x18000617a  lea     r9, [rbp+57h+cbData]; lpType
0x18000617e  lea     rax, [rbp+57h+Data]
0x180006182  mov     dword ptr [rbp+57h+cbData], edi
0x180006185  xor     r8d, r8d; lpReserved
0x180006188  mov     [rsp+0A0h+ppvFuncAddr], rax; lpData
0x18000618d  lea     rdx, ValueName; "CryptnetCachedOcspSwitchToCrlCount"
0x180006194  mov     dword ptr [rbp+57h+Data], edi
0x180006197  mov     dword ptr [rbp+57h+hFuncAddr], ebx
0x18000619a  call    cs:__imp_RegQueryValueExW
0x1800061a0  test    eax, eax
0x1800061a2  jnz     short loc_1800061BF
0x1800061a4  cmp     dword ptr [rbp+57h+cbData], ebx
0x1800061a7  jnz     short loc_1800061BF
0x1800061a9  cmp     dword ptr [rbp+57h+hFuncAddr], ebx
0x1800061ac  jnz     short loc_1800061BF
0x1800061ae  mov     ecx, dword ptr [rbp+57h+Data]
0x1800061b1  test    ecx, ecx
0x1800061b3  jz      short loc_1800061BF
0x1800061b5  cmp     ecx, 0FFFFFFFFh
0x1800061b8  mov     r15d, ecx
0x1800061bb  cmovz   r15d, edi
0x1800061bf  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800061c3  call    cs:__imp_RegCloseKey
0x1800061c9  jmp     loc_1800060FA
0x1800061ce  mov     eax, 2
0x1800061d3  jmp     loc_18000614F
0x1800061d8  mov     eax, 1
0x1800061dd  jmp     short loc_18000615F
0x1800061df  mov     eax, 1
0x1800061e4  jmp     loc_18000614A
0x1800061e9  cmp     dword ptr [rbp+57h+hFuncAddr], ebx
0x1800061ec  jnz     loc_180006091
0x1800061f2  cmp     dword ptr [rbp+57h+cbData], ebx
0x1800061f5  jnz     loc_180006091
0x1800061fb  mov     ecx, dword ptr [rbp+57h+Data]
0x1800061fe  test    ecx, ecx
0x180006200  jz      loc_180006091
0x180006206  cmp     ecx, 0FFFFFFFFh
0x180006209  mov     r15d, ecx
0x18000620c  cmovz   r15d, edi
0x180006210  jmp     loc_180006091
0x180006215  cmp     dword ptr [rbp+57h+hFuncAddr], ebx
0x180006218  jnz     loc_1800060C6
0x18000621e  cmp     dword ptr [rbp+57h+cbData], ebx
0x180006221  jnz     loc_1800060C6
0x180006227  mov     edx, dword ptr [rbp+57h+Data]
0x18000622a  test    edx, edx
0x18000622c  jz      loc_1800060C6
0x180006232  cmp     edx, 0FFFFFFFFh
0x180006235  mov     r12d, edx
0x180006238  cmovz   r12d, edi
0x18000623c  jmp     loc_1800060C6
0x180006241  lea     rax, ?I_CountCachedOcspCallback@@YAHPEBU_CRYPTNET_URL_CACHE_ENTRY@@KPEAX1@Z; I_CountCachedOcspCallback(_CRYPTNET_URL_CACHE_ENTRY const *,ulong,void *,void *)
0x180006248  mov     r8d, 1
0x18000624e  lea     r9, [rbp+57h+var_4C]
0x180006252  mov     [rsp+0A0h+ppvFuncAddr], rax; __int64
0x180006257  mov     rdx, r14; void *
0x18000625a  mov     rcx, rsi; Src
0x18000625d  call    I_UrlCacheEnum
0x180006262  call    cs:__imp_GetLastError
0x180006268  mov     rcx, rsi; hMem
0x18000626b  mov     edi, eax
0x18000626d  call    cs:__imp_LocalFree
0x180006273  mov     ecx, edi; dwErrCode
0x180006275  call    cs:__imp_SetLastError
0x18000627b  jmp     loc_18000610B
0x180006280  mov     ebx, 2
0x180006285  jmp     loc_18000612F
```
