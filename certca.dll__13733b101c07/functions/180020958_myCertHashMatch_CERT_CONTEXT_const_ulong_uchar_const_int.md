# myCertHashMatch(_CERT_CONTEXT const *,ulong,uchar const *,int *)

- ea: `0x180020958`
- end: `0x180020bb5`
- name: `?myCertHashMatch@@YAJPEBU_CERT_CONTEXT@@KPEBEPEAH@Z`
- size: `605`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext, size_t Size, const unsigned __int8 *Buf2, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001f61c`

## callees

- `0x180008400`
- `0x180012450`
- `0x18001e080`
- `0x180020958`
- `0x180038256`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020b89`
- `CRYPT32!CryptHashCertificate` at `0x180020ae3`
- `CRYPT32!CryptHashCertificate` at `0x180020ae3`
- `CRYPT32!CertFindExtension` at `0x180020a43`
- `CRYPT32!CertFindExtension` at `0x180020a43`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180020b47`
- `CRYPT32!CryptHashPublicKeyInfo` at `0x180020b47`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800209a2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800209f6`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800209a2`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800209f6`

## pseudocode

```c
__int64 __fastcall myCertHashMatch(PCCERT_CONTEXT pCertContext, size_t Size, const unsigned __int8 *Buf2, int *a4)
{
  int v4; // edi
  size_t v5; // rsi
  int v9; // eax
  unsigned int v10; // ecx
  unsigned int v11; // ebx
  int v12; // eax
  PCERT_EXTENSION Extension; // rax
  PCERT_INFO pCertInfo; // r9
  CERT_PUBLIC_KEY_INFO *p_SubjectPublicKeyInfo; // rax
  HLOCAL v16; // rcx
  DWORD pcbData[2]; // [rsp+40h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-28h]
  BYTE pvData[24]; // [rsp+50h] [rbp-20h] BYREF

  v4 = 0;
  v5 = (unsigned int)Size;
  pcbData[1] = 0;
  hMem = 0;
  pcbData[0] = 20;
  if ( !CertGetCertificateContextProperty(pCertContext, 3u, pvData, pcbData) )
  {
    v9 = myHLastError();
    v10 = 61276571;
LABEL_3:
    v11 = v9;
    CSPrintErrorLineFile(v10, v9);
    goto LABEL_26;
  }
  if ( pcbData[0] == (_DWORD)v5 && !memcmp_0(pvData, Buf2, v5) )
    goto LABEL_6;
  pcbData[0] = 20;
  if ( CertGetCertificateContextProperty(pCertContext, 0x14u, pvData, pcbData) )
  {
    if ( pcbData[0] == (_DWORD)v5 && !memcmp_0(pvData, Buf2, v5) )
    {
LABEL_6:
      v4 = 1;
      goto LABEL_25;
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
    if ( !(unsigned int)myDecodeObjectEx(1, 25, Extension->Value.pbData, Extension->Value.cbData, 0) )
    {
      v9 = myHLastError();
      v10 = 64553371;
      goto LABEL_3;
    }
    if ( *(_DWORD *)hMem == (_DWORD)v5 && !memcmp_0(*((const void **)hMem + 1), Buf2, v5) )
      goto LABEL_24;
  }
  pCertInfo = pCertContext->pCertInfo;
  pcbData[0] = 20;
  if ( !CryptHashCertificate(
          0,
          0x8004u,
          0,
          pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
          pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
          pvData,
          pcbData) )
  {
    v9 = myHLastError();
    v10 = 65929627;
    goto LABEL_3;
  }
  if ( pcbData[0] == (_DWORD)v5 && !memcmp_0(pvData, Buf2, v5) )
    goto LABEL_24;
  p_SubjectPublicKeyInfo = &pCertContext->pCertInfo->SubjectPublicKeyInfo;
  pcbData[0] = 20;
  if ( !CryptHashPublicKeyInfo(0, 0x8004u, 0, 1u, p_SubjectPublicKeyInfo, pvData, pcbData) )
  {
    v9 = myHLastError();
    v10 = 67305883;
    goto LABEL_3;
  }
  if ( pcbData[0] == (_DWORD)v5 && !memcmp_0(pvData, Buf2, v5) )
LABEL_24:
    v4 = 1;
LABEL_25:
  v11 = 0;
LABEL_26:
  v16 = hMem;
  *a4 = v4;
  if ( v16 )
    LocalFree(v16);
  return v11;
}

```

## disassembly

