# CertGetOriginIdentifier(_CERT_CONTEXT const *,_CERT_CONTEXT const *,ulong,uchar * const)

- ea: `0x18001a9c8`
- end: `0x18001ab23`
- name: `?CertGetOriginIdentifier@@YAHPEBU_CERT_CONTEXT@@0KQEAE@Z`
- size: `347`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, const struct _CERT_CONTEXT *, __int64, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cfa0`
- `0x180018ff8`

## callees

- `0x18001a9c8`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18001aa2d`
- `bcrypt!BCryptHashData` at `0x18001aa4b`
- `bcrypt!BCryptHashData` at `0x18001aa7d`
- `bcrypt!BCryptHashData` at `0x18001aa97`
- `bcrypt!BCryptHashData` at `0x18001aab4`
- `bcrypt!BCryptHashData` at `0x18001aad1`
- `bcrypt!BCryptHashData` at `0x18001aa2d`
- `bcrypt!BCryptHashData` at `0x18001aa4b`
- `bcrypt!BCryptHashData` at `0x18001aa7d`
- `bcrypt!BCryptHashData` at `0x18001aa97`
- `bcrypt!BCryptHashData` at `0x18001aab4`
- `bcrypt!BCryptHashData` at `0x18001aad1`
- `bcrypt!BCryptDestroyHash` at `0x18001ab08`
- `bcrypt!BCryptDestroyHash` at `0x18001ab08`
- `bcrypt!BCryptFinishHash` at `0x18001aaea`
- `bcrypt!BCryptFinishHash` at `0x18001aaea`
- `bcrypt!BCryptCreateHash` at `0x18001aa0f`
- `bcrypt!BCryptCreateHash` at `0x18001aa0f`

## pseudocode

```c
__int64 __fastcall CertGetOriginIdentifier(
        const struct _CERT_CONTEXT *a1,
        const struct _CERT_CONTEXT *a2,
        __int64 a3,
        unsigned __int8 *const a4)
{
  PCERT_INFO pCertInfo; // rbx
  PCERT_INFO v6; // rdi
  UCHAR *pszObjId; // rdx
  __int64 v8; // r8
  BCRYPT_HASH_HANDLE hHash; // [rsp+50h] [rbp+8h] BYREF

  pCertInfo = a1->pCertInfo;
  v6 = a2->pCertInfo;
  hHash = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &hHash, 0, 0, 0, 0, 0)
    || BCryptHashData(hHash, v6->Subject.pbData, v6->Subject.cbData, 0)
    || BCryptHashData(hHash, pCertInfo->Subject.pbData, pCertInfo->Subject.cbData, 0) )
  {
    goto LABEL_14;
  }
  pszObjId = (UCHAR *)pCertInfo->SubjectPublicKeyInfo.Algorithm.pszObjId;
  if ( pszObjId )
  {
    v8 = -1;
    do
      ++v8;
    while ( pszObjId[v8] );
  }
  else
  {
    LODWORD(v8) = 0;
  }
  if ( BCryptHashData(hHash, pszObjId, v8, 0)
    || BCryptHashData(
         hHash,
         pCertInfo->SubjectPublicKeyInfo.Algorithm.Parameters.pbData,
         pCertInfo->SubjectPublicKeyInfo.Algorithm.Parameters.cbData,
         0)
    || BCryptHashData(
         hHash,
         pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
         pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
         0)
    || BCryptHashData(hHash, v6->SubjectPublicKeyInfo.PublicKey.pbData, v6->SubjectPublicKeyInfo.PublicKey.cbData, 0)
    || BCryptFinishHash(hHash, a4, 0x20u, 0) )
  {
LABEL_14:
    *(_OWORD *)a4 = 0;
    *((_OWORD *)a4 + 1) = 0;
  }
  if ( hHash )
    BCryptDestroyHash(hHash);
  return 1;
}

```

## disassembly

