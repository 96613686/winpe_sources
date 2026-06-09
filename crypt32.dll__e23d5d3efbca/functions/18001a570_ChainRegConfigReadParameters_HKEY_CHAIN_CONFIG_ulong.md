# ChainRegConfigReadParameters(HKEY__ *,_CHAIN_CONFIG *,ulong *)

- ea: `0x18001a570`
- end: `0x18001ab26`
- name: `?ChainRegConfigReadParameters@@YAXPEAUHKEY__@@PEAU_CHAIN_CONFIG@@PEAK@Z`
- size: `1462`
- prototype: `void __fastcall(HKEY hKey, struct _CHAIN_CONFIG *, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017e6c`
- `0x1800198a0`

## callees

- `0x18001a570`
- `0x180028d60`
- `0x1800353c8`
- `0x180035404`
- `0x18005550c`
- `0x1800582e8`
- `0x18005936c`
- `0x180059c58`
- `0x18008b370`
- `0x180099b44`
- `0x1800a80ac`
- `0x1800bf63c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a7d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a7d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a6ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a708`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a6ac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a708`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aa26`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aa91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aa26`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001aa91`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001aa33`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001aa9e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001aa33`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001aa9e`

## string_xrefs

- `0x18001aa60`: `ChainCacheResyncFiletime`
- `0x18001a829`: `DisableUnsupportedCriticalExtensions`
- `0x18001a911`: `MaxPathCountPerChain`
- `0x18001a6fe`: `Software\Policies\Microsoft\SystemCertificates\ChainEngine\Config`
- `0x18001a7ad`: `CRLValidityExtensionPeriod`

## pseudocode

```c
void __fastcall ChainRegConfigReadParameters(HKEY hKey, struct _CHAIN_CONFIG *a2, unsigned int *a3)
{
  unsigned int v6; // r14d
  __int64 updated; // rax
  HKEY v8; // r15
  unsigned int v9; // ecx
  char *SZValueFromRegistry; // rax
  int v11; // ecx
  __int64 v12; // rdx
  int v13; // ecx
  int v14; // ecx
  FILETIME *v15; // rsi
  bool v16; // cc
  HKEY v17; // rax
  FILETIME *v18; // rsi
  HKEY v19; // rax
  unsigned __int16 *v20; // rax
  HKEY hKeya; // [rsp+70h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+48h] BYREF
  FILETIME *lpFileTime1; // [rsp+80h] [rbp+50h] BYREF

  memset_0(a2, 0, 0x228u);
  *((_DWORD *)a2 + 4) = 5;
  *((_DWORD *)a2 + 14) = 2047;
  *((_DWORD *)a2 + 15) = 2047;
  *((_QWORD *)a2 + 8) = 129067776000000000LL;
  *((_DWORD *)a2 + 5) = 3;
  *((_DWORD *)a2 + 6) = 100000;
  *((_DWORD *)a2 + 7) = 10;
  *((_DWORD *)a2 + 3) = 104857600;
  *((_DWORD *)a2 + 8) = 100;
  *((_DWORD *)a2 + 9) = 12;
  *((_DWORD *)a2 + 10) = 1000;
  *((_DWORD *)a2 + 11) = 600;
  *((_DWORD *)a2 + 13) = 1023;
  if ( a3 )
    *a3 = 15000;
  *((_DWORD *)a2 + 130) = 20000;
  *((_DWORD *)a2 + 132) = 604800;
  v6 = 0;
  LODWORD(hKeya) = 0;
  updated = OpenAutoUpdateKey(-2147483646);
  v8 = (HKEY)updated;
  if ( updated )
  {
    ReadDWORDValueFromRegistry(updated, L"DisallowedCertSyncDeltaTime", &hKeya);
    v6 = (unsigned int)hKeya;
  }
  if ( !v6 )
    v6 = 57600;
  PkiDefaultCryptFree(0);
  CloseRegistryKey(v8);
  hKeya = 0;
  v9 = v6 + (v6 >> 1);
  if ( v9 < 0xF )
    v9 = 15;
  *((_DWORD *)a2 + 136) = v9;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\SystemCertificates\\Root\\ProtectedRoots",
          0,
          0x20019u,
          &hKeya) )
  {
    SZValueFromRegistry = ILS_ReadSZValueFromRegistry(hKeya, "PeerUsages");
    if ( SZValueFromRegistry )
    {
      if ( *SZValueFromRegistry )
        *((_QWORD *)a2 + 67) = SZValueFromRegistry;
      else
        PkiDefaultCryptFree(SZValueFromRegistry);
    }
    RegCloseKey(hKeya);
  }
  phkResult = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\SystemCertificates\\ChainEngine\\Config",
          0,
          0x20019u,
          &phkResult) )
  {
    LODWORD(hKeya) = 0;
    ILS_ReadDWORDValueFromRegistry(
      phkResult,
      L"ChainRevAccumulativeUrlRetrievalTimeoutMilliseconds",
      (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 130) = (_DWORD)hKeya;
    if ( a3 )
    {
      ILS_ReadDWORDValueFromRegistry(phkResult, L"ChainUrlRetrievalTimeoutMilliseconds", (unsigned int *)&hKeya);
      if ( (_DWORD)hKeya )
        *a3 = (unsigned int)hKeya;
    }
    ILS_ReadDWORDValueFromRegistry(phkResult, L"Options", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 131) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(phkResult, L"CrossCertDownloadIntervalHours", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 132) = 3600 * (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(phkResult, L"CRLValidityExtensionPeriod", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 133) = 3600 * (_DWORD)hKeya;
    RegCloseKey(phkResult);
  }
  if ( hKey )
  {
    LODWORD(hKeya) = 0;
    ILS_ReadDWORDValueFromRegistry(hKey, L"DisableMandatoryBasicConstraints", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *(_DWORD *)a2 = 1;
    ILS_ReadDWORDValueFromRegistry(hKey, L"DisableCANameConstraints", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 1) = 1;
    ILS_ReadDWORDValueFromRegistry(hKey, L"DisableUnsupportedCriticalExtensions", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 2) = 1;
    ILS_ReadDWORDValueFromRegistry(hKey, L"MaxAIAUrlCountInCert", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 4) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(hKey, L"MaxAIAUrlRetrievalCountPerChain", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 5) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(hKey, L"MaxUrlRetrievalByteCount", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 3) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(hKey, L"MaxAIAUrlRetrievalByteCount", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 6) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(hKey, L"MaxAIAUrlRetrievalCertCount", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 7) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(hKey, L"MaxVerifySignatureCountPerChain", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 8) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(hKey, L"MaxIssuerDepth", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 9) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(hKey, L"MaxPathCountPerChain", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 10) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(hKey, L"CryptnetPreFetchTriggerPeriodSeconds", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 11) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(hKey, L"EnableWeakSignatureFlags", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
      *((_DWORD *)a2 + 12) = (_DWORD)hKeya;
    ILS_ReadDWORDValueFromRegistry(hKey, L"MinRsaPubKeyBitLength", (unsigned int *)&hKeya);
    v11 = (int)hKeya;
    if ( (_DWORD)hKeya )
    {
      if ( (_DWORD)hKeya == -1 )
        v11 = 0;
      LODWORD(hKeya) = v11;
      *((_DWORD *)a2 + 13) = v11;
    }
    ILS_ReadDWORDValueFromRegistry(hKey, L"MinTelemetryRsaPubKeyBitLength", (unsigned int *)&hKeya);
    v13 = (int)hKeya;
    if ( (_DWORD)hKeya )
    {
      if ( (_DWORD)hKeya == -1 )
        v13 = 0;
      LODWORD(hKeya) = v13;
      *((_DWORD *)a2 + 14) = v13;
    }
    LOBYTE(v12) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WeakPublicKeyBitLength_Deprecation>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_WeakPublicKeyBitLength_Deprecation>::GetImpl'::`2'::impl,
      v12);
    ILS_ReadDWORDValueFromRegistry(hKey, L"MinWeakRsaPubKeyBitLength", (unsigned int *)&hKeya);
    v14 = (int)hKeya;
    if ( (_DWORD)hKeya )
    {
      if ( (_DWORD)hKeya == -1 )
        v14 = 0;
      LODWORD(hKeya) = v14;
      *((_DWORD *)a2 + 15) = v14;
    }
    lpFileTime1 = 0;
    LODWORD(phkResult) = 0;
    ILS_ReadBINARYValueFromRegistry(
      hKey,
      L"WeakRsaPubKeyTime",
      (unsigned __int8 **)&lpFileTime1,
      (unsigned int *)&phkResult);
    v15 = lpFileTime1;
    if ( lpFileTime1 )
    {
      if ( (_DWORD)phkResult == 8 && (lpFileTime1->dwLowDateTime || lpFileTime1->dwHighDateTime) )
      {
        phkResult = 0;
        GetSystemTimeAsFileTime((LPFILETIME)&phkResult);
        v16 = CompareFileTime(v15, (const FILETIME *)&phkResult) <= 0;
        v17 = phkResult;
        if ( v16 )
          v17 = (HKEY)*v15;
        *((_QWORD *)a2 + 8) = v17;
      }
      PkiDefaultCryptFree(v15);
    }
    lpFileTime1 = 0;
    LODWORD(phkResult) = 0;
    ILS_ReadBINARYValueFromRegistry(
      hKey,
      L"ChainCacheResyncFiletime",
      (unsigned __int8 **)&lpFileTime1,
      (unsigned int *)&phkResult);
    v18 = lpFileTime1;
    if ( lpFileTime1 )
    {
      if ( (_DWORD)phkResult == 8 && (lpFileTime1->dwLowDateTime || lpFileTime1->dwHighDateTime) )
      {
        phkResult = 0;
        GetSystemTimeAsFileTime((LPFILETIME)&phkResult);
        v16 = CompareFileTime(v18, (const FILETIME *)&phkResult) <= 0;
        v19 = phkResult;
        if ( v16 )
          v19 = (HKEY)*v18;
        *(_QWORD *)((char *)a2 + 92) = v19;
        *((_DWORD *)a2 + 22) = 1;
      }
      PkiDefaultCryptFree(v18);
    }
    ILS_ReadDWORDValueFromRegistry(hKey, L"EnableStrictChecksFlags", (unsigned int *)&hKeya);
    if ( (_DWORD)hKeya )
    {
      *((_DWORD *)a2 + 18) = (_DWORD)hKeya;
      v20 = ILS_ReadSZValueFromRegistry(hKey, L"StrictCASKIList");
      if ( v20 )
      {
        if ( *v20 )
          *((_QWORD *)a2 + 10) = v20;
        else
          PkiDefaultCryptFree(v20);
      }
    }
  }
  ReadWeakConfigParameters(hKey);
}

```

## disassembly

```asm
0x18001a570  mov     [rsp-38h+arg_18], rbx
0x18001a575  push    rbp
0x18001a576  push    rsi
0x18001a577  push    rdi
0x18001a578  push    r12
0x18001a57a  push    r13
0x18001a57c  push    r14
0x18001a57e  push    r15
0x18001a580  mov     rbp, rsp
0x18001a583  sub     rsp, 30h
0x18001a587  mov     rbx, rdx
0x18001a58a  mov     rsi, r8
0x18001a58d  mov     rdi, rcx
0x18001a590  xor     edx, edx; Val
0x18001a592  mov     rcx, rbx; void *
0x18001a595  mov     r8d, 228h; Size
0x18001a59b  call    memset_0
0x18001a5a0  mov     eax, 7FFh
0x18001a5a5  mov     dword ptr [rbx+10h], 5
0x18001a5ac  mov     [rbx+38h], eax
0x18001a5af  xor     r12d, r12d
0x18001a5b2  mov     [rbx+3Ch], eax
0x18001a5b5  mov     rax, 1CA8A755C6E0000h
0x18001a5bf  mov     [rbx+40h], rax
0x18001a5c3  mov     dword ptr [rbx+14h], 3
0x18001a5ca  mov     dword ptr [rbx+18h], 186A0h
0x18001a5d1  mov     dword ptr [rbx+1Ch], 0Ah
0x18001a5d8  mov     dword ptr [rbx+0Ch], 6400000h
0x18001a5df  mov     dword ptr [rbx+20h], 64h ; 'd'
0x18001a5e6  mov     dword ptr [rbx+24h], 0Ch
0x18001a5ed  mov     dword ptr [rbx+28h], 3E8h
0x18001a5f4  mov     dword ptr [rbx+2Ch], 258h
0x18001a5fb  mov     dword ptr [rbx+34h], 3FFh
0x18001a602  test    rsi, rsi
0x18001a605  jz      short loc_18001A60D
0x18001a607  mov     dword ptr [rsi], 3A98h
0x18001a60d  mov     r13, 0FFFFFFFF80000002h
0x18001a614  mov     dword ptr [rbx+208h], 4E20h
0x18001a61e  mov     rcx, r13
0x18001a621  mov     dword ptr [rbx+210h], 93A80h
0x18001a62b  mov     r14d, r12d
0x18001a62e  mov     dword ptr [rbp+hKey], r12d
0x18001a632  call    _OpenAutoUpdateKey
0x18001a637  mov     r15, rax
0x18001a63a  test    rax, rax
0x18001a63d  jz      short loc_18001A656
0x18001a63f  lea     r8, [rbp+hKey]
0x18001a643  mov     rcx, rax
0x18001a646  lea     rdx, aDisallowedcert_1; "DisallowedCertSyncDeltaTime"
0x18001a64d  call    _ReadDWORDValueFromRegistry
0x18001a652  mov     r14d, dword ptr [rbp+hKey]
0x18001a656  test    r14d, r14d
0x18001a659  mov     eax, 0E100h
0x18001a65e  cmovz   r14d, eax
0x18001a662  xor     ecx, ecx; hMem
0x18001a664  call    PkiDefaultCryptFree
0x18001a669  mov     rcx, r15; hKey
0x18001a66c  call    _CloseRegistryKey
0x18001a671  mov     ecx, r14d
0x18001a674  mov     [rbp+hKey], r12
0x18001a678  shr     ecx, 1
0x18001a67a  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\SystemCe"...
0x18001a681  add     ecx, r14d
0x18001a684  mov     eax, 0Fh
0x18001a689  cmp     ecx, eax
0x18001a68b  mov     r14d, 20019h
0x18001a691  mov     r9d, r14d; samDesired
0x18001a694  cmovb   ecx, eax
0x18001a697  lea     rax, [rbp+hKey]
0x18001a69b  mov     [rbx+220h], ecx
0x18001a6a1  xor     r8d, r8d; ulOptions
0x18001a6a4  mov     rcx, r13; hKey
0x18001a6a7  mov     [rsp+30h+phkResult], rax; phkResult
0x18001a6ac  call    cs:__imp_RegOpenKeyExW
0x18001a6b2  test    eax, eax
0x18001a6b4  jnz     short loc_18001A6EB
0x18001a6b6  mov     rcx, [rbp+hKey]; hKey
0x18001a6ba  lea     rdx, aPeerusages; "PeerUsages"
0x18001a6c1  call    ?ILS_ReadSZValueFromRegistry@@YAPEADPEAUHKEY__@@PEBD@Z; ILS_ReadSZValueFromRegistry(HKEY__ *,char const *)
0x18001a6c6  test    rax, rax
0x18001a6c9  jz      short loc_18001A6E1
0x18001a6cb  cmp     [rax], r12b
0x18001a6ce  jnz     short loc_18001A6DA
0x18001a6d0  mov     rcx, rax; hMem
0x18001a6d3  call    PkiDefaultCryptFree
0x18001a6d8  jmp     short loc_18001A6E1
0x18001a6da  mov     [rbx+218h], rax
0x18001a6e1  mov     rcx, [rbp+hKey]; hKey
0x18001a6e5  call    cs:__imp_RegCloseKey
0x18001a6eb  lea     rax, [rbp+arg_8]
0x18001a6ef  mov     [rbp+arg_8], r12
0x18001a6f3  mov     r9d, r14d; samDesired
0x18001a6f6  mov     [rsp+30h+phkResult], rax; phkResult
0x18001a6fb  xor     r8d, r8d; ulOptions
0x18001a6fe  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\SystemCe"...
0x18001a705  mov     rcx, r13; hKey
0x18001a708  call    cs:__imp_RegOpenKeyExW
0x18001a70e  test    eax, eax
0x18001a710  jnz     loc_18001A7D6
0x18001a716  mov     rcx, [rbp+arg_8]; HKEY
0x18001a71a  lea     r8, [rbp+hKey]; unsigned int *
0x18001a71e  lea     rdx, aChainrevaccumu; "ChainRevAccumulativeUrlRetrievalTimeout"...
0x18001a725  mov     dword ptr [rbp+hKey], r12d
0x18001a729  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a72e  mov     eax, dword ptr [rbp+hKey]
0x18001a731  test    eax, eax
0x18001a733  jz      short loc_18001A73B
0x18001a735  mov     [rbx+208h], eax
0x18001a73b  test    rsi, rsi
0x18001a73e  jz      short loc_18001A75D
0x18001a740  mov     rcx, [rbp+arg_8]; HKEY
0x18001a744  lea     r8, [rbp+hKey]; unsigned int *
0x18001a748  lea     rdx, aChainurlretrie; "ChainUrlRetrievalTimeoutMilliseconds"
0x18001a74f  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a754  mov     eax, dword ptr [rbp+hKey]
0x18001a757  test    eax, eax
0x18001a759  jz      short loc_18001A75D
0x18001a75b  mov     [rsi], eax
0x18001a75d  mov     rcx, [rbp+arg_8]; HKEY
0x18001a761  lea     r8, [rbp+hKey]; unsigned int *
0x18001a765  lea     rdx, aOptions; "Options"
0x18001a76c  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a771  mov     eax, dword ptr [rbp+hKey]
0x18001a774  test    eax, eax
0x18001a776  jz      short loc_18001A77E
0x18001a778  mov     [rbx+20Ch], eax
0x18001a77e  mov     rcx, [rbp+arg_8]; HKEY
0x18001a782  lea     r8, [rbp+hKey]; unsigned int *
0x18001a786  lea     rdx, aCrosscertdownl; "CrossCertDownloadIntervalHours"
0x18001a78d  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a792  mov     eax, dword ptr [rbp+hKey]
0x18001a795  test    eax, eax
0x18001a797  jz      short loc_18001A7A5
0x18001a799  imul    eax, 0E10h
0x18001a79f  mov     [rbx+210h], eax
0x18001a7a5  mov     rcx, [rbp+arg_8]; HKEY
0x18001a7a9  lea     r8, [rbp+hKey]; unsigned int *
0x18001a7ad  lea     rdx, aCrlvalidityext; "CRLValidityExtensionPeriod"
0x18001a7b4  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a7b9  mov     eax, dword ptr [rbp+hKey]
0x18001a7bc  test    eax, eax
0x18001a7be  jz      short loc_18001A7CC
0x18001a7c0  imul    eax, 0E10h
0x18001a7c6  mov     [rbx+214h], eax
0x18001a7cc  mov     rcx, [rbp+arg_8]; hKey
0x18001a7d0  call    cs:__imp_RegCloseKey
0x18001a7d6  test    rdi, rdi
0x18001a7d9  jz      loc_18001AB04
0x18001a7df  lea     r8, [rbp+hKey]; unsigned int *
0x18001a7e3  mov     dword ptr [rbp+hKey], r12d
0x18001a7e7  lea     rdx, aDisablemandato; "DisableMandatoryBasicConstraints"
0x18001a7ee  mov     rcx, rdi; HKEY
0x18001a7f1  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a7f6  mov     r14d, 1
0x18001a7fc  cmp     dword ptr [rbp+hKey], r12d
0x18001a800  jz      short loc_18001A805
0x18001a802  mov     [rbx], r14d
0x18001a805  lea     r8, [rbp+hKey]; unsigned int *
0x18001a809  mov     rcx, rdi; HKEY
0x18001a80c  lea     rdx, aDisablecanamec; "DisableCANameConstraints"
0x18001a813  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a818  cmp     dword ptr [rbp+hKey], r12d
0x18001a81c  jz      short loc_18001A822
0x18001a81e  mov     [rbx+4], r14d
0x18001a822  lea     r8, [rbp+hKey]; unsigned int *
0x18001a826  mov     rcx, rdi; HKEY
0x18001a829  lea     rdx, aDisableunsuppo; "DisableUnsupportedCriticalExtensions"
0x18001a830  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a835  cmp     dword ptr [rbp+hKey], r12d
0x18001a839  jz      short loc_18001A83F
0x18001a83b  mov     [rbx+8], r14d
0x18001a83f  lea     r8, [rbp+hKey]; unsigned int *
0x18001a843  mov     rcx, rdi; HKEY
0x18001a846  lea     rdx, aMaxaiaurlcount; "MaxAIAUrlCountInCert"
0x18001a84d  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a852  mov     eax, dword ptr [rbp+hKey]
0x18001a855  test    eax, eax
0x18001a857  jz      short loc_18001A85C
0x18001a859  mov     [rbx+10h], eax
0x18001a85c  lea     r8, [rbp+hKey]; unsigned int *
0x18001a860  mov     rcx, rdi; HKEY
0x18001a863  lea     rdx, aMaxaiaurlretri_1; "MaxAIAUrlRetrievalCountPerChain"
0x18001a86a  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a86f  mov     eax, dword ptr [rbp+hKey]
0x18001a872  test    eax, eax
0x18001a874  jz      short loc_18001A879
0x18001a876  mov     [rbx+14h], eax
0x18001a879  lea     r8, [rbp+hKey]; unsigned int *
0x18001a87d  mov     rcx, rdi; HKEY
0x18001a880  lea     rdx, aMaxurlretrieva; "MaxUrlRetrievalByteCount"
0x18001a887  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a88c  mov     eax, dword ptr [rbp+hKey]
0x18001a88f  test    eax, eax
0x18001a891  jz      short loc_18001A896
0x18001a893  mov     [rbx+0Ch], eax
0x18001a896  lea     r8, [rbp+hKey]; unsigned int *
0x18001a89a  mov     rcx, rdi; HKEY
0x18001a89d  lea     rdx, aMaxaiaurlretri_0; "MaxAIAUrlRetrievalByteCount"
0x18001a8a4  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a8a9  mov     eax, dword ptr [rbp+hKey]
0x18001a8ac  test    eax, eax
0x18001a8ae  jz      short loc_18001A8B3
0x18001a8b0  mov     [rbx+18h], eax
0x18001a8b3  lea     r8, [rbp+hKey]; unsigned int *
0x18001a8b7  mov     rcx, rdi; HKEY
0x18001a8ba  lea     rdx, aMaxaiaurlretri; "MaxAIAUrlRetrievalCertCount"
0x18001a8c1  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a8c6  mov     eax, dword ptr [rbp+hKey]
0x18001a8c9  test    eax, eax
0x18001a8cb  jz      short loc_18001A8D0
0x18001a8cd  mov     [rbx+1Ch], eax
0x18001a8d0  lea     r8, [rbp+hKey]; unsigned int *
0x18001a8d4  mov     rcx, rdi; HKEY
0x18001a8d7  lea     rdx, aMaxverifysigna; "MaxVerifySignatureCountPerChain"
0x18001a8de  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a8e3  mov     eax, dword ptr [rbp+hKey]
0x18001a8e6  test    eax, eax
0x18001a8e8  jz      short loc_18001A8ED
0x18001a8ea  mov     [rbx+20h], eax
0x18001a8ed  lea     r8, [rbp+hKey]; unsigned int *
0x18001a8f1  mov     rcx, rdi; HKEY
0x18001a8f4  lea     rdx, aMaxissuerdepth; "MaxIssuerDepth"
0x18001a8fb  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a900  mov     eax, dword ptr [rbp+hKey]
0x18001a903  test    eax, eax
0x18001a905  jz      short loc_18001A90A
0x18001a907  mov     [rbx+24h], eax
0x18001a90a  lea     r8, [rbp+hKey]; unsigned int *
0x18001a90e  mov     rcx, rdi; HKEY
0x18001a911  lea     rdx, aMaxpathcountpe; "MaxPathCountPerChain"
0x18001a918  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a91d  mov     eax, dword ptr [rbp+hKey]
0x18001a920  test    eax, eax
0x18001a922  jz      short loc_18001A927
0x18001a924  mov     [rbx+28h], eax
0x18001a927  lea     r8, [rbp+hKey]; unsigned int *
0x18001a92b  mov     rcx, rdi; HKEY
0x18001a92e  lea     rdx, aCryptnetprefet; "CryptnetPreFetchTriggerPeriodSeconds"
0x18001a935  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a93a  mov     eax, dword ptr [rbp+hKey]
0x18001a93d  test    eax, eax
0x18001a93f  jz      short loc_18001A944
0x18001a941  mov     [rbx+2Ch], eax
0x18001a944  lea     r8, [rbp+hKey]; unsigned int *
0x18001a948  mov     rcx, rdi; HKEY
0x18001a94b  lea     rdx, aEnableweaksign; "EnableWeakSignatureFlags"
0x18001a952  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a957  mov     eax, dword ptr [rbp+hKey]
0x18001a95a  test    eax, eax
0x18001a95c  jz      short loc_18001A961
0x18001a95e  mov     [rbx+30h], eax
0x18001a961  lea     r8, [rbp+hKey]; unsigned int *
0x18001a965  mov     rcx, rdi; HKEY
0x18001a968  lea     rdx, aMinrsapubkeybi; "MinRsaPubKeyBitLength"
0x18001a96f  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a974  mov     ecx, dword ptr [rbp+hKey]
0x18001a977  or      esi, 0FFFFFFFFh
0x18001a97a  test    ecx, ecx
0x18001a97c  jz      short loc_18001A98A
0x18001a97e  cmp     ecx, esi
0x18001a980  cmovz   ecx, r12d
0x18001a984  mov     dword ptr [rbp+hKey], ecx
0x18001a987  mov     [rbx+34h], ecx
0x18001a98a  lea     r8, [rbp+hKey]; unsigned int *
0x18001a98e  mov     rcx, rdi; HKEY
0x18001a991  lea     rdx, aMintelemetryrs; "MinTelemetryRsaPubKeyBitLength"
0x18001a998  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a99d  mov     ecx, dword ptr [rbp+hKey]
0x18001a9a0  test    ecx, ecx
0x18001a9a2  jz      short loc_18001A9B0
0x18001a9a4  cmp     ecx, esi
0x18001a9a6  cmovz   ecx, r12d
0x18001a9aa  mov     dword ptr [rbp+hKey], ecx
0x18001a9ad  mov     [rbx+38h], ecx
0x18001a9b0  mov     dl, r14b
0x18001a9b3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WeakPublicKeyBitLength_Deprecation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WeakPublicKeyBitLength_Deprecation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WeakPublicKeyBitLength_Deprecation> `wil::Feature<__WilFeatureTraits_Feature_WeakPublicKeyBitLength_Deprecation>::GetImpl(void)'::`2'::impl
0x18001a9ba  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WeakPublicKeyBitLength_Deprecation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WeakPublicKeyBitLength_Deprecation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001a9bf  lea     r8, [rbp+hKey]; unsigned int *
0x18001a9c3  mov     rcx, rdi; HKEY
0x18001a9c6  lea     rdx, aMinweakrsapubk; "MinWeakRsaPubKeyBitLength"
0x18001a9cd  call    ?ILS_ReadDWORDValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAK@Z; ILS_ReadDWORDValueFromRegistry(HKEY__ *,ushort const *,ulong *)
0x18001a9d2  mov     ecx, dword ptr [rbp+hKey]
0x18001a9d5  test    ecx, ecx
0x18001a9d7  jz      short loc_18001A9E5
0x18001a9d9  cmp     ecx, esi
0x18001a9db  cmovz   ecx, r12d
0x18001a9df  mov     dword ptr [rbp+hKey], ecx
0x18001a9e2  mov     [rbx+3Ch], ecx
0x18001a9e5  lea     r9, [rbp+arg_8]; unsigned int *
0x18001a9e9  mov     [rbp+lpFileTime1], r12
0x18001a9ed  lea     r8, [rbp+lpFileTime1]; unsigned __int8 **
0x18001a9f1  mov     dword ptr [rbp+arg_8], r12d
0x18001a9f5  lea     rdx, aWeakrsapubkeyt; "WeakRsaPubKeyTime"
0x18001a9fc  mov     rcx, rdi; hKey
0x18001a9ff  call    ?ILS_ReadBINARYValueFromRegistry@@YAHPEAUHKEY__@@PEBGPEAPEAEPEAK@Z; ILS_ReadBINARYValueFromRegistry(HKEY__ *,ushort const *,uchar * *,ulong *)
0x18001aa04  mov     rsi, [rbp+lpFileTime1]
0x18001aa08  test    rsi, rsi
0x18001aa0b  jz      short loc_18001AA50
0x18001aa0d  cmp     dword ptr [rbp+arg_8], 8
0x18001aa11  jnz     short loc_18001AA48
  ... truncated ...
```
