# _DevAuth2_EccKeyGen

- ea: `0x180004e58`
- end: `0x18000501a`
- name: `_DevAuth2_EccKeyGen`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004280`

## callees

- `0x180003320`
- `0x180004e58`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180004fc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004fc2`
- `cng!BCryptExportKey` at `0x180004f1e`
- `cng!BCryptExportKey` at `0x180004f72`
- `cng!BCryptExportKey` at `0x180004f1e`
- `cng!BCryptExportKey` at `0x180004f72`
- `cng!BCryptGenerateKeyPair` at `0x180004ecc`
- `cng!BCryptGenerateKeyPair` at `0x180004ecc`
- `cng!BCryptFinalizeKeyPair` at `0x180004ee6`
- `cng!BCryptFinalizeKeyPair` at `0x180004ee6`
- `cng!BCryptDestroyKey` at `0x180004fd7`
- `cng!BCryptDestroyKey` at `0x180004fd7`
- `cng!BCryptOpenAlgorithmProvider` at `0x180004ea7`
- `cng!BCryptOpenAlgorithmProvider` at `0x180004ea7`
- `cng!BCryptCloseAlgorithmProvider` at `0x180004ff6`
- `cng!BCryptCloseAlgorithmProvider` at `0x180004ff6`

## pseudocode

```c
__int64 __fastcall DevAuth2_EccKeyGen(__int64 a1, __int64 a2, _OWORD *a3, _OWORD *a4)
{
  unsigned int v4; // esi
  __int64 v7; // rbx
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-8h] BYREF
  ULONG cbOutput; // [rsp+78h] [rbp+28h] BYREF

  v4 = 0;
  phAlgorithm = 0;
  phKey = 0;
  cbOutput = 0;
  if ( a3 && a4 )
  {
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"ECDH_P256", 0, 0) >= 0
      && BCryptGenerateKeyPair(phAlgorithm, &phKey, 0x100u, 0) >= 0
      && BCryptFinalizeKeyPair(phKey, 0) >= 0
      && BCryptExportKey(phKey, 0, L"ECCPRIVATEBLOB", 0, cbOutput, &cbOutput, 0) >= 0 )
    {
      if ( cbOutput )
      {
        v7 = DevAuthAlloc(cbOutput);
        if ( v7 )
        {
          if ( BCryptExportKey(phKey, 0, L"ECCPRIVATEBLOB", (PUCHAR)v7, cbOutput, &cbOutput, 0) >= 0
            && *(_DWORD *)(v7 + 4) == 32 )
          {
            v4 = 1;
            v8 = *(_OWORD *)(v7 + 88);
            *a3 = *(_OWORD *)(v7 + 72);
            v9 = *(_OWORD *)(v7 + 8);
            a3[1] = v8;
            v10 = *(_OWORD *)(v7 + 24);
            *a4 = v9;
            v11 = *(_OWORD *)(v7 + 40);
            a4[1] = v10;
            v12 = *(_OWORD *)(v7 + 56);
            a4[2] = v11;
            a4[3] = v12;
          }
          ExFreePoolWithTag((PVOID)v7, 0);
        }
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
  return v4;
}

```

## disassembly