```asm
0x18001a9c8  mov     rax, rsp
0x18001a9cb  mov     [rax+10h], rbx
0x18001a9cf  mov     [rax+18h], rsi
0x18001a9d3  push    rdi
0x18001a9d4  sub     rsp, 40h
0x18001a9d8  mov     rbx, [rcx+18h]
0x18001a9dc  mov     rsi, r9
0x18001a9df  mov     rdi, [rdx+18h]
0x18001a9e3  xor     r9d, r9d; cbHashObject
0x18001a9e6  mov     dword ptr [rax-18h], 0
0x18001a9ed  lea     rdx, [rax+8]; phHash
0x18001a9f1  mov     dword ptr [rax-20h], 0
0x18001a9f8  xor     r8d, r8d; pbHashObject
0x18001a9fb  mov     qword ptr [rax+8], 0
0x18001aa03  lea     ecx, [r9+41h]; hAlgorithm
0x18001aa07  mov     qword ptr [rax-28h], 0
0x18001aa0f  call    cs:__imp_BCryptCreateHash
0x18001aa15  test    eax, eax
0x18001aa17  jnz     loc_18001AAF4
0x18001aa1d  mov     r8d, [rdi+50h]; cbInput
0x18001aa21  xor     r9d, r9d; dwFlags
0x18001aa24  mov     rdx, [rdi+58h]; pbInput
0x18001aa28  mov     rcx, [rsp+48h+hHash]; hHash
0x18001aa2d  call    cs:__imp_BCryptHashData
0x18001aa33  test    eax, eax
0x18001aa35  jnz     loc_18001AAF4
0x18001aa3b  mov     r8d, [rbx+50h]; cbInput
0x18001aa3f  xor     r9d, r9d; dwFlags
0x18001aa42  mov     rdx, [rbx+58h]; pbInput
0x18001aa46  mov     rcx, [rsp+48h+hHash]; hHash
0x18001aa4b  call    cs:__imp_BCryptHashData
0x18001aa51  test    eax, eax
0x18001aa53  jnz     loc_18001AAF4
0x18001aa59  mov     rdx, [rbx+60h]; pbInput
0x18001aa5d  test    rdx, rdx
0x18001aa60  jz      short loc_18001AA72
0x18001aa62  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001aa66  inc     r8
0x18001aa69  cmp     byte ptr [rdx+r8], 0
0x18001aa6e  jnz     short loc_18001AA66
0x18001aa70  jmp     short loc_18001AA75
0x18001aa72  xor     r8d, r8d; cbInput
0x18001aa75  mov     rcx, [rsp+48h+hHash]; hHash
0x18001aa7a  xor     r9d, r9d; dwFlags
0x18001aa7d  call    cs:__imp_BCryptHashData
0x18001aa83  test    eax, eax
0x18001aa85  jnz     short loc_18001AAF4
0x18001aa87  mov     r8d, [rbx+68h]; cbInput
0x18001aa8b  xor     r9d, r9d; dwFlags
0x18001aa8e  mov     rdx, [rbx+70h]; pbInput
0x18001aa92  mov     rcx, [rsp+48h+hHash]; hHash
0x18001aa97  call    cs:__imp_BCryptHashData
0x18001aa9d  test    eax, eax
0x18001aa9f  jnz     short loc_18001AAF4
0x18001aaa1  mov     r8d, [rbx+78h]; cbInput
0x18001aaa5  xor     r9d, r9d; dwFlags
0x18001aaa8  mov     rdx, [rbx+80h]; pbInput
0x18001aaaf  mov     rcx, [rsp+48h+hHash]; hHash
0x18001aab4  call    cs:__imp_BCryptHashData
0x18001aaba  test    eax, eax
0x18001aabc  jnz     short loc_18001AAF4
0x18001aabe  mov     r8d, [rdi+78h]; cbInput
0x18001aac2  xor     r9d, r9d; dwFlags
0x18001aac5  mov     rdx, [rdi+80h]; pbInput
0x18001aacc  mov     rcx, [rsp+48h+hHash]; hHash
0x18001aad1  call    cs:__imp_BCryptHashData
0x18001aad7  test    eax, eax
0x18001aad9  jnz     short loc_18001AAF4
0x18001aadb  mov     rcx, [rsp+48h+hHash]; hHash
0x18001aae0  lea     r8d, [rax+20h]; cbOutput
0x18001aae4  xor     r9d, r9d; dwFlags
0x18001aae7  mov     rdx, rsi; pbOutput
0x18001aaea  call    cs:__imp_BCryptFinishHash
0x18001aaf0  test    eax, eax
0x18001aaf2  jz      short loc_18001AAFE
0x18001aaf4  xorps   xmm0, xmm0
0x18001aaf7  movups  xmmword ptr [rsi], xmm0
0x18001aafa  movups  xmmword ptr [rsi+10h], xmm0
0x18001aafe  mov     rcx, [rsp+48h+hHash]; hHash
0x18001ab03  test    rcx, rcx
0x18001ab06  jz      short loc_18001AB0E
0x18001ab08  call    cs:__imp_BCryptDestroyHash
0x18001ab0e  mov     rbx, [rsp+48h+arg_8]
0x18001ab13  mov     eax, 1
0x18001ab18  mov     rsi, [rsp+48h+arg_10]
0x18001ab1d  add     rsp, 40h
0x18001ab21  pop     rdi
0x18001ab22  retn
```
