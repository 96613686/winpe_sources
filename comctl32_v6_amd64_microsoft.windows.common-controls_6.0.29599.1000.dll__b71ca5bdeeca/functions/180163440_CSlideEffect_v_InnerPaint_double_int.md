# CSlideEffect::v_InnerPaint(double,int)

- ea: `0x180163440`
- end: `0x180163951`
- name: `?v_InnerPaint@CSlideEffect@@MEAAHNH@Z`
- size: `1297`
- prototype: `__int64 __fastcall(CSlideEffect *__hidden this, double, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800052e8`
- `0x18000d610`
- `0x180114520`
- `0x180163440`
- `0x1801d1010`

## import_xrefs

- `GDI32!DeleteObject` at `0x1801636d2`
- `GDI32!DeleteObject` at `0x1801637af`
- `GDI32!DeleteObject` at `0x1801636d2`
- `GDI32!DeleteObject` at `0x1801637af`
- `GDI32!CombineRgn` at `0x1801636aa`
- `GDI32!CombineRgn` at `0x180163796`
- `GDI32!CombineRgn` at `0x1801636aa`
- `GDI32!CombineRgn` at `0x180163796`
- `GDI32!SelectClipRgn` at `0x1801636fa`
- `GDI32!SelectClipRgn` at `0x1801637a6`
- `GDI32!SelectClipRgn` at `0x180163854`
- `GDI32!SelectClipRgn` at `0x1801638af`
- `GDI32!SelectClipRgn` at `0x1801636fa`
- `GDI32!SelectClipRgn` at `0x1801637a6`
- `GDI32!SelectClipRgn` at `0x180163854`
- `GDI32!SelectClipRgn` at `0x1801638af`
- `GDI32!CreateRectRgn` at `0x1801635cb`
- `GDI32!CreateRectRgn` at `0x1801635e7`
- `GDI32!CreateRectRgn` at `0x1801635cb`
- `GDI32!CreateRectRgn` at `0x1801635e7`
- `GDI32!BitBlt` at `0x18016375f`
- `GDI32!BitBlt` at `0x18016381a`
- `GDI32!BitBlt` at `0x180163893`
- `GDI32!BitBlt` at `0x18016375f`
- `GDI32!BitBlt` at `0x18016381a`
- `GDI32!BitBlt` at `0x180163893`
- `GDI32!GdiAlphaBlend` at `0x18016390b`
- `GDI32!GdiAlphaBlend` at `0x18016390b`
- `GDI32!GetClipRgn` at `0x180163835`
- `GDI32!GetClipRgn` at `0x180163835`
- `GDI32!SetRectRgn` at `0x180163691`
- `GDI32!SetRectRgn` at `0x180163691`
- `GDI32!OffsetRgn` at `0x1801636ea`
- `GDI32!OffsetRgn` at `0x18016377f`
- `GDI32!OffsetRgn` at `0x1801637c2`
- `GDI32!OffsetRgn` at `0x1801636ea`
- `GDI32!OffsetRgn` at `0x18016377f`
- `GDI32!OffsetRgn` at `0x1801637c2`
- `USER32!OffsetRect` at `0x180163676`
- `USER32!OffsetRect` at `0x180163716`
- `USER32!OffsetRect` at `0x1801637da`
- `USER32!OffsetRect` at `0x180163676`
- `USER32!OffsetRect` at `0x180163716`
- `USER32!OffsetRect` at `0x1801637da`

## pseudocode

