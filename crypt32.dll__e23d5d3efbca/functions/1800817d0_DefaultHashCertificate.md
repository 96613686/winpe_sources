# DefaultHashCertificate

- ea: `0x1800817d0`
- end: `0x1800819bf`
- name: `DefaultHashCertificate`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002a150`

## callees

- `0x1800817d0`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008198d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008198d`
- `bcrypt!BCryptFinishHash` at `0x180081888`
- `bcrypt!BCryptFinishHash` at `0x180081963`
- `bcrypt!BCryptFinishHash` at `0x180081888`
- `bcrypt!BCryptFinishHash` at `0x180081963`
- `bcrypt!BCryptDestroyHash` at `0x18008189a`
- `bcrypt!BCryptDestroyHash` at `0x18008194b`
- `bcrypt!BCryptDestroyHash` at `0x18008189a`
- `bcrypt!BCryptDestroyHash` at `0x18008194b`
- `bcrypt!BCryptHashData` at `0x18008186c`
- `bcrypt!BCryptHashData` at `0x180081933`
- `bcrypt!BCryptHashData` at `0x18008186c`
- `bcrypt!BCryptHashData` at `0x180081933`
- `bcrypt!BCryptCreateHash` at `0x180081849`
- `bcrypt!BCryptCreateHash` at `0x180081914`
- `bcrypt!BCryptCreateHash` at `0x180081849`
- `bcrypt!BCryptCreateHash` at `0x180081914`

## pseudocode

```c
__int64 __fastcall DefaultHashCertificate(int a1, UCHAR *a2, ULONG a3, __int64 a4, unsigned int *a5)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-30h] BYREF
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v13; // [rsp+58h] [rbp-18h]

  if ( a4 )
    v8 = *a5;
  else
    v8 = 0;
  if ( a1 == 32771 )
  {
    v9 = 16;
    if ( v8 >= 0x10 )
    {
      v13 = 0;
      *(_OWORD *)phHash = 0;
      if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
        __fastfail(7u);
      if ( a3 && BCryptHashData(phHash[0], a2, a3, 0) < 0 )
        __fastfail(7u);
      if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash[0]);
      *(BCRYPT_HASH_HANDLE *)a4 = phHash[1];
      *(_QWORD *)(a4 + 8) = v13;
LABEL_10:
      *a5 = v9;
      return 1;
    }
  }
  else
  {
    v9 = 20;
    if ( v8 >= 0x14 )
    {
      hHash = 0;
      if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &hHash, 0, 0, 0, 0, 0) < 0 )
        __fastfail(7u);
      if ( a3 && BCryptHashData(hHash, a2, a3, 0) < 0 )
        __fastfail(7u);
      if ( a4 && BCryptFinishHash(hHash, (PUCHAR)a4, 0x14u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(hHash);
      goto LABEL_10;
    }
  }
  *a5 = v9;
  if ( v8 >= v9 || !a4 )
    return 1;
  SetLastError(0xEAu);
  return 0;
}

```

## disassembly

