# GenerateHashKey

- ea: `0x180053f5c`
- end: `0x180054124`
- name: `GenerateHashKey`
- size: `456`
- prototype: `__int64 __fastcall(ULONG cbInput, PUCHAR pbInput)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180019be4`

## callees

- `0x180004c64`
- `0x180012dcc`
- `0x180034744`
- `0x18004b5f0`
- `0x180053f5c`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180053fc0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180053fc0`
- `bcrypt!BCryptGetProperty` at `0x180053ff4`
- `bcrypt!BCryptGetProperty` at `0x180053ff4`
- `bcrypt!BCryptCreateHash` at `0x18005404a`
- `bcrypt!BCryptCreateHash` at `0x18005404a`
- `bcrypt!BCryptHashData` at `0x180054067`
- `bcrypt!BCryptHashData` at `0x180054067`
- `bcrypt!BCryptFinishHash` at `0x180054086`
- `bcrypt!BCryptFinishHash` at `0x180054086`
- `bcrypt!BCryptDestroyHash` at `0x1800540ce`
- `bcrypt!BCryptDestroyHash` at `0x1800540ce`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800540f2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800540f2`

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
0x180053f5c  mov     [rsp-8+arg_18], rbx
0x180053f61  push    rbp
0x180053f62  push    rsi
0x180053f63  push    rdi
0x180053f64  push    r14
0x180053f66  push    r15
0x180053f68  lea     rbp, [rsp-37h]
0x180053f6d  sub     rsp, 90h
0x180053f74  mov     rax, cs:__security_cookie
0x180053f7b  xor     rax, rsp
0x180053f7e  mov     [rbp+57h+var_30], rax
0x180053f82  mov     r15, r8
0x180053f85  mov     [rbp+57h+phAlgorithm], 0
0x180053f8d  mov     r14, rdx
0x180053f90  mov     [rbp+57h+phHash], 0
0x180053f98  mov     ebx, ecx
0x180053f9a  mov     [rbp+57h+var_58], 0
0x180053fa1  xor     r8d, r8d; pszImplementation
0x180053fa4  mov     dword ptr [rbp+57h+pbOutput], 0
0x180053fab  lea     rdx, pszAlgId; "SHA256"
0x180053fb2  xor     r9d, r9d; dwFlags
0x180053fb5  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180053fb9  xor     edi, edi
0x180053fbb  mov     esi, 8000FFFFh
0x180053fc0  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180053fc7  nop     dword ptr [rax+rax+00h]
0x180053fcc  test    eax, eax
0x180053fce  js      loc_1800540C5
0x180053fd4  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x180053fd8  lea     rax, [rbp+57h+var_58]
0x180053fdc  mov     [rsp+0B0h+dwFlags], edi; dwFlags
0x180053fe0  lea     r9d, [rdi+4]; cbOutput
0x180053fe4  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180053fe8  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x180053fed  lea     rdx, pszProperty; "ObjectLength"
0x180053ff4  call    cs:__imp_BCryptGetProperty
0x180053ffb  nop     dword ptr [rax+rax+00h]
0x180054000  test    eax, eax
0x180054002  js      loc_1800540C5
0x180054008  mov     ecx, dword ptr [rbp+57h+pbOutput]; dwBytes
0x18005400b  call    MALLOC
0x180054010  mov     rdi, rax
0x180054013  test    rax, rax
0x180054016  jnz     short loc_180054022
0x180054018  mov     esi, 8007000Eh
0x18005401d  jmp     loc_1800540C5
0x180054022  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x180054026  lea     rdx, [rbp+57h+phHash]; phHash
0x18005402a  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18005402e  mov     r8, rax; pbHashObject
0x180054031  mov     [rsp+0B0h+var_80], 0; dwFlags
0x180054039  mov     [rsp+0B0h+dwFlags], 0; cbSecret
0x180054041  mov     [rsp+0B0h+pcbResult], 0; pbSecret
0x18005404a  call    cs:__imp_BCryptCreateHash
0x180054051  nop     dword ptr [rax+rax+00h]
0x180054056  test    eax, eax
0x180054058  js      short loc_1800540C5
0x18005405a  mov     rcx, [rbp+57h+phHash]; hHash
0x18005405e  xor     r9d, r9d; dwFlags
0x180054061  mov     r8d, ebx; cbInput
0x180054064  mov     rdx, r14; pbInput
0x180054067  call    cs:__imp_BCryptHashData
0x18005406e  nop     dword ptr [rax+rax+00h]
0x180054073  test    eax, eax
0x180054075  js      short loc_1800540C5
0x180054077  mov     rcx, [rbp+57h+phHash]; hHash
0x18005407b  lea     rdx, [rbp+57h+var_50]; pbOutput
0x18005407f  xor     r9d, r9d; dwFlags
0x180054082  lea     r8d, [r9+20h]; cbOutput
0x180054086  call    cs:__imp_BCryptFinishHash
0x18005408d  nop     dword ptr [rax+rax+00h]
0x180054092  test    eax, eax
0x180054094  js      short loc_1800540C5
0x180054096  xor     ebx, ebx
0x180054098  movzx   r9d, [rbp+rbx+57h+var_50]
0x18005409e  lea     ecx, [rbx+rbx]
0x1800540a1  mov     edx, 41h ; 'A'
0x1800540a6  lea     r8, a0x; "%0X"
0x1800540ad  sub     edx, ecx; cchDest
0x1800540af  lea     rcx, [r15+rcx*2]; pszDest
0x1800540b3  call    StringCchPrintfW
0x1800540b8  mov     esi, eax
0x1800540ba  test    eax, eax
0x1800540bc  jnz     short loc_1800540C5
0x1800540be  inc     ebx
0x1800540c0  cmp     ebx, 20h ; ' '
0x1800540c3  jb      short loc_180054098
0x1800540c5  mov     rcx, [rbp+57h+phHash]; hHash
0x1800540c9  test    rcx, rcx
0x1800540cc  jz      short loc_1800540DA
0x1800540ce  call    cs:__imp_BCryptDestroyHash
0x1800540d5  nop     dword ptr [rax+rax+00h]
0x1800540da  test    rdi, rdi
0x1800540dd  jz      short loc_1800540E7
0x1800540df  mov     rcx, rdi
0x1800540e2  call    FREE
0x1800540e7  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800540eb  test    rcx, rcx
0x1800540ee  jz      short loc_1800540FE
0x1800540f0  xor     edx, edx; dwFlags
0x1800540f2  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800540f9  nop     dword ptr [rax+rax+00h]
0x1800540fe  mov     eax, esi
0x180054100  mov     rcx, [rbp+57h+var_30]
0x180054104  xor     rcx, rsp; StackCookie
0x180054107  call    __security_check_cookie
0x18005410c  mov     rbx, [rsp+0B0h+arg_18]
0x180054114  add     rsp, 90h
0x18005411b  pop     r15
0x18005411d  pop     r14
0x18005411f  pop     rdi
0x180054120  pop     rsi
0x180054121  pop     rbp
0x180054122  retn
```
