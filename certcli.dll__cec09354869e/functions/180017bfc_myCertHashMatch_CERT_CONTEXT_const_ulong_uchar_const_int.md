# myCertHashMatch(_CERT_CONTEXT const *,ulong,uchar const *,int *)

- ea: `0x180017bfc`
- end: `0x180017e63`
- name: `?myCertHashMatch@@YAJPEBU_CERT_CONTEXT@@KPEBEPEAH@Z`
- size: `615`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, size_t Size, const unsigned __int8 *Buf2, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800168e8`

## callees

- `0x180017bfc`
- `0x180020834`
- `0x180021438`
- `0x1800396e6`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017e36`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180017df1`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180017df1`
- `CRYPT32!CryptHashCertificate` at `0x180017d8a`
- `CRYPT32!CryptHashCertificate` at `0x180017d8a`
- `CRYPT32!CertFindExtension` at `0x180017cef`
- `CRYPT32!CertFindExtension` at `0x180017cef`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180017c49`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180017c9d`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180017c49`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180017c9d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180017c61`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180017cb3`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180017c61`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180017cb3`

## pseudocode

```c
__int64 __fastcall myCertHashMatch(PCCERT_CONTEXT pCertContext, size_t Size, const unsigned __int8 *Buf2, int *a4)
{
  int v4; // edi
  size_t v5; // rbx
  unsigned int v9; // eax
  unsigned int v10; // ecx
  unsigned int v11; // ebx
  int v12; // eax
  PCERT_EXTENSION Extension; // rax
  PCERT_INFO pCertInfo; // r9
  CERT_PUBLIC_KEY_INFO *p_SubjectPublicKeyInfo; // rax
  HLOCAL v16; // rcx
  BYTE *pbComputedHash; // [rsp+28h] [rbp-48h]
  DWORD pcbData; // [rsp+40h] [rbp-30h] BYREF
  DWORD v20; // [rsp+44h] [rbp-2Ch] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-28h] BYREF
  BYTE pvData[24]; // [rsp+50h] [rbp-20h] BYREF

  v4 = 0;
  v5 = (unsigned int)Size;
  v20 = 0;
  hMem = 0;
  pcbData = 20;
  if ( !CertGetCertificateContextProperty(pCertContext, 3u, pvData, &pcbData) )
  {
    v9 = myHLastError();
    v10 = 61276571;
LABEL_3:
    v11 = v9;
    CSPrintErrorLineFile(v10, v9);
    goto LABEL_25;
  }
  if ( pcbData == (_DWORD)v5 && !memcmp_0(pvData, Buf2, v5) )
    goto LABEL_23;
  pcbData = 20;
  if ( CertGetCertificateContextProperty(pCertContext, 0x14u, pvData, &pcbData) )
  {
    if ( pcbData == (_DWORD)v5 && !memcmp_0(pvData, Buf2, v5) )
    {
LABEL_23:
      v4 = 1;
      goto LABEL_24;
    }
  }
  else
  {
    v12 = myHLastError();
    CSPrintErrorLineFile(0x3BA019Bu, v12);
  }
  Extension = CertFindExtension("2.5.29.14", pCertContext->pCertInfo->cExtension, pCertContext->pCertInfo->rgExtension);
  if ( Extension )
  {
    if ( !myDecodeObjectEx(
            (__int64)&hMem,
            (const CHAR *)0x19,
            Extension->Value.pbData,
            Extension->Value.cbData,
            0,
            (__int64)pbComputedHash,
            &hMem,
            &v20) )
    {
      v9 = myHLastError();
      v10 = 64553371;
      goto LABEL_3;
    }
    if ( *(_DWORD *)hMem == (_DWORD)v5 && !memcmp_0(*((const void **)hMem + 1), Buf2, v5) )
      goto LABEL_23;
  }
  pCertInfo = pCertContext->pCertInfo;
  pcbData = 20;
  if ( !CryptHashCertificate(
          0,
          0x8004u,
          0,
          pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
          pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
          pvData,
          &pcbData) )
  {
    v9 = myHLastError();
    v10 = 65929627;
    goto LABEL_3;
  }
  if ( pcbData == (_DWORD)v5 && !memcmp_0(pvData, Buf2, v5) )
    goto LABEL_23;
  p_SubjectPublicKeyInfo = &pCertContext->pCertInfo->SubjectPublicKeyInfo;
  pcbData = 20;
  if ( !CryptHashPublicKeyInfo(0, 0x8004u, 0, 1u, p_SubjectPublicKeyInfo, pvData, &pcbData) )
  {
    v9 = myHLastError();
    v10 = 67305883;
    goto LABEL_3;
  }
  if ( pcbData == (_DWORD)v5 && !memcmp_0(pvData, Buf2, v5) )
    goto LABEL_23;
LABEL_24:
  v11 = 0;
LABEL_25:
  v16 = hMem;
  *a4 = v4;
  if ( v16 )
    LocalFree(v16);
  return v11;
}

