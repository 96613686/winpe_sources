# IsProtectedCertificate

- ea: `0x180099438`
- end: `0x1800998dc`
- name: `IsProtectedCertificate`
- size: `1188`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180082fa0`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x180099438`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009969d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009969d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099808`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099808`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800994f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800995df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009965d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800996ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800994f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099576`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800995df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009965d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800996ab`
- `CRYPT32!CertCloseStore` at `0x180099895`
- `CRYPT32!CertCloseStore` at `0x180099895`
- `CRYPT32!CertOpenStore` at `0x1800994e6`
- `CRYPT32!CertOpenStore` at `0x1800994e6`
- `CRYPT32!CertFreeCertificateContext` at `0x180099818`
- `CRYPT32!CertFreeCertificateContext` at `0x180099818`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800995d5`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800995d5`
- `CRYPT32!CertFindCertificateInStore` at `0x180099568`
- `CRYPT32!CertFindCertificateInStore` at `0x180099568`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18009987e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18009987e`
- `ncrypt!NCryptGetProperty` at `0x180099653`
- `ncrypt!NCryptGetProperty` at `0x18009970f`
- `ncrypt!NCryptGetProperty` at `0x180099653`
- `ncrypt!NCryptGetProperty` at `0x18009970f`
- `ncrypt!NCryptFreeObject` at `0x180099874`
- `ncrypt!NCryptFreeObject` at `0x180099874`

## pseudocode

```c
__int64 __fastcall IsProtectedCertificate(__int64 a1, _DWORD *a2)
{
  _QWORD *v4; // rcx
  HCERTSTORE v5; // rax
  void *v6; // r14
  DWORD LastError; // eax
  unsigned int Property; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rcx
  const CERT_CONTEXT *CertificateInStore; // r15
  DWORD v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  BYTE *v16; // rsi
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+30h] [rbp-20h] BYREF
  __int64 pvFindPara; // [rsp+38h] [rbp-18h] BYREF
  __int64 v22; // [rsp+40h] [rbp-10h]
  DWORD pcbResult; // [rsp+90h] [rbp+40h] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+A0h] [rbp+50h] BYREF
  DWORD pdwKeySpec; // [rsp+A8h] [rbp+58h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 1408, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  LODWORD(v22) = 0;
  pvFindPara = 0;
  phCryptProvOrNCryptKey = 0;
  pdwKeySpec = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  pcbResult = 0;
  if ( a1 && a2 && *(_QWORD *)(a1 + 4) )
  {
    *a2 = 0;
    v5 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x18000u, L"My");
    v6 = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      Property = LastError;
      if ( LastError )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_69;
        }
        v9 = 1410;
        goto LABEL_14;
      }
      goto LABEL_68;
    }
    v11 = *(_QWORD *)(a1 + 4);
    LODWORD(pvFindPara) = *(_DWORD *)(v11 + 16);
    v22 = v11 + 20;
    CertificateInStore = CertFindCertificateInStore(v5, 1u, 0, 0x10000u, &pvFindPara, 0);
    if ( !CertificateInStore )
    {
      LastError = GetLastError();
      Property = LastError;
      if ( LastError )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_69;
        }
        v9 = 1411;
LABEL_14:
        v10 = LastError;
LABEL_67:
        WPP_SF_d(v4[2], v9, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v10);
      }
LABEL_68:
      v4 = WPP_GLOBAL_Control;
