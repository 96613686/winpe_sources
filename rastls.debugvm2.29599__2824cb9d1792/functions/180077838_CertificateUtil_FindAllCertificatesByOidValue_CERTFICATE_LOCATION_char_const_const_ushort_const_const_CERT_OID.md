# CertificateUtil::FindAllCertificatesByOidValue(_CERTFICATE_LOCATION,char const * * const,ushort const * * const,_CERT_OID_VALUE_TYPE * const,ulong,_CERT_CONTEXT const * * const,ulong *)

- ea: `0x180077838`
- end: `0x180077daf`
- name: `?FindAllCertificatesByOidValue@CertificateUtil@@SAJW4_CERTFICATE_LOCATION@@QEAPEBDQEAPEBGQEAW4_CERT_OID_VALUE_TYPE@@KQEAPEBU_CERT_CONTEXT@@PEAK@Z`
- size: `1399`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180078cbc`

## callees

- `0x180022fcc`
- `0x18002c90c`
- `0x18002c978`
- `0x18002cb48`
- `0x18002ce0c`
- `0x180077698`
- `0x180077838`
- `0x180077db8`
- `0x18007824c`
- `0x180078898`
- `0x1800788d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077d07`
- `CRYPT32!CertCloseStore` at `0x180077cfd`
- `CRYPT32!CertCloseStore` at `0x180077cfd`
- `CRYPT32!CertFindCertificateInStore` at `0x180077abf`
- `CRYPT32!CertFindCertificateInStore` at `0x180077c11`
- `CRYPT32!CertFindCertificateInStore` at `0x180077abf`
- `CRYPT32!CertFindCertificateInStore` at `0x180077c11`
- `CRYPT32!CertFreeCertificateContext` at `0x180077cce`
- `CRYPT32!CertFreeCertificateContext` at `0x180077cce`
- `CRYPT32!CertOpenStore` at `0x180077a75`
- `CRYPT32!CertOpenStore` at `0x180077a75`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180077bde`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180077bde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077d33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077d33`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077968`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077a1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077968`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180077a1b`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18007799f`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180077d6b`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18007799f`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180077d6b`

## string_xrefs

