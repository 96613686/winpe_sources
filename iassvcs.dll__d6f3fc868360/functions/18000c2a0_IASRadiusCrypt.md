# IASRadiusCrypt

- ea: `0x18000c2a0`
- end: `0x18000c460`
- name: `IASRadiusCrypt`
- size: `448`
- prototype: `char __fastcall(int, int, UCHAR *, ULONG, UCHAR *pbInput, PUCHAR, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c2a0`
- `0x1800181e0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000c36e`
- `bcrypt!BCryptHashData` at `0x18000c38d`
- `bcrypt!BCryptHashData` at `0x18000c3b1`
- `bcrypt!BCryptHashData` at `0x18000c36e`
- `bcrypt!BCryptHashData` at `0x18000c38d`
- `bcrypt!BCryptHashData` at `0x18000c3b1`
- `bcrypt!BCryptDestroyHash` at `0x18000c3e9`
- `bcrypt!BCryptDestroyHash` at `0x18000c3e9`
- `bcrypt!BCryptFinishHash` at `0x18000c3d4`
- `bcrypt!BCryptFinishHash` at `0x18000c3d4`
- `bcrypt!BCryptCreateHash` at `0x18000c34f`
- `bcrypt!BCryptCreateHash` at `0x18000c34f`

## pseudocode

