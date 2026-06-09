# RouterAesKeyWrap

- ea: `0x18006632c`
- end: `0x1800666ef`
- name: `RouterAesKeyWrap`
- size: `963`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800632a0`

## callees

- `0x18001155c`
- `0x180025ec0`
- `0x180025fb0`
- `0x18006632c`
- `0x1800666f8`
- `0x1800a4260`
- `0x1800a4300`
- `0x1800a45c0`

## string_xrefs

- `0x18006643c`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x1800664b9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x1800664ff`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`
- `0x180066607`: `onecore\ds\security\cryptoapi\ncrypt\crypt\routeraeskeywrap.c`

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
0x18006632c  mov     [rsp-8+arg_18], rbx
0x180066331  push    rbp
0x180066332  push    rsi
0x180066333  push    rdi
0x180066334  push    r12
0x180066336  push    r13
0x180066338  push    r14
0x18006633a  push    r15
0x18006633c  lea     rbp, [rsp-30h]
0x180066341  sub     rsp, 130h
0x180066348  mov     rax, cs:__security_cookie
0x18006634f  xor     rax, rsp
0x180066352  mov     [rbp+60h+var_40], rax
0x180066356  mov     rax, [rcx+8]
0x18006635a  mov     r15d, r9d
0x18006635d  mov     r10, [rdx+10h]
0x180066361  xor     r9d, r9d
0x180066364  mov     rdi, [rcx+10h]
0x180066368  mov     rsi, [rbp+60h+arg_20]
0x18006636f  mov     [rsp+160h+var_F8], r9d
0x180066374  mov     [rsp+160h+var_100], r9d
0x180066379  mov     [rsp+160h+var_FC], r9d
0x18006637e  mov     r14, [rax+40h]
0x180066382  mov     rax, [rdx+8]
0x180066386  lea     rdx, aBlocklength; "BlockLength"
0x18006638d  mov     [rsp+160h+var_E8], r8
0x180066392  mov     [rsp+160h+var_F0], rcx
0x180066397  lea     rcx, [rsp+160h+var_FC]
0x18006639c  mov     [rsp+160h+var_138], r9d
0x1800663a1  mov     r9d, 4
0x1800663a7  mov     r8, [rax+60h]
0x1800663ab  mov     rax, [rax+40h]
0x1800663af  mov     [rbp+60h+var_D8], r8
0x1800663b3  lea     r8, [rsp+160h+var_F8]
0x1800663b8  mov     [rsp+160h+var_140], rcx
0x1800663bd  mov     rcx, r10
0x1800663c0  mov     [rbp+60h+var_E0], r10
0x1800663c4  call    _guard_dispatch_icall
0x1800663c9  mov     r12d, 8
0x1800663cf  mov     ebx, eax
0x1800663d1  lea     r13d, [r12+8]
0x1800663d6  test    eax, eax
0x1800663d8  jns     short loc_1800663E2
0x1800663da  mov     r9d, 0BAh
0x1800663e0  jmp     short loc_180066433
0x1800663e2  cmp     [rsp+160h+var_FC], 4
0x1800663e7  jnz     loc_1800666DA
0x1800663ed  cmp     [rsp+160h+var_F8], r13d
0x1800663f2  jnz     loc_1800666DA
0x1800663f8  lea     rax, [rsp+160h+var_FC]
0x1800663fd  mov     [rsp+160h+var_138], 0
0x180066405  mov     [rsp+160h+var_140], rax
0x18006640a  lea     r8, [rsp+160h+var_100]
0x18006640f  mov     rax, r14
0x180066412  lea     rdx, aKeylength; "KeyLength"
0x180066419  mov     r9d, 4
0x18006641f  mov     rcx, rdi
0x180066422  call    _guard_dispatch_icall
0x180066427  mov     ebx, eax
0x180066429  test    eax, eax
0x18006642b  jns     short loc_18006644D
0x18006642d  mov     r9d, 0D0h
0x180066433  mov     ecx, eax
0x180066435  lea     rdx, aStatus; "Status"
0x18006643c  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180066443  call    DebugTraceError
0x180066448  jmp     loc_1800666D2
0x18006644d  mov     r8d, [rsp+160h+var_100]
0x180066452  shr     r8d, 3
0x180066456  cmp     [rsp+160h+var_FC], 4
0x18006645b  mov     r14d, r8d
0x18006645e  mov     [rsp+160h+var_100], r8d
0x180066463  jnz     loc_1800666CD
0x180066469  test    r14b, 7
0x18006646d  jnz     loc_1800666CD
0x180066473  cmp     [rsp+160h+var_E8], 0
0x180066479  lea     edi, [r8+8]
0x18006647d  jnz     short loc_180066483
0x18006647f  xor     ebx, ebx
0x180066481  jmp     short loc_1800664D6
0x180066483  cmp     r15d, edi
0x180066486  jnb     short loc_18006648F
0x180066488  mov     ebx, 0C0000023h
0x18006648d  jmp     short loc_1800664D6
0x18006648f  mov     eax, edi
0x180066491  mov     [rbp+60h+Size], rax
0x180066495  cmp     edi, 48h ; 'H'
0x180066498  ja      short loc_1800664A3
0x18006649a  xor     r15d, r15d
0x18006649d  lea     rdi, [rbp+60h+Src]
0x1800664a1  jmp     short loc_1800664E5
0x1800664a3  mov     rcx, rax
0x1800664a6  call    BCryptAlloc
0x1800664ab  mov     r15, rax
0x1800664ae  test    rax, rax
0x1800664b1  jnz     short loc_1800664DD
0x1800664b3  mov     r9d, 100h
0x1800664b9  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800664c0  lea     rdx, aStatus; "Status"
0x1800664c7  mov     ecx, 0C0000017h
0x1800664cc  mov     ebx, 0C0000017h
0x1800664d1  call    DebugTraceError
0x1800664d6  mov     [rsi], edi
0x1800664d8  jmp     loc_180066670
0x1800664dd  mov     r8d, [rsp+160h+var_100]
0x1800664e2  mov     rdi, rax
0x1800664e5  mov     rcx, [rsp+160h+var_F0]
0x1800664ea  lea     rdx, [rdi+8]
0x1800664ee  call    RouterGetKeyDataBlob
0x1800664f3  mov     ebx, eax
0x1800664f5  test    eax, eax
0x1800664f7  jns     short loc_18006651C
0x1800664f9  mov     r9d, 112h
0x1800664ff  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180066506  lea     rdx, aStatus; "Status"
0x18006650d  mov     ecx, eax
0x18006650f  call    DebugTraceError
0x180066514  mov     r13d, r14d
0x180066517  jmp     loc_180066637
0x18006651c  mov     edx, [rsp+160h+var_100]
0x180066520  mov     r13d, r14d
0x180066523  shr     rdx, 3
0x180066527  mov     rax, 0A6A6A6A6A6A6A6A6h
0x180066531  mov     [rbp+60h+var_D0], rdx
0x180066535  xor     r14d, r14d
0x180066538  cmp     r14d, 6
0x18006653c  jnb     loc_18006661E
0x180066542  xor     ecx, ecx
0x180066544  mov     r8d, ecx
0x180066547  mov     dword ptr [rsp+160h+var_F0], ecx
0x18006654b  mov     [rbp+60h+var_C8], r8
0x18006654f  cmp     r8, rdx
0x180066552  jnb     loc_1800665F9
0x180066558  mov     [rbp+60h+var_B8], rax
0x18006655c  lea     rdx, [rbp+60h+var_B8]
0x180066560  lea     eax, ds:0[rcx*8]
0x180066567  mov     [rsp+160h+var_118], 0
0x18006656f  mov     [rbp+60h+var_C0], rax
0x180066573  lea     rcx, [rbp+60h+var_B8]
0x180066577  mov     rax, [rax+rdi+8]
0x18006657c  xorps   xmm0, xmm0
0x18006657f  mov     [rbp+60h+var_B0], rax
0x180066583  xor     r9d, r9d
0x180066586  lea     rax, [rsp+160h+var_FC]
0x18006658b  mov     [rsp+160h+var_120], rax
0x180066590  mov     eax, 10h
0x180066595  mov     [rsp+160h+var_128], eax
0x180066599  mov     r8d, eax
0x18006659c  mov     [rsp+160h+var_130], rcx
0x1800665a1  lea     rcx, [rbp+60h+var_A0]
0x1800665a5  mov     [rsp+160h+var_138], eax
0x1800665a9  mov     rax, [rbp+60h+var_D8]
0x1800665ad  mov     [rsp+160h+var_140], rcx
0x1800665b2  mov     rcx, [rbp+60h+var_E0]
0x1800665b6  movups  [rbp+60h+var_A0], xmm0
0x1800665ba  call    _guard_dispatch_icall
0x1800665bf  mov     ebx, eax
0x1800665c1  test    eax, eax
0x1800665c3  js      short loc_180066601
0x1800665c5  mov     rdx, [rbp+60h+var_D0]
0x1800665c9  mov     rcx, [rbp+60h+var_C8]
0x1800665cd  mov     r8, [rbp+60h+var_C0]
0x1800665d1  inc     rcx
0x1800665d4  mov     eax, r14d
0x1800665d7  imul    rax, rdx
0x1800665db  add     rax, rcx
0x1800665de  mov     rcx, [rbp+60h+var_B0]
0x1800665e2  bswap   rax
0x1800665e5  xor     rax, [rbp+60h+var_B8]
0x1800665e9  mov     [r8+rdi+8], rcx
0x1800665ee  mov     ecx, dword ptr [rsp+160h+var_F0]
0x1800665f2  inc     ecx
0x1800665f4  jmp     loc_180066544
0x1800665f9  inc     r14d
0x1800665fc  jmp     loc_180066538
0x180066601  mov     r9d, 135h
0x180066607  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006660e  lea     rdx, aStatus; "Status"
0x180066615  mov     ecx, eax
0x180066617  call    DebugTraceError
0x18006661c  jmp     short loc_180066634
0x18006661e  mov     r8, [rbp+60h+Size]; Size
0x180066622  mov     rdx, rdi; Src
0x180066625  mov     rcx, [rsp+160h+var_E8]; void *
0x18006662a  mov     [rdi], rax
0x18006662d  call    memmove
0x180066632  xor     ebx, ebx
0x180066634  mov     r14d, r13d
0x180066637  mov     eax, r12d
0x18006663a  mov     ecx, r12d
0x18006663d  add     eax, r14d
0x180066640  mov     [rsi], eax
0x180066642  test    rdi, rdi
0x180066645  jz      short loc_18006665D
0x180066647  lea     eax, [rcx+r13]
0x18006664b  mov     ecx, eax
0x18006664d  test    eax, eax
0x18006664f  jz      short loc_18006665D
0x180066651  mov     byte ptr [rdi], 0
0x180066654  inc     rdi
0x180066657  sub     rcx, 1
0x18006665b  jnz     short loc_180066651
0x18006665d  test    r15, r15
0x180066660  jz      short loc_18006666A
0x180066662  mov     rcx, r15; P
0x180066665  call    BCryptFree
0x18006666a  mov     r13d, 10h
0x180066670  mov     rcx, r13
0x180066673  lea     rax, [rbp+60h+var_A0]
0x180066677  mov     byte ptr [rax], 0
0x18006667a  inc     rax
0x18006667d  sub     rcx, 1
0x180066681  jnz     short loc_180066677
0x180066683  lea     rax, [rbp+60h+var_B8]
0x180066687  mov     byte ptr [rax], 0
0x18006668a  inc     rax
0x18006668d  sub     r13, 1
0x180066691  jnz     short loc_180066687
0x180066693  lea     rax, [rbp+60h+Size]
0x180066697  mov     byte ptr [rax], 0
0x18006669a  inc     rax
0x18006669d  sub     r12, 1
0x1800666a1  jnz     short loc_180066697
0x1800666a3  mov     eax, ebx
0x1800666a5  mov     rcx, [rbp+60h+var_40]
0x1800666a9  xor     rcx, rsp; StackCookie
0x1800666ac  call    __security_check_cookie
0x1800666b1  mov     rbx, [rsp+160h+arg_18]
0x1800666b9  add     rsp, 130h
0x1800666c0  pop     r15
0x1800666c2  pop     r14
0x1800666c4  pop     r13
0x1800666c6  pop     r12
0x1800666c8  pop     rdi
0x1800666c9  pop     rsi
0x1800666ca  pop     rbp
0x1800666cb  retn
0x1800666cd  mov     ebx, 0C0000008h
0x1800666d2  mov     dword ptr [rsi], 0
0x1800666d8  jmp     short loc_180066670
0x1800666da  mov     ebx, 0C0000008h
0x1800666df  mov     r9d, 0C2h
0x1800666e5  mov     ecx, 0C0000008h
0x1800666ea  jmp     loc_180066435
```