LABEL_69:
      if ( phCryptProvOrNCryptKey && pfCallerFreeProvOrNCryptKey )
      {
        if ( pdwKeySpec == -1 )
          NCryptFreeObject(phCryptProvOrNCryptKey);
        else
          CryptReleaseContext(phCryptProvOrNCryptKey, 0);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v6 )
      {
        CertCloseStore(v6, 0);
        v4 = WPP_GLOBAL_Control;
      }
      goto LABEL_77;
    }
    if ( !CryptAcquireCertificatePrivateKey(
            CertificateInStore,
            0x40008u,
            0,
            &phCryptProvOrNCryptKey,
            &pdwKeySpec,
            &pfCallerFreeProvOrNCryptKey) )
    {
      v13 = GetLastError();
      Property = v13;
      if ( !v13 )
        goto LABEL_62;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v15 = 1412;
      goto LABEL_27;
    }
    if ( NCryptGetProperty(phCryptProvOrNCryptKey, L"UI Policy", 0, 0, &pcbResult, 0x40u) )
    {
      v13 = GetLastError();
      Property = v13;
      if ( !v13 )
        goto LABEL_62;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v15 = 1413;
      goto LABEL_27;
    }
    v16 = (BYTE *)LocalAlloc(0x40u, pcbResult);
    if ( !v16 )
    {
      v13 = GetLastError();
      Property = v13;
      if ( !v13 )
        goto LABEL_62;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v15 = 1414;
LABEL_27:
      WPP_SF_d(v14[2], v15, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v13);
LABEL_62:
      CertFreeCertificateContext(CertificateInStore);
      goto LABEL_68;
    }
    Property = NCryptGetProperty(phCryptProvOrNCryptKey, L"UI Policy", v16, pcbResult, &pcbResult, 0x40u);
    if ( Property )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1415, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, Property);
      }
      goto LABEL_61;
    }
    if ( (v16[4] & 2) != 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_56;
      }
      v18 = 1416;
    }
    else
    {
      if ( (v16[4] & 1) == 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 1418, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
        }
        goto LABEL_61;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
        goto LABEL_56;
      }
      v18 = 1417;
    }
    WPP_SF_(v17[2], v18, WPP_425b3625ab793a6219f8039beff53b24_Traceguids);
LABEL_56:
    *a2 = 1;
LABEL_61:
    LocalFree(v16);
    goto LABEL_62;
  }
  Property = 87;
  if ( v4 == &WPP_GLOBAL_Control )
    return Property;
  if ( (*((_DWORD *)v4 + 7) & 0x800) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    v6 = 0;
    v9 = 1409;
    v10 = 87;
    goto LABEL_67;
  }
LABEL_77:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x800) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 1419, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, Property);
  return Property;
}

