# CImpIAccessor::CopyAccessors(CExtBuffer *)

- ea: `0x1000cc30`
- end: `0x1000ce5d`
- name: `?CopyAccessors@CImpIAccessor@@AAGJPAVCExtBuffer@@@Z`
- size: `557`
- prototype: `int(CImpIAccessor *__hidden this, struct CExtBuffer *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1000bea0`

## callees

- `0x1000bb80`
- `0x1000cc30`
- `0x1000e9f0`
- `0x1004ce5d`
- `0x1004dc81`

## import_xrefs

- `msvcrt!realloc` at `0x1000cd83`
- `msvcrt!realloc` at `0x1000cd83`

## pseudocode

```c
int __fastcall CImpIAccessor::CopyAccessors(int a1, int a2)
{
  int v2; // esi
  unsigned int v3; // ebx
  _DWORD *v4; // esi
  int v5; // ecx
  _DWORD *v6; // edi
  int v7; // eax
  size_t v8; // ecx
  _DWORD *v9; // eax
  _DWORD *v10; // esi
  const void *v11; // eax
  void *v12; // edx
  unsigned int i; // esi
  _DWORD *v14; // eax
  int v15; // ecx
  void *v16; // eax
  _DWORD *v17; // ecx
  unsigned int v18; // eax
  unsigned int v19; // edi
  bool v20; // zf
  unsigned int *v22; // [esp+0h] [ebp-20h]
  unsigned int v23; // [esp+4h] [ebp-1Ch]
  unsigned int v24; // [esp+Ch] [ebp-14h]
  size_t Size; // [esp+14h] [ebp-Ch]
  size_t Sizea; // [esp+14h] [ebp-Ch]
  size_t Sizeb; // [esp+14h] [ebp-Ch]
  _DWORD *Src; // [esp+18h] [ebp-8h] BYREF
  int v30; // [esp+1Ch] [ebp-4h]

  v2 = a1;
  v30 = a1;
  if ( !a2 )
    return 0;
  CExtBuffer::GetNextUsedItem((CExtBuffer *)1, v22, v23);
  v3 = (unsigned int)Src;
  if ( !Src )
    return 0;
  while ( 1 )
  {
    v4 = *(_DWORD **)(v2 + 20);
    v5 = v4[6];
    if ( v3 > v5 + 8 * v4[5] - 1
      || (*(_BYTE *)(((v3 - v5) >> 3) + v4[4]) & *((_BYTE *)&Bitmap::ThisBit + ((v3 - v5) & 7))) != 0 )
    {
      v6 = 0;
    }
    else
    {
      v6 = *(_DWORD **)(v4[2] + 4 * v3);
    }
    v7 = v6[9];
    v8 = 52 * v7 + 40;
    if ( !v7 )
      v8 = 92;
    Size = v8;
    v9 = operator new(v8);
    v10 = v9;
    Src = v9;
    if ( !v9 )
      return -2147024882;
    memcpy(v9, v6, Size);
    if ( v6[8] )
    {
      v11 = operator new(saturated_mul(4u, v6[9]));
      v6[8] = v11;
      v12 = (void *)v10[8];
      if ( !v12 )
        return -2147024882;
      memcpy(v12, v11, 4 * v6[9]);
    }
    else
    {
      v6[8] = 0;
    }
    for ( i = 0; i < v6[9]; ++i )
    {
      Sizea = 13 * i;
      if ( v6[13 * i + 15] )
      {
        v14 = operator new(0x14u);
        Src[Sizea + 15] = v14;
        if ( !v14 )
          return -2147024882;
        v15 = v6[Sizea + 15];
        *(_OWORD *)v14 = *(_OWORD *)v15;
        v14[4] = *(_DWORD *)(v15 + 16);
      }
    }
    if ( v3 >= *(_DWORD *)(a2 + 4) )
    {
      v16 = _realloc(*(void **)(a2 + 8), (v3 + 64) * *(_DWORD *)a2);
      if ( !v16 )
        return -2147024882;
      *(_DWORD *)(a2 + 4) = v3 + 64;
      *(_DWORD *)(a2 + 8) = v16;
    }
    memcpy((void *)(*(_DWORD *)(a2 + 8) + v3 * *(_DWORD *)a2), &Src, *(_DWORD *)a2);
    if ( v3 - *(_DWORD *)(a2 + 24) < 8 * *(_DWORD *)(a2 + 20) || DynaBitmap::Grow((DynaBitmap *)(a2 + 16), v3) >= 0 )
      *(_BYTE *)(*(_DWORD *)(a2 + 16) + ((v3 - *(_DWORD *)(a2 + 24)) >> 3)) &= ~*((_BYTE *)&Bitmap::ThisBit
                                                                                + ((v3 - *(_DWORD *)(a2 + 24)) & 7));
    v2 = v30;
    v3 = 0;
    v17 = *(_DWORD **)(v30 + 20);
    Src = v17;
    Sizeb = v17[6];
    v18 = v17[3];
    v24 = Sizeb + 8 * v17[5] - 1;
    if ( v18 <= v24 )
    {
      v19 = v17[3];
      while ( 1 )
      {
        v18 = v19;
        v20 = (*(_BYTE *)(((v19 - Sizeb) >> 3) + v17[4]) & *((_BYTE *)&Bitmap::ThisBit + ((v19 - Sizeb) & 7))) == 0;
        v17 = Src;
        if ( v20 )
          break;
        v18 = v19 + 1;
        v19 = v18;
        Src[3] = v18;
        if ( v18 > v24 )
          goto LABEL_31;
      }
      v3 = v19;
LABEL_31:
      v2 = v30;
    }
    v17[3] = v18 + 1;
    if ( !v3 )
      return 0;
  }
}

```

