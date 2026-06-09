# CrlGetOriginIdentifierFromCrlIssuer(_CERT_CONTEXT const *,_CRYPTOAPI_BLOB *,int,uchar * const)

- ea: `0x180017c34`
- end: `0x180017d2b`
- name: `?CrlGetOriginIdentifierFromCrlIssuer@@YAHPEBU_CERT_CONTEXT@@PEAU_CRYPTOAPI_BLOB@@HQEAE@Z`
- size: `247`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, struct _CRYPTOAPI_BLOB *, int, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e5a8`
- `0x18001e1b8`

## callees

- `0x180017c34`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180017ca8`
- `bcrypt!BCryptHashData` at `0x180017cc1`
- `bcrypt!BCryptHashData` at `0x180017cde`
- `bcrypt!BCryptHashData` at `0x180017ca8`
- `bcrypt!BCryptHashData` at `0x180017cc1`
- `bcrypt!BCryptHashData` at `0x180017cde`
- `bcrypt!BCryptDestroyHash` at `0x180017d0b`
- `bcrypt!BCryptDestroyHash` at `0x180017d0b`
- `bcrypt!BCryptFinishHash` at `0x180017cf7`
- `bcrypt!BCryptFinishHash` at `0x180017cf7`
- `bcrypt!BCryptCreateHash` at `0x180017c7c`
- `bcrypt!BCryptCreateHash` at `0x180017c7c`

## pseudocode

```c
__int64 __fastcall CrlGetOriginIdentifierFromCrlIssuer(
        const struct _CERT_CONTEXT *a1,
        struct _CRYPTOAPI_BLOB *a2,
        int a3,
        unsigned __int8 *const a4)
{
  PCERT_INFO pCertInfo; // rdi
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-38h] BYREF
  UCHAR pbInput; // [rsp+80h] [rbp+8h] BYREF

  pCertInfo = a1->pCertInfo;
  pbInput = 0;
  hHash = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &hHash, 0, 0, 0, 0, 0)
    || (pbInput = a3 != 0, BCryptHashData(hHash, &pbInput, 1u, 0))
    || BCryptHashData(hHash, a2->pbData, a2->cbData, 0)
    || BCryptHashData(
         hHash,
         pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
         pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
         0)
    || BCryptFinishHash(hHash, a4, 0x20u, 0) )
  {
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
0x180017c34  mov     rax, rsp
0x180017c37  push    rbx
0x180017c38  push    rbp
0x180017c39  push    rsi
0x180017c3a  push    rdi
0x180017c3b  sub     rsp, 58h
0x180017c3f  mov     rdi, [rcx+18h]
0x180017c43  mov     rbx, r9
0x180017c46  mov     dword ptr [rax-48h], 0
0x180017c4d  xor     r9d, r9d; cbHashObject
0x180017c50  mov     ebp, r8d
0x180017c53  mov     dword ptr [rax-50h], 0
0x180017c5a  mov     rsi, rdx
0x180017c5d  mov     byte ptr [rax+8], 0
0x180017c61  xor     r8d, r8d; pbHashObject
0x180017c64  mov     qword ptr [rax-38h], 0
0x180017c6c  lea     ecx, [r9+41h]; hAlgorithm
0x180017c70  mov     qword ptr [rax-58h], 0
0x180017c78  lea     rdx, [rax-38h]; phHash
0x180017c7c  call    cs:__imp_BCryptCreateHash
0x180017c82  test    eax, eax
0x180017c84  jnz     loc_180017D1F
0x180017c8a  mov     rcx, [rsp+78h+hHash]; hHash
0x180017c8f  lea     r8d, [rax+1]; cbInput
0x180017c93  test    ebp, ebp
0x180017c95  lea     rdx, [rsp+78h+pbInput]; pbInput
0x180017c9d  setnz   [rsp+78h+pbInput]
0x180017ca5  xor     r9d, r9d; dwFlags
0x180017ca8  call    cs:__imp_BCryptHashData
0x180017cae  test    eax, eax
0x180017cb0  jnz     short loc_180017D1F
0x180017cb2  mov     r8d, [rsi]; cbInput
0x180017cb5  xor     r9d, r9d; dwFlags
0x180017cb8  mov     rdx, [rsi+8]; pbInput
0x180017cbc  mov     rcx, [rsp+78h+hHash]; hHash
0x180017cc1  call    cs:__imp_BCryptHashData
0x180017cc7  test    eax, eax
0x180017cc9  jnz     short loc_180017D1F
0x180017ccb  mov     r8d, [rdi+78h]; cbInput
0x180017ccf  xor     r9d, r9d; dwFlags
0x180017cd2  mov     rdx, [rdi+80h]; pbInput
0x180017cd9  mov     rcx, [rsp+78h+hHash]; hHash
0x180017cde  call    cs:__imp_BCryptHashData
0x180017ce4  test    eax, eax
0x180017ce6  jnz     short loc_180017D1F
0x180017ce8  mov     rcx, [rsp+78h+hHash]; hHash
0x180017ced  lea     r8d, [rax+20h]; cbOutput
0x180017cf1  xor     r9d, r9d; dwFlags
0x180017cf4  mov     rdx, rbx; pbOutput
0x180017cf7  call    cs:__imp_BCryptFinishHash
0x180017cfd  test    eax, eax
0x180017cff  jnz     short loc_180017D1F
0x180017d01  mov     rcx, [rsp+78h+hHash]; hHash
0x180017d06  test    rcx, rcx
0x180017d09  jz      short loc_180017D11
0x180017d0b  call    cs:__imp_BCryptDestroyHash
0x180017d11  mov     eax, 1
0x180017d16  add     rsp, 58h
0x180017d1a  pop     rdi
0x180017d1b  pop     rsi
0x180017d1c  pop     rbp
0x180017d1d  pop     rbx
0x180017d1e  retn
0x180017d1f  xorps   xmm0, xmm0
0x180017d22  movups  xmmword ptr [rbx], xmm0
0x180017d25  movups  xmmword ptr [rbx+10h], xmm0
0x180017d29  jmp     short loc_180017D01
```
