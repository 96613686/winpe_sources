# PerformNonNgcSign

- ea: `0x18005ac44`
- end: `0x18005b065`
- name: `PerformNonNgcSign`
- size: `1057`
- prototype: `__int64 __usercall@<rax>(HANDLE hToken@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005b06c`

## callees

- `0x180005bfc`
- `0x18000c37c`
- `0x180033d48`
- `0x1800590e8`
- `0x18005ac44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005acf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ad76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ade5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ae59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005afd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005acf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ad76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ade5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ae59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005afd8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005ace2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18005ace2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005afc4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005afc4`
- `ncrypt!NCryptFreeObject` at `0x18005af65`
- `ncrypt!NCryptFreeObject` at `0x18005af65`
- `CRYPT32!CertFindCertificateInStore` at `0x18005add1`
- `CRYPT32!CertFindCertificateInStore` at `0x18005add1`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18005ae49`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x18005ae49`
- `CRYPT32!CertFreeCertificateContext` at `0x18005af90`
- `CRYPT32!CertFreeCertificateContext` at `0x18005af90`
- `CRYPT32!CertCloseStore` at `0x18005afad`
- `CRYPT32!CertCloseStore` at `0x18005afad`
- `CRYPT32!CertOpenStore` at `0x18005ad62`
- `CRYPT32!CertOpenStore` at `0x18005ad62`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18005af75`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18005af75`

## pseudocode

