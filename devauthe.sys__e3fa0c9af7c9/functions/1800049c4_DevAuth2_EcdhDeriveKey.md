# DevAuth2_EcdhDeriveKey

- ea: `0x1800049c4`
- end: `0x180004cc5`
- name: `DevAuth2_EcdhDeriveKey`
- size: `769`
- prototype: `_BOOL8 __fastcall(__int64, _OWORD *, _OWORD *, _OWORD *, int, __int64, int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004280`

## callees

- `0x180002888`
- `0x180003320`
- `0x1800049c4`
- `0x1800067e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180004c46`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004c46`
- `cng!BCryptDestroySecret` at `0x180004c2c`
- `cng!BCryptDestroySecret` at `0x180004c2c`
- `cng!BCryptDeriveKey` at `0x180004bdd`
- `cng!BCryptDeriveKey` at `0x180004bdd`
- `cng!BCryptDestroyKey` at `0x180004c5b`
- `cng!BCryptDestroyKey` at `0x180004c74`
- `cng!BCryptDestroyKey` at `0x180004c5b`
- `cng!BCryptDestroyKey` at `0x180004c74`
- `cng!BCryptOpenAlgorithmProvider` at `0x180004a70`
- `cng!BCryptOpenAlgorithmProvider` at `0x180004a70`
- `cng!BCryptCloseAlgorithmProvider` at `0x180004c8f`
- `cng!BCryptCloseAlgorithmProvider` at `0x180004c8f`
- `cng!BCryptImportKeyPair` at `0x180004b00`
- `cng!BCryptImportKeyPair` at `0x180004b5c`
- `cng!BCryptImportKeyPair` at `0x180004b00`
- `cng!BCryptImportKeyPair` at `0x180004b5c`
- `cng!BCryptSecretAgreement` at `0x180004b7f`
- `cng!BCryptSecretAgreement` at `0x180004b7f`

## pseudocode

```c
_BOOL8 __fastcall DevAuth2_EcdhDeriveKey(
        __int64 a1,
        _OWORD *a2,
        _OWORD *a3,
        _OWORD *a4,
        int a5,
        __int64 a6,
        int a7,
        void *a8)
{
  BOOL v11; // edi
  __int64 v12; // rbx
  __int64 pbInput; // rax
  size_t dwFlags; // [rsp+30h] [rbp-79h]
  ULONG cbDerivedKey; // [rsp+40h] [rbp-69h] BYREF
  BCRYPT_SECRET_HANDLE phAgreedSecret; // [rsp+48h] [rbp-61h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-59h] BYREF
  BCRYPT_KEY_HANDLE hPubKey; // [rsp+58h] [rbp-51h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+60h] [rbp-49h] BYREF
  __int128 v21; // [rsp+68h] [rbp-41h] BYREF
  BCryptBufferDesc pParameterList; // [rsp+78h] [rbp-31h] BYREF
  UCHAR pbDerivedKey[16]; // [rsp+88h] [rbp-21h] BYREF
  __int128 v24; // [rsp+98h] [rbp-11h]

  phAlgorithm = 0;
  phKey = 0;
  hPubKey = 0;
  phAgreedSecret = 0;
  cbDerivedKey = 32;
  v11 = 0;
  *(_OWORD *)pbDerivedKey = 0;
  v24 = 0;
  pParameterList = 0;
  v21 = 0;
  if ( a2 && a3 && a4 && a6 && a8 )
  {
    v12 = 0;
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"ECDH_P256", 0, 0) >= 0 )
    {
      pbInput = DevAuthAlloc(0x68u);
      v12 = pbInput;
      if ( pbInput )
      {
        *(_DWORD *)pbInput = 843793221;
        *(_DWORD *)(pbInput + 4) = 32;
        *(_OWORD *)(pbInput + 8) = *a3;
        *(_OWORD *)(pbInput + 24) = a3[1];
        *(_OWORD *)(pbInput + 40) = a3[2];
        *(_OWORD *)(pbInput + 56) = a3[3];
        *(_OWORD *)(pbInput + 72) = *a2;
        *(_OWORD *)(pbInput + 88) = a2[1];
        if ( BCryptImportKeyPair(phAlgorithm, 0, L"ECCPRIVATEBLOB", &phKey, (PUCHAR)pbInput, 0x68u, 0) >= 0 )
        {
          *(_DWORD *)v12 = 827016005;
          *(_OWORD *)(v12 + 8) = *a4;
          *(_OWORD *)(v12 + 24) = a4[1];
          *(_OWORD *)(v12 + 40) = a4[2];
          *(_OWORD *)(v12 + 56) = a4[3];
          if ( BCryptImportKeyPair(phAlgorithm, 0, L"ECCPUBLICBLOB", &hPubKey, (PUCHAR)v12, 0x48u, 0) >= 0
            && BCryptSecretAgreement(phKey, hPubKey, &phAgreedSecret, 0) >= 0 )
          {
            pParameterList.pBuffers = (PBCryptBuffer)&v21;
            *((_QWORD *)&v21 + 1) = L"SHA256";
            pParameterList.cBuffers = 1;
            *(_QWORD *)&v21 = 14;
            if ( BCryptDeriveKey(phAgreedSecret, L"HASH", &pParameterList, pbDerivedKey, cbDerivedKey, &cbDerivedKey, 0) >= 0 )
            {
              LODWORD(dwFlags) = 48;
              v11 = DevAuthPesudoRandomFunction((int)"Master Secret", (int)pbDerivedKey, 32, a6, 64, a8, dwFlags) != 0;
            }
          }
        }
      }
    }
    if ( phAgreedSecret )
    {
      BCryptDestroySecret(phAgreedSecret);
      phAgreedSecret = 0;
    }
    if ( v12 )
      ExFreePoolWithTag((PVOID)v12, 0);
    if ( phKey )
    {
      BCryptDestroyKey(phKey);
      phKey = 0;
    }
    if ( hPubKey )
    {
      BCryptDestroyKey(hPubKey);
      hPubKey = 0;
    }
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  return v11;
}