```c
__int64 __fastcall CSlideEffect::v_InnerPaint(CSlideEffect *this, double a2, unsigned int a3)
{
  unsigned int ClipRgn; // r14d
  _DWORD *v5; // rsi
  struct tagRECT *v6; // rdi
  int v7; // ecx
  int v8; // r14d
  int v9; // r15d
  int v10; // r12d
  int v11; // r13d
  int v12; // ecx
  int v13; // ecx
  int v14; // eax
  int v15; // eax
  HRGN RectRgn; // rsi
  HRGN v17; // rdi
  struct _DSA *v18; // rcx
  int v19; // r13d
  int v20; // eax
  int v21; // edx
  int v22; // r12d
  int v23; // eax
  bool v24; // cc
  int v25; // r15d
  int v26; // edx
  struct tagRECT v27; // xmm0
  HRGN v28; // rdx
  HRGN v29; // rdx
  BLENDFUNCTION v31; // [rsp+68h] [rbp-49h]
  BLENDFUNCTION ftn; // [rsp+68h] [rbp-49h]
  int v33; // [rsp+6Ch] [rbp-45h]
  int v34; // [rsp+70h] [rbp-41h]
  int v35; // [rsp+74h] [rbp-3Dh]
  int dy; // [rsp+80h] [rbp-31h]
  int v37; // [rsp+84h] [rbp-2Dh]
  struct tagRECT rc; // [rsp+90h] [rbp-21h] BYREF
  struct tagRECT v40; // [rsp+A0h] [rbp-11h] BYREF
  struct tagRECT v41; // [rsp+B0h] [rbp-1h] BYREF

  ClipRgn = a3;
  if ( a2 >= 1.0
    || (v5 = (_DWORD *)((char *)this + 256), v6 = (struct tagRECT *)((char *)this + 32), !*((_DWORD *)this + 64))
    && (CCBeginDoubleBuffer(*((HDC *)this + 11)), !*v5) )
  {
    (*(void (__fastcall **)(CSlideEffect *))(*(_QWORD *)this + 32LL))(this);
    return ClipRgn;
  }
  v7 = *((_DWORD *)this + 52);
  v8 = 0;
  v9 = 0;
  v31 = 0;
  v10 = 0;
  v33 = 0;
  v11 = 0;
  v34 = 0;
  v35 = 0;
  if ( !v7 )
  {
    v8 = (int)((double)(*((_DWORD *)this + 55) - *((_DWORD *)this + 53)) * a2);
    v10 = *((_DWORD *)this + 53) + v8 - *((_DWORD *)this + 55);
    goto LABEL_13;
  }
  v12 = v7 - 1;
  if ( !v12 )
  {
    v15 = *((_DWORD *)this + 55) - *((_DWORD *)this + 53);
    v8 = (int)((double)v15 * COERCE_DOUBLE(*(_QWORD *)&a2 ^ _xmm));
    v10 = v8 + v15;
LABEL_13:
    v34 = v10;
    v31 = (BLENDFUNCTION)v8;
    goto LABEL_14;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v9 = (int)((double)(*((_DWORD *)this + 56) - *((_DWORD *)this + 54)) * a2);
    v11 = *((_DWORD *)this + 54) + v9 - *((_DWORD *)this + 56);
    goto LABEL_10;
  }
  if ( v13 == 1 )
  {
    v14 = *((_DWORD *)this + 56) - *((_DWORD *)this + 54);
    v9 = (int)((double)v14 * COERCE_DOUBLE(*(_QWORD *)&a2 ^ _xmm));
    v11 = v9 + v14;
LABEL_10:
    v33 = v9;
    v35 = v11;
  }
LABEL_14:
  if ( *((_QWORD *)this + 29) )
  {
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    if ( RectRgn )
    {
      v17 = CreateRectRgn(0, 0, 0, 0);
      if ( v17 )
      {
        v18 = (struct _DSA *)*((_QWORD *)this + 29);
        if ( *(int *)v18 > 0 )
        {
          v19 = 0;
          v20 = -v8;
          v21 = v9;
          if ( v8 > 0 )
            v20 = v8;
          v22 = v20;
          v23 = -v9;
          if ( v9 > 0 )
            v23 = v9;
          v24 = v9 <= 0;
          v25 = v23;
          if ( v24 )
            v21 = 0;
          dy = v21;
          v26 = v8;
          if ( v8 <= 0 )
            v26 = 0;
          v37 = v26;
          do
          {
            rc = *(struct tagRECT *)DSA_GetItemPtr(v18, v19);
            v27 = rc;
            rc.bottom -= v25;
            rc.right = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v27, 8)) - v22;
            OffsetRect(&rc, v37, dy);
            if ( SetRectRgn(v17, rc.left, rc.top, rc.right, rc.bottom) )
              CombineRgn(RectRgn, RectRgn, v17, 2);
            v18 = (struct _DSA *)*((_QWORD *)this + 29);
            ++v19;
          }
          while ( v19 < *(_DWORD *)v18 );
          v8 = (int)v31;
          v9 = v33;
          v10 = v34;
          v11 = v35;
        }
        DeleteObject(v17);
      }
      v6 = (struct tagRECT *)((char *)this + 32);
      OffsetRgn(RectRgn, -*((_DWORD *)this + 8), -*((_DWORD *)this + 9));
      SelectClipRgn(*((HDC *)this + 33), RectRgn);
    }
  }
  else
  {
    RectRgn = 0;
  }
  v40 = *v6;
  OffsetRect(&v40, v8, v9);
  BitBlt(
    *((HDC *)this + 33),
    v40.left,
    v40.top,
    v40.right - v40.left,
    v40.bottom - v40.top,
    *((HDC *)this + 20),
    v6->left,
    *((_DWORD *)this + 9),
    0xCC0020u);
  if ( RectRgn )
  {
    OffsetRgn(*((HRGN *)this + 30), -v6->left, -*((_DWORD *)this + 9));
    CombineRgn(RectRgn, *((HRGN *)this + 30), RectRgn, 3);
    SelectClipRgn(*((HDC *)this + 33), RectRgn);
    DeleteObject(RectRgn);
    OffsetRgn(*((HRGN *)this + 30), v6->left, *((_DWORD *)this + 9));
  }
  v41 = *v6;
  OffsetRect(&v41, v10, v11);
  BitBlt(
    *((HDC *)this + 33),
    v41.left,
    v41.top,
    v41.right - v41.left,
    v41.bottom - v41.top,
    *((HDC *)this + 8),
    v6->left,
    *((_DWORD *)this + 9),
    0xCC0020u);
  ClipRgn = a3;
  if ( a3 == -1 )
    ClipRgn = GetClipRgn(*((HDC *)this + 11), *((HRGN *)this + 16));
  v28 = (HRGN)*((_QWORD *)this + 30);
  if ( v28 && ClipRgn != -1 )
    SelectClipRgn(*((HDC *)this + 11), v28);
  BitBlt(
    *((HDC *)this + 11),
    *((_DWORD *)this + 8),
    *((_DWORD *)this + 9),
    *((_DWORD *)this + 10) - *((_DWORD *)this + 8),
    *((_DWORD *)this + 11) - *((_DWORD *)this + 9),
    *((HDC *)this + 33),
    *((_DWORD *)this + 8),
    *((_DWORD *)this + 9),
    0xCC0020u);
  v29 = (HRGN)*((_QWORD *)this + 31);
  if ( v29 && ClipRgn != -1 )
    SelectClipRgn(*((HDC *)this + 11), v29);
  *(_WORD *)&ftn.BlendOp = 0;
  *(_WORD *)&ftn.SourceConstantAlpha = (unsigned __int8)(int)(a2 * 255.0);
  GdiAlphaBlend(
    *((HDC *)this + 11),
    *((_DWORD *)this + 8),
    *((_DWORD *)this + 9),
    *((_DWORD *)this + 10) - *((_DWORD *)this + 8),
    *((_DWORD *)this + 11) - *((_DWORD *)this + 9),
    *((HDC *)this + 8),
    *((_DWORD *)this + 8),
    *((_DWORD *)this + 9),
    *((_DWORD *)this + 10) - *((_DWORD *)this + 8),
    *((_DWORD *)this + 11) - *((_DWORD *)this + 9),
    ftn);
  return ClipRgn;
}

```

