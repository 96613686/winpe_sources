# MSCryptAesKeyUnwrapPad

- ea: `0x18007f298`
- end: `0x18007f64b`
- name: `MSCryptAesKeyUnwrapPad`
- size: `947`
- prototype: `__int64 __fastcall(__int64, void *, unsigned __int32 *, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18007e108`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180008850`
- `0x18007f298`
- `0x18007f654`
- `0x18009d820`
- `0x18009da40`

## string_xrefs

- `0x18007f2fb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18007f342`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18007f39c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18007f59b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptAesKeyUnwrapPad(
        __int64 a1,
        void *a2,
        unsigned __int32 *a3,
        unsigned __int64 *a4,
        unsigned int a5)
{
  _QWORD *v5; // rsi
  unsigned int v6; // r13d
  unsigned __int32 *v7; // r12
  __int64 v9; // rdi
  __int64 v10; // r15
  __int64 v11; // r9
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // r9
  __int64 v16; // rcx
  int v17; // eax
  unsigned __int64 v18; // rbx
  const void *v19; // rdx
  __int64 v20; // r12
  __int64 i; // r15
  __int64 v22; // rcx
  unsigned __int32 v23; // edx
  unsigned __int8 v24; // r8
  int v25; // edi
  char v26; // al
  void *v27; // rcx
  unsigned __int64 *v28; // rax
  unsigned __int64 **v29; // rax
  __int64 v30; // rcx
  _BYTE *v31; // rax
  int v33; // [rsp+50h] [rbp-51h] BYREF
  int v34; // [rsp+54h] [rbp-4Dh] BYREF
  int v35; // [rsp+58h] [rbp-49h]
  void *v36; // [rsp+60h] [rbp-41h]
  unsigned __int32 *v37; // [rsp+68h] [rbp-39h]
  int *v38; // [rsp+70h] [rbp-31h]
  unsigned __int64 *v39; // [rsp+78h] [rbp-29h] BYREF
  unsigned __int64 v40; // [rsp+80h] [rbp-21h] BYREF
  __int64 v41; // [rsp+88h] [rbp-19h]

  v5 = 0;
  v39 = a4;
  v34 = 0;
  v33 = 0;
  v6 = 0;
  v38 = &v33;
  v7 = a3;
  v37 = a3;
  v36 = a2;
  v35 = 0;
  v9 = 32;
  v10 = 8;
  if ( a1 )
  {
    if ( !a3 )
    {
      v11 = 617;
      goto LABEL_3;
    }
    v13 = MSCryptAesKeyUnwrapPadValidateInput(a1, a5);
    v12 = v13;
    if ( v13 < 0 )
    {
      DebugTraceError(
        (unsigned int)v13,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        624);
      v10 = 8;
      goto LABEL_36;
    }
    v14 = (a5 - 8) >> 3;
    v6 = 8 * v14;
    if ( !v36 )
    {
      *v7 = v6;
      v10 = 8;
LABEL_34:
      v12 = 0;
      goto LABEL_35;
    }
    if ( *v7 < v6 )
    {
      v12 = -1073741789;
      v15 = 646;
      v16 = 3221225507LL;
LABEL_12:
      DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", v15);
      v10 = 8;
      goto LABEL_35;
    }
    v5 = (_QWORD *)MSCryptAlloc(v6);
    if ( !v5 )
    {
      v12 = -1073741801;
      v15 = 654;
      v16 = 3221225495LL;
      goto LABEL_12;
    }
    v35 = *(_DWORD *)(a1 + 12);
    *(_DWORD *)(a1 + 12) = 2;
    if ( v14 == 1 )
    {
      v17 = MSCryptDecrypt(a1, (_DWORD)v39, 16, 0, 0, 0, (__int64)&v40, 32, (__int64)&v34, 0);
      v12 = v17;
      if ( v17 < 0 )
      {
        v15 = 683;
LABEL_18:
        v16 = (unsigned int)v17;
        goto LABEL_12;
      }
      LODWORD(v18) = v40;
      v39 = (unsigned __int64 *)v40;
      *v5 = v41;
    }
    else
    {
      v18 = *v39;
      v19 = v39 + 1;
      v39 = (unsigned __int64 *)*v39;
      memmove(v5, v19, a5 - 8LL);
      v20 = 5;
LABEL_21:
      if ( v20 >= 0 )
      {
        for ( i = v14; ; --i )
        {
          if ( i <= 0 )
          {
            --v20;
            goto LABEL_21;
          }
          v40 = v18 ^ _byteswap_uint64(i + v20 * v14);
          v41 = v5[i - 1];
          v17 = MSCryptDecrypt(a1, (unsigned int)&v40, 32, 0, 0, 0, (__int64)&v40, 32, (__int64)&v34, 0);
          v12 = v17;
          if ( v17 < 0 )
            break;
          v18 = v40;
          v5[i - 1] = v41;
          v39 = (unsigned __int64 *)v18;
        }
        v15 = 720;
        goto LABEL_18;
      }
      v7 = v37;
    }
    v22 = 1;
    v23 = _byteswap_ulong(HIDWORD(v39));
    v10 = 8;
    v24 = 0;
    v25 = v18 ^ 0xA65959A6 | (v23 >> 3) ^ (v14 - ((v23 & 7) != 0));
    v33 = v25;
    do
    {
      v26 = (v23 & 7) != 0 && v22 >= (unsigned __int64)(v23 & 7) ? *((_BYTE *)&v5[v6 / 8 - 1] + v22) : 0;
      ++v22;
      v24 |= v26;
    }
    while ( v22 < 8 );
    v33 = v24 | v25;
    if ( !*v38 )
    {
      v27 = v36;
      *v7 = v23;
      memmove(v27, v5, v23);
      goto LABEL_34;
    }
    v12 = -1073739509;
    DebugTraceError(3221227787LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", 752);
LABEL_35:
    v9 = 32;
    goto LABEL_36;
  }
  v11 = 610;
LABEL_3:
  v12 = -1073741811;
  DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", v11);
LABEL_36:
  v28 = &v40;
  do
  {
    *(_BYTE *)v28 = 0;
    v28 = (unsigned __int64 *)((char *)v28 + 1);
    --v9;
  }
  while ( v9 );
  v29 = &v39;
  do
  {
    *(_BYTE *)v29 = 0;
    v29 = (unsigned __int64 **)((char *)v29 + 1);
    --v10;
  }
  while ( v10 );
  if ( v5 )
  {
    v30 = v6;
    v31 = v5;
    if ( v6 )
    {
      do
      {
        *v31++ = 0;
        --v30;
      }
      while ( v30 );
    }
    MSCryptFree(v5);
  }
  if ( a1 && v35 )
    *(_DWORD *)(a1 + 12) = v35;
  return v12;
}

```

