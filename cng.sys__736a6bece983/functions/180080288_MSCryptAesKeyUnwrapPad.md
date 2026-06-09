# MSCryptAesKeyUnwrapPad

- ea: `0x180080288`
- end: `0x18008063b`
- name: `MSCryptAesKeyUnwrapPad`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18007f0f8`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180008850`
- `0x180080288`
- `0x180080644`
- `0x18009f650`
- `0x18009f780`

## string_xrefs

- `0x1800802eb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180080332`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18008038c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18008058b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

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
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // edi
  __int64 v18; // r9
  __int64 v19; // rcx
  int v20; // eax
  unsigned __int64 v21; // rbx
  const void *v22; // rdx
  __int64 v23; // r12
  __int64 i; // r15
  __int64 v25; // rcx
  unsigned __int32 v26; // edx
  unsigned __int8 v27; // r8
  unsigned __int32 v28; // edi
  char v29; // al
  void *v30; // rcx
  unsigned __int64 **v31; // rax
  unsigned __int64 **v32; // rax
  __int64 v33; // rcx
  _BYTE *v34; // rax
  int v36; // [rsp+50h] [rbp-51h] BYREF
  unsigned int v37; // [rsp+54h] [rbp-4Dh] BYREF
  int v38; // [rsp+58h] [rbp-49h]
  void *v39; // [rsp+60h] [rbp-41h]
  unsigned __int32 *v40; // [rsp+68h] [rbp-39h]
  int *v41; // [rsp+70h] [rbp-31h]
  unsigned __int64 *v42; // [rsp+78h] [rbp-29h] BYREF
  unsigned __int64 *v43; // [rsp+80h] [rbp-21h] BYREF
  __int64 v44; // [rsp+88h] [rbp-19h]

  v5 = 0;
  v42 = a4;
  v37 = 0;
  v36 = 0;
  v6 = 0;
  v41 = &v36;
  v7 = a3;
  v40 = a3;
  v39 = a2;
  v38 = 0;
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
    v17 = (a5 - 8) >> 3;
    v6 = 8 * v17;
    if ( !v39 )
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
      v18 = 646;
      v19 = 3221225507LL;
LABEL_12:
      DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", v18);
      v10 = 8;
      goto LABEL_35;
    }
    v5 = (_QWORD *)MSCryptAlloc(v6, v14, v15, v16);
    if ( !v5 )
    {
      v12 = -1073741801;
      v18 = 654;
      v19 = 3221225495LL;
      goto LABEL_12;
    }
    v38 = *(_DWORD *)(a1 + 12);
    *(_DWORD *)(a1 + 12) = 2;
    if ( v17 == 1 )
    {
      v20 = MSCryptDecrypt(a1, (unsigned __int64)v42, 0x10u, 0, 0, 0, (unsigned __int64)&v43, 0x20u, &v37, 0);
      v12 = v20;
      if ( v20 < 0 )
      {
        v18 = 683;
LABEL_18:
        v19 = (unsigned int)v20;
        goto LABEL_12;
      }
      LODWORD(v21) = (_DWORD)v43;
      v42 = v43;
      *v5 = v44;
    }
    else
    {
      v21 = *v42;
      v22 = v42 + 1;
      v42 = (unsigned __int64 *)*v42;
      memmove(v5, v22, a5 - 8LL);
      v23 = 5;
LABEL_21:
      if ( v23 >= 0 )
      {
        for ( i = v17; ; --i )
        {
          if ( i <= 0 )
          {
            --v23;
            goto LABEL_21;
          }
          v43 = (unsigned __int64 *)(v21 ^ _byteswap_uint64(i + v23 * v17));
          v44 = v5[i - 1];
          v20 = MSCryptDecrypt(a1, (unsigned __int64)&v43, 0x20u, 0, 0, 0, (unsigned __int64)&v43, 0x20u, &v37, 0);
          v12 = v20;
          if ( v20 < 0 )
            break;
          v21 = (unsigned __int64)v43;
          v5[i - 1] = v44;
          v42 = (unsigned __int64 *)v21;
        }
        v18 = 720;
        goto LABEL_18;
      }
      v7 = v40;
    }
    v25 = 1;
    v26 = _byteswap_ulong(HIDWORD(v42));
    v10 = 8;
    v27 = 0;
    v28 = v21 ^ 0xA65959A6 | (v26 >> 3) ^ (v17 - ((v26 & 7) != 0));
    v36 = v28;
    do
    {
      v29 = (v26 & 7) != 0 && v25 >= (unsigned __int64)(v26 & 7) ? *((_BYTE *)&v5[v6 / 8 - 1] + v25) : 0;
      ++v25;
      v27 |= v29;
    }
    while ( v25 < 8 );
    v36 = v27 | v28;
    if ( !*v41 )
    {
      v30 = v39;
      *v7 = v26;
      memmove(v30, v5, v26);
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
  v31 = &v43;
  do
  {
    *(_BYTE *)v31 = 0;
    v31 = (unsigned __int64 **)((char *)v31 + 1);
    --v9;
  }
  while ( v9 );
  v32 = &v42;
  do
  {
    *(_BYTE *)v32 = 0;
    v32 = (unsigned __int64 **)((char *)v32 + 1);
    --v10;
  }
  while ( v10 );
  if ( v5 )
  {
    v33 = v6;
    v34 = v5;
    if ( v6 )
    {
      do
      {
        *v34++ = 0;
        --v33;
      }
      while ( v33 );
    }
    MSCryptFree(v5);
  }
  if ( a1 && v38 )
    *(_DWORD *)(a1 + 12) = v38;
  return v12;
}

