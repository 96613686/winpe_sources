# GenerateHashKey

- ea: `0x180053f38`
- end: `0x180054100`
- name: `GenerateHashKey`
- size: `456`
- prototype: `__int64 __fastcall(ULONG cbInput, PUCHAR pbInput)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180019bd4`

## callees

- `0x180004c54`
- `0x180012dbc`
- `0x180034734`
- `0x18004b630`
- `0x180053f38`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180053f9c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180053f9c`
- `bcrypt!BCryptGetProperty` at `0x180053fd0`
- `bcrypt!BCryptGetProperty` at `0x180053fd0`
- `bcrypt!BCryptCreateHash` at `0x180054026`
- `bcrypt!BCryptCreateHash` at `0x180054026`
- `bcrypt!BCryptHashData` at `0x180054043`
- `bcrypt!BCryptHashData` at `0x180054043`
- `bcrypt!BCryptFinishHash` at `0x180054062`
- `bcrypt!BCryptFinishHash` at `0x180054062`
- `bcrypt!BCryptDestroyHash` at `0x1800540aa`
- `bcrypt!BCryptDestroyHash` at `0x1800540aa`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800540ce`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800540ce`

## pseudocode

```c
__int64 __fastcall GenerateHashKey(ULONG cbInput, PUCHAR pbInput, __int64 a3)
{
  UCHAR *v6; // rdi
  unsigned int v7; // esi
  UCHAR *v8; // rax
  __int64 v9; // rbx
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-19h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-11h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-9h] BYREF
  ULONG pcbResult; // [rsp+58h] [rbp-1h] BYREF
  UCHAR v15[32]; // [rsp+60h] [rbp+7h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pcbResult = 0;
  *(_DWORD *)pbOutput = 0;
  v6 = 0;
  v7 = -2147418113;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0) >= 0
    && BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0) >= 0 )
  {
    v8 = (UCHAR *)MALLOC(*(unsigned int *)pbOutput);
    v6 = v8;
    if ( v8 )
    {
      if ( BCryptCreateHash(phAlgorithm, &phHash, v8, *(ULONG *)pbOutput, 0, 0, 0) >= 0
        && BCryptHashData(phHash, pbInput, cbInput, 0) >= 0
        && BCryptFinishHash(phHash, v15, 0x20u, 0) >= 0 )
      {
        v9 = 0;
        do
        {
          v7 = StringCchPrintfW(
                 (STRSAFE_LPWSTR)(a3 + 2LL * (unsigned int)(2 * v9)),
                 (unsigned int)(65 - 2 * v9),
                 L"%0X",
                 v15[v9]);
          if ( v7 )
            break;
          v9 = (unsigned int)(v9 + 1);
        }
        while ( (unsigned int)v9 < 0x20 );
      }
    }
    else
    {
      v7 = -2147024882;
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v6 )
    FREE(v6);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v7;
}