## disassembly

```asm
0x1000cc30  mov     edi, edi
0x1000cc32  push    ebp
0x1000cc33  mov     ebp, esp
0x1000cc35  sub     esp, 14h
0x1000cc38  mov     [ebp+var_10], edx
0x1000cc3b  push    ebx
0x1000cc3c  push    esi; unsigned int
0x1000cc3d  mov     esi, ecx
0x1000cc3f  mov     [ebp+var_4], esi
0x1000cc42  push    edi; unsigned int *
0x1000cc43  test    edx, edx
0x1000cc45  jz      loc_1000CE48
0x1000cc4b  mov     ecx, [esi+14h]
0x1000cc4e  lea     edx, [ebp+Src]
0x1000cc51  push    1; this
0x1000cc53  call    ?GetNextUsedItem@CExtBuffer@@QAGXAAKK@Z; CExtBuffer::GetNextUsedItem(ulong &,ulong)
0x1000cc58  mov     ebx, [ebp+Src]
0x1000cc5b  test    ebx, ebx
0x1000cc5d  jz      loc_1000CE48
0x1000cc63  mov     esi, [esi+14h]
0x1000cc66  mov     eax, [esi+14h]
0x1000cc69  mov     ecx, [esi+18h]
0x1000cc6c  lea     eax, ds:0FFFFFFFFh[eax*8]
0x1000cc73  add     eax, ecx
0x1000cc75  cmp     ebx, eax
0x1000cc77  ja      short loc_1000CC9B
0x1000cc79  mov     eax, [esi+10h]
0x1000cc7c  mov     edx, ebx
0x1000cc7e  sub     edx, ecx
0x1000cc80  mov     ecx, edx
0x1000cc82  and     edx, 7
0x1000cc85  shr     ecx, 3
0x1000cc88  mov     al, [ecx+eax]
0x1000cc8b  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x1000cc91  jnz     short loc_1000CC9B
0x1000cc93  mov     eax, [esi+8]
0x1000cc96  mov     edi, [eax+ebx*4]
0x1000cc99  jmp     short loc_1000CC9D
0x1000cc9b  xor     edi, edi
0x1000cc9d  mov     eax, [edi+24h]
0x1000cca0  imul    ecx, eax, 34h ; '4'
0x1000cca3  add     ecx, 28h ; '('
0x1000cca6  test    eax, eax
0x1000cca8  mov     eax, 5Ch ; '\'
0x1000ccad  cmovz   ecx, eax
0x1000ccb0  push    ecx; Size
0x1000ccb1  mov     [ebp+Size], ecx
0x1000ccb4  call    ??2@YAPAXI@Z; operator new(uint)
0x1000ccb9  mov     esi, eax
0x1000ccbb  add     esp, 4
0x1000ccbe  mov     [ebp+Src], esi
0x1000ccc1  test    esi, esi
0x1000ccc3  jz      loc_1000CE51
0x1000ccc9  push    [ebp+Size]; Size
0x1000cccc  push    edi; Src
0x1000cccd  push    esi; void *
0x1000ccce  call    _memcpy
0x1000ccd3  add     esp, 0Ch
0x1000ccd6  cmp     dword ptr [edi+20h], 0
0x1000ccda  jnz     short loc_1000CCE5
0x1000ccdc  mov     dword ptr [edi+20h], 0
0x1000cce3  jmp     short loc_1000CD1F
0x1000cce5  mov     eax, [edi+24h]
0x1000cce8  mov     ecx, 4
0x1000cced  mul     ecx
0x1000ccef  mov     ecx, 0FFFFFFFFh
0x1000ccf4  cmovb   eax, ecx
0x1000ccf7  push    eax; Size
0x1000ccf8  call    ??2@YAPAXI@Z; operator new(uint)
0x1000ccfd  mov     [edi+20h], eax
0x1000cd00  add     esp, 4
0x1000cd03  mov     edx, [esi+20h]
0x1000cd06  test    edx, edx
0x1000cd08  jz      loc_1000CE51
0x1000cd0e  mov     ecx, [edi+24h]
0x1000cd11  shl     ecx, 2
0x1000cd14  push    ecx; Size
0x1000cd15  push    eax; Src
0x1000cd16  push    edx; void *
0x1000cd17  call    _memcpy
0x1000cd1c  add     esp, 0Ch
0x1000cd1f  xor     esi, esi
0x1000cd21  cmp     [edi+24h], esi
0x1000cd24  jbe     short loc_1000CD6F
0x1000cd26  nop     word ptr [eax+eax+00000000h]
0x1000cd30  imul    eax, esi, 34h ; '4'
0x1000cd33  mov     [ebp+Size], eax
0x1000cd36  cmp     dword ptr [eax+edi+3Ch], 0
0x1000cd3b  jz      short loc_1000CD69
0x1000cd3d  push    14h; Size
0x1000cd3f  call    ??2@YAPAXI@Z; operator new(uint)
0x1000cd44  mov     ecx, [ebp+Size]
0x1000cd47  add     esp, 4
0x1000cd4a  mov     edx, [ebp+Src]
0x1000cd4d  mov     [ecx+edx+3Ch], eax
0x1000cd51  test    eax, eax
0x1000cd53  jz      loc_1000CE51
0x1000cd59  mov     ecx, [ecx+edi+3Ch]
0x1000cd5d  movups  xmm0, xmmword ptr [ecx]
0x1000cd60  movups  xmmword ptr [eax], xmm0
0x1000cd63  mov     ecx, [ecx+10h]
0x1000cd66  mov     [eax+10h], ecx
0x1000cd69  inc     esi
0x1000cd6a  cmp     esi, [edi+24h]
0x1000cd6d  jb      short loc_1000CD30
0x1000cd6f  mov     edi, [ebp+var_10]
0x1000cd72  cmp     ebx, [edi+4]
0x1000cd75  jb      short loc_1000CD9A
0x1000cd77  mov     eax, [edi]
0x1000cd79  lea     esi, [ebx+40h]
0x1000cd7c  imul    eax, esi
0x1000cd7f  push    eax; Size
0x1000cd80  push    dword ptr [edi+8]; Block
0x1000cd83  call    ds:__imp__realloc
0x1000cd89  add     esp, 8
0x1000cd8c  test    eax, eax
0x1000cd8e  jz      loc_1000CE51
0x1000cd94  mov     [edi+4], esi
0x1000cd97  mov     [edi+8], eax
0x1000cd9a  mov     eax, [edi]
0x1000cd9c  lea     ecx, [ebp+Src]
0x1000cd9f  push    eax; Size
0x1000cda0  imul    eax, ebx
0x1000cda3  push    ecx; Src
0x1000cda4  add     eax, [edi+8]
0x1000cda7  push    eax; void *
0x1000cda8  call    _memcpy
0x1000cdad  mov     ecx, [edi+14h]
0x1000cdb0  mov     eax, ebx
0x1000cdb2  sub     eax, [edi+18h]
0x1000cdb5  add     esp, 0Ch
0x1000cdb8  shl     ecx, 3
0x1000cdbb  cmp     eax, ecx
0x1000cdbd  jb      short loc_1000CDCC
0x1000cdbf  push    ebx; unsigned int
0x1000cdc0  lea     ecx, [edi+10h]; this
0x1000cdc3  call    ?Grow@DynaBitmap@@AAEJK@Z; DynaBitmap::Grow(ulong)
0x1000cdc8  test    eax, eax
0x1000cdca  js      short loc_1000CDE4
0x1000cdcc  sub     ebx, [edi+18h]
0x1000cdcf  mov     ecx, ebx
0x1000cdd1  and     ebx, 7
0x1000cdd4  shr     ecx, 3
0x1000cdd7  add     ecx, [edi+10h]
0x1000cdda  mov     al, ds:?ThisBit@Bitmap@@1QBEB[ebx]; uchar const * const Bitmap::ThisBit
0x1000cde0  not     al
0x1000cde2  and     [ecx], al
0x1000cde4  mov     esi, [ebp+var_4]
0x1000cde7  xor     ebx, ebx
0x1000cde9  mov     ecx, [esi+14h]
0x1000cdec  mov     [ebp+Src], ecx
0x1000cdef  mov     edx, [ecx+18h]
0x1000cdf2  mov     eax, [ecx+14h]
0x1000cdf5  mov     [ebp+Size], edx
0x1000cdf8  lea     edx, [edx+eax*8]
0x1000cdfb  mov     eax, [ecx+0Ch]
0x1000cdfe  dec     edx
0x1000cdff  mov     [ebp+var_14], edx
0x1000ce02  cmp     eax, edx
0x1000ce04  ja      short loc_1000CE3C
0x1000ce06  mov     edi, eax
0x1000ce08  mov     ecx, [ecx+10h]
0x1000ce0b  mov     esi, edi
0x1000ce0d  sub     esi, [ebp+Size]
0x1000ce10  mov     eax, edi
0x1000ce12  mov     edx, esi
0x1000ce14  and     esi, 7
0x1000ce17  shr     edx, 3
0x1000ce1a  mov     cl, [edx+ecx]
0x1000ce1d  test    ds:?ThisBit@Bitmap@@1QBEB[esi], cl; uchar const * const Bitmap::ThisBit
0x1000ce23  mov     ecx, [ebp+Src]
0x1000ce26  jz      short loc_1000CE37
0x1000ce28  lea     eax, [edi+1]
0x1000ce2b  mov     edi, eax
0x1000ce2d  mov     [ecx+0Ch], eax
0x1000ce30  cmp     eax, [ebp+var_14]
0x1000ce33  jbe     short loc_1000CE08
0x1000ce35  jmp     short loc_1000CE39
0x1000ce37  mov     ebx, eax
0x1000ce39  mov     esi, [ebp+var_4]
0x1000ce3c  inc     eax
0x1000ce3d  mov     [ecx+0Ch], eax
0x1000ce40  test    ebx, ebx
0x1000ce42  jnz     loc_1000CC63
0x1000ce48  pop     edi
0x1000ce49  pop     esi
0x1000ce4a  xor     eax, eax
0x1000ce4c  pop     ebx
0x1000ce4d  mov     esp, ebp
0x1000ce4f  pop     ebp
0x1000ce50  retn
0x1000ce51  pop     edi
0x1000ce52  pop     esi
0x1000ce53  mov     eax, 8007000Eh
0x1000ce58  pop     ebx
0x1000ce59  mov     esp, ebp
0x1000ce5b  pop     ebp
0x1000ce5c  retn
```
