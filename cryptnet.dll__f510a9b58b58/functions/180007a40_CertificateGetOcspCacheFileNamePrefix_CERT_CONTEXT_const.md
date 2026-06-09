# CertificateGetOcspCacheFileNamePrefix(_CERT_CONTEXT const *)

- ea: `0x180007a40`
- end: `0x180007bf0`
- name: `?CertificateGetOcspCacheFileNamePrefix@@YAPEAGPEBU_CERT_CONTEXT@@@Z`
- size: `432`
- prototype: `unsigned __int16 *__fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `4`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005f10`
- `0x180009e30`
- `0x18000c300`
- `0x18001e524`

## callees

- `0x180007a40`
- `0x180016310`
- `0x18001fa58`
- `0x18001fa9c`
- `0x18001fae4`
- `0x180026552`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007be5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007be5`
- `CRYPT32!CertFindExtension` at `0x180007b35`
- `CRYPT32!CertFindExtension` at `0x180007b35`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180007a89`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180007a89`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180007bc9`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180007bc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007aec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007aec`

## pseudocode

```c
unsigned __int16 *__fastcall CertificateGetOcspCacheFileNamePrefix(PCCERT_CONTEXT pCertContext)
{
  __int64 v2; // rbx
  HLOCAL v3; // rdi
  SIZE_T v5; // rbx
  HLOCAL v6; // rax
  PCERT_EXTENSION Extension; // rax
  PCERT_EXTENSION v8; // rbx
  __int64 v9; // rcx
  DWORD pcbData; // [rsp+20h] [rbp-98h] BYREF
  __int128 v11; // [rsp+28h] [rbp-90h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+38h] [rbp-80h] BYREF
  __int64 v13; // [rsp+48h] [rbp-70h]
  _WORD pvData[32]; // [rsp+50h] [rbp-68h] BYREF
  int v15; // [rsp+90h] [rbp-28h]

  pcbData = 68;
  v11 = 0;
  if ( !CertGetCertificateContextProperty(pCertContext, 0x4Bu, pvData, &pcbData) )
    goto LABEL_11;
  v2 = pcbData >> 1;
  if ( (_DWORD)v2 == 1 )
  {
    v3 = 0;
    if ( !pvData[0] )
      goto LABEL_5;
    goto LABEL_12;
  }
  if ( (_DWORD)v2 == 34 )
  {
    v3 = 0;
    if ( !HIWORD(v15) )
      goto LABEL_5;
  }
  else
  {
LABEL_11:
    v3 = 0;
  }
LABEL_12:
  Extension = CertFindExtension("2.5.29.31", pCertContext->pCertInfo->cExtension, pCertContext->pCertInfo->rgExtension);
  v8 = Extension;
  if ( Extension && Extension->Value.cbData )
  {
    *(_OWORD *)phHash = 0;
    v13 = 0;
    CngRsa32Compat_MD5Init(phHash);
    CngRsa32Compat_MD5Update(phHash, v8->Value.pbData, v8->Value.cbData);
    CngRsa32Compat_MD5Final(phHash);
    I_UrlCacheBytesToWStr(v9, &phHash[1], pvData);
    v15 = 95;
    v2 = 34;
  }
  else
  {
    pvData[0] = 0;
    v2 = 1;
  }
  *((_QWORD *)&v11 + 1) = pvData;
  LODWORD(v11) = 2 * v2;
  CertSetCertificateContextProperty(pCertContext, 0x4Bu, 0x80000000, &v11);
LABEL_5:
  if ( (unsigned int)v2 > 1 )
  {
    v5 = 2 * v2;
    v6 = LocalAlloc(0, v5);
    v3 = v6;
    if ( v6 )
      memcpy_0(v6, pvData, v5);
    else
      SetLastError(0x8007000E);
  }
  return (unsigned __int16 *)v3;
}

