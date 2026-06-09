# RouterAesKeyWrap

- ea: `0x18005c15c`
- end: `0x18005c51f`
- name: `RouterAesKeyWrap`
- size: `963`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800590d0`

## callees

- `0x18000743c`
- `0x18001bd90`
- `0x18001be80`
- `0x18005c15c`
- `0x18005c528`
- `0x18009d820`
- `0x18009d860`
- `0x18009da40`

## string_xrefs

- `0x18005c26c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18005c2e9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18005c32f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x18005c437`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

## pseudocode

```c
__int64 __fastcall RouterAesKeyWrap(__int64 a1, __int64 a2, void *a3, unsigned int a4, unsigned int *a5)
{
  __int64 v5; // rax
  __int64 v7; // r10
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, const wchar_t *, unsigned int *, __int64, int *, _DWORD); // r14
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD); // r8
  __int64 (__fastcall *v12)(__int64, const wchar_t *, int *, __int64, int *, _DWORD); // rax
  int v13; // eax
  __int64 v14; // r12
  unsigned int v15; // ebx
  __int64 v16; // r13
  __int64 v17; // r9
  __int64 v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // r14d
  unsigned int v21; // edi
  void *v22; // r15
  char *p_Src; // rdi
  __int64 v24; // rax
  int KeyDataBlob; // eax
  unsigned int v26; // r13d
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rax
  unsigned int v29; // r14d
  unsigned int i; // ecx
  int v31; // eax
  size_t v32; // r8
  void *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int128 *v36; // rax
  unsigned __int64 *v37; // rax
  size_t *p_Size; // rax
  unsigned int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  int v42; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h]
  void *v44; // [rsp+78h] [rbp-88h]
  __int64 v45; // [rsp+80h] [rbp-80h]
  __int64 (__fastcall *v46)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD); // [rsp+88h] [rbp-78h]
  unsigned __int64 v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h]
  __int64 v49; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v50; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-50h]
  size_t Size; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v53; // [rsp+C0h] [rbp-40h] BYREF
  char Src; // [rsp+D0h] [rbp-30h] BYREF

  v5 = *(_QWORD *)(a1 + 8);
  v7 = *(_QWORD *)(a2 + 16);
  v8 = *(_QWORD *)(a1 + 16);
  v42 = 0;
  v40 = 0;
  v41 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, __int64, int *, _DWORD))(v5 + 64);
  v10 = *(_QWORD *)(a2 + 8);
  v44 = a3;
  v43 = a1;
  v11 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *, __int64, _QWORD, __int128 *, int, unsigned __int64 *, int, int *, _DWORD))(v10 + 96);
  v12 = *(__int64 (__fastcall **)(__int64, const wchar_t *, int *, __int64, int *, _DWORD))(v10 + 64);
  v46 = v11;
  v45 = v7;
  v13 = v12(v7, L"BlockLength", &v42, 4, &v41, 0);
  v14 = 8;
  v15 = v13;
  v16 = 16;
  if ( v13 < 0 )
  {
    v17 = 186;
LABEL_7:
    v18 = (unsigned int)v13;
LABEL_8:
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c", v17);
LABEL_47:
    *a5 = 0;
    goto LABEL_39;
  }
  if ( v41 != 4 || v42 != 16 )
  {
    v15 = -1073741816;
    v17 = 194;
    v18 = 3221225480LL;
    goto LABEL_8;
  }
  v13 = v9(v8, L"KeyLength", &v40, 4, &v41, 0);
  v15 = v13;
  if ( v13 < 0 )
  {
    v17 = 208;
    goto LABEL_7;
  }
  v19 = v40 >> 3;
  v20 = v40 >> 3;
  v40 >>= 3;
  if ( v41 != 4 || (v20 & 7) != 0 )
  {
    v15 = -1073741816;
    goto LABEL_47;
  }
  v21 = v19 + 8;
  if ( !v44 )
  {
    v15 = 0;
LABEL_19:
    *a5 = v21;
    goto LABEL_39;
  }
  if ( a4 < v21 )
  {
    v15 = -1073741789;
    goto LABEL_19;
  }
  Size = v21;
  if ( v21 > 0x48 )
  {
    v24 = BCryptAlloc(v21);
    v22 = (void *)v24;
    if ( !v24 )
    {
      v15 = -1073741801;
      DebugTraceError(
        3221225495LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c",
        256);
      goto LABEL_19;
    }
    v19 = v40;
    p_Src = (char *)v24;
  }
  else
  {
    v22 = 0;
    p_Src = &Src;
  }
  KeyDataBlob = RouterGetKeyDataBlob(v43, p_Src + 8, v19);
  v15 = KeyDataBlob;
  if ( KeyDataBlob >= 0 )
  {
    v26 = v20;
    v27 = (unsigned __int64)v40 >> 3;
    v28 = 0xA6A6A6A6A6A6A6A6uLL;
    v47 = v27;
    v29 = 0;
LABEL_24:
    if ( v29 >= 6 )
    {
      v32 = Size;
      v33 = v44;
      *(_QWORD *)p_Src = v28;
      memmove(v33, p_Src, v32);
      v15 = 0;
    }
    else
    {
      for ( i = 0; ; i = v43 + 1 )
      {
        LODWORD(v43) = i;
        v48 = i;
        if ( i >= v27 )
        {
          ++v29;
          goto LABEL_24;
        }
        v50 = v28;
        v49 = 8 * i;
        v51 = *(_QWORD *)&p_Src[v49 + 8];
        v53 = 0;
        v31 = v46(v45, &v50, 16, 0, &v53, 16, &v50, 16, &v41, 0);
        v15 = v31;
        if ( v31 < 0 )
          break;
        v27 = v47;
        v28 = v50 ^ _byteswap_uint64(v48 + 1 + v47 * v29);
        *(_QWORD *)&p_Src[v49 + 8] = v51;
      }
      DebugTraceError(
        (unsigned int)v31,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c",
        309);
    }
    v20 = v26;
  }
  else
  {
    DebugTraceError(
      (unsigned int)KeyDataBlob,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\routeraeskeywrap.c",
      274);
    v26 = v20;
  }
  *a5 = v20 + 8;
  if ( p_Src )
  {
    v34 = v26 + 8;
    if ( v26 != -8 )
    {
      do
      {
        *p_Src++ = 0;
        --v34;
      }
      while ( v34 );
    }
  }
  if ( v22 )
    BCryptFree(v22);
  v16 = 16;
