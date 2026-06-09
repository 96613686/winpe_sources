# InitPreFetchPara(void)

- ea: `0x18000c46c`
- end: `0x18000c6cc`
- name: `?InitPreFetchPara@@YAXXZ`
- size: `608`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d548`

## callees

- `0x18000c370`
- `0x18000c46c`
- `0x18000c6d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c697`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c697`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c52c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c52c`

## string_xrefs

- `0x18000c48c`: `Software\Microsoft\Cryptography\OID\EncodingType 0\CertDllCreateCertificateChainEngine\Config`
- `0x18000c5e6`: `CryptnetPreFetchBeforeNextUpdatePreFetchDivisor`
- `0x18000c5fd`: `CryptnetPreFetchMinBeforeNextUpdatePreFetchSeconds`
- `0x18000c614`: `CryptnetPreFetchValidityPeriodAfterNextUpdatePreFetchDivisor`
- `0x18000c62b`: `CryptnetPreFetchMaxAfterNextUpdatePreFetchPeriodSeconds`
- `0x18000c642`: `CryptnetPreFetchMinAfterNextUpdatePreFetchPeriodSeconds`

## pseudocode

```c
void InitPreFetchPara(void)
{
  int v0; // ebx
  HKEY hKey; // [rsp+40h] [rbp+10h] BYREF

  hKey = 0;
  dword_180020280 = 1209600;
  dword_180020284 = 1209600;
  dword_18002027C = 3600;
  dword_180020288 = 10;
  v0 = 300;
  dword_180020294 = 10;
  dword_180020290 = 3600;
  dword_18002029C = 1800;
  dword_1800202A0 = 1800;
  PreFetchPara = 0;
  dword_180020278 = 104857600;
  dword_180020274 = 2419200;
  dword_18002028C = 20;
  dword_180020298 = 14400;
  dword_1800202A4 = 60;
  dword_1800202AC = 300;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Cryptography\\OID\\EncodingType 0\\CertDllCreateCertificateChainEngine\\Config",
          0,
          0x20119u,
          &hKey) )
  {
    UpdatePreFetchParaFromRegistry(hKey, L"MaxUrlRetrievalByteCount", &dword_180020278);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchEnable", &PreFetchPara);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetDefaultFlushExemptSeconds", &dword_180020274);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchMinMaxAgeSeconds", &dword_18002027C);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchMaxMaxAgeSeconds", &dword_180020280);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchMinOcspValidityPeriodSeconds", &dword_180020284);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchAfterPublishPreFetchDivisor", &dword_180020288);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchBeforeNextUpdatePreFetchDivisor", &dword_18002028C);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchMinBeforeNextUpdatePreFetchSeconds", &dword_180020290);
    UpdatePreFetchParaFromRegistry(
      hKey,
      L"CryptnetPreFetchValidityPeriodAfterNextUpdatePreFetchDivisor",
      &dword_180020294);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchMaxAfterNextUpdatePreFetchPeriodSeconds", &dword_180020298);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchMinAfterNextUpdatePreFetchPeriodSeconds", &dword_18002029C);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchAfterCurrentTimePreFetchPeriodSeconds", &dword_1800202A0);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchScanAfterTriggerDelaySeconds", &dword_1800202A4);
    UpdatePreFetchParaFromRegistry(hKey, L"CryptnetPreFetchRetrievalTimeoutSeconds", &dword_1800202AC);
    RegCloseKey(hKey);
  }
  if ( (unsigned int)dword_1800202A4 > 0x12C )
    v0 = dword_1800202A4;
  dword_1800202A8 = v0 + 300;
  dword_1800202B0 = GetPreFetchDebugFlags();
}

