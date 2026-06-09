# RefreshPasswordCertContext(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_CACHED_CREDS *)

- ea: `0x180056aac`
- end: `0x180056c76`
- name: `?RefreshPasswordCertContext@@YAHPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_CACHED_CREDS@@@Z`
- size: `458`
- prototype: `int(struct _EAPTLS_CONTROL_BLOCK *, struct _EAPTLS_CACHED_CREDS *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022a48`

## callees

- `0x180004bd0`
- `0x18002ce48`
- `0x180056aac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056bcd`
- `CRYPT32!CertCloseStore` at `0x180056c59`
- `CRYPT32!CertCloseStore` at `0x180056c59`
- `CRYPT32!CertFindCertificateInStore` at `0x180056b69`
- `CRYPT32!CertFindCertificateInStore` at `0x180056b69`
- `CRYPT32!CertFreeCertificateContext` at `0x180056c05`
- `CRYPT32!CertFreeCertificateContext` at `0x180056c36`
- `CRYPT32!CertFreeCertificateContext` at `0x180056c05`
- `CRYPT32!CertFreeCertificateContext` at `0x180056c36`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180056bb3`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180056bb3`
- `CRYPT32!CertOpenStore` at `0x180056b02`
- `CRYPT32!CertOpenStore` at `0x180056b02`
- `ncrypt!NCryptFreeObject` at `0x180056c22`
- `ncrypt!NCryptFreeObject` at `0x180056c22`
- `CRYPTSP!CryptReleaseContext` at `0x180056c2c`
- `CRYPTSP!CryptReleaseContext` at `0x180056c2c`

## pseudocode

```c
__int64 __fastcall RefreshPasswordCertContext(struct _EAPTLS_CONTROL_BLOCK *a1, struct _EAPTLS_CACHED_CREDS *a2)
{
  unsigned __int8 v4; // si
  HCERTSTORE v5; // rax
  void *v6; // r14
  const CERT_CONTEXT *CertificateInStore; // rdi
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  NCRYPT_HANDLE v11; // rcx
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+30h] [rbp-20h] BYREF
  __int128 pvFindPara; // [rsp+38h] [rbp-18h] BYREF
  BOOL pfCallerFreeProvOrNCryptKey; // [rsp+80h] [rbp+30h] BYREF
  DWORD pdwKeySpec; // [rsp+88h] [rbp+38h] BYREF

  phCryptProvOrNCryptKey = 0;
  pfCallerFreeProvOrNCryptKey = 0;
  pdwKeySpec = 0;
  v4 = 1;
  pvFindPara = 0;
  v5 = CertOpenStore((LPCSTR)9, 1u, 0, 0x18000u, "MY");
  v6 = v5;
  if ( !v5 )
  {
    CertificateInStore = 0;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_11;
    LastError = GetLastError();
    v9 = 108;
    goto LABEL_10;
  }
  v10 = *((_QWORD *)a1 + 71);
  LODWORD(pvFindPara) = *(_DWORD *)(v10 + 16);
  *((_QWORD *)&pvFindPara + 1) = v10 + 20;
  CertificateInStore = CertFindCertificateInStore(v5, 1u, 0, 0x10000u, &pvFindPara, 0);
  if ( !CertificateInStore )
  {
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_11;
    LastError = GetLastError();
    v9 = 109;
    goto LABEL_10;
  }
  if ( CryptAcquireCertificatePrivateKey(
         CertificateInStore,
         0x40008u,
         0,
         &phCryptProvOrNCryptKey,
         &pdwKeySpec,
         &pfCallerFreeProvOrNCryptKey) )
  {
    if ( *((_DWORD *)a2 + 19) )
    {
      v11 = *((_QWORD *)a2 + 8);
      if ( *((_DWORD *)a2 + 18) == -1 )
        NCryptFreeObject(v11);
      else
        CryptReleaseContext(v11, 0);
    }
    CertFreeCertificateContext(*((PCCERT_CONTEXT *)a2 + 7));
    *((_DWORD *)a2 + 19) = pfCallerFreeProvOrNCryptKey;
    *((_DWORD *)a2 + 18) = pdwKeySpec;
    *((_QWORD *)a2 + 8) = phCryptProvOrNCryptKey;
    *((_QWORD *)a2 + 7) = CertificateInStore;
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    LastError = GetLastError();
    v9 = 110;
LABEL_10:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, LastError);
  }
LABEL_11:
  v4 = 0;
  RemoveNodeFromCachedCredList(a2);
  if ( CertificateInStore )
    CertFreeCertificateContext(CertificateInStore);
  if ( v6 )
LABEL_20:
    CertCloseStore(v6, 0);
  return v4;
}

```