LABEL_39:
  v35 = 16;
  v36 = &v53;
  do
  {
    *(_BYTE *)v36 = 0;
    v36 = (__int128 *)((char *)v36 + 1);
    --v35;
  }
  while ( v35 );
  v37 = &v50;
  do
  {
    *(_BYTE *)v37 = 0;
    v37 = (unsigned __int64 *)((char *)v37 + 1);
    --v16;
  }
  while ( v16 );
  p_Size = &Size;
  do
  {
    *(_BYTE *)p_Size = 0;
    p_Size = (size_t *)((char *)p_Size + 1);
    --v14;
  }
  while ( v14 );
  return v15;
}

```

## disassembly

```asm
0x18005c15c  mov     [rsp-8+arg_18], rbx
0x18005c161  push    rbp
0x18005c162  push    rsi
0x18005c163  push    rdi
0x18005c164  push    r12
0x18005c166  push    r13
0x18005c168  push    r14
0x18005c16a  push    r15
0x18005c16c  lea     rbp, [rsp-30h]
0x18005c171  sub     rsp, 130h
0x18005c178  mov     rax, cs:__security_cookie
0x18005c17f  xor     rax, rsp
0x18005c182  mov     [rbp+60h+var_40], rax
0x18005c186  mov     rax, [rcx+8]
0x18005c18a  mov     r15d, r9d
0x18005c18d  mov     r10, [rdx+10h]
0x18005c191  xor     r9d, r9d
0x18005c194  mov     rdi, [rcx+10h]
0x18005c198  mov     rsi, [rbp+60h+arg_20]
0x18005c19f  mov     [rsp+160h+var_F8], r9d
0x18005c1a4  mov     [rsp+160h+var_100], r9d
0x18005c1a9  mov     [rsp+160h+var_FC], r9d
0x18005c1ae  mov     r14, [rax+40h]
0x18005c1b2  mov     rax, [rdx+8]
0x18005c1b6  lea     rdx, aBlocklength; "BlockLength"
0x18005c1bd  mov     [rsp+160h+var_E8], r8
0x18005c1c2  mov     [rsp+160h+var_F0], rcx
0x18005c1c7  lea     rcx, [rsp+160h+var_FC]
0x18005c1cc  mov     [rsp+160h+var_138], r9d
0x18005c1d1  mov     r9d, 4
0x18005c1d7  mov     r8, [rax+60h]
0x18005c1db  mov     rax, [rax+40h]
0x18005c1df  mov     [rbp+60h+var_D8], r8
0x18005c1e3  lea     r8, [rsp+160h+var_F8]
0x18005c1e8  mov     [rsp+160h+var_140], rcx
0x18005c1ed  mov     rcx, r10
0x18005c1f0  mov     [rbp+60h+var_E0], r10
0x18005c1f4  call    _guard_dispatch_icall
0x18005c1f9  mov     r12d, 8
0x18005c1ff  mov     ebx, eax
0x18005c201  lea     r13d, [r12+8]
0x18005c206  test    eax, eax
0x18005c208  jns     short loc_18005C212
0x18005c20a  mov     r9d, 0BAh
0x18005c210  jmp     short loc_18005C263
0x18005c212  cmp     [rsp+160h+var_FC], 4
0x18005c217  jnz     loc_18005C50A
0x18005c21d  cmp     [rsp+160h+var_F8], r13d
0x18005c222  jnz     loc_18005C50A
0x18005c228  lea     rax, [rsp+160h+var_FC]
0x18005c22d  mov     [rsp+160h+var_138], 0
0x18005c235  mov     [rsp+160h+var_140], rax
0x18005c23a  lea     r8, [rsp+160h+var_100]
0x18005c23f  mov     rax, r14
0x18005c242  lea     rdx, aKeylength; "KeyLength"
0x18005c249  mov     r9d, 4
0x18005c24f  mov     rcx, rdi
0x18005c252  call    _guard_dispatch_icall
0x18005c257  mov     ebx, eax
0x18005c259  test    eax, eax
0x18005c25b  jns     short loc_18005C27D
0x18005c25d  mov     r9d, 0D0h
0x18005c263  mov     ecx, eax
0x18005c265  lea     rdx, aStatus; "Status"
0x18005c26c  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005c273  call    DebugTraceError
0x18005c278  jmp     loc_18005C502
0x18005c27d  mov     r8d, [rsp+160h+var_100]
0x18005c282  shr     r8d, 3
0x18005c286  cmp     [rsp+160h+var_FC], 4
0x18005c28b  mov     r14d, r8d
0x18005c28e  mov     [rsp+160h+var_100], r8d
0x18005c293  jnz     loc_18005C4FD
0x18005c299  test    r14b, 7
0x18005c29d  jnz     loc_18005C4FD
0x18005c2a3  cmp     [rsp+160h+var_E8], 0
0x18005c2a9  lea     edi, [r8+8]
0x18005c2ad  jnz     short loc_18005C2B3
0x18005c2af  xor     ebx, ebx
0x18005c2b1  jmp     short loc_18005C306
0x18005c2b3  cmp     r15d, edi
0x18005c2b6  jnb     short loc_18005C2BF
0x18005c2b8  mov     ebx, 0C0000023h
0x18005c2bd  jmp     short loc_18005C306
0x18005c2bf  mov     eax, edi
0x18005c2c1  mov     [rbp+60h+Size], rax
0x18005c2c5  cmp     edi, 48h ; 'H'
0x18005c2c8  ja      short loc_18005C2D3
0x18005c2ca  xor     r15d, r15d
0x18005c2cd  lea     rdi, [rbp+60h+Src]
0x18005c2d1  jmp     short loc_18005C315
0x18005c2d3  mov     rcx, rax
0x18005c2d6  call    BCryptAlloc
0x18005c2db  mov     r15, rax
0x18005c2de  test    rax, rax
0x18005c2e1  jnz     short loc_18005C30D
0x18005c2e3  mov     r9d, 100h
0x18005c2e9  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005c2f0  lea     rdx, aStatus; "Status"
0x18005c2f7  mov     ecx, 0C0000017h
0x18005c2fc  mov     ebx, 0C0000017h
0x18005c301  call    DebugTraceError
0x18005c306  mov     [rsi], edi
0x18005c308  jmp     loc_18005C4A0
0x18005c30d  mov     r8d, [rsp+160h+var_100]
0x18005c312  mov     rdi, rax
0x18005c315  mov     rcx, [rsp+160h+var_F0]
0x18005c31a  lea     rdx, [rdi+8]
0x18005c31e  call    RouterGetKeyDataBlob
0x18005c323  mov     ebx, eax
0x18005c325  test    eax, eax
0x18005c327  jns     short loc_18005C34C
0x18005c329  mov     r9d, 112h
0x18005c32f  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005c336  lea     rdx, aStatus; "Status"
0x18005c33d  mov     ecx, eax
0x18005c33f  call    DebugTraceError
0x18005c344  mov     r13d, r14d
0x18005c347  jmp     loc_18005C467
0x18005c34c  mov     edx, [rsp+160h+var_100]
0x18005c350  mov     r13d, r14d
0x18005c353  shr     rdx, 3
0x18005c357  mov     rax, 0A6A6A6A6A6A6A6A6h
0x18005c361  mov     [rbp+60h+var_D0], rdx
0x18005c365  xor     r14d, r14d
0x18005c368  cmp     r14d, 6
0x18005c36c  jnb     loc_18005C44E
0x18005c372  xor     ecx, ecx
0x18005c374  mov     r8d, ecx
0x18005c377  mov     dword ptr [rsp+160h+var_F0], ecx
0x18005c37b  mov     [rbp+60h+var_C8], r8
0x18005c37f  cmp     r8, rdx
0x18005c382  jnb     loc_18005C429
0x18005c388  mov     [rbp+60h+var_B8], rax
0x18005c38c  lea     rdx, [rbp+60h+var_B8]
0x18005c390  lea     eax, ds:0[rcx*8]
0x18005c397  mov     [rsp+160h+var_118], 0
0x18005c39f  mov     [rbp+60h+var_C0], rax
0x18005c3a3  lea     rcx, [rbp+60h+var_B8]
0x18005c3a7  mov     rax, [rax+rdi+8]
0x18005c3ac  xorps   xmm0, xmm0
0x18005c3af  mov     [rbp+60h+var_B0], rax
0x18005c3b3  xor     r9d, r9d
0x18005c3b6  lea     rax, [rsp+160h+var_FC]
0x18005c3bb  mov     [rsp+160h+var_120], rax
0x18005c3c0  mov     eax, 10h
0x18005c3c5  mov     [rsp+160h+var_128], eax
0x18005c3c9  mov     r8d, eax
0x18005c3cc  mov     [rsp+160h+var_130], rcx
0x18005c3d1  lea     rcx, [rbp+60h+var_A0]
0x18005c3d5  mov     [rsp+160h+var_138], eax
0x18005c3d9  mov     rax, [rbp+60h+var_D8]
0x18005c3dd  mov     [rsp+160h+var_140], rcx
0x18005c3e2  mov     rcx, [rbp+60h+var_E0]
0x18005c3e6  movups  [rbp+60h+var_A0], xmm0
0x18005c3ea  call    _guard_dispatch_icall
0x18005c3ef  mov     ebx, eax
0x18005c3f1  test    eax, eax
0x18005c3f3  js      short loc_18005C431
0x18005c3f5  mov     rdx, [rbp+60h+var_D0]
0x18005c3f9  mov     rcx, [rbp+60h+var_C8]
0x18005c3fd  mov     r8, [rbp+60h+var_C0]
0x18005c401  inc     rcx
0x18005c404  mov     eax, r14d
0x18005c407  imul    rax, rdx
0x18005c40b  add     rax, rcx
0x18005c40e  mov     rcx, [rbp+60h+var_B0]
0x18005c412  bswap   rax
0x18005c415  xor     rax, [rbp+60h+var_B8]
0x18005c419  mov     [r8+rdi+8], rcx
0x18005c41e  mov     ecx, dword ptr [rsp+160h+var_F0]
0x18005c422  inc     ecx
0x18005c424  jmp     loc_18005C374
0x18005c429  inc     r14d
0x18005c42c  jmp     loc_18005C368
0x18005c431  mov     r9d, 135h
0x18005c437  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005c43e  lea     rdx, aStatus; "Status"
0x18005c445  mov     ecx, eax
0x18005c447  call    DebugTraceError
0x18005c44c  jmp     short loc_18005C464
0x18005c44e  mov     r8, [rbp+60h+Size]; Size
0x18005c452  mov     rdx, rdi; Src
0x18005c455  mov     rcx, [rsp+160h+var_E8]; void *
0x18005c45a  mov     [rdi], rax
0x18005c45d  call    memmove
0x18005c462  xor     ebx, ebx
0x18005c464  mov     r14d, r13d
0x18005c467  mov     eax, r12d
0x18005c46a  mov     ecx, r12d
0x18005c46d  add     eax, r14d
0x18005c470  mov     [rsi], eax
0x18005c472  test    rdi, rdi
0x18005c475  jz      short loc_18005C48D
0x18005c477  lea     eax, [rcx+r13]
0x18005c47b  mov     ecx, eax
0x18005c47d  test    eax, eax
0x18005c47f  jz      short loc_18005C48D
0x18005c481  mov     byte ptr [rdi], 0
0x18005c484  inc     rdi
0x18005c487  sub     rcx, 1
0x18005c48b  jnz     short loc_18005C481
0x18005c48d  test    r15, r15
0x18005c490  jz      short loc_18005C49A
0x18005c492  mov     rcx, r15; P
0x18005c495  call    BCryptFree
0x18005c49a  mov     r13d, 10h
0x18005c4a0  mov     rcx, r13
0x18005c4a3  lea     rax, [rbp+60h+var_A0]
0x18005c4a7  mov     byte ptr [rax], 0
0x18005c4aa  inc     rax
0x18005c4ad  sub     rcx, 1
0x18005c4b1  jnz     short loc_18005C4A7
0x18005c4b3  lea     rax, [rbp+60h+var_B8]
0x18005c4b7  mov     byte ptr [rax], 0
0x18005c4ba  inc     rax
0x18005c4bd  sub     r13, 1
0x18005c4c1  jnz     short loc_18005C4B7
0x18005c4c3  lea     rax, [rbp+60h+Size]
0x18005c4c7  mov     byte ptr [rax], 0
0x18005c4ca  inc     rax
0x18005c4cd  sub     r12, 1
0x18005c4d1  jnz     short loc_18005C4C7
0x18005c4d3  mov     eax, ebx
0x18005c4d5  mov     rcx, [rbp+60h+var_40]
0x18005c4d9  xor     rcx, rsp; StackCookie
0x18005c4dc  call    __security_check_cookie
0x18005c4e1  mov     rbx, [rsp+160h+arg_18]
0x18005c4e9  add     rsp, 130h
0x18005c4f0  pop     r15
0x18005c4f2  pop     r14
0x18005c4f4  pop     r13
0x18005c4f6  pop     r12
0x18005c4f8  pop     rdi
0x18005c4f9  pop     rsi
0x18005c4fa  pop     rbp
0x18005c4fb  retn
0x18005c4fd  mov     ebx, 0C0000008h
0x18005c502  mov     dword ptr [rsi], 0
0x18005c508  jmp     short loc_18005C4A0
0x18005c50a  mov     ebx, 0C0000008h
0x18005c50f  mov     r9d, 0C2h
0x18005c515  mov     ecx, 0C0000008h
0x18005c51a  jmp     loc_18005C265
```