```asm
0x180020958  mov     [rsp-38h+arg_8], rbx
0x18002095d  push    rbp
0x18002095e  push    rsi
0x18002095f  push    rdi
0x180020960  push    r12
0x180020962  push    r13
0x180020964  push    r14
0x180020966  push    r15
0x180020968  mov     rbp, rsp
0x18002096b  sub     rsp, 70h
0x18002096f  mov     rax, cs:__security_cookie
0x180020976  xor     rax, rsp
0x180020979  mov     [rbp+var_8], rax
0x18002097d  xor     edi, edi
0x18002097f  mov     esi, edx
0x180020981  mov     r12, r9
0x180020984  mov     [rbp+var_2C], edi
0x180020987  mov     r15, r8
0x18002098a  mov     [rbp+hMem], rdi
0x18002098e  lea     r9, [rbp+pcbData]; pcbData
0x180020992  mov     r13, rcx
0x180020995  lea     ebx, [rdi+14h]
0x180020998  lea     r8, [rbp+pvData]; pvData
0x18002099c  mov     [rbp+pcbData], ebx
0x18002099f  lea     edx, [rdi+3]; dwPropId
0x1800209a2  call    cs:__imp_CertGetCertificateContextProperty
0x1800209a8  test    eax, eax
0x1800209aa  jnz     short loc_1800209C4
0x1800209ac  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800209b1  mov     ecx, 3A7019Bh; unsigned int
0x1800209b6  mov     edx, eax; int
0x1800209b8  mov     ebx, eax
0x1800209ba  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800209bf  jmp     loc_180020B7C
0x1800209c4  cmp     [rbp+pcbData], esi
0x1800209c7  jnz     short loc_1800209E6
0x1800209c9  mov     r8, rsi; Size
0x1800209cc  lea     rcx, [rbp+pvData]; Buf1
0x1800209d0  mov     rdx, r15; Buf2
0x1800209d3  call    memcmp_0
0x1800209d8  test    eax, eax
0x1800209da  jnz     short loc_1800209E6
0x1800209dc  mov     edi, 1
0x1800209e1  jmp     loc_180020B7A
0x1800209e6  lea     r9, [rbp+pcbData]; pcbData
0x1800209ea  mov     [rbp+pcbData], ebx
0x1800209ed  lea     r8, [rbp+pvData]; pvData
0x1800209f1  mov     edx, ebx; dwPropId
0x1800209f3  mov     rcx, r13; pCertContext
0x1800209f6  call    cs:__imp_CertGetCertificateContextProperty
0x1800209fc  test    eax, eax
0x1800209fe  jnz     short loc_180020A13
0x180020a00  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180020a05  mov     edx, eax; int
0x180020a07  mov     ecx, 3BA019Bh; unsigned int
0x180020a0c  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180020a11  jmp     short loc_180020A2B
0x180020a13  cmp     [rbp+pcbData], esi
0x180020a16  jnz     short loc_180020A2B
0x180020a18  mov     r8, rsi; Size
0x180020a1b  lea     rcx, [rbp+pvData]; Buf1
0x180020a1f  mov     rdx, r15; Buf2
0x180020a22  call    memcmp_0
0x180020a27  test    eax, eax
0x180020a29  jz      short loc_1800209DC
0x180020a2b  mov     rdx, [r13+18h]
0x180020a2f  lea     rcx, a252914; "2.5.29.14"
0x180020a36  mov     r8, [rdx+0C8h]; rgExtensions
0x180020a3d  mov     edx, [rdx+0C0h]; cExtensions
0x180020a43  call    cs:__imp_CertFindExtension
0x180020a49  mov     ebx, 1
0x180020a4e  test    rax, rax
0x180020a51  jz      short loc_180020AAD
0x180020a53  mov     r9d, [rax+10h]
0x180020a57  lea     rcx, [rbp+var_2C]
0x180020a5b  mov     r8, [rax+18h]
0x180020a5f  lea     edx, [rbx+18h]
0x180020a62  mov     [rsp+70h+var_38], rcx
0x180020a67  lea     rcx, [rbp+hMem]
0x180020a6b  mov     [rsp+70h+pcbComputedHash], rcx
0x180020a70  mov     ecx, ebx
0x180020a72  mov     [rsp+70h+cbEncoded], edi
0x180020a76  call    ?myDecodeObjectEx@@YAHKPEBDPEBEKKW4CERTLIB_ALLOCATOR@@PEAPEAXPEAK@Z; myDecodeObjectEx(ulong,char const *,uchar const *,ulong,ulong,CERTLIB_ALLOCATOR,void * *,ulong *)
0x180020a7b  test    eax, eax
0x180020a7d  jnz     short loc_180020A8E
0x180020a7f  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180020a84  mov     ecx, 3D9019Bh
0x180020a89  jmp     loc_1800209B6
0x180020a8e  mov     rcx, [rbp+hMem]
0x180020a92  cmp     [rcx], esi
0x180020a94  jnz     short loc_180020AAD
0x180020a96  mov     rcx, [rcx+8]; Buf1
0x180020a9a  mov     r8, rsi; Size
0x180020a9d  mov     rdx, r15; Buf2
0x180020aa0  call    memcmp_0
0x180020aa5  test    eax, eax
0x180020aa7  jz      loc_180020B78
0x180020aad  mov     r9, [r13+18h]
0x180020ab1  lea     rax, [rbp+pcbData]
0x180020ab5  mov     [rsp+70h+pcbComputedHash], rax; pcbComputedHash
0x180020aba  xor     r8d, r8d; dwFlags
0x180020abd  lea     rax, [rbp+pvData]
0x180020ac1  mov     [rbp+pcbData], 14h
0x180020ac8  mov     [rsp+70h+pbComputedHash], rax; pbComputedHash
0x180020acd  mov     edx, 8004h; Algid
0x180020ad2  mov     eax, [r9+78h]
0x180020ad6  xor     ecx, ecx; hCryptProv
0x180020ad8  mov     r9, [r9+80h]; pbEncoded
0x180020adf  mov     [rsp+70h+cbEncoded], eax; cbEncoded
0x180020ae3  call    cs:__imp_CryptHashCertificate
0x180020ae9  test    eax, eax
0x180020aeb  jnz     short loc_180020AFC
0x180020aed  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180020af2  mov     ecx, 3EE019Bh
0x180020af7  jmp     loc_1800209B6
0x180020afc  cmp     [rbp+pcbData], esi
0x180020aff  jnz     short loc_180020B14
0x180020b01  mov     r8, rsi; Size
0x180020b04  lea     rcx, [rbp+pvData]; Buf1
0x180020b08  mov     rdx, r15; Buf2
0x180020b0b  call    memcmp_0
0x180020b10  test    eax, eax
0x180020b12  jz      short loc_180020B78
0x180020b14  mov     rax, [r13+18h]
0x180020b18  lea     rcx, [rbp+pcbData]
0x180020b1c  mov     [rsp+70h+pcbComputedHash], rcx; pcbComputedHash
0x180020b21  add     rax, 60h ; '`'
0x180020b25  lea     rcx, [rbp+pvData]
0x180020b29  mov     [rbp+pcbData], 14h
0x180020b30  mov     [rsp+70h+pbComputedHash], rcx; pbComputedHash
0x180020b35  mov     r9d, ebx; dwCertEncodingType
0x180020b38  xor     ecx, ecx; hCryptProv
0x180020b3a  mov     qword ptr [rsp+70h+cbEncoded], rax; pInfo
0x180020b3f  xor     r8d, r8d; dwFlags
0x180020b42  mov     edx, 8004h; Algid
0x180020b47  call    cs:__imp_CryptHashPublicKeyInfo
0x180020b4d  test    eax, eax
0x180020b4f  jnz     short loc_180020B60
0x180020b51  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180020b56  mov     ecx, 403019Bh
0x180020b5b  jmp     loc_1800209B6
0x180020b60  cmp     [rbp+pcbData], esi
0x180020b63  jnz     short loc_180020B7A
0x180020b65  mov     r8, rsi; Size
0x180020b68  lea     rcx, [rbp+pvData]; Buf1
0x180020b6c  mov     rdx, r15; Buf2
0x180020b6f  call    memcmp_0
0x180020b74  test    eax, eax
0x180020b76  jnz     short loc_180020B7A
0x180020b78  mov     edi, ebx
0x180020b7a  xor     ebx, ebx
0x180020b7c  mov     rcx, [rbp+hMem]; hMem
0x180020b80  mov     [r12], edi
0x180020b84  test    rcx, rcx
0x180020b87  jz      short loc_180020B8F
0x180020b89  call    cs:__imp_LocalFree
0x180020b8f  mov     eax, ebx
0x180020b91  mov     rcx, [rbp+var_8]
0x180020b95  xor     rcx, rsp; StackCookie
0x180020b98  call    __security_check_cookie
0x180020b9d  mov     rbx, [rsp+70h+arg_8]
0x180020ba5  add     rsp, 70h
0x180020ba9  pop     r15
0x180020bab  pop     r14
0x180020bad  pop     r13
0x180020baf  pop     r12
0x180020bb1  pop     rdi
0x180020bb2  pop     rsi
0x180020bb3  pop     rbp
0x180020bb4  retn
```
