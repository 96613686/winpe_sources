# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x18007cc34`
- end: `0x18007d1fa`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1478`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007e188`

## callees

- `0x180025b2c`
- `0x18002ee04`
- `0x18002ee70`
- `0x18002f048`
- `0x18002f324`
- `0x18007ca8c`
- `0x18007cc34`
- `0x18007d200`
- `0x18007d6d4`
- `0x18007dd48`
- `0x18007dd84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d13f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d13f`
- `CRYPT32!CertCloseStore` at `0x18007d12f`
- `CRYPT32!CertCloseStore` at `0x18007d12f`
- `CRYPT32!CertFindCertificateInStore` at `0x18007ced9`
- `CRYPT32!CertFindCertificateInStore` at `0x18007d037`
- `CRYPT32!CertFindCertificateInStore` at `0x18007ced9`
- `CRYPT32!CertFindCertificateInStore` at `0x18007d037`
- `CRYPT32!CertFreeCertificateContext` at `0x18007d0fa`
- `CRYPT32!CertFreeCertificateContext` at `0x18007d0fa`
- `CRYPT32!CertOpenStore` at `0x18007ce83`
- `CRYPT32!CertOpenStore` at `0x18007ce83`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007cffe`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007cffe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d171`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d171`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007cd64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ce23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007cd64`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007ce23`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18007cda1`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18007d1af`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18007cda1`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18007d1af`

## string_xrefs

- `0x18007cd87`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x18007ce3c`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x18007ceab`: `%s: CertOpenStore failed with error code: 0x%08x`
- `0x18007d085`: `CertificateUtil::DoesExtensionWithValueExist`

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
  HCERTSTORE v8; // r15
  const CERT_CONTEXT *v9; // rbp
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
  HKEY v23; // rax
  DWORD v24; // r9d
  __int64 v25; // rcx
  HCERTSTORE v26; // rax
  int v27; // ebp
  __int64 v28; // r15
  __int64 v29; // rdx
  const char *v30; // rcx
  int DoesExtensionWithValueExist; // eax
  const wchar_t *v32; // r8
  unsigned int v33; // eax
  signed int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-88h]
  unsigned int v39; // [rsp+30h] [rbp-78h]
  int v40; // [rsp+34h] [rbp-74h] BYREF
  int v41; // [rsp+38h] [rbp-70h]
  int v42; // [rsp+3Ch] [rbp-6Ch]
  PCCERT_CONTEXT pCertContext; // [rsp+40h] [rbp-68h]
  HKEY hKey; // [rsp+48h] [rbp-60h] BYREF
  HCERTSTORE hCertStore; // [rsp+50h] [rbp-58h]
  unsigned int v46; // [rsp+B0h] [rbp+8h]

  LODWORD(LastError) = 0;
  v8 = 0;
  v42 = 0;
  v9 = 0;
  hKey = 0;
  v10 = 0;
  v39 = 0;
  v46 = 0;
  v41 = 0;
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
    goto LABEL_41;
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
  v39 = *a7;
  *a7 = 0;
  if ( a1 == 1 && (unsigned int)IsWinPEHost() )
  {
    Logger::TraceInformation(L"%s: System is WinPE.", L"CertificateUtil::FindAllCertificatesByOidValue");
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, &hKey);
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
      v42 = 1;
      v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"TargetSoftware\\Microsoft\\SystemCertificates\\MY", 0, 0x20019u, &hKey);
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
    v23 = hKey;
    v24 = 0x8000;
    v25 = 4;
  }
  else
  {
    v25 = 10;
    v23 = (HKEY)L"My";
    v24 = a1 != 0 ? 163840 : 98304;
  }
  v26 = CertOpenStore((LPCSTR)v25, 0, 0, v24, v23);
  hCertStore = v26;
  v8 = v26;
  if ( !v26 )
  {
    LastError = GetLastError();
    Logger::TraceError(
      L"%s: CertOpenStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      LastError);
    goto LABEL_41;
  }
  pCertContext = CertFindCertificateInStore(v26, 0x10001u, 0, 0, 0, 0);
  v9 = pCertContext;
  if ( pCertContext )
  {
    do
    {
      ++v41;
      v27 = 1;
      v40 = 1;
      v28 = 0;
      do
      {
        if ( (unsigned int)v28 >= a5 )
          break;
        Logger::TraceVerbose(
          L"%s: Will try to find the OID: '%hs' and value: '%.*s'",
          L"CertificateUtil::FindAllCertificatesByOidValue",
          *(_QWORD *)(a2 + 8 * v28),
          1024,
          *(_QWORD *)(a3 + 8 * v28));
        v29 = *(_QWORD *)(a3 + 8 * v28);
        v30 = *(const char **)(a2 + 8 * v28);
        if ( v29 )
        {
          v9 = pCertContext;
          DoesExtensionWithValueExist = CertificateUtil::DoesExtensionWithValueExist(
                                          v30,
                                          v29,
                                          *(unsigned int *)(a4 + 4 * v28),
                                          pCertContext,
                                          &v40);
          v12 = DoesExtensionWithValueExist;
          if ( DoesExtensionWithValueExist < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"CertificateUtil::FindAllCertificatesByOidValue",
              L"CertificateUtil::DoesExtensionWithValueExist",
              (unsigned int)DoesExtensionWithValueExist);
            v8 = hCertStore;
            goto LABEL_41;
          }
          v27 = v40;
        }
        else
        {
          if ( CertificateUtil::FindExtensionByOid(v30, pCertContext) )
            v27 = 0;
          v40 = v27;
        }
        v32 = L"TRUE";
        if ( !v27 )
          v32 = L"FALSE";
        Logger::TraceVerbose(L"%s: Cert matching: %s", L"CertificateUtil::FindAllCertificatesByOidValue", v32);
        v28 = (unsigned int)(v28 + 1);
      }
      while ( v27 );
      if ( v27 )
      {
        ++v46;
        if ( v39 > (unsigned int)v10 )
        {
          if ( a6 )
          {
            a6[v10] = (struct _CERT_CONTEXT *)CertDuplicateCertificateContext(pCertContext);
            v10 = (unsigned int)(v10 + 1);
          }
        }
      }
      v8 = hCertStore;
      pCertContext = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0, 0, pCertContext);
      v9 = pCertContext;
    }
    while ( pCertContext );
    v33 = v46;
    if ( v39 >= v46 )
      goto LABEL_46;
    goto LABEL_40;
  }
  v33 = 0;
LABEL_46:
  if ( !a6 )
  {
LABEL_40:
    *a7 = v33;
    LODWORD(LastError) = 122;
    goto LABEL_41;
  }
  *a7 = v10;
LABEL_41:
  if ( a1 )
  {
    if ( a1 != 1 )
    {
      p_hCertStore = L"Unknown";
      goto LABEL_49;
    }
LABEL_15:
    p_hCertStore = L"LocalMachine";
    goto LABEL_49;
  }
  p_hCertStore = (const wchar_t *)&stru_18008DE98.hCertStore;
LABEL_49:
  LODWORD(phkResult) = v41;
  Logger::TraceVerbose(
    L"%s: %u total %s certificate(s) found. %u certificate(s) checked.",
    L"CertificateUtil::FindAllCertificatesByOidValue",
    v46,
    p_hCertStore,
    phkResult);
  if ( (_DWORD)LastError )
  {
    if ( (int)LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    else
      v12 = LastError;
  }
  if ( v9 )
    CertFreeCertificateContext(v9);
  if ( v12 < 0 )
  {
    if ( v39 < (unsigned int)v10 )
      LODWORD(v10) = v39;
    CertificateUtil::FreeCertificates((const struct _CERT_CONTEXT **const)a6, v10);
  }
  if ( v8 && !CertCloseStore(v8, 0) )
  {
    v34 = GetLastError();
    if ( v34 > 0 )
      v34 = (unsigned __int16)v34 | 0x80070000;
    Logger::TraceWarning(
      L"%s: CertCloseStore failed with error code: 0x%08x",
      L"CertificateUtil::FindAllCertificatesByOidValue",
      (unsigned int)v34);
  }
  if ( hKey )
  {
    v35 = RegCloseKey(hKey);
    if ( v35 )
      Logger::TraceWarning(
        L"%s: Cannot close reg key %s. RegCloseKey failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware\\Microsoft\\SystemCertificates\\MY",
        v35);
  }
  if ( v42 )
  {
    v36 = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"TargetSoftware");
    if ( v36 )
      Logger::TraceWarning(
        L"%s: Cannot unload reg key %s. RegUnLoadKeyW failed with error code: 0x%08x.",
        L"CertificateUtil::FindAllCertificatesByOidValue",
        L"HKEY_LOCAL_MACHINE\\TargetSoftware",
        v36);
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
0x18007cc34  mov     r11, rsp
0x18007cc37  mov     [r11+20h], r9
0x18007cc3b  mov     [r11+18h], r8
0x18007cc3f  mov     [r11+10h], rdx
0x18007cc43  push    rbx
0x18007cc44  push    rbp
0x18007cc45  push    rsi
0x18007cc46  push    rdi
0x18007cc47  push    r12
0x18007cc49  push    r13
0x18007cc4b  push    r14
0x18007cc4d  push    r15
0x18007cc4f  sub     rsp, 68h
0x18007cc53  xor     esi, esi
0x18007cc55  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x18007cc5c  xor     r15d, r15d
0x18007cc5f  mov     [rsp+0A8h+var_6C], esi
0x18007cc63  xor     ebp, ebp
0x18007cc65  mov     [r11-60h], rsi
0x18007cc69  xor     r14d, r14d
0x18007cc6c  mov     [rsp+0A8h+var_78], esi
0x18007cc70  mov     [rsp+0A8h+arg_0], esi
0x18007cc77  mov     rax, r8
0x18007cc7a  mov     [rsp+0A8h+var_70], esi
0x18007cc7e  mov     r13d, ecx
0x18007cc81  test    rdx, rdx
0x18007cc84  jnz     short loc_18007CCB5
0x18007cc86  lea     r8, aPcszoids; "pcszOids"
0x18007cc8d  mov     rdx, rbx
0x18007cc90  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007cc97  mov     edi, 80070057h
0x18007cc9c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007cca1  lea     rdx, aPcszoids; "pcszOids"
0x18007cca8  mov     rcx, rbx; unsigned __int16 *
0x18007ccab  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007ccb0  jmp     loc_18007D06A
0x18007ccb5  test    rax, rax
0x18007ccb8  jnz     short loc_18007CCDE
0x18007ccba  lea     r8, aPcszoidvalues; "pcszOidValues"
0x18007ccc1  mov     rdx, rbx
0x18007ccc4  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007cccb  mov     edi, 80070057h
0x18007ccd0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007ccd5  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x18007ccdc  jmp     short loc_18007CCA8
0x18007ccde  mov     r12, [rsp+0A8h+arg_30]
0x18007cce6  test    r12, r12
0x18007cce9  jnz     short loc_18007CD0F
0x18007cceb  lea     r8, aPdwcount; "pdwCount"
0x18007ccf2  mov     rdx, rbx
0x18007ccf5  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007ccfc  mov     edi, 80070057h
0x18007cd01  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007cd06  lea     rdx, aPdwcount; "pdwCount"
0x18007cd0d  jmp     short loc_18007CCA8
0x18007cd0f  mov     eax, [r12]
0x18007cd13  xor     edi, edi
0x18007cd15  mov     [rsp+0A8h+var_78], eax
0x18007cd19  mov     [r12], esi
0x18007cd1d  cmp     r13d, 1
0x18007cd21  jnz     loc_18007CE57
0x18007cd27  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x18007cd2c  test    eax, eax
0x18007cd2e  jz      loc_18007CE57
0x18007cd34  mov     rdx, rbx
0x18007cd37  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x18007cd3e  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18007cd43  lea     rax, [rsp+0A8h+hKey]
0x18007cd48  mov     r9d, 20019h; samDesired
0x18007cd4e  xor     r8d, r8d; ulOptions
0x18007cd51  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18007cd56  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18007cd5d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007cd64  call    cs:__imp_RegOpenKeyExW
0x18007cd6b  nop     dword ptr [rax+rax+00h]
0x18007cd70  mov     esi, eax
0x18007cd72  test    eax, eax
0x18007cd74  jz      loc_18007CE45
0x18007cd7a  mov     r9d, eax
0x18007cd7d  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18007cd84  mov     rdx, rbx
0x18007cd87  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x18007cd8e  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18007cd93  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x18007cd9a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007cda1  call    cs:__imp_RegUnLoadKeyW
0x18007cda8  nop     dword ptr [rax+rax+00h]
0x18007cdad  test    eax, eax
0x18007cdaf  jz      short loc_18007CDCA
0x18007cdb1  mov     r9d, eax
0x18007cdb4  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x18007cdbb  mov     rdx, rbx
0x18007cdbe  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x18007cdc5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007cdca  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18007cdcf  mov     edi, eax
0x18007cdd1  test    eax, eax
0x18007cdd3  jns     short loc_18007CDFA
0x18007cdd5  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x18007cddc  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18007cde3  mov     rdx, rbx
0x18007cde6  mov     r9d, eax
0x18007cde9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007cdee  lea     r9, aLocalmachine; "LocalMachine"
0x18007cdf5  jmp     loc_18007D0BD
0x18007cdfa  lea     rax, [rsp+0A8h+hKey]
0x18007cdff  mov     [rsp+0A8h+var_6C], 1
0x18007ce07  mov     r9d, 20019h; samDesired
0x18007ce0d  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18007ce12  xor     r8d, r8d; ulOptions
0x18007ce15  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x18007ce1c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007ce23  call    cs:__imp_RegOpenKeyExW
0x18007ce2a  nop     dword ptr [rax+rax+00h]
0x18007ce2f  mov     esi, eax
0x18007ce31  test    eax, eax
0x18007ce33  jz      short loc_18007CE45
0x18007ce35  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x18007ce3c  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x18007ce43  jmp     short loc_18007CDE3
0x18007ce45  mov     rax, [rsp+0A8h+hKey]
0x18007ce4a  mov     r9d, 8000h
0x18007ce50  mov     ecx, 4
0x18007ce55  jmp     short loc_18007CE79
0x18007ce57  mov     eax, r13d
0x18007ce5a  mov     ecx, 0Ah; lpszStoreProvider
0x18007ce5f  neg     eax
0x18007ce61  lea     rax, aMy_0; "My"
0x18007ce68  sbb     r9d, r9d
0x18007ce6b  and     r9d, 10000h
0x18007ce72  add     r9d, 18000h; dwFlags
0x18007ce79  xor     r8d, r8d; hCryptProv
0x18007ce7c  mov     [rsp+0A8h+phkResult], rax; pvPara
0x18007ce81  xor     edx, edx; dwEncodingType
0x18007ce83  call    cs:__imp_CertOpenStore
0x18007ce8a  nop     dword ptr [rax+rax+00h]
0x18007ce8f  mov     [rsp+0A8h+hCertStore], rax
0x18007ce94  mov     r15, rax
0x18007ce97  test    rax, rax
0x18007ce9a  jnz     short loc_18007CEC1
0x18007ce9c  call    cs:__imp_GetLastError
0x18007cea3  nop     dword ptr [rax+rax+00h]
0x18007cea8  mov     rdx, rbx
0x18007ceab  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x18007ceb2  mov     r8d, eax
0x18007ceb5  mov     esi, eax
0x18007ceb7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007cebc  jmp     loc_18007D06A
0x18007cec1  mov     [rsp+0A8h+pPrevCertContext], rbp; pPrevCertContext
0x18007cec6  xor     r9d, r9d; dwFindType
0x18007cec9  xor     r8d, r8d; dwFindFlags
0x18007cecc  mov     [rsp+0A8h+phkResult], rbp; pvFindPara
0x18007ced1  mov     edx, 10001h; dwCertEncodingType
0x18007ced6  mov     rcx, r15; hCertStore
0x18007ced9  call    cs:__imp_CertFindCertificateInStore
0x18007cee0  nop     dword ptr [rax+rax+00h]
0x18007cee5  mov     [rsp+0A8h+pCertContext], rax
0x18007ceea  mov     rbp, rax
0x18007ceed  test    rax, rax
0x18007cef0  jz      loc_18007D0A2
0x18007cef6  inc     [rsp+0A8h+var_70]
0x18007cefa  mov     ebp, 1
0x18007ceff  mov     [rsp+0A8h+var_74], ebp
0x18007cf03  xor     r15d, r15d
0x18007cf06  cmp     r15d, [rsp+0A8h+arg_20]
0x18007cf0e  jnb     loc_18007CFDA
0x18007cf14  mov     rax, [rsp+0A8h+arg_10]
0x18007cf1c  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x18007cf23  mov     r8, [rsp+0A8h+arg_8]
0x18007cf2b  mov     r9d, 400h
0x18007cf31  mov     rdx, rbx
0x18007cf34  mov     rax, [rax+r15*8]
0x18007cf38  mov     r8, [r8+r15*8]
0x18007cf3c  mov     [rsp+0A8h+phkResult], rax
0x18007cf41  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007cf46  mov     rax, [rsp+0A8h+arg_10]
0x18007cf4e  mov     rdx, [rax+r15*8]
0x18007cf52  mov     rax, [rsp+0A8h+arg_8]
0x18007cf5a  mov     rcx, [rax+r15*8]; char *
0x18007cf5e  test    rdx, rdx
0x18007cf61  jz      short loc_18007CF96
0x18007cf63  mov     rbp, [rsp+0A8h+pCertContext]
0x18007cf68  lea     rax, [rsp+0A8h+var_74]
0x18007cf6d  mov     [rsp+0A8h+phkResult], rax
0x18007cf72  mov     r9, rbp
0x18007cf75  mov     rax, [rsp+0A8h+arg_18]
0x18007cf7d  mov     r8d, [rax+r15*4]
0x18007cf81  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x18007cf86  mov     edi, eax
0x18007cf88  test    eax, eax
0x18007cf8a  js      loc_18007D082
0x18007cf90  mov     ebp, [rsp+0A8h+var_74]
0x18007cf94  jmp     short loc_18007CFAC
0x18007cf96  mov     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT *
0x18007cf9b  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x18007cfa0  xor     ecx, ecx
0x18007cfa2  test    rax, rax
0x18007cfa5  cmovnz  ebp, ecx
0x18007cfa8  mov     [rsp+0A8h+var_74], ebp
0x18007cfac  lea     rax, aFalse_1; "FALSE"
0x18007cfb3  test    ebp, ebp
0x18007cfb5  lea     r8, aTrue_1; "TRUE"
0x18007cfbc  mov     rdx, rbx
0x18007cfbf  cmovz   r8, rax
0x18007cfc3  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x18007cfca  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007cfcf  inc     r15d
0x18007cfd2  test    ebp, ebp
0x18007cfd4  jnz     loc_18007CF06
0x18007cfda  test    ebp, ebp
0x18007cfdc  jz      short loc_18007D011
0x18007cfde  inc     [rsp+0A8h+arg_0]
0x18007cfe5  cmp     [rsp+0A8h+var_78], r14d
0x18007cfea  jbe     short loc_18007D011
0x18007cfec  mov     r15, [rsp+0A8h+arg_28]
0x18007cff4  test    r15, r15
0x18007cff7  jz      short loc_18007D011
0x18007cff9  mov     rcx, [rsp+0A8h+pCertContext]; pCertContext
0x18007cffe  call    cs:__imp_CertDuplicateCertificateContext
0x18007d005  nop     dword ptr [rax+rax+00h]
0x18007d00a  mov     [r15+r14*8], rax
0x18007d00e  inc     r14d
0x18007d011  mov     rax, [rsp+0A8h+pCertContext]
0x18007d016  xor     r9d, r9d; dwFindType
0x18007d019  mov     r15, [rsp+0A8h+hCertStore]
0x18007d01e  xor     r8d, r8d; dwFindFlags
0x18007d021  mov     [rsp+0A8h+pPrevCertContext], rax; pPrevCertContext
0x18007d026  mov     rcx, r15; hCertStore
0x18007d029  mov     edx, 10001h; dwCertEncodingType
0x18007d02e  mov     [rsp+0A8h+phkResult], 0; pvFindPara
0x18007d037  call    cs:__imp_CertFindCertificateInStore
0x18007d03e  nop     dword ptr [rax+rax+00h]
0x18007d043  mov     [rsp+0A8h+pCertContext], rax
0x18007d048  mov     rbp, rax
0x18007d04b  test    rax, rax
0x18007d04e  jnz     loc_18007CEF6
0x18007d054  mov     eax, [rsp+0A8h+arg_0]
0x18007d05b  cmp     [rsp+0A8h+var_78], eax
0x18007d05f  jnb     short loc_18007D0A5
0x18007d061  mov     [r12], eax
0x18007d065  mov     esi, 7Ah ; 'z'
0x18007d06a  test    r13d, r13d
0x18007d06d  jz      short loc_18007D0B6
0x18007d06f  cmp     r13d, 1
0x18007d073  jz      loc_18007CDEE
0x18007d079  lea     r9, aUnknown_0; "Unknown"
0x18007d080  jmp     short loc_18007D0BD
0x18007d082  mov     r9d, eax
0x18007d085  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18007d08c  mov     rdx, rbx
0x18007d08f  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18007d096  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007d09b  mov     r15, [rsp+0A8h+hCertStore]
0x18007d0a0  jmp     short loc_18007D06A
0x18007d0a2  mov     eax, r14d
0x18007d0a5  cmp     [rsp+0A8h+arg_28], 0
0x18007d0ae  jz      short loc_18007D061
0x18007d0b0  mov     [r12], r14d
0x18007d0b4  jmp     short loc_18007D06A
0x18007d0b6  lea     r9, stru_18008DE98.hCertStore
0x18007d0bd  mov     eax, [rsp+0A8h+var_70]
0x18007d0c1  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x18007d0c8  mov     r8d, [rsp+0A8h+arg_0]
0x18007d0d0  mov     rdx, rbx
0x18007d0d3  mov     dword ptr [rsp+0A8h+phkResult], eax
0x18007d0d7  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007d0dc  mov     r12d, 80070000h
0x18007d0e2  test    esi, esi
0x18007d0e4  jz      short loc_18007D0F2
0x18007d0e6  jg      short loc_18007D0EC
0x18007d0e8  mov     edi, esi
0x18007d0ea  jmp     short loc_18007D0F2
0x18007d0ec  movzx   edi, si
0x18007d0ef  or      edi, r12d
0x18007d0f2  test    rbp, rbp
0x18007d0f5  jz      short loc_18007D106
0x18007d0f7  mov     rcx, rbp; pCertContext
0x18007d0fa  call    cs:__imp_CertFreeCertificateContext
0x18007d101  nop     dword ptr [rax+rax+00h]
0x18007d106  test    edi, edi
0x18007d108  jns     short loc_18007D125
0x18007d10a  cmp     [rsp+0A8h+var_78], r14d
0x18007d10f  mov     rcx, [rsp+0A8h+arg_28]; struct _CERT_CONTEXT **
0x18007d117  cmovb   r14d, [rsp+0A8h+var_78]
0x18007d11d  mov     edx, r14d; unsigned int
0x18007d120  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x18007d125  test    r15, r15
0x18007d128  jz      short loc_18007D167
0x18007d12a  xor     edx, edx; dwFlags
0x18007d12c  mov     rcx, r15; hCertStore
0x18007d12f  call    cs:__imp_CertCloseStore
0x18007d136  nop     dword ptr [rax+rax+00h]
0x18007d13b  test    eax, eax
0x18007d13d  jnz     short loc_18007D167
0x18007d13f  call    cs:__imp_GetLastError
0x18007d146  nop     dword ptr [rax+rax+00h]
0x18007d14b  test    eax, eax
0x18007d14d  jle     short loc_18007D155
0x18007d14f  movzx   eax, ax
0x18007d152  or      eax, r12d
  ... truncated ...
```
