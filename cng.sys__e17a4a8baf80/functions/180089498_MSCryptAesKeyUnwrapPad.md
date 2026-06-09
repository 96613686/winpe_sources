# MSCryptAesKeyUnwrapPad

- ea: `0x180089498`
- end: `0x18008984b`
- name: `MSCryptAesKeyUnwrapPad`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180088308`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x180012970`
- `0x180089498`
- `0x180089854`
- `0x1800a4260`
- `0x1800a45c0`

## string_xrefs

- `0x1800894fb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x180089542`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18008959c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`
- `0x18008979b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\AesKeyWrap.c`

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
  unsigned int v15; // edi
  __int64 v16; // r9
  __int64 v17; // rcx
  int v18; // eax
  unsigned __int64 v19; // rbx
  const void *v20; // rdx
  __int64 v21; // r12
  __int64 i; // r15
  __int64 v23; // rcx
  unsigned __int32 v24; // edx
  unsigned __int8 v25; // r8
  unsigned __int32 v26; // edi
  char v27; // al
  void *v28; // rcx
  unsigned __int64 **v29; // rax
  unsigned __int64 **v30; // rax
  __int64 v31; // rcx
  _BYTE *v32; // rax
  int v34; // [rsp+50h] [rbp-51h] BYREF
  int v35; // [rsp+54h] [rbp-4Dh] BYREF
  int v36; // [rsp+58h] [rbp-49h]
  void *v37; // [rsp+60h] [rbp-41h]
  unsigned __int32 *v38; // [rsp+68h] [rbp-39h]
  int *v39; // [rsp+70h] [rbp-31h]
  unsigned __int64 *v40; // [rsp+78h] [rbp-29h] BYREF
  unsigned __int64 *v41; // [rsp+80h] [rbp-21h] BYREF
  __int64 v42; // [rsp+88h] [rbp-19h]

  v5 = 0;
  v40 = a4;
  v35 = 0;
  v34 = 0;
  v6 = 0;
  v39 = &v34;
  v7 = a3;
  v38 = a3;
  v37 = a2;
  v36 = 0;
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
    v15 = (a5 - 8) >> 3;
    v6 = 8 * v15;
    if ( !v37 )
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
      v16 = 646;
      v17 = 3221225507LL;
LABEL_12:
      DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\AesKeyWrap.c", v16);
      v10 = 8;
      goto LABEL_35;
    }
    v5 = (_QWORD *)MSCryptAlloc(v6, v14);
    if ( !v5 )
    {
      v12 = -1073741801;
      v16 = 654;
      v17 = 3221225495LL;
      goto LABEL_12;
    }
    v36 = *(_DWORD *)(a1 + 12);
    *(_DWORD *)(a1 + 12) = 2;
    if ( v15 == 1 )
    {
      v18 = MSCryptDecrypt(a1, (unsigned __int64)v40, 16, 0, 0, 0, (unsigned __int64)&v41, 0x20u, &v35, 0);
      v12 = v18;
      if ( v18 < 0 )
      {
        v16 = 683;
LABEL_18:
        v17 = (unsigned int)v18;
        goto LABEL_12;
      }
      LODWORD(v19) = (_DWORD)v41;
      v40 = v41;
      *v5 = v42;
    }
    else
    {
      v19 = *v40;
      v20 = v40 + 1;
      v40 = (unsigned __int64 *)*v40;
      memmove(v5, v20, a5 - 8LL);
      v21 = 5;
LABEL_21:
      if ( v21 >= 0 )
      {
        for ( i = v15; ; --i )
        {
          if ( i <= 0 )
          {
            --v21;
            goto LABEL_21;
          }
          v41 = (unsigned __int64 *)(v19 ^ _byteswap_uint64(i + v21 * v15));
          v42 = v5[i - 1];
          v18 = MSCryptDecrypt(a1, (unsigned __int64)&v41, 32, 0, 0, 0, (unsigned __int64)&v41, 0x20u, &v35, 0);
          v12 = v18;
          if ( v18 < 0 )
            break;
          v19 = (unsigned __int64)v41;
          v5[i - 1] = v42;
          v40 = (unsigned __int64 *)v19;
        }
        v16 = 720;
        goto LABEL_18;
      }
      v7 = v38;
    }
    v23 = 1;
    v24 = _byteswap_ulong(HIDWORD(v40));
    v10 = 8;
    v25 = 0;
    v26 = v19 ^ 0xA65959A6 | (v24 >> 3) ^ (v15 - ((v24 & 7) != 0));
    v34 = v26;
    do
    {
      v27 = (v24 & 7) != 0 && v23 >= (unsigned __int64)(v24 & 7) ? *((_BYTE *)&v5[v6 / 8 - 1] + v23) : 0;
      ++v23;
      v25 |= v27;
    }
    while ( v23 < 8 );
    v34 = v25 | v26;
    if ( !*v39 )
    {
      v28 = v37;
      *v7 = v24;
      memmove(v28, v5, v24);
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
  v29 = &v41;
  do
  {
    *(_BYTE *)v29 = 0;
    v29 = (unsigned __int64 **)((char *)v29 + 1);
    --v9;
  }
  while ( v9 );
  v30 = &v40;
  do
  {
    *(_BYTE *)v30 = 0;
    v30 = (unsigned __int64 **)((char *)v30 + 1);
    --v10;
  }
  while ( v10 );
  if ( v5 )
  {
    v31 = v6;
    v32 = v5;
    if ( v6 )
    {
      do
      {
        *v32++ = 0;
        --v31;
      }
      while ( v31 );
    }
    MSCryptFree(v5);
  }
  if ( a1 && v36 )
    *(_DWORD *)(a1 + 12) = v36;
  return v12;
}

```