```

## disassembly

```asm
0x1800049c4  mov     [rsp-8+arg_0], rbx
0x1800049c9  push    rbp
0x1800049ca  push    rsi
0x1800049cb  push    rdi
0x1800049cc  push    r12
0x1800049ce  push    r13
0x1800049d0  push    r14
0x1800049d2  push    r15
0x1800049d4  lea     rbp, [rsp-7]
0x1800049d9  sub     rsp, 0B0h
0x1800049e0  mov     rax, cs:__security_cookie
0x1800049e7  xor     rax, rsp
0x1800049ea  mov     [rbp+37h+var_38], rax
0x1800049ee  mov     r15, [rbp+37h+arg_28]
0x1800049f2  xor     eax, eax
0x1800049f4  mov     r12, [rbp+37h+arg_38]
0x1800049f8  xorps   xmm0, xmm0
0x1800049fb  mov     [rbp+37h+phAlgorithm], rax
0x1800049ff  xorps   xmm1, xmm1
0x180004a02  mov     [rbp+37h+phKey], rax
0x180004a06  mov     rsi, r9
0x180004a09  mov     [rbp+37h+hPubKey], rax
0x180004a0d  mov     r14, r8
0x180004a10  mov     [rbp+37h+phAgreedSecret], rax
0x180004a14  mov     r13, rdx
0x180004a17  mov     [rbp+37h+cbDerivedKey], 20h ; ' '
0x180004a1e  mov     edi, eax
0x180004a20  movups  xmmword ptr [rbp+37h+pbDerivedKey], xmm0
0x180004a24  movups  [rbp+37h+var_48], xmm0
0x180004a28  movups  xmmword ptr [rbp+37h+pParameterList.ulVersion], xmm0
0x180004a2c  movups  [rbp+37h+var_78], xmm1
0x180004a30  test    rdx, rdx
0x180004a33  jz      loc_180004C9B
0x180004a39  test    r8, r8
0x180004a3c  jz      loc_180004C9B
0x180004a42  test    r9, r9
0x180004a45  jz      loc_180004C9B
0x180004a4b  test    r15, r15
0x180004a4e  jz      loc_180004C9B
0x180004a54  test    r12, r12
0x180004a57  jz      loc_180004C9B
0x180004a5d  xor     r9d, r9d; dwFlags
0x180004a60  lea     rdx, aEcdhP256; "ECDH_P256"
0x180004a67  xor     r8d, r8d; pszImplementation
0x180004a6a  lea     rcx, [rbp+37h+phAlgorithm]; phAlgorithm
0x180004a6e  mov     ebx, eax
0x180004a70  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180004a77  nop     dword ptr [rax+rax+00h]
0x180004a7c  test    eax, eax
0x180004a7e  js      loc_180004C20
0x180004a84  lea     ecx, [rbx+68h]; Size
0x180004a87  call    DevAuthAlloc
0x180004a8c  mov     rbx, rax
0x180004a8f  test    rax, rax
0x180004a92  jz      loc_180004C20
0x180004a98  mov     dword ptr [rax], 324B4345h
0x180004a9e  lea     r9, [rbp+37h+phKey]; phKey
0x180004aa2  mov     dword ptr [rax+4], 20h ; ' '
0x180004aa9  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x180004ab0  movups  xmm0, xmmword ptr [r14]
0x180004ab4  xor     edx, edx; hImportKey
0x180004ab6  movups  xmmword ptr [rax+8], xmm0
0x180004aba  movups  xmm1, xmmword ptr [r14+10h]
0x180004abf  movups  xmmword ptr [rax+18h], xmm1
0x180004ac3  movups  xmm0, xmmword ptr [r14+20h]
0x180004ac8  movups  xmmword ptr [rax+28h], xmm0
0x180004acc  movups  xmm1, xmmword ptr [r14+30h]
0x180004ad1  xor     r14d, r14d
0x180004ad4  mov     dword ptr [rsp+0E0h+dwFlags], r14d; dwFlags
0x180004ad9  movups  xmmword ptr [rax+38h], xmm1
0x180004add  mov     [rsp+0E0h+cbInput], 68h ; 'h'; cbInput
0x180004ae5  movups  xmm0, xmmword ptr [r13+0]
0x180004aea  mov     [rsp+0E0h+pbInput], rax; pbInput
0x180004aef  movups  xmmword ptr [rax+48h], xmm0
0x180004af3  movups  xmm1, xmmword ptr [r13+10h]
0x180004af8  movups  xmmword ptr [rax+58h], xmm1
0x180004afc  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x180004b00  call    cs:__imp_BCryptImportKeyPair
0x180004b07  nop     dword ptr [rax+rax+00h]
0x180004b0c  test    eax, eax
0x180004b0e  js      loc_180004C23
0x180004b14  mov     dword ptr [rbx], 314B4345h
0x180004b1a  lea     r9, [rbp+37h+hPubKey]; phKey
0x180004b1e  movups  xmm0, xmmword ptr [rsi]
0x180004b21  mov     dword ptr [rsp+0E0h+dwFlags], r14d; dwFlags
0x180004b26  lea     r8, aEccpublicblob; "ECCPUBLICBLOB"
0x180004b2d  mov     [rsp+0E0h+cbInput], 48h ; 'H'; cbInput
0x180004b35  xor     edx, edx; hImportKey
0x180004b37  movups  xmmword ptr [rbx+8], xmm0
0x180004b3b  mov     [rsp+0E0h+pbInput], rbx; pbInput
0x180004b40  movups  xmm1, xmmword ptr [rsi+10h]
0x180004b44  movups  xmmword ptr [rbx+18h], xmm1
0x180004b48  movups  xmm0, xmmword ptr [rsi+20h]
0x180004b4c  movups  xmmword ptr [rbx+28h], xmm0
0x180004b50  movups  xmm1, xmmword ptr [rsi+30h]
0x180004b54  movups  xmmword ptr [rbx+38h], xmm1
0x180004b58  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x180004b5c  call    cs:__imp_BCryptImportKeyPair
0x180004b63  nop     dword ptr [rax+rax+00h]
0x180004b68  test    eax, eax
0x180004b6a  js      loc_180004C23
0x180004b70  mov     rdx, [rbp+37h+hPubKey]; hPubKey
0x180004b74  lea     r8, [rbp+37h+phAgreedSecret]; phAgreedSecret
0x180004b78  mov     rcx, [rbp+37h+phKey]; hPrivKey
0x180004b7c  xor     r9d, r9d; dwFlags
0x180004b7f  call    cs:__imp_BCryptSecretAgreement
0x180004b86  nop     dword ptr [rax+rax+00h]
0x180004b8b  test    eax, eax
0x180004b8d  js      loc_180004C23
0x180004b93  mov     rcx, [rbp+37h+phAgreedSecret]; hSharedSecret
0x180004b97  lea     rax, [rbp+37h+var_78]
0x180004b9b  mov     [rbp+37h+pParameterList.pBuffers], rax
0x180004b9f  lea     esi, [r14+1]
0x180004ba3  lea     rax, pszAlgId; "SHA256"
0x180004baa  mov     dword ptr [rsp+0E0h+dwFlags], r14d; dwFlags
0x180004baf  mov     qword ptr [rbp+37h+var_78+8], rax
0x180004bb3  lea     r9, [rbp+37h+pbDerivedKey]; pbDerivedKey
0x180004bb7  lea     rax, [rbp+37h+cbDerivedKey]
0x180004bbb  mov     [rbp+37h+pParameterList.cBuffers], esi
0x180004bbe  mov     qword ptr [rsp+0E0h+cbInput], rax; pcbResult
0x180004bc3  lea     r8, [rbp+37h+pParameterList]; pParameterList
0x180004bc7  mov     eax, [rbp+37h+cbDerivedKey]
0x180004bca  lea     rdx, pwszKDF; "HASH"
0x180004bd1  mov     dword ptr [rsp+0E0h+pbInput], eax; cbDerivedKey
0x180004bd5  mov     qword ptr [rbp+37h+var_78], 0Eh
0x180004bdd  call    cs:__imp_BCryptDeriveKey
0x180004be4  nop     dword ptr [rax+rax+00h]
0x180004be9  test    eax, eax
0x180004beb  js      short loc_180004C23
0x180004bed  mov     dword ptr [rsp+0E0h+dwFlags], 30h ; '0'; Size
0x180004bf5  lea     r8d, [r14+20h]; int
0x180004bf9  mov     qword ptr [rsp+0E0h+cbInput], r12; void *
0x180004bfe  lea     rdx, [rbp+37h+pbDerivedKey]; int
0x180004c02  mov     r9, r15; int
0x180004c05  mov     dword ptr [rsp+0E0h+pbInput], 40h ; '@'; int
0x180004c0d  lea     rcx, aMasterSecret; "Master Secret"
0x180004c14  call    DevAuthPesudoRandomFunction
0x180004c19  test    eax, eax
0x180004c1b  cmovnz  edi, esi
0x180004c1e  jmp     short loc_180004C23
0x180004c20  xor     r14d, r14d
0x180004c23  mov     rcx, [rbp+37h+phAgreedSecret]; hSecret
0x180004c27  test    rcx, rcx
0x180004c2a  jz      short loc_180004C3C
0x180004c2c  call    cs:__imp_BCryptDestroySecret
0x180004c33  nop     dword ptr [rax+rax+00h]
0x180004c38  mov     [rbp+37h+phAgreedSecret], r14
0x180004c3c  test    rbx, rbx
0x180004c3f  jz      short loc_180004C52
0x180004c41  xor     edx, edx; Tag
0x180004c43  mov     rcx, rbx; P
0x180004c46  call    cs:__imp_ExFreePoolWithTag
0x180004c4d  nop     dword ptr [rax+rax+00h]
0x180004c52  mov     rcx, [rbp+37h+phKey]; hKey
0x180004c56  test    rcx, rcx
0x180004c59  jz      short loc_180004C6B
0x180004c5b  call    cs:__imp_BCryptDestroyKey
0x180004c62  nop     dword ptr [rax+rax+00h]
0x180004c67  mov     [rbp+37h+phKey], r14
0x180004c6b  mov     rcx, [rbp+37h+hPubKey]; hKey
0x180004c6f  test    rcx, rcx
0x180004c72  jz      short loc_180004C84
0x180004c74  call    cs:__imp_BCryptDestroyKey
0x180004c7b  nop     dword ptr [rax+rax+00h]
0x180004c80  mov     [rbp+37h+hPubKey], r14
0x180004c84  mov     rcx, [rbp+37h+phAlgorithm]; hAlgorithm
0x180004c88  test    rcx, rcx
0x180004c8b  jz      short loc_180004C9B
0x180004c8d  xor     edx, edx; dwFlags
0x180004c8f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180004c96  nop     dword ptr [rax+rax+00h]
0x180004c9b  mov     eax, edi
0x180004c9d  mov     rcx, [rbp+37h+var_38]
0x180004ca1  xor     rcx, rsp; StackCookie
0x180004ca4  call    __security_check_cookie
0x180004ca9  mov     rbx, [rsp+0E0h+arg_0]
0x180004cb1  add     rsp, 0B0h
0x180004cb8  pop     r15
0x180004cba  pop     r14
0x180004cbc  pop     r13
0x180004cbe  pop     r12
0x180004cc0  pop     rdi
0x180004cc1  pop     rsi
0x180004cc2  pop     rbp
0x180004cc3  retn
```
