# CryptUIDlgSelectCertificateW

- ea: `0x1800389e0`
- end: `0x180038d44`
- name: `CryptUIDlgSelectCertificateW`
- size: `868`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180038850`
- `0x180038930`

## callees

- `0x18002e368`
- `0x180038488`
- `0x1800389e0`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038cc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038cc4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038a68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038a68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180038aee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180038b2f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180038aee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180038b2f`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180038b65`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180038b65`
- `CRYPT32!CertFindCertificateInStore` at `0x180038c59`
- `CRYPT32!CertFindCertificateInStore` at `0x180038c59`
- `CRYPT32!CertFreeCertificateContext` at `0x180038c73`
- `CRYPT32!CertFreeCertificateContext` at `0x180038caf`
- `CRYPT32!CertFreeCertificateContext` at `0x180038c73`
- `CRYPT32!CertFreeCertificateContext` at `0x180038caf`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180038ca2`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180038ca2`
- `CRYPT32!CertAddSerializedElementToStore` at `0x180038c0f`
- `CRYPT32!CertAddSerializedElementToStore` at `0x180038c0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038cee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038cee`
- `ncrypt!NCryptFreeObject` at `0x180038d0b`
- `ncrypt!NCryptFreeObject` at `0x180038d0b`
- `CRYPTSP!CryptReleaseContext` at `0x180038d15`
- `CRYPTSP!CryptReleaseContext` at `0x180038d15`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x180038bd7`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x180038bd7`

## pseudocode

