# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x1800b7a6c`
- end: `0x1800b800e`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1442`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180146bec`

## callees

- `0x18007d6cc`
- `0x18007d7c4`
- `0x18007de38`
- `0x18007df04`
- `0x18007df64`
- `0x18008ef34`
- `0x1800ad648`
- `0x1800b27f4`
- `0x1800b4ea8`
- `0x1800b7a6c`
- `0x1800b8014`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7f53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b7f53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7f85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7f85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7b9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7c59`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7b9a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7c59`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b7bd7`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b7fc3`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b7bd7`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800b7fc3`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800b7e4d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800b7e4d`
- `CRYPT32!CertCloseStore` at `0x1800b7f43`
- `CRYPT32!CertCloseStore` at `0x1800b7f43`
- `CRYPT32!CertFreeCertificateContext` at `0x1800b7f0e`
- `CRYPT32!CertFreeCertificateContext` at `0x1800b7f0e`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b7d1d`
- `CRYPT32!CertFindCertificateInStore` at `0x1800b7d1d`
- `CRYPT32!CertOpenStore` at `0x1800b7cb9`
- `CRYPT32!CertOpenStore` at `0x1800b7cb9`

## string_xrefs

- `0x1800b7e70`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800b7bbd`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x1800b7c72`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x1800b7ce1`: `%s: CertOpenStore failed with error code: 0x%08x`

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
  const wchar_t *p_hCertStore; // r9
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
  if ( a1 == 1 && (unsigned int)IsWinPEHost() )
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
      p_hCertStore = L"Unknown";
      goto LABEL_48;
    }
LABEL_15:
    p_hCertStore = (const wchar_t *)&stru_18017B288.hCertStore;
    goto LABEL_48;
  }
  p_hCertStore = L"CurrentUser";
LABEL_48:
  LODWORD(phkResult) = v39;
  Logger::TraceVerbose(
    L"%s: %u total %s certificate(s) found. %u certificate(s) checked.",
    L"CertificateUtil::FindAllCertificatesByOidValue",
    v44,
    p_hCertStore,
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
0x1800b7a6c  mov     r11, rsp
0x1800b7a6f  mov     [r11+20h], r9
0x1800b7a73  mov     [r11+18h], r8
0x1800b7a77  mov     [r11+10h], rdx
0x1800b7a7b  push    rbx
0x1800b7a7c  push    rbp
0x1800b7a7d  push    rsi
0x1800b7a7e  push    rdi
0x1800b7a7f  push    r12
0x1800b7a81  push    r13
0x1800b7a83  push    r14
0x1800b7a85  push    r15
0x1800b7a87  sub     rsp, 68h
0x1800b7a8b  xor     esi, esi
0x1800b7a8d  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x1800b7a94  xor     r12d, r12d
0x1800b7a97  mov     [rsp+0A8h+var_6C], esi
0x1800b7a9b  xor     ebp, ebp
0x1800b7a9d  mov     [r11-58h], rsi
0x1800b7aa1  xor     r14d, r14d
0x1800b7aa4  mov     [rsp+0A8h+var_78], esi
0x1800b7aa8  mov     [rsp+0A8h+arg_0], esi
0x1800b7aaf  mov     rax, r8
0x1800b7ab2  mov     [rsp+0A8h+var_70], esi
0x1800b7ab6  mov     r13d, ecx
0x1800b7ab9  test    rdx, rdx
0x1800b7abc  jnz     short loc_1800B7AED
0x1800b7abe  lea     r8, aPcszoids; "pcszOids"
0x1800b7ac5  mov     rdx, rbx
0x1800b7ac8  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b7acf  mov     edi, 80070057h
0x1800b7ad4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7ad9  lea     rdx, aPcszoids; "pcszOids"
0x1800b7ae0  mov     rcx, rbx; unsigned __int16 *
0x1800b7ae3  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800b7ae8  jmp     loc_1800B7EB2
0x1800b7aed  test    rax, rax
0x1800b7af0  jnz     short loc_1800B7B16
0x1800b7af2  lea     r8, aPcszoidvalues; "pcszOidValues"
0x1800b7af9  mov     rdx, rbx
0x1800b7afc  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b7b03  mov     edi, 80070057h
0x1800b7b08  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7b0d  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x1800b7b14  jmp     short loc_1800B7AE0
0x1800b7b16  mov     r15, [rsp+0A8h+arg_30]
0x1800b7b1e  test    r15, r15
0x1800b7b21  jnz     short loc_1800B7B47
0x1800b7b23  lea     r8, aPdwcount; "pdwCount"
0x1800b7b2a  mov     rdx, rbx
0x1800b7b2d  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800b7b34  mov     edi, 80070057h
0x1800b7b39  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7b3e  lea     rdx, aPdwcount; "pdwCount"
0x1800b7b45  jmp     short loc_1800B7AE0
0x1800b7b47  mov     eax, [r15]
0x1800b7b4a  xor     edi, edi
0x1800b7b4c  mov     [rsp+0A8h+var_78], eax
0x1800b7b50  mov     [r15], esi
0x1800b7b53  cmp     r13d, 1
0x1800b7b57  jnz     loc_1800B7C8D
0x1800b7b5d  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x1800b7b62  test    eax, eax
0x1800b7b64  jz      loc_1800B7C8D
0x1800b7b6a  mov     rdx, rbx
0x1800b7b6d  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x1800b7b74  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x1800b7b79  lea     rax, [rsp+0A8h+hKey]
0x1800b7b7e  mov     r9d, 20019h; samDesired
0x1800b7b84  xor     r8d, r8d; ulOptions
0x1800b7b87  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800b7b8c  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x1800b7b93  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b7b9a  call    cs:__imp_RegOpenKeyExW
0x1800b7ba1  nop     dword ptr [rax+rax+00h]
0x1800b7ba6  mov     esi, eax
0x1800b7ba8  test    eax, eax
0x1800b7baa  jz      loc_1800B7C7B
0x1800b7bb0  mov     r9d, eax
0x1800b7bb3  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x1800b7bba  mov     rdx, rbx
0x1800b7bbd  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x1800b7bc4  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800b7bc9  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x1800b7bd0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b7bd7  call    cs:__imp_RegUnLoadKeyW
0x1800b7bde  nop     dword ptr [rax+rax+00h]
0x1800b7be3  test    eax, eax
0x1800b7be5  jz      short loc_1800B7C00
0x1800b7be7  mov     r9d, eax
0x1800b7bea  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x1800b7bf1  mov     rdx, rbx
0x1800b7bf4  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x1800b7bfb  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b7c00  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800b7c05  mov     edi, eax
0x1800b7c07  test    eax, eax
0x1800b7c09  jns     short loc_1800B7C30
0x1800b7c0b  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800b7c12  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800b7c19  mov     rdx, rbx
0x1800b7c1c  mov     r9d, eax
0x1800b7c1f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7c24  lea     r9, stru_18017B288.hCertStore
0x1800b7c2b  jmp     loc_1800B7ED1
0x1800b7c30  lea     rax, [rsp+0A8h+hKey]
0x1800b7c35  mov     [rsp+0A8h+var_6C], 1
0x1800b7c3d  mov     r9d, 20019h; samDesired
0x1800b7c43  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800b7c48  xor     r8d, r8d; ulOptions
0x1800b7c4b  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x1800b7c52  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b7c59  call    cs:__imp_RegOpenKeyExW
0x1800b7c60  nop     dword ptr [rax+rax+00h]
0x1800b7c65  mov     esi, eax
0x1800b7c67  test    eax, eax
0x1800b7c69  jz      short loc_1800B7C7B
0x1800b7c6b  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x1800b7c72  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x1800b7c79  jmp     short loc_1800B7C19
0x1800b7c7b  mov     rax, [rsp+0A8h+hKey]
0x1800b7c80  mov     r9d, 8000h
0x1800b7c86  mov     ecx, 4
0x1800b7c8b  jmp     short loc_1800B7CAF
0x1800b7c8d  mov     eax, r13d
0x1800b7c90  mov     ecx, 0Ah; lpszStoreProvider
0x1800b7c95  neg     eax
0x1800b7c97  lea     rax, aMy; "My"
0x1800b7c9e  sbb     r9d, r9d
0x1800b7ca1  and     r9d, 10000h
0x1800b7ca8  add     r9d, 18000h; dwFlags
0x1800b7caf  xor     r8d, r8d; hCryptProv
0x1800b7cb2  mov     [rsp+0A8h+phkResult], rax; pvPara
0x1800b7cb7  xor     edx, edx; dwEncodingType
0x1800b7cb9  call    cs:__imp_CertOpenStore
0x1800b7cc0  nop     dword ptr [rax+rax+00h]
0x1800b7cc5  mov     [rsp+0A8h+var_60], rax
0x1800b7cca  mov     r12, rax
0x1800b7ccd  test    rax, rax
0x1800b7cd0  jnz     short loc_1800B7D01
0x1800b7cd2  call    cs:__imp_GetLastError
0x1800b7cd9  nop     dword ptr [rax+rax+00h]
0x1800b7cde  mov     rdx, rbx
0x1800b7ce1  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x1800b7ce8  mov     r8d, eax
0x1800b7ceb  mov     esi, eax
0x1800b7ced  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7cf2  jmp     loc_1800B7EB2
0x1800b7cf7  mov     rbp, [rsp+0A8h+pCertContext]
0x1800b7cfc  mov     r12, [rsp+0A8h+var_60]
0x1800b7d01  mov     [rsp+0A8h+pPrevCertContext], rbp; pPrevCertContext
0x1800b7d06  xor     r9d, r9d; dwFindType
0x1800b7d09  xor     r8d, r8d; dwFindFlags
0x1800b7d0c  mov     [rsp+0A8h+phkResult], 0; pvFindPara
0x1800b7d15  mov     edx, 10001h; dwCertEncodingType
0x1800b7d1a  mov     rcx, r12; hCertStore
0x1800b7d1d  call    cs:__imp_CertFindCertificateInStore
0x1800b7d24  nop     dword ptr [rax+rax+00h]
0x1800b7d29  mov     [rsp+0A8h+pCertContext], rax
0x1800b7d2e  mov     rbp, rax
0x1800b7d31  test    rax, rax
0x1800b7d34  jz      loc_1800B7E8D
0x1800b7d3a  inc     [rsp+0A8h+var_70]
0x1800b7d3e  mov     ebp, 1
0x1800b7d43  mov     [rsp+0A8h+var_74], ebp
0x1800b7d47  xor     r12d, r12d
0x1800b7d4a  test    ebp, ebp
0x1800b7d4c  jz      short loc_1800B7CF7
0x1800b7d4e  cmp     r12d, [rsp+0A8h+arg_20]
0x1800b7d56  jnb     loc_1800B7E1F
0x1800b7d5c  mov     rax, [rsp+0A8h+arg_10]
0x1800b7d64  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x1800b7d6b  mov     r8, [rsp+0A8h+arg_8]
0x1800b7d73  mov     r9d, 400h
0x1800b7d79  mov     rdx, rbx
0x1800b7d7c  mov     rax, [rax+r12*8]
0x1800b7d80  mov     r8, [r8+r12*8]
0x1800b7d84  mov     [rsp+0A8h+phkResult], rax
0x1800b7d89  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b7d8e  mov     rax, [rsp+0A8h+arg_10]
0x1800b7d96  mov     rdx, [rax+r12*8]
0x1800b7d9a  mov     rax, [rsp+0A8h+arg_8]
0x1800b7da2  mov     rcx, [rax+r12*8]; char *
0x1800b7da6  test    rdx, rdx
0x1800b7da9  jz      short loc_1800B7DDE
0x1800b7dab  mov     rbp, [rsp+0A8h+pCertContext]
0x1800b7db0  lea     rax, [rsp+0A8h+var_74]
0x1800b7db5  mov     [rsp+0A8h+phkResult], rax
0x1800b7dba  mov     r9, rbp
0x1800b7dbd  mov     rax, [rsp+0A8h+arg_18]
0x1800b7dc5  mov     r8d, [rax+r12*4]
0x1800b7dc9  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x1800b7dce  mov     edi, eax
0x1800b7dd0  test    eax, eax
0x1800b7dd2  js      loc_1800B7E6D
0x1800b7dd8  mov     ebp, [rsp+0A8h+var_74]
0x1800b7ddc  jmp     short loc_1800B7DF4
0x1800b7dde  mov     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT *
0x1800b7de3  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x1800b7de8  xor     ecx, ecx
0x1800b7dea  test    rax, rax
0x1800b7ded  cmovnz  ebp, ecx
0x1800b7df0  mov     [rsp+0A8h+var_74], ebp
0x1800b7df4  lea     rax, aFalse; "FALSE"
0x1800b7dfb  test    ebp, ebp
0x1800b7dfd  lea     r8, aTrue_0; "TRUE"
0x1800b7e04  mov     rdx, rbx
0x1800b7e07  cmovz   r8, rax
0x1800b7e0b  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x1800b7e12  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b7e17  inc     r12d
0x1800b7e1a  jmp     loc_1800B7D4A
0x1800b7e1f  inc     [rsp+0A8h+arg_0]
0x1800b7e26  mov     rbp, [rsp+0A8h+pCertContext]
0x1800b7e2b  mov     r12, [rsp+0A8h+var_60]
0x1800b7e30  cmp     [rsp+0A8h+var_78], r14d
0x1800b7e35  jbe     loc_1800B7D01
0x1800b7e3b  cmp     [rsp+0A8h+arg_28], 0
0x1800b7e44  jz      loc_1800B7D01
0x1800b7e4a  mov     rcx, rbp; pCertContext
0x1800b7e4d  call    cs:__imp_CertDuplicateCertificateContext
0x1800b7e54  nop     dword ptr [rax+rax+00h]
0x1800b7e59  mov     rdx, [rsp+0A8h+arg_28]
0x1800b7e61  mov     [rdx+r14*8], rax
0x1800b7e65  inc     r14d
0x1800b7e68  jmp     loc_1800B7D01
0x1800b7e6d  mov     r9d, eax
0x1800b7e70  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800b7e77  mov     rdx, rbx
0x1800b7e7a  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800b7e81  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b7e86  mov     r12, [rsp+0A8h+var_60]
0x1800b7e8b  jmp     short loc_1800B7EB2
0x1800b7e8d  mov     eax, [rsp+0A8h+arg_0]
0x1800b7e94  cmp     [rsp+0A8h+var_78], eax
0x1800b7e98  jb      short loc_1800B7EAA
0x1800b7e9a  cmp     [rsp+0A8h+arg_28], 0
0x1800b7ea3  jz      short loc_1800B7EAA
0x1800b7ea5  mov     [r15], r14d
0x1800b7ea8  jmp     short loc_1800B7EB2
0x1800b7eaa  mov     [r15], eax
0x1800b7ead  mov     esi, 7Ah ; 'z'
0x1800b7eb2  test    r13d, r13d
0x1800b7eb5  jz      short loc_1800B7ECA
0x1800b7eb7  cmp     r13d, 1
0x1800b7ebb  jz      loc_1800B7C24
0x1800b7ec1  lea     r9, aUnknown; "Unknown"
0x1800b7ec8  jmp     short loc_1800B7ED1
0x1800b7eca  lea     r9, aCurrentuser; "CurrentUser"
0x1800b7ed1  mov     eax, [rsp+0A8h+var_70]
0x1800b7ed5  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x1800b7edc  mov     r8d, [rsp+0A8h+arg_0]
0x1800b7ee4  mov     rdx, rbx
0x1800b7ee7  mov     dword ptr [rsp+0A8h+phkResult], eax
0x1800b7eeb  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b7ef0  mov     r15d, 80070000h
0x1800b7ef6  test    esi, esi
0x1800b7ef8  jz      short loc_1800B7F06
0x1800b7efa  jg      short loc_1800B7F00
0x1800b7efc  mov     edi, esi
0x1800b7efe  jmp     short loc_1800B7F06
0x1800b7f00  movzx   edi, si
0x1800b7f03  or      edi, r15d
0x1800b7f06  test    rbp, rbp
0x1800b7f09  jz      short loc_1800B7F1A
0x1800b7f0b  mov     rcx, rbp; pCertContext
0x1800b7f0e  call    cs:__imp_CertFreeCertificateContext
0x1800b7f15  nop     dword ptr [rax+rax+00h]
0x1800b7f1a  test    edi, edi
0x1800b7f1c  jns     short loc_1800B7F39
0x1800b7f1e  cmp     [rsp+0A8h+var_78], r14d
0x1800b7f23  mov     rcx, [rsp+0A8h+arg_28]; struct _CERT_CONTEXT **
0x1800b7f2b  cmovb   r14d, [rsp+0A8h+var_78]
0x1800b7f31  mov     edx, r14d; unsigned int
0x1800b7f34  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x1800b7f39  test    r12, r12
0x1800b7f3c  jz      short loc_1800B7F7B
0x1800b7f3e  xor     edx, edx; dwFlags
0x1800b7f40  mov     rcx, r12; hCertStore
0x1800b7f43  call    cs:__imp_CertCloseStore
0x1800b7f4a  nop     dword ptr [rax+rax+00h]
0x1800b7f4f  test    eax, eax
0x1800b7f51  jnz     short loc_1800B7F7B
0x1800b7f53  call    cs:__imp_GetLastError
0x1800b7f5a  nop     dword ptr [rax+rax+00h]
0x1800b7f5f  test    eax, eax
0x1800b7f61  jle     short loc_1800B7F69
0x1800b7f63  movzx   eax, ax
0x1800b7f66  or      eax, r15d
0x1800b7f69  mov     r8d, eax
0x1800b7f6c  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x1800b7f73  mov     rdx, rbx
0x1800b7f76  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800b7f7b  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800b7f80  test    rcx, rcx
0x1800b7f83  jz      short loc_1800B7FAE
0x1800b7f85  call    cs:__imp_RegCloseKey
0x1800b7f8c  nop     dword ptr [rax+rax+00h]
0x1800b7f91  test    eax, eax
0x1800b7f93  jz      short loc_1800B7FAE
  ... truncated ...
```
