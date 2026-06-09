# DevAuth2_EcdsaVerifySignature

- ea: `0x180004ccc`
- end: `0x180004e50`
- name: `DevAuth2_EcdsaVerifySignature`
- size: `388`
- prototype: `_BOOL8 __fastcall(__int64, _OWORD *, UCHAR *, __int64, UCHAR *pbSignature)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004594`
- `0x1800047d0`

## callees

- `0x180004ccc`
- `0x180006cc0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180004dff`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004dff`
- `ntoskrnl!ExAllocatePool2` at `0x180004d40`
- `ntoskrnl!ExAllocatePool2` at `0x180004d40`
- `cng!BCryptDestroyKey` at `0x180004e15`
- `cng!BCryptDestroyKey` at `0x180004e15`
- `cng!BCryptVerifySignature` at `0x180004de6`
- `cng!BCryptVerifySignature` at `0x180004de6`
- `cng!BCryptOpenAlgorithmProvider` at `0x180004d1e`
- `cng!BCryptOpenAlgorithmProvider` at `0x180004d1e`
- `cng!BCryptCloseAlgorithmProvider` at `0x180004e36`
- `cng!BCryptCloseAlgorithmProvider` at `0x180004e36`
- `cng!BCryptImportKeyPair` at `0x180004db7`
- `cng!BCryptImportKeyPair` at `0x180004db7`

## pseudocode

```c
_BOOL8 __fastcall DevAuth2_EcdsaVerifySignature(__int64 a1, _OWORD *a2, UCHAR *a3, __int64 a4, UCHAR *pbSignature)
{
  BOOL v5; // edi
  __int64 Pool2; // rax
  __int64 pbInput; // rbx
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-30h] BYREF

  v5 = 0;
  phAlgorithm = 0;
  phKey = 0;
  if ( a2 && a3 && pbSignature )
  {
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"ECDSA_P256", 0, 0) >= 0 )
    {
      Pool2 = ExAllocatePool2(258, 104, 1967220036);
      pbInput = Pool2;
      if ( Pool2 )
      {
        memset((void *)(Pool2 + 8), 0, 0x60u);
        *(_DWORD *)pbInput = 827540293;
        *(_DWORD *)(pbInput + 4) = 32;
        *(_OWORD *)(pbInput + 8) = *a2;
        *(_OWORD *)(pbInput + 24) = a2[1];
        *(_OWORD *)(pbInput + 40) = a2[2];
        *(_OWORD *)(pbInput + 56) = a2[3];
        if ( BCryptImportKeyPair(phAlgorithm, 0, L"ECCPUBLICBLOB", &phKey, (PUCHAR)pbInput, 0x48u, 0) >= 0 )
          v5 = BCryptVerifySignature(phKey, 0, a3, 0x20u, pbSignature, 0x40u, 0) >= 0;
        ExFreePoolWithTag((PVOID)pbInput, 0);
      }
    }
    if ( phKey )
    {
      BCryptDestroyKey(phKey);
      phKey = 0;
    }
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x180004ccc  push    rbx
0x180004cce  push    rbp
0x180004ccf  push    rsi
0x180004cd0  push    rdi
0x180004cd1  push    r14
0x180004cd3  sub     rsp, 50h
0x180004cd7  xor     edi, edi
0x180004cd9  mov     r14, r8
0x180004cdc  mov     [rsp+78h+phAlgorithm], rdi
0x180004ce1  mov     rsi, rdx
0x180004ce4  mov     [rsp+78h+phKey], rdi
0x180004ce9  test    rdx, rdx
0x180004cec  jz      loc_180004E42
0x180004cf2  test    r8, r8
0x180004cf5  jz      loc_180004E42
0x180004cfb  mov     rbp, [rsp+78h+pbSignature]
0x180004d03  test    rbp, rbp
0x180004d06  jz      loc_180004E42
0x180004d0c  xor     r9d, r9d; dwFlags
0x180004d0f  lea     rdx, aEcdsaP256; "ECDSA_P256"
0x180004d16  xor     r8d, r8d; pszImplementation
0x180004d19  lea     rcx, [rsp+78h+phAlgorithm]; phAlgorithm
0x180004d1e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180004d25  nop     dword ptr [rax+rax+00h]
0x180004d2a  test    eax, eax
0x180004d2c  js      loc_180004E0B
0x180004d32  lea     edx, [rdi+68h]
0x180004d35  mov     ecx, 102h
0x180004d3a  mov     r8d, 75416544h
0x180004d40  call    cs:__imp_ExAllocatePool2
0x180004d47  nop     dword ptr [rax+rax+00h]
0x180004d4c  mov     rbx, rax
0x180004d4f  test    rax, rax
0x180004d52  jz      loc_180004E0B
0x180004d58  lea     rcx, [rax+8]; void *
0x180004d5c  xor     edx, edx; Val
0x180004d5e  lea     r8d, [rdi+60h]; Size
0x180004d62  call    memset
0x180004d67  mov     dword ptr [rbx], 31534345h
0x180004d6d  lea     r9, [rsp+78h+phKey]; phKey
0x180004d72  mov     dword ptr [rbx+4], 20h ; ' '
0x180004d79  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x180004d80  movups  xmm0, xmmword ptr [rsi]
0x180004d83  mov     [rsp+78h+dwFlags], edi; dwFlags
0x180004d87  xor     edx, edx; hImportKey
0x180004d89  mov     [rsp+78h+cbInput], 48h ; 'H'; cbInput
0x180004d91  movups  xmmword ptr [rbx+8], xmm0
0x180004d95  mov     [rsp+78h+pbInput], rbx; pbInput
0x180004d9a  movups  xmm1, xmmword ptr [rsi+10h]
0x180004d9e  movups  xmmword ptr [rbx+18h], xmm1
0x180004da2  movups  xmm0, xmmword ptr [rsi+20h]
0x180004da6  movups  xmmword ptr [rbx+28h], xmm0
0x180004daa  movups  xmm1, xmmword ptr [rsi+30h]
0x180004dae  movups  xmmword ptr [rbx+38h], xmm1
0x180004db2  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x180004db7  call    cs:__imp_BCryptImportKeyPair
0x180004dbe  nop     dword ptr [rax+rax+00h]
0x180004dc3  test    eax, eax
0x180004dc5  js      short loc_180004DFA
0x180004dc7  mov     rcx, [rsp+78h+phKey]; hKey
0x180004dcc  lea     r9d, [rdi+20h]; cbHash
0x180004dd0  mov     [rsp+78h+dwFlags], edi; dwFlags
0x180004dd4  mov     r8, r14; pbHash
0x180004dd7  mov     [rsp+78h+cbInput], 40h ; '@'; cbSignature
0x180004ddf  xor     edx, edx; pPaddingInfo
0x180004de1  mov     [rsp+78h+pbInput], rbp; pbSignature
0x180004de6  call    cs:__imp_BCryptVerifySignature
0x180004ded  nop     dword ptr [rax+rax+00h]
0x180004df2  test    eax, eax
0x180004df4  lea     ecx, [rdi+1]
0x180004df7  cmovns  edi, ecx
0x180004dfa  xor     edx, edx; Tag
0x180004dfc  mov     rcx, rbx; P
0x180004dff  call    cs:__imp_ExFreePoolWithTag
0x180004e06  nop     dword ptr [rax+rax+00h]
0x180004e0b  mov     rcx, [rsp+78h+phKey]; hKey
0x180004e10  test    rcx, rcx
0x180004e13  jz      short loc_180004E2A
0x180004e15  call    cs:__imp_BCryptDestroyKey
0x180004e1c  nop     dword ptr [rax+rax+00h]
0x180004e21  mov     [rsp+78h+phKey], 0
0x180004e2a  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x180004e2f  test    rcx, rcx
0x180004e32  jz      short loc_180004E42
0x180004e34  xor     edx, edx; dwFlags
0x180004e36  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180004e3d  nop     dword ptr [rax+rax+00h]
0x180004e42  mov     eax, edi
0x180004e44  add     rsp, 50h
0x180004e48  pop     r14
0x180004e4a  pop     rdi
0x180004e4b  pop     rsi
0x180004e4c  pop     rbp
0x180004e4d  pop     rbx
0x180004e4e  retn
```