```

## disassembly

```asm
0x18000c46c  mov     [rsp-8+arg_8], rbx
0x18000c471  push    rbp
0x18000c472  mov     rbp, rsp
0x18000c475  sub     rsp, 30h
0x18000c479  mov     eax, 127500h
0x18000c47e  mov     [rbp+hKey], 0
0x18000c486  mov     cs:dword_180020280, eax
0x18000c48c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\OID"...
0x18000c493  mov     cs:dword_180020284, eax
0x18000c499  mov     ecx, 0E10h
0x18000c49e  mov     eax, 0Ah
0x18000c4a3  mov     cs:dword_18002027C, ecx
0x18000c4a9  mov     cs:dword_180020288, eax
0x18000c4af  mov     ebx, 12Ch
0x18000c4b4  mov     cs:dword_180020294, eax
0x18000c4ba  mov     r9d, 20119h; samDesired
0x18000c4c0  mov     eax, 708h
0x18000c4c5  mov     cs:dword_180020290, ecx
0x18000c4cb  mov     cs:dword_18002029C, eax
0x18000c4d1  xor     r8d, r8d; ulOptions
0x18000c4d4  mov     cs:dword_1800202A0, eax
0x18000c4da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c4e1  lea     rax, [rbp+hKey]
0x18000c4e5  mov     cs:?PreFetchPara@@3U_CUCS_PRE_FETCH_PARA@@A, 0; _CUCS_PRE_FETCH_PARA PreFetchPara
0x18000c4ef  mov     [rsp+30h+phkResult], rax; phkResult
0x18000c4f4  mov     cs:dword_180020278, 6400000h
0x18000c4fe  mov     cs:dword_180020274, 24EA00h
0x18000c508  mov     cs:dword_18002028C, 14h
0x18000c512  mov     cs:dword_180020298, 3840h
0x18000c51c  mov     cs:dword_1800202A4, 3Ch ; '<'
0x18000c526  mov     cs:dword_1800202AC, ebx
0x18000c52c  call    cs:__imp_RegOpenKeyExW
0x18000c532  test    eax, eax
0x18000c534  jnz     loc_18000C69D
0x18000c53a  mov     rcx, [rbp+hKey]
0x18000c53e  lea     r8, dword_180020278
0x18000c545  lea     rdx, aMaxurlretrieva; "MaxUrlRetrievalByteCount"
0x18000c54c  call    UpdatePreFetchParaFromRegistry
0x18000c551  mov     rcx, [rbp+hKey]
0x18000c555  lea     r8, ?PreFetchPara@@3U_CUCS_PRE_FETCH_PARA@@A; _CUCS_PRE_FETCH_PARA PreFetchPara
0x18000c55c  lea     rdx, aCryptnetprefet_1; "CryptnetPreFetchEnable"
0x18000c563  call    UpdatePreFetchParaFromRegistry
0x18000c568  mov     rcx, [rbp+hKey]
0x18000c56c  lea     r8, dword_180020274
0x18000c573  lea     rdx, aCryptnetdefaul; "CryptnetDefaultFlushExemptSeconds"
0x18000c57a  call    UpdatePreFetchParaFromRegistry
0x18000c57f  mov     rcx, [rbp+hKey]
0x18000c583  lea     r8, dword_18002027C
0x18000c58a  lea     rdx, aCryptnetprefet_7; "CryptnetPreFetchMinMaxAgeSeconds"
0x18000c591  call    UpdatePreFetchParaFromRegistry
0x18000c596  mov     rcx, [rbp+hKey]
0x18000c59a  lea     r8, dword_180020280
0x18000c5a1  lea     rdx, aCryptnetprefet; "CryptnetPreFetchMaxMaxAgeSeconds"
0x18000c5a8  call    UpdatePreFetchParaFromRegistry
0x18000c5ad  mov     rcx, [rbp+hKey]
0x18000c5b1  lea     r8, dword_180020284
0x18000c5b8  lea     rdx, aCryptnetprefet_3; "CryptnetPreFetchMinOcspValidityPeriodSe"...
0x18000c5bf  call    UpdatePreFetchParaFromRegistry
0x18000c5c4  mov     rcx, [rbp+hKey]
0x18000c5c8  lea     r8, dword_180020288
0x18000c5cf  lea     rdx, aCryptnetprefet_5; "CryptnetPreFetchAfterPublishPreFetchDiv"...
0x18000c5d6  call    UpdatePreFetchParaFromRegistry
0x18000c5db  mov     rcx, [rbp+hKey]
0x18000c5df  lea     r8, dword_18002028C
0x18000c5e6  lea     rdx, aCryptnetprefet_4; "CryptnetPreFetchBeforeNextUpdatePreFetc"...
0x18000c5ed  call    UpdatePreFetchParaFromRegistry
0x18000c5f2  mov     rcx, [rbp+hKey]
0x18000c5f6  lea     r8, dword_180020290
0x18000c5fd  lea     rdx, aCryptnetprefet_6; "CryptnetPreFetchMinBeforeNextUpdatePreF"...
0x18000c604  call    UpdatePreFetchParaFromRegistry
0x18000c609  mov     rcx, [rbp+hKey]
0x18000c60d  lea     r8, dword_180020294
0x18000c614  lea     rdx, aCryptnetprefet_2; "CryptnetPreFetchValidityPeriodAfterNext"...
0x18000c61b  call    UpdatePreFetchParaFromRegistry
0x18000c620  mov     rcx, [rbp+hKey]
0x18000c624  lea     r8, dword_180020298
0x18000c62b  lea     rdx, aCryptnetprefet_8; "CryptnetPreFetchMaxAfterNextUpdatePreFe"...
0x18000c632  call    UpdatePreFetchParaFromRegistry
0x18000c637  mov     rcx, [rbp+hKey]
0x18000c63b  lea     r8, dword_18002029C
0x18000c642  lea     rdx, aCryptnetprefet_11; "CryptnetPreFetchMinAfterNextUpdatePreFe"...
0x18000c649  call    UpdatePreFetchParaFromRegistry
0x18000c64e  mov     rcx, [rbp+hKey]
0x18000c652  lea     r8, dword_1800202A0
0x18000c659  lea     rdx, aCryptnetprefet_0; "CryptnetPreFetchAfterCurrentTimePreFetc"...
0x18000c660  call    UpdatePreFetchParaFromRegistry
0x18000c665  mov     rcx, [rbp+hKey]
0x18000c669  lea     r8, dword_1800202A4
0x18000c670  lea     rdx, aCryptnetprefet_9; "CryptnetPreFetchScanAfterTriggerDelaySe"...
0x18000c677  call    UpdatePreFetchParaFromRegistry
0x18000c67c  mov     rcx, [rbp+hKey]
0x18000c680  lea     r8, dword_1800202AC
0x18000c687  lea     rdx, aCryptnetprefet_10; "CryptnetPreFetchRetrievalTimeoutSeconds"
0x18000c68e  call    UpdatePreFetchParaFromRegistry
0x18000c693  mov     rcx, [rbp+hKey]; hKey
0x18000c697  call    cs:__imp_RegCloseKey
0x18000c69d  cmp     cs:dword_1800202A4, ebx
0x18000c6a3  cmova   ebx, cs:dword_1800202A4
0x18000c6aa  lea     eax, [rbx+12Ch]
0x18000c6b0  mov     cs:dword_1800202A8, eax
0x18000c6b6  call    ?GetPreFetchDebugFlags@@YAKXZ; GetPreFetchDebugFlags(void)
0x18000c6bb  mov     rbx, [rsp+30h+arg_8]
0x18000c6c0  mov     cs:dword_1800202B0, eax
0x18000c6c6  add     rsp, 30h
0x18000c6ca  pop     rbp
0x18000c6cb  retn
```