```c
__int64 __fastcall PerformNonNgcSign(HANDLE hToken, int a2, __int64 a3, __int64 a4, _DWORD *a5, _DWORD *a6, _QWORD *a7)
{
  const CERT_CONTEXT *CertificateInStore; // r14
  HCERTSTORE v11; // rdi
  int v12; // esi
  DWORD LastError; // eax
  unsigned int v14; // ebx
  struct _LIST_ENTRY *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // r9
  DWORD v19; // eax
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+30h] [rbp-20h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+38h] [rbp-18h] BYREF
  _DWORD pvFindPara[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v24; // [rsp+48h] [rbp-8h]
  DWORD pdwKeySpec; // [rsp+A0h] [rbp+50h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_qdq(WPP_GLOBAL_Control[1].Flink, 119, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, hToken, a2, a4);
  }
  CertificateInStore = 0;
  phCryptProvOrNCryptKey = 0;
  pdwKeySpec = 0;
  *a5 = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  pvFindPara[1] = 0;
  pvFindPara[0] = a2;
  *a6 = 0;
  v24 = a3;
  *a7 = 0;
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    v11 = 0;
    v12 = 0;
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v16 = 120;
LABEL_11:
        v17 = LastError;
LABEL_43:
        WPP_SF_d(v15[1].Flink, v16, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v17);
        goto LABEL_44;
      }
      goto LABEL_45;
    }
LABEL_44:
    v15 = WPP_GLOBAL_Control;
    goto LABEL_45;
  }
  v12 = 1;
  v11 = CertOpenStore((LPCSTR)0xA, 0x10001u, 0, 0x18000u, L"MY");
  if ( v11 )
  {
    CertificateInStore = CertFindCertificateInStore(v11, 0x10001u, 0, 0x10000u, pvFindPara, 0);
    if ( CertificateInStore )
    {
      if ( CryptAcquireCertificatePrivateKey(
             CertificateInStore,
             0x20000u,
             0,
             &phCryptProvOrNCryptKey,
             &pdwKeySpec,
             &pfCallerFreeProvOrNCryptKey) )
      {
        LastError = DoDummySign(pdwKeySpec, phCryptProvOrNCryptKey);
        v14 = LastError;
        if ( LastError )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v16 = 124;
            goto LABEL_11;
          }
        }
        else
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
          {
            LOBYTE(v18) = 0;
            WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 125, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v18);
            v15 = WPP_GLOBAL_Control;
          }
          v14 = 87;
          if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v15[1].Blink) & 0x2000) != 0
            && BYTE1(v15[1].Blink) >= 2u )
          {
            v16 = 126;
            v17 = 87;
            goto LABEL_43;
          }
        }
        goto LABEL_45;
      }
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v16 = 123;
          goto LABEL_11;
        }
        goto LABEL_45;
      }
    }
    else
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( LastError )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v16 = 122;
          goto LABEL_11;
        }
        goto LABEL_45;
      }
    }
    goto LABEL_44;
  }
  LastError = GetLastError();
  v14 = LastError;
  if ( !LastError )
    goto LABEL_44;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v16 = 121;
    goto LABEL_11;
  }
LABEL_45:
  if ( pfCallerFreeProvOrNCryptKey )
  {
    if ( pdwKeySpec == -1 )
      NCryptFreeObject(phCryptProvOrNCryptKey);
    else
      CryptReleaseContext(phCryptProvOrNCryptKey, 0);
    v15 = WPP_GLOBAL_Control;
  }
  if ( CertificateInStore )
  {
    CertFreeCertificateContext(CertificateInStore);
    v15 = WPP_GLOBAL_Control;
  }
  if ( v11 )
  {
    CertCloseStore(v11, 0);
    v15 = WPP_GLOBAL_Control;
  }
  if ( !v12 )
    goto LABEL_63;
  if ( RevertToSelf() )
    goto LABEL_62;
  if ( v14 )
    goto LABEL_62;
  v19 = GetLastError();
  v14 = v19;
  if ( !v19 )
    goto LABEL_62;
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v14;
  if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 127, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v19);
LABEL_62:
    v15 = WPP_GLOBAL_Control;
  }
LABEL_63:
  if ( v15 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v15[1].Blink) & 0x2000) != 0
    && BYTE1(v15[1].Blink) >= 6u )
  {
    WPP_SF_d(v15[1].Flink, 128, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x18005ac44  mov     [rsp-38h+arg_0], rbx
0x18005ac49  push    rbp
0x18005ac4a  push    rsi
0x18005ac4b  push    rdi
0x18005ac4c  push    r12
0x18005ac4e  push    r13
0x18005ac50  push    r14
0x18005ac52  push    r15
0x18005ac54  mov     rbp, rsp
0x18005ac57  sub     rsp, 50h
0x18005ac5b  mov     rsi, r8
0x18005ac5e  mov     ebx, edx
0x18005ac60  mov     rdi, rcx
0x18005ac63  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ac6a  lea     r13, WPP_GLOBAL_Control
0x18005ac71  mov     r12d, 2000h
0x18005ac77  cmp     rcx, r13
0x18005ac7a  jz      short loc_18005ACA9
0x18005ac7c  test    [rcx+1Ch], r12d
0x18005ac80  jz      short loc_18005ACA9
0x18005ac82  cmp     byte ptr [rcx+19h], 6
0x18005ac86  jb      short loc_18005ACA9
0x18005ac88  mov     rcx, [rcx+10h]
0x18005ac8c  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x18005ac93  mov     [rsp+50h+pPrevCertContext], r9
0x18005ac98  mov     edx, 77h ; 'w'
0x18005ac9d  mov     r9, rdi
0x18005aca0  mov     dword ptr [rsp+50h+pvPara], ebx
0x18005aca4  call    WPP_SF_qdq
0x18005aca9  mov     rax, [rbp+arg_20]
0x18005acad  xor     r15d, r15d
0x18005acb0  mov     rcx, rdi; hToken
0x18005acb3  mov     [rbp+arg_8], r15d
0x18005acb7  mov     r14d, r15d
0x18005acba  mov     [rbp+phCryptProvOrNCryptKey], r15
0x18005acbe  mov     [rbp+pdwKeySpec], r15d
0x18005acc2  mov     [rax], r15d
0x18005acc5  mov     rax, [rbp+arg_28]
0x18005acc9  mov     [rbp+pfCallerFreeProvOrNCryptKey], r15d
0x18005accd  mov     [rbp+var_C], r15d
0x18005acd1  mov     [rbp+pvFindPara], ebx
0x18005acd4  mov     [rax], r15d
0x18005acd7  mov     rax, [rbp+arg_30]
0x18005acdb  mov     [rbp+var_8], rsi
0x18005acdf  mov     [rax], r15
0x18005ace2  call    cs:__imp_ImpersonateLoggedOnUser
0x18005ace9  nop     dword ptr [rax+rax+00h]
0x18005acee  test    eax, eax
0x18005acf0  jnz     short loc_18005AD3E
0x18005acf2  mov     edi, r15d
0x18005acf5  mov     esi, r15d
0x18005acf8  call    cs:__imp_GetLastError
0x18005acff  nop     dword ptr [rax+rax+00h]
0x18005ad04  mov     ebx, eax
0x18005ad06  test    eax, eax
0x18005ad08  jz      loc_18005AF4E
0x18005ad0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ad15  cmp     rcx, r13
0x18005ad18  jz      loc_18005AF55
0x18005ad1e  test    [rcx+1Ch], r12d
0x18005ad22  jz      loc_18005AF55
0x18005ad28  cmp     byte ptr [rcx+19h], 2
0x18005ad2c  jb      loc_18005AF55
0x18005ad32  lea     edx, [r15+78h]
0x18005ad36  mov     r9d, eax
0x18005ad39  jmp     loc_18005AF3E
0x18005ad3e  lea     rax, aMy_0; "MY"
0x18005ad45  mov     esi, 1
0x18005ad4a  mov     ebx, 10001h
0x18005ad4f  mov     [rsp+50h+pvPara], rax; pvPara
0x18005ad54  mov     r9d, 18000h; dwFlags
0x18005ad5a  xor     r8d, r8d; hCryptProv
0x18005ad5d  mov     edx, ebx; dwEncodingType
0x18005ad5f  lea     ecx, [rsi+9]; lpszStoreProvider
0x18005ad62  call    cs:__imp_CertOpenStore
0x18005ad69  nop     dword ptr [rax+rax+00h]
0x18005ad6e  mov     rdi, rax
0x18005ad71  test    rax, rax
0x18005ad74  jnz     short loc_18005ADB5
0x18005ad76  call    cs:__imp_GetLastError
0x18005ad7d  nop     dword ptr [rax+rax+00h]
0x18005ad82  mov     ebx, eax
0x18005ad84  test    eax, eax
0x18005ad86  jz      loc_18005AF4E
0x18005ad8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ad93  cmp     rcx, r13
0x18005ad96  jz      loc_18005AF55
0x18005ad9c  test    [rcx+1Ch], r12d
0x18005ada0  jz      loc_18005AF55
0x18005ada6  cmp     byte ptr [rcx+19h], 2
0x18005adaa  jb      loc_18005AF55
0x18005adb0  lea     edx, [rsi+78h]
0x18005adb3  jmp     short loc_18005AD36
0x18005adb5  lea     rax, [rbp+pvFindPara]
0x18005adb9  mov     [rsp+50h+pPrevCertContext], r15; pPrevCertContext
0x18005adbe  mov     r9d, 10000h; dwFindType
0x18005adc4  mov     [rsp+50h+pvPara], rax; pvFindPara
0x18005adc9  xor     r8d, r8d; dwFindFlags
0x18005adcc  mov     edx, ebx; dwCertEncodingType
0x18005adce  mov     rcx, rdi; hCertStore
0x18005add1  call    cs:__imp_CertFindCertificateInStore
0x18005add8  nop     dword ptr [rax+rax+00h]
0x18005addd  mov     r14, rax
0x18005ade0  test    rax, rax
0x18005ade3  jnz     short loc_18005AE28
0x18005ade5  call    cs:__imp_GetLastError
0x18005adec  nop     dword ptr [rax+rax+00h]
0x18005adf1  mov     ebx, eax
0x18005adf3  test    eax, eax
0x18005adf5  jz      loc_18005AF4E
0x18005adfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ae02  cmp     rcx, r13
0x18005ae05  jz      loc_18005AF55
0x18005ae0b  test    [rcx+1Ch], r12d
0x18005ae0f  jz      loc_18005AF55
0x18005ae15  cmp     byte ptr [rcx+19h], 2
0x18005ae19  jb      loc_18005AF55
0x18005ae1f  lea     edx, [r14+7Ah]
0x18005ae23  jmp     loc_18005AD36
0x18005ae28  lea     rax, [rbp+pfCallerFreeProvOrNCryptKey]
0x18005ae2c  xor     r8d, r8d; pvParameters
0x18005ae2f  mov     [rsp+50h+pPrevCertContext], rax; pfCallerFreeProvOrNCryptKey
0x18005ae34  lea     r9, [rbp+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x18005ae38  lea     rax, [rbp+pdwKeySpec]
0x18005ae3c  mov     edx, 20000h; dwFlags
0x18005ae41  mov     rcx, r14; pCert
0x18005ae44  mov     [rsp+50h+pvPara], rax; pdwKeySpec
0x18005ae49  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x18005ae50  nop     dword ptr [rax+rax+00h]
0x18005ae55  test    eax, eax
0x18005ae57  jnz     short loc_18005AE9D
0x18005ae59  call    cs:__imp_GetLastError
0x18005ae60  nop     dword ptr [rax+rax+00h]
0x18005ae65  mov     ebx, eax
0x18005ae67  test    eax, eax
0x18005ae69  jz      loc_18005AF4E
0x18005ae6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ae76  cmp     rcx, r13
0x18005ae79  jz      loc_18005AF55
0x18005ae7f  test    [rcx+1Ch], r12d
0x18005ae83  jz      loc_18005AF55
0x18005ae89  cmp     byte ptr [rcx+19h], 2
0x18005ae8d  jb      loc_18005AF55
0x18005ae93  mov     edx, 7Bh ; '{'
0x18005ae98  jmp     loc_18005AD36
0x18005ae9d  mov     rdx, [rbp+phCryptProvOrNCryptKey]; hProv
0x18005aea1  lea     r9, [rbp+arg_8]
0x18005aea5  mov     ecx, [rbp+pdwKeySpec]; dwKeySpec
0x18005aea8  mov     r8d, esi
0x18005aeab  call    DoDummySign
0x18005aeb0  mov     ebx, eax
0x18005aeb2  test    eax, eax
0x18005aeb4  jz      short loc_18005AEE0
0x18005aeb6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aebd  cmp     rcx, r13
0x18005aec0  jz      loc_18005AF55
0x18005aec6  test    [rcx+1Ch], r12d
0x18005aeca  jz      loc_18005AF55
0x18005aed0  cmp     byte ptr [rcx+19h], 2
0x18005aed4  jb      short loc_18005AF55
0x18005aed6  mov     edx, 7Ch ; '|'
0x18005aedb  jmp     loc_18005AD36
0x18005aee0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aee7  cmp     rcx, r13
0x18005aeea  jz      short loc_18005AF1C
0x18005aeec  test    [rcx+1Ch], r12d
0x18005aef0  jz      short loc_18005AF1C
0x18005aef2  cmp     byte ptr [rcx+19h], 5
0x18005aef6  jb      short loc_18005AF1C
0x18005aef8  cmp     [rbp+arg_8], r15d
0x18005aefc  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x18005af03  mov     rcx, [rcx+10h]
0x18005af07  mov     edx, 7Dh ; '}'
0x18005af0c  setnz   r9b
0x18005af10  call    WPP_SF_c
0x18005af15  mov     rcx, cs:WPP_GLOBAL_Control
0x18005af1c  cmp     [rbp+arg_8], r15d
0x18005af20  jnz     short loc_18005AF55
0x18005af22  mov     ebx, 57h ; 'W'
0x18005af27  cmp     rcx, r13
0x18005af2a  jz      short loc_18005AF55
0x18005af2c  test    [rcx+1Ch], r12d
0x18005af30  jz      short loc_18005AF55
0x18005af32  cmp     byte ptr [rcx+19h], 2
0x18005af36  jb      short loc_18005AF55
0x18005af38  lea     edx, [rbx+27h]
0x18005af3b  mov     r9d, ebx
0x18005af3e  mov     rcx, [rcx+10h]
0x18005af42  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x18005af49  call    WPP_SF_d
0x18005af4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005af55  cmp     [rbp+pfCallerFreeProvOrNCryptKey], r15d
0x18005af59  jz      short loc_18005AF88
0x18005af5b  cmp     [rbp+pdwKeySpec], 0FFFFFFFFh
0x18005af5f  mov     rcx, [rbp+phCryptProvOrNCryptKey]; hProv
0x18005af63  jnz     short loc_18005AF73
0x18005af65  call    cs:__imp_NCryptFreeObject
0x18005af6c  nop     dword ptr [rax+rax+00h]
0x18005af71  jmp     short loc_18005AF81
0x18005af73  xor     edx, edx; dwFlags
0x18005af75  call    cs:__imp_CryptReleaseContext
0x18005af7c  nop     dword ptr [rax+rax+00h]
0x18005af81  mov     rcx, cs:WPP_GLOBAL_Control
0x18005af88  test    r14, r14
0x18005af8b  jz      short loc_18005AFA3
0x18005af8d  mov     rcx, r14; pCertContext
0x18005af90  call    cs:__imp_CertFreeCertificateContext
0x18005af97  nop     dword ptr [rax+rax+00h]
0x18005af9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005afa3  test    rdi, rdi
0x18005afa6  jz      short loc_18005AFC0
0x18005afa8  xor     edx, edx; dwFlags
0x18005afaa  mov     rcx, rdi; hCertStore
0x18005afad  call    cs:__imp_CertCloseStore
0x18005afb4  nop     dword ptr [rax+rax+00h]
0x18005afb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005afc0  test    esi, esi
0x18005afc2  jz      short loc_18005B021
0x18005afc4  call    cs:__imp_RevertToSelf
0x18005afcb  nop     dword ptr [rax+rax+00h]
0x18005afd0  test    eax, eax
0x18005afd2  jnz     short loc_18005B01A
0x18005afd4  test    ebx, ebx
0x18005afd6  jnz     short loc_18005B01A
0x18005afd8  call    cs:__imp_GetLastError
0x18005afdf  nop     dword ptr [rax+rax+00h]
0x18005afe4  mov     ebx, eax
0x18005afe6  test    eax, eax
0x18005afe8  jz      short loc_18005B01A
0x18005afea  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aff1  cmp     rcx, r13
0x18005aff4  jz      short loc_18005B04A
0x18005aff6  test    [rcx+1Ch], r12d
0x18005affa  jz      short loc_18005B021
0x18005affc  cmp     byte ptr [rcx+19h], 2
0x18005b000  jb      short loc_18005B021
0x18005b002  mov     rcx, [rcx+10h]
0x18005b006  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x18005b00d  mov     edx, 7Fh
0x18005b012  mov     r9d, eax
0x18005b015  call    WPP_SF_d
0x18005b01a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b021  cmp     rcx, r13
0x18005b024  jz      short loc_18005B04A
0x18005b026  test    [rcx+1Ch], r12d
0x18005b02a  jz      short loc_18005B04A
0x18005b02c  cmp     byte ptr [rcx+19h], 6
0x18005b030  jb      short loc_18005B04A
0x18005b032  mov     rcx, [rcx+10h]
0x18005b036  lea     r8, WPP_04c25a37be9d3af9bf8f5a84c4d81d65_Traceguids
0x18005b03d  mov     edx, 80h
0x18005b042  mov     r9d, ebx
0x18005b045  call    WPP_SF_d
0x18005b04a  mov     eax, ebx
0x18005b04c  mov     rbx, [rsp+50h+arg_0]
0x18005b054  add     rsp, 50h
0x18005b058  pop     r15
0x18005b05a  pop     r14
0x18005b05c  pop     r13
0x18005b05e  pop     r12
0x18005b060  pop     rdi
0x18005b061  pop     rsi
0x18005b062  pop     rbp
0x18005b063  retn
```