```asm
0x1800817d0  push    rbp
0x1800817d2  push    rbx
0x1800817d3  push    rsi
0x1800817d4  push    rdi
0x1800817d5  push    r12
0x1800817d7  push    r14
0x1800817d9  push    r15
0x1800817db  mov     rbp, rsp
0x1800817de  sub     rsp, 70h
0x1800817e2  mov     rax, cs:__security_cookie
0x1800817e9  xor     rax, rsp
0x1800817ec  mov     [rbp+var_10], rax
0x1800817f0  mov     r14, [rbp+arg_20]
0x1800817f4  mov     rsi, r9
0x1800817f7  mov     r15d, r8d
0x1800817fa  mov     r12, rdx
0x1800817fd  test    r9, r9
0x180081800  jz      loc_1800818D2
0x180081806  mov     eax, [r14]
0x180081809  cmp     ecx, 8003h
0x18008180f  jnz     loc_1800818D9
0x180081815  mov     ebx, 10h
0x18008181a  cmp     eax, ebx
0x18008181c  jb      loc_180081974
0x180081822  xor     eax, eax
0x180081824  lea     rdx, [rbp+phHash]; phHash
0x180081828  mov     [rsp+70h+dwFlags], eax; dwFlags
0x18008182c  lea     ecx, [rbx+11h]; hAlgorithm
0x18008182f  xorps   xmm0, xmm0
0x180081832  mov     [rsp+70h+cbSecret], eax; cbSecret
0x180081836  xor     r9d, r9d; cbHashObject
0x180081839  mov     [rsp+70h+pbSecret], rax; pbSecret
0x18008183e  xor     r8d, r8d; pbHashObject
0x180081841  mov     [rbp+var_18], rax
0x180081845  movups  xmmword ptr [rbp+phHash], xmm0
0x180081849  call    cs:__imp_BCryptCreateHash
0x18008184f  lea     edi, [rbx-9]
0x180081852  test    eax, eax
0x180081854  js      loc_1800819A1
0x18008185a  test    r15d, r15d
0x18008185d  jz      short loc_18008187A
0x18008185f  mov     rcx, [rbp+phHash]; hHash
0x180081863  xor     r9d, r9d; dwFlags
0x180081866  mov     r8d, r15d; cbInput
0x180081869  mov     rdx, r12; pbInput
0x18008186c  call    cs:__imp_BCryptHashData
0x180081872  test    eax, eax
0x180081874  js      loc_1800819AB
0x18008187a  mov     rcx, [rbp+phHash]; hHash
0x18008187e  lea     rdx, [rbp+phHash+8]; pbOutput
0x180081882  xor     r9d, r9d; dwFlags
0x180081885  mov     r8d, ebx; cbOutput
0x180081888  call    cs:__imp_BCryptFinishHash
0x18008188e  test    eax, eax
0x180081890  js      loc_1800819B5
0x180081896  mov     rcx, [rbp+phHash]; hHash
0x18008189a  call    cs:__imp_BCryptDestroyHash
0x1800818a0  mov     rax, [rbp+phHash+8]
0x1800818a4  mov     [rsi], rax
0x1800818a7  mov     rax, [rbp+var_18]
0x1800818ab  mov     [rsi+8], rax
0x1800818af  mov     [r14], ebx
0x1800818b2  mov     eax, 1
0x1800818b7  mov     rcx, [rbp+var_10]
0x1800818bb  xor     rcx, rsp; StackCookie
0x1800818be  call    __security_check_cookie
0x1800818c3  add     rsp, 70h
0x1800818c7  pop     r15
0x1800818c9  pop     r14
0x1800818cb  pop     r12
0x1800818cd  pop     rdi
0x1800818ce  pop     rsi
0x1800818cf  pop     rbx
0x1800818d0  pop     rbp
0x1800818d1  retn
0x1800818d2  xor     eax, eax
0x1800818d4  jmp     loc_180081809
0x1800818d9  mov     ebx, 14h
0x1800818de  cmp     eax, ebx
0x1800818e0  jb      loc_180081974
0x1800818e6  mov     [rsp+70h+dwFlags], 0; dwFlags
0x1800818ee  lea     rdx, [rbp+hHash]; phHash
0x1800818f2  mov     [rsp+70h+cbSecret], 0; cbSecret
0x1800818fa  lea     ecx, [rbx+1Dh]; hAlgorithm
0x1800818fd  xor     r9d, r9d; cbHashObject
0x180081900  mov     [rsp+70h+pbSecret], 0; pbSecret
0x180081909  xor     r8d, r8d; pbHashObject
0x18008190c  mov     [rbp+hHash], 0
0x180081914  call    cs:__imp_BCryptCreateHash
0x18008191a  lea     edi, [rbx-0Dh]
0x18008191d  test    eax, eax
0x18008191f  js      short loc_18008199A
0x180081921  test    r15d, r15d
0x180081924  jz      short loc_180081942
0x180081926  mov     rcx, [rbp+hHash]; hHash
0x18008192a  xor     r9d, r9d; dwFlags
0x18008192d  mov     r8d, r15d; cbInput
0x180081930  mov     rdx, r12; pbInput
0x180081933  call    cs:__imp_BCryptHashData
0x180081939  test    eax, eax
0x18008193b  jns     short loc_180081942
0x18008193d  mov     rcx, rdi
0x180081940  int     29h; Win8: RtlFailFast(ecx)
0x180081942  test    rsi, rsi
0x180081945  jnz     short loc_180081956
0x180081947  mov     rcx, [rbp+hHash]; hHash
0x18008194b  call    cs:__imp_BCryptDestroyHash
0x180081951  jmp     loc_1800818AF
0x180081956  mov     rcx, [rbp+hHash]; hHash
0x18008195a  xor     r9d, r9d; dwFlags
0x18008195d  mov     r8d, ebx; cbOutput
0x180081960  mov     rdx, rsi; pbOutput
0x180081963  call    cs:__imp_BCryptFinishHash
0x180081969  test    eax, eax
0x18008196b  jns     short loc_180081947
0x18008196d  mov     rcx, rdi
0x180081970  int     29h; Win8: RtlFailFast(ecx)
0x180081972  jmp     short loc_180081947
0x180081974  mov     [r14], ebx
0x180081977  cmp     eax, ebx
0x180081979  jnb     loc_1800818B2
0x18008197f  test    rsi, rsi
0x180081982  jz      loc_1800818B2
0x180081988  mov     ecx, 0EAh; dwErrCode
0x18008198d  call    cs:__imp_SetLastError
0x180081993  xor     eax, eax
0x180081995  jmp     loc_1800818B7
0x18008199a  mov     rcx, rdi
0x18008199d  int     29h; Win8: RtlFailFast(ecx)
0x18008199f  jmp     short loc_180081921
0x1800819a1  mov     rcx, rdi
0x1800819a4  int     29h; Win8: RtlFailFast(ecx)
0x1800819a6  jmp     loc_18008185A
0x1800819ab  mov     rcx, rdi
0x1800819ae  int     29h; Win8: RtlFailFast(ecx)
0x1800819b0  jmp     loc_18008187A
0x1800819b5  mov     rcx, rdi
0x1800819b8  int     29h; Win8: RtlFailFast(ecx)
0x1800819ba  jmp     loc_180081896
```
