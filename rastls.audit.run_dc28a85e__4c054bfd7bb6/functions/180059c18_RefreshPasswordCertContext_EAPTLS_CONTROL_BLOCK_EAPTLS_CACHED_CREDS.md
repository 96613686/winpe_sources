# RefreshPasswordCertContext(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_CACHED_CREDS *)

- ea: `0x180059c18`
- end: `0x180059e25`
- name: `?RefreshPasswordCertContext@@YAHPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_CACHED_CREDS@@@Z`
- size: `525`
- prototype: `int(struct _EAPTLS_CONTROL_BLOCK *, struct _EAPTLS_CACHED_CREDS *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180025564`

## callees

- `0x180005010`
- `0x18002f38c`
- `0x180059c18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059d57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059c98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059d05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059d57`
- `CRYPT32!CertCloseStore` at `0x180059e01`
- `CRYPT32!CertCloseStore` at `0x180059e01`
- `CRYPT32!CertFindCertificateInStore` at `0x180059ce1`
- `CRYPT32!CertFindCertificateInStore` at `0x180059ce1`
- `CRYPT32!CertFreeCertificateContext` at `0x180059d95`
- `CRYPT32!CertFreeCertificateContext` at `0x180059dd8`
- `CRYPT32!CertFreeCertificateContext` at `0x180059d95`
- `CRYPT32!CertFreeCertificateContext` at `0x180059dd8`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180059d37`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x180059d37`
- `CRYPT32!CertOpenStore` at `0x180059c6e`
- `CRYPT32!CertOpenStore` at `0x180059c6e`
- `ncrypt!NCryptFreeObject` at `0x180059db8`
- `ncrypt!NCryptFreeObject` at `0x180059db8`
- `CRYPTSP!CryptReleaseContext` at `0x180059dc8`
- `CRYPTSP!CryptReleaseContext` at `0x180059dc8`

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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, LastError);
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
0x180059c18  mov     [rsp-18h+arg_0], rbx
0x180059c1d  mov     [rsp-18h+arg_8], rsi
0x180059c22  push    rbp
0x180059c23  push    rdi
0x180059c24  push    r14
0x180059c26  mov     rbp, rsp
0x180059c29  sub     rsp, 50h
0x180059c2d  xor     r8d, r8d; hCryptProv
0x180059c30  mov     [rbp+phCryptProvOrNCryptKey], 0
0x180059c38  mov     rbx, rdx
0x180059c3b  mov     [rbp+pfCallerFreeProvOrNCryptKey], 0
0x180059c42  mov     rdi, rcx
0x180059c45  mov     [rbp+pdwKeySpec], 0
0x180059c4c  xorps   xmm0, xmm0
0x180059c4f  lea     rax, aMy; "MY"
0x180059c56  lea     esi, [r8+1]
0x180059c5a  mov     [rsp+50h+pvPara], rax; pvPara
0x180059c5f  mov     edx, esi; dwEncodingType
0x180059c61  lea     ecx, [rsi+8]; lpszStoreProvider
0x180059c64  mov     r9d, 18000h; dwFlags
0x180059c6a  movups  [rbp+pvFindPara], xmm0
0x180059c6e  call    cs:__imp_CertOpenStore
0x180059c75  nop     dword ptr [rax+rax+00h]
0x180059c7a  mov     r14, rax
0x180059c7d  test    rax, rax
0x180059c80  jnz     short loc_180059CAC
0x180059c82  xor     edi, edi
0x180059c84  lea     rcx, WPP_GLOBAL_Control
0x180059c8b  cmp     cs:WPP_GLOBAL_Control, rcx
0x180059c92  jz      loc_180059D82
0x180059c98  call    cs:__imp_GetLastError
0x180059c9f  nop     dword ptr [rax+rax+00h]
0x180059ca4  lea     edx, [rsi+6Bh]
0x180059ca7  jmp     loc_180059D68
0x180059cac  mov     rcx, [rdi+238h]
0x180059cb3  mov     r9d, 10000h; dwFindType
0x180059cb9  mov     [rsp+50h+pPrevCertContext], 0; pPrevCertContext
0x180059cc2  xor     r8d, r8d; dwFindFlags
0x180059cc5  mov     edx, esi; dwCertEncodingType
0x180059cc7  mov     eax, [rcx+10h]
0x180059cca  mov     dword ptr [rbp+pvFindPara], eax
0x180059ccd  lea     rax, [rcx+14h]
0x180059cd1  mov     qword ptr [rbp+pvFindPara+8], rax
0x180059cd5  mov     rcx, r14; hCertStore
0x180059cd8  lea     rax, [rbp+pvFindPara]
0x180059cdc  mov     [rsp+50h+pvPara], rax; pvFindPara
0x180059ce1  call    cs:__imp_CertFindCertificateInStore
0x180059ce8  nop     dword ptr [rax+rax+00h]
0x180059ced  mov     rdi, rax
0x180059cf0  test    rax, rax
0x180059cf3  jnz     short loc_180059D16
0x180059cf5  lea     rcx, WPP_GLOBAL_Control
0x180059cfc  cmp     cs:WPP_GLOBAL_Control, rcx
0x180059d03  jz      short loc_180059D82
0x180059d05  call    cs:__imp_GetLastError
0x180059d0c  nop     dword ptr [rax+rax+00h]
0x180059d11  lea     edx, [rdi+6Dh]
0x180059d14  jmp     short loc_180059D68
0x180059d16  lea     rax, [rbp+pfCallerFreeProvOrNCryptKey]
0x180059d1a  xor     r8d, r8d; pvParameters
0x180059d1d  mov     [rsp+50h+pPrevCertContext], rax; pfCallerFreeProvOrNCryptKey
0x180059d22  lea     r9, [rbp+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x180059d26  lea     rax, [rbp+pdwKeySpec]
0x180059d2a  mov     edx, 40008h; dwFlags
0x180059d2f  mov     rcx, rdi; pCert
0x180059d32  mov     [rsp+50h+pvPara], rax; pdwKeySpec
0x180059d37  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x180059d3e  nop     dword ptr [rax+rax+00h]
0x180059d43  test    eax, eax
0x180059d45  jnz     short loc_180059DA8
0x180059d47  lea     rcx, WPP_GLOBAL_Control
0x180059d4e  cmp     cs:WPP_GLOBAL_Control, rcx
0x180059d55  jz      short loc_180059D82
0x180059d57  call    cs:__imp_GetLastError
0x180059d5e  nop     dword ptr [rax+rax+00h]
0x180059d63  mov     edx, 6Eh ; 'n'
0x180059d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d6f  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180059d76  mov     r9d, eax
0x180059d79  mov     rcx, [rcx+10h]
0x180059d7d  call    WPP_SF_d
0x180059d82  mov     rcx, rbx; hMem
0x180059d85  xor     sil, sil
0x180059d88  call    ?RemoveNodeFromCachedCredList@@YAKPEAU_EAPTLS_CACHED_CREDS@@@Z; RemoveNodeFromCachedCredList(_EAPTLS_CACHED_CREDS *)
0x180059d8d  test    rdi, rdi
0x180059d90  jz      short loc_180059DA1
0x180059d92  mov     rcx, rdi; pCertContext
0x180059d95  call    cs:__imp_CertFreeCertificateContext
0x180059d9c  nop     dword ptr [rax+rax+00h]
0x180059da1  test    r14, r14
0x180059da4  jz      short loc_180059E0D
0x180059da6  jmp     short loc_180059DFC
0x180059da8  cmp     dword ptr [rbx+4Ch], 0
0x180059dac  jz      short loc_180059DD4
0x180059dae  cmp     dword ptr [rbx+48h], 0FFFFFFFFh
0x180059db2  mov     rcx, [rbx+40h]; hProv
0x180059db6  jnz     short loc_180059DC6
0x180059db8  call    cs:__imp_NCryptFreeObject
0x180059dbf  nop     dword ptr [rax+rax+00h]
0x180059dc4  jmp     short loc_180059DD4
0x180059dc6  xor     edx, edx; dwFlags
0x180059dc8  call    cs:__imp_CryptReleaseContext
0x180059dcf  nop     dword ptr [rax+rax+00h]
0x180059dd4  mov     rcx, [rbx+38h]; pCertContext
0x180059dd8  call    cs:__imp_CertFreeCertificateContext
0x180059ddf  nop     dword ptr [rax+rax+00h]
0x180059de4  mov     eax, [rbp+pfCallerFreeProvOrNCryptKey]
0x180059de7  mov     [rbx+4Ch], eax
0x180059dea  mov     eax, [rbp+pdwKeySpec]
0x180059ded  mov     [rbx+48h], eax
0x180059df0  mov     rax, [rbp+phCryptProvOrNCryptKey]
0x180059df4  mov     [rbx+40h], rax
0x180059df8  mov     [rbx+38h], rdi
0x180059dfc  xor     edx, edx; dwFlags
0x180059dfe  mov     rcx, r14; hCertStore
0x180059e01  call    cs:__imp_CertCloseStore
0x180059e08  nop     dword ptr [rax+rax+00h]
0x180059e0d  mov     rbx, [rsp+50h+arg_0]
0x180059e12  movzx   eax, sil
0x180059e16  mov     rsi, [rsp+50h+arg_8]
0x180059e1b  add     rsp, 50h
0x180059e1f  pop     r14
0x180059e21  pop     rdi
0x180059e22  pop     rbp
0x180059e23  retn
```