```c
const struct _CERT_CONTEXT *__fastcall CryptUIDlgSelectCertificateW(__int64 a1)
{
  int v2; // eax
  const CERT_CONTEXT *CertificateInStore; // r14
  WCHAR *v5; // rax
  UINT v6; // esi
  unsigned int v7; // edi
  UINT v8; // edx
  WCHAR *v9; // rax
  unsigned int i; // edi
  __int64 v11; // rcx
  void *v12; // rsi
  unsigned int j; // edi
  BYTE *v14; // rcx
  __int64 v15; // rax
  ULONG cbElement; // [rsp+50h] [rbp-B0h] BYREF
  void *ppvContext; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v18; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ulInAuthBufferSize; // [rsp+64h] [rbp-9Ch] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD pdwKeySpec; // [rsp+6Ch] [rbp-94h] BYREF
  LPCVOID pvInAuthBuffer; // [rsp+70h] [rbp-90h] BYREF
  BYTE *pbElement; // [rsp+78h] [rbp-88h] BYREF
  BOOL pfSave; // [rsp+80h] [rbp-80h] BYREF
  ULONG pulAuthPackage; // [rsp+84h] [rbp-7Ch] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+88h] [rbp-78h] BYREF
  _CREDUI_INFOW pUiInfo; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[512]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v29[512]; // [rsp+4C0h] [rbp+3C0h] BYREF

  pulAuthPackage = -509;
  pbElement = 0;
  v2 = *(_DWORD *)a1 - 120;
  cbElement = 0;
  pfSave = 0;
  ppvContext = 0;
  pvInAuthBuffer = 0;
  ulInAuthBufferSize = 0;
  v18 = 0;
  phCryptProvOrNCryptKey = 0;
  pdwKeySpec = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  memset(&pUiInfo, 0, sizeof(pUiInfo));
  if ( (v2 & 0xFFFFFFF7) != 0 )
  {
    SetLastError(0x80070057);
    return 0;
  }
  if ( *(_DWORD *)(a1 + 88) || (*(_DWORD *)(a1 + 16) & 0x1010001) != 0 || *(_DWORD *)(a1 + 104) )
    return ShowLegacyCertificateSelectionUI((const struct tagCRYPTUI_SELECTCERTIFICATE_STRUCTW *)a1);
  CertificateInStore = 0;
  if ( !ObtainSerializedBlob(
          (const struct tagCRYPTUI_SELECTCERTIFICATE_STRUCTW *)a1,
          (void **)&pvInAuthBuffer,
          &ulInAuthBufferSize,
          &v18) )
  {
    v5 = *(WCHAR **)(a1 + 24);
    v6 = 3446;
    v7 = v18;
    if ( !v5 )
    {
      if ( v18 )
      {
        v8 = 3322;
        if ( v18 == 1 )
          v8 = 3447;
      }
      else
      {
        v8 = 3446;
      }
      LoadStringW(HinstDll, v8, Buffer, 512);
      v5 = Buffer;
    }
    pUiInfo.pszCaptionText = v5;
    v9 = *(WCHAR **)(a1 + 40);
    if ( !v9 )
    {
      if ( v7 )
      {
        v6 = 3312;
        if ( v7 == 1 )
          v6 = 3448;
      }
      LoadStringW(HinstDll, v6, v29, 512);
      v9 = v29;
    }
    pUiInfo.pszMessageText = v9;
    if ( v7 == 1 && (*(_BYTE *)(a1 + 16) & 0x20) != 0 )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 72); ++i )
      {
        v11 = *(_QWORD *)(a1 + 80);
        ppvContext = 0;
        ppvContext = (void *)CertEnumCertificatesInStore(*(HCERTSTORE *)(v11 + 8LL * i), 0);
        if ( ppvContext )
          break;
      }
      v12 = (void *)(a1 + 8);
      goto LABEL_26;
    }
    v12 = (void *)(a1 + 8);
    pUiInfo.hwndParent = *(HWND *)(a1 + 8);
    pUiInfo.cbSize = 40;
    pUiInfo.hbmBanner = 0;
    if ( CredUIPromptForWindowsCredentialsW(
           &pUiInfo,
           0,
           &pulAuthPackage,
           pvInAuthBuffer,
           ulInAuthBufferSize,
           (LPVOID *)&pbElement,
           &cbElement,
           &pfSave,
           0x10u)
      || CertAddSerializedElementToStore(0, pbElement, cbElement, 4u, 0, 2u, 0, (const void **)&ppvContext) )
    {
LABEL_26:
      if ( ppvContext )
      {
        for ( j = 0; j < *(_DWORD *)(a1 + 72); ++j )
        {
          CertificateInStore = CertFindCertificateInStore(
                                 *(HCERTSTORE *)(*(_QWORD *)(a1 + 80) + 8LL * j),
                                 0x10001u,
                                 0,
                                 0xD0000u,
                                 ppvContext,
                                 0);
          if ( CertificateInStore )
            break;
        }
        CertFreeCertificateContext((PCCERT_CONTEXT)ppvContext);
        if ( (*(_BYTE *)(a1 + 16) & 0x40) != 0
          && !CryptAcquireCertificatePrivateKey(
                CertificateInStore,
                0x10080u,
                v12,
                &phCryptProvOrNCryptKey,
                &pdwKeySpec,
                &pfCallerFreeProvOrNCryptKey) )
        {
          CertFreeCertificateContext(CertificateInStore);
          CertificateInStore = 0;
        }
      }
    }
  }
  if ( pvInAuthBuffer )
    LocalFree((HLOCAL)pvInAuthBuffer);
  v14 = pbElement;
  if ( pbElement )
  {
    v15 = cbElement;
    if ( cbElement )
    {
      do
      {
        *v14++ = 0;
        --v15;
      }
      while ( v15 );
      v14 = pbElement;
    }
    CoTaskMemFree(v14);
  }
  if ( phCryptProvOrNCryptKey && pfCallerFreeProvOrNCryptKey )
  {
    if ( pdwKeySpec )
      NCryptFreeObject(phCryptProvOrNCryptKey);
    else
      CryptReleaseContext(phCryptProvOrNCryptKey, 0);
  }
  return CertificateInStore;
}

```

## disassembly

