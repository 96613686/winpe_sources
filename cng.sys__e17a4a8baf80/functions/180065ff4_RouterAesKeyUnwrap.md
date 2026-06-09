# RouterAesKeyUnwrap

- ea: `0x180065ff4`
- end: `0x180066323`
- name: `RouterAesKeyUnwrap`
- size: `815`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000d0b0`

## callees

- `0x18001155c`
- `0x180025ec0`
- `0x180025fb0`
- `0x180065ff4`
- `0x1800a4260`
- `0x1800a4300`
- `0x1800a45c0`

## string_xrefs

- `0x1800661fa`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x1800662b6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

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
0x180065ff4  push    rbp
0x180065ff6  push    rbx
0x180065ff7  push    rsi
0x180065ff8  push    rdi
0x180065ff9  push    r12
0x180065ffb  push    r13
0x180065ffd  push    r14
0x180065fff  push    r15
0x180066001  lea     rbp, [rsp-38h]
0x180066006  sub     rsp, 138h
0x18006600d  mov     rax, cs:__security_cookie
0x180066014  xor     rax, rsp
0x180066017  mov     [rbp+70h+var_50], rax
0x18006601b  mov     rax, [rdx+8]
0x18006601f  mov     r13, [rbp+70h+Src]
0x180066026  mov     [rbp+70h+var_D8], rcx
0x18006602a  mov     rcx, [rcx+58h]
0x18006602e  mov     [rbp+70h+var_E0], r8
0x180066032  mov     [rsp+170h+var_10C], 0
0x18006603a  mov     [rsp+170h+var_110], 0
0x180066042  mov     r8, [rax+68h]
0x180066046  mov     rax, [rax+40h]
0x18006604a  mov     [rbp+70h+var_C0], rcx
0x18006604e  mov     rcx, [rdx+10h]
0x180066052  lea     rdx, [rsp+170h+var_110]
0x180066057  mov     [rsp+170h+var_F8], r8
0x18006605c  lea     r8, [rsp+170h+var_10C]
0x180066061  mov     [rbp+70h+var_E8], r9
0x180066065  mov     r9d, 4
0x18006606b  mov     [rsp+170h+var_148], 0
0x180066073  mov     [rsp+170h+var_150], rdx
0x180066078  lea     rdx, aBlocklength; "BlockLength"
0x18006607f  mov     [rsp+170h+var_100], rcx
0x180066084  call    _guard_dispatch_icall
0x180066089  mov     ebx, eax
0x18006608b  mov     r15d, 10h
0x180066091  test    eax, eax
0x180066093  jns     short loc_1800660A2
0x180066095  mov     r9d, 194h
0x18006609b  mov     ecx, eax
0x18006609d  jmp     loc_1800662B6
0x1800660a2  cmp     [rsp+170h+var_110], 4
0x1800660a7  jnz     loc_1800662A6
0x1800660ad  cmp     [rsp+170h+var_10C], r15d
0x1800660b2  jnz     loc_1800662A6
0x1800660b8  mov     esi, dword ptr [rbp+70h+Size]
0x1800660be  test    sil, 7
0x1800660c2  jnz     loc_180066294
0x1800660c8  cmp     esi, r15d
0x1800660cb  jb      loc_180066294
0x1800660d1  mov     ebx, esi
0x1800660d3  cmp     esi, 48h ; 'H'
0x1800660d6  ja      short loc_1800660E1
0x1800660d8  xor     r14d, r14d
0x1800660db  lea     rdi, [rbp+70h+var_A0]
0x1800660df  jmp     short loc_180066109
0x1800660e1  mov     rcx, rbx
0x1800660e4  call    BCryptAlloc
0x1800660e9  mov     r14, rax
0x1800660ec  test    rax, rax
0x1800660ef  jnz     short loc_180066106
0x1800660f1  mov     ebx, 0C0000017h
0x1800660f6  mov     r9d, 1B8h
0x1800660fc  mov     ecx, 0C0000017h
0x180066101  jmp     loc_1800662B6
0x180066106  mov     rdi, rax
0x180066109  mov     r8, rbx; Size
0x18006610c  lea     r12d, [rsi-8]
0x180066110  mov     rdx, r13; Src
0x180066113  mov     rcx, rdi; void *
0x180066116  call    memmove
0x18006611b  mov     rax, [rdi]
0x18006611e  lea     r9, [rdi+8]
0x180066122  mov     r13d, r12d
0x180066125  shr     r13, 3
0x180066129  xor     r12d, r12d
0x18006612c  cmp     r12d, 6
0x180066130  jnb     loc_180066211
0x180066136  mov     r8d, r13d
0x180066139  test    r8d, r8d
0x18006613c  jz      loc_1800661EC
0x180066142  mov     ecx, r8d
0x180066145  mov     edx, 5
0x18006614a  sub     edx, r12d
0x18006614d  mov     [rsp+170h+var_128], 0
0x180066155  imul    rdx, r13
0x180066159  xorps   xmm0, xmm0
0x18006615c  add     rdx, rcx
0x18006615f  mov     rcx, [rsp+170h+var_100]
0x180066164  bswap   rdx
0x180066167  xor     rdx, rax
0x18006616a  dec     r8d
0x18006616d  mov     [rbp+70h+var_D0], rdx
0x180066171  mov     [rsp+170h+var_108], r8d
0x180066176  lea     rdx, [rbp+70h+var_D0]
0x18006617a  lea     eax, ds:0[r8*8]
0x180066182  mov     r8d, r15d
0x180066185  mov     [rbp+70h+var_F0], rax
0x180066189  mov     rax, [rax+r9]
0x18006618d  xor     r9d, r9d
0x180066190  mov     [rbp+70h+var_C8], rax
0x180066194  lea     rax, [rsp+170h+var_110]
0x180066199  mov     [rsp+170h+var_130], rax
0x18006619e  lea     rax, [rbp+70h+var_D0]
0x1800661a2  mov     [rsp+170h+var_138], r15d
0x1800661a7  mov     [rsp+170h+var_140], rax
0x1800661ac  lea     rax, [rbp+70h+var_B8]
0x1800661b0  mov     [rsp+170h+var_148], r15d
0x1800661b5  mov     [rsp+170h+var_150], rax
0x1800661ba  mov     rax, [rsp+170h+var_F8]
0x1800661bf  movups  [rbp+70h+var_B8], xmm0
0x1800661c3  call    _guard_dispatch_icall
0x1800661c8  mov     ebx, eax
0x1800661ca  test    eax, eax
0x1800661cc  js      short loc_1800661F4
0x1800661ce  mov     rdx, [rbp+70h+var_F0]
0x1800661d2  lea     r9, [rdi+8]
0x1800661d6  mov     rcx, [rbp+70h+var_C8]
0x1800661da  mov     rax, [rbp+70h+var_D0]
0x1800661de  mov     r8d, [rsp+170h+var_108]
0x1800661e3  mov     [rdx+r9], rcx
0x1800661e7  jmp     loc_180066139
0x1800661ec  inc     r12d
0x1800661ef  jmp     loc_18006612C
0x1800661f4  mov     r9d, 1E5h
0x1800661fa  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180066201  mov     ecx, eax
0x180066203  lea     rdx, aStatus; "Status"
0x18006620a  call    DebugTraceError
0x18006620f  jmp     short loc_18006626D
0x180066211  mov     rcx, 0A6A6A6A6A6A6A6A6h
0x18006621b  cmp     rax, rcx
0x18006621e  jz      short loc_180066227
0x180066220  mov     ebx, 0C000A002h
0x180066225  jmp     short loc_18006626D
0x180066227  mov     rcx, [rbp+70h+var_D8]
0x18006622b  lea     r10d, [rsi-8]
0x18006622f  mov     r8, [rbp+70h+var_E8]
0x180066233  mov     rdx, [rbp+70h+var_E0]
0x180066237  mov     rax, [rbp+70h+var_C0]
0x18006623b  mov     rcx, [rcx+18h]
0x18006623f  mov     dword ptr [rsp+170h+var_140], 0
0x180066247  mov     [rsp+170h+var_148], r10d
0x18006624c  mov     [rsp+170h+var_150], r9
0x180066251  mov     r9d, [rbp+70h+arg_20]
0x180066258  call    _guard_dispatch_icall
0x18006625d  mov     ebx, eax
0x18006625f  test    eax, eax
0x180066261  jns     short loc_18006626B
0x180066263  mov     r9d, 1FFh
0x180066269  jmp     short loc_1800661FA
0x18006626b  xor     ebx, ebx
0x18006626d  test    rdi, rdi
0x180066270  jz      short loc_180066285
0x180066272  mov     rax, rsi
0x180066275  test    esi, esi
0x180066277  jz      short loc_180066285
0x180066279  mov     byte ptr [rdi], 0
0x18006627c  inc     rdi
0x18006627f  sub     rax, 1
0x180066283  jnz     short loc_180066279
0x180066285  test    r14, r14
0x180066288  jz      short loc_1800662C9
0x18006628a  mov     rcx, r14; P
0x18006628d  call    BCryptFree
0x180066292  jmp     short loc_1800662C9
0x180066294  mov     ebx, 0C000000Dh
0x180066299  mov     r9d, 1A4h
0x18006629f  mov     ecx, 0C000000Dh
0x1800662a4  jmp     short loc_1800662B6
0x1800662a6  mov     ebx, 0C0000008h
0x1800662ab  mov     r9d, 19Ch
0x1800662b1  mov     ecx, 0C0000008h
0x1800662b6  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800662bd  lea     rdx, aStatus; "Status"
0x1800662c4  call    DebugTraceError
0x1800662c9  mov     rcx, r15
0x1800662cc  lea     rax, [rbp+70h+var_B8]
0x1800662d0  mov     byte ptr [rax], 0
0x1800662d3  inc     rax
0x1800662d6  sub     rcx, 1
0x1800662da  jnz     short loc_1800662D0
0x1800662dc  lea     rax, [rbp+70h+var_D0]
0x1800662e0  mov     byte ptr [rax], 0
0x1800662e3  inc     rax
0x1800662e6  sub     r15, 1
0x1800662ea  jnz     short loc_1800662E0
0x1800662ec  lea     ecx, [r15+8]
0x1800662f0  lea     rax, [rbp+70h+var_C0]
0x1800662f4  mov     byte ptr [rax], 0
0x1800662f7  inc     rax
0x1800662fa  sub     rcx, 1
0x1800662fe  jnz     short loc_1800662F4
0x180066300  mov     eax, ebx
0x180066302  mov     rcx, [rbp+70h+var_50]
0x180066306  xor     rcx, rsp; StackCookie
0x180066309  call    __security_check_cookie
0x18006630e  add     rsp, 138h
0x180066315  pop     r15
0x180066317  pop     r14
0x180066319  pop     r13
0x18006631b  pop     r12
0x18006631d  pop     rdi
0x18006631e  pop     rsi
0x18006631f  pop     rbx
0x180066320  pop     rbp
0x180066321  retn
```
