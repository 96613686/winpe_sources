# EnumerateDirectoryFromCache

- ea: `0x1400020a0`
- end: `0x1400028bf`
- name: `EnumerateDirectoryFromCache`
- size: `2079`
- prototype: `__int64 __fastcall(unsigned int *Context, __m128i *, char, int, unsigned __int64 *, __int64, unsigned int *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002b80`

## callees

- `0x1400020a0`
- `0x140035520`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400022a7`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400025c0`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400022a7`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400025c0`
- `ntoskrnl!bsearch_s` at `0x140002507`
- `ntoskrnl!bsearch_s` at `0x1400026dc`
- `ntoskrnl!bsearch_s` at `0x140002507`
- `ntoskrnl!bsearch_s` at `0x1400026dc`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400021d3`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400021d3`

## pseudocode

```c
__int64 __fastcall EnumerateDirectoryFromCache(
        unsigned int *Context,
        __m128i *a2,
        char a3,
        int a4,
        unsigned __int64 *a5,
        __int64 a6,
        unsigned int *a7,
        char a8)
{
  struct _UNICODE_STRING v8; // xmm0
  char v9; // r9
  char v11; // di
  unsigned __int16 v12; // dx
  unsigned int v13; // r8d
  __int64 v14; // rcx
  char v15; // al
  __int64 v16; // rsi
  unsigned int v17; // r14d
  unsigned int v18; // r13d
  unsigned __int64 v19; // r8
  unsigned int v20; // edx
  unsigned int v22; // r9d
  int v23; // r12d
  unsigned int v24; // ebx
  CCHAR MostSignificantBit; // al
  __int64 v26; // rdx
  unsigned int v27; // ecx
  __int64 v28; // rdx
  __int64 v29; // rbx
  USHORT v30; // cx
  __int16 v31; // dx
  __int16 v32; // dx
  unsigned int v33; // edi
  __int64 v34; // rax
  void *v35; // rcx
  void *v36; // rcx
  PWSTR Buffer; // rdx
  size_t Length; // r8
  __int64 v40; // rax
  void *v41; // rax
  int v42; // r8d
  unsigned int v43; // ebx
  _DWORD *v44; // r14
  unsigned int *v45; // r12
  unsigned int v46; // edi
  __int64 v47; // rax
  void *v48; // rax
  unsigned __int16 i; // r8
  __int64 v50; // rax
  __int64 v51; // [rsp+38h] [rbp-41h]
  char v52; // [rsp+40h] [rbp-39h]
  _DWORD *v53; // [rsp+48h] [rbp-31h]
  struct _UNICODE_STRING Name; // [rsp+50h] [rbp-29h] BYREF
  void *Src[2]; // [rsp+60h] [rbp-19h] BYREF
  struct _UNICODE_STRING Expression; // [rsp+70h] [rbp-9h] BYREF
  unsigned int v57; // [rsp+C8h] [rbp+4Fh]
  unsigned __int64 v58; // [rsp+C8h] [rbp+4Fh]

  v8 = (struct _UNICODE_STRING)*a2;
  v9 = a3;
  v11 = 1;
  v12 = _mm_cvtsi128_si32(*a2);
  Expression = v8;
  if ( v12 && *Expression.Buffer == 92 )
  {
    for ( i = 1; i < (unsigned __int16)(v12 >> 1); ++i )
    {
      if ( Expression.Buffer[i] != 92 )
        break;
    }
    Expression.MaximumLength -= 2 * i;
    Expression.Length = v12 - 2 * i;
    if ( !Expression.Length )
      return 3221225485LL;
    v9 = a3;
    Expression.Buffer += i;
  }
  LOBYTE(v13) = 0;
  v14 = *((_QWORD *)Context + 17);
  v15 = 0;
  v16 = 0;
  v17 = Context[31];
  v52 = 0;
  v18 = *a7;
  v51 = *((_QWORD *)Context + 17);
  v57 = v17;
  if ( a5 && *((_DWORD *)a5 + 1) )
  {
    v19 = *a5;
    if ( HIDWORD(*a5) != Context[10] )
    {
      __int2c();
      return 3221225485LL;
    }
    if ( (v19 & 0x80000000) == 0LL )
      __int2c();
    v15 = 1;
    v16 = *a5 & 0x3FFFFFFF;
    v13 = ((unsigned int)v19 >> 30) & 1;
    v52 = v13;
    if ( v13 )
    {
      v14 = *((_QWORD *)Context + 18);
      v17 = Context[32];
      v51 = v14;
      v57 = v17;
    }
  }
  if ( (unsigned int)v16 >= v17 )
    return 2147483654LL;
  if ( !v15 && !v9 )
  {
    v41 = bsearch_s(&Expression, *((const void **)Context + 17), Context[31], 4u, DirCacheLongNameKeyCompare, Context);
    if ( v41 )
    {
      v43 = ((unsigned int)v41 - Context[34]) >> 2;
      v11 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_ZqD(WPP_GLOBAL_Control->AttachedDevice, 12, v42, (unsigned int)&Expression, (char)Context, v43);
      }
      v44 = Context + 36;
      v45 = Context + 32;
    }
    else
    {
      v45 = Context + 32;
      v44 = Context + 36;
      v48 = bsearch_s(
              &Expression,
              *((const void **)Context + 18),
              Context[32],
              4u,
              DirCacheShortNameKeyCompare,
              Context);
      if ( !v48 )
        return 3221225487LL;
      v43 = (unsigned int)((_DWORD)v48 - *v44) >> 2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_ZqD(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          (unsigned int)((_DWORD)v48 - *v44) >> 2,
          (unsigned int)&Expression,
          (char)Context,
          (unsigned int)((_DWORD)v48 - *v44) >> 2);
      }
    }
    v46 = v43 | ((*(_DWORD *)&v11 | 0xFFFFFFFE) << 30);
    v16 = v46 & 0x3FFFFFFF;
    v13 = (v46 >> 30) & 1;
    v52 = v13;
    if ( v13 )
    {
      v14 = *(_QWORD *)v44;
      v51 = *(_QWORD *)v44;
      v57 = *v45;
    }
    else
    {
      v14 = v51;
    }
  }
  v20 = v57;
  v22 = 0;
  v23 = 0;
  v53 = 0;
  if ( (unsigned int)v16 >= v57 )
    goto LABEL_36;
  while ( 1 )
  {
    v24 = *(_DWORD *)(v14 + 4 * v16);
    Name = 0;
    *(_OWORD *)Src = 0;
    MostSignificantBit = RtlFindMostSignificantBit(v24);
    if ( MostSignificantBit <= 4 )
    {
      v26 = 0;
    }
    else
    {
      v26 = (unsigned int)(MostSignificantBit - 3) >> 1;
      if ( (unsigned int)v26 >= 8 )
        goto LABEL_85;
    }
    _mm_lfence();
    if ( (_DWORD)v26 )
      v27 = v24 - (32 << (2 * v26 - 2));
    else
      v27 = v24;
    v28 = *(_QWORD *)&Context[2 * v26 + 38];
    if ( !v28 || v24 >= Context[54] )
    {
LABEL_85:
      __int2c();
      v29 = 0;
      goto LABEL_20;
    }
    v29 = v28 + (v27 << 7);
LABEL_20:
    if ( v23 == 1 && (a8 || !a3) )
      break;
    v30 = 2 * (*(_WORD *)(v29 + 86) >> 4);
    Name.MaximumLength = v30;
    Name.Length = v30;
    Name.Buffer = (PWSTR)(v29 + 2 * ((*(_WORD *)(v29 + 86) & 0xF) + 44LL));
    v31 = *(_WORD *)(v29 + 86);
    Src[1] = (void *)(v29 + 88);
    v32 = 2 * (v31 & 0xF);
    WORD1(Src[0]) = v32;
    LOWORD(Src[0]) = v32;
    if ( (*(_BYTE *)(v29 + 84) & 1) != 0 )
      goto LABEL_33;
    if ( v30 )
    {
      if ( FsRtlIsNameInExpression(&Expression, &Name, 1u, 0) )
        goto LABEL_24;
      v32 = (__int16)Src[0];
    }
    if ( !v32 || !FsRtlIsNameInExpression(&Expression, (PUNICODE_STRING)Src, 1u, 0) )
      goto LABEL_33;
LABEL_24:
    if ( a4 == 37 )
    {
      v33 = (Name.Length + 111) & 0xFFFFFFF8;
      if ( v18 < v33 )
        break;
      *(_DWORD *)(a6 + 4) = 0;
      *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
      *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
      *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
      *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
      *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
      *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
      *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
      v34 = 80;
      if ( (*(_DWORD *)(v29 + 72) & 0x400) == 0 )
        v34 = 76;
      v35 = (void *)(a6 + 104);
      *(_DWORD *)(a6 + 64) = *(_DWORD *)(v34 + v29);
      *(_QWORD *)(a6 + 96) = *(_QWORD *)(v29 + 48);
    }
    else
    {
      if ( a4 != 3 )
      {
        switch ( a4 )
        {
          case 1:
            v33 = (Name.Length + 71) & 0xFFFFFFF8;
            if ( v18 < v33 )
              goto LABEL_40;
            *(_DWORD *)(a6 + 4) = 0;
            v36 = (void *)(a6 + 64);
            *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
            *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
            *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
            *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
            *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
            *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
            *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
            *(_DWORD *)(a6 + 60) = Name.Length;
            Length = Name.Length;
            Buffer = Name.Buffer;
            goto LABEL_31;
          case 2:
            v33 = (Name.Length + 75) & 0xFFFFFFF8;
            if ( v18 < v33 )
              goto LABEL_40;
            *(_DWORD *)(a6 + 4) = 0;
            *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
            *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
            *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
            *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
            *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
            *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
            *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
            v47 = 80;
            if ( (*(_DWORD *)(v29 + 72) & 0x400) == 0 )
              v47 = 76;
            v36 = (void *)(a6 + 68);
            *(_DWORD *)(a6 + 64) = *(_DWORD *)(v47 + v29);
            *(_DWORD *)(a6 + 60) = Name.Length;
            Length = Name.Length;
            Buffer = Name.Buffer;
            goto LABEL_31;
          case 12:
            v33 = (Name.Length + 19) & 0xFFFFFFF8;
            if ( v18 < v33 )
              goto LABEL_40;
            *(_DWORD *)(a6 + 4) = 0;
            v36 = (void *)(a6 + 12);
            *(_DWORD *)(a6 + 8) = Name.Length;
            Length = Name.Length;
            Buffer = Name.Buffer;
            goto LABEL_31;
          case 38:
            v33 = (Name.Length + 87) & 0xFFFFFFF8;
            if ( v18 < v33 )
              goto LABEL_40;
            *(_DWORD *)(a6 + 4) = 0;
            *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
            *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
            *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
            *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
            *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
            *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
            *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
            v50 = 80;
            if ( (*(_DWORD *)(v29 + 72) & 0x400) == 0 )
              v50 = 76;
            *(_DWORD *)(a6 + 64) = *(_DWORD *)(v50 + v29);
            goto LABEL_104;
          case 60:
            v33 = (Name.Length + 95) & 0xFFFFFFF8;
            if ( v18 < v33 )
              goto LABEL_40;
            *(_DWORD *)(a6 + 4) = 0;
            v36 = (void *)(a6 + 88);
            *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
            *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
            *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
            *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
            *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
            *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
            *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
            *(_DWORD *)(a6 + 64) = *(_DWORD *)(v29 + 76);
            *(_DWORD *)(a6 + 68) = *(_DWORD *)(v29 + 80);
            *(_OWORD *)(a6 + 72) = *(_OWORD *)(v29 + 56);
            *(_DWORD *)(a6 + 60) = Name.Length;
            Length = Name.Length;
            Buffer = Name.Buffer;
            goto LABEL_31;
          case 63:
            v33 = (Name.Length + 121) & 0xFFFFFFF8;
            if ( v18 < v33 )
              goto LABEL_40;
            *(_DWORD *)(a6 + 4) = 0;
            *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
            *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
            *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
            *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
            *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
            *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
            *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
            *(_DWORD *)(a6 + 64) = *(_DWORD *)(v29 + 76);
            *(_DWORD *)(a6 + 68) = *(_DWORD *)(v29 + 80);
            *(_OWORD *)(a6 + 72) = *(_OWORD *)(v29 + 56);
            *(_DWORD *)(a6 + 60) = Name.Length;
            *(_BYTE *)(a6 + 88) = Src[0];
            memmove((void *)(a6 + 114), Name.Buffer, Name.Length);
            v36 = (void *)(a6 + 90);
            goto LABEL_30;
          case 78:
            v33 = (Name.Length + 87) & 0xFFFFFFF8;
            if ( v18 < v33 )
              goto LABEL_40;
            *(_DWORD *)(a6 + 4) = 0;
            *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
            *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
            *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
            *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
            *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
            *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
            *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
            *(_DWORD *)(a6 + 64) = *(_DWORD *)(v29 + 76);
            *(_DWORD *)(a6 + 68) = *(_DWORD *)(v29 + 80);
LABEL_104:
            v36 = (void *)(a6 + 80);
            *(_QWORD *)(a6 + 72) = *(_QWORD *)(v29 + 48);
            goto LABEL_105;
          case 79:
            v33 = (Name.Length + 113) & 0xFFFFFFF8;
            if ( v18 < v33 )
              goto LABEL_40;
            *(_DWORD *)(a6 + 4) = 0;
            *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
            *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
            *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
            *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
            *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
            *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
            *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
            *(_DWORD *)(a6 + 64) = *(_DWORD *)(v29 + 76);
            *(_DWORD *)(a6 + 68) = *(_DWORD *)(v29 + 80);
            *(_QWORD *)(a6 + 72) = *(_QWORD *)(v29 + 48);
            *(_DWORD *)(a6 + 60) = Name.Length;
            *(_BYTE *)(a6 + 80) = Src[0];
            memmove((void *)(a6 + 106), Name.Buffer, Name.Length);
            v36 = (void *)(a6 + 82);
            goto LABEL_30;
          case 80:
            v33 = (Name.Length + 103) & 0xFFFFFFF8;
            if ( v18 < v33 )
              goto LABEL_40;
            *(_DWORD *)(a6 + 4) = 0;
            v36 = (void *)(a6 + 96);
            *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
            *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
            *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
            *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
            *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
            *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
            *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
            *(_DWORD *)(a6 + 64) = *(_DWORD *)(v29 + 76);
            *(_DWORD *)(a6 + 68) = *(_DWORD *)(v29 + 80);
            *(_QWORD *)(a6 + 72) = *(_QWORD *)(v29 + 48);
            *(_OWORD *)(a6 + 80) = *(_OWORD *)(v29 + 56);
LABEL_105:
            *(_DWORD *)(a6 + 60) = Name.Length;
            break;
          case 81:
            v33 = (Name.Length + 129) & 0xFFFFFFF8;
            if ( v18 < v33 )
              goto LABEL_40;
            *(_DWORD *)(a6 + 4) = 0;
            *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
            *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
            *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
            *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
            *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
            *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
            *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
            *(_DWORD *)(a6 + 64) = *(_DWORD *)(v29 + 76);
            *(_DWORD *)(a6 + 68) = *(_DWORD *)(v29 + 80);
            *(_QWORD *)(a6 + 72) = *(_QWORD *)(v29 + 48);
            *(_OWORD *)(a6 + 80) = *(_OWORD *)(v29 + 56);
            *(_DWORD *)(a6 + 60) = Name.Length;
            *(_BYTE *)(a6 + 96) = Src[0];
            memmove((void *)(a6 + 98), Src[1], LOWORD(Src[0]));
            v36 = (void *)(a6 + 122);
            break;
          default:
            goto LABEL_40;
        }
        Length = Name.Length;
        Buffer = Name.Buffer;
        goto LABEL_31;
      }
      v33 = (Name.Length + 101) & 0xFFFFFFF8;
      if ( v18 < v33 )
        break;
      *(_DWORD *)(a6 + 4) = 0;
      *(_QWORD *)(a6 + 8) = *(_QWORD *)v29;
      *(_QWORD *)(a6 + 16) = *(_QWORD *)(v29 + 8);
      *(_QWORD *)(a6 + 24) = *(_QWORD *)(v29 + 16);
      *(_QWORD *)(a6 + 32) = *(_QWORD *)(v29 + 24);
      *(_QWORD *)(a6 + 40) = *(_QWORD *)(v29 + 32);
      *(_QWORD *)(a6 + 48) = *(_QWORD *)(v29 + 40);
      *(_DWORD *)(a6 + 56) = *(_DWORD *)(v29 + 72);
      v40 = 80;
      if ( (*(_DWORD *)(v29 + 72) & 0x400) == 0 )
        v40 = 76;
      v35 = (void *)(a6 + 94);
      *(_DWORD *)(a6 + 64) = *(_DWORD *)(v40 + v29);
    }
    *(_DWORD *)(a6 + 60) = Name.Length;
    *(_BYTE *)(a6 + 68) = Src[0];
    memmove(v35, Name.Buffer, Name.Length);
    v36 = (void *)(a6 + 70);
LABEL_30:
    Buffer = (PWSTR)Src[1];
    Length = LOWORD(Src[0]);
LABEL_31:
    memmove(v36, Buffer, Length);
    *(_DWORD *)a6 = v33;
    if ( !v33 )
      break;
    v18 -= v33;
    ++v23;
    v53 = (_DWORD *)a6;
    a6 += v33;
LABEL_33:
    v20 = v57;
    v16 = (unsigned int)(v16 + 1);
    v14 = v51;
    if ( (unsigned int)v16 >= v57 )
      goto LABEL_34;
  }
LABEL_40:
  v20 = v57;
LABEL_34:
  LOBYTE(v13) = v52;
  v22 = 0;
  if ( v53 )
    *v53 = 0;
LABEL_36:
  HIDWORD(v58) = Context[10];
  LODWORD(v58) = v16 & 0x3FFFFFFF | ((v13 | 0xFFFFFFFE) << 30);
  *a5 = v58;
  *a7 = v18;
  if ( !v23 && (unsigned int)v16 >= v20 )
    return (unsigned int)-2147483642;
  return v22;
}

```