```

## disassembly

```asm
0x180017bfc  mov     [rsp-28h+arg_8], rbx
0x180017c01  mov     [rsp-28h+arg_10], rsi
0x180017c06  push    rbp
0x180017c07  push    rdi
0x180017c08  push    r12
0x180017c0a  push    r14
0x180017c0c  push    r15
0x180017c0e  mov     rbp, rsp
0x180017c11  sub     rsp, 70h
0x180017c15  mov     rax, cs:__security_cookie
0x180017c1c  xor     rax, rsp
0x180017c1f  mov     [rbp+var_8], rax
0x180017c23  xor     edi, edi
0x180017c25  mov     ebx, edx
0x180017c27  mov     r12, r9
0x180017c2a  mov     [rbp+var_2C], edi
0x180017c2d  mov     r14, r8
0x180017c30  mov     [rbp+hMem], rdi
0x180017c34  lea     r9, [rbp+pcbData]; pcbData
0x180017c38  mov     [rbp+pcbData], 14h
0x180017c3f  lea     edx, [rdi+3]; dwPropId
0x180017c42  mov     r15, rcx
0x180017c45  lea     r8, [rbp+pvData]; pvData
0x180017c49  call    cs:__imp_CertGetCertificateContextProperty
0x180017c4f  test    eax, eax
0x180017c51  jnz     short loc_180017C6C
0x180017c53  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017c58  mov     ecx, 3A7019Bh
0x180017c5d  mov     edx, eax
0x180017c5f  mov     ebx, eax
0x180017c61  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180017c67  jmp     loc_180017E29
0x180017c6c  cmp     [rbp+pcbData], ebx
0x180017c6f  jnz     short loc_180017C88
0x180017c71  mov     r8, rbx; Size
0x180017c74  lea     rcx, [rbp+pvData]; Buf1
0x180017c78  mov     rdx, r14; Buf2
0x180017c7b  call    memcmp_0
0x180017c80  test    eax, eax
0x180017c82  jz      loc_180017E22
0x180017c88  mov     eax, 14h
0x180017c8d  lea     r9, [rbp+pcbData]; pcbData
0x180017c91  mov     edx, eax; dwPropId
0x180017c93  mov     [rbp+pcbData], eax
0x180017c96  lea     r8, [rbp+pvData]; pvData
0x180017c9a  mov     rcx, r15; pCertContext
0x180017c9d  call    cs:__imp_CertGetCertificateContextProperty
0x180017ca3  test    eax, eax
0x180017ca5  jnz     short loc_180017CBB
0x180017ca7  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017cac  mov     edx, eax
0x180017cae  mov     ecx, 3BA019Bh
0x180017cb3  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180017cb9  jmp     short loc_180017CD7
0x180017cbb  cmp     [rbp+pcbData], ebx
0x180017cbe  jnz     short loc_180017CD7
0x180017cc0  mov     r8, rbx; Size
0x180017cc3  lea     rcx, [rbp+pvData]; Buf1
0x180017cc7  mov     rdx, r14; Buf2
0x180017cca  call    memcmp_0
0x180017ccf  test    eax, eax
0x180017cd1  jz      loc_180017E22
0x180017cd7  mov     rdx, [r15+18h]
0x180017cdb  lea     rcx, a252914; "2.5.29.14"
0x180017ce2  mov     r8, [rdx+0C8h]; rgExtensions
0x180017ce9  mov     edx, [rdx+0C0h]; cExtensions
0x180017cef  call    cs:__imp_CertFindExtension
0x180017cf5  test    rax, rax
0x180017cf8  jz      short loc_180017D54
0x180017cfa  mov     r9d, [rax+10h]
0x180017cfe  lea     rcx, [rbp+var_2C]
0x180017d02  mov     r8, [rax+18h]
0x180017d06  mov     edx, 19h
0x180017d0b  mov     [rsp+70h+var_38], rcx
0x180017d10  lea     rcx, [rbp+hMem]
0x180017d14  mov     [rsp+70h+pcbComputedHash], rcx
0x180017d19  mov     [rsp+70h+cbEncoded], edi
0x180017d1d  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x180017d22  test    eax, eax
0x180017d24  jnz     short loc_180017D35
0x180017d26  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017d2b  mov     ecx, 3D9019Bh
0x180017d30  jmp     loc_180017C5D
0x180017d35  mov     rcx, [rbp+hMem]
0x180017d39  cmp     [rcx], ebx
0x180017d3b  jnz     short loc_180017D54
0x180017d3d  mov     rcx, [rcx+8]; Buf1
0x180017d41  mov     r8, rbx; Size
0x180017d44  mov     rdx, r14; Buf2
0x180017d47  call    memcmp_0
0x180017d4c  test    eax, eax
0x180017d4e  jz      loc_180017E22
0x180017d54  mov     r9, [r15+18h]
0x180017d58  lea     rax, [rbp+pcbData]
0x180017d5c  mov     [rsp+70h+pcbComputedHash], rax; pcbComputedHash
0x180017d61  xor     r8d, r8d; dwFlags
0x180017d64  lea     rax, [rbp+pvData]
0x180017d68  mov     [rbp+pcbData], 14h
0x180017d6f  mov     [rsp+70h+pbComputedHash], rax; pbComputedHash
0x180017d74  mov     edx, 8004h; Algid
0x180017d79  mov     eax, [r9+78h]
0x180017d7d  xor     ecx, ecx; hCryptProv
0x180017d7f  mov     r9, [r9+80h]; pbEncoded
0x180017d86  mov     [rsp+70h+cbEncoded], eax; cbEncoded
0x180017d8a  call    cs:__imp_CryptHashCertificate
0x180017d90  test    eax, eax
0x180017d92  jnz     short loc_180017DA3
0x180017d94  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017d99  mov     ecx, 3EE019Bh
0x180017d9e  jmp     loc_180017C5D
0x180017da3  cmp     [rbp+pcbData], ebx
0x180017da6  jnz     short loc_180017DBB
0x180017da8  mov     r8, rbx; Size
0x180017dab  lea     rcx, [rbp+pvData]; Buf1
0x180017daf  mov     rdx, r14; Buf2
0x180017db2  call    memcmp_0
0x180017db7  test    eax, eax
0x180017db9  jz      short loc_180017E22
0x180017dbb  mov     rax, [r15+18h]
0x180017dbf  lea     rcx, [rbp+pcbData]
0x180017dc3  mov     [rsp+70h+pcbComputedHash], rcx; pcbComputedHash
0x180017dc8  add     rax, 60h ; '`'
0x180017dcc  lea     rcx, [rbp+pvData]
0x180017dd0  mov     [rbp+pcbData], 14h
0x180017dd7  mov     [rsp+70h+pbComputedHash], rcx; pbComputedHash
0x180017ddc  mov     r9d, 1; dwCertEncodingType
0x180017de2  xor     ecx, ecx; hCryptProv
0x180017de4  mov     qword ptr [rsp+70h+cbEncoded], rax; pInfo
0x180017de9  xor     r8d, r8d; dwFlags
0x180017dec  mov     edx, 8004h; Algid
0x180017df1  call    cs:__imp_CryptHashPublicKeyInfo
0x180017df7  test    eax, eax
0x180017df9  jnz     short loc_180017E0A
0x180017dfb  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017e00  mov     ecx, 403019Bh
0x180017e05  jmp     loc_180017C5D
0x180017e0a  cmp     [rbp+pcbData], ebx
0x180017e0d  jnz     short loc_180017E27
0x180017e0f  mov     r8, rbx; Size
0x180017e12  lea     rcx, [rbp+pvData]; Buf1
0x180017e16  mov     rdx, r14; Buf2
0x180017e19  call    memcmp_0
0x180017e1e  test    eax, eax
0x180017e20  jnz     short loc_180017E27
0x180017e22  mov     edi, 1
0x180017e27  xor     ebx, ebx
0x180017e29  mov     rcx, [rbp+hMem]; hMem
0x180017e2d  mov     [r12], edi
0x180017e31  test    rcx, rcx
0x180017e34  jz      short loc_180017E3C
0x180017e36  call    cs:__imp_LocalFree
0x180017e3c  mov     eax, ebx
0x180017e3e  mov     rcx, [rbp+var_8]
0x180017e42  xor     rcx, rsp; StackCookie
0x180017e45  call    __security_check_cookie
0x180017e4a  lea     r11, [rsp+70h+var_s0]
0x180017e4f  mov     rbx, [r11+38h]
0x180017e53  mov     rsi, [r11+40h]
0x180017e57  mov     rsp, r11
0x180017e5a  pop     r15
0x180017e5c  pop     r14
0x180017e5e  pop     r12
0x180017e60  pop     rdi
0x180017e61  pop     rbp
0x180017e62  retn
```
