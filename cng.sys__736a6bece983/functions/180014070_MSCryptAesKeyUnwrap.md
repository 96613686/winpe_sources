# MSCryptAesKeyUnwrap

- ea: `0x180014070`
- end: `0x180014449`
- name: `MSCryptAesKeyUnwrap`
- size: `985`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180014da0`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x1800082b0`
- `0x180008850`
- `0x180014070`
- `0x1800148a0`
- `0x180016e80`
- `0x18009f650`
- `0x18009f780`

## string_xrefs

- `0x180014313`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180014358`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x1800143ab`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18001440d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x1800a1675`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

## pseudocode

```c
__int64 __fastcall MSCryptAesKeyUnwrap(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, void *Src, size_t Size)
{
  __int64 v7; // rdx
  int Property; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r14
  void *v12; // r15
  char *v13; // rdi
  unsigned __int64 v14; // rax
  char *v15; // r9
  unsigned int v16; // r12d
  unsigned int v17; // r8d
  int v18; // edx
  int v19; // r8d
  int SymmetricKey; // eax
  __int64 v21; // rax
  __int64 v22; // rcx
  __int128 *v23; // rax
  unsigned __int64 *v24; // rax
  __int64 v25; // rcx
  int *v26; // rax
  __int64 v28; // rax
  __int64 v29; // r9
  __int64 v30; // rcx
  size_t v31; // [rsp+28h] [rbp-D8h]
  unsigned int v32; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v33; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h]
  __int64 v35; // [rsp+60h] [rbp-A0h]
  int v36[2]; // [rsp+68h] [rbp-98h]
  int v37[2]; // [rsp+70h] [rbp-90h]
  unsigned __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h]
  int v40[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v41; // [rsp+90h] [rbp-70h] BYREF
  char v42; // [rsp+A0h] [rbp-60h] BYREF

  *(_QWORD *)v40 = a1;
  *(_QWORD *)v36 = a4;
  *(_QWORD *)v37 = a3;
  v34 = a2;
  v32 = 0;
  v33 = 0;
  Property = MSCryptGetProperty(a2, L"BlockLength", &v32, 4, &v33, 0);
  v11 = 16;
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
  if ( v33 != 4 || v32 != 16 )
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
    v29 = 409;
    v30 = 3221225485LL;
    goto LABEL_45;
  }
  if ( (unsigned int)Size <= 0x48 )
  {
    v12 = 0;
    v13 = &v42;
    goto LABEL_8;
  }
  v28 = MSCryptAlloc((unsigned int)Size, v7, v9, v10);
  v12 = (void *)v28;
  if ( !v28 )
  {
    Property = -1073741801;
    v29 = 429;
    v30 = 3221225495LL;
LABEL_45:
    DebugTraceError(v30, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", v29);
    goto LABEL_23;
  }
  v13 = (char *)v28;
LABEL_8:
  memmove(v13, Src, (unsigned int)Size);
  v14 = *(_QWORD *)v13;
  v15 = v13 + 8;
  v16 = 0;
LABEL_9:
  if ( v16 >= 6 )
  {
    if ( v14 == 0xA6A6A6A6A6A6A6A6uLL )
    {
      LODWORD(v31) = Size - 8;
      SymmetricKey = MSCryptGenerateSymmetricKey(v40[0], v37[0], v36[0], a5, v15, v31, 128);
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
    v17 = (unsigned int)(Size - 8) >> 3;
    while ( 1 )
    {
      if ( !v17 )
      {
        ++v16;
        goto LABEL_9;
      }
      v38 = v14 ^ _byteswap_uint64(v17 + ((unsigned __int64)(unsigned int)(Size - 8) >> 3) * (5 - v16));
      v32 = v17 - 1;
      v35 = 8 * (v17 - 1);
      v39 = *(_QWORD *)&v15[v35];
      v41 = 0;
      Property = MSCryptDecrypt(
                   v34,
                   (unsigned __int64)&v38,
                   0x10u,
                   0,
                   (__int64 *)&v41,
                   16,
                   (unsigned __int64)&v38,
                   0x10u,
                   &v33,
                   0);
      if ( Property < 0 )
        break;
      v15 = v13 + 8;
      v14 = v38;
      v17 = v32;
      *(_QWORD *)&v13[v35 + 8] = v39;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v18,
        v19,
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c",
        218);
  }
  if ( v13 )
  {
    v21 = (unsigned int)Size;
    do
    {
      *v13++ = 0;
      --v21;
    }
    while ( v21 );
  }
  if ( v12 )
    MSCryptFree(v12);
LABEL_23:
  v22 = 16;
  v23 = &v41;
  do
  {
    *(_BYTE *)v23 = 0;
    v23 = (__int128 *)((char *)v23 + 1);
    --v22;
  }
  while ( v22 );
  v24 = &v38;
  do
  {
    *(_BYTE *)v24 = 0;
    v24 = (unsigned __int64 *)((char *)v24 + 1);
    --v11;
  }
  while ( v11 );
  v25 = 8;
  v26 = v40;
  do
  {
    *(_BYTE *)v26 = 0;
    v26 = (int *)((char *)v26 + 1);
    --v25;
  }
  while ( v25 );
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180014070  push    rbp
0x180014072  push    rbx
0x180014073  push    rsi
0x180014074  push    rdi
0x180014075  push    r12
0x180014077  push    r13
0x180014079  push    r14
0x18001407b  push    r15
0x18001407d  lea     rbp, [rsp-8]
0x180014082  sub     rsp, 108h
0x180014089  mov     rax, cs:__security_cookie
0x180014090  xor     rax, rsp
0x180014093  mov     [rbp+40h+var_50], rax
0x180014097  mov     r13, [rbp+40h+Src]
0x18001409b  mov     rax, rdx
0x18001409e  mov     qword ptr [rbp+40h+var_B8], rcx
0x1800140a2  lea     rcx, [rsp+140h+var_EC]
0x1800140a7  mov     qword ptr [rsp+140h+var_D8], r9
0x1800140ac  mov     r9d, 4
0x1800140b2  mov     qword ptr [rsp+140h+var_D0], r8
0x1800140b7  lea     r8, [rsp+140h+var_F0]
0x1800140bc  mov     [rsp+140h+var_E8], rdx
0x1800140c1  lea     rdx, aBlocklength; "BlockLength"
0x1800140c8  mov     dword ptr [rsp+140h+var_118], 0
0x1800140d0  mov     [rsp+140h+var_120], rcx
0x1800140d5  mov     rcx, rax
0x1800140d8  mov     [rsp+140h+var_F0], 0
0x1800140e0  mov     [rsp+140h+var_EC], 0
0x1800140e8  call    MSCryptGetProperty
0x1800140ed  mov     ebx, eax
0x1800140ef  mov     r14d, 10h
0x1800140f5  test    eax, eax
0x1800140f7  js      loc_1800142F4
0x1800140fd  cmp     [rsp+140h+var_EC], 4
0x180014102  jnz     loc_18001432D
0x180014108  cmp     [rsp+140h+var_F0], r14d
0x18001410d  jnz     loc_18001432D
0x180014113  mov     esi, dword ptr [rbp+40h+Size]
0x180014119  test    sil, 7
0x18001411d  jnz     loc_180014434
0x180014123  cmp     esi, r14d
0x180014126  jb      loc_180014434
0x18001412c  mov     ebx, esi
0x18001412e  cmp     esi, 48h ; 'H'
0x180014131  ja      loc_1800143D4
0x180014137  xor     r15d, r15d
0x18001413a  lea     rdi, [rbp+40h+var_A0]
0x18001413e  mov     r8, rbx; Size
0x180014141  lea     r12d, [rsi-8]
0x180014145  mov     rdx, r13; Src
0x180014148  mov     rcx, rdi; void *
0x18001414b  call    memmove
0x180014150  mov     rax, [rdi]
0x180014153  lea     r9, [rdi+8]
0x180014157  mov     r13d, r12d
0x18001415a  shr     r13, 3
0x18001415e  xor     r12d, r12d
0x180014161  cmp     r12d, 6
0x180014165  jnb     loc_18001422E
0x18001416b  mov     r8d, r13d
0x18001416e  test    r8d, r8d
0x180014171  jz      loc_180014226
0x180014177  mov     ecx, r8d
0x18001417a  mov     edx, 5
0x18001417f  sub     edx, r12d
0x180014182  mov     [rsp+140h+var_F8], 0
0x18001418a  imul    rdx, r13
0x18001418e  xorps   xmm0, xmm0
0x180014191  add     rdx, rcx
0x180014194  mov     rcx, [rsp+140h+var_E8]
0x180014199  bswap   rdx
0x18001419c  xor     rdx, rax
0x18001419f  dec     r8d
0x1800141a2  mov     [rsp+140h+var_C8], rdx
0x1800141a7  mov     [rsp+140h+var_F0], r8d
0x1800141ac  lea     rdx, [rsp+140h+var_C8]
0x1800141b1  lea     eax, ds:0[r8*8]
0x1800141b9  mov     r8d, r14d
0x1800141bc  mov     [rsp+140h+var_E0], rax
0x1800141c1  mov     rax, [rax+r9]
0x1800141c5  xor     r9d, r9d
0x1800141c8  mov     [rbp+40h+var_C0], rax
0x1800141cc  lea     rax, [rsp+140h+var_EC]
0x1800141d1  mov     [rsp+140h+var_100], rax
0x1800141d6  lea     rax, [rsp+140h+var_C8]
0x1800141db  mov     [rsp+140h+var_108], r14d
0x1800141e0  mov     qword ptr [rsp+140h+var_110], rax
0x1800141e5  lea     rax, [rbp+40h+var_B0]
0x1800141e9  mov     dword ptr [rsp+140h+var_118], r14d
0x1800141ee  mov     [rsp+140h+var_120], rax
0x1800141f3  movups  [rbp+40h+var_B0], xmm0
0x1800141f7  call    MSCryptDecrypt
0x1800141fc  mov     ebx, eax
0x1800141fe  test    eax, eax
0x180014200  js      loc_180014385
0x180014206  mov     rdx, [rsp+140h+var_E0]
0x18001420b  lea     r9, [rdi+8]
0x18001420f  mov     rcx, [rbp+40h+var_C0]
0x180014213  mov     rax, [rsp+140h+var_C8]
0x180014218  mov     r8d, [rsp+140h+var_F0]
0x18001421d  mov     [rdx+r9], rcx
0x180014221  jmp     loc_18001416E
0x180014226  inc     r12d
0x180014229  jmp     loc_180014161
0x18001422e  mov     rcx, 0A6A6A6A6A6A6A6A6h
0x180014238  cmp     rax, rcx
0x18001423b  jnz     loc_1800143FD
0x180014241  mov     r8, qword ptr [rsp+140h+var_D8]; int
0x180014246  lea     eax, [rsi-8]
0x180014249  mov     rdx, qword ptr [rsp+140h+var_D0]; int
0x18001424e  mov     rcx, qword ptr [rbp+40h+var_B8]; int
0x180014252  mov     [rsp+140h+var_110], 80h; int
0x18001425a  mov     dword ptr [rsp+140h+var_118], eax; Size
0x18001425e  mov     [rsp+140h+var_120], r9; Src
0x180014263  mov     r9d, [rbp+40h+arg_20]; int
0x180014267  call    MSCryptGenerateSymmetricKey
0x18001426c  mov     ebx, eax
0x18001426e  test    eax, eax
0x180014270  js      loc_180014407
0x180014276  xor     ebx, ebx
0x180014278  test    rdi, rdi
0x18001427b  jz      short loc_180014290
0x18001427d  mov     rax, rsi
0x180014280  test    esi, esi
0x180014282  jz      short loc_180014290
0x180014284  mov     byte ptr [rdi], 0
0x180014287  inc     rdi
0x18001428a  sub     rax, 1
0x18001428e  jnz     short loc_180014284
0x180014290  test    r15, r15
0x180014293  jnz     loc_180014427
0x180014299  mov     rcx, r14
0x18001429c  lea     rax, [rbp+40h+var_B0]
0x1800142a0  mov     byte ptr [rax], 0
0x1800142a3  inc     rax
0x1800142a6  sub     rcx, 1
0x1800142aa  jnz     short loc_1800142A0
0x1800142ac  lea     rax, [rsp+140h+var_C8]
0x1800142b1  mov     byte ptr [rax], 0
0x1800142b4  inc     rax
0x1800142b7  sub     r14, 1
0x1800142bb  jnz     short loc_1800142B1
0x1800142bd  lea     ecx, [r14+8]
0x1800142c1  lea     rax, [rbp+40h+var_B8]
0x1800142c5  mov     byte ptr [rax], 0
0x1800142c8  inc     rax
0x1800142cb  sub     rcx, 1
0x1800142cf  jnz     short loc_1800142C5
0x1800142d1  mov     eax, ebx
0x1800142d3  mov     rcx, [rbp+40h+var_50]
0x1800142d7  xor     rcx, rsp; StackCookie
0x1800142da  call    __security_check_cookie
0x1800142df  add     rsp, 108h
0x1800142e6  pop     r15
0x1800142e8  pop     r14
0x1800142ea  pop     r13
0x1800142ec  pop     r12
0x1800142ee  pop     rdi
0x1800142ef  pop     rsi
0x1800142f0  pop     rbx
0x1800142f1  pop     rbp
0x1800142f2  retn
0x1800142f4  mov     rdx, cs:WPP_GLOBAL_Control
0x1800142fb  lea     rax, WPP_GLOBAL_Control
0x180014302  cmp     rdx, rax
0x180014305  jz      short loc_180014299
0x180014307  mov     ecx, [rdx+2Ch]
0x18001430a  test    cl, 1
0x18001430d  jz      short loc_180014299
0x18001430f  mov     rcx, [rdx+18h]
0x180014313  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001431a  mov     [rsp+140h+var_110], 189h
0x180014322  mov     [rsp+140h+var_118], rax
0x180014327  mov     dword ptr [rsp+140h+var_120], ebx
0x18001432b  jmp     short loc_180014374
0x18001432d  mov     ebx, 0C0000008h
0x180014332  mov     rcx, cs:WPP_GLOBAL_Control
0x180014339  lea     rax, WPP_GLOBAL_Control
0x180014340  cmp     rcx, rax
0x180014343  jz      loc_180014299
0x180014349  mov     eax, [rcx+2Ch]
0x18001434c  test    al, 1
0x18001434e  jz      loc_180014299
0x180014354  mov     rcx, [rcx+18h]
0x180014358  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001435f  mov     [rsp+140h+var_110], 191h
0x180014367  mov     [rsp+140h+var_118], rax
0x18001436c  mov     dword ptr [rsp+140h+var_120], 0C0000008h
0x180014374  lea     r9, aStatus; "Status"
0x18001437b  call    WPP_SF_sDsd
0x180014380  jmp     loc_180014299
0x180014385  mov     rcx, cs:WPP_GLOBAL_Control
0x18001438c  lea     rax, WPP_GLOBAL_Control
0x180014393  cmp     rcx, rax
0x180014396  jz      loc_180014278
0x18001439c  mov     eax, [rcx+2Ch]
0x18001439f  test    al, 1
0x1800143a1  jz      loc_180014278
0x1800143a7  mov     rcx, [rcx+18h]
0x1800143ab  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800143b2  mov     [rsp+140h+var_110], 1DAh
0x1800143ba  lea     r9, aStatus; "Status"
0x1800143c1  mov     [rsp+140h+var_118], rax
0x1800143c6  mov     dword ptr [rsp+140h+var_120], ebx
0x1800143ca  call    WPP_SF_sDsd
0x1800143cf  jmp     loc_180014278
0x1800143d4  mov     rcx, rbx
0x1800143d7  call    MSCryptAlloc
0x1800143dc  mov     r15, rax
0x1800143df  test    rax, rax
0x1800143e2  jnz     loc_1800A1666
0x1800143e8  mov     ebx, 0C0000017h
0x1800143ed  mov     r9d, 1ADh
0x1800143f3  mov     ecx, 0C0000017h
0x1800143f8  jmp     loc_1800A166E
0x1800143fd  mov     ebx, 0C000A002h
0x180014402  jmp     loc_180014278
0x180014407  mov     r9d, 1F4h
0x18001440d  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014414  lea     rdx, aStatus; "Status"
0x18001441b  mov     ecx, eax
0x18001441d  call    DebugTraceError
0x180014422  jmp     loc_180014278
0x180014427  mov     rcx, r15; P
0x18001442a  call    MSCryptFree
0x18001442f  jmp     loc_180014299
0x180014434  mov     ebx, 0C000000Dh
0x180014439  mov     r9d, 199h
0x18001443f  mov     ecx, 0C000000Dh
0x180014444  jmp     loc_1800A166E
0x1800a1666  mov     rdi, rax
0x1800a1669  jmp     loc_18001413E
0x1800a166e  lea     rdx, aStatus; "Status"
0x1800a1675  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a167c  call    DebugTraceError
0x1800a1681  nop
0x1800a1682  jmp     loc_180014299
```