## disassembly

```asm
0x180056aac  mov     [rsp-18h+arg_0], rbx
0x180056ab1  mov     [rsp-18h+arg_8], rsi
0x180056ab6  push    rbp
0x180056ab7  push    rdi
0x180056ab8  push    r14
0x180056aba  mov     rbp, rsp
0x180056abd  sub     rsp, 50h
0x180056ac1  xor     r8d, r8d; hCryptProv
0x180056ac4  mov     [rbp+phCryptProvOrNCryptKey], 0
0x180056acc  mov     rbx, rdx
0x180056acf  mov     [rbp+pfCallerFreeProvOrNCryptKey], 0
0x180056ad6  mov     rdi, rcx
0x180056ad9  mov     [rbp+pdwKeySpec], 0
0x180056ae0  xorps   xmm0, xmm0
0x180056ae3  lea     rax, aMy; "MY"
0x180056aea  lea     esi, [r8+1]
0x180056aee  mov     [rsp+50h+pvPara], rax; pvPara
0x180056af3  mov     edx, esi; dwEncodingType
0x180056af5  lea     ecx, [rsi+8]; lpszStoreProvider
0x180056af8  mov     r9d, 18000h; dwFlags
0x180056afe  movups  [rbp+pvFindPara], xmm0
0x180056b02  call    cs:__imp_CertOpenStore
0x180056b08  mov     r14, rax
0x180056b0b  test    rax, rax
0x180056b0e  jnz     short loc_180056B34
0x180056b10  xor     edi, edi
0x180056b12  lea     rcx, WPP_GLOBAL_Control
0x180056b19  cmp     cs:WPP_GLOBAL_Control, rcx
0x180056b20  jz      loc_180056BF2
0x180056b26  call    cs:__imp_GetLastError
0x180056b2c  lea     edx, [rsi+6Bh]
0x180056b2f  jmp     loc_180056BD8
0x180056b34  mov     rcx, [rdi+238h]
0x180056b3b  mov     r9d, 10000h; dwFindType
0x180056b41  mov     [rsp+50h+pPrevCertContext], 0; pPrevCertContext
0x180056b4a  xor     r8d, r8d; dwFindFlags
0x180056b4d  mov     edx, esi; dwCertEncodingType
0x180056b4f  mov     eax, [rcx+10h]
0x180056b52  mov     dword ptr [rbp+pvFindPara], eax
0x180056b55  lea     rax, [rcx+14h]
0x180056b59  mov     qword ptr [rbp+pvFindPara+8], rax
0x180056b5d  mov     rcx, r14; hCertStore
0x180056b60  lea     rax, [rbp+pvFindPara]
0x180056b64  mov     [rsp+50h+pvPara], rax; pvFindPara
0x180056b69  call    cs:__imp_CertFindCertificateInStore
0x180056b6f  mov     rdi, rax
0x180056b72  test    rax, rax
0x180056b75  jnz     short loc_180056B92
0x180056b77  lea     rcx, WPP_GLOBAL_Control
0x180056b7e  cmp     cs:WPP_GLOBAL_Control, rcx
0x180056b85  jz      short loc_180056BF2
0x180056b87  call    cs:__imp_GetLastError
0x180056b8d  lea     edx, [rdi+6Dh]
0x180056b90  jmp     short loc_180056BD8
0x180056b92  lea     rax, [rbp+pfCallerFreeProvOrNCryptKey]
0x180056b96  xor     r8d, r8d; pvParameters
0x180056b99  mov     [rsp+50h+pPrevCertContext], rax; pfCallerFreeProvOrNCryptKey
0x180056b9e  lea     r9, [rbp+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x180056ba2  lea     rax, [rbp+pdwKeySpec]
0x180056ba6  mov     edx, 40008h; dwFlags
0x180056bab  mov     rcx, rdi; pCert
0x180056bae  mov     [rsp+50h+pvPara], rax; pdwKeySpec
0x180056bb3  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x180056bb9  test    eax, eax
0x180056bbb  jnz     short loc_180056C12
0x180056bbd  lea     rcx, WPP_GLOBAL_Control
0x180056bc4  cmp     cs:WPP_GLOBAL_Control, rcx
0x180056bcb  jz      short loc_180056BF2
0x180056bcd  call    cs:__imp_GetLastError
0x180056bd3  mov     edx, 6Eh ; 'n'
0x180056bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180056bdf  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180056be6  mov     r9d, eax
0x180056be9  mov     rcx, [rcx+10h]
0x180056bed  call    WPP_SF_d
0x180056bf2  mov     rcx, rbx; hMem
0x180056bf5  xor     sil, sil
0x180056bf8  call    ?RemoveNodeFromCachedCredList@@YAKPEAU_EAPTLS_CACHED_CREDS@@@Z; RemoveNodeFromCachedCredList(_EAPTLS_CACHED_CREDS *)
0x180056bfd  test    rdi, rdi
0x180056c00  jz      short loc_180056C0B
0x180056c02  mov     rcx, rdi; pCertContext
0x180056c05  call    cs:__imp_CertFreeCertificateContext
0x180056c0b  test    r14, r14
0x180056c0e  jz      short loc_180056C5F
0x180056c10  jmp     short loc_180056C54
0x180056c12  cmp     dword ptr [rbx+4Ch], 0
0x180056c16  jz      short loc_180056C32
0x180056c18  cmp     dword ptr [rbx+48h], 0FFFFFFFFh
0x180056c1c  mov     rcx, [rbx+40h]; hProv
0x180056c20  jnz     short loc_180056C2A
0x180056c22  call    cs:__imp_NCryptFreeObject
0x180056c28  jmp     short loc_180056C32
0x180056c2a  xor     edx, edx; dwFlags
0x180056c2c  call    cs:__imp_CryptReleaseContext
0x180056c32  mov     rcx, [rbx+38h]; pCertContext
0x180056c36  call    cs:__imp_CertFreeCertificateContext
0x180056c3c  mov     eax, [rbp+pfCallerFreeProvOrNCryptKey]
0x180056c3f  mov     [rbx+4Ch], eax
0x180056c42  mov     eax, [rbp+pdwKeySpec]
0x180056c45  mov     [rbx+48h], eax
0x180056c48  mov     rax, [rbp+phCryptProvOrNCryptKey]
0x180056c4c  mov     [rbx+40h], rax
0x180056c50  mov     [rbx+38h], rdi
0x180056c54  xor     edx, edx; dwFlags
0x180056c56  mov     rcx, r14; hCertStore
0x180056c59  call    cs:__imp_CertCloseStore
0x180056c5f  mov     rbx, [rsp+50h+arg_0]
0x180056c64  movzx   eax, sil
0x180056c68  mov     rsi, [rsp+50h+arg_8]
0x180056c6d  add     rsp, 50h
0x180056c71  pop     r14
0x180056c73  pop     rdi
0x180056c74  pop     rbp
0x180056c75  retn
```