- `0x180077985`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x. Try loading the registry key...`
- `0x180077c59`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180077a2e`: `%s: Cannot open registry key "%s". RegOpenKeyExW error code: 0x%08x.`
- `0x180077a91`: `%s: CertOpenStore failed with error code: 0x%08x`

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
    p_hCertStore = (const wchar_t *)&stru_180087E98.hCertStore;
    goto LABEL_49;
  }
  p_hCertStore = L"CurrentUser";
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
0x180077838  mov     r11, rsp
0x18007783b  mov     [r11+20h], r9
0x18007783f  mov     [r11+18h], r8
0x180077843  mov     [r11+10h], rdx
0x180077847  push    rbx
0x180077848  push    rbp
0x180077849  push    rsi
0x18007784a  push    rdi
0x18007784b  push    r12
0x18007784d  push    r13
0x18007784f  push    r14
0x180077851  push    r15
0x180077853  sub     rsp, 68h
0x180077857  xor     esi, esi
0x180077859  lea     rbx, aCertificateuti; "CertificateUtil::FindAllCertificatesByO"...
0x180077860  xor     r15d, r15d
0x180077863  mov     [rsp+0A8h+var_6C], esi
0x180077867  xor     ebp, ebp
0x180077869  mov     [r11-60h], rsi
0x18007786d  xor     r14d, r14d
0x180077870  mov     [rsp+0A8h+var_78], esi
0x180077874  mov     [rsp+0A8h+arg_0], esi
0x18007787b  mov     rax, r8
0x18007787e  mov     [rsp+0A8h+var_70], esi
0x180077882  mov     r13d, ecx
0x180077885  test    rdx, rdx
0x180077888  jnz     short loc_1800778B9
0x18007788a  lea     r8, aPcszoids; "pcszOids"
0x180077891  mov     rdx, rbx
0x180077894  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007789b  mov     edi, 80070057h
0x1800778a0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800778a5  lea     rdx, aPcszoids; "pcszOids"
0x1800778ac  mov     rcx, rbx; unsigned __int16 *
0x1800778af  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800778b4  jmp     loc_180077C3E
0x1800778b9  test    rax, rax
0x1800778bc  jnz     short loc_1800778E2
0x1800778be  lea     r8, aPcszoidvalues; "pcszOidValues"
0x1800778c5  mov     rdx, rbx
0x1800778c8  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800778cf  mov     edi, 80070057h
0x1800778d4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800778d9  lea     rdx, aPcszoidvalues; "pcszOidValues"
0x1800778e0  jmp     short loc_1800778AC
0x1800778e2  mov     r12, [rsp+0A8h+arg_30]
0x1800778ea  test    r12, r12
0x1800778ed  jnz     short loc_180077913
0x1800778ef  lea     r8, aPdwcount; "pdwCount"
0x1800778f6  mov     rdx, rbx
0x1800778f9  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180077900  mov     edi, 80070057h
0x180077905  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007790a  lea     rdx, aPdwcount; "pdwCount"
0x180077911  jmp     short loc_1800778AC
0x180077913  mov     eax, [r12]
0x180077917  xor     edi, edi
0x180077919  mov     [rsp+0A8h+var_78], eax
0x18007791d  mov     [r12], esi
0x180077921  cmp     r13d, 1
0x180077925  jnz     loc_180077A49
0x18007792b  call    ?IsWinPEHost@@YAHXZ; IsWinPEHost(void)
0x180077930  test    eax, eax
0x180077932  jz      loc_180077A49
0x180077938  mov     rdx, rbx
0x18007793b  lea     rcx, aSSystemIsWinpe; "%s: System is WinPE."
0x180077942  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180077947  lea     rax, [rsp+0A8h+hKey]
0x18007794c  mov     r9d, 20019h; samDesired
0x180077952  xor     r8d, r8d; ulOptions
0x180077955  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18007795a  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x180077961  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180077968  call    cs:__imp_RegOpenKeyExW
0x18007796e  mov     esi, eax
0x180077970  test    eax, eax
0x180077972  jz      loc_180077A37
0x180077978  mov     r9d, eax
0x18007797b  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x180077982  mov     rdx, rbx
0x180077985  lea     rcx, aSCannotOpenReg; "%s: Cannot open registry key \"%s\". Re"...
0x18007798c  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180077991  lea     rdx, aTargetsoftware_0; "TargetSoftware"
0x180077998  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007799f  call    cs:__imp_RegUnLoadKeyW
0x1800779a5  test    eax, eax
0x1800779a7  jz      short loc_1800779C2
0x1800779a9  mov     r9d, eax
0x1800779ac  lea     r8, aHkeyLocalMachi_2; "HKEY_LOCAL_MACHINE\\TargetSoftware"
0x1800779b3  mov     rdx, rbx
0x1800779b6  lea     rcx, aSAlwaysTryUnlo; "%s: Always try unloading reg key \"%s\""...
0x1800779bd  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800779c2  call    ?RegLoadKeyWinPE@@YAJPEAUHKEY__@@PEBG11@Z; RegLoadKeyWinPE(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800779c7  mov     edi, eax
0x1800779c9  test    eax, eax
0x1800779cb  jns     short loc_1800779F2
0x1800779cd  lea     r8, aRegloadkeywinp; "RegLoadKeyWinPE"
0x1800779d4  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x1800779db  mov     rdx, rbx
0x1800779de  mov     r9d, eax
0x1800779e1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800779e6  lea     r9, stru_180087E98.hCertStore
0x1800779ed  jmp     loc_180077C91
0x1800779f2  lea     rax, [rsp+0A8h+hKey]
0x1800779f7  mov     [rsp+0A8h+var_6C], 1
0x1800779ff  mov     r9d, 20019h; samDesired
0x180077a05  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180077a0a  xor     r8d, r8d; ulOptions
0x180077a0d  lea     rdx, aTargetsoftware; "TargetSoftware\\Microsoft\\SystemCertif"...
0x180077a14  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180077a1b  call    cs:__imp_RegOpenKeyExW
0x180077a21  mov     esi, eax
0x180077a23  test    eax, eax
0x180077a25  jz      short loc_180077A37
0x180077a27  lea     r8, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE\\TargetSoftware\\Mic"...
0x180077a2e  lea     rcx, aSCannotOpenReg_0; "%s: Cannot open registry key \"%s\". Re"...
0x180077a35  jmp     short loc_1800779DB
0x180077a37  mov     rax, [rsp+0A8h+hKey]
0x180077a3c  mov     r9d, 8000h
0x180077a42  mov     ecx, 4
0x180077a47  jmp     short loc_180077A6B
0x180077a49  mov     eax, r13d
0x180077a4c  mov     ecx, 0Ah; lpszStoreProvider
0x180077a51  neg     eax
0x180077a53  lea     rax, aMy_0; "My"
0x180077a5a  sbb     r9d, r9d
0x180077a5d  and     r9d, 10000h
0x180077a64  add     r9d, 18000h; dwFlags
0x180077a6b  xor     r8d, r8d; hCryptProv
0x180077a6e  mov     [rsp+0A8h+phkResult], rax; pvPara
0x180077a73  xor     edx, edx; dwEncodingType
0x180077a75  call    cs:__imp_CertOpenStore
0x180077a7b  mov     [rsp+0A8h+hCertStore], rax
0x180077a80  mov     r15, rax
0x180077a83  test    rax, rax
0x180077a86  jnz     short loc_180077AA7
0x180077a88  call    cs:__imp_GetLastError
0x180077a8e  mov     rdx, rbx
0x180077a91  lea     rcx, aSCertopenstore; "%s: CertOpenStore failed with error cod"...
0x180077a98  mov     r8d, eax
0x180077a9b  mov     esi, eax
0x180077a9d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077aa2  jmp     loc_180077C3E
0x180077aa7  mov     [rsp+0A8h+pPrevCertContext], rbp; pPrevCertContext
0x180077aac  xor     r9d, r9d; dwFindType
0x180077aaf  xor     r8d, r8d; dwFindFlags
0x180077ab2  mov     [rsp+0A8h+phkResult], rbp; pvFindPara
0x180077ab7  mov     edx, 10001h; dwCertEncodingType
0x180077abc  mov     rcx, r15; hCertStore
0x180077abf  call    cs:__imp_CertFindCertificateInStore
0x180077ac5  mov     [rsp+0A8h+pCertContext], rax
0x180077aca  mov     rbp, rax
0x180077acd  test    rax, rax
0x180077ad0  jz      loc_180077C76
0x180077ad6  inc     [rsp+0A8h+var_70]
0x180077ada  mov     ebp, 1
0x180077adf  mov     [rsp+0A8h+var_74], ebp
0x180077ae3  xor     r15d, r15d
0x180077ae6  cmp     r15d, [rsp+0A8h+arg_20]
0x180077aee  jnb     loc_180077BBA
0x180077af4  mov     rax, [rsp+0A8h+arg_10]
0x180077afc  lea     rcx, aSWillTryToFind; "%s: Will try to find the OID: '%hs' and"...
0x180077b03  mov     r8, [rsp+0A8h+arg_8]
0x180077b0b  mov     r9d, 400h
0x180077b11  mov     rdx, rbx
0x180077b14  mov     rax, [rax+r15*8]
0x180077b18  mov     r8, [r8+r15*8]
0x180077b1c  mov     [rsp+0A8h+phkResult], rax
0x180077b21  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180077b26  mov     rax, [rsp+0A8h+arg_10]
0x180077b2e  mov     rdx, [rax+r15*8]
0x180077b32  mov     rax, [rsp+0A8h+arg_8]
0x180077b3a  mov     rcx, [rax+r15*8]; char *
0x180077b3e  test    rdx, rdx
0x180077b41  jz      short loc_180077B76
0x180077b43  mov     rbp, [rsp+0A8h+pCertContext]
0x180077b48  lea     rax, [rsp+0A8h+var_74]
0x180077b4d  mov     [rsp+0A8h+phkResult], rax
0x180077b52  mov     r9, rbp
0x180077b55  mov     rax, [rsp+0A8h+arg_18]
0x180077b5d  mov     r8d, [rax+r15*4]
0x180077b61  call    ?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z; CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)
0x180077b66  mov     edi, eax
0x180077b68  test    eax, eax
0x180077b6a  js      loc_180077C56
0x180077b70  mov     ebp, [rsp+0A8h+var_74]
0x180077b74  jmp     short loc_180077B8C
0x180077b76  mov     rdx, [rsp+0A8h+pCertContext]; struct _CERT_CONTEXT *
0x180077b7b  call    ?FindExtensionByOid@CertificateUtil@@SAPEAU_CERT_EXTENSION@@PEBDPEBU_CERT_CONTEXT@@@Z; CertificateUtil::FindExtensionByOid(char const *,_CERT_CONTEXT const *)
0x180077b80  xor     ecx, ecx
0x180077b82  test    rax, rax
0x180077b85  cmovnz  ebp, ecx
0x180077b88  mov     [rsp+0A8h+var_74], ebp
0x180077b8c  lea     rax, aFalse_1; "FALSE"
0x180077b93  test    ebp, ebp
0x180077b95  lea     r8, aTrue_1; "TRUE"
0x180077b9c  mov     rdx, rbx
0x180077b9f  cmovz   r8, rax
0x180077ba3  lea     rcx, aSCertMatchingS; "%s: Cert matching: %s"
0x180077baa  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180077baf  inc     r15d
0x180077bb2  test    ebp, ebp
0x180077bb4  jnz     loc_180077AE6
0x180077bba  test    ebp, ebp
0x180077bbc  jz      short loc_180077BEB
0x180077bbe  inc     [rsp+0A8h+arg_0]
0x180077bc5  cmp     [rsp+0A8h+var_78], r14d
0x180077bca  jbe     short loc_180077BEB
0x180077bcc  mov     r15, [rsp+0A8h+arg_28]
0x180077bd4  test    r15, r15
0x180077bd7  jz      short loc_180077BEB
0x180077bd9  mov     rcx, [rsp+0A8h+pCertContext]; pCertContext
0x180077bde  call    cs:__imp_CertDuplicateCertificateContext
0x180077be4  mov     [r15+r14*8], rax
0x180077be8  inc     r14d
0x180077beb  mov     rax, [rsp+0A8h+pCertContext]
0x180077bf0  xor     r9d, r9d; dwFindType
0x180077bf3  mov     r15, [rsp+0A8h+hCertStore]
0x180077bf8  xor     r8d, r8d; dwFindFlags
0x180077bfb  mov     [rsp+0A8h+pPrevCertContext], rax; pPrevCertContext
0x180077c00  mov     rcx, r15; hCertStore
0x180077c03  mov     edx, 10001h; dwCertEncodingType
0x180077c08  mov     [rsp+0A8h+phkResult], 0; pvFindPara
0x180077c11  call    cs:__imp_CertFindCertificateInStore
0x180077c17  mov     [rsp+0A8h+pCertContext], rax
0x180077c1c  mov     rbp, rax
0x180077c1f  test    rax, rax
0x180077c22  jnz     loc_180077AD6
0x180077c28  mov     eax, [rsp+0A8h+arg_0]
0x180077c2f  cmp     [rsp+0A8h+var_78], eax
0x180077c33  jnb     short loc_180077C79
0x180077c35  mov     [r12], eax
0x180077c39  mov     esi, 7Ah ; 'z'
0x180077c3e  test    r13d, r13d
0x180077c41  jz      short loc_180077C8A
0x180077c43  cmp     r13d, 1
0x180077c47  jz      loc_1800779E6
0x180077c4d  lea     r9, aUnknown_0; "Unknown"
0x180077c54  jmp     short loc_180077C91
0x180077c56  mov     r9d, eax
0x180077c59  lea     r8, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180077c60  mov     rdx, rbx
0x180077c63  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x180077c6a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077c6f  mov     r15, [rsp+0A8h+hCertStore]
0x180077c74  jmp     short loc_180077C3E
0x180077c76  mov     eax, r14d
0x180077c79  cmp     [rsp+0A8h+arg_28], 0
0x180077c82  jz      short loc_180077C35
0x180077c84  mov     [r12], r14d
0x180077c88  jmp     short loc_180077C3E
0x180077c8a  lea     r9, aCurrentuser; "CurrentUser"
0x180077c91  mov     eax, [rsp+0A8h+var_70]
0x180077c95  lea     rcx, aSUTotalSCertif; "%s: %u total %s certificate(s) found. %"...
0x180077c9c  mov     r8d, [rsp+0A8h+arg_0]
0x180077ca4  mov     rdx, rbx
0x180077ca7  mov     dword ptr [rsp+0A8h+phkResult], eax
0x180077cab  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180077cb0  mov     r12d, 80070000h
0x180077cb6  test    esi, esi
0x180077cb8  jz      short loc_180077CC6
0x180077cba  jg      short loc_180077CC0
0x180077cbc  mov     edi, esi
0x180077cbe  jmp     short loc_180077CC6
0x180077cc0  movzx   edi, si
0x180077cc3  or      edi, r12d
0x180077cc6  test    rbp, rbp
0x180077cc9  jz      short loc_180077CD4
0x180077ccb  mov     rcx, rbp; pCertContext
0x180077cce  call    cs:__imp_CertFreeCertificateContext
0x180077cd4  test    edi, edi
0x180077cd6  jns     short loc_180077CF3
0x180077cd8  cmp     [rsp+0A8h+var_78], r14d
0x180077cdd  mov     rcx, [rsp+0A8h+arg_28]; struct _CERT_CONTEXT **
0x180077ce5  cmovb   r14d, [rsp+0A8h+var_78]
0x180077ceb  mov     edx, r14d; unsigned int
0x180077cee  call    ?FreeCertificates@CertificateUtil@@SAXQEAPEBU_CERT_CONTEXT@@K@Z; CertificateUtil::FreeCertificates(_CERT_CONTEXT const * * const,ulong)
0x180077cf3  test    r15, r15
0x180077cf6  jz      short loc_180077D29
0x180077cf8  xor     edx, edx; dwFlags
0x180077cfa  mov     rcx, r15; hCertStore
0x180077cfd  call    cs:__imp_CertCloseStore
0x180077d03  test    eax, eax
0x180077d05  jnz     short loc_180077D29
0x180077d07  call    cs:__imp_GetLastError
0x180077d0d  test    eax, eax
0x180077d0f  jle     short loc_180077D17
0x180077d11  movzx   eax, ax
0x180077d14  or      eax, r12d
0x180077d17  mov     r8d, eax
0x180077d1a  lea     rcx, aSCertclosestor; "%s: CertCloseStore failed with error co"...
0x180077d21  mov     rdx, rbx
0x180077d24  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180077d29  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180077d2e  test    rcx, rcx
0x180077d31  jz      short loc_180077D56
0x180077d33  call    cs:__imp_RegCloseKey
0x180077d39  test    eax, eax
0x180077d3b  jz      short loc_180077D56
0x180077d3d  mov     r9d, eax
  ... truncated ...
```
