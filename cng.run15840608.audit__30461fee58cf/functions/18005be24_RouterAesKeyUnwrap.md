# RouterAesKeyUnwrap

- ea: `0x18005be24`
- end: `0x18005c153`
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
- `0x18001bd90`
- `0x18001be80`
- `0x18005be24`
- `0x18009d820`
- `0x18009d860`
- `0x18009da40`

## string_xrefs

- `0x18005c02a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18005c0e6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

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
0x18005be24  push    rbp
0x18005be26  push    rbx
0x18005be27  push    rsi
0x18005be28  push    rdi
0x18005be29  push    r12
0x18005be2b  push    r13
0x18005be2d  push    r14
0x18005be2f  push    r15
0x18005be31  lea     rbp, [rsp-38h]
0x18005be36  sub     rsp, 138h
0x18005be3d  mov     rax, cs:__security_cookie
0x18005be44  xor     rax, rsp
0x18005be47  mov     [rbp+70h+var_50], rax
0x18005be4b  mov     rax, [rdx+8]
0x18005be4f  mov     r13, [rbp+70h+Src]
0x18005be56  mov     [rbp+70h+var_D8], rcx
0x18005be5a  mov     rcx, [rcx+58h]
0x18005be5e  mov     [rbp+70h+var_E0], r8
0x18005be62  mov     [rsp+170h+var_10C], 0
0x18005be6a  mov     [rsp+170h+var_110], 0
0x18005be72  mov     r8, [rax+68h]
0x18005be76  mov     rax, [rax+40h]
0x18005be7a  mov     [rbp+70h+var_C0], rcx
0x18005be7e  mov     rcx, [rdx+10h]
0x18005be82  lea     rdx, [rsp+170h+var_110]
0x18005be87  mov     [rsp+170h+var_F8], r8
0x18005be8c  lea     r8, [rsp+170h+var_10C]
0x18005be91  mov     [rbp+70h+var_E8], r9
0x18005be95  mov     r9d, 4
0x18005be9b  mov     [rsp+170h+var_148], 0
0x18005bea3  mov     [rsp+170h+var_150], rdx
0x18005bea8  lea     rdx, aBlocklength; "BlockLength"
0x18005beaf  mov     [rsp+170h+var_100], rcx
0x18005beb4  call    _guard_dispatch_icall
0x18005beb9  mov     ebx, eax
0x18005bebb  mov     r15d, 10h
0x18005bec1  test    eax, eax
0x18005bec3  jns     short loc_18005BED2
0x18005bec5  mov     r9d, 194h
0x18005becb  mov     ecx, eax
0x18005becd  jmp     loc_18005C0E6
0x18005bed2  cmp     [rsp+170h+var_110], 4
0x18005bed7  jnz     loc_18005C0D6
0x18005bedd  cmp     [rsp+170h+var_10C], r15d
0x18005bee2  jnz     loc_18005C0D6
0x18005bee8  mov     esi, dword ptr [rbp+70h+Size]
0x18005beee  test    sil, 7
0x18005bef2  jnz     loc_18005C0C4
0x18005bef8  cmp     esi, r15d
0x18005befb  jb      loc_18005C0C4
0x18005bf01  mov     ebx, esi
0x18005bf03  cmp     esi, 48h ; 'H'
0x18005bf06  ja      short loc_18005BF11
0x18005bf08  xor     r14d, r14d
0x18005bf0b  lea     rdi, [rbp+70h+var_A0]
0x18005bf0f  jmp     short loc_18005BF39
0x18005bf11  mov     rcx, rbx
0x18005bf14  call    BCryptAlloc
0x18005bf19  mov     r14, rax
0x18005bf1c  test    rax, rax
0x18005bf1f  jnz     short loc_18005BF36
0x18005bf21  mov     ebx, 0C0000017h
0x18005bf26  mov     r9d, 1B8h
0x18005bf2c  mov     ecx, 0C0000017h
0x18005bf31  jmp     loc_18005C0E6
0x18005bf36  mov     rdi, rax
0x18005bf39  mov     r8, rbx; Size
0x18005bf3c  lea     r12d, [rsi-8]
0x18005bf40  mov     rdx, r13; Src
0x18005bf43  mov     rcx, rdi; void *
0x18005bf46  call    memmove
0x18005bf4b  mov     rax, [rdi]
0x18005bf4e  lea     r9, [rdi+8]
0x18005bf52  mov     r13d, r12d
0x18005bf55  shr     r13, 3
0x18005bf59  xor     r12d, r12d
0x18005bf5c  cmp     r12d, 6
0x18005bf60  jnb     loc_18005C041
0x18005bf66  mov     r8d, r13d
0x18005bf69  test    r8d, r8d
0x18005bf6c  jz      loc_18005C01C
0x18005bf72  mov     ecx, r8d
0x18005bf75  mov     edx, 5
0x18005bf7a  sub     edx, r12d
0x18005bf7d  mov     [rsp+170h+var_128], 0
0x18005bf85  imul    rdx, r13
0x18005bf89  xorps   xmm0, xmm0
0x18005bf8c  add     rdx, rcx
0x18005bf8f  mov     rcx, [rsp+170h+var_100]
0x18005bf94  bswap   rdx
0x18005bf97  xor     rdx, rax
0x18005bf9a  dec     r8d
0x18005bf9d  mov     [rbp+70h+var_D0], rdx
0x18005bfa1  mov     [rsp+170h+var_108], r8d
0x18005bfa6  lea     rdx, [rbp+70h+var_D0]
0x18005bfaa  lea     eax, ds:0[r8*8]
0x18005bfb2  mov     r8d, r15d
0x18005bfb5  mov     [rbp+70h+var_F0], rax
0x18005bfb9  mov     rax, [rax+r9]
0x18005bfbd  xor     r9d, r9d
0x18005bfc0  mov     [rbp+70h+var_C8], rax
0x18005bfc4  lea     rax, [rsp+170h+var_110]
0x18005bfc9  mov     [rsp+170h+var_130], rax
0x18005bfce  lea     rax, [rbp+70h+var_D0]
0x18005bfd2  mov     [rsp+170h+var_138], r15d
0x18005bfd7  mov     [rsp+170h+var_140], rax
0x18005bfdc  lea     rax, [rbp+70h+var_B8]
0x18005bfe0  mov     [rsp+170h+var_148], r15d
0x18005bfe5  mov     [rsp+170h+var_150], rax
0x18005bfea  mov     rax, [rsp+170h+var_F8]
0x18005bfef  movups  [rbp+70h+var_B8], xmm0
0x18005bff3  call    _guard_dispatch_icall
0x18005bff8  mov     ebx, eax
0x18005bffa  test    eax, eax
0x18005bffc  js      short loc_18005C024
0x18005bffe  mov     rdx, [rbp+70h+var_F0]
0x18005c002  lea     r9, [rdi+8]
0x18005c006  mov     rcx, [rbp+70h+var_C8]
0x18005c00a  mov     rax, [rbp+70h+var_D0]
0x18005c00e  mov     r8d, [rsp+170h+var_108]
0x18005c013  mov     [rdx+r9], rcx
0x18005c017  jmp     loc_18005BF69
0x18005c01c  inc     r12d
0x18005c01f  jmp     loc_18005BF5C
0x18005c024  mov     r9d, 1E5h
0x18005c02a  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005c031  mov     ecx, eax
0x18005c033  lea     rdx, aStatus; "Status"
0x18005c03a  call    DebugTraceError
0x18005c03f  jmp     short loc_18005C09D
0x18005c041  mov     rcx, 0A6A6A6A6A6A6A6A6h
0x18005c04b  cmp     rax, rcx
0x18005c04e  jz      short loc_18005C057
0x18005c050  mov     ebx, 0C000A002h
0x18005c055  jmp     short loc_18005C09D
0x18005c057  mov     rcx, [rbp+70h+var_D8]
0x18005c05b  lea     r10d, [rsi-8]
0x18005c05f  mov     r8, [rbp+70h+var_E8]
0x18005c063  mov     rdx, [rbp+70h+var_E0]
0x18005c067  mov     rax, [rbp+70h+var_C0]
0x18005c06b  mov     rcx, [rcx+18h]
0x18005c06f  mov     dword ptr [rsp+170h+var_140], 0
0x18005c077  mov     [rsp+170h+var_148], r10d
0x18005c07c  mov     [rsp+170h+var_150], r9
0x18005c081  mov     r9d, [rbp+70h+arg_20]
0x18005c088  call    _guard_dispatch_icall
0x18005c08d  mov     ebx, eax
0x18005c08f  test    eax, eax
0x18005c091  jns     short loc_18005C09B
0x18005c093  mov     r9d, 1FFh
0x18005c099  jmp     short loc_18005C02A
0x18005c09b  xor     ebx, ebx
0x18005c09d  test    rdi, rdi
0x18005c0a0  jz      short loc_18005C0B5
0x18005c0a2  mov     rax, rsi
0x18005c0a5  test    esi, esi
0x18005c0a7  jz      short loc_18005C0B5
0x18005c0a9  mov     byte ptr [rdi], 0
0x18005c0ac  inc     rdi
0x18005c0af  sub     rax, 1
0x18005c0b3  jnz     short loc_18005C0A9
0x18005c0b5  test    r14, r14
0x18005c0b8  jz      short loc_18005C0F9
0x18005c0ba  mov     rcx, r14; P
0x18005c0bd  call    BCryptFree
0x18005c0c2  jmp     short loc_18005C0F9
0x18005c0c4  mov     ebx, 0C000000Dh
0x18005c0c9  mov     r9d, 1A4h
0x18005c0cf  mov     ecx, 0C000000Dh
0x18005c0d4  jmp     short loc_18005C0E6
0x18005c0d6  mov     ebx, 0C0000008h
0x18005c0db  mov     r9d, 19Ch
0x18005c0e1  mov     ecx, 0C0000008h
0x18005c0e6  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005c0ed  lea     rdx, aStatus; "Status"
0x18005c0f4  call    DebugTraceError
0x18005c0f9  mov     rcx, r15
0x18005c0fc  lea     rax, [rbp+70h+var_B8]
0x18005c100  mov     byte ptr [rax], 0
0x18005c103  inc     rax
0x18005c106  sub     rcx, 1
0x18005c10a  jnz     short loc_18005C100
0x18005c10c  lea     rax, [rbp+70h+var_D0]
0x18005c110  mov     byte ptr [rax], 0
0x18005c113  inc     rax
0x18005c116  sub     r15, 1
0x18005c11a  jnz     short loc_18005C110
0x18005c11c  lea     ecx, [r15+8]
0x18005c120  lea     rax, [rbp+70h+var_C0]
0x18005c124  mov     byte ptr [rax], 0
0x18005c127  inc     rax
0x18005c12a  sub     rcx, 1
0x18005c12e  jnz     short loc_18005C124
0x18005c130  mov     eax, ebx
0x18005c132  mov     rcx, [rbp+70h+var_50]
0x18005c136  xor     rcx, rsp; StackCookie
0x18005c139  call    __security_check_cookie
0x18005c13e  add     rsp, 138h
0x18005c145  pop     r15
0x18005c147  pop     r14
0x18005c149  pop     r13
0x18005c14b  pop     r12
0x18005c14d  pop     rdi
0x18005c14e  pop     rsi
0x18005c14f  pop     rbx
0x18005c150  pop     rbp
0x18005c151  retn
```