```c
char __fastcall IASRadiusCrypt(int a1, int a2, UCHAR *a3, ULONG a4, UCHAR *pbInput, PUCHAR a6, int a7)
{
  __int16 v7; // ax
  unsigned __int64 v9; // rdi
  int v11; // r14d
  unsigned __int16 v13; // cx
  UCHAR *v14; // rbx
  UCHAR *v15; // rcx
  BCRYPT_HASH_HANDLE *v16; // rdx
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v20; // [rsp+58h] [rbp-28h]
  __int128 v21; // [rsp+60h] [rbp-20h] BYREF

  LOBYTE(v7) = 0;
  v9 = (unsigned __int64)&a6[a7];
  v20 = 0;
  v11 = a2;
  *(_OWORD *)phHash = 0;
  if ( a2 )
  {
    if ( a1 )
    {
      v13 = ++dword_180025828 | 0x8000;
      a6[1] = dword_180025828;
      v7 = HIBYTE(v13);
      *a6 = HIBYTE(v13);
    }
    v14 = a6 + 2;
  }
  else
  {
    v14 = a6;
  }
  while ( (unsigned __int64)v14 < v9 )
  {
    if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0) < 0 )
      __fastfail(7u);
    if ( BCryptHashData(phHash[0], a3, a4, 0) < 0 )
      __fastfail(7u);
    if ( BCryptHashData(phHash[0], pbInput, 0x10u, 0) < 0 )
      __fastfail(7u);
    if ( v11 )
    {
      if ( BCryptHashData(phHash[0], a6, 2u, 0) < 0 )
        __fastfail(7u);
      v11 = 0;
    }
    if ( BCryptFinishHash(phHash[0], (PUCHAR)&phHash[1], 0x10u, 0) < 0 )
      __fastfail(7u);
    LOBYTE(v7) = BCryptDestroyHash(phHash[0]);
    v15 = v14 + 16;
    phHash[0] = 0;
    if ( (unsigned __int64)(v14 + 16) < v9 )
    {
      if ( a1 )
      {
        pbInput = v14;
      }
      else
      {
        pbInput = (UCHAR *)&v21;
        v21 = *(_OWORD *)v14;
      }
    }
    else
    {
      v15 = &a6[a7];
    }
    v16 = &phHash[1];
    while ( v14 < v15 )
    {
      LOBYTE(v7) = *(_BYTE *)v16;
      v16 = (BCRYPT_HASH_HANDLE *)((char *)v16 + 1);
      *v14++ ^= v7;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000c2a0  mov     [rsp-38h+arg_0], rbx
0x18000c2a5  push    rbp
0x18000c2a6  push    rsi
0x18000c2a7  push    rdi
0x18000c2a8  push    r12
0x18000c2aa  push    r13
0x18000c2ac  push    r14
0x18000c2ae  push    r15
0x18000c2b0  mov     rbp, rsp
0x18000c2b3  sub     rsp, 80h
0x18000c2ba  mov     rax, cs:__security_cookie
0x18000c2c1  xor     rax, rsp
0x18000c2c4  mov     [rbp+var_10], rax
0x18000c2c8  mov     rsi, [rbp+arg_28]
0x18000c2cc  xor     eax, eax
0x18000c2ce  mov     edi, [rbp+arg_30]
0x18000c2d1  xorps   xmm0, xmm0
0x18000c2d4  mov     r15, [rbp+pbInput]
0x18000c2d8  add     rdi, rsi
0x18000c2db  mov     [rbp+cbInput], r9d
0x18000c2df  mov     r13, r8
0x18000c2e2  mov     [rbp+var_28], rax
0x18000c2e6  mov     r14d, edx
0x18000c2e9  mov     r12d, ecx
0x18000c2ec  movups  xmmword ptr [rbp+phHash], xmm0
0x18000c2f0  test    edx, edx
0x18000c2f2  jz      short loc_18000C320
0x18000c2f4  test    ecx, ecx
0x18000c2f6  jz      short loc_18000C317
0x18000c2f8  mov     ecx, cs:dword_180025828
0x18000c2fe  inc     ecx
0x18000c300  mov     cs:dword_180025828, ecx
0x18000c306  or      cx, 8000h
0x18000c30b  movzx   eax, cx
0x18000c30e  mov     [rsi+1], cl
0x18000c311  shr     ax, 8
0x18000c315  mov     [rsi], al
0x18000c317  lea     rbx, [rsi+2]
0x18000c31b  jmp     loc_18000C430
0x18000c320  mov     rbx, rsi
0x18000c323  jmp     loc_18000C430
0x18000c328  xor     r9d, r9d; cbHashObject
0x18000c32b  mov     [rsp+80h+dwFlags], 0; dwFlags
0x18000c333  mov     [rsp+80h+cbSecret], 0; cbSecret
0x18000c33b  lea     rdx, [rbp+phHash]; phHash
0x18000c33f  xor     r8d, r8d; pbHashObject
0x18000c342  mov     [rsp+80h+pbSecret], 0; pbSecret
0x18000c34b  lea     ecx, [r9+21h]; hAlgorithm
0x18000c34f  call    cs:__imp_BCryptCreateHash
0x18000c355  test    eax, eax
0x18000c357  jns     short loc_18000C360
0x18000c359  mov     ecx, 7
0x18000c35e  int     29h; Win8: RtlFailFast(ecx)
0x18000c360  mov     r8d, [rbp+cbInput]; cbInput
0x18000c364  xor     r9d, r9d; dwFlags
0x18000c367  mov     rcx, [rbp+phHash]; hHash
0x18000c36b  mov     rdx, r13; pbInput
0x18000c36e  call    cs:__imp_BCryptHashData
0x18000c374  test    eax, eax
0x18000c376  jns     short loc_18000C37F
0x18000c378  mov     ecx, 7
0x18000c37d  int     29h; Win8: RtlFailFast(ecx)
0x18000c37f  mov     rcx, [rbp+phHash]; hHash
0x18000c383  xor     r9d, r9d; dwFlags
0x18000c386  mov     rdx, r15; pbInput
0x18000c389  lea     r8d, [r9+10h]; cbInput
0x18000c38d  call    cs:__imp_BCryptHashData
0x18000c393  test    eax, eax
0x18000c395  jns     short loc_18000C39E
0x18000c397  mov     ecx, 7
0x18000c39c  int     29h; Win8: RtlFailFast(ecx)
0x18000c39e  test    r14d, r14d
0x18000c3a1  jz      short loc_18000C3C5
0x18000c3a3  mov     rcx, [rbp+phHash]; hHash
0x18000c3a7  xor     r9d, r9d; dwFlags
0x18000c3aa  mov     rdx, rsi; pbInput
0x18000c3ad  lea     r8d, [r9+2]; cbInput
0x18000c3b1  call    cs:__imp_BCryptHashData
0x18000c3b7  test    eax, eax
0x18000c3b9  jns     short loc_18000C3C2
0x18000c3bb  mov     ecx, 7
0x18000c3c0  int     29h; Win8: RtlFailFast(ecx)
0x18000c3c2  xor     r14d, r14d
0x18000c3c5  mov     rcx, [rbp+phHash]; hHash
0x18000c3c9  lea     rdx, [rbp+phHash+8]; pbOutput
0x18000c3cd  xor     r9d, r9d; dwFlags
0x18000c3d0  lea     r8d, [r9+10h]; cbOutput
0x18000c3d4  call    cs:__imp_BCryptFinishHash
0x18000c3da  test    eax, eax
0x18000c3dc  jns     short loc_18000C3E5
0x18000c3de  mov     ecx, 7
0x18000c3e3  int     29h; Win8: RtlFailFast(ecx)
0x18000c3e5  mov     rcx, [rbp+phHash]; hHash
0x18000c3e9  call    cs:__imp_BCryptDestroyHash
0x18000c3ef  lea     rcx, [rbx+10h]
0x18000c3f3  mov     [rbp+phHash], 0
0x18000c3fb  cmp     rcx, rdi
0x18000c3fe  jb      short loc_18000C405
0x18000c400  mov     rcx, rdi
0x18000c403  jmp     short loc_18000C41B
0x18000c405  test    r12d, r12d
0x18000c408  jz      short loc_18000C40F
0x18000c40a  mov     r15, rbx
0x18000c40d  jmp     short loc_18000C41B
0x18000c40f  movups  xmm0, xmmword ptr [rbx]
0x18000c412  lea     r15, [rbp+var_20]
0x18000c416  movdqu  [rbp+var_20], xmm0
0x18000c41b  lea     rdx, [rbp+phHash+8]
0x18000c41f  jmp     short loc_18000C42B
0x18000c421  mov     al, [rdx]
0x18000c423  inc     rdx
0x18000c426  xor     [rbx], al
0x18000c428  inc     rbx
0x18000c42b  cmp     rbx, rcx
0x18000c42e  jb      short loc_18000C421
0x18000c430  cmp     rbx, rdi
0x18000c433  jb      loc_18000C328
0x18000c439  mov     rcx, [rbp+var_10]
0x18000c43d  xor     rcx, rsp; StackCookie
0x18000c440  call    __security_check_cookie
0x18000c445  mov     rbx, [rsp+80h+arg_0]
0x18000c44d  add     rsp, 80h
0x18000c454  pop     r15
0x18000c456  pop     r14
0x18000c458  pop     r13
0x18000c45a  pop     r12
0x18000c45c  pop     rdi
0x18000c45d  pop     rsi
0x18000c45e  pop     rbp
0x18000c45f  retn
```
