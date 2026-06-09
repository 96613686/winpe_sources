# DevAuthVerifySignature

- ea: `0x180002c44`
- end: `0x180002d73`
- name: `DevAuthVerifySignature`
- size: `303`
- prototype: `_BOOL8 __fastcall(void *, size_t, UCHAR *, __int64, PUCHAR pbSignature, ULONG cbSignature)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000325c`

## callees

- `0x180002c44`
- `0x180002d7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180002d2b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180002d2b`
- `cng!BCryptDestroyKey` at `0x180002d40`
- `cng!BCryptDestroyKey` at `0x180002d40`
- `cng!BCryptVerifySignature` at `0x180002d0d`
- `cng!BCryptVerifySignature` at `0x180002d0d`
- `cng!BCryptOpenAlgorithmProvider` at `0x180002c9a`
- `cng!BCryptOpenAlgorithmProvider` at `0x180002c9a`
- `cng!BCryptCloseAlgorithmProvider` at `0x180002d57`
- `cng!BCryptCloseAlgorithmProvider` at `0x180002d57`
- `cng!BCryptImportKeyPair` at `0x180002ccb`
- `cng!BCryptImportKeyPair` at `0x180002ccb`

## pseudocode

```c
_BOOL8 __fastcall DevAuthVerifySignature(
        void *a1,
        size_t a2,
        UCHAR *a3,
        __int64 a4,
        PUCHAR pbSignature,
        ULONG cbSignature)
{
  BOOL v6; // edi
  int v8; // eax
  UCHAR *pbInput; // rbx
  PUCHAR v11; // [rsp+40h] [rbp-10h] BYREF
  const WCHAR *pPaddingInfo; // [rsp+48h] [rbp-8h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+70h] [rbp+20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+80h] [rbp+30h] BYREF
  ULONG cbInput; // [rsp+88h] [rbp+38h] BYREF

  v6 = 0;
  v11 = 0;
  cbInput = 0;
  phAlgorithm = 0;
  phKey = 0;
  pPaddingInfo = 0;
  v8 = CreateCngPublicKeyBlob(a1, a2, (__int64 *)&v11, &cbInput);
  pbInput = v11;
  if ( v8
    && BCryptOpenAlgorithmProvider(&phAlgorithm, L"RSA", 0, 0) >= 0
    && BCryptImportKeyPair(phAlgorithm, 0, L"RSAPUBLICBLOB", &phKey, pbInput, cbInput, 0) >= 0 )
  {
    pPaddingInfo = L"SHA256";
    v6 = BCryptVerifySignature(phKey, &pPaddingInfo, a3, 0x20u, pbSignature, cbSignature, 2u) >= 0;
  }
  if ( pbInput )
    ExFreePoolWithTag(pbInput, 0);
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v6;
}

```

## disassembly

```asm
0x180002c44  mov     [rsp-18h+arg_8], rbx
0x180002c49  mov     [rsp-18h+arg_18], r9d
0x180002c4e  push    rbp
0x180002c4f  push    rsi
0x180002c50  push    rdi
0x180002c51  mov     rbp, rsp
0x180002c54  sub     rsp, 50h
0x180002c58  xor     edi, edi
0x180002c5a  lea     r9, [rbp+arg_18]
0x180002c5e  mov     rsi, r8
0x180002c61  mov     [rbp+var_10], rdi
0x180002c65  lea     r8, [rbp+var_10]
0x180002c69  mov     [rbp+arg_18], edi
0x180002c6c  mov     [rbp+phAlgorithm], rdi
0x180002c70  mov     [rbp+phKey], rdi
0x180002c74  mov     [rbp+pPaddingInfo], rdi
0x180002c78  call    _CreateCngPublicKeyBlob
0x180002c7d  mov     rbx, [rbp+var_10]
0x180002c81  test    eax, eax
0x180002c83  jz      loc_180002D21
0x180002c89  xor     r9d, r9d; dwFlags
0x180002c8c  lea     rdx, aRsa; "RSA"
0x180002c93  xor     r8d, r8d; pszImplementation
0x180002c96  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180002c9a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180002ca1  nop     dword ptr [rax+rax+00h]
0x180002ca6  test    eax, eax
0x180002ca8  js      short loc_180002D21
0x180002caa  mov     eax, [rbp+arg_18]
0x180002cad  lea     r9, [rbp+phKey]; phKey
0x180002cb1  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180002cb5  lea     r8, pszBlobType; "RSAPUBLICBLOB"
0x180002cbc  mov     [rsp+50h+dwFlags], edi; dwFlags
0x180002cc0  xor     edx, edx; hImportKey
0x180002cc2  mov     [rsp+50h+cbInput], eax; cbInput
0x180002cc6  mov     [rsp+50h+pbInput], rbx; pbInput
0x180002ccb  call    cs:__imp_BCryptImportKeyPair
0x180002cd2  nop     dword ptr [rax+rax+00h]
0x180002cd7  test    eax, eax
0x180002cd9  js      short loc_180002D21
0x180002cdb  mov     rcx, [rbp+phKey]; hKey
0x180002cdf  lea     rax, pszAlgId; "SHA256"
0x180002ce6  mov     [rbp+pPaddingInfo], rax
0x180002cea  lea     r9d, [rdi+20h]; cbHash
0x180002cee  mov     eax, [rbp+cbSignature]
0x180002cf1  lea     rdx, [rbp+pPaddingInfo]; pPaddingInfo
0x180002cf5  mov     [rsp+50h+dwFlags], 2; dwFlags
0x180002cfd  mov     r8, rsi; pbHash
0x180002d00  mov     [rsp+50h+cbInput], eax; cbSignature
0x180002d04  mov     rax, [rbp+pbSignature]
0x180002d08  mov     [rsp+50h+pbInput], rax; pbSignature
0x180002d0d  call    cs:__imp_BCryptVerifySignature
0x180002d14  nop     dword ptr [rax+rax+00h]
0x180002d19  test    eax, eax
0x180002d1b  lea     ecx, [rdi+1]
0x180002d1e  cmovns  edi, ecx
0x180002d21  test    rbx, rbx
0x180002d24  jz      short loc_180002D37
0x180002d26  xor     edx, edx; Tag
0x180002d28  mov     rcx, rbx; P
0x180002d2b  call    cs:__imp_ExFreePoolWithTag
0x180002d32  nop     dword ptr [rax+rax+00h]
0x180002d37  mov     rcx, [rbp+phKey]; hKey
0x180002d3b  test    rcx, rcx
0x180002d3e  jz      short loc_180002D4C
0x180002d40  call    cs:__imp_BCryptDestroyKey
0x180002d47  nop     dword ptr [rax+rax+00h]
0x180002d4c  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180002d50  test    rcx, rcx
0x180002d53  jz      short loc_180002D63
0x180002d55  xor     edx, edx; dwFlags
0x180002d57  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180002d5e  nop     dword ptr [rax+rax+00h]
0x180002d63  mov     rbx, [rsp+50h+arg_8]
0x180002d68  mov     eax, edi
0x180002d6a  add     rsp, 50h
0x180002d6e  pop     rdi
0x180002d6f  pop     rsi
0x180002d70  pop     rbp
0x180002d71  retn
```