```

## disassembly

```asm
0x180099438  push    rbp
0x18009943a  push    rbx
0x18009943b  push    rsi
0x18009943c  push    rdi
0x18009943d  push    r13
0x18009943f  push    r14
0x180099441  push    r15
0x180099443  mov     rbp, rsp
0x180099446  sub     rsp, 50h
0x18009944a  mov     rdi, rdx
0x18009944d  mov     rbx, rcx
0x180099450  mov     rcx, cs:WPP_GLOBAL_Control
0x180099457  lea     rsi, WPP_GLOBAL_Control
0x18009945e  mov     r13d, 800h
0x180099464  cmp     rcx, rsi
0x180099467  jz      short loc_180099491
0x180099469  test    [rcx+1Ch], r13d
0x18009946d  jz      short loc_180099491
0x18009946f  cmp     byte ptr [rcx+19h], 6
0x180099473  jb      short loc_180099491
0x180099475  mov     rcx, [rcx+10h]
0x180099479  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180099480  mov     edx, 580h
0x180099485  call    WPP_SF_
0x18009948a  mov     rcx, cs:WPP_GLOBAL_Control
0x180099491  xor     eax, eax
0x180099493  mov     qword ptr [rbp+var_14], rax
0x180099497  mov     [rbp-18h], rax
0x18009949b  mov     [rbp+phCryptProvOrNCryptKey], rax
0x18009949f  mov     [rbp+pdwKeySpec], eax
0x1800994a2  mov     [rbp+pfCallerFreeProvOrNCryptKey], eax
0x1800994a5  mov     [rbp+pcbResult], eax
0x1800994a8  test    rbx, rbx
0x1800994ab  jz      loc_180099820
0x1800994b1  test    rdi, rdi
0x1800994b4  jz      loc_180099820
0x1800994ba  cmp     [rbx+4], rax
0x1800994be  jz      loc_180099820
0x1800994c4  xor     r8d, r8d; hCryptProv
0x1800994c7  mov     [rdi], eax
0x1800994c9  lea     rax, aMy; "My"
0x1800994d0  mov     r9d, 18000h; dwFlags
0x1800994d6  mov     [rsp+50h+pvPara], rax; pvPara
0x1800994db  lea     r15d, [r8+1]
0x1800994df  mov     edx, r15d; dwEncodingType
0x1800994e2  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x1800994e6  call    cs:__imp_CertOpenStore
0x1800994ec  mov     r14, rax
0x1800994ef  test    rax, rax
0x1800994f2  jnz     short loc_180099535
0x1800994f4  call    cs:__imp_GetLastError
0x1800994fa  mov     ebx, eax
0x1800994fc  test    eax, eax
0x1800994fe  jz      loc_180099855
0x180099504  mov     rcx, cs:WPP_GLOBAL_Control
0x18009950b  cmp     rcx, rsi
0x18009950e  jz      loc_18009985C
0x180099514  test    [rcx+1Ch], r13d
0x180099518  jz      loc_18009985C
0x18009951e  cmp     byte ptr [rcx+19h], 2
0x180099522  jb      loc_18009985C
0x180099528  mov     edx, 582h
0x18009952d  mov     r9d, eax
0x180099530  jmp     loc_180099845
0x180099535  mov     rcx, [rbx+4]
0x180099539  mov     r9d, 10000h; dwFindType
0x18009953f  mov     [rsp+50h+pPrevCertContext], 0; pPrevCertContext
0x180099548  xor     r8d, r8d; dwFindFlags
0x18009954b  mov     edx, r15d; dwCertEncodingType
0x18009954e  mov     eax, [rcx+10h]
0x180099551  mov     [rbp+pvFindPara], eax
0x180099554  lea     rax, [rcx+14h]
0x180099558  mov     qword ptr [rbp+var_14+4], rax
0x18009955c  mov     rcx, r14; hCertStore
0x18009955f  lea     rax, [rbp+pvFindPara]
0x180099563  mov     [rsp+50h+pvPara], rax; pvFindPara
0x180099568  call    cs:__imp_CertFindCertificateInStore
0x18009956e  mov     r15, rax
0x180099571  test    rax, rax
0x180099574  jnz     short loc_1800995B4
0x180099576  call    cs:__imp_GetLastError
0x18009957c  mov     ebx, eax
0x18009957e  test    eax, eax
0x180099580  jz      loc_180099855
0x180099586  mov     rcx, cs:WPP_GLOBAL_Control
0x18009958d  cmp     rcx, rsi
0x180099590  jz      loc_18009985C
0x180099596  test    [rcx+1Ch], r13d
0x18009959a  jz      loc_18009985C
0x1800995a0  cmp     byte ptr [rcx+19h], 2
0x1800995a4  jb      loc_18009985C
0x1800995aa  mov     edx, 583h
0x1800995af  jmp     loc_18009952D
0x1800995b4  lea     rax, [rbp+pfCallerFreeProvOrNCryptKey]
0x1800995b8  xor     r8d, r8d; pvParameters
0x1800995bb  mov     [rsp+50h+pPrevCertContext], rax; pfCallerFreeProvOrNCryptKey
0x1800995c0  lea     r9, [rbp+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x1800995c4  lea     rax, [rbp+pdwKeySpec]
0x1800995c8  mov     edx, 40008h; dwFlags
0x1800995cd  mov     rcx, r15; pCert
0x1800995d0  mov     [rsp+50h+pvPara], rax; pdwKeySpec
0x1800995d5  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x1800995db  test    eax, eax
0x1800995dd  jnz     short loc_180099630
0x1800995df  call    cs:__imp_GetLastError
0x1800995e5  mov     ebx, eax
0x1800995e7  test    eax, eax
0x1800995e9  jz      loc_180099815
0x1800995ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800995f6  cmp     rcx, rsi
0x1800995f9  jz      loc_180099815
0x1800995ff  test    [rcx+1Ch], r13d
0x180099603  jz      loc_180099815
0x180099609  cmp     byte ptr [rcx+19h], 2
0x18009960d  jb      loc_180099815
0x180099613  mov     edx, 584h
0x180099618  mov     rcx, [rcx+10h]
0x18009961c  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180099623  mov     r9d, eax
0x180099626  call    WPP_SF_d
0x18009962b  jmp     loc_180099815
0x180099630  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hObject
0x180099634  lea     rax, [rbp+pcbResult]
0x180099638  mov     ebx, 40h ; '@'
0x18009963d  lea     rdx, pszProperty; "UI Policy"
0x180099644  mov     dword ptr [rsp+50h+pPrevCertContext], ebx; dwFlags
0x180099648  xor     r9d, r9d; cbOutput
0x18009964b  xor     r8d, r8d; pbOutput
0x18009964e  mov     [rsp+50h+pvPara], rax; pcbResult
0x180099653  call    cs:__imp_NCryptGetProperty
0x180099659  test    eax, eax
0x18009965b  jz      short loc_180099698
0x18009965d  call    cs:__imp_GetLastError
0x180099663  mov     ebx, eax
0x180099665  test    eax, eax
0x180099667  jz      loc_180099815
0x18009966d  mov     rcx, cs:WPP_GLOBAL_Control
0x180099674  cmp     rcx, rsi
0x180099677  jz      loc_180099815
0x18009967d  test    [rcx+1Ch], r13d
0x180099681  jz      loc_180099815
0x180099687  cmp     byte ptr [rcx+19h], 2
0x18009968b  jb      loc_180099815
0x180099691  mov     edx, 585h
0x180099696  jmp     short loc_180099618
0x180099698  mov     edx, [rbp+pcbResult]; uBytes
0x18009969b  mov     ecx, ebx; uFlags
0x18009969d  call    cs:__imp_LocalAlloc
0x1800996a3  mov     rsi, rax
0x1800996a6  test    rax, rax
0x1800996a9  jnz     short loc_1800996F0
0x1800996ab  call    cs:__imp_GetLastError
0x1800996b1  mov     ebx, eax
0x1800996b3  test    eax, eax
0x1800996b5  jz      loc_18009980E
0x1800996bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800996c2  lea     rsi, WPP_GLOBAL_Control
0x1800996c9  cmp     rcx, rsi
0x1800996cc  jz      loc_180099815
0x1800996d2  test    [rcx+1Ch], r13d
0x1800996d6  jz      loc_180099815
0x1800996dc  cmp     byte ptr [rcx+19h], 2
0x1800996e0  jb      loc_180099815
0x1800996e6  mov     edx, 586h
0x1800996eb  jmp     loc_180099618
0x1800996f0  mov     r9d, [rbp+pcbResult]; cbOutput
0x1800996f4  lea     rax, [rbp+pcbResult]
0x1800996f8  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hObject
0x1800996fc  lea     rdx, pszProperty; "UI Policy"
0x180099703  mov     dword ptr [rsp+50h+pPrevCertContext], ebx; dwFlags
0x180099707  mov     r8, rsi; pbOutput
0x18009970a  mov     [rsp+50h+pvPara], rax; pcbResult
0x18009970f  call    cs:__imp_NCryptGetProperty
0x180099715  mov     ebx, eax
0x180099717  test    eax, eax
0x180099719  jz      short loc_180099763
0x18009971b  mov     rcx, cs:WPP_GLOBAL_Control
0x180099722  lea     rax, WPP_GLOBAL_Control
0x180099729  cmp     rcx, rax
0x18009972c  jz      loc_180099805
0x180099732  test    [rcx+1Ch], r13d
0x180099736  jz      loc_180099805
0x18009973c  cmp     byte ptr [rcx+19h], 2
0x180099740  jb      loc_180099805
0x180099746  mov     rcx, [rcx+10h]
0x18009974a  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180099751  mov     edx, 587h
0x180099756  mov     r9d, ebx
0x180099759  call    WPP_SF_d
0x18009975e  jmp     loc_180099805
0x180099763  test    byte ptr [rsi+4], 2
0x180099767  jz      short loc_18009978F
0x180099769  mov     rcx, cs:WPP_GLOBAL_Control
0x180099770  lea     rax, WPP_GLOBAL_Control
0x180099777  cmp     rcx, rax
0x18009977a  jz      short loc_1800997C9
0x18009977c  test    [rcx+1Ch], r13d
0x180099780  jz      short loc_1800997C9
0x180099782  cmp     byte ptr [rcx+19h], 5
0x180099786  jb      short loc_1800997C9
0x180099788  mov     edx, 588h
0x18009978d  jmp     short loc_1800997B9
0x18009978f  test    byte ptr [rsi+4], 1
0x180099793  jz      short loc_1800997D1
0x180099795  mov     rcx, cs:WPP_GLOBAL_Control
0x18009979c  lea     rax, WPP_GLOBAL_Control
0x1800997a3  cmp     rcx, rax
0x1800997a6  jz      short loc_1800997C9
0x1800997a8  test    [rcx+1Ch], r13d
0x1800997ac  jz      short loc_1800997C9
0x1800997ae  cmp     byte ptr [rcx+19h], 5
0x1800997b2  jb      short loc_1800997C9
0x1800997b4  mov     edx, 589h
0x1800997b9  mov     rcx, [rcx+10h]
0x1800997bd  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800997c4  call    WPP_SF_
0x1800997c9  mov     dword ptr [rdi], 1
0x1800997cf  jmp     short loc_180099805
0x1800997d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800997d8  lea     rax, WPP_GLOBAL_Control
0x1800997df  cmp     rcx, rax
0x1800997e2  jz      short loc_180099805
0x1800997e4  test    [rcx+1Ch], r13d
0x1800997e8  jz      short loc_180099805
0x1800997ea  cmp     byte ptr [rcx+19h], 5
0x1800997ee  jb      short loc_180099805
0x1800997f0  mov     rcx, [rcx+10h]
0x1800997f4  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800997fb  mov     edx, 58Ah
0x180099800  call    WPP_SF_
0x180099805  mov     rcx, rsi; hMem
0x180099808  call    cs:__imp_LocalFree
0x18009980e  lea     rsi, WPP_GLOBAL_Control
0x180099815  mov     rcx, r15; pCertContext
0x180099818  call    cs:__imp_CertFreeCertificateContext
0x18009981e  jmp     short loc_180099855
0x180099820  mov     ebx, 57h ; 'W'
0x180099825  cmp     rcx, rsi
0x180099828  jz      loc_1800998CB
0x18009982e  test    [rcx+1Ch], r13d
0x180099832  jz      short loc_1800998A2
0x180099834  cmp     byte ptr [rcx+19h], 2
0x180099838  jb      short loc_1800998A2
0x18009983a  xor     r14d, r14d
0x18009983d  mov     edx, 581h
0x180099842  mov     r9d, ebx
0x180099845  mov     rcx, [rcx+10h]
0x180099849  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180099850  call    WPP_SF_d
0x180099855  mov     rcx, cs:WPP_GLOBAL_Control
0x18009985c  mov     rax, [rbp+phCryptProvOrNCryptKey]
0x180099860  test    rax, rax
0x180099863  jz      short loc_18009988B
0x180099865  cmp     [rbp+pfCallerFreeProvOrNCryptKey], 0
0x180099869  jz      short loc_18009988B
0x18009986b  cmp     [rbp+pdwKeySpec], 0FFFFFFFFh
0x18009986f  mov     rcx, rax; hProv
0x180099872  jnz     short loc_18009987C
0x180099874  call    cs:__imp_NCryptFreeObject
0x18009987a  jmp     short loc_180099884
0x18009987c  xor     edx, edx; dwFlags
0x18009987e  call    cs:__imp_CryptReleaseContext
0x180099884  mov     rcx, cs:WPP_GLOBAL_Control
0x18009988b  test    r14, r14
0x18009988e  jz      short loc_1800998A2
0x180099890  xor     edx, edx; dwFlags
0x180099892  mov     rcx, r14; hCertStore
0x180099895  call    cs:__imp_CertCloseStore
0x18009989b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800998a2  cmp     rcx, rsi
0x1800998a5  jz      short loc_1800998CB
0x1800998a7  test    [rcx+1Ch], r13d
0x1800998ab  jz      short loc_1800998CB
0x1800998ad  cmp     byte ptr [rcx+19h], 6
0x1800998b1  jb      short loc_1800998CB
0x1800998b3  mov     rcx, [rcx+10h]
0x1800998b7  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800998be  mov     edx, 58Bh
0x1800998c3  mov     r9d, ebx
0x1800998c6  call    WPP_SF_d
0x1800998cb  mov     eax, ebx
0x1800998cd  add     rsp, 50h
0x1800998d1  pop     r15
0x1800998d3  pop     r14
0x1800998d5  pop     r13
0x1800998d7  pop     rdi
0x1800998d8  pop     rsi
0x1800998d9  pop     rbx
0x1800998da  pop     rbp
0x1800998db  retn
```
