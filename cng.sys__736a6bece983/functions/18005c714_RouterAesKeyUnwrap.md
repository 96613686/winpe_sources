# RouterAesKeyUnwrap

- ea: `0x18005c714`
- end: `0x18005ca43`
- name: `RouterAesKeyUnwrap`
- size: `815`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002f90`

## callees

- `0x18000743c`
- `0x180018e40`
- `0x180018f30`
- `0x18005c714`
- `0x18009f650`
- `0x18009f6d0`
- `0x18009f780`

## string_xrefs

- `0x18005c91a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18005c9d6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

## pseudocode

```c
__int64 __fastcall RouterAesKeyUnwrap(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        void *Src,
        size_t Size)
{
  __int64 v7; // rax
  __int64 (__fastcall *v8)(_QWORD, __int64, __int64, _QWORD, _BYTE *, int, _DWORD); // rcx
  __int64 (__fastcall *v9)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD); // r8
  __int64 (__fastcall *v10)(__int64, const wchar_t *, int *, __int64, int *, _DWORD); // rax
  __int64 v11; // rcx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r15
  __int64 v15; // r9
  __int64 v16; // rcx
  void *v17; // r14
  char *v18; // rdi
  __int64 v19; // rax
  unsigned __int64 v20; // rax
  _BYTE *v21; // r9
  unsigned int v22; // r12d
  unsigned int v23; // r8d
  int v24; // eax
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rcx
  __int128 *v28; // rax
  unsigned __int64 *v29; // rax
  __int64 v30; // rcx
  _BYTE *v31; // rax
  int v33; // [rsp+60h] [rbp-A0h] BYREF
  int v34; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v35; // [rsp+68h] [rbp-98h]
  __int64 v36; // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v37)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD); // [rsp+78h] [rbp-88h]
  __int64 v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+88h] [rbp-78h]
  __int64 v40; // [rsp+90h] [rbp-70h]
  __int64 v41; // [rsp+98h] [rbp-68h]
  unsigned __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v44)(_QWORD, __int64, __int64, _QWORD, _BYTE *, int, _DWORD); // [rsp+B0h] [rbp-50h] BYREF
  __int128 v45; // [rsp+B8h] [rbp-48h] BYREF
  char v46; // [rsp+D0h] [rbp-30h] BYREF

  v7 = *(_QWORD *)(a2 + 8);
  v41 = a1;
  v8 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _BYTE *, int, _DWORD))(a1 + 88);
  v40 = a3;
  v34 = 0;
  v33 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD))(v7 + 104);
  v10 = *(__int64 (__fastcall **)(__int64, const wchar_t *, int *, __int64, int *, _DWORD))(v7 + 64);
  v44 = v8;
  v11 = *(_QWORD *)(a2 + 16);
  v37 = v9;
  v39 = a4;
  v36 = v11;
  v12 = v10(v11, L"BlockLength", &v34, 4, &v33, 0);
  v13 = v12;
  v14 = 16;
  if ( v12 < 0 )
  {
    v15 = 404;
    v16 = (unsigned int)v12;
LABEL_33:
    DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c", v15);
    goto LABEL_34;
  }
  if ( v33 != 4 || v34 != 16 )
  {
    v13 = -1073741816;
    v15 = 412;
    v16 = 3221225480LL;
    goto LABEL_33;
  }
  if ( (Size & 7) != 0 || (unsigned int)Size < 0x10 )
  {
    v13 = -1073741811;
    v15 = 420;
    v16 = 3221225485LL;
    goto LABEL_33;
  }
  if ( (unsigned int)Size > 0x48 )
  {
    v19 = BCryptAlloc((unsigned int)Size);
    v17 = (void *)v19;
    if ( !v19 )
    {
      v13 = -1073741801;
      v15 = 440;
      v16 = 3221225495LL;
      goto LABEL_33;
    }
    v18 = (char *)v19;
  }
  else
  {
    v17 = 0;
    v18 = &v46;
  }
  memmove(v18, Src, (unsigned int)Size);
  v20 = *(_QWORD *)v18;
  v21 = v18 + 8;
  v22 = 0;
LABEL_13:
  if ( v22 >= 6 )
  {
    if ( v20 != 0xA6A6A6A6A6A6A6A6uLL )
    {
      v13 = -1073700862;
      goto LABEL_26;
    }
    v24 = v44(*(_QWORD *)(v41 + 24), v40, v39, a5, v21, (int)Size - 8, 0);
    v13 = v24;
    if ( v24 >= 0 )
    {
      v13 = 0;
      goto LABEL_26;
    }
    v25 = 511;
  }
  else
  {
    v23 = (unsigned int)(Size - 8) >> 3;
    while ( 1 )
    {
      if ( !v23 )
      {
        ++v22;
        goto LABEL_13;
      }
      v42 = v20 ^ _byteswap_uint64(v23 + ((unsigned __int64)(unsigned int)(Size - 8) >> 3) * (5 - v22));
      v35 = v23 - 1;
      v38 = 8 * (v23 - 1);
      v43 = *(_QWORD *)&v21[v38];
      v45 = 0;
      v24 = v37(v36, &v42, 16, 0, &v45, 16, &v42, 16, &v33, 0);
      v13 = v24;
      if ( v24 < 0 )
        break;
      v21 = v18 + 8;
      v20 = v42;
      v23 = v35;
      *(_QWORD *)&v18[v38 + 8] = v43;
    }
    v25 = 485;
  }
  DebugTraceError(
    (unsigned int)v24,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c",
    v25);
LABEL_26:
  if ( v18 )
  {
    v26 = (unsigned int)Size;
    do
    {
      *v18++ = 0;
      --v26;
    }
    while ( v26 );
  }
  if ( v17 )
    BCryptFree(v17);
LABEL_34:
  v27 = 16;
  v28 = &v45;
  do
  {
    *(_BYTE *)v28 = 0;
    v28 = (__int128 *)((char *)v28 + 1);
    --v27;
  }
  while ( v27 );
  v29 = &v42;
  do
  {
    *(_BYTE *)v29 = 0;
    v29 = (unsigned __int64 *)((char *)v29 + 1);
    --v14;
  }
  while ( v14 );
  v30 = 8;
  v31 = &v44;
  do
  {
    *v31++ = 0;
    --v30;
  }
  while ( v30 );
  return v13;
}

```