```

## disassembly

```asm
0x180053f38  mov     [rsp-8+arg_18], rbx
0x180053f3d  push    rbp
0x180053f3e  push    rsi
0x180053f3f  push    rdi
0x180053f40  push    r14
0x180053f42  push    r15
0x180053f44  lea     rbp, [rsp-37h]
0x180053f49  sub     rsp, 90h
0x180053f50  mov     rax, cs:__security_cookie
0x180053f57  xor     rax, rsp
0x180053f5a  mov     [rbp+57h+var_30], rax
0x180053f5e  mov     r15, r8
0x180053f61  mov     [rbp+57h+phAlgorithm], 0
0x180053f69  mov     r14, rdx
0x180053f6c  mov     [rbp+57h+phHash], 0
0x180053f74  mov     ebx, ecx
0x180053f76  mov     [rbp+57h+var_58], 0
0x180053f7d  xor     r8d, r8d; pszImplementation
0x180053f80  mov     dword ptr [rbp+57h+pbOutput], 0
0x180053f87  lea     rdx, pszAlgId; "SHA256"
0x180053f8e  xor     r9d, r9d; dwFlags
0x180053f91  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180053f95  xor     edi, edi
0x180053f97  mov     esi, 8000FFFFh
0x180053f9c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180053fa3  nop     dword ptr [rax+rax+00h]
0x180053fa8  test    eax, eax
0x180053faa  js      loc_1800540A1
0x180053fb0  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x180053fb4  lea     rax, [rbp+57h+var_58]
0x180053fb8  mov     [rsp+0B0h+dwFlags], edi; dwFlags
0x180053fbc  lea     r9d, [rdi+4]; cbOutput
0x180053fc0  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180053fc4  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x180053fc9  lea     rdx, pszProperty; "ObjectLength"
0x180053fd0  call    cs:__imp_BCryptGetProperty
0x180053fd7  nop     dword ptr [rax+rax+00h]
0x180053fdc  test    eax, eax
0x180053fde  js      loc_1800540A1
0x180053fe4  mov     ecx, dword ptr [rbp+57h+pbOutput]; dwBytes
0x180053fe7  call    MALLOC
0x180053fec  mov     rdi, rax
0x180053fef  test    rax, rax
0x180053ff2  jnz     short loc_180053FFE
0x180053ff4  mov     esi, 8007000Eh
0x180053ff9  jmp     loc_1800540A1
0x180053ffe  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x180054002  lea     rdx, [rbp+57h+phHash]; phHash
0x180054006  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18005400a  mov     r8, rax; pbHashObject
0x18005400d  mov     [rsp+0B0h+var_80], 0; dwFlags
0x180054015  mov     [rsp+0B0h+dwFlags], 0; cbSecret
0x18005401d  mov     [rsp+0B0h+pcbResult], 0; pbSecret
0x180054026  call    cs:__imp_BCryptCreateHash
0x18005402d  nop     dword ptr [rax+rax+00h]
0x180054032  test    eax, eax
0x180054034  js      short loc_1800540A1
0x180054036  mov     rcx, [rbp+57h+phHash]; hHash
0x18005403a  xor     r9d, r9d; dwFlags
0x18005403d  mov     r8d, ebx; cbInput
0x180054040  mov     rdx, r14; pbInput
0x180054043  call    cs:__imp_BCryptHashData
0x18005404a  nop     dword ptr [rax+rax+00h]
0x18005404f  test    eax, eax
0x180054051  js      short loc_1800540A1
0x180054053  mov     rcx, [rbp+57h+phHash]; hHash
0x180054057  lea     rdx, [rbp+57h+var_50]; pbOutput
0x18005405b  xor     r9d, r9d; dwFlags
0x18005405e  lea     r8d, [r9+20h]; cbOutput
0x180054062  call    cs:__imp_BCryptFinishHash
0x180054069  nop     dword ptr [rax+rax+00h]
0x18005406e  test    eax, eax
0x180054070  js      short loc_1800540A1
0x180054072  xor     ebx, ebx
0x180054074  movzx   r9d, [rbp+rbx+57h+var_50]
0x18005407a  lea     ecx, [rbx+rbx]
0x18005407d  mov     edx, 41h ; 'A'
0x180054082  lea     r8, a0x; "%0X"
0x180054089  sub     edx, ecx; cchDest
0x18005408b  lea     rcx, [r15+rcx*2]; pszDest
0x18005408f  call    StringCchPrintfW
0x180054094  mov     esi, eax
0x180054096  test    eax, eax
0x180054098  jnz     short loc_1800540A1
0x18005409a  inc     ebx
0x18005409c  cmp     ebx, 20h ; ' '
0x18005409f  jb      short loc_180054074
0x1800540a1  mov     rcx, [rbp+57h+phHash]; hHash
0x1800540a5  test    rcx, rcx
0x1800540a8  jz      short loc_1800540B6
0x1800540aa  call    cs:__imp_BCryptDestroyHash
0x1800540b1  nop     dword ptr [rax+rax+00h]
0x1800540b6  test    rdi, rdi
0x1800540b9  jz      short loc_1800540C3
0x1800540bb  mov     rcx, rdi
0x1800540be  call    FREE
0x1800540c3  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800540c7  test    rcx, rcx
0x1800540ca  jz      short loc_1800540DA
0x1800540cc  xor     edx, edx; dwFlags
0x1800540ce  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800540d5  nop     dword ptr [rax+rax+00h]
0x1800540da  mov     eax, esi
0x1800540dc  mov     rcx, [rbp+57h+var_30]
0x1800540e0  xor     rcx, rsp; StackCookie
0x1800540e3  call    __security_check_cookie
0x1800540e8  mov     rbx, [rsp+0B0h+arg_18]
0x1800540f0  add     rsp, 90h
0x1800540f7  pop     r15
0x1800540f9  pop     r14
0x1800540fb  pop     rdi
0x1800540fc  pop     rsi
0x1800540fd  pop     rbp
0x1800540fe  retn
```