```

## disassembly

```asm
0x180007a40  mov     [rsp+arg_10], rbx
0x180007a45  push    rdi
0x180007a46  sub     rsp, 0B0h
0x180007a4d  mov     rax, cs:__security_cookie
0x180007a54  xor     rax, rsp
0x180007a57  mov     [rsp+0B8h+var_18], rax
0x180007a5f  xorps   xmm0, xmm0
0x180007a62  mov     [rsp+0B8h+arg_8], rsi
0x180007a6a  lea     r9, [rsp+0B8h+pcbData]; pcbData
0x180007a6f  mov     [rsp+0B8h+pcbData], 44h ; 'D'
0x180007a77  lea     r8, [rsp+0B8h+pvData]; pvData
0x180007a7c  mov     edx, 4Bh ; 'K'; dwPropId
0x180007a81  movups  [rsp+0B8h+var_90], xmm0
0x180007a86  mov     rsi, rcx
0x180007a89  call    cs:__imp_CertGetCertificateContextProperty
0x180007a8f  test    eax, eax
0x180007a91  jz      loc_180007B1B
0x180007a97  mov     ebx, [rsp+0B8h+pcbData]
0x180007a9b  shr     ebx, 1
0x180007a9d  cmp     ebx, 1
0x180007aa0  jz      short loc_180007B10
0x180007aa2  cmp     ebx, 22h ; '"'
0x180007aa5  jnz     short loc_180007B1B
0x180007aa7  xor     edi, edi
0x180007aa9  cmp     di, [rsp+0B8h+var_26]
0x180007ab1  jnz     short loc_180007B1D
0x180007ab3  mov     rsi, [rsp+0B8h+arg_8]
0x180007abb  cmp     ebx, 1
0x180007abe  ja      short loc_180007AE4
0x180007ac0  mov     rax, rdi
0x180007ac3  mov     rcx, [rsp+0B8h+var_18]
0x180007acb  xor     rcx, rsp; StackCookie
0x180007ace  call    __security_check_cookie
0x180007ad3  mov     rbx, [rsp+0B8h+arg_10]
0x180007adb  add     rsp, 0B0h
0x180007ae2  pop     rdi
0x180007ae3  retn
0x180007ae4  add     rbx, rbx
0x180007ae7  xor     ecx, ecx; uFlags
0x180007ae9  mov     rdx, rbx; uBytes
0x180007aec  call    cs:__imp_LocalAlloc
0x180007af2  mov     rdi, rax
0x180007af5  test    rax, rax
0x180007af8  jz      loc_180007BE0
0x180007afe  mov     r8, rbx; Size
0x180007b01  lea     rdx, [rsp+0B8h+pvData]; Src
0x180007b06  mov     rcx, rax; void *
0x180007b09  call    memcpy_0
0x180007b0e  jmp     short loc_180007AC0
0x180007b10  xor     edi, edi
0x180007b12  cmp     di, [rsp+0B8h+pvData]
0x180007b17  jz      short loc_180007AB3
0x180007b19  jmp     short loc_180007B1D
0x180007b1b  xor     edi, edi
0x180007b1d  mov     rdx, [rsi+18h]
0x180007b21  lea     rcx, pszObjId; "2.5.29.31"
0x180007b28  mov     r8, [rdx+0C8h]; rgExtensions
0x180007b2f  mov     edx, [rdx+0C0h]; cExtensions
0x180007b35  call    cs:__imp_CertFindExtension
0x180007b3b  mov     rbx, rax
0x180007b3e  test    rax, rax
0x180007b41  jz      loc_180007BD4
0x180007b47  cmp     dword ptr [rax+10h], 0
0x180007b4b  jz      loc_180007BD4
0x180007b51  xorps   xmm0, xmm0
0x180007b54  lea     rcx, [rsp+0B8h+phHash]; phHash
0x180007b59  xor     eax, eax
0x180007b5b  movups  xmmword ptr [rsp+0B8h+phHash], xmm0
0x180007b60  mov     [rsp+0B8h+var_70], rax
0x180007b65  call    CngRsa32Compat_MD5Init
0x180007b6a  mov     r8d, [rbx+10h]
0x180007b6e  lea     rcx, [rsp+0B8h+phHash]
0x180007b73  mov     rdx, [rbx+18h]
0x180007b77  call    CngRsa32Compat_MD5Update
0x180007b7c  lea     rcx, [rsp+0B8h+phHash]
0x180007b81  call    CngRsa32Compat_MD5Final
0x180007b86  lea     r8, [rsp+0B8h+pvData]
0x180007b8b  lea     rdx, [rsp+0B8h+phHash+8]
0x180007b90  call    I_UrlCacheBytesToWStr
0x180007b95  mov     dword ptr [rsp+90h], 5Fh ; '_'
0x180007ba0  mov     ebx, 22h ; '"'
0x180007ba5  lea     rax, [rsp+0B8h+pvData]
0x180007baa  mov     edx, 4Bh ; 'K'; dwPropId
0x180007baf  mov     qword ptr [rsp+0B8h+var_90+8], rax
0x180007bb4  lea     r9, [rsp+0B8h+var_90]; pvData
0x180007bb9  lea     eax, [rbx+rbx]
0x180007bbc  mov     r8d, 80000000h; dwFlags
0x180007bc2  mov     rcx, rsi; pCertContext
0x180007bc5  mov     dword ptr [rsp+0B8h+var_90], eax
0x180007bc9  call    cs:__imp_CertSetCertificateContextProperty
0x180007bcf  jmp     loc_180007AB3
0x180007bd4  mov     [rsp+0B8h+pvData], di
0x180007bd9  mov     ebx, 1
0x180007bde  jmp     short loc_180007BA5
0x180007be0  mov     ecx, 8007000Eh; dwErrCode
0x180007be5  call    cs:__imp_SetLastError
0x180007beb  jmp     loc_180007AC0
```
