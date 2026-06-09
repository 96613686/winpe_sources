# ComputePasswordHash

- ea: `0x1800038ac`
- end: `0x1800039ce`
- name: `ComputePasswordHash`
- size: `290`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003e20`
- `0x180004350`

## callees

- `0x1800037f4`
- `0x18000383c`
- `0x180003884`
- `0x1800038ac`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18000395f`
- `bcrypt!BCryptDestroyHash` at `0x18000395f`
- `bcrypt!BCryptFinishHash` at `0x18000394c`
- `bcrypt!BCryptFinishHash` at `0x18000394c`
- `bcrypt!BCryptHashData` at `0x18000392a`
- `bcrypt!BCryptHashData` at `0x18000392a`
- `bcrypt!BCryptCreateHash` at `0x180003908`
- `bcrypt!BCryptCreateHash` at `0x180003908`

## pseudocode

```c
void __fastcall ComputePasswordHash(int a1, UCHAR *a2, ULONG a3, UCHAR *a4)
{
  __int64 v7; // rax
  BCRYPT_HASH_HANDLE *v8; // rcx
  __int64 v9; // rax
  BCRYPT_HASH_HANDLE *v10; // rcx
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+40h] [rbp-10h] BYREF

  phHash[0] = 0;
  if ( a1 == 32782 )
  {
    if ( a2 )
    {
      if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x61, phHash, 0, 0, 0, 0, 0) < 0 )
        __fastfail(7u);
      if ( BCryptHashData(phHash[0], a2, a3, 0) < 0 )
        __fastfail(7u);
      if ( a4 && BCryptFinishHash(phHash[0], a4, 0x40u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash[0]);
      v7 = 8;
      phHash[0] = 0;
      v8 = phHash;
      do
      {
        *(_BYTE *)v8 = 0;
        v8 = (BCRYPT_HASH_HANDLE *)((char *)v8 + 1);
        --v7;
      }
      while ( v7 );
    }
  }
  else if ( a2 )
  {
    CngRsa32Compat_SHAInit(phHash);
    CngRsa32Compat_SHAUpdate(phHash, a2, a3);
    CngRsa32Compat_SHAFinal(phHash, a4);
    v9 = 8;
    v10 = phHash;
    do
    {
      *(_BYTE *)v10 = 0;
      v10 = (BCRYPT_HASH_HANDLE *)((char *)v10 + 1);
      --v9;
    }
    while ( v9 );
  }
}

```

## disassembly

```asm
0x1800038ac  push    rbp
0x1800038ae  push    rsi
0x1800038af  push    rdi
0x1800038b0  push    r14
0x1800038b2  push    r15
0x1800038b4  mov     rbp, rsp
0x1800038b7  sub     rsp, 50h
0x1800038bb  mov     [rbp+phHash], 0
0x1800038c3  mov     rsi, r9
0x1800038c6  mov     r14d, r8d
0x1800038c9  mov     rdi, rdx
0x1800038cc  cmp     ecx, 800Eh
0x1800038d2  jnz     loc_180003984
0x1800038d8  test    rdx, rdx
0x1800038db  jz      loc_1800039C2
0x1800038e1  xor     r9d, r9d; cbHashObject
0x1800038e4  mov     [rsp+50h+dwFlags], 0; dwFlags
0x1800038ec  mov     [rsp+50h+cbSecret], 0; cbSecret
0x1800038f4  lea     rdx, [rbp+phHash]; phHash
0x1800038f8  xor     r8d, r8d; pbHashObject
0x1800038fb  mov     [rsp+50h+pbSecret], 0; pbSecret
0x180003904  lea     ecx, [r9+61h]; hAlgorithm
0x180003908  call    cs:__imp_BCryptCreateHash
0x18000390e  mov     r15d, 7
0x180003914  test    eax, eax
0x180003916  jns     short loc_18000391D
0x180003918  mov     ecx, r15d
0x18000391b  int     29h; Win8: RtlFailFast(ecx)
0x18000391d  mov     rcx, [rbp+phHash]; hHash
0x180003921  xor     r9d, r9d; dwFlags
0x180003924  mov     r8d, r14d; cbInput
0x180003927  mov     rdx, rdi; pbInput
0x18000392a  call    cs:__imp_BCryptHashData
0x180003930  test    eax, eax
0x180003932  jns     short loc_180003939
0x180003934  mov     rcx, r15
0x180003937  int     29h; Win8: RtlFailFast(ecx)
0x180003939  test    rsi, rsi
0x18000393c  jz      short loc_18000395B
0x18000393e  mov     rcx, [rbp+phHash]; hHash
0x180003942  xor     r9d, r9d; dwFlags
0x180003945  mov     rdx, rsi; pbOutput
0x180003948  lea     r8d, [r9+40h]; cbOutput
0x18000394c  call    cs:__imp_BCryptFinishHash
0x180003952  test    eax, eax
0x180003954  jns     short loc_18000395B
0x180003956  mov     rcx, r15
0x180003959  int     29h; Win8: RtlFailFast(ecx)
0x18000395b  mov     rcx, [rbp+phHash]; hHash
0x18000395f  call    cs:__imp_BCryptDestroyHash
0x180003965  mov     eax, 8
0x18000396a  mov     [rbp+phHash], 0
0x180003972  lea     rcx, [rbp+phHash]
0x180003976  mov     byte ptr [rcx], 0
0x180003979  inc     rcx
0x18000397c  sub     rax, 1
0x180003980  jnz     short loc_180003976
0x180003982  jmp     short loc_1800039C2
0x180003984  test    rdi, rdi
0x180003987  jz      short loc_1800039C2
0x180003989  lea     rcx, [rbp+phHash]; phHash
0x18000398d  call    CngRsa32Compat_SHAInit
0x180003992  mov     r8d, r14d
0x180003995  lea     rcx, [rbp+phHash]
0x180003999  mov     rdx, rdi
0x18000399c  call    CngRsa32Compat_SHAUpdate
0x1800039a1  mov     rdx, rsi
0x1800039a4  lea     rcx, [rbp+phHash]
0x1800039a8  call    CngRsa32Compat_SHAFinal
0x1800039ad  mov     eax, 8
0x1800039b2  lea     rcx, [rbp+phHash]
0x1800039b6  mov     byte ptr [rcx], 0
0x1800039b9  inc     rcx
0x1800039bc  sub     rax, 1
0x1800039c0  jnz     short loc_1800039B6
0x1800039c2  add     rsp, 50h
0x1800039c6  pop     r15
0x1800039c8  pop     r14
0x1800039ca  pop     rdi
0x1800039cb  pop     rsi
0x1800039cc  pop     rbp
0x1800039cd  retn
```