## disassembly

```asm
0x180163440  mov     rax, rsp
0x180163443  mov     [rax+18h], rbx
0x180163447  push    rbp
0x180163448  push    rsi
0x180163449  push    rdi
0x18016344a  push    r12
0x18016344c  push    r13
0x18016344e  push    r14
0x180163450  push    r15
0x180163452  lea     rbp, [rax-5Fh]
0x180163456  sub     rsp, 0D0h
0x18016345d  movaps  xmmword ptr [rax-48h], xmm6
0x180163461  mov     rax, cs:__security_cookie
0x180163468  xor     rax, rsp
0x18016346b  mov     [rbp+57h+var_48], rax
0x18016346f  movsd   xmm0, cs:__real@3ff0000000000000
0x180163477  mov     r14d, r8d
0x18016347a  comisd  xmm0, xmm1
0x18016347e  mov     [rbp+57h+var_80], r8d
0x180163482  mov     rbx, rcx
0x180163485  movaps  xmm6, xmm1
0x180163488  jbe     loc_180163913
0x18016348e  lea     rsi, [rcx+100h]
0x180163495  cmp     dword ptr [rsi], 0
0x180163498  lea     rdi, [rcx+20h]
0x18016349c  jnz     short loc_1801634B6
0x18016349e  mov     rcx, [rcx+58h]; hdc
0x1801634a2  mov     r8, rsi
0x1801634a5  mov     rdx, rdi
0x1801634a8  call    CCBeginDoubleBuffer
0x1801634ad  cmp     dword ptr [rsi], 0
0x1801634b0  jz      loc_180163913
0x1801634b6  mov     ecx, [rbx+0D0h]
0x1801634bc  xor     r14d, r14d
0x1801634bf  xor     r15d, r15d
0x1801634c2  mov     dword ptr [rbp+57h+var_A0.BlendOp], r14d
0x1801634c6  xor     r12d, r12d
0x1801634c9  mov     [rbp+57h+var_9C], r15d
0x1801634cd  xor     r13d, r13d
0x1801634d0  mov     [rbp+57h+var_98], r12d
0x1801634d4  mov     [rbp+57h+var_94], r13d
0x1801634d8  test    ecx, ecx
0x1801634da  jz      loc_180163581
0x1801634e0  sub     ecx, 1
0x1801634e3  jz      short loc_180163554
0x1801634e5  sub     ecx, 1
0x1801634e8  jz      short loc_180163520
0x1801634ea  cmp     ecx, 1
0x1801634ed  jnz     loc_1801635B3
0x1801634f3  mov     eax, [rbx+0E0h]
0x1801634f9  movaps  xmm0, xmm6
0x1801634fc  sub     eax, [rbx+0D8h]
0x180163502  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x180163509  movd    xmm1, eax
0x18016350d  cvtdq2pd xmm1, xmm1
0x180163511  mulsd   xmm1, xmm0
0x180163515  cvttsd2si r15d, xmm1
0x18016351a  lea     r13d, [r15+rax]
0x18016351e  jmp     short loc_18016354A
0x180163520  mov     ecx, [rbx+0E0h]
0x180163526  mov     eax, ecx
0x180163528  mov     edx, [rbx+0D8h]
0x18016352e  sub     eax, edx
0x180163530  movd    xmm0, eax
0x180163534  cvtdq2pd xmm0, xmm0
0x180163538  mulsd   xmm0, xmm6
0x18016353c  cvttsd2si r15d, xmm0
0x180163541  mov     r13d, r15d
0x180163544  sub     r13d, ecx
0x180163547  add     r13d, edx
0x18016354a  mov     [rbp+57h+var_9C], r15d
0x18016354e  mov     [rbp+57h+var_94], r13d
0x180163552  jmp     short loc_1801635B3
0x180163554  mov     eax, [rbx+0DCh]
0x18016355a  movaps  xmm0, xmm6
0x18016355d  sub     eax, [rbx+0D4h]
0x180163563  xorps   xmm0, cs:__xmm@80000000000000008000000000000000
0x18016356a  movd    xmm1, eax
0x18016356e  cvtdq2pd xmm1, xmm1
0x180163572  mulsd   xmm1, xmm0
0x180163576  cvttsd2si r14d, xmm1
0x18016357b  lea     r12d, [r14+rax]
0x18016357f  jmp     short loc_1801635AB
0x180163581  mov     ecx, [rbx+0DCh]
0x180163587  mov     eax, ecx
0x180163589  mov     edx, [rbx+0D4h]
0x18016358f  sub     eax, edx
0x180163591  movd    xmm0, eax
0x180163595  cvtdq2pd xmm0, xmm0
0x180163599  mulsd   xmm0, xmm6
0x18016359d  cvttsd2si r14d, xmm0
0x1801635a2  mov     r12d, r14d
0x1801635a5  sub     r12d, ecx
0x1801635a8  add     r12d, edx
0x1801635ab  mov     [rbp+57h+var_98], r12d
0x1801635af  mov     dword ptr [rbp+57h+var_A0.BlendOp], r14d
0x1801635b3  cmp     qword ptr [rbx+0E8h], 0
0x1801635bb  jz      loc_180163702
0x1801635c1  xor     r9d, r9d; y2
0x1801635c4  xor     r8d, r8d; x2
0x1801635c7  xor     edx, edx; y1
0x1801635c9  xor     ecx, ecx; x1
0x1801635cb  call    cs:__imp_CreateRectRgn
0x1801635d1  mov     rsi, rax
0x1801635d4  test    rax, rax
0x1801635d7  jz      loc_180163704
0x1801635dd  xor     r9d, r9d; y2
0x1801635e0  xor     r8d, r8d; x2
0x1801635e3  xor     edx, edx; y1
0x1801635e5  xor     ecx, ecx; x1
0x1801635e7  call    cs:__imp_CreateRectRgn
0x1801635ed  mov     rdi, rax
0x1801635f0  test    rax, rax
0x1801635f3  jz      loc_1801636D8
0x1801635f9  mov     rcx, [rbx+0E8h]; hdsa
0x180163600  cmp     dword ptr [rcx], 0
0x180163603  jle     loc_1801636CF
0x180163609  xor     r13d, r13d
0x18016360c  mov     eax, r14d
0x18016360f  neg     eax
0x180163611  mov     edx, r15d
0x180163614  cmovs   eax, r14d
0x180163618  mov     [rbp+57h+var_90], eax
0x18016361b  mov     eax, r15d
0x18016361e  mov     r12d, [rbp+57h+var_90]
0x180163622  neg     eax
0x180163624  cmovs   eax, r15d
0x180163628  mov     [rbp+57h+var_8C], eax
0x18016362b  xor     eax, eax
0x18016362d  test    r15d, r15d
0x180163630  mov     r15d, [rbp+57h+var_8C]
0x180163634  cmovle  edx, eax
0x180163637  test    r14d, r14d
0x18016363a  mov     [rbp+57h+dy], edx
0x18016363d  mov     edx, r14d
0x180163640  mov     r14d, [rbp+57h+dy]
0x180163644  cmovle  edx, eax
0x180163647  mov     [rbp+57h+var_84], edx
0x18016364a  mov     edx, r13d; i
0x18016364d  call    DSA_GetItemPtr
0x180163652  mov     edx, [rbp+57h+var_84]; dx
0x180163655  lea     rcx, [rbp+57h+rc]; lprc
0x180163659  mov     r8d, r14d; dy
0x18016365c  movups  xmm0, xmmword ptr [rax]
0x18016365f  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x180163663  sub     [rbp+57h+rc.bottom], r15d
0x180163667  psrldq  xmm0, 8
0x18016366c  movd    eax, xmm0
0x180163670  sub     eax, r12d
0x180163673  mov     [rbp+57h+rc.right], eax
0x180163676  call    cs:__imp_OffsetRect
0x18016367c  mov     eax, [rbp+57h+rc.bottom]
0x18016367f  mov     rcx, rdi; hrgn
0x180163682  mov     r9d, [rbp+57h+rc.right]; right
0x180163686  mov     r8d, [rbp+57h+rc.top]; top
0x18016368a  mov     edx, [rbp+57h+rc.left]; left
0x18016368d  mov     [rsp+100h+bottom], eax; bottom
0x180163691  call    cs:__imp_SetRectRgn
0x180163697  test    eax, eax
0x180163699  jz      short loc_1801636B0
0x18016369b  mov     r9d, 2; iMode
0x1801636a1  mov     r8, rdi; hrgnSrc2
0x1801636a4  mov     rdx, rsi; hrgnSrc1
0x1801636a7  mov     rcx, rsi; hrgnDst
0x1801636aa  call    cs:__imp_CombineRgn
0x1801636b0  mov     rcx, [rbx+0E8h]
0x1801636b7  inc     r13d
0x1801636ba  cmp     r13d, [rcx]
0x1801636bd  jl      short loc_18016364A
0x1801636bf  mov     r14d, dword ptr [rbp+57h+var_A0.BlendOp]
0x1801636c3  mov     r15d, [rbp+57h+var_9C]
0x1801636c7  mov     r12d, [rbp+57h+var_98]
0x1801636cb  mov     r13d, [rbp+57h+var_94]
0x1801636cf  mov     rcx, rdi; ho
0x1801636d2  call    cs:__imp_DeleteObject
0x1801636d8  mov     r8d, [rbx+24h]
0x1801636dc  lea     rdi, [rbx+20h]
0x1801636e0  mov     edx, [rdi]
0x1801636e2  neg     r8d; y
0x1801636e5  neg     edx; x
0x1801636e7  mov     rcx, rsi; hrgn
0x1801636ea  call    cs:__imp_OffsetRgn
0x1801636f0  mov     rcx, [rbx+108h]; hdc
0x1801636f7  mov     rdx, rsi; hrgn
0x1801636fa  call    cs:__imp_SelectClipRgn
0x180163700  jmp     short loc_180163704
0x180163702  xor     esi, esi
0x180163704  movups  xmm0, xmmword ptr [rdi]
0x180163707  mov     r8d, r15d; dy
0x18016370a  lea     rcx, [rbp+57h+var_68]; lprc
0x18016370e  mov     edx, r14d; dx
0x180163711  movdqu  xmmword ptr [rbp+57h+var_68.left], xmm0
0x180163716  call    cs:__imp_OffsetRect
0x18016371c  mov     eax, [rbx+24h]
0x18016371f  mov     r14d, 0CC0020h
0x180163725  mov     ecx, [rbp+57h+var_68.bottom]
0x180163728  mov     r8d, [rbp+57h+var_68.top]; y
0x18016372c  sub     ecx, r8d
0x18016372f  mov     r9d, [rbp+57h+var_68.right]
0x180163733  mov     edx, [rbp+57h+var_68.left]; x
0x180163736  sub     r9d, edx; cx
0x180163739  mov     [rsp+100h+rop], r14d; rop
0x18016373e  mov     [rsp+100h+y1], eax; y1
0x180163742  mov     eax, [rdi]
0x180163744  mov     [rsp+100h+x1], eax; x1
0x180163748  mov     rax, [rbx+0A0h]
0x18016374f  mov     [rsp+100h+hdcSrc], rax; hdcSrc
0x180163754  mov     [rsp+100h+bottom], ecx; cy
0x180163758  mov     rcx, [rbx+108h]; hdc
0x18016375f  call    cs:__imp_BitBlt
0x180163765  xor     r15d, r15d
0x180163768  test    rsi, rsi
0x18016376b  jz      short loc_1801637C8
0x18016376d  mov     r8d, [rbx+24h]
0x180163771  mov     edx, [rdi]
0x180163773  neg     r8d; y
0x180163776  mov     rcx, [rbx+0F0h]; hrgn
0x18016377d  neg     edx; x
0x18016377f  call    cs:__imp_OffsetRgn
0x180163785  mov     rdx, [rbx+0F0h]; hrgnSrc1
0x18016378c  lea     r9d, [r15+3]; iMode
0x180163790  mov     r8, rsi; hrgnSrc2
0x180163793  mov     rcx, rsi; hrgnDst
0x180163796  call    cs:__imp_CombineRgn
0x18016379c  mov     rcx, [rbx+108h]; hdc
0x1801637a3  mov     rdx, rsi; hrgn
0x1801637a6  call    cs:__imp_SelectClipRgn
0x1801637ac  mov     rcx, rsi; ho
0x1801637af  call    cs:__imp_DeleteObject
0x1801637b5  mov     r8d, [rbx+24h]; y
0x1801637b9  mov     edx, [rdi]; x
0x1801637bb  mov     rcx, [rbx+0F0h]; hrgn
0x1801637c2  call    cs:__imp_OffsetRgn
0x1801637c8  movups  xmm0, xmmword ptr [rdi]
0x1801637cb  mov     r8d, r13d; dy
0x1801637ce  lea     rcx, [rbp+57h+var_58]; lprc
0x1801637d2  mov     edx, r12d; dx
0x1801637d5  movdqu  xmmword ptr [rbp+57h+var_58.left], xmm0
0x1801637da  call    cs:__imp_OffsetRect
0x1801637e0  mov     eax, [rbx+24h]
0x1801637e3  mov     ecx, [rbp+57h+var_58.bottom]
0x1801637e6  mov     r8d, [rbp+57h+var_58.top]; y
0x1801637ea  sub     ecx, r8d
0x1801637ed  mov     r9d, [rbp+57h+var_58.right]
0x1801637f1  mov     edx, [rbp+57h+var_58.left]; x
0x1801637f4  sub     r9d, edx; cx
0x1801637f7  mov     [rsp+100h+rop], r14d; rop
0x1801637fc  mov     [rsp+100h+y1], eax; y1
0x180163800  mov     eax, [rdi]
0x180163802  mov     [rsp+100h+x1], eax; x1
0x180163806  mov     rax, [rbx+40h]
0x18016380a  mov     [rsp+100h+hdcSrc], rax; hdcSrc
0x18016380f  mov     [rsp+100h+bottom], ecx; cy
0x180163813  mov     rcx, [rbx+108h]; hdc
0x18016381a  call    cs:__imp_BitBlt
0x180163820  mov     r14d, [rbp+57h+var_80]
0x180163824  cmp     r14d, 0FFFFFFFFh
0x180163828  jnz     short loc_18016383E
0x18016382a  mov     rdx, [rbx+80h]; hrgn
0x180163831  mov     rcx, [rbx+58h]; hdc
0x180163835  call    cs:__imp_GetClipRgn
0x18016383b  mov     r14d, eax
0x18016383e  mov     rdx, [rbx+0F0h]; hrgn
0x180163845  test    rdx, rdx
0x180163848  jz      short loc_18016385A
0x18016384a  cmp     r14d, 0FFFFFFFFh
0x18016384e  jz      short loc_18016385A
0x180163850  mov     rcx, [rbx+58h]; hdc
0x180163854  call    cs:__imp_SelectClipRgn
0x18016385a  mov     r8d, [rbx+24h]; y
0x18016385e  mov     ecx, [rbx+2Ch]
0x180163861  mov     edx, [rbx+20h]; x
0x180163864  sub     ecx, r8d
0x180163867  mov     rax, [rbx+108h]
0x18016386e  mov     r9d, [rbx+28h]
0x180163872  mov     [rsp+100h+rop], 0CC0020h; rop
0x18016387a  sub     r9d, edx; cx
0x18016387d  mov     [rsp+100h+y1], r8d; y1
0x180163882  mov     [rsp+100h+x1], edx; x1
0x180163886  mov     [rsp+100h+hdcSrc], rax; hdcSrc
0x18016388b  mov     [rsp+100h+bottom], ecx; cy
0x18016388f  mov     rcx, [rbx+58h]; hdc
0x180163893  call    cs:__imp_BitBlt
0x180163899  mov     rdx, [rbx+0F8h]; hrgn
0x1801638a0  test    rdx, rdx
0x1801638a3  jz      short loc_1801638B5
0x1801638a5  cmp     r14d, 0FFFFFFFFh
0x1801638a9  jz      short loc_1801638B5
0x1801638ab  mov     rcx, [rbx+58h]; hdc
0x1801638af  call    cs:__imp_SelectClipRgn
0x1801638b5  mov     ecx, [rbx+2Ch]
0x1801638b8  mov     r8d, [rbx+24h]; yoriginDest
0x1801638bc  sub     ecx, r8d
0x1801638bf  mov     edx, [rbx+20h]; xoriginDest
0x1801638c2  mulsd   xmm6, cs:__real@406fe00000000000
0x1801638ca  mov     r9d, [rbx+28h]
0x1801638ce  sub     r9d, edx; wDest
0x1801638d1  mov     word ptr [rbp+57h+var_A0.BlendOp], r15w
0x1801638d6  mov     [rbp+57h+var_A0.AlphaFormat], r15b
0x1801638da  cvttsd2si eax, xmm6
  ... truncated ...
```