```asm
0x1800389e0  push    rbp
0x1800389e2  push    rbx
0x1800389e3  push    rsi
0x1800389e4  push    rdi
0x1800389e5  push    r12
0x1800389e7  push    r14
0x1800389e9  lea     rbp, [rsp-7D8h]
0x1800389f1  sub     rsp, 8D8h
0x1800389f8  mov     rax, cs:__security_cookie
0x1800389ff  xor     rax, rsp
0x180038a02  mov     [rbp+800h+var_40], rax
0x180038a09  xor     r12d, r12d
0x180038a0c  mov     [rbp+800h+pulAuthPackage], 0FFFFFE03h
0x180038a13  xor     eax, eax
0x180038a15  mov     [rsp+900h+pbElement], r12
0x180038a1a  mov     [rbp+800h+pUiInfo.hbmBanner], rax
0x180038a1e  xorps   xmm0, xmm0
0x180038a21  mov     eax, [rcx]
0x180038a23  mov     rbx, rcx
0x180038a26  sub     eax, 78h ; 'x'
0x180038a29  mov     [rsp+900h+cbElement], r12d
0x180038a2e  mov     [rbp+800h+var_880], r12d
0x180038a32  mov     [rsp+900h+ppvContext], r12
0x180038a37  mov     [rsp+900h+pvInAuthBuffer], r12
0x180038a3c  mov     [rsp+900h+var_89C], r12d
0x180038a41  mov     [rsp+900h+var_8A0], r12d
0x180038a46  mov     [rbp+800h+phCryptProvOrNCryptKey], r12
0x180038a4a  mov     [rsp+900h+pdwKeySpec], r12d
0x180038a4f  mov     [rsp+900h+pfCallerFreeProvOrNCryptKey], r12d
0x180038a54  movups  xmmword ptr [rbp+800h+pUiInfo.cbSize], xmm0
0x180038a58  movups  xmmword ptr [rbp+800h+pUiInfo.pszMessageText], xmm0
0x180038a5c  test    eax, 0FFFFFFF7h
0x180038a61  jz      short loc_180038A75
0x180038a63  mov     ecx, 80070057h; dwErrCode
0x180038a68  call    cs:__imp_SetLastError
0x180038a6e  xor     eax, eax
0x180038a70  jmp     loc_180038D25
0x180038a75  cmp     [rcx+58h], r12d
0x180038a79  jnz     loc_180038D20
0x180038a7f  test    dword ptr [rcx+10h], 1010001h
0x180038a86  jnz     loc_180038D20
0x180038a8c  cmp     [rcx+68h], r12d
0x180038a90  jnz     loc_180038D20
0x180038a96  lea     r9, [rsp+900h+var_8A0]; unsigned int *
0x180038a9b  mov     r14, r12
0x180038a9e  lea     r8, [rsp+900h+var_89C]; unsigned int *
0x180038aa3  lea     rdx, [rsp+900h+pvInAuthBuffer]; void **
0x180038aa8  call    ?ObtainSerializedBlob@@YAJPEBUtagCRYPTUI_SELECTCERTIFICATE_STRUCTW@@PEAPEAXPEAK2@Z; ObtainSerializedBlob(tagCRYPTUI_SELECTCERTIFICATE_STRUCTW const *,void * *,ulong *,ulong *)
0x180038aad  test    eax, eax
0x180038aaf  jnz     loc_180038CB8
0x180038ab5  mov     rax, [rbx+18h]
0x180038ab9  mov     esi, 0D76h
0x180038abe  mov     edi, [rsp+900h+var_8A0]
0x180038ac2  test    rax, rax
0x180038ac5  jnz     short loc_180038AF8
0x180038ac7  test    edi, edi
0x180038ac9  jnz     short loc_180038ACF
0x180038acb  mov     edx, esi
0x180038acd  jmp     short loc_180038ADD
0x180038acf  mov     edx, 0CFAh
0x180038ad4  cmp     edi, 1
0x180038ad7  lea     eax, [rdx+7Dh]
0x180038ada  cmovz   edx, eax; uID
0x180038add  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180038ae4  lea     r8, [rbp+800h+Buffer]; lpBuffer
0x180038ae8  mov     r9d, 200h; cchBufferMax
0x180038aee  call    cs:__imp_LoadStringW
0x180038af4  lea     rax, [rbp+800h+Buffer]
0x180038af8  mov     [rbp+800h+pUiInfo.pszCaptionText], rax
0x180038afc  mov     rax, [rbx+28h]
0x180038b00  test    rax, rax
0x180038b03  jnz     short loc_180038B3C
0x180038b05  test    edi, edi
0x180038b07  jz      short loc_180038B19
0x180038b09  cmp     edi, 1
0x180038b0c  mov     esi, 0CF0h
0x180038b11  mov     eax, 0D78h
0x180038b16  cmovz   esi, eax
0x180038b19  mov     rcx, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; hInstance
0x180038b20  lea     r8, [rbp+800h+var_440]; lpBuffer
0x180038b27  mov     r9d, 200h; cchBufferMax
0x180038b2d  mov     edx, esi; uID
0x180038b2f  call    cs:__imp_LoadStringW
0x180038b35  lea     rax, [rbp+800h+var_440]
0x180038b3c  mov     [rbp+800h+pUiInfo.pszMessageText], rax
0x180038b40  cmp     edi, 1
0x180038b43  jnz     short loc_180038B85
0x180038b45  test    byte ptr [rbx+10h], 20h
0x180038b49  jz      short loc_180038B85
0x180038b4b  mov     edi, r12d
0x180038b4e  cmp     [rbx+48h], r12d
0x180038b52  jbe     short loc_180038B7C
0x180038b54  mov     rcx, [rbx+50h]
0x180038b58  xor     edx, edx; pPrevCertContext
0x180038b5a  mov     eax, edi
0x180038b5c  mov     [rsp+900h+ppvContext], r12
0x180038b61  mov     rcx, [rcx+rax*8]; hCertStore
0x180038b65  call    cs:__imp_CertEnumCertificatesInStore
0x180038b6b  mov     [rsp+900h+ppvContext], rax
0x180038b70  test    rax, rax
0x180038b73  jnz     short loc_180038B7C
0x180038b75  inc     edi
0x180038b77  cmp     edi, [rbx+48h]
0x180038b7a  jb      short loc_180038B54
0x180038b7c  lea     rsi, [rbx+8]
0x180038b80  jmp     loc_180038C1D
0x180038b85  mov     r9, [rsp+900h+pvInAuthBuffer]; pvInAuthBuffer
0x180038b8a  lea     rsi, [rbx+8]
0x180038b8e  mov     rax, [rsi]
0x180038b91  lea     r8, [rbp+800h+pulAuthPackage]; pulAuthPackage
0x180038b95  mov     [rbp+800h+pUiInfo.hwndParent], rax
0x180038b99  lea     rcx, [rbp+800h+pUiInfo]; pUiInfo
0x180038b9d  mov     [rsp+900h+dwFlags], 10h; dwFlags
0x180038ba5  lea     rax, [rbp+800h+var_880]
0x180038ba9  mov     [rsp+900h+pfSave], rax; pfSave
0x180038bae  xor     edx, edx; dwAuthError
0x180038bb0  lea     rax, [rsp+900h+cbElement]
0x180038bb5  mov     [rbp+800h+pUiInfo.cbSize], 28h ; '('
0x180038bbc  mov     [rsp+900h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x180038bc1  lea     rax, [rsp+900h+pbElement]
0x180038bc6  mov     [rsp+900h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x180038bcb  mov     eax, [rsp+900h+var_89C]
0x180038bcf  mov     [rsp+900h+ulInAuthBufferSize], eax; ulInAuthBufferSize
0x180038bd3  mov     [rbp+800h+pUiInfo.hbmBanner], r12
0x180038bd7  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x180038bdd  test    eax, eax
0x180038bdf  jnz     short loc_180038C1D
0x180038be1  mov     r8d, [rsp+900h+cbElement]; cbElement
0x180038be6  lea     rax, [rsp+900h+ppvContext]
0x180038beb  mov     rdx, [rsp+900h+pbElement]; pbElement
0x180038bf0  mov     r9d, 4; dwAddDisposition
0x180038bf6  mov     [rsp+900h+pfSave], rax; ppvContext
0x180038bfb  xor     ecx, ecx; hCertStore
0x180038bfd  mov     [rsp+900h+pulOutAuthBufferSize], r12; pdwContextType
0x180038c02  mov     dword ptr [rsp+900h+ppvOutAuthBuffer], 2; dwContextTypeFlags
0x180038c0a  mov     [rsp+900h+ulInAuthBufferSize], r12d; dwFlags
0x180038c0f  call    cs:__imp_CertAddSerializedElementToStore
0x180038c15  test    eax, eax
0x180038c17  jz      loc_180038CB8
0x180038c1d  cmp     [rsp+900h+ppvContext], r12
0x180038c22  jz      loc_180038CB8
0x180038c28  mov     edi, r12d
0x180038c2b  cmp     [rbx+48h], r12d
0x180038c2f  jbe     short loc_180038C6E
0x180038c31  mov     rcx, [rbx+50h]
0x180038c35  mov     r9d, 0D0000h; dwFindType
0x180038c3b  mov     rax, [rsp+900h+ppvContext]
0x180038c40  xor     r8d, r8d; dwFindFlags
0x180038c43  mov     r10d, edi
0x180038c46  mov     edx, 10001h; dwCertEncodingType
0x180038c4b  mov     [rsp+900h+ppvOutAuthBuffer], r12; pPrevCertContext
0x180038c50  mov     qword ptr [rsp+900h+ulInAuthBufferSize], rax; pvFindPara
0x180038c55  mov     rcx, [rcx+r10*8]; hCertStore
0x180038c59  call    cs:__imp_CertFindCertificateInStore
0x180038c5f  mov     r14, rax
0x180038c62  test    rax, rax
0x180038c65  jnz     short loc_180038C6E
0x180038c67  inc     edi
0x180038c69  cmp     edi, [rbx+48h]
0x180038c6c  jb      short loc_180038C31
0x180038c6e  mov     rcx, [rsp+900h+ppvContext]; pCertContext
0x180038c73  call    cs:__imp_CertFreeCertificateContext
0x180038c79  test    byte ptr [rbx+10h], 40h
0x180038c7d  jz      short loc_180038CB8
0x180038c7f  lea     rax, [rsp+900h+pfCallerFreeProvOrNCryptKey]
0x180038c84  mov     r8, rsi; pvParameters
0x180038c87  mov     [rsp+900h+ppvOutAuthBuffer], rax; pfCallerFreeProvOrNCryptKey
0x180038c8c  lea     r9, [rbp+800h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x180038c90  lea     rax, [rsp+900h+pdwKeySpec]
0x180038c95  mov     edx, 10080h; dwFlags
0x180038c9a  mov     rcx, r14; pCert
0x180038c9d  mov     qword ptr [rsp+900h+ulInAuthBufferSize], rax; pdwKeySpec
0x180038ca2  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x180038ca8  test    eax, eax
0x180038caa  jnz     short loc_180038CB8
0x180038cac  mov     rcx, r14; pCertContext
0x180038caf  call    cs:__imp_CertFreeCertificateContext
0x180038cb5  mov     r14, r12
0x180038cb8  cmp     [rsp+900h+pvInAuthBuffer], r12
0x180038cbd  jz      short loc_180038CCA
0x180038cbf  mov     rcx, [rsp+900h+pvInAuthBuffer]; hMem
0x180038cc4  call    cs:__imp_LocalFree
0x180038cca  mov     rcx, [rsp+900h+pbElement]
0x180038ccf  test    rcx, rcx
0x180038cd2  jz      short loc_180038CF4
0x180038cd4  mov     eax, [rsp+900h+cbElement]
0x180038cd8  test    rax, rax
0x180038cdb  jz      short loc_180038CEE
0x180038cdd  mov     [rcx], r12b
0x180038ce0  inc     rcx
0x180038ce3  sub     rax, 1
0x180038ce7  jnz     short loc_180038CDD
0x180038ce9  mov     rcx, [rsp+900h+pbElement]; pv
0x180038cee  call    cs:__imp_CoTaskMemFree
0x180038cf4  mov     rcx, [rbp+800h+phCryptProvOrNCryptKey]; hProv
0x180038cf8  test    rcx, rcx
0x180038cfb  jz      short loc_180038D1B
0x180038cfd  cmp     [rsp+900h+pfCallerFreeProvOrNCryptKey], r12d
0x180038d02  jz      short loc_180038D1B
0x180038d04  cmp     [rsp+900h+pdwKeySpec], r12d
0x180038d09  jz      short loc_180038D13
0x180038d0b  call    cs:__imp_NCryptFreeObject
0x180038d11  jmp     short loc_180038D1B
0x180038d13  xor     edx, edx; dwFlags
0x180038d15  call    cs:__imp_CryptReleaseContext
0x180038d1b  mov     rax, r14
0x180038d1e  jmp     short loc_180038D25
0x180038d20  call    ?ShowLegacyCertificateSelectionUI@@YAPEBU_CERT_CONTEXT@@PEBUtagCRYPTUI_SELECTCERTIFICATE_STRUCTW@@@Z; ShowLegacyCertificateSelectionUI(tagCRYPTUI_SELECTCERTIFICATE_STRUCTW const *)
0x180038d25  mov     rcx, [rbp+800h+var_40]
0x180038d2c  xor     rcx, rsp; StackCookie
0x180038d2f  call    __security_check_cookie
0x180038d34  add     rsp, 8D8h
0x180038d3b  pop     r14
0x180038d3d  pop     r12
0x180038d3f  pop     rdi
0x180038d40  pop     rsi
0x180038d41  pop     rbx
0x180038d42  pop     rbp
0x180038d43  retn
```