## disassembly

```asm
0x18007f298  push    rbp
0x18007f29a  push    rbx
0x18007f29b  push    rsi
0x18007f29c  push    rdi
0x18007f29d  push    r12
0x18007f29f  push    r13
0x18007f2a1  push    r14
0x18007f2a3  push    r15
0x18007f2a5  lea     rbp, [rsp-17h]
0x18007f2aa  sub     rsp, 0B8h
0x18007f2b1  mov     rax, cs:__security_cookie
0x18007f2b8  xor     rax, rsp
0x18007f2bb  mov     [rbp+4Fh+var_50], rax
0x18007f2bf  xor     esi, esi
0x18007f2c1  mov     [rbp+4Fh+var_78], r9
0x18007f2c5  lea     rax, [rbp+4Fh+var_A0]
0x18007f2c9  mov     [rbp+4Fh+var_9C], esi
0x18007f2cc  mov     [rbp+4Fh+var_A0], esi
0x18007f2cf  xor     r13d, r13d
0x18007f2d2  mov     [rbp+4Fh+var_80], rax
0x18007f2d6  mov     r12, r8
0x18007f2d9  xor     eax, eax
0x18007f2db  mov     [rbp+4Fh+var_88], r8
0x18007f2df  mov     [rbp+4Fh+var_90], rdx
0x18007f2e3  mov     r14, rcx
0x18007f2e6  mov     [rbp+4Fh+var_98], eax
0x18007f2e9  lea     edi, [rsi+20h]
0x18007f2ec  lea     r15d, [rsi+8]
0x18007f2f0  test    rcx, rcx
0x18007f2f3  jnz     short loc_18007F31D
0x18007f2f5  mov     r9d, 262h
0x18007f2fb  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f302  mov     ecx, 0C000000Dh
0x18007f307  lea     rdx, aStatus; "Status"
0x18007f30e  mov     ebx, 0C000000Dh
0x18007f313  call    DebugTraceError
0x18007f318  jmp     loc_18007F5D4
0x18007f31d  test    r12, r12
0x18007f320  jnz     short loc_18007F32A
0x18007f322  mov     r9d, 269h
0x18007f328  jmp     short loc_18007F2FB
0x18007f32a  mov     r15d, [rbp+4Fh+arg_20]
0x18007f32e  mov     edx, r15d
0x18007f331  call    MSCryptAesKeyUnwrapPadValidateInput
0x18007f336  mov     ebx, eax
0x18007f338  test    eax, eax
0x18007f33a  jns     short loc_18007F362
0x18007f33c  mov     r9d, 270h
0x18007f342  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f349  lea     rdx, aStatus; "Status"
0x18007f350  mov     ecx, eax
0x18007f352  call    DebugTraceError
0x18007f357  mov     r15d, 8
0x18007f35d  jmp     loc_18007F5D4
0x18007f362  lea     edi, [r15-8]
0x18007f366  shr     edi, 3
0x18007f369  lea     r13d, ds:0[rdi*8]
0x18007f371  cmp     [rbp+4Fh+var_90], rsi
0x18007f375  jnz     short loc_18007F386
0x18007f377  mov     [r12], r13d
0x18007f37b  mov     r15d, 8
0x18007f381  jmp     loc_18007F5CD
0x18007f386  cmp     [r12], r13d
0x18007f38a  jnb     short loc_18007F3BA
0x18007f38c  mov     ebx, 0C0000023h
0x18007f391  mov     r9d, 286h
0x18007f397  mov     ecx, 0C0000023h
0x18007f39c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f3a3  lea     rdx, aStatus; "Status"
0x18007f3aa  call    DebugTraceError
0x18007f3af  mov     r15d, 8
0x18007f3b5  jmp     loc_18007F5CF
0x18007f3ba  mov     ecx, r13d
0x18007f3bd  call    MSCryptAlloc
0x18007f3c2  mov     rsi, rax
0x18007f3c5  test    rax, rax
0x18007f3c8  jnz     short loc_18007F3DC
0x18007f3ca  mov     ebx, 0C0000017h
0x18007f3cf  mov     r9d, 28Eh
0x18007f3d5  mov     ecx, 0C0000017h
0x18007f3da  jmp     short loc_18007F39C
0x18007f3dc  mov     eax, [r14+0Ch]
0x18007f3e0  mov     [rbp+4Fh+var_98], eax
0x18007f3e3  mov     dword ptr [r14+0Ch], 2
0x18007f3eb  cmp     edi, 1
0x18007f3ee  jnz     short loc_18007F45D
0x18007f3f0  mov     rdx, [rbp+4Fh+var_78]
0x18007f3f4  lea     rax, [rbp+4Fh+var_9C]
0x18007f3f8  mov     [rsp+0F0h+var_A8], 0
0x18007f400  lea     r8d, [rdi+0Fh]
0x18007f404  mov     [rsp+0F0h+var_B0], rax
0x18007f409  xor     r9d, r9d
0x18007f40c  mov     [rsp+0F0h+var_B8], 20h ; ' '
0x18007f414  lea     rax, [rbp+4Fh+var_70]
0x18007f418  mov     [rsp+0F0h+var_C0], rax
0x18007f41d  mov     rcx, r14
0x18007f420  mov     [rsp+0F0h+var_C8], 0
0x18007f428  mov     [rsp+0F0h+var_D0], 0
0x18007f431  call    MSCryptDecrypt
0x18007f436  mov     ebx, eax
0x18007f438  test    eax, eax
0x18007f43a  jns     short loc_18007F449
0x18007f43c  mov     r9d, 2ABh
0x18007f442  mov     ecx, eax
0x18007f444  jmp     loc_18007F39C
0x18007f449  mov     rbx, [rbp+4Fh+var_70]
0x18007f44d  mov     rax, [rbp+4Fh+var_68]
0x18007f451  mov     [rbp+4Fh+var_78], rbx
0x18007f455  mov     [rsi], rax
0x18007f458  jmp     loc_18007F527
0x18007f45d  mov     rax, [rbp+4Fh+var_78]
0x18007f461  lea     r8, [r15-8]; Size
0x18007f465  mov     rcx, rsi; void *
0x18007f468  mov     rbx, [rax]
0x18007f46b  lea     rdx, [rax+8]; Src
0x18007f46f  mov     [rbp+4Fh+var_78], rbx
0x18007f473  call    memmove
0x18007f478  mov     r12d, 5
0x18007f47e  test    r12, r12
0x18007f481  js      loc_18007F523
0x18007f487  mov     r15d, edi
0x18007f48a  mov     eax, edi
0x18007f48c  test    r15, r15
0x18007f48f  jle     short loc_18007F510
0x18007f491  imul    rax, r12
0x18007f495  mov     [rsp+0F0h+var_A8], 0
0x18007f49d  lea     rcx, [rbp+4Fh+var_70]
0x18007f4a1  add     rax, r15
0x18007f4a4  lea     rdx, [rbp+4Fh+var_70]
0x18007f4a8  bswap   rax
0x18007f4ab  xor     rax, rbx
0x18007f4ae  xor     r9d, r9d
0x18007f4b1  mov     [rbp+4Fh+var_70], rax
0x18007f4b5  mov     rax, [rsi+r15*8-8]
0x18007f4ba  mov     [rbp+4Fh+var_68], rax
0x18007f4be  lea     rax, [rbp+4Fh+var_9C]
0x18007f4c2  mov     [rsp+0F0h+var_B0], rax
0x18007f4c7  mov     eax, 20h ; ' '
0x18007f4cc  mov     [rsp+0F0h+var_B8], eax
0x18007f4d0  mov     r8d, eax
0x18007f4d3  mov     [rsp+0F0h+var_C0], rcx
0x18007f4d8  mov     rcx, r14
0x18007f4db  mov     [rsp+0F0h+var_C8], 0
0x18007f4e3  mov     [rsp+0F0h+var_D0], 0
0x18007f4ec  call    MSCryptDecrypt
0x18007f4f1  mov     ebx, eax
0x18007f4f3  test    eax, eax
0x18007f4f5  js      short loc_18007F518
0x18007f4f7  mov     rbx, [rbp+4Fh+var_70]
0x18007f4fb  mov     rax, [rbp+4Fh+var_68]
0x18007f4ff  mov     [rsi+r15*8-8], rax
0x18007f504  dec     r15
0x18007f507  mov     [rbp+4Fh+var_78], rbx
0x18007f50b  jmp     loc_18007F48A
0x18007f510  dec     r12
0x18007f513  jmp     loc_18007F47E
0x18007f518  mov     r9d, 2D0h
0x18007f51e  jmp     loc_18007F442
0x18007f523  mov     r12, [rbp+4Fh+var_88]
0x18007f527  mov     edx, dword ptr [rbp+4Fh+var_78+4]
0x18007f52a  lea     r9d, [r13-8]
0x18007f52e  mov     eax, 0
0x18007f533  mov     ecx, 1
0x18007f538  bswap   edx
0x18007f53a  mov     r10d, edx
0x18007f53d  and     r10d, 7
0x18007f541  lea     r15d, [rcx+7]
0x18007f545  setnz   al
0x18007f548  xor     ebx, 0A65959A6h
0x18007f54e  sub     edi, eax
0x18007f550  xor     r8b, r8b
0x18007f553  mov     eax, edx
0x18007f555  shr     eax, 3
0x18007f558  xor     edi, eax
0x18007f55a  or      edi, ebx
0x18007f55c  test    r10d, r10d
0x18007f55f  mov     [rbp+4Fh+var_A0], edi
0x18007f562  setnz   r11b
0x18007f566  add     r9, rsi
0x18007f569  cmp     rcx, r10
0x18007f56c  setnb   al
0x18007f56f  and     al, r11b
0x18007f572  neg     al
0x18007f574  and     al, [r9+rcx]
0x18007f578  inc     rcx
0x18007f57b  or      r8b, al
0x18007f57e  cmp     rcx, r15
0x18007f581  jl      short loc_18007F569
0x18007f583  movzx   eax, r8b
0x18007f587  or      edi, eax
0x18007f589  mov     rax, [rbp+4Fh+var_80]
0x18007f58d  mov     [rbp+4Fh+var_A0], edi
0x18007f590  cmp     dword ptr [rax], 0
0x18007f593  jz      short loc_18007F5BA
0x18007f595  mov     r9d, 2F0h
0x18007f59b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f5a2  lea     rdx, aStatus; "Status"
0x18007f5a9  mov     ecx, 0C000090Bh
0x18007f5ae  mov     ebx, 0C000090Bh
0x18007f5b3  call    DebugTraceError
0x18007f5b8  jmp     short loc_18007F5CF
0x18007f5ba  mov     rcx, [rbp+4Fh+var_90]; void *
0x18007f5be  mov     [r12], edx
0x18007f5c2  mov     r8d, edx; Size
0x18007f5c5  mov     rdx, rsi; Src
0x18007f5c8  call    memmove
0x18007f5cd  xor     ebx, ebx
0x18007f5cf  mov     edi, 20h ; ' '
0x18007f5d4  lea     rax, [rbp+4Fh+var_70]
0x18007f5d8  mov     byte ptr [rax], 0
0x18007f5db  inc     rax
0x18007f5de  sub     rdi, 1
0x18007f5e2  jnz     short loc_18007F5D8
0x18007f5e4  lea     rax, [rbp+4Fh+var_78]
0x18007f5e8  mov     byte ptr [rax], 0
0x18007f5eb  inc     rax
0x18007f5ee  sub     r15, 1
0x18007f5f2  jnz     short loc_18007F5E8
0x18007f5f4  test    rsi, rsi
0x18007f5f7  jz      short loc_18007F618
0x18007f5f9  mov     ecx, r13d
0x18007f5fc  mov     rax, rsi
0x18007f5ff  test    r13d, r13d
0x18007f602  jz      short loc_18007F610
0x18007f604  mov     byte ptr [rax], 0
0x18007f607  inc     rax
0x18007f60a  sub     rcx, 1
0x18007f60e  jnz     short loc_18007F604
0x18007f610  mov     rcx, rsi; P
0x18007f613  call    MSCryptFree
0x18007f618  test    r14, r14
0x18007f61b  jz      short loc_18007F628
0x18007f61d  mov     eax, [rbp+4Fh+var_98]
0x18007f620  test    eax, eax
0x18007f622  jz      short loc_18007F628
0x18007f624  mov     [r14+0Ch], eax
0x18007f628  mov     eax, ebx
0x18007f62a  mov     rcx, [rbp+4Fh+var_50]
0x18007f62e  xor     rcx, rsp; StackCookie
0x18007f631  call    __security_check_cookie
0x18007f636  add     rsp, 0B8h
0x18007f63d  pop     r15
0x18007f63f  pop     r14
0x18007f641  pop     r13
0x18007f643  pop     r12
0x18007f645  pop     rdi
0x18007f646  pop     rsi
0x18007f647  pop     rbx
0x18007f648  pop     rbp
0x18007f649  retn
```