```

## disassembly

```asm
0x180080288  push    rbp
0x18008028a  push    rbx
0x18008028b  push    rsi
0x18008028c  push    rdi
0x18008028d  push    r12
0x18008028f  push    r13
0x180080291  push    r14
0x180080293  push    r15
0x180080295  lea     rbp, [rsp-17h]
0x18008029a  sub     rsp, 0B8h
0x1800802a1  mov     rax, cs:__security_cookie
0x1800802a8  xor     rax, rsp
0x1800802ab  mov     [rbp+4Fh+var_50], rax
0x1800802af  xor     esi, esi
0x1800802b1  mov     [rbp+4Fh+var_78], r9
0x1800802b5  lea     rax, [rbp+4Fh+var_A0]
0x1800802b9  mov     [rbp+4Fh+var_9C], esi
0x1800802bc  mov     [rbp+4Fh+var_A0], esi
0x1800802bf  xor     r13d, r13d
0x1800802c2  mov     [rbp+4Fh+var_80], rax
0x1800802c6  mov     r12, r8
0x1800802c9  xor     eax, eax
0x1800802cb  mov     [rbp+4Fh+var_88], r8
0x1800802cf  mov     [rbp+4Fh+var_90], rdx
0x1800802d3  mov     r14, rcx
0x1800802d6  mov     [rbp+4Fh+var_98], eax
0x1800802d9  lea     edi, [rsi+20h]
0x1800802dc  lea     r15d, [rsi+8]
0x1800802e0  test    rcx, rcx
0x1800802e3  jnz     short loc_18008030D
0x1800802e5  mov     r9d, 262h
0x1800802eb  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800802f2  mov     ecx, 0C000000Dh
0x1800802f7  lea     rdx, aStatus; "Status"
0x1800802fe  mov     ebx, 0C000000Dh
0x180080303  call    DebugTraceError
0x180080308  jmp     loc_1800805C4
0x18008030d  test    r12, r12
0x180080310  jnz     short loc_18008031A
0x180080312  mov     r9d, 269h
0x180080318  jmp     short loc_1800802EB
0x18008031a  mov     r15d, [rbp+4Fh+arg_20]
0x18008031e  mov     edx, r15d
0x180080321  call    MSCryptAesKeyUnwrapPadValidateInput
0x180080326  mov     ebx, eax
0x180080328  test    eax, eax
0x18008032a  jns     short loc_180080352
0x18008032c  mov     r9d, 270h
0x180080332  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180080339  lea     rdx, aStatus; "Status"
0x180080340  mov     ecx, eax
0x180080342  call    DebugTraceError
0x180080347  mov     r15d, 8
0x18008034d  jmp     loc_1800805C4
0x180080352  lea     edi, [r15-8]
0x180080356  shr     edi, 3
0x180080359  lea     r13d, ds:0[rdi*8]
0x180080361  cmp     [rbp+4Fh+var_90], rsi
0x180080365  jnz     short loc_180080376
0x180080367  mov     [r12], r13d
0x18008036b  mov     r15d, 8
0x180080371  jmp     loc_1800805BD
0x180080376  cmp     [r12], r13d
0x18008037a  jnb     short loc_1800803AA
0x18008037c  mov     ebx, 0C0000023h
0x180080381  mov     r9d, 286h
0x180080387  mov     ecx, 0C0000023h
0x18008038c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180080393  lea     rdx, aStatus; "Status"
0x18008039a  call    DebugTraceError
0x18008039f  mov     r15d, 8
0x1800803a5  jmp     loc_1800805BF
0x1800803aa  mov     ecx, r13d
0x1800803ad  call    MSCryptAlloc
0x1800803b2  mov     rsi, rax
0x1800803b5  test    rax, rax
0x1800803b8  jnz     short loc_1800803CC
0x1800803ba  mov     ebx, 0C0000017h
0x1800803bf  mov     r9d, 28Eh
0x1800803c5  mov     ecx, 0C0000017h
0x1800803ca  jmp     short loc_18008038C
0x1800803cc  mov     eax, [r14+0Ch]
0x1800803d0  mov     [rbp+4Fh+var_98], eax
0x1800803d3  mov     dword ptr [r14+0Ch], 2
0x1800803db  cmp     edi, 1
0x1800803de  jnz     short loc_18008044D
0x1800803e0  mov     rdx, [rbp+4Fh+var_78]
0x1800803e4  lea     rax, [rbp+4Fh+var_9C]
0x1800803e8  mov     [rsp+0F0h+var_A8], 0
0x1800803f0  lea     r8d, [rdi+0Fh]
0x1800803f4  mov     [rsp+0F0h+var_B0], rax
0x1800803f9  xor     r9d, r9d
0x1800803fc  mov     [rsp+0F0h+var_B8], 20h ; ' '
0x180080404  lea     rax, [rbp+4Fh+var_70]
0x180080408  mov     [rsp+0F0h+var_C0], rax
0x18008040d  mov     rcx, r14
0x180080410  mov     [rsp+0F0h+var_C8], 0
0x180080418  mov     [rsp+0F0h+var_D0], 0
0x180080421  call    MSCryptDecrypt
0x180080426  mov     ebx, eax
0x180080428  test    eax, eax
0x18008042a  jns     short loc_180080439
0x18008042c  mov     r9d, 2ABh
0x180080432  mov     ecx, eax
0x180080434  jmp     loc_18008038C
0x180080439  mov     rbx, [rbp+4Fh+var_70]
0x18008043d  mov     rax, [rbp+4Fh+var_68]
0x180080441  mov     [rbp+4Fh+var_78], rbx
0x180080445  mov     [rsi], rax
0x180080448  jmp     loc_180080517
0x18008044d  mov     rax, [rbp+4Fh+var_78]
0x180080451  lea     r8, [r15-8]; Size
0x180080455  mov     rcx, rsi; void *
0x180080458  mov     rbx, [rax]
0x18008045b  lea     rdx, [rax+8]; Src
0x18008045f  mov     [rbp+4Fh+var_78], rbx
0x180080463  call    memmove
0x180080468  mov     r12d, 5
0x18008046e  test    r12, r12
0x180080471  js      loc_180080513
0x180080477  mov     r15d, edi
0x18008047a  mov     eax, edi
0x18008047c  test    r15, r15
0x18008047f  jle     short loc_180080500
0x180080481  imul    rax, r12
0x180080485  mov     [rsp+0F0h+var_A8], 0
0x18008048d  lea     rcx, [rbp+4Fh+var_70]
0x180080491  add     rax, r15
0x180080494  lea     rdx, [rbp+4Fh+var_70]
0x180080498  bswap   rax
0x18008049b  xor     rax, rbx
0x18008049e  xor     r9d, r9d
0x1800804a1  mov     [rbp+4Fh+var_70], rax
0x1800804a5  mov     rax, [rsi+r15*8-8]
0x1800804aa  mov     [rbp+4Fh+var_68], rax
0x1800804ae  lea     rax, [rbp+4Fh+var_9C]
0x1800804b2  mov     [rsp+0F0h+var_B0], rax
0x1800804b7  mov     eax, 20h ; ' '
0x1800804bc  mov     [rsp+0F0h+var_B8], eax
0x1800804c0  mov     r8d, eax
0x1800804c3  mov     [rsp+0F0h+var_C0], rcx
0x1800804c8  mov     rcx, r14
0x1800804cb  mov     [rsp+0F0h+var_C8], 0
0x1800804d3  mov     [rsp+0F0h+var_D0], 0
0x1800804dc  call    MSCryptDecrypt
0x1800804e1  mov     ebx, eax
0x1800804e3  test    eax, eax
0x1800804e5  js      short loc_180080508
0x1800804e7  mov     rbx, [rbp+4Fh+var_70]
0x1800804eb  mov     rax, [rbp+4Fh+var_68]
0x1800804ef  mov     [rsi+r15*8-8], rax
0x1800804f4  dec     r15
0x1800804f7  mov     [rbp+4Fh+var_78], rbx
0x1800804fb  jmp     loc_18008047A
0x180080500  dec     r12
0x180080503  jmp     loc_18008046E
0x180080508  mov     r9d, 2D0h
0x18008050e  jmp     loc_180080432
0x180080513  mov     r12, [rbp+4Fh+var_88]
0x180080517  mov     edx, dword ptr [rbp+4Fh+var_78+4]
0x18008051a  lea     r9d, [r13-8]
0x18008051e  mov     eax, 0
0x180080523  mov     ecx, 1
0x180080528  bswap   edx
0x18008052a  mov     r10d, edx
0x18008052d  and     r10d, 7
0x180080531  lea     r15d, [rcx+7]
0x180080535  setnz   al
0x180080538  xor     ebx, 0A65959A6h
0x18008053e  sub     edi, eax
0x180080540  xor     r8b, r8b
0x180080543  mov     eax, edx
0x180080545  shr     eax, 3
0x180080548  xor     edi, eax
0x18008054a  or      edi, ebx
0x18008054c  test    r10d, r10d
0x18008054f  mov     [rbp+4Fh+var_A0], edi
0x180080552  setnz   r11b
0x180080556  add     r9, rsi
0x180080559  cmp     rcx, r10
0x18008055c  setnb   al
0x18008055f  and     al, r11b
0x180080562  neg     al
0x180080564  and     al, [r9+rcx]
0x180080568  inc     rcx
0x18008056b  or      r8b, al
0x18008056e  cmp     rcx, r15
0x180080571  jl      short loc_180080559
0x180080573  movzx   eax, r8b
0x180080577  or      edi, eax
0x180080579  mov     rax, [rbp+4Fh+var_80]
0x18008057d  mov     [rbp+4Fh+var_A0], edi
0x180080580  cmp     dword ptr [rax], 0
0x180080583  jz      short loc_1800805AA
0x180080585  mov     r9d, 2F0h
0x18008058b  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180080592  lea     rdx, aStatus; "Status"
0x180080599  mov     ecx, 0C000090Bh
0x18008059e  mov     ebx, 0C000090Bh
0x1800805a3  call    DebugTraceError
0x1800805a8  jmp     short loc_1800805BF
0x1800805aa  mov     rcx, [rbp+4Fh+var_90]; void *
0x1800805ae  mov     [r12], edx
0x1800805b2  mov     r8d, edx; Size
0x1800805b5  mov     rdx, rsi; Src
0x1800805b8  call    memmove
0x1800805bd  xor     ebx, ebx
0x1800805bf  mov     edi, 20h ; ' '
0x1800805c4  lea     rax, [rbp+4Fh+var_70]
0x1800805c8  mov     byte ptr [rax], 0
0x1800805cb  inc     rax
0x1800805ce  sub     rdi, 1
0x1800805d2  jnz     short loc_1800805C8
0x1800805d4  lea     rax, [rbp+4Fh+var_78]
0x1800805d8  mov     byte ptr [rax], 0
0x1800805db  inc     rax
0x1800805de  sub     r15, 1
0x1800805e2  jnz     short loc_1800805D8
0x1800805e4  test    rsi, rsi
0x1800805e7  jz      short loc_180080608
0x1800805e9  mov     ecx, r13d
0x1800805ec  mov     rax, rsi
0x1800805ef  test    r13d, r13d
0x1800805f2  jz      short loc_180080600
0x1800805f4  mov     byte ptr [rax], 0
0x1800805f7  inc     rax
0x1800805fa  sub     rcx, 1
0x1800805fe  jnz     short loc_1800805F4
0x180080600  mov     rcx, rsi; P
0x180080603  call    MSCryptFree
0x180080608  test    r14, r14
0x18008060b  jz      short loc_180080618
0x18008060d  mov     eax, [rbp+4Fh+var_98]
0x180080610  test    eax, eax
0x180080612  jz      short loc_180080618
0x180080614  mov     [r14+0Ch], eax
0x180080618  mov     eax, ebx
0x18008061a  mov     rcx, [rbp+4Fh+var_50]
0x18008061e  xor     rcx, rsp; StackCookie
0x180080621  call    __security_check_cookie
0x180080626  add     rsp, 0B8h
0x18008062d  pop     r15
0x18008062f  pop     r14
0x180080631  pop     r13
0x180080633  pop     r12
0x180080635  pop     rdi
0x180080636  pop     rsi
0x180080637  pop     rbx
0x180080638  pop     rbp
0x180080639  retn
```
