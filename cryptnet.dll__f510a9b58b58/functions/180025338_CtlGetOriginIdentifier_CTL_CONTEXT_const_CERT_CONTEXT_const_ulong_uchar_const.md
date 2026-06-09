# CtlGetOriginIdentifier(_CTL_CONTEXT const *,_CERT_CONTEXT const *,ulong,uchar * const)

- ea: `0x180025338`
- end: `0x18002547a`
- name: `?CtlGetOriginIdentifier@@YAHPEBU_CTL_CONTEXT@@PEBU_CERT_CONTEXT@@KQEAE@Z`
- size: `322`
- prototype: `__int64 __fastcall(const struct _CTL_CONTEXT *, const struct _CERT_CONTEXT *, __int64, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cfa0`
- `0x180018ff8`

## callees

- `0x180025338`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180025398`
- `bcrypt!BCryptHashData` at `0x1800253b6`
- `bcrypt!BCryptHashData` at `0x1800253f3`
- `bcrypt!BCryptHashData` at `0x180025411`
- `bcrypt!BCryptHashData` at `0x18002542e`
- `bcrypt!BCryptHashData` at `0x180025398`
- `bcrypt!BCryptHashData` at `0x1800253b6`
- `bcrypt!BCryptHashData` at `0x1800253f3`
- `bcrypt!BCryptHashData` at `0x180025411`
- `bcrypt!BCryptHashData` at `0x18002542e`
- `bcrypt!BCryptDestroyHash` at `0x180025466`
- `bcrypt!BCryptDestroyHash` at `0x180025466`
- `bcrypt!BCryptFinishHash` at `0x180025447`
- `bcrypt!BCryptFinishHash` at `0x180025447`
- `bcrypt!BCryptCreateHash` at `0x18002537a`
- `bcrypt!BCryptCreateHash` at `0x18002537a`

## pseudocode

```c
__int64 __fastcall CtlGetOriginIdentifier(
        const struct _CTL_CONTEXT *a1,
        const struct _CERT_CONTEXT *a2,
        __int64 a3,
        unsigned __int8 *const a4)
{
  PCTL_INFO pCtlInfo; // rsi
  PCERT_INFO pCertInfo; // rdi
  __int64 i; // rbx
  UCHAR *v8; // rdx
  __int64 v9; // r8
  BCRYPT_HASH_HANDLE hHash; // [rsp+70h] [rbp+8h] BYREF

  pCtlInfo = a1->pCtlInfo;
  pCertInfo = a2->pCertInfo;
  hHash = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &hHash, 0, 0, 0, 0, 0)
    || BCryptHashData(hHash, pCertInfo->Subject.pbData, pCertInfo->Subject.cbData, 0)
    || BCryptHashData(hHash, pCertInfo->SerialNumber.pbData, pCertInfo->SerialNumber.cbData, 0) )
  {
    goto LABEL_16;
  }
  for ( i = 0; (unsigned int)i < pCtlInfo->SubjectUsage.cUsageIdentifier; i = (unsigned int)(i + 1) )
  {
    v8 = (UCHAR *)pCtlInfo->SubjectUsage.rgpszUsageIdentifier[i];
    if ( v8 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
    }
    else
    {
      LODWORD(v9) = 0;
    }
    if ( BCryptHashData(hHash, v8, v9, 0) )
      goto LABEL_16;
  }
  if ( BCryptHashData(hHash, pCtlInfo->ListIdentifier.pbData, pCtlInfo->ListIdentifier.cbData, 0)
    || BCryptHashData(
         hHash,
         pCertInfo->SubjectPublicKeyInfo.PublicKey.pbData,
         pCertInfo->SubjectPublicKeyInfo.PublicKey.cbData,
         0)
    || BCryptFinishHash(hHash, a4, 0x20u, 0) )
  {
LABEL_16:
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
0x180025338  mov     rax, rsp
0x18002533b  push    rbx
0x18002533c  push    rbp
0x18002533d  push    rsi
0x18002533e  push    rdi
0x18002533f  sub     rsp, 48h
0x180025343  mov     rsi, [rcx+18h]
0x180025347  mov     rbp, r9
0x18002534a  mov     rdi, [rdx+18h]
0x18002534e  xor     r9d, r9d; cbHashObject
0x180025351  mov     dword ptr [rax-38h], 0
0x180025358  lea     rdx, [rax+8]; phHash
0x18002535c  mov     dword ptr [rax-40h], 0
0x180025363  xor     r8d, r8d; pbHashObject
0x180025366  mov     qword ptr [rax+8], 0
0x18002536e  lea     ecx, [r9+41h]; hAlgorithm
0x180025372  mov     qword ptr [rax-48h], 0
0x18002537a  call    cs:__imp_BCryptCreateHash
0x180025380  test    eax, eax
0x180025382  jnz     loc_180025451
0x180025388  mov     r8d, [rdi+50h]; cbInput
0x18002538c  xor     r9d, r9d; dwFlags
0x18002538f  mov     rdx, [rdi+58h]; pbInput
0x180025393  mov     rcx, [rsp+68h+hHash]; hHash
0x180025398  call    cs:__imp_BCryptHashData
0x18002539e  test    eax, eax
0x1800253a0  jnz     loc_180025451
0x1800253a6  mov     r8d, [rdi+8]; cbInput
0x1800253aa  xor     r9d, r9d; dwFlags
0x1800253ad  mov     rdx, [rdi+10h]; pbInput
0x1800253b1  mov     rcx, [rsp+68h+hHash]; hHash
0x1800253b6  call    cs:__imp_BCryptHashData
0x1800253bc  test    eax, eax
0x1800253be  jnz     loc_180025451
0x1800253c4  xor     ebx, ebx
0x1800253c6  cmp     ebx, [rsi+8]
0x1800253c9  jnb     short loc_180025401
0x1800253cb  mov     rax, [rsi+10h]
0x1800253cf  mov     rdx, [rax+rbx*8]; pbInput
0x1800253d3  test    rdx, rdx
0x1800253d6  jz      short loc_1800253E8
0x1800253d8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800253dc  inc     r8
0x1800253df  cmp     byte ptr [rdx+r8], 0
0x1800253e4  jnz     short loc_1800253DC
0x1800253e6  jmp     short loc_1800253EB
0x1800253e8  xor     r8d, r8d; cbInput
0x1800253eb  mov     rcx, [rsp+68h+hHash]; hHash
0x1800253f0  xor     r9d, r9d; dwFlags
0x1800253f3  call    cs:__imp_BCryptHashData
0x1800253f9  test    eax, eax
0x1800253fb  jnz     short loc_180025451
0x1800253fd  inc     ebx
0x1800253ff  jmp     short loc_1800253C6
0x180025401  mov     r8d, [rsi+18h]; cbInput
0x180025405  xor     r9d, r9d; dwFlags
0x180025408  mov     rdx, [rsi+20h]; pbInput
0x18002540c  mov     rcx, [rsp+68h+hHash]; hHash
0x180025411  call    cs:__imp_BCryptHashData
0x180025417  test    eax, eax
0x180025419  jnz     short loc_180025451
0x18002541b  mov     r8d, [rdi+78h]; cbInput
0x18002541f  xor     r9d, r9d; dwFlags
0x180025422  mov     rdx, [rdi+80h]; pbInput
0x180025429  mov     rcx, [rsp+68h+hHash]; hHash
0x18002542e  call    cs:__imp_BCryptHashData
0x180025434  test    eax, eax
0x180025436  jnz     short loc_180025451
0x180025438  mov     rcx, [rsp+68h+hHash]; hHash
0x18002543d  lea     r8d, [rax+20h]; cbOutput
0x180025441  xor     r9d, r9d; dwFlags
0x180025444  mov     rdx, rbp; pbOutput
0x180025447  call    cs:__imp_BCryptFinishHash
0x18002544d  test    eax, eax
0x18002544f  jz      short loc_18002545C
0x180025451  xorps   xmm0, xmm0
0x180025454  movups  xmmword ptr [rbp+0], xmm0
0x180025458  movups  xmmword ptr [rbp+10h], xmm0
0x18002545c  mov     rcx, [rsp+68h+hHash]; hHash
0x180025461  test    rcx, rcx
0x180025464  jz      short loc_18002546C
0x180025466  call    cs:__imp_BCryptDestroyHash
0x18002546c  mov     eax, 1
0x180025471  add     rsp, 48h
0x180025475  pop     rdi
0x180025476  pop     rsi
0x180025477  pop     rbp
0x180025478  pop     rbx
0x180025479  retn
```