## disassembly

```asm
0x180089498  push    rbp
0x18008949a  push    rbx
0x18008949b  push    rsi
0x18008949c  push    rdi
0x18008949d  push    r12
0x18008949f  push    r13
0x1800894a1  push    r14
0x1800894a3  push    r15
0x1800894a5  lea     rbp, [rsp-17h]
0x1800894aa  sub     rsp, 0B8h
0x1800894b1  mov     rax, cs:__security_cookie
0x1800894b8  xor     rax, rsp
0x1800894bb  mov     [rbp+4Fh+var_50], rax
0x1800894bf  xor     esi, esi
0x1800894c1  mov     [rbp+4Fh+var_78], r9
0x1800894c5  lea     rax, [rbp+4Fh+var_A0]
0x1800894c9  mov     [rbp+4Fh+var_9C], esi
0x1800894cc  mov     [rbp+4Fh+var_A0], esi
0x1800894cf  xor     r13d, r13d
0x1800894d2  mov     [rbp+4Fh+var_80], rax
0x1800894d6  mov     r12, r8
0x1800894d9  xor     eax, eax
0x1800894db  mov     [rbp+4Fh+var_88], r8
0x1800894df  mov     [rbp+4Fh+var_90], rdx
0x1800894e3  mov     r14, rcx
0x1800894e6  mov     [rbp+4Fh+var_98], eax
0x1800894e9  lea     edi, [rsi+20h]
0x1800894ec  lea     r15d, [rsi+8]
0x1800894f0  test    rcx, rcx
0x1800894f3  jnz     short loc_18008951D
0x1800894f5  mov     r9d, 262h
0x1800894fb  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180089502  mov     ecx, 0C000000Dh
0x180089507  lea     rdx, aStatus; "Status"
0x18008950e  mov     ebx, 0C000000Dh
0x180089513  call    DebugTraceError
0x180089518  jmp     loc_1800897D4
0x18008951d  test    r12, r12
0x180089520  jnz     short loc_18008952A
0x180089522  mov     r9d, 269h
0x180089528  jmp     short loc_1800894FB
0x18008952a  mov     r15d, [rbp+4Fh+arg_20]
0x18008952e  mov     edx, r15d
0x180089531  call    MSCryptAesKeyUnwrapPadValidateInput
0x180089536  mov     ebx, eax
0x180089538  test    eax, eax
0x18008953a  jns     short loc_180089562
0x18008953c  mov     r9d, 270h
0x180089542  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180089549  lea     rdx, aStatus; "Status"
0x180089550  mov     ecx, eax
0x180089552  call    DebugTraceError
0x180089557  mov     r15d, 8
0x18008955d  jmp     loc_1800897D4
0x180089562  lea     edi, [r15-8]
0x180089566  shr     edi, 3
0x180089569  lea     r13d, ds:0[rdi*8]
0x180089571  cmp     [rbp+4Fh+var_90], rsi
0x180089575  jnz     short loc_180089586
0x180089577  mov     [r12], r13d
0x18008957b  mov     r15d, 8
0x180089581  jmp     loc_1800897CD
0x180089586  cmp     [r12], r13d
0x18008958a  jnb     short loc_1800895BA
0x18008958c  mov     ebx, 0C0000023h
0x180089591  mov     r9d, 286h
0x180089597  mov     ecx, 0C0000023h
0x18008959c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800895a3  lea     rdx, aStatus; "Status"
0x1800895aa  call    DebugTraceError
0x1800895af  mov     r15d, 8
0x1800895b5  jmp     loc_1800897CF
0x1800895ba  mov     ecx, r13d
0x1800895bd  call    MSCryptAlloc
0x1800895c2  mov     rsi, rax
0x1800895c5  test    rax, rax
0x1800895c8  jnz     short loc_1800895DC
0x1800895ca  mov     ebx, 0C0000017h
0x1800895cf  mov     r9d, 28Eh
0x1800895d5  mov     ecx, 0C0000017h
0x1800895da  jmp     short loc_18008959C
0x1800895dc  mov     eax, [r14+0Ch]
0x1800895e0  mov     [rbp+4Fh+var_98], eax
0x1800895e3  mov     dword ptr [r14+0Ch], 2
0x1800895eb  cmp     edi, 1
0x1800895ee  jnz     short loc_18008965D
0x1800895f0  mov     rdx, [rbp+4Fh+var_78]
0x1800895f4  lea     rax, [rbp+4Fh+var_9C]
0x1800895f8  mov     [rsp+0F0h+var_A8], 0
0x180089600  lea     r8d, [rdi+0Fh]
0x180089604  mov     [rsp+0F0h+var_B0], rax
0x180089609  xor     r9d, r9d
0x18008960c  mov     [rsp+0F0h+var_B8], 20h ; ' '
0x180089614  lea     rax, [rbp+4Fh+var_70]
0x180089618  mov     [rsp+0F0h+var_C0], rax
0x18008961d  mov     rcx, r14
0x180089620  mov     [rsp+0F0h+var_C8], 0
0x180089628  mov     [rsp+0F0h+var_D0], 0
0x180089631  call    MSCryptDecrypt
0x180089636  mov     ebx, eax
0x180089638  test    eax, eax
0x18008963a  jns     short loc_180089649
0x18008963c  mov     r9d, 2ABh
0x180089642  mov     ecx, eax
0x180089644  jmp     loc_18008959C
0x180089649  mov     rbx, [rbp+4Fh+var_70]
0x18008964d  mov     rax, [rbp+4Fh+var_68]
0x180089651  mov     [rbp+4Fh+var_78], rbx
0x180089655  mov     [rsi], rax
0x180089658  jmp     loc_180089727
0x18008965d  mov     rax, [rbp+4Fh+var_78]
0x180089661  lea     r8, [r15-8]; Size
0x180089665  mov     rcx, rsi; void *
0x180089668  mov     rbx, [rax]
0x18008966b  lea     rdx, [rax+8]; Src
0x18008966f  mov     [rbp+4Fh+var_78], rbx
0x180089673  call    memmove
0x180089678  mov     r12d, 5
0x18008967e  test    r12, r12
0x180089681  js      loc_180089723
0x180089687  mov     r15d, edi
0x18008968a  mov     eax, edi
0x18008968c  test    r15, r15
0x18008968f  jle     short loc_180089710
0x180089691  imul    rax, r12
0x180089695  mov     [rsp+0F0h+var_A8], 0
0x18008969d  lea     rcx, [rbp+4Fh+var_70]
0x1800896a1  add     rax, r15
0x1800896a4  lea     rdx, [rbp+4Fh+var_70]
0x1800896a8  bswap   rax
0x1800896ab  xor     rax, rbx
0x1800896ae  xor     r9d, r9d
0x1800896b1  mov     [rbp+4Fh+var_70], rax
0x1800896b5  mov     rax, [rsi+r15*8-8]
0x1800896ba  mov     [rbp+4Fh+var_68], rax
0x1800896be  lea     rax, [rbp+4Fh+var_9C]
0x1800896c2  mov     [rsp+0F0h+var_B0], rax
0x1800896c7  mov     eax, 20h ; ' '
0x1800896cc  mov     [rsp+0F0h+var_B8], eax
0x1800896d0  mov     r8d, eax
0x1800896d3  mov     [rsp+0F0h+var_C0], rcx
0x1800896d8  mov     rcx, r14
0x1800896db  mov     [rsp+0F0h+var_C8], 0
0x1800896e3  mov     [rsp+0F0h+var_D0], 0
0x1800896ec  call    MSCryptDecrypt
0x1800896f1  mov     ebx, eax
0x1800896f3  test    eax, eax
0x1800896f5  js      short loc_180089718
0x1800896f7  mov     rbx, [rbp+4Fh+var_70]
0x1800896fb  mov     rax, [rbp+4Fh+var_68]
0x1800896ff  mov     [rsi+r15*8-8], rax
0x180089704  dec     r15
0x180089707  mov     [rbp+4Fh+var_78], rbx
0x18008970b  jmp     loc_18008968A
0x180089710  dec     r12
0x180089713  jmp     loc_18008967E
0x180089718  mov     r9d, 2D0h
0x18008971e  jmp     loc_180089642
0x180089723  mov     r12, [rbp+4Fh+var_88]
0x180089727  mov     edx, dword ptr [rbp+4Fh+var_78+4]
0x18008972a  lea     r9d, [r13-8]
0x18008972e  mov     eax, 0
0x180089733  mov     ecx, 1
0x180089738  bswap   edx
0x18008973a  mov     r10d, edx
0x18008973d  and     r10d, 7
0x180089741  lea     r15d, [rcx+7]
0x180089745  setnz   al
0x180089748  xor     ebx, 0A65959A6h
0x18008974e  sub     edi, eax
0x180089750  xor     r8b, r8b
0x180089753  mov     eax, edx
0x180089755  shr     eax, 3
0x180089758  xor     edi, eax
0x18008975a  or      edi, ebx
0x18008975c  test    r10d, r10d
0x18008975f  mov     [rbp+4Fh+var_A0], edi
0x180089762  setnz   r11b
0x180089766  add     r9, rsi
0x180089769  cmp     rcx, r10
0x18008976c  setnb   al
0x18008976f  and     al, r11b
0x180089772  neg     al
0x180089774  and     al, [r9+rcx]
0x180089778  inc     rcx
0x18008977b  or      r8b, al
0x18008977e  cmp     rcx, r15
0x180089781  jl      short loc_180089769
0x180089783  movzx   eax, r8b
0x180089787  or      edi, eax
0x180089789  mov     rax, [rbp+4Fh+var_80]
0x18008978d  mov     [rbp+4Fh+var_A0], edi
0x180089790  cmp     dword ptr [rax], 0
0x180089793  jz      short loc_1800897BA
0x180089795  mov     r9d, 2F0h
0x18008979b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800897a2  lea     rdx, aStatus; "Status"
0x1800897a9  mov     ecx, 0C000090Bh
0x1800897ae  mov     ebx, 0C000090Bh
0x1800897b3  call    DebugTraceError
0x1800897b8  jmp     short loc_1800897CF
0x1800897ba  mov     rcx, [rbp+4Fh+var_90]; void *
0x1800897be  mov     [r12], edx
0x1800897c2  mov     r8d, edx; Size
0x1800897c5  mov     rdx, rsi; Src
0x1800897c8  call    memmove
0x1800897cd  xor     ebx, ebx
0x1800897cf  mov     edi, 20h ; ' '
0x1800897d4  lea     rax, [rbp+4Fh+var_70]
0x1800897d8  mov     byte ptr [rax], 0
0x1800897db  inc     rax
0x1800897de  sub     rdi, 1
0x1800897e2  jnz     short loc_1800897D8
0x1800897e4  lea     rax, [rbp+4Fh+var_78]
0x1800897e8  mov     byte ptr [rax], 0
0x1800897eb  inc     rax
0x1800897ee  sub     r15, 1
0x1800897f2  jnz     short loc_1800897E8
0x1800897f4  test    rsi, rsi
0x1800897f7  jz      short loc_180089818
0x1800897f9  mov     ecx, r13d
0x1800897fc  mov     rax, rsi
0x1800897ff  test    r13d, r13d
0x180089802  jz      short loc_180089810
0x180089804  mov     byte ptr [rax], 0
0x180089807  inc     rax
0x18008980a  sub     rcx, 1
0x18008980e  jnz     short loc_180089804
0x180089810  mov     rcx, rsi; P
0x180089813  call    MSCryptFree
0x180089818  test    r14, r14
0x18008981b  jz      short loc_180089828
0x18008981d  mov     eax, [rbp+4Fh+var_98]
0x180089820  test    eax, eax
0x180089822  jz      short loc_180089828
0x180089824  mov     [r14+0Ch], eax
0x180089828  mov     eax, ebx
0x18008982a  mov     rcx, [rbp+4Fh+var_50]
0x18008982e  xor     rcx, rsp; StackCookie
0x180089831  call    __security_check_cookie
0x180089836  add     rsp, 0B8h
0x18008983d  pop     r15
0x18008983f  pop     r14
0x180089841  pop     r13
0x180089843  pop     r12
0x180089845  pop     rdi
0x180089846  pop     rsi
0x180089847  pop     rbx
0x180089848  pop     rbp
0x180089849  retn
```