```asm
0x180004e58  mov     [rsp-18h+arg_0], rbx
0x180004e5d  mov     [rsp-18h+arg_10], rsi
0x180004e62  mov     [rsp-18h+arg_8], edx
0x180004e66  push    rbp
0x180004e67  push    rdi
0x180004e68  push    r14
0x180004e6a  mov     rbp, rsp
0x180004e6d  sub     rsp, 50h
0x180004e71  xor     esi, esi
0x180004e73  mov     rdi, r9
0x180004e76  mov     [rbp+phAlgorithm], rsi
0x180004e7a  mov     r14, r8
0x180004e7d  mov     [rbp+phKey], rsi
0x180004e81  mov     [rbp+arg_8], esi
0x180004e84  test    r8, r8
0x180004e87  jz      loc_180005002
0x180004e8d  test    r9, r9
0x180004e90  jz      loc_180005002
0x180004e96  xor     r9d, r9d; dwFlags
0x180004e99  lea     rdx, aEcdhP256; "ECDH_P256"
0x180004ea0  xor     r8d, r8d; pszImplementation
0x180004ea3  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180004ea7  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180004eae  nop     dword ptr [rax+rax+00h]
0x180004eb3  test    eax, eax
0x180004eb5  js      loc_180004FCE
0x180004ebb  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180004ebf  lea     rdx, [rbp+phKey]; phKey
0x180004ec3  xor     r9d, r9d; dwFlags
0x180004ec6  mov     r8d, 100h; dwLength
0x180004ecc  call    cs:__imp_BCryptGenerateKeyPair
0x180004ed3  nop     dword ptr [rax+rax+00h]
0x180004ed8  test    eax, eax
0x180004eda  js      loc_180004FCE
0x180004ee0  mov     rcx, [rbp+phKey]; hKey
0x180004ee4  xor     edx, edx; dwFlags
0x180004ee6  call    cs:__imp_BCryptFinalizeKeyPair
0x180004eed  nop     dword ptr [rax+rax+00h]
0x180004ef2  test    eax, eax
0x180004ef4  js      loc_180004FCE
0x180004efa  mov     rcx, [rbp+phKey]; hKey
0x180004efe  lea     rax, [rbp+arg_8]
0x180004f02  mov     [rsp+50h+dwFlags], esi; dwFlags
0x180004f06  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x180004f0d  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180004f12  xor     r9d, r9d; pbOutput
0x180004f15  mov     eax, [rbp+arg_8]
0x180004f18  xor     edx, edx; hExportKey
0x180004f1a  mov     [rsp+50h+cbOutput], eax; cbOutput
0x180004f1e  call    cs:__imp_BCryptExportKey
0x180004f25  nop     dword ptr [rax+rax+00h]
0x180004f2a  test    eax, eax
0x180004f2c  js      loc_180004FCE
0x180004f32  mov     ecx, [rbp+arg_8]; Size
0x180004f35  test    ecx, ecx
0x180004f37  jz      loc_180004FCE
0x180004f3d  call    DevAuthAlloc
0x180004f42  mov     rbx, rax
0x180004f45  test    rax, rax
0x180004f48  jz      loc_180004FCE
0x180004f4e  mov     ecx, [rbp+arg_8]
0x180004f51  lea     rax, [rbp+arg_8]
0x180004f55  mov     [rsp+50h+dwFlags], esi; dwFlags
0x180004f59  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x180004f60  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180004f65  mov     r9, rbx; pbOutput
0x180004f68  mov     [rsp+50h+cbOutput], ecx; cbOutput
0x180004f6c  xor     edx, edx; hExportKey
0x180004f6e  mov     rcx, [rbp+phKey]; hKey
0x180004f72  call    cs:__imp_BCryptExportKey
0x180004f79  nop     dword ptr [rax+rax+00h]
0x180004f7e  test    eax, eax
0x180004f80  js      short loc_180004FBD
0x180004f82  cmp     dword ptr [rbx+4], 20h ; ' '
0x180004f86  jnz     short loc_180004FBD
0x180004f88  movups  xmm0, xmmword ptr [rbx+48h]
0x180004f8c  mov     esi, 1
0x180004f91  movups  xmm1, xmmword ptr [rbx+58h]
0x180004f95  movups  xmmword ptr [r14], xmm0
0x180004f99  movups  xmm0, xmmword ptr [rbx+8]
0x180004f9d  movups  xmmword ptr [r14+10h], xmm1
0x180004fa2  movups  xmm1, xmmword ptr [rbx+18h]
0x180004fa6  movups  xmmword ptr [rdi], xmm0
0x180004fa9  movups  xmm0, xmmword ptr [rbx+28h]
0x180004fad  movups  xmmword ptr [rdi+10h], xmm1
0x180004fb1  movups  xmm1, xmmword ptr [rbx+38h]
0x180004fb5  movups  xmmword ptr [rdi+20h], xmm0
0x180004fb9  movups  xmmword ptr [rdi+30h], xmm1
0x180004fbd  xor     edx, edx; Tag
0x180004fbf  mov     rcx, rbx; P
0x180004fc2  call    cs:__imp_ExFreePoolWithTag
0x180004fc9  nop     dword ptr [rax+rax+00h]
0x180004fce  mov     rcx, [rbp+phKey]; hKey
0x180004fd2  test    rcx, rcx
0x180004fd5  jz      short loc_180004FEB
0x180004fd7  call    cs:__imp_BCryptDestroyKey
0x180004fde  nop     dword ptr [rax+rax+00h]
0x180004fe3  mov     [rbp+phKey], 0
0x180004feb  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180004fef  test    rcx, rcx
0x180004ff2  jz      short loc_180005002
0x180004ff4  xor     edx, edx; dwFlags
0x180004ff6  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180004ffd  nop     dword ptr [rax+rax+00h]
0x180005002  lea     r11, [rsp+50h+var_s0]
0x180005007  mov     eax, esi
0x180005009  mov     rbx, [r11+20h]
0x18000500d  mov     rsi, [r11+30h]
0x180005011  mov     rsp, r11
0x180005014  pop     r14
0x180005016  pop     rdi
0x180005017  pop     rbp
0x180005018  retn
```
