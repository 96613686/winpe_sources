# MSCryptAesKeyUnwrap

- ea: `0x1800210a0`
- end: `0x180021479`
- name: `MSCryptAesKeyUnwrap`
- size: `985`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180021e20`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x1800123d0`
- `0x180012970`
- `0x1800210a0`
- `0x1800218d0`
- `0x180023f00`
- `0x1800a4260`
- `0x1800a45c0`

## string_xrefs

- `0x180021343`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180021388`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x1800213db`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18002143d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x1800a685d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

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
0x1800210a0  push    rbp
0x1800210a2  push    rbx
0x1800210a3  push    rsi
0x1800210a4  push    rdi
0x1800210a5  push    r12
0x1800210a7  push    r13
0x1800210a9  push    r14
0x1800210ab  push    r15
0x1800210ad  lea     rbp, [rsp-8]
0x1800210b2  sub     rsp, 108h
0x1800210b9  mov     rax, cs:__security_cookie
0x1800210c0  xor     rax, rsp
0x1800210c3  mov     [rbp+40h+var_50], rax
0x1800210c7  mov     r13, [rbp+40h+Src]
0x1800210cb  mov     rax, rdx
0x1800210ce  mov     qword ptr [rbp+40h+var_B8], rcx
0x1800210d2  lea     rcx, [rsp+140h+var_EC]
0x1800210d7  mov     qword ptr [rsp+140h+var_D8], r9
0x1800210dc  mov     r9d, 4
0x1800210e2  mov     qword ptr [rsp+140h+var_D0], r8
0x1800210e7  lea     r8, [rsp+140h+var_F0]
0x1800210ec  mov     [rsp+140h+var_E8], rdx
0x1800210f1  lea     rdx, aBlocklength; "BlockLength"
0x1800210f8  mov     dword ptr [rsp+140h+var_118], 0
0x180021100  mov     [rsp+140h+var_120], rcx
0x180021105  mov     rcx, rax
0x180021108  mov     [rsp+140h+var_F0], 0
0x180021110  mov     [rsp+140h+var_EC], 0
0x180021118  call    MSCryptGetProperty
0x18002111d  mov     ebx, eax
0x18002111f  mov     r14d, 10h
0x180021125  test    eax, eax
0x180021127  js      loc_180021324
0x18002112d  cmp     [rsp+140h+var_EC], 4
0x180021132  jnz     loc_18002135D
0x180021138  cmp     [rsp+140h+var_F0], r14d
0x18002113d  jnz     loc_18002135D
0x180021143  mov     esi, dword ptr [rbp+40h+Size]
0x180021149  test    sil, 7
0x18002114d  jnz     loc_180021464
0x180021153  cmp     esi, r14d
0x180021156  jb      loc_180021464
0x18002115c  mov     ebx, esi
0x18002115e  cmp     esi, 48h ; 'H'
0x180021161  ja      loc_180021404
0x180021167  xor     r15d, r15d
0x18002116a  lea     rdi, [rbp+40h+var_A0]
0x18002116e  mov     r8, rbx; Size
0x180021171  lea     r12d, [rsi-8]
0x180021175  mov     rdx, r13; Src
0x180021178  mov     rcx, rdi; void *
0x18002117b  call    memmove
0x180021180  mov     rax, [rdi]
0x180021183  lea     r9, [rdi+8]
0x180021187  mov     r13d, r12d
0x18002118a  shr     r13, 3
0x18002118e  xor     r12d, r12d
0x180021191  cmp     r12d, 6
0x180021195  jnb     loc_18002125E
0x18002119b  mov     r8d, r13d
0x18002119e  test    r8d, r8d
0x1800211a1  jz      loc_180021256
0x1800211a7  mov     ecx, r8d
0x1800211aa  mov     edx, 5
0x1800211af  sub     edx, r12d
0x1800211b2  mov     [rsp+140h+var_F8], 0
0x1800211ba  imul    rdx, r13
0x1800211be  xorps   xmm0, xmm0
0x1800211c1  add     rdx, rcx
0x1800211c4  mov     rcx, [rsp+140h+var_E8]
0x1800211c9  bswap   rdx
0x1800211cc  xor     rdx, rax
0x1800211cf  dec     r8d
0x1800211d2  mov     [rsp+140h+var_C8], rdx
0x1800211d7  mov     [rsp+140h+var_F0], r8d
0x1800211dc  lea     rdx, [rsp+140h+var_C8]
0x1800211e1  lea     eax, ds:0[r8*8]
0x1800211e9  mov     r8d, r14d
0x1800211ec  mov     [rsp+140h+var_E0], rax
0x1800211f1  mov     rax, [rax+r9]
0x1800211f5  xor     r9d, r9d
0x1800211f8  mov     [rbp+40h+var_C0], rax
0x1800211fc  lea     rax, [rsp+140h+var_EC]
0x180021201  mov     [rsp+140h+var_100], rax
0x180021206  lea     rax, [rsp+140h+var_C8]
0x18002120b  mov     [rsp+140h+var_108], r14d
0x180021210  mov     qword ptr [rsp+140h+var_110], rax
0x180021215  lea     rax, [rbp+40h+var_B0]
0x180021219  mov     dword ptr [rsp+140h+var_118], r14d
0x18002121e  mov     [rsp+140h+var_120], rax
0x180021223  movups  [rbp+40h+var_B0], xmm0
0x180021227  call    MSCryptDecrypt
0x18002122c  mov     ebx, eax
0x18002122e  test    eax, eax
0x180021230  js      loc_1800213B5
0x180021236  mov     rdx, [rsp+140h+var_E0]
0x18002123b  lea     r9, [rdi+8]
0x18002123f  mov     rcx, [rbp+40h+var_C0]
0x180021243  mov     rax, [rsp+140h+var_C8]
0x180021248  mov     r8d, [rsp+140h+var_F0]
0x18002124d  mov     [rdx+r9], rcx
0x180021251  jmp     loc_18002119E
0x180021256  inc     r12d
0x180021259  jmp     loc_180021191
0x18002125e  mov     rcx, 0A6A6A6A6A6A6A6A6h
0x180021268  cmp     rax, rcx
0x18002126b  jnz     loc_18002142D
0x180021271  mov     r8, qword ptr [rsp+140h+var_D8]; int
0x180021276  lea     eax, [rsi-8]
0x180021279  mov     rdx, qword ptr [rsp+140h+var_D0]; int
0x18002127e  mov     rcx, qword ptr [rbp+40h+var_B8]; int
0x180021282  mov     [rsp+140h+var_110], 80h; int
0x18002128a  mov     dword ptr [rsp+140h+var_118], eax; Size
0x18002128e  mov     [rsp+140h+var_120], r9; Src
0x180021293  mov     r9d, [rbp+40h+arg_20]; int
0x180021297  call    MSCryptGenerateSymmetricKey
0x18002129c  mov     ebx, eax
0x18002129e  test    eax, eax
0x1800212a0  js      loc_180021437
0x1800212a6  xor     ebx, ebx
0x1800212a8  test    rdi, rdi
0x1800212ab  jz      short loc_1800212C0
0x1800212ad  mov     rax, rsi
0x1800212b0  test    esi, esi
0x1800212b2  jz      short loc_1800212C0
0x1800212b4  mov     byte ptr [rdi], 0
0x1800212b7  inc     rdi
0x1800212ba  sub     rax, 1
0x1800212be  jnz     short loc_1800212B4
0x1800212c0  test    r15, r15
0x1800212c3  jnz     loc_180021457
0x1800212c9  mov     rcx, r14
0x1800212cc  lea     rax, [rbp+40h+var_B0]
0x1800212d0  mov     byte ptr [rax], 0
0x1800212d3  inc     rax
0x1800212d6  sub     rcx, 1
0x1800212da  jnz     short loc_1800212D0
0x1800212dc  lea     rax, [rsp+140h+var_C8]
0x1800212e1  mov     byte ptr [rax], 0
0x1800212e4  inc     rax
0x1800212e7  sub     r14, 1
0x1800212eb  jnz     short loc_1800212E1
0x1800212ed  lea     ecx, [r14+8]
0x1800212f1  lea     rax, [rbp+40h+var_B8]
0x1800212f5  mov     byte ptr [rax], 0
0x1800212f8  inc     rax
0x1800212fb  sub     rcx, 1
0x1800212ff  jnz     short loc_1800212F5
0x180021301  mov     eax, ebx
0x180021303  mov     rcx, [rbp+40h+var_50]
0x180021307  xor     rcx, rsp; StackCookie
0x18002130a  call    __security_check_cookie
0x18002130f  add     rsp, 108h
0x180021316  pop     r15
0x180021318  pop     r14
0x18002131a  pop     r13
0x18002131c  pop     r12
0x18002131e  pop     rdi
0x18002131f  pop     rsi
0x180021320  pop     rbx
0x180021321  pop     rbp
0x180021322  retn
0x180021324  mov     rdx, cs:WPP_GLOBAL_Control
0x18002132b  lea     rax, WPP_GLOBAL_Control
0x180021332  cmp     rdx, rax
0x180021335  jz      short loc_1800212C9
0x180021337  mov     ecx, [rdx+2Ch]
0x18002133a  test    cl, 1
0x18002133d  jz      short loc_1800212C9
0x18002133f  mov     rcx, [rdx+18h]
0x180021343  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002134a  mov     [rsp+140h+var_110], 189h
0x180021352  mov     [rsp+140h+var_118], rax
0x180021357  mov     dword ptr [rsp+140h+var_120], ebx
0x18002135b  jmp     short loc_1800213A4
0x18002135d  mov     ebx, 0C0000008h
0x180021362  mov     rcx, cs:WPP_GLOBAL_Control
0x180021369  lea     rax, WPP_GLOBAL_Control
0x180021370  cmp     rcx, rax
0x180021373  jz      loc_1800212C9
0x180021379  mov     eax, [rcx+2Ch]
0x18002137c  test    al, 1
0x18002137e  jz      loc_1800212C9
0x180021384  mov     rcx, [rcx+18h]
0x180021388  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002138f  mov     [rsp+140h+var_110], 191h
0x180021397  mov     [rsp+140h+var_118], rax
0x18002139c  mov     dword ptr [rsp+140h+var_120], 0C0000008h
0x1800213a4  lea     r9, aStatus; "Status"
0x1800213ab  call    WPP_SF_sDsd
0x1800213b0  jmp     loc_1800212C9
0x1800213b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213bc  lea     rax, WPP_GLOBAL_Control
0x1800213c3  cmp     rcx, rax
0x1800213c6  jz      loc_1800212A8
0x1800213cc  mov     eax, [rcx+2Ch]
0x1800213cf  test    al, 1
0x1800213d1  jz      loc_1800212A8
0x1800213d7  mov     rcx, [rcx+18h]
0x1800213db  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800213e2  mov     [rsp+140h+var_110], 1DAh
0x1800213ea  lea     r9, aStatus; "Status"
0x1800213f1  mov     [rsp+140h+var_118], rax
0x1800213f6  mov     dword ptr [rsp+140h+var_120], ebx
0x1800213fa  call    WPP_SF_sDsd
0x1800213ff  jmp     loc_1800212A8
0x180021404  mov     rcx, rbx
0x180021407  call    MSCryptAlloc
0x18002140c  mov     r15, rax
0x18002140f  test    rax, rax
0x180021412  jnz     loc_1800A684E
0x180021418  mov     ebx, 0C0000017h
0x18002141d  mov     r9d, 1ADh
0x180021423  mov     ecx, 0C0000017h
0x180021428  jmp     loc_1800A6856
0x18002142d  mov     ebx, 0C000A002h
0x180021432  jmp     loc_1800212A8
0x180021437  mov     r9d, 1F4h
0x18002143d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021444  lea     rdx, aStatus; "Status"
0x18002144b  mov     ecx, eax
0x18002144d  call    DebugTraceError
0x180021452  jmp     loc_1800212A8
0x180021457  mov     rcx, r15; P
0x18002145a  call    MSCryptFree
0x18002145f  jmp     loc_1800212C9
0x180021464  mov     ebx, 0C000000Dh
0x180021469  mov     r9d, 199h
0x18002146f  mov     ecx, 0C000000Dh
0x180021474  jmp     loc_1800A6856
0x1800a684e  mov     rdi, rax
0x1800a6851  jmp     loc_18002116E
0x1800a6856  lea     rdx, aStatus; "Status"
0x1800a685d  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a6864  call    DebugTraceError
0x1800a6869  nop
0x1800a686a  jmp     loc_1800212C9
```