## disassembly

```asm
0x18005c714  push    rbp
0x18005c716  push    rbx
0x18005c717  push    rsi
0x18005c718  push    rdi
0x18005c719  push    r12
0x18005c71b  push    r13
0x18005c71d  push    r14
0x18005c71f  push    r15
0x18005c721  lea     rbp, [rsp-38h]
0x18005c726  sub     rsp, 138h
0x18005c72d  mov     rax, cs:__security_cookie
0x18005c734  xor     rax, rsp
0x18005c737  mov     [rbp+70h+var_50], rax
0x18005c73b  mov     rax, [rdx+8]
0x18005c73f  mov     r13, [rbp+70h+Src]
0x18005c746  mov     [rbp+70h+var_D8], rcx
0x18005c74a  mov     rcx, [rcx+58h]
0x18005c74e  mov     [rbp+70h+var_E0], r8
0x18005c752  mov     [rsp+170h+var_10C], 0
0x18005c75a  mov     [rsp+170h+var_110], 0
0x18005c762  mov     r8, [rax+68h]
0x18005c766  mov     rax, [rax+40h]
0x18005c76a  mov     [rbp+70h+var_C0], rcx
0x18005c76e  mov     rcx, [rdx+10h]
0x18005c772  lea     rdx, [rsp+170h+var_110]
0x18005c777  mov     [rsp+170h+var_F8], r8
0x18005c77c  lea     r8, [rsp+170h+var_10C]
0x18005c781  mov     [rbp+70h+var_E8], r9
0x18005c785  mov     r9d, 4
0x18005c78b  mov     [rsp+170h+var_148], 0
0x18005c793  mov     [rsp+170h+var_150], rdx
0x18005c798  lea     rdx, aBlocklength; "BlockLength"
0x18005c79f  mov     [rsp+170h+var_100], rcx
0x18005c7a4  call    _guard_dispatch_icall
0x18005c7a9  mov     ebx, eax
0x18005c7ab  mov     r15d, 10h
0x18005c7b1  test    eax, eax
0x18005c7b3  jns     short loc_18005C7C2
0x18005c7b5  mov     r9d, 194h
0x18005c7bb  mov     ecx, eax
0x18005c7bd  jmp     loc_18005C9D6
0x18005c7c2  cmp     [rsp+170h+var_110], 4
0x18005c7c7  jnz     loc_18005C9C6
0x18005c7cd  cmp     [rsp+170h+var_10C], r15d
0x18005c7d2  jnz     loc_18005C9C6
0x18005c7d8  mov     esi, dword ptr [rbp+70h+Size]
0x18005c7de  test    sil, 7
0x18005c7e2  jnz     loc_18005C9B4
0x18005c7e8  cmp     esi, r15d
0x18005c7eb  jb      loc_18005C9B4
0x18005c7f1  mov     ebx, esi
0x18005c7f3  cmp     esi, 48h ; 'H'
0x18005c7f6  ja      short loc_18005C801
0x18005c7f8  xor     r14d, r14d
0x18005c7fb  lea     rdi, [rbp+70h+var_A0]
0x18005c7ff  jmp     short loc_18005C829
0x18005c801  mov     rcx, rbx
0x18005c804  call    BCryptAlloc
0x18005c809  mov     r14, rax
0x18005c80c  test    rax, rax
0x18005c80f  jnz     short loc_18005C826
0x18005c811  mov     ebx, 0C0000017h
0x18005c816  mov     r9d, 1B8h
0x18005c81c  mov     ecx, 0C0000017h
0x18005c821  jmp     loc_18005C9D6
0x18005c826  mov     rdi, rax
0x18005c829  mov     r8, rbx; Size
0x18005c82c  lea     r12d, [rsi-8]
0x18005c830  mov     rdx, r13; Src
0x18005c833  mov     rcx, rdi; void *
0x18005c836  call    memmove
0x18005c83b  mov     rax, [rdi]
0x18005c83e  lea     r9, [rdi+8]
0x18005c842  mov     r13d, r12d
0x18005c845  shr     r13, 3
0x18005c849  xor     r12d, r12d
0x18005c84c  cmp     r12d, 6
0x18005c850  jnb     loc_18005C931
0x18005c856  mov     r8d, r13d
0x18005c859  test    r8d, r8d
0x18005c85c  jz      loc_18005C90C
0x18005c862  mov     ecx, r8d
0x18005c865  mov     edx, 5
0x18005c86a  sub     edx, r12d
0x18005c86d  mov     [rsp+170h+var_128], 0
0x18005c875  imul    rdx, r13
0x18005c879  xorps   xmm0, xmm0
0x18005c87c  add     rdx, rcx
0x18005c87f  mov     rcx, [rsp+170h+var_100]
0x18005c884  bswap   rdx
0x18005c887  xor     rdx, rax
0x18005c88a  dec     r8d
0x18005c88d  mov     [rbp+70h+var_D0], rdx
0x18005c891  mov     [rsp+170h+var_108], r8d
0x18005c896  lea     rdx, [rbp+70h+var_D0]
0x18005c89a  lea     eax, ds:0[r8*8]
0x18005c8a2  mov     r8d, r15d
0x18005c8a5  mov     [rbp+70h+var_F0], rax
0x18005c8a9  mov     rax, [rax+r9]
0x18005c8ad  xor     r9d, r9d
0x18005c8b0  mov     [rbp+70h+var_C8], rax
0x18005c8b4  lea     rax, [rsp+170h+var_110]
0x18005c8b9  mov     [rsp+170h+var_130], rax
0x18005c8be  lea     rax, [rbp+70h+var_D0]
0x18005c8c2  mov     [rsp+170h+var_138], r15d
0x18005c8c7  mov     [rsp+170h+var_140], rax
0x18005c8cc  lea     rax, [rbp+70h+var_B8]
0x18005c8d0  mov     [rsp+170h+var_148], r15d
0x18005c8d5  mov     [rsp+170h+var_150], rax
0x18005c8da  mov     rax, [rsp+170h+var_F8]
0x18005c8df  movups  [rbp+70h+var_B8], xmm0
0x18005c8e3  call    _guard_dispatch_icall
0x18005c8e8  mov     ebx, eax
0x18005c8ea  test    eax, eax
0x18005c8ec  js      short loc_18005C914
0x18005c8ee  mov     rdx, [rbp+70h+var_F0]
0x18005c8f2  lea     r9, [rdi+8]
0x18005c8f6  mov     rcx, [rbp+70h+var_C8]
0x18005c8fa  mov     rax, [rbp+70h+var_D0]
0x18005c8fe  mov     r8d, [rsp+170h+var_108]
0x18005c903  mov     [rdx+r9], rcx
0x18005c907  jmp     loc_18005C859
0x18005c90c  inc     r12d
0x18005c90f  jmp     loc_18005C84C
0x18005c914  mov     r9d, 1E5h
0x18005c91a  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005c921  mov     ecx, eax
0x18005c923  lea     rdx, aStatus; "Status"
0x18005c92a  call    DebugTraceError
0x18005c92f  jmp     short loc_18005C98D
0x18005c931  mov     rcx, 0A6A6A6A6A6A6A6A6h
0x18005c93b  cmp     rax, rcx
0x18005c93e  jz      short loc_18005C947
0x18005c940  mov     ebx, 0C000A002h
0x18005c945  jmp     short loc_18005C98D
0x18005c947  mov     rcx, [rbp+70h+var_D8]
0x18005c94b  lea     r10d, [rsi-8]
0x18005c94f  mov     r8, [rbp+70h+var_E8]
0x18005c953  mov     rdx, [rbp+70h+var_E0]
0x18005c957  mov     rax, [rbp+70h+var_C0]
0x18005c95b  mov     rcx, [rcx+18h]
0x18005c95f  mov     dword ptr [rsp+170h+var_140], 0
0x18005c967  mov     [rsp+170h+var_148], r10d
0x18005c96c  mov     [rsp+170h+var_150], r9
0x18005c971  mov     r9d, [rbp+70h+arg_20]
0x18005c978  call    _guard_dispatch_icall
0x18005c97d  mov     ebx, eax
0x18005c97f  test    eax, eax
0x18005c981  jns     short loc_18005C98B
0x18005c983  mov     r9d, 1FFh
0x18005c989  jmp     short loc_18005C91A
0x18005c98b  xor     ebx, ebx
0x18005c98d  test    rdi, rdi
0x18005c990  jz      short loc_18005C9A5
0x18005c992  mov     rax, rsi
0x18005c995  test    esi, esi
0x18005c997  jz      short loc_18005C9A5
0x18005c999  mov     byte ptr [rdi], 0
0x18005c99c  inc     rdi
0x18005c99f  sub     rax, 1
0x18005c9a3  jnz     short loc_18005C999
0x18005c9a5  test    r14, r14
0x18005c9a8  jz      short loc_18005C9E9
0x18005c9aa  mov     rcx, r14; P
0x18005c9ad  call    BCryptFree
0x18005c9b2  jmp     short loc_18005C9E9
0x18005c9b4  mov     ebx, 0C000000Dh
0x18005c9b9  mov     r9d, 1A4h
0x18005c9bf  mov     ecx, 0C000000Dh
0x18005c9c4  jmp     short loc_18005C9D6
0x18005c9c6  mov     ebx, 0C0000008h
0x18005c9cb  mov     r9d, 19Ch
0x18005c9d1  mov     ecx, 0C0000008h
0x18005c9d6  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005c9dd  lea     rdx, aStatus; "Status"
0x18005c9e4  call    DebugTraceError
0x18005c9e9  mov     rcx, r15
0x18005c9ec  lea     rax, [rbp+70h+var_B8]
0x18005c9f0  mov     byte ptr [rax], 0
0x18005c9f3  inc     rax
0x18005c9f6  sub     rcx, 1
0x18005c9fa  jnz     short loc_18005C9F0
0x18005c9fc  lea     rax, [rbp+70h+var_D0]
0x18005ca00  mov     byte ptr [rax], 0
0x18005ca03  inc     rax
0x18005ca06  sub     r15, 1
0x18005ca0a  jnz     short loc_18005CA00
0x18005ca0c  lea     ecx, [r15+8]
0x18005ca10  lea     rax, [rbp+70h+var_C0]
0x18005ca14  mov     byte ptr [rax], 0
0x18005ca17  inc     rax
0x18005ca1a  sub     rcx, 1
0x18005ca1e  jnz     short loc_18005CA14
0x18005ca20  mov     eax, ebx
0x18005ca22  mov     rcx, [rbp+70h+var_50]
0x18005ca26  xor     rcx, rsp; StackCookie
0x18005ca29  call    __security_check_cookie
0x18005ca2e  add     rsp, 138h
0x18005ca35  pop     r15
0x18005ca37  pop     r14
0x18005ca39  pop     r13
0x18005ca3b  pop     r12
0x18005ca3d  pop     rdi
0x18005ca3e  pop     rsi
0x18005ca3f  pop     rbx
0x18005ca40  pop     rbp
0x18005ca41  retn
```
