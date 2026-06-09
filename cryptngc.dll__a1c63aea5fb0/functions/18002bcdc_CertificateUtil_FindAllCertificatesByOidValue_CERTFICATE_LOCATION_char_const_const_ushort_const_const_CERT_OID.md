# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x18002bcdc`
- end: `0x18002c235`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1369`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180045e7c`

## callees

- `0x1800073c0`
- `0x180015b10`
- `0x1800166e0`
- `0x180016750`
- `0x18001a530`
- `0x180027278`
- `0x180027448`
- `0x18002bcdc`
- `0x18002c23c`
- `0x18002cd24`
- `0x180044554`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c18d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c18d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002be0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bebd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002be0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bebd`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18002be41`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18002c1f1`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18002be41`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18002c1f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c1b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c1b9`
- `CRYPT32!CertOpenStore` at `0x18002bf17`
- `CRYPT32!CertOpenStore` at `0x18002bf17`
- `CRYPT32!CertFreeCertificateContext` at `0x18002c154`
- `CRYPT32!CertFreeCertificateContext` at `0x18002c154`
- `CRYPT32!CertFindCertificateInStore` at `0x18002bf6f`
- `CRYPT32!CertFindCertificateInStore` at `0x18002bf6f`
- `CRYPT32!CertCloseStore` at `0x18002c183`
- `CRYPT32!CertCloseStore` at `0x18002c183`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18002c099`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18002c099`

## string_xrefs

- `0x18002c0b6`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18002be27`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x18002bed0`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x18002bf33`: `%s: CertOpenStore failed with error code: 0x%08x`

## pseudocode

