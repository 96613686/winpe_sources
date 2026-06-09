# CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)

- ea: `0x18002bdb4`
- end: `0x18002c175`
- name: `?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z`
- size: `961`
- prototype: `__int64 __fastcall(CWriterGlobalHelper *__hidden this, unsigned int, unsigned __int16 **, unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000674c`
- `0x18002ec50`
- `0x18002f494`
- `0x18002fb58`
- `0x180030634`

## callees

- `0x18000839c`
- `0x180008a08`
- `0x18002bdb4`
- `0x18002c67c`
- `0x18002d32c`
- `0x18002d3ac`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18002c0fe`
- `msvcrt!wcscat_s` at `0x18002c11a`
- `msvcrt!wcscat_s` at `0x18002c0fe`
- `msvcrt!wcscat_s` at `0x18002c11a`
- `msvcrt!wcscpy_s` at `0x18002c0c6`
- `msvcrt!wcscpy_s` at `0x18002c0c6`

## pseudocode

```c
__int64 __fastcall CWriterGlobalHelper::FlagToString(
        __int64 **this,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  int v5; // r12d
  CWriterGlobalHelper *v6; // r15
  __int64 *v7; // rcx
  unsigned __int16 *v8; // r13
  __int64 v11; // rax
  __int64 result; // rax
  unsigned int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rdi
  unsigned int v16; // r14d
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned __int16 *v19; // rcx
  int v20; // edx
  int v21; // r8d
  __int64 v22; // r15
  unsigned __int16 *v23; // r13
  wchar_t *v24; // rcx
  unsigned int v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-BCh] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+4Ch] [rbp-B4h] BYREF
  int v29; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v30; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *Src; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *Destination; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v33; // [rsp+70h] [rbp-90h]
  CWriterGlobalHelper *v34; // [rsp+78h] [rbp-88h]
  _QWORD v35[2]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v36[4]; // [rsp+90h] [rbp-70h] BYREF
  int v37; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+A4h] [rbp-5Ch]
  int v39; // [rsp+ACh] [rbp-54h]
  __int128 v40; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *Source[2]; // [rsp+C0h] [rbp-40h]
  __int128 v42; // [rsp+D0h] [rbp-30h]
  _QWORD v43[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v44; // [rsp+F0h] [rbp-10h]
  int *v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+108h] [rbp+8h]

  v5 = 0;
  v34 = (CWriterGlobalHelper *)this;
  v35[0] = a4;
  v6 = (CWriterGlobalHelper *)this;
  v43[0] = a4;
  v26 = 0;
  v35[1] = &a5;
  v37 = 4;
  v36[2] = 4;
  v7 = this[5];
  v8 = a4;
  v43[1] = &a5;
  v25 = 0;
  v45 = &v28;
  v27 = 0;
  Src = 0;
  v38 = 2;
  v39 = 1;
  v40 = 0;
  v29 = 8;
  *(_OWORD *)Source = 0;
  v30 = 0;
  v42 = 0;
  v28 = 0;
  v36[0] = 0;
  v36[1] = 1;
  v44 = 0;
  v46 = 0;
  v11 = *v7;
  v33 = a4;
  result = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD *, unsigned int *))(v11 + 24))(v7, 0, v35, &v25);
  if ( (int)result < 0 )
  {
    if ( (_DWORD)result != -2145318890 )
      return result;
    goto LABEL_41;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, int *, _QWORD, _DWORD **))(**((_QWORD **)v6 + 5) + 32LL))(
             *((_QWORD *)v6 + 5),
             v25,
             1,
             &v29,
             0,
             &v30);
  if ( (int)result < 0 )
    return result;
  if ( (~(a2 & *v30) & a2) != 0 )
  {
LABEL_41:
    v13 = a2;
    return UnsignedLongToNewString(v13, a3);
  }
  if ( a2 )
  {
    v16 = 1024;
    result = NewString(0x400u, a3);
    if ( (int)result < 0 )
      return result;
    result = CWriterGlobalHelper::GetStartRowIndex(v6, v8, a5, &v26);
    if ( (int)result < 0 )
      return result;
    v17 = v26;
    if ( v26 == -1 )
      return result;
    while ( 1 )
    {
      v18 = *((_QWORD *)v6 + 2);
      v25 = v17;
      result = (*(__int64 (__fastcall **)(__int64, __int64, __int64, int *, _QWORD, __int128 *))(*(_QWORD *)v18 + 32LL))(
                 v18,
                 v17,
                 4,
                 &v37,
                 0,
                 &v40);
      if ( !a2 || (_DWORD)result == -2145318890 || a5 != **((_DWORD **)&v40 + 1) )
        return 0;
      v19 = v8;
      do
      {
        v20 = *(unsigned __int16 *)((char *)v19 + v40 - (_QWORD)v8);
        v21 = *v19 - v20;
        if ( v21 )
          break;
        ++v19;
      }
      while ( v20 );
      if ( v21 )
        return 0;
      if ( (int)result < 0 )
        return result;
      if ( (a2 & *(_DWORD *)v42) != 0 )
        break;
LABEL_38:
      v17 = v25 + 1;
    }
    v22 = -1;
    do
      ++v22;
    while ( Source[0][v22] );
    if ( (int)v22 + v5 + 3 <= v16 )
    {
      if ( !a3 )
      {
LABEL_37:
        v6 = v34;
        a2 &= ~*(_DWORD *)v42;
        goto LABEL_38;
      }
    }
    else
    {
      Destination = 0;
      v16 += v22 + 1027;
      result = NewString(v16, &Destination);
      if ( (int)result < 0 )
        return result;
      v23 = Destination;
      if ( *a3 )
      {
        wcscpy_s(Destination, v16, *a3);
        operator delete(*a3);
      }
      *a3 = v23;
      v8 = v33;
    }
    v24 = *a3;
    if ( *a3 && *v24 )
    {
      wcscat_s(v24, v16, L" | ");
      v5 += 3;
    }
    if ( *a3 )
    {
      wcscat_s(*a3, v16, Source[0]);
      v5 += v22;
    }
    goto LABEL_37;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _DWORD *, _QWORD, _QWORD *, unsigned int *))(**((_QWORD **)v6 + 1) + 56LL))(
             *((_QWORD *)v6 + 1),
             v26,
             3,
             v36,
             0,
             v43,
             &v25);
  if ( (_DWORD)result == -2145318890 )
  {
    v13 = 0;
    return UnsignedLongToNewString(v13, a3);
  }
  if ( (int)result >= 0 )
  {
    v14 = *((_QWORD *)v6 + 1);
    v27 = 2;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *, _QWORD, unsigned __int16 **))(*(_QWORD *)v14 + 32LL))(
               v14,
               v25,
               1,
               &v27,
               0,
               &Src);
    if ( (int)result >= 0 )
    {
      v15 = -1;
      do
        ++v15;
      while ( Src[v15] );
      return StringToNewString(Src, v15, a3);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002bdb4  push    rbp
0x18002bdb6  push    rbx
0x18002bdb7  push    rsi
0x18002bdb8  push    rdi
0x18002bdb9  push    r12
0x18002bdbb  push    r13
0x18002bdbd  push    r14
0x18002bdbf  push    r15
0x18002bdc1  lea     rbp, [rsp-28h]
0x18002bdc6  sub     rsp, 128h
0x18002bdcd  mov     rax, cs:__security_cookie
0x18002bdd4  xor     rax, rsp
0x18002bdd7  mov     [rbp+60h+var_50], rax
0x18002bddb  xor     r12d, r12d
0x18002bdde  mov     [rsp+160h+var_E8], rcx
0x18002bde3  xorps   xmm0, xmm0
0x18002bde6  mov     [rbp+60h+var_E0], r9
0x18002bdea  mov     r15, rcx
0x18002bded  mov     [rbp+60h+var_80], r9
0x18002bdf1  lea     rax, [rbp+60h+arg_20]
0x18002bdf8  mov     [rsp+160h+var_11C], r12d
0x18002bdfd  mov     [rbp+60h+var_D8], rax
0x18002be01  lea     ecx, [r12+4]
0x18002be06  lea     edi, [rcx-3]
0x18002be09  mov     [rbp+60h+var_C0], ecx
0x18002be0c  mov     [rbp+60h+var_C8], ecx
0x18002be0f  lea     rax, [rbp+60h+arg_20]
0x18002be16  mov     rcx, [r15+28h]
0x18002be1a  mov     r13, r9
0x18002be1d  mov     [rbp+60h+var_78], rax
0x18002be21  mov     rbx, r8
0x18002be24  lea     rax, [rsp+160h+var_114]
0x18002be29  mov     [rsp+160h+var_120], r12d
0x18002be2e  mov     [rbp+60h+var_60], rax
0x18002be32  lea     r8, [rbp+60h+var_E0]
0x18002be36  mov     [rsp+160h+var_118], r12d
0x18002be3b  mov     esi, edx
0x18002be3d  mov     [rsp+160h+Src], r12
0x18002be42  xor     edx, edx
0x18002be44  mov     [rbp+60h+var_BC], 2
0x18002be4c  mov     [rbp+60h+var_B4], edi
0x18002be4f  movups  [rbp+60h+var_B0], xmm0
0x18002be53  mov     [rsp+160h+var_110], 8
0x18002be5b  movups  xmmword ptr [rbp+60h+Source], xmm0
0x18002be5f  mov     [rsp+160h+var_108], r12
0x18002be64  movups  [rbp+60h+var_90], xmm0
0x18002be68  mov     [rsp+160h+var_114], r12d
0x18002be6d  mov     [rbp+60h+var_D0], r12d
0x18002be71  mov     [rbp+60h+var_CC], edi
0x18002be74  movdqu  [rbp+60h+var_70], xmm0
0x18002be79  mov     [rbp+60h+var_58], r12
0x18002be7d  mov     rax, [rcx]
0x18002be80  mov     [rsp+160h+var_F0], r9
0x18002be85  lea     r9, [rsp+160h+var_120]
0x18002be8a  mov     rax, [rax+18h]
0x18002be8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be93  test    eax, eax
0x18002be95  js      loc_18002C144
0x18002be9b  mov     rcx, [r15+28h]
0x18002be9f  lea     rdx, [rsp+160h+var_108]
0x18002bea4  mov     [rsp+160h+var_138], rdx
0x18002bea9  lea     r9, [rsp+160h+var_110]
0x18002beae  mov     edx, [rsp+160h+var_120]
0x18002beb2  mov     r8d, edi
0x18002beb5  mov     [rsp+160h+var_140], r12
0x18002beba  mov     rax, [rcx]
0x18002bebd  mov     rax, [rax+20h]
0x18002bec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bec6  test    eax, eax
0x18002bec8  js      loc_18002C155
0x18002bece  mov     rax, [rsp+160h+var_108]
0x18002bed3  mov     ecx, [rax]
0x18002bed5  and     ecx, esi
0x18002bed7  not     ecx
0x18002bed9  test    esi, ecx
0x18002bedb  jnz     loc_18002C14B
0x18002bee1  test    esi, esi
0x18002bee3  jnz     loc_18002BF91
0x18002bee9  mov     rcx, [r15+8]
0x18002beed  lea     rdx, [rsp+160h+var_120]
0x18002bef2  mov     [rsp+160h+var_130], rdx
0x18002bef7  lea     r9, [rbp+60h+var_D0]
0x18002befb  lea     rdx, [rbp+60h+var_80]
0x18002beff  mov     [rsp+160h+var_138], rdx
0x18002bf04  lea     r8d, [r12+3]
0x18002bf09  mov     rax, [rcx]
0x18002bf0c  mov     edx, [rsp+160h+var_11C]
0x18002bf10  mov     [rsp+160h+var_140], r12
0x18002bf15  mov     rax, [rax+38h]
0x18002bf19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf1e  cmp     eax, 80210816h
0x18002bf23  jnz     short loc_18002BF2C
0x18002bf25  xor     ecx, ecx
0x18002bf27  jmp     loc_18002C14D
0x18002bf2c  test    eax, eax
0x18002bf2e  js      loc_18002C155
0x18002bf34  mov     rcx, [r15+8]
0x18002bf38  lea     rdx, [rsp+160h+Src]
0x18002bf3d  mov     [rsp+160h+var_138], rdx
0x18002bf42  lea     r9, [rsp+160h+var_118]
0x18002bf47  mov     edx, [rsp+160h+var_120]
0x18002bf4b  mov     r8d, edi
0x18002bf4e  mov     [rsp+160h+var_118], 2
0x18002bf56  mov     rax, [rcx]
0x18002bf59  mov     [rsp+160h+var_140], r12
0x18002bf5e  mov     rax, [rax+20h]
0x18002bf62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf67  test    eax, eax
0x18002bf69  js      loc_18002C155
0x18002bf6f  mov     rcx, [rsp+160h+Src]; Src
0x18002bf74  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002bf78  inc     rdi
0x18002bf7b  cmp     [rcx+rdi*2], r12w
0x18002bf80  jnz     short loc_18002BF78
0x18002bf82  mov     r8, rbx; unsigned __int16 **
0x18002bf85  mov     edx, edi; unsigned int
0x18002bf87  call    ?StringToNewString@@YAJPEAGKPEAPEAG@Z; StringToNewString(ushort *,ulong,ushort * *)
0x18002bf8c  jmp     loc_18002C155
0x18002bf91  mov     r14d, 400h
0x18002bf97  mov     rdx, rbx; unsigned __int16 **
0x18002bf9a  mov     ecx, r14d; unsigned int
0x18002bf9d  call    ?NewString@@YAJKPEAPEAG@Z; NewString(ulong,ushort * *)
0x18002bfa2  test    eax, eax
0x18002bfa4  js      loc_18002C155
0x18002bfaa  mov     r8d, [rbp+60h+arg_20]; unsigned int
0x18002bfb1  lea     r9, [rsp+160h+var_11C]; unsigned int *
0x18002bfb6  mov     rdx, r13; unsigned __int16 *
0x18002bfb9  mov     rcx, r15; this
0x18002bfbc  call    ?GetStartRowIndex@CWriterGlobalHelper@@AEAAJPEAGKPEAK@Z; CWriterGlobalHelper::GetStartRowIndex(ushort *,ulong,ulong *)
0x18002bfc1  test    eax, eax
0x18002bfc3  js      loc_18002C155
0x18002bfc9  mov     edx, [rsp+160h+var_11C]
0x18002bfcd  cmp     edx, 0FFFFFFFFh
0x18002bfd0  jz      loc_18002C155
0x18002bfd6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002bfda  xor     r10d, r10d
0x18002bfdd  mov     rcx, [r15+10h]
0x18002bfe1  lea     r8, [rbp+60h+var_B0]
0x18002bfe5  mov     [rsp+160h+var_138], r8
0x18002bfea  lea     r9, [rbp+60h+var_C0]
0x18002bfee  mov     [rsp+160h+var_120], edx
0x18002bff2  mov     r8d, 4
0x18002bff8  mov     [rsp+160h+var_140], r10
0x18002bffd  mov     rax, [rcx]
0x18002c000  mov     rax, [rax+20h]
0x18002c004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c009  xor     r10d, r10d
0x18002c00c  test    esi, esi
0x18002c00e  jz      loc_18002C140
0x18002c014  cmp     eax, 80210816h
0x18002c019  jz      loc_18002C140
0x18002c01f  mov     rcx, qword ptr [rbp+60h+var_B0+8]
0x18002c023  mov     edx, [rcx]
0x18002c025  cmp     [rbp+60h+arg_20], edx
0x18002c02b  jnz     loc_18002C140
0x18002c031  mov     r9, qword ptr [rbp+60h+var_B0]
0x18002c035  mov     rcx, r13
0x18002c038  sub     r9, r13
0x18002c03b  movzx   r8d, word ptr [rcx]
0x18002c03f  movzx   edx, word ptr [rcx+r9]
0x18002c044  sub     r8d, edx
0x18002c047  jnz     short loc_18002C051
0x18002c049  add     rcx, 2
0x18002c04d  test    edx, edx
0x18002c04f  jnz     short loc_18002C03B
0x18002c051  test    r8d, r8d
0x18002c054  jnz     loc_18002C140
0x18002c05a  test    eax, eax
0x18002c05c  js      loc_18002C155
0x18002c062  mov     rax, qword ptr [rbp+60h+var_90]
0x18002c066  test    [rax], esi
0x18002c068  jz      loc_18002C135
0x18002c06e  mov     rax, [rbp+60h+Source]
0x18002c072  mov     r15, rdi
0x18002c075  inc     r15
0x18002c078  cmp     [rax+r15*2], r10w
0x18002c07d  jnz     short loc_18002C075
0x18002c07f  lea     eax, [r12+3]
0x18002c084  add     eax, r15d
0x18002c087  cmp     eax, r14d
0x18002c08a  jbe     short loc_18002C0E1
0x18002c08c  add     r14d, 403h
0x18002c093  mov     [rsp+160h+Destination], r10
0x18002c098  add     r14d, r15d
0x18002c09b  lea     rdx, [rsp+160h+Destination]; unsigned __int16 **
0x18002c0a0  mov     ecx, r14d; unsigned int
0x18002c0a3  call    ?NewString@@YAJKPEAPEAG@Z; NewString(ulong,ushort * *)
0x18002c0a8  xor     r10d, r10d
0x18002c0ab  test    eax, eax
0x18002c0ad  js      loc_18002C155
0x18002c0b3  mov     r8, [rbx]; Source
0x18002c0b6  mov     r13, [rsp+160h+Destination]
0x18002c0bb  test    r8, r8
0x18002c0be  jz      short loc_18002C0D7
0x18002c0c0  mov     edx, r14d; SizeInWords
0x18002c0c3  mov     rcx, r13; Destination
0x18002c0c6  call    cs:__imp_wcscpy_s
0x18002c0cc  mov     rcx, [rbx]; Block
0x18002c0cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c0d4  xor     r10d, r10d
0x18002c0d7  mov     [rbx], r13
0x18002c0da  mov     r13, [rsp+160h+var_F0]
0x18002c0df  jmp     short loc_18002C0E6
0x18002c0e1  test    rbx, rbx
0x18002c0e4  jz      short loc_18002C126
0x18002c0e6  mov     rcx, [rbx]; Destination
0x18002c0e9  test    rcx, rcx
0x18002c0ec  jz      short loc_18002C10B
0x18002c0ee  cmp     [rcx], r10w
0x18002c0f2  jz      short loc_18002C10B
0x18002c0f4  mov     edx, r14d; SizeInWords
0x18002c0f7  lea     r8, asc_180041F48; " | "
0x18002c0fe  call    cs:__imp_wcscat_s
0x18002c104  add     r12d, 3
0x18002c108  xor     r10d, r10d
0x18002c10b  mov     rcx, [rbx]; Destination
0x18002c10e  test    rcx, rcx
0x18002c111  jz      short loc_18002C126
0x18002c113  mov     r8, [rbp+60h+Source]; Source
0x18002c117  mov     edx, r14d; SizeInWords
0x18002c11a  call    cs:__imp_wcscat_s
0x18002c120  add     r12d, r15d
0x18002c123  xor     r10d, r10d
0x18002c126  mov     rax, qword ptr [rbp+60h+var_90]
0x18002c12a  mov     r15, [rsp+160h+var_E8]
0x18002c12f  mov     ecx, [rax]
0x18002c131  not     ecx
0x18002c133  and     esi, ecx
0x18002c135  mov     edx, [rsp+160h+var_120]
0x18002c139  inc     edx
0x18002c13b  jmp     loc_18002BFDD
0x18002c140  xor     eax, eax
0x18002c142  jmp     short loc_18002C155
0x18002c144  cmp     eax, 80210816h
0x18002c149  jnz     short loc_18002C155
0x18002c14b  mov     ecx, esi; unsigned int
0x18002c14d  mov     rdx, rbx; unsigned __int16 **
0x18002c150  call    ?UnsignedLongToNewString@@YAJKPEAPEAG@Z; UnsignedLongToNewString(ulong,ushort * *)
0x18002c155  mov     rcx, [rbp+60h+var_50]
0x18002c159  xor     rcx, rsp; StackCookie
0x18002c15c  call    __security_check_cookie
0x18002c161  add     rsp, 128h
0x18002c168  pop     r15
0x18002c16a  pop     r14
0x18002c16c  pop     r13
0x18002c16e  pop     r12
0x18002c170  pop     rdi
0x18002c171  pop     rsi
0x18002c172  pop     rbx
0x18002c173  pop     rbp
0x18002c174  retn
```