## disassembly

```asm
0x1400020a0  mov     [rsp-8+arg_18], r9d
0x1400020a5  mov     [rsp-8+arg_10], r8b
0x1400020aa  push    rbp
0x1400020ab  push    rdi
0x1400020ac  push    r15
0x1400020ae  lea     rbp, [rsp-27h]
0x1400020b3  sub     rsp, 0A0h
0x1400020ba  movups  xmm0, xmmword ptr [rdx]
0x1400020bd  movzx   r9d, r8b
0x1400020c1  mov     r15, rcx
0x1400020c4  mov     edi, 1
0x1400020c9  movd    edx, xmm0
0x1400020cd  movups  xmmword ptr [rbp+37h+Expression.Length], xmm0
0x1400020d1  test    dx, dx
0x1400020d4  jz      short loc_1400020E4
0x1400020d6  mov     rcx, [rbp+37h+Expression.Buffer]
0x1400020da  cmp     word ptr [rcx], 5Ch ; '\'
0x1400020de  jz      loc_1400027D4
0x1400020e4  mov     rdx, [rbp+37h+arg_20]
0x1400020e8  xor     r8d, r8d
0x1400020eb  mov     rcx, [r15+88h]
0x1400020f2  xor     al, al
0x1400020f4  mov     [rsp+0B0h+var_18], rsi
0x1400020fc  xor     esi, esi
0x1400020fe  mov     [rsp+0B0h+var_28], r13
0x140002106  mov     r13, [rbp+37h+arg_30]
0x14000210a  mov     [rsp+0B0h+var_30], r14
0x140002112  mov     r14d, [r15+7Ch]
0x140002116  mov     [rbp+37h+var_70], r8
0x14000211a  mov     r13d, [r13+0]
0x14000211e  mov     [rbp+37h+var_78], rcx
0x140002122  mov     dword ptr [rbp+37h+arg_8], r14d
0x140002126  test    rdx, rdx
0x140002129  jz      short loc_14000216B
0x14000212b  cmp     [rdx+4], esi
0x14000212e  jz      short loc_14000216B
0x140002130  mov     r8, [rdx]
0x140002133  mov     rax, r8
0x140002136  shr     rax, 20h
0x14000213a  cmp     eax, [r15+28h]
0x14000213e  jnz     loc_140002811
0x140002144  test    r8d, r8d
0x140002147  jns     loc_1400027EF
0x14000214d  mov     esi, r8d
0x140002150  movzx   eax, dil
0x140002154  shr     r8d, 1Eh
0x140002158  and     esi, 3FFFFFFFh
0x14000215e  and     r8d, edi
0x140002161  mov     [rbp+37h+var_70], r8
0x140002165  jnz     loc_1400027F6
0x14000216b  cmp     esi, r14d
0x14000216e  jnb     loc_14000259B
0x140002174  mov     [rsp+0B0h+arg_0], rbx
0x14000217c  mov     [rsp+0B0h+var_20], r12
0x140002184  test    al, al
0x140002186  jz      loc_1400024D8
0x14000218c  mov     edx, dword ptr [rbp+37h+arg_8]
0x14000218f  xor     eax, eax
0x140002191  mov     r14, [rbp+37h+arg_28]
0x140002195  xor     r9d, r9d
0x140002198  xor     r12d, r12d
0x14000219b  mov     [rbp+37h+var_68], rax
0x14000219f  mov     [rbp+37h+var_80], r9d
0x1400021a3  cmp     esi, edx
0x1400021a5  jnb     loc_1400023B8
0x1400021ab  lea     rdi, cs:140000000h
0x1400021b2  nop     dword ptr [rax+00h]
0x1400021b6  nop     word ptr [rax+rax+00000000h]
0x1400021c0  mov     ebx, [rcx+rsi*4]
0x1400021c3  xorps   xmm0, xmm0
0x1400021c6  xorps   xmm1, xmm1
0x1400021c9  mov     ecx, ebx; Set
0x1400021cb  movups  xmmword ptr [rbp+37h+Name.Length], xmm0
0x1400021cf  movups  xmmword ptr [rbp+37h+Src], xmm1
0x1400021d3  call    cs:__imp_RtlFindMostSignificantBit
0x1400021da  nop     dword ptr [rax+rax+00h]
0x1400021df  cmp     al, 4
0x1400021e1  jle     loc_140002440
0x1400021e7  movsx   edx, al
0x1400021ea  sub     edx, 3
0x1400021ed  shr     edx, 1
0x1400021ef  cmp     edx, 8
0x1400021f2  jnb     loc_14000285B
0x1400021f8  lfence
0x1400021fb  test    edx, edx
0x1400021fd  jz      loc_140002447
0x140002203  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x14000220a  mov     eax, 20h ; ' '
0x14000220f  shl     eax, cl
0x140002211  mov     ecx, ebx
0x140002213  sub     ecx, eax
0x140002215  mov     rdx, [r15+rdx*8+98h]
0x14000221d  test    rdx, rdx
0x140002220  jz      loc_140002769
0x140002226  cmp     ebx, [r15+0D8h]
0x14000222d  jnb     loc_140002772
0x140002233  shl     ecx, 7
0x140002236  mov     ebx, ecx
0x140002238  add     rbx, rdx
0x14000223b  cmp     r12d, 1
0x14000223f  jz      loc_1400024BF
0x140002245  movzx   ecx, word ptr [rbx+56h]
0x140002249  shr     cx, 4
0x14000224d  add     cx, cx
0x140002250  mov     [rbp+37h+Name.MaximumLength], cx
0x140002254  mov     [rbp+37h+Name.Length], cx
0x140002258  movzx   eax, word ptr [rbx+56h]
0x14000225c  and     eax, 0Fh
0x14000225f  add     rax, 2Ch ; ','
0x140002263  lea     rax, [rbx+rax*2]
0x140002267  mov     [rbp+37h+Name.Buffer], rax
0x14000226b  lea     rax, [rbx+58h]
0x14000226f  movzx   edx, word ptr [rbx+56h]
0x140002273  and     dx, 0Fh
0x140002277  mov     [rbp+37h+Src+8], rax
0x14000227b  add     dx, dx
0x14000227e  mov     word ptr [rbp+37h+Src+2], dx
0x140002282  mov     word ptr [rbp+37h+Src], dx
0x140002286  test    byte ptr [rbx+54h], 1
0x14000228a  jnz     loc_140002390
0x140002290  test    cx, cx
0x140002293  jz      loc_1400025A9
0x140002299  xor     r9d, r9d; UpcaseTable
0x14000229c  lea     rdx, [rbp+37h+Name]; Name
0x1400022a0  mov     r8b, 1; IgnoreCase
0x1400022a3  lea     rcx, [rbp+37h+Expression]; Expression
0x1400022a7  call    cs:__imp_FsRtlIsNameInExpression
0x1400022ae  nop     dword ptr [rax+rax+00h]
0x1400022b3  test    al, al
0x1400022b5  jz      loc_1400025A5
0x1400022bb  mov     eax, [rbp+37h+arg_18]
0x1400022be  cmp     eax, 25h ; '%'
0x1400022c1  jnz     loc_140002428
0x1400022c7  movzx   edi, [rbp+37h+Name.Length]
0x1400022cb  add     edi, 6Fh ; 'o'
0x1400022ce  and     edi, 0FFFFFFF8h
0x1400022d1  cmp     r13d, edi
0x1400022d4  jb      def_1400025EB; jumptable 00000001400025EB default case, cases 3-11,13-37,39-59,61,62,64-77
0x1400022da  mov     dword ptr [r14+4], 0
0x1400022e2  mov     ecx, 4Ch ; 'L'
0x1400022e7  mov     rax, [rbx]
0x1400022ea  mov     [r14+8], rax
0x1400022ee  mov     rax, [rbx+8]
0x1400022f2  mov     [r14+10h], rax
0x1400022f6  mov     rax, [rbx+10h]
0x1400022fa  mov     [r14+18h], rax
0x1400022fe  mov     rax, [rbx+18h]
0x140002302  mov     [r14+20h], rax
0x140002306  mov     rax, [rbx+20h]
0x14000230a  mov     [r14+28h], rax
0x14000230e  mov     rax, [rbx+28h]
0x140002312  mov     [r14+30h], rax
0x140002316  mov     eax, [rbx+48h]
0x140002319  mov     [r14+38h], eax
0x14000231d  mov     eax, 50h ; 'P'
0x140002322  test    dword ptr [rbx+48h], 400h
0x140002329  cmovz   eax, ecx
0x14000232c  lea     rcx, [r14+68h]; void *
0x140002330  mov     eax, [rax+rbx]
0x140002333  mov     [r14+40h], eax
0x140002337  mov     rax, [rbx+30h]
0x14000233b  mov     [r14+60h], rax
0x14000233f  movzx   eax, [rbp+37h+Name.Length]
0x140002343  mov     [r14+3Ch], eax
0x140002347  movzx   eax, byte ptr [rbp+37h+Src]
0x14000234b  mov     [r14+44h], al
0x14000234f  movzx   r8d, [rbp+37h+Name.Length]; Size
0x140002354  mov     rdx, [rbp+37h+Name.Buffer]; Src
0x140002358  call    memmove
0x14000235d  lea     rcx, [r14+46h]; void *
0x140002361  mov     rdx, [rbp+37h+Src+8]; Src
0x140002365  movzx   r8d, word ptr [rbp+37h+Src]; Size
0x14000236a  call    memmove
0x14000236f  mov     [r14], edi
0x140002372  test    edi, edi
0x140002374  jz      def_1400025EB; jumptable 00000001400025EB default case, cases 3-11,13-37,39-59,61,62,64-77
0x14000237a  sub     r13d, edi
0x14000237d  mov     eax, edi
0x14000237f  inc     r12d
0x140002382  mov     [rbp+37h+var_68], r14
0x140002386  add     r14, rax
0x140002389  lea     rdi, cs:140000000h
0x140002390  mov     edx, dword ptr [rbp+37h+arg_8]
0x140002393  inc     esi
0x140002395  mov     rcx, [rbp+37h+var_78]
0x140002399  cmp     esi, edx
0x14000239b  jb      loc_1400021C0
0x1400023a1  mov     rax, [rbp+37h+var_68]
0x1400023a5  mov     r8, [rbp+37h+var_70]
0x1400023a9  mov     r9d, [rbp+37h+var_80]
0x1400023ad  test    rax, rax
0x1400023b0  jz      short loc_1400023B8
0x1400023b2  mov     dword ptr [rax], 0
0x1400023b8  mov     eax, [r15+28h]
0x1400023bc  or      r8d, 0FFFFFFFEh
0x1400023c0  mov     dword ptr [rbp+37h+arg_8+4], eax
0x1400023c3  mov     eax, esi
0x1400023c5  and     eax, 3FFFFFFFh
0x1400023ca  shl     r8d, 1Eh
0x1400023ce  or      r8d, eax
0x1400023d1  mov     rax, [rbp+37h+arg_30]
0x1400023d5  mov     dword ptr [rbp+37h+arg_8], r8d
0x1400023d9  mov     r8, [rbp+37h+arg_20]
0x1400023dd  mov     rcx, [rbp+37h+arg_8]
0x1400023e1  mov     [r8], rcx
0x1400023e4  mov     [rax], r13d
0x1400023e7  test    r12d, r12d
0x1400023ea  jz      loc_1400028AF
0x1400023f0  mov     eax, r9d
0x1400023f3  mov     r12, [rsp+0B0h+var_20]
0x1400023fb  mov     rbx, [rsp+0B0h+arg_0]
0x140002403  mov     rsi, [rsp+0B0h+var_18]
0x14000240b  mov     r13, [rsp+0B0h+var_28]
0x140002413  mov     r14, [rsp+0B0h+var_30]
0x14000241b  add     rsp, 0A0h
0x140002422  pop     r15
0x140002424  pop     rdi
0x140002425  pop     rbp
0x140002426  retn
0x140002428  cmp     eax, 3
0x14000242b  jz      short loc_14000244E
0x14000242d  dec     eax; switch 81 cases
0x14000242f  cmp     eax, 50h
0x140002432  jbe     loc_1400025D9
0x140002438  mov     edx, dword ptr [rbp+37h+arg_8]; jumptable 00000001400025EB default case, cases 3-11,13-37,39-59,61,62,64-77
0x14000243b  jmp     loc_1400023A1
0x140002440  xor     edx, edx
0x140002442  jmp     loc_1400021F8
0x140002447  mov     ecx, ebx
0x140002449  jmp     loc_140002215
0x14000244e  movzx   edi, [rbp+37h+Name.Length]
0x140002452  add     edi, 65h ; 'e'
0x140002455  and     edi, 0FFFFFFF8h
0x140002458  cmp     r13d, edi
0x14000245b  jb      short def_1400025EB; jumptable 00000001400025EB default case, cases 3-11,13-37,39-59,61,62,64-77
0x14000245d  mov     dword ptr [r14+4], 0
0x140002465  mov     ecx, 4Ch ; 'L'
0x14000246a  mov     rax, [rbx]
0x14000246d  mov     [r14+8], rax
0x140002471  mov     rax, [rbx+8]
0x140002475  mov     [r14+10h], rax
0x140002479  mov     rax, [rbx+10h]
0x14000247d  mov     [r14+18h], rax
0x140002481  mov     rax, [rbx+18h]
0x140002485  mov     [r14+20h], rax
0x140002489  mov     rax, [rbx+20h]
0x14000248d  mov     [r14+28h], rax
0x140002491  mov     rax, [rbx+28h]
0x140002495  mov     [r14+30h], rax
0x140002499  mov     eax, [rbx+48h]
0x14000249c  mov     [r14+38h], eax
0x1400024a0  mov     eax, 50h ; 'P'
0x1400024a5  test    dword ptr [rbx+48h], 400h
0x1400024ac  cmovz   eax, ecx
0x1400024af  lea     rcx, [r14+5Eh]
0x1400024b3  mov     eax, [rax+rbx]
0x1400024b6  mov     [r14+40h], eax
0x1400024ba  jmp     loc_14000233F
0x1400024bf  cmp     [rbp+37h+arg_38], 0
0x1400024c3  jnz     def_1400025EB; jumptable 00000001400025EB default case, cases 3-11,13-37,39-59,61,62,64-77
0x1400024c9  cmp     [rbp+37h+arg_10], 0
0x1400024cd  jnz     loc_140002245
0x1400024d3  jmp     def_1400025EB; jumptable 00000001400025EB default case, cases 3-11,13-37,39-59,61,62,64-77
0x1400024d8  test    r9b, r9b
0x1400024db  jnz     loc_14000218C
0x1400024e1  mov     r8d, [r15+7Ch]; NumOfElements
0x1400024e5  lea     rax, DirCacheLongNameKeyCompare
0x1400024ec  mov     rdx, [r15+88h]; Base
0x1400024f3  lea     rcx, [rbp+37h+Expression]; Key
0x1400024f7  mov     [rsp+0B0h+Context], r15; Context
0x1400024fc  mov     r9d, 4; SizeOfElements
0x140002502  mov     [rsp+0B0h+PtFuncCompare], rax; PtFuncCompare
0x140002507  call    cs:__imp_bsearch_s
0x14000250e  nop     dword ptr [rax+rax+00h]
0x140002513  mov     rbx, rax
0x140002516  test    rax, rax
0x140002519  jz      loc_1400026AC
0x14000251f  sub     ebx, [r15+88h]
0x140002526  shr     ebx, 2
0x140002529  xor     edi, edi
0x14000252b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002532  lea     rax, WPP_GLOBAL_Control
0x140002539  cmp     rcx, rax
0x14000253c  jz      short loc_14000254B
0x14000253e  test    dword ptr [rcx+2Ch], 100h
0x140002545  jnz     loc_14000281D
0x14000254b  lea     r14, [r15+90h]
0x140002552  lea     r12, [r15+80h]
0x140002559  mov     eax, [r15+28h]
0x14000255d  or      edi, 0FFFFFFFEh
0x140002560  mov     dword ptr [rbp+37h+var_70+4], eax
0x140002563  shl     edi, 1Eh
0x140002566  or      edi, ebx
0x140002568  mov     dword ptr [rbp+37h+var_70], edi
0x14000256b  mov     rax, [rbp+37h+var_70]
0x14000256f  mov     [rbp+37h+var_68], rax
0x140002573  mov     rax, [rbp+37h+var_68]
0x140002577  mov     esi, eax
0x140002579  shr     eax, 1Eh
0x14000257c  and     esi, 3FFFFFFFh
  ... truncated ...
```