```c
__int64 __fastcall CertificateUtil::FindAllCertificatesByOidValue(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        struct _CERT_CONTEXT **a6,
        unsigned int *a7)
{
  __int64 LastError; // rsi
  void *v8; // r12
  const CERT_CONTEXT *pPrevCertContext; // rbp
  __int64 v10; // r14
  signed int v12; // edi
  const unsigned __int16 *v13; // rdx
  unsigned int v14; // eax
  unsigned int KeyW; // eax
  const unsigned __int16 *v16; // rdx
  HKEY v17; // rcx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r9
  int KeyWinPE; // eax
  const wchar_t *v21; // r9
  unsigned int v22; // eax
  const wchar_t *v23; // rax
  DWORD v24; // r9d
  __int64 v25; // rcx
  int v26; // ebp
  __int64 i; // r12
  __int64 v28; // rdx
  const char *v29; // rcx
  int DoesExtensionWithValueExist; // eax
  const wchar_t *v31; // r8
  signed int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-88h]
  unsigned int v37; // [rsp+30h] [rbp-78h]
  int v38; // [rsp+34h] [rbp-74h] BYREF
  int v39; // [rsp+38h] [rbp-70h]
  int v40; // [rsp+3Ch] [rbp-6Ch]
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-68h]
  HCERTSTORE v42; // [rsp+48h] [rbp-60h]
  HKEY hKey[11]; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v44; // [rsp+B0h] [rbp+8h]

  LODWORD(LastError) = 0;
  v8 = 0;
  v40 = 0;
  pPrevCertContext = 0;
  hKey[0] = 0;
  v10 = 0;
  v37 = 0;
  v44 = 0;
  v39 = 0;
  if ( !a2 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOids");
    v13 = L"pcszOids";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::FindAllCertificatesByOidValue", v13);
    goto LABEL_44;
  }
  if ( !a3 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pcszOidValues");
    v13 = L"pcszOidValues";
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      L"pdwCount");
    v13 = L"pdwCount";
    goto LABEL_3;
  }
  v12 = 0;
  v37 = *a7;
  *a7 = 0;
  if ( a1 == 1 && IsWinPEHost() )
  {
    Logger::TraceInformation(L"%s: System is WinPE.", L"CertificateUtil::FindAllCertificatesByOidValue");
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, hKey);
    LODWORD(LastError) = v14;
    if ( v14 )
    {
      Logger::TraceWarning(
        L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v14);
      KeyW = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
      if ( KeyW )
        Logger::TraceVerbose(
          L"%s: Always try unloading reg key \"%s\" first before loading it. RegUnLoadKeyW failed with error code: 0x%08x."
           " Failure ignored. Continue to load the key...",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware",
          KeyW);
      KeyWinPE = RegLoadKeyWinPE(v17, v16, v18, v19);
      v12 = KeyWinPE;
      if ( KeyWinPE < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"RegLoadKeyWinPE",
          (unsigned int)KeyWinPE);
        goto LABEL_15;
      }
      v40 = 1;
      v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, hKey);
      LODWORD(LastError) = v22;
      if ( v22 )
      {
        Logger::TraceError(
          L"%s: Cannot open registry key \"%s\". RegOpenKeyExW error code: 0x%08x.",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
          v22);
        goto LABEL_15;
      }
    }
    v23 = (const wchar_t *)hKey[0];
    v24 = 0x8000;
    v25 = 4;
  }
  else
  {
    v25 = 10;
    v23 = L"My";
    v24 = a1 != 0 ? 163840 : 98304;
  }
  v42 = CertOpenStore((LPCSTR)v25, 0, 0, v24, v23);
  v8 = v42;
  if ( v42 )
  {
LABEL_23:
    while ( 1 )
    {
      pCertContext = CertFindCertificateInStore(v8, 0x10001u, 0, 0, 0, pPrevCertContext);
      pPrevCertContext = pCertContext;
      if ( !pCertContext )
        break;
      ++v39;
      v26 = 1;
      v38 = 1;
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        if ( !v26 )
        {
          pPrevCertContext = pCertContext;
          v8 = v42;
          goto LABEL_23;
        }
        if ( (unsigned int)i >= a5 )
          break;
        Logger::TraceVerbose(
          L"%s: Will try to find the OID: '%hs' and value: '%.*s'",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          *(_QWORD *)(a2 + 8 * i),
          1024,
          *(_QWORD *)(a3 + 8 * i));
        v28 = *(_QWORD *)(a3 + 8 * i);
        v29 = *(const char **)(a2 + 8 * i);
        if ( v28 )
        {
          pPrevCertContext = pCertContext;
          DoesExtensionWithValueExist = CertificateUtil::DoesExtensionWithValueExist(
                                          v29,
                                          v28,
                                          *(unsigned int *)(a4 + 4 * i),
                                          pCertContext,
                                          &v38);
          v12 = DoesExtensionWithValueExist;
          if ( DoesExtensionWithValueExist < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"CertificateUtil::FindAllCertificatesByOidValue",
              L"CertificateUtil::DoesExtensionWithValueExist",
              (unsigned int)DoesExtensionWithValueExist);
            v8 = v42;
            goto LABEL_44;
          }
          v26 = v38;
        }
        else
        {
          if ( CertificateUtil::FindExtensionByOid(v29, pCertContext) )
            v26 = 0;
          v38 = v26;
        }
        v31 = L"TRUE";
        if ( !v26 )
          v31 = L"FALSE";
        Logger::TraceVerbose(L"%s: Cert matching: %s", L"CertificateUtil::FindAllCertificatesByOidValue", v31);
      }
      ++v44;
      pPrevCertContext = pCertContext;
      v8 = v42;
      if ( v37 > (unsigned int)v10 && a6 )
      {
        a6[v10] = (struct _CERT_CONTEXT *)CertDuplicateCertificateContext(pCertContext);
        v10 = (unsigned int)(v10 + 1);
      }
    }
    if ( v37 >= v44 && a6 )
    {
      *a7 = v10;
    }
    else
    {
      *a7 = v44;
      LODWORD(LastError) = 122;
    }
  }
  else
  {
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CertOpenStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      LastError);
  }
LABEL_44:
  if ( a1 )
  {
    if ( a1 != 1 )
    {
      v21 = L"Unknown";
      goto LABEL_48;
    }
LABEL_15:
    v21 = L"LocalMachine";
    goto LABEL_48;
  }
  v21 = L"CurrentUser";
LABEL_48:
  LODWORD(phkResult) = v39;
  Logger::TraceVerbose(
    L"%s: %u total %s certificate(s) found. %u certificate(s) checked.",
    L"CertificateUtil::FindAllCertificatesByOidValue",
    v44,
    v21,
    phkResult);
  if ( (_DWORD)LastError )
  {
    if ( (int)LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    else
      v12 = LastError;
  }
  if ( pPrevCertContext )
    CertFreeCertificateContext(pPrevCertContext);
  if ( v12 < 0 )
  {
    if ( v37 < (unsigned int)v10 )
      LODWORD(v10) = v37;
    CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)a6, v10);
  }
  if ( v8 && !CertCloseStore(v8, 0) )
  {
    v32 = GetLastError();
    if ( v32 > 0 )
      v32 = (unsigned __int16)v32 | 0x80070000;
    Logger::TraceWarning(
      L"%s: CertCloseStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      (unsigned int)v32);
  }
  if ( hKey[0] )
  {
    v33 = RegCloseKey(hKey[0]);
    if ( v33 )
      Logger::TraceWarning(
        L"%s: Cannot close reg key %s. RegCloseKey failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v33);
  }
  if ( v40 )
  {
    v34 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
    if ( v34 )
      Logger::TraceWarning(
        L"%s: Cannot unload reg key %s. RegUnLoadKeyW failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        v34);
    else
      Logger::TraceVerbose(
        L"%s: reg key \"%s\" unloaded.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware");
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002bcdc  mov     r11, rsp
0x18002bcdf  mov     [r11+20h], r9
0x18002bce3  mov     [r11+18h], r8
0x18002bce7  mov     [r11+10h], rdx
0x18002bceb  push    rbx
0x18002bcec  push    rbp
0x18002bced  push    rsi
0x18002bcee  push    rdi
0x18002bcef  push    r12
0x18002bcf1  push    r13
0x18002bcf3  push    r14
0x18002bcf5  push    r15
0x18002bcf7  sub     rsp, 68h
0x18002bcfb  xor     esi, esi
0x18002bcfd  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x18002bd04  xor     r12d, r12d
0x18002bd07  mov     [rsp+0A8h+var_6C], esi
0x18002bd0b  xor     ebp, ebp
0x18002bd0d  mov     [r11-58h], rsi
0x18002bd11  xor     r14d, r14d
0x18002bd14  mov     [rsp+0A8h+var_78], esi
0x18002bd18  mov     [rsp+0A8h+arg_0], esi
0x18002bd1f  mov     rax, r8
0x18002bd22  mov     [rsp+0A8h+var_70], esi
0x18002bd26  mov     r13d, ecx
0x18002bd29  test    rdx, rdx
0x18002bd2c  jnz     short loc_18002BD5D
0x18002bd2e  lea     r8, aPcszoids; "pcszOids"
0x18002bd35  mov     rdx, rbx
0x18002bd38  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18002bd3f  mov     edi, 80070057h
0x18002bd44  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002bd49  lea     rdx, aPcszoids; "pcszOids"
0x18002bd50  mov     rcx, rbx; unsigned __int16 *
0x18002bd53  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18002bd58  jmp     loc_18002C0F8
0x18002bd5d  test    rax, rax
0x18002bd60  jnz     short loc_18002BD86
0x18002bd62  lea     r8, aPcszoidvalues; "pcszOidValues"
0x18002bd69  mov     rdx, rbx
0x18002bd6c  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18002bd73  mov     edi, 80070057h
0x18002bd78  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002bd7d  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x18002bd84  jmp     short loc_18002BD50
0x18002bd86  mov     r15, [rsp+0A8h+arg_30]
0x18002bd8e  test    r15, r15
0x18002bd91  jnz     short loc_18002BDB7
0x18002bd93  lea     r8, aPdwcount; "pdwCount"
0x18002bd9a  mov     rdx, rbx
0x18002bd9d  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18002bda4  mov     edi, 80070057h
0x18002bda9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002bdae  lea     rdx, aPdwcount; "pdwCount"
0x18002bdb5  jmp     short loc_18002BD50
0x18002bdb7  mov     eax, [r15]
0x18002bdba  xor     edi, edi
0x18002bdbc  mov     [rsp+0A8h+var_78], eax
0x18002bdc0  mov     [r15], esi
0x18002bdc3  cmp     r13d, 1
0x18002bdc7  jnz     loc_18002BEEB
0x18002bdcd  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x18002bdd2  test    eax, eax
0x18002bdd4  jz      loc_18002BEEB
0x18002bdda  mov     rdx, rbx
0x18002bddd  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x18002bde4  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18002bde9  lea     rax, [rsp+0A8h+hKey]
0x18002bdee  mov     r9d, 20019h; samDesired
0x18002bdf4  xor     r8d, r8d; ulOptions
0x18002bdf7  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18002bdfc  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18002be03  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002be0a  call    cs:__imp_RegOpenKeyExW
0x18002be10  mov     esi, eax
0x18002be12  test    eax, eax
0x18002be14  jz      loc_18002BED9
0x18002be1a  mov     r9d, eax
0x18002be1d  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18002be24  mov     rdx, rbx
0x18002be27  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x18002be2e  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18002be33  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18002be3a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002be41  call    cs:__imp_RegUnLoadKeyW
0x18002be47  test    eax, eax
0x18002be49  jz      short loc_18002BE64
0x18002be4b  mov     r9d, eax
0x18002be4e  lea     r8, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x18002be55  mov     rdx, rbx
0x18002be58  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x18002be5f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002be64  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18002be69  mov     edi, eax
0x18002be6b  test    eax, eax
0x18002be6d  jns     short loc_18002BE94
0x18002be6f  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18002be76  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18002be7d  mov     rdx, rbx
0x18002be80  mov     r9d, eax
0x18002be83  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002be88  lea     r9, aLocalmachine; "LocalMachine"
0x18002be8f  jmp     loc_18002C117
0x18002be94  lea     rax, [rsp+0A8h+hKey]
0x18002be99  mov     [rsp+0A8h+var_6C], 1
0x18002bea1  mov     r9d, 20019h; samDesired
0x18002bea7  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18002beac  xor     r8d, r8d; ulOptions
0x18002beaf  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18002beb6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bebd  call    cs:__imp_RegOpenKeyExW
0x18002bec3  mov     esi, eax
0x18002bec5  test    eax, eax
0x18002bec7  jz      short loc_18002BED9
0x18002bec9  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18002bed0  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x18002bed7  jmp     short loc_18002BE7D
0x18002bed9  mov     rax, [rsp+0A8h+hKey]
0x18002bede  mov     r9d, 8000h
0x18002bee4  mov     ecx, 4
0x18002bee9  jmp     short loc_18002BF0D
0x18002beeb  mov     eax, r13d
0x18002beee  mov     ecx, 0Ah; lpszStoreProvider
0x18002bef3  neg     eax
0x18002bef5  lea     rax, aMy; "My"
0x18002befc  sbb     r9d, r9d
0x18002beff  and     r9d, 10000h
0x18002bf06  add     r9d, 18000h; dwFlags
0x18002bf0d  xor     r8d, r8d; hCryptProv
0x18002bf10  mov     [rsp+0A8h+phkResult], rax; pvPara
0x18002bf15  xor     edx, edx; dwEncodingType
0x18002bf17  call    cs:__imp_CertOpenStore
0x18002bf1d  mov     [rsp+0A8h+var_60], rax
0x18002bf22  mov     r12, rax
0x18002bf25  test    rax, rax
0x18002bf28  jnz     short loc_18002BF53
0x18002bf2a  call    cs:__imp_GetLastError
0x18002bf30  mov     rdx, rbx
0x18002bf33  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x18002bf3a  mov     r8d, eax
0x18002bf3d  mov     esi, eax
0x18002bf3f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002bf44  jmp     loc_18002C0F8
0x18002bf49  mov     rbp, [rsp+0A8h+pCertContext]
0x18002bf4e  mov     r12, [rsp+0A8h+var_60]
0x18002bf53  mov     [rsp+0A8h+pPrevCertContext], rbp; pPrevCertContext
0x18002bf58  xor     r9d, r9d; dwFindType
0x18002bf5b  xor     r8d, r8d; dwFindFlags
0x18002bf5e  mov     [rsp+0A8h+phkResult], 0; pvFindPara
0x18002bf67  mov     edx, 10001h; dwCertEncodingType
0x18002bf6c  mov     rcx, r12; hCertStore
0x18002bf6f  call    cs:__imp_CertFindCertificateInStore
0x18002bf75  mov     [rsp+0A8h+pCertContext], rax
0x18002bf7a  mov     rbp, rax
0x18002bf7d  test    rax, rax
0x18002bf80  jz      loc_18002C0D3
0x18002bf86  inc     [rsp+0A8h+var_70]
0x18002bf8a  mov     ebp, 1
0x18002bf8f  mov     [rsp+0A8h+var_74], ebp
0x18002bf93  xor     r12d, r12d
0x18002bf96  test    ebp, ebp
0x18002bf98  jz      short loc_18002BF49
0x18002bf9a  cmp     r12d, [rsp+0A8h+arg_20]
0x18002bfa2  jnb     loc_18002C06B
0x18002bfa8  mov     rax, [rsp+0A8h+arg_10]
0x18002bfb0  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x18002bfb7  mov     r8, [rsp+0A8h+arg_8]
0x18002bfbf  mov     r9d, 400h
0x18002bfc5  mov     rdx, rbx
0x18002bfc8  mov     rax, [rax+r12*8]
0x18002bfcc  mov     r8, [r8+r12*8]
0x18002bfd0  mov     [rsp+0A8h+phkResult], rax
0x18002bfd5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002bfda  mov     rax, [rsp+0A8h+arg_10]
0x18002bfe2  mov     rdx, [rax+r12*8]
0x18002bfe6  mov     rax, [rsp+0A8h+arg_8]
0x18002bfee  mov     rcx, [rax+r12*8]; char *
0x18002bff2  test    rdx, rdx
0x18002bff5  jz      short loc_18002C02A
0x18002bff7  mov     rbp, [rsp+0A8h+pCertContext]
0x18002bffc  lea     rax, [rsp+0A8h+var_74]
0x18002c001  mov     [rsp+0A8h+phkResult], rax
0x18002c006  mov     r9, rbp
0x18002c009  mov     rax, [rsp+0A8h+arg_18]
0x18002c011  mov     r8d, [rax+r12*4]
0x18002c015  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x18002c01a  mov     edi, eax
0x18002c01c  test    eax, eax
0x18002c01e  js      loc_18002C0B3
0x18002c024  mov     ebp, [rsp+0A8h+var_74]
0x18002c028  jmp     short loc_18002C040
0x18002c02a  mov     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT *
0x18002c02f  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x18002c034  xor     ecx, ecx
0x18002c036  test    rax, rax
0x18002c039  cmovnz  ebp, ecx
0x18002c03c  mov     [rsp+0A8h+var_74], ebp
0x18002c040  lea     rax, aFalse; "FALSE"
0x18002c047  test    ebp, ebp
0x18002c049  lea     r8, aTrue; "TRUE"
0x18002c050  mov     rdx, rbx
0x18002c053  cmovz   r8, rax
0x18002c057  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x18002c05e  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002c063  inc     r12d
0x18002c066  jmp     loc_18002BF96
0x18002c06b  inc     [rsp+0A8h+arg_0]
0x18002c072  mov     rbp, [rsp+0A8h+pCertContext]
0x18002c077  mov     r12, [rsp+0A8h+var_60]
0x18002c07c  cmp     [rsp+0A8h+var_78], r14d
0x18002c081  jbe     loc_18002BF53
0x18002c087  cmp     [rsp+0A8h+arg_28], 0
0x18002c090  jz      loc_18002BF53
0x18002c096  mov     rcx, rbp; pCertContext
0x18002c099  call    cs:__imp_CertDuplicateCertificateContext
0x18002c09f  mov     rdx, [rsp+0A8h+arg_28]
0x18002c0a7  mov     [rdx+r14*8], rax
0x18002c0ab  inc     r14d
0x18002c0ae  jmp     loc_18002BF53
0x18002c0b3  mov     r9d, eax
0x18002c0b6  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18002c0bd  mov     rdx, rbx
0x18002c0c0  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18002c0c7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18002c0cc  mov     r12, [rsp+0A8h+var_60]
0x18002c0d1  jmp     short loc_18002C0F8
0x18002c0d3  mov     eax, [rsp+0A8h+arg_0]
0x18002c0da  cmp     [rsp+0A8h+var_78], eax
0x18002c0de  jb      short loc_18002C0F0
0x18002c0e0  cmp     [rsp+0A8h+arg_28], 0
0x18002c0e9  jz      short loc_18002C0F0
0x18002c0eb  mov     [r15], r14d
0x18002c0ee  jmp     short loc_18002C0F8
0x18002c0f0  mov     [r15], eax
0x18002c0f3  mov     esi, 7Ah ; 'z'
0x18002c0f8  test    r13d, r13d
0x18002c0fb  jz      short loc_18002C110
0x18002c0fd  cmp     r13d, 1
0x18002c101  jz      loc_18002BE88
0x18002c107  lea     r9, aUnknown; "Unknown"
0x18002c10e  jmp     short loc_18002C117
0x18002c110  lea     r9, aCurrentuser; "CurrentUser"
0x18002c117  mov     eax, [rsp+0A8h+var_70]
0x18002c11b  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x18002c122  mov     r8d, [rsp+0A8h+arg_0]
0x18002c12a  mov     rdx, rbx
0x18002c12d  mov     dword ptr [rsp+0A8h+phkResult], eax
0x18002c131  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18002c136  mov     r15d, 80070000h
0x18002c13c  test    esi, esi
0x18002c13e  jz      short loc_18002C14C
0x18002c140  jg      short loc_18002C146
0x18002c142  mov     edi, esi
0x18002c144  jmp     short loc_18002C14C
0x18002c146  movzx   edi, si
0x18002c149  or      edi, r15d
0x18002c14c  test    rbp, rbp
0x18002c14f  jz      short loc_18002C15A
0x18002c151  mov     rcx, rbp; pCertContext
0x18002c154  call    cs:__imp_CertFreeCertificateContext
0x18002c15a  test    edi, edi
0x18002c15c  jns     short loc_18002C179
0x18002c15e  cmp     [rsp+0A8h+var_78], r14d
0x18002c163  mov     rcx, [rsp+0A8h+arg_28]; struct _CERT_CONTEXT **
0x18002c16b  cmovb   r14d, [rsp+0A8h+var_78]
0x18002c171  mov     edx, r14d; unsigned int
0x18002c174  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x18002c179  test    r12, r12
0x18002c17c  jz      short loc_18002C1AF
0x18002c17e  xor     edx, edx; dwFlags
0x18002c180  mov     rcx, r12; hCertStore
0x18002c183  call    cs:__imp_CertCloseStore
0x18002c189  test    eax, eax
0x18002c18b  jnz     short loc_18002C1AF
0x18002c18d  call    cs:__imp_GetLastError
0x18002c193  test    eax, eax
0x18002c195  jle     short loc_18002C19D
0x18002c197  movzx   eax, ax
0x18002c19a  or      eax, r15d
0x18002c19d  mov     r8d, eax
0x18002c1a0  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x18002c1a7  mov     rdx, rbx
0x18002c1aa  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18002c1af  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18002c1b4  test    rcx, rcx
0x18002c1b7  jz      short loc_18002C1DC
0x18002c1b9  call    cs:__imp_RegCloseKey
0x18002c1bf  test    eax, eax
0x18002c1c1  jz      short loc_18002C1DC
0x18002c1c3  mov     r9d, eax
0x18002c1c6  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18002c1cd  mov     rdx, rbx
0x18002c1d0  lea     rcx, aSCannotCloseRe; "%s: Cannot close reg key %s. RegCloseKe"...
0x18002c1d7  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18002c1dc  cmp     [rsp+0A8h+var_6C], 0
0x18002c1e1  jz      short loc_18002C222
0x18002c1e3  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18002c1ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c1f1  call    cs:__imp_RegUnLoadKeyW
0x18002c1f7  lea     r8, aHkeyLocalMachi_3; "HKEY_LOCAL_MACHINE\\TargetSoftware"
  ... truncated ...
```
