# MSCryptAesKeyUnwrap

- ea: `0x180016fc0`
- end: `0x180017399`
- name: `MSCryptAesKeyUnwrap`
- size: `985`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180017cf0`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x180008850`
- `0x180016fc0`
- `0x1800177f0`
- `0x180019dd0`
- `0x18009d820`
- `0x18009da40`

## string_xrefs

- `0x180017263`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x1800172a8`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x1800172fb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18001735d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18009fabf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptAesKeyUnwrap(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, void *Src, size_t Size)
{
  __int64 v7; // rdx
  int Property; // ebx
  int v9; // r8d
  __int64 v10; // r14
  void *v11; // r15
  char *v12; // rdi
  unsigned __int64 v13; // rax
  char *v14; // r9
  unsigned int v15; // r12d
  unsigned int v16; // r8d
  int v17; // edx
  int v18; // r8d
  int SymmetricKey; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  __int128 *v22; // rax
  unsigned __int64 *v23; // rax
  __int64 v24; // rcx
  int *v25; // rax
  __int64 v27; // rax
  __int64 v28; // r9
  __int64 v29; // rcx
  size_t v30; // [rsp+28h] [rbp-D8h]
  unsigned int v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  int v35[2]; // [rsp+68h] [rbp-98h]
  int v36[2]; // [rsp+70h] [rbp-90h]
  unsigned __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h]
  int v39[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v40; // [rsp+90h] [rbp-70h] BYREF
  char v41; // [rsp+A0h] [rbp-60h] BYREF

  *(_QWORD *)v39 = a1;
  *(_QWORD *)v35 = a4;
  *(_QWORD *)v36 = a3;
  v33 = a2;
  v31 = 0;
  v32 = 0;
  Property = MSCryptGetProperty(a2, L"BlockLength", &v31, 4, &v32, 0);
  v10 = 16;
  if ( Property < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        (_DWORD)WPP_GLOBAL_Control,
        v9,
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        137);
    goto LABEL_23;
  }
  if ( v32 != 4 || v31 != 16 )
  {
    Property = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v7,
        v9,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        145);
    goto LABEL_23;
  }
  if ( (Size & 7) != 0 || (unsigned int)Size < 0x10 )
  {
    Property = -1073741811;
    v28 = 409;
    v29 = 3221225485LL;
    goto LABEL_45;
  }
  if ( (unsigned int)Size <= 0x48 )
  {
    v11 = 0;
    v12 = &v41;
    goto LABEL_8;
  }
  v27 = MSCryptAlloc((unsigned int)Size, v7);
  v11 = (void *)v27;
  if ( !v27 )
  {
    Property = -1073741801;
    v28 = 429;
    v29 = 3221225495LL;
LABEL_45:
    DebugTraceError(v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", v28);
    goto LABEL_23;
  }
  v12 = (char *)v27;
LABEL_8:
  memmove(v12, Src, (unsigned int)Size);
  v13 = *(_QWORD *)v12;
  v14 = v12 + 8;
  v15 = 0;
LABEL_9:
  if ( v15 >= 6 )
  {
    if ( v13 == 0xA6A6A6A6A6A6A6A6uLL )
    {
      LODWORD(v30) = Size - 8;
      SymmetricKey = MSCryptGenerateSymmetricKey(v39[0], v36[0], v35[0], a5, v14, v30, 128);
      Property = SymmetricKey;
      if ( SymmetricKey < 0 )
        DebugTraceError(
          (unsigned int)SymmetricKey,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
          500);
      else
        Property = 0;
    }
    else
    {
      Property = -1073700862;
    }
  }
  else
  {
    v16 = (unsigned int)(Size - 8) >> 3;
    while ( 1 )
    {
      if ( !v16 )
      {
        ++v15;
        goto LABEL_9;
      }
      v37 = v13 ^ _byteswap_uint64(v16 + ((unsigned __int64)(unsigned int)(Size - 8) >> 3) * (5 - v15));
      v31 = v16 - 1;
      v34 = 8 * (v16 - 1);
      v38 = *(_QWORD *)&v14[v34];
      v40 = 0;
      Property = MSCryptDecrypt(
                   v33,
                   (unsigned __int64)&v37,
                   16,
                   0,
                   (__int64 *)&v40,
                   16,
                   (unsigned __int64)&v37,
                   0x10u,
                   &v32,
                   0);
      if ( Property < 0 )
        break;
      v14 = v12 + 8;
      v13 = v37;
      v16 = v31;
      *(_QWORD *)&v12[v34 + 8] = v38;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v17,
        v18,
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        218);
  }
  if ( v12 )
  {
    v20 = (unsigned int)Size;
    do
    {
      *v12++ = 0;
      --v20;
    }
    while ( v20 );
  }
  if ( v11 )
    MSCryptFree(v11);
LABEL_23:
  v21 = 16;
  v22 = &v40;
  do
  {
    *(_BYTE *)v22 = 0;
    v22 = (__int128 *)((char *)v22 + 1);
    --v21;
  }
  while ( v21 );
  v23 = &v37;
  do
  {
    *(_BYTE *)v23 = 0;
    v23 = (unsigned __int64 *)((char *)v23 + 1);
    --v10;
  }
  while ( v10 );
  v24 = 8;
  v25 = v39;
  do
  {
    *(_BYTE *)v25 = 0;
    v25 = (int *)((char *)v25 + 1);
    --v24;
  }
  while ( v24 );
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180016fc0  push    rbp
0x180016fc2  push    rbx
0x180016fc3  push    rsi
0x180016fc4  push    rdi
0x180016fc5  push    r12
0x180016fc7  push    r13
0x180016fc9  push    r14
0x180016fcb  push    r15
0x180016fcd  lea     rbp, [rsp-8]
0x180016fd2  sub     rsp, 108h
0x180016fd9  mov     rax, cs:__security_cookie
0x180016fe0  xor     rax, rsp
0x180016fe3  mov     [rbp+40h+var_50], rax
0x180016fe7  mov     r13, [rbp+40h+Src]
0x180016feb  mov     rax, rdx
0x180016fee  mov     qword ptr [rbp+40h+var_B8], rcx
0x180016ff2  lea     rcx, [rsp+140h+var_EC]
0x180016ff7  mov     qword ptr [rsp+140h+var_D8], r9
0x180016ffc  mov     r9d, 4
0x180017002  mov     qword ptr [rsp+140h+var_D0], r8
0x180017007  lea     r8, [rsp+140h+var_F0]
0x18001700c  mov     [rsp+140h+var_E8], rdx
0x180017011  lea     rdx, aBlocklength; "BlockLength"
0x180017018  mov     dword ptr [rsp+140h+var_118], 0
0x180017020  mov     [rsp+140h+var_120], rcx
0x180017025  mov     rcx, rax
0x180017028  mov     [rsp+140h+var_F0], 0
0x180017030  mov     [rsp+140h+var_EC], 0
0x180017038  call    MSCryptGetProperty
0x18001703d  mov     ebx, eax
0x18001703f  mov     r14d, 10h
0x180017045  test    eax, eax
0x180017047  js      loc_180017244
0x18001704d  cmp     [rsp+140h+var_EC], 4
0x180017052  jnz     loc_18001727D
0x180017058  cmp     [rsp+140h+var_F0], r14d
0x18001705d  jnz     loc_18001727D
0x180017063  mov     esi, dword ptr [rbp+40h+Size]
0x180017069  test    sil, 7
0x18001706d  jnz     loc_180017384
0x180017073  cmp     esi, r14d
0x180017076  jb      loc_180017384
0x18001707c  mov     ebx, esi
0x18001707e  cmp     esi, 48h ; 'H'
0x180017081  ja      loc_180017324
0x180017087  xor     r15d, r15d
0x18001708a  lea     rdi, [rbp+40h+var_A0]
0x18001708e  mov     r8, rbx; Size
0x180017091  lea     r12d, [rsi-8]
0x180017095  mov     rdx, r13; Src
0x180017098  mov     rcx, rdi; void *
0x18001709b  call    memmove
0x1800170a0  mov     rax, [rdi]
0x1800170a3  lea     r9, [rdi+8]
0x1800170a7  mov     r13d, r12d
0x1800170aa  shr     r13, 3
0x1800170ae  xor     r12d, r12d
0x1800170b1  cmp     r12d, 6
0x1800170b5  jnb     loc_18001717E
0x1800170bb  mov     r8d, r13d
0x1800170be  test    r8d, r8d
0x1800170c1  jz      loc_180017176
0x1800170c7  mov     ecx, r8d
0x1800170ca  mov     edx, 5
0x1800170cf  sub     edx, r12d
0x1800170d2  mov     [rsp+140h+var_F8], 0
0x1800170da  imul    rdx, r13
0x1800170de  xorps   xmm0, xmm0
0x1800170e1  add     rdx, rcx
0x1800170e4  mov     rcx, [rsp+140h+var_E8]
0x1800170e9  bswap   rdx
0x1800170ec  xor     rdx, rax
0x1800170ef  dec     r8d
0x1800170f2  mov     [rsp+140h+var_C8], rdx
0x1800170f7  mov     [rsp+140h+var_F0], r8d
0x1800170fc  lea     rdx, [rsp+140h+var_C8]
0x180017101  lea     eax, ds:0[r8*8]
0x180017109  mov     r8d, r14d
0x18001710c  mov     [rsp+140h+var_E0], rax
0x180017111  mov     rax, [rax+r9]
0x180017115  xor     r9d, r9d
0x180017118  mov     [rbp+40h+var_C0], rax
0x18001711c  lea     rax, [rsp+140h+var_EC]
0x180017121  mov     [rsp+140h+var_100], rax
0x180017126  lea     rax, [rsp+140h+var_C8]
0x18001712b  mov     [rsp+140h+var_108], r14d
0x180017130  mov     qword ptr [rsp+140h+var_110], rax
0x180017135  lea     rax, [rbp+40h+var_B0]
0x180017139  mov     dword ptr [rsp+140h+var_118], r14d
0x18001713e  mov     [rsp+140h+var_120], rax
0x180017143  movups  [rbp+40h+var_B0], xmm0
0x180017147  call    MSCryptDecrypt
0x18001714c  mov     ebx, eax
0x18001714e  test    eax, eax
0x180017150  js      loc_1800172D5
0x180017156  mov     rdx, [rsp+140h+var_E0]
0x18001715b  lea     r9, [rdi+8]
0x18001715f  mov     rcx, [rbp+40h+var_C0]
0x180017163  mov     rax, [rsp+140h+var_C8]
0x180017168  mov     r8d, [rsp+140h+var_F0]
0x18001716d  mov     [rdx+r9], rcx
0x180017171  jmp     loc_1800170BE
0x180017176  inc     r12d
0x180017179  jmp     loc_1800170B1
0x18001717e  mov     rcx, 0A6A6A6A6A6A6A6A6h
0x180017188  cmp     rax, rcx
0x18001718b  jnz     loc_18001734D
0x180017191  mov     r8, qword ptr [rsp+140h+var_D8]; int
0x180017196  lea     eax, [rsi-8]
0x180017199  mov     rdx, qword ptr [rsp+140h+var_D0]; int
0x18001719e  mov     rcx, qword ptr [rbp+40h+var_B8]; int
0x1800171a2  mov     [rsp+140h+var_110], 80h; int
0x1800171aa  mov     dword ptr [rsp+140h+var_118], eax; Size
0x1800171ae  mov     [rsp+140h+var_120], r9; Src
0x1800171b3  mov     r9d, [rbp+40h+arg_20]; int
0x1800171b7  call    MSCryptGenerateSymmetricKey
0x1800171bc  mov     ebx, eax
0x1800171be  test    eax, eax
0x1800171c0  js      loc_180017357
0x1800171c6  xor     ebx, ebx
0x1800171c8  test    rdi, rdi
0x1800171cb  jz      short loc_1800171E0
0x1800171cd  mov     rax, rsi
0x1800171d0  test    esi, esi
0x1800171d2  jz      short loc_1800171E0
0x1800171d4  mov     byte ptr [rdi], 0
0x1800171d7  inc     rdi
0x1800171da  sub     rax, 1
0x1800171de  jnz     short loc_1800171D4
0x1800171e0  test    r15, r15
0x1800171e3  jnz     loc_180017377
0x1800171e9  mov     rcx, r14
0x1800171ec  lea     rax, [rbp+40h+var_B0]
0x1800171f0  mov     byte ptr [rax], 0
0x1800171f3  inc     rax
0x1800171f6  sub     rcx, 1
0x1800171fa  jnz     short loc_1800171F0
0x1800171fc  lea     rax, [rsp+140h+var_C8]
0x180017201  mov     byte ptr [rax], 0
0x180017204  inc     rax
0x180017207  sub     r14, 1
0x18001720b  jnz     short loc_180017201
0x18001720d  lea     ecx, [r14+8]
0x180017211  lea     rax, [rbp+40h+var_B8]
0x180017215  mov     byte ptr [rax], 0
0x180017218  inc     rax
0x18001721b  sub     rcx, 1
0x18001721f  jnz     short loc_180017215
0x180017221  mov     eax, ebx
0x180017223  mov     rcx, [rbp+40h+var_50]
0x180017227  xor     rcx, rsp; StackCookie
0x18001722a  call    __security_check_cookie
0x18001722f  add     rsp, 108h
0x180017236  pop     r15
0x180017238  pop     r14
0x18001723a  pop     r13
0x18001723c  pop     r12
0x18001723e  pop     rdi
0x18001723f  pop     rsi
0x180017240  pop     rbx
0x180017241  pop     rbp
0x180017242  retn
0x180017244  mov     rdx, cs:WPP_GLOBAL_Control
0x18001724b  lea     rax, WPP_GLOBAL_Control
0x180017252  cmp     rdx, rax
0x180017255  jz      short loc_1800171E9
0x180017257  mov     ecx, [rdx+2Ch]
0x18001725a  test    cl, 1
0x18001725d  jz      short loc_1800171E9
0x18001725f  mov     rcx, [rdx+18h]
0x180017263  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001726a  mov     [rsp+140h+var_110], 189h
0x180017272  mov     [rsp+140h+var_118], rax
0x180017277  mov     dword ptr [rsp+140h+var_120], ebx
0x18001727b  jmp     short loc_1800172C4
0x18001727d  mov     ebx, 0C0000008h
0x180017282  mov     rcx, cs:WPP_GLOBAL_Control
0x180017289  lea     rax, WPP_GLOBAL_Control
0x180017290  cmp     rcx, rax
0x180017293  jz      loc_1800171E9
0x180017299  mov     eax, [rcx+2Ch]
0x18001729c  test    al, 1
0x18001729e  jz      loc_1800171E9
0x1800172a4  mov     rcx, [rcx+18h]
0x1800172a8  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800172af  mov     [rsp+140h+var_110], 191h
0x1800172b7  mov     [rsp+140h+var_118], rax
0x1800172bc  mov     dword ptr [rsp+140h+var_120], 0C0000008h
0x1800172c4  lea     r9, aStatus; "Status"
0x1800172cb  call    WPP_SF_sDsd
0x1800172d0  jmp     loc_1800171E9
0x1800172d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172dc  lea     rax, WPP_GLOBAL_Control
0x1800172e3  cmp     rcx, rax
0x1800172e6  jz      loc_1800171C8
0x1800172ec  mov     eax, [rcx+2Ch]
0x1800172ef  test    al, 1
0x1800172f1  jz      loc_1800171C8
0x1800172f7  mov     rcx, [rcx+18h]
0x1800172fb  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017302  mov     [rsp+140h+var_110], 1DAh
0x18001730a  lea     r9, aStatus; "Status"
0x180017311  mov     [rsp+140h+var_118], rax
0x180017316  mov     dword ptr [rsp+140h+var_120], ebx
0x18001731a  call    WPP_SF_sDsd
0x18001731f  jmp     loc_1800171C8
0x180017324  mov     rcx, rbx
0x180017327  call    MSCryptAlloc
0x18001732c  mov     r15, rax
0x18001732f  test    rax, rax
0x180017332  jnz     loc_18009FAB0
0x180017338  mov     ebx, 0C0000017h
0x18001733d  mov     r9d, 1ADh
0x180017343  mov     ecx, 0C0000017h
0x180017348  jmp     loc_18009FAB8
0x18001734d  mov     ebx, 0C000A002h
0x180017352  jmp     loc_1800171C8
0x180017357  mov     r9d, 1F4h
0x18001735d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180017364  lea     rdx, aStatus; "Status"
0x18001736b  mov     ecx, eax
0x18001736d  call    DebugTraceError
0x180017372  jmp     loc_1800171C8
0x180017377  mov     rcx, r15; P
0x18001737a  call    MSCryptFree
0x18001737f  jmp     loc_1800171E9
0x180017384  mov     ebx, 0C000000Dh
0x180017389  mov     r9d, 199h
0x18001738f  mov     ecx, 0C000000Dh
0x180017394  jmp     loc_18009FAB8
0x18009fab0  mov     rdi, rax
0x18009fab3  jmp     loc_18001708E
0x18009fab8  lea     rdx, aStatus; "Status"
0x18009fabf  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009fac6  call    DebugTraceError
0x18009facb  nop
0x18009facc  jmp     loc_1800171E9
```
