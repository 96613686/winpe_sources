# ShlTextOut(HDC__ *,void * *,int,int,uint,tagRECT const *,tag_SCRIPT_ANALYSIS const *,ushort const *,int,int const *,int const *,tagGOFFSET const *)

- ea: `0x180015190`
- end: `0x1800156f0`
- name: `?ShlTextOut@@YAJPEAUHDC__@@PEAPEAXHHIPEBUtagRECT@@PEBUtag_SCRIPT_ANALYSIS@@PEBGHPEBH5PEBUtagGOFFSET@@@Z`
- size: `1376`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, void **@<rdx>, int@<r8d>, int@<r9d>, unsigned int, const struct tagRECT *, const struct tag_SCRIPT_ANALYSIS *, const unsigned __int16 *, int, const int *, const int *, const struct tagGOFFSET *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180014710`

## callees

- `0x18000d6c0`
- `0x180014240`
- `0x180015190`
- `0x180015970`
- `0x180016900`
- `0x18001fe20`
- `0x180021fe0`
- `0x180029790`
- `0x18004140c`
- `0x18007ac50`

## import_xrefs

- `GDI32!DeleteDC` at `0x1800155c0`
- `GDI32!DeleteDC` at `0x1800155c0`
- `GDI32!ExtTextOutW` at `0x180015393`
- `GDI32!ExtTextOutW` at `0x18001559f`
- `GDI32!ExtTextOutW` at `0x180015393`
- `GDI32!ExtTextOutW` at `0x18001559f`
- `GDI32!MoveToEx` at `0x180015351`
- `GDI32!MoveToEx` at `0x1800153bc`
- `GDI32!MoveToEx` at `0x180015564`
- `GDI32!MoveToEx` at `0x180015351`
- `GDI32!MoveToEx` at `0x1800153bc`
- `GDI32!MoveToEx` at `0x180015564`
- `GDI32!SelectObject` at `0x180015517`
- `GDI32!SelectObject` at `0x1800156be`
- `GDI32!SelectObject` at `0x1800156db`
- `GDI32!SelectObject` at `0x180015517`
- `GDI32!SelectObject` at `0x1800156be`
- `GDI32!SelectObject` at `0x1800156db`
- `GDI32!SetBkMode` at `0x180015340`
- `GDI32!SetBkMode` at `0x1800153d7`
- `GDI32!SetBkMode` at `0x180015552`
- `GDI32!SetBkMode` at `0x180015340`
- `GDI32!SetBkMode` at `0x1800153d7`
- `GDI32!SetBkMode` at `0x180015552`
- `GDI32!SetTextAlign` at `0x180015332`
- `GDI32!SetTextAlign` at `0x1800153c7`
- `GDI32!SetTextAlign` at `0x180015543`
- `GDI32!SetTextAlign` at `0x180015332`
- `GDI32!SetTextAlign` at `0x1800153c7`
- `GDI32!SetTextAlign` at `0x180015543`
- `GDI32!DeleteObject` at `0x1800156c8`
- `GDI32!DeleteObject` at `0x1800156e5`
- `GDI32!DeleteObject` at `0x1800156c8`
- `GDI32!DeleteObject` at `0x1800156e5`
- `TextShaping!ShapingDrawGlyphs` at `0x180015468`
- `TextShaping!ShapingDrawGlyphs` at `0x180015468`

## pseudocode

```c
__int64 __fastcall ShlTextOut(
        HDC hdc,
        void **a2,
        int a3,
        int a4,
        unsigned int a5,
        const struct tagRECT *a6,
        const struct tag_SCRIPT_ANALYSIS *a7,
        const unsigned __int16 *a8,
        int a9,
        const int *a10,
        const int *a11,
        const struct tagGOFFSET *a12)
{
  const struct tagGOFFSET *v12; // rsi
  __int64 v15; // r8
  __int64 v16; // rax
  __int16 v17; // dx
  unsigned __int16 v18; // cx
  int v19; // edi
  UINT TextAlign; // esi
  int BkMode; // edi
  UINT v22; // eax
  int v23; // eax
  HDC CompatibleDC; // rax
  UINT v26; // eax
  const int *v27; // r8
  int v28; // r9d
  signed int v29; // edx
  __m128i v30; // xmm2
  __m128i v31; // xmm1
  __int64 v32; // rax
  __m128i v33; // xmm1
  __m128i v34; // xmm1
  __int64 v35; // rax
  INT lpDx; // [rsp+90h] [rbp-80h] BYREF
  HDC hdca; // [rsp+98h] [rbp-78h]
  struct tagPOINT pt; // [rsp+A0h] [rbp-70h] BYREF
  void **v39; // [rsp+B0h] [rbp-60h] BYREF
  HDC v40; // [rsp+B8h] [rbp-58h]
  int v41; // [rsp+C0h] [rbp-50h]
  int v42; // [rsp+C4h] [rbp-4Ch]
  int v43; // [rsp+C8h] [rbp-48h]
  HGDIOBJ ho[2]; // [rsp+D0h] [rbp-40h]
  HGDIOBJ v45[2]; // [rsp+E0h] [rbp-30h]
  struct tagPOINT v46; // [rsp+F0h] [rbp-20h] BYREF
  int v47; // [rsp+F8h] [rbp-18h]
  __int64 v48; // [rsp+FCh] [rbp-14h]
  __int64 v49; // [rsp+108h] [rbp-8h]
  int *v50; // [rsp+110h] [rbp+0h]
  int v51; // [rsp+118h] [rbp+8h]
  int v52; // [rsp+11Ch] [rbp+Ch]
  HGDIOBJ h; // [rsp+120h] [rbp+10h]
  const struct tagGOFFSET *v54; // [rsp+128h] [rbp+18h]
  __int128 v55; // [rsp+130h] [rbp+20h] BYREF
  void **v56; // [rsp+140h] [rbp+30h] BYREF
  int v57; // [rsp+148h] [rbp+38h]
  int v58; // [rsp+150h] [rbp+40h] BYREF
  _DWORD v59[5]; // [rsp+154h] [rbp+44h] BYREF
  RECT rect; // [rsp+168h] [rbp+58h] BYREF
  _QWORD v61[3]; // [rsp+180h] [rbp+70h] BYREF
  int v62; // [rsp+198h] [rbp+88h]

  v12 = a12;
  v15 = (__int64)*a2;
  v54 = a12;
  v16 = *(_QWORD *)(v15 + 80);
  lpDx = 1000;
  v17 = *(_WORD *)(v16 + 20);
  v56 = &CUspShapingClient::`vftable';
  v61[0] = &CUspShapingFont::`vftable';
  v57 = 0;
  v62 = 0;
  v59[3] = 0;
  v18 = *(_WORD *)a7;
  LOWORD(v16) = *(_WORD *)a7;
  v61[1] = hdc;
  v61[2] = v15;
  v55 = 0;
  qmemcpy(v59, "dfltdflt", 8);
  v19 = *((unsigned __int16 *)&ShlScriptSupport + 4 * (v16 & 0x3FF));
  v40 = hdc;
  v41 = a3;
  v59[2] = v17 == 64;
  v42 = a4;
  *(_OWORD *)ho = 0;
  *(_OWORD *)v45 = 0;
  LODWORD(v16) = *(_WORD *)&a7->s & 0x400 | 0x2000;
  v47 = -1;
  v49 = v15;
  v59[4] = ((unsigned int)v16 >> 7) | ((v18 & 0x400 | (v18 >> 1) & 0x1800u) >> 10);
  v52 = -1;
  if ( v19 == 0xFFFF )
    v19 = 1;
  v43 = 1;
  v58 = v19;
  v39 = &CUspShapingDrawingSurface::`vftable';
  v48 = 0;
  v51 = v18 & 0x3FF;
  v50 = &v58;
  if ( hdc )
  {
    pt = 0;
    TextAlign = GetTextAlign(hdc);
    GetCurrentPositionEx(hdc, &pt);
    BkMode = GetBkMode(hdc);
    SetTextAlign(hdc, TextAlign & 0xFFFFFFF8 | 1);
    SetBkMode(hdc, 1);
    MoveToEx(hdc, 0, 0, 0);
    rect = 0;
    ExtTextOutW(hdc, 0, 0, 0x1004u, &rect, L" ", 1u, &lpDx);
    GetCurrentPositionEx(hdc, &v46);
    if ( !v46.x && !v46.y )
    {
      v46.x = lpDx;
      h = (HGDIOBJ)GetDCObject(hdc, 655360);
      if ( h )
      {
        CompatibleDC = CreateCompatibleDC(hdc);
        hdca = CompatibleDC;
        if ( CompatibleDC )
        {
          SelectObject(CompatibleDC, h);
          if ( GetGraphicsMode(hdc) == 2 )
            SetGraphicsMode(hdca, 2);
          v26 = GetTextAlign(hdca);
          SetTextAlign(hdca, v26 & 0xFFFFFFF8 | 1);
          SetBkMode(hdca, 1);
          MoveToEx(hdca, 0, 0, 0);
          ExtTextOutW(hdca, 0, 0, 0x1000u, &rect, L" ", 1u, &lpDx);
          GetCurrentPositionEx(hdca, &v46);
          if ( !v46.x && !v46.y )
            v46.x = lpDx;
          DeleteDC(hdca);
        }
      }
    }
    MoveToEx(hdc, pt.x, pt.y, 0);
    SetTextAlign(hdc, TextAlign);
    if ( BkMode != 1 )
      SetBkMode(hdc, BkMode);
    v22 = GetTextAlign(hdc);
    v19 = v58;
    v12 = v54;
    HIDWORD(v48) = v22;
  }
  else
  {
    v43 = 0;
  }
  if ( v19 == 23 )
  {
    v27 = a11;
    v28 = 0;
    if ( !a11 )
      v27 = a10;
    if ( a9 > 0 )
    {
      v29 = 0;
      if ( (unsigned int)a9 < 8 )
        goto LABEL_42;
      v30 = 0;
      v31 = 0;
      do
      {
        v32 = v29;
        v29 += 8;
        v30 = _mm_add_epi32(v30, _mm_loadu_si128((const __m128i *)&v27[v32]));
        v31 = _mm_add_epi32(v31, _mm_loadu_si128((const __m128i *)&v27[v32 + 4]));
      }
      while ( v29 < (int)(a9 & 0xFFFFFFF8) );
      v33 = _mm_add_epi32(v31, v30);
      v34 = _mm_add_epi32(v33, _mm_srli_si128(v33, 8));
      v28 = _mm_cvtsi128_si32(_mm_add_epi32(v34, _mm_srli_si128(v34, 4)));
      if ( v29 < a9 )
      {
LABEL_42:
        do
        {
          v35 = v29++;
          v28 += v27[v35];
        }
        while ( v29 < a9 );
      }
    }
    v52 = v28;
  }
  DWORD2(v55) = a5;
  *(_QWORD *)&v55 = a6;
  v23 = ShapingDrawGlyphs(&v56, v61, &v58, 0, 0, 0, 0, a8, 0, a9, a10, a11, v12, &v39, &v55, 0, 0);
  if ( v23 )
  {
    if ( v23 == -2 )
    {
      CUspShapingDrawingSurface::~CUspShapingDrawingSurface((CUspShapingDrawingSurface *)&v39);
      return 2147942414LL;
    }
    else if ( v62 == -2147483638 )
    {
      CUspShapingDrawingSurface::~CUspShapingDrawingSurface((CUspShapingDrawingSurface *)&v39);
      return 2147483658LL;
    }
    else
    {
      CUspShapingDrawingSurface::~CUspShapingDrawingSurface((CUspShapingDrawingSurface *)&v39);
      return 2147500037LL;
    }
  }
  else
  {
    v39 = &CUspShapingDrawingSurface::`vftable';
    if ( ho[0] )
    {
      SelectObject(v40, ho[1]);
      DeleteObject(ho[0]);
    }
    if ( v45[0] )
    {
      SelectObject(v40, v45[1]);
      DeleteObject(v45[0]);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180015190  push    rbp
0x180015192  push    rbx
0x180015193  push    rsi
0x180015194  push    rdi
0x180015195  push    r12
0x180015197  push    r13
0x180015199  push    r14
0x18001519b  push    r15
0x18001519d  lea     rbp, [rsp-128h]
0x1800151a5  sub     rsp, 238h
0x1800151ac  mov     rax, cs:__security_cookie
0x1800151b3  xor     rax, rsp
0x1800151b6  mov     [rbp+160h+var_50], rax
0x1800151bd  mov     r10, [rbp+160h+arg_30]
0x1800151c4  lea     rdi, ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport
0x1800151cb  mov     rsi, [rbp+160h+arg_58]
0x1800151d2  mov     rbx, rcx
0x1800151d5  mov     r14, [rbp+160h+arg_50]
0x1800151dc  xor     ecx, ecx
0x1800151de  mov     r15, [rbp+160h+arg_48]
0x1800151e5  mov     r11d, r8d
0x1800151e8  mov     r8, [rdx]
0x1800151eb  xorps   xmm0, xmm0
0x1800151ee  mov     r12, [rbp+160h+arg_28]
0x1800151f5  xorps   xmm1, xmm1
0x1800151f8  mov     r13, [rbp+160h+arg_38]
0x1800151ff  mov     [rbp+160h+var_148], rsi
0x180015203  mov     rax, [r8+50h]
0x180015207  mov     [rbp+160h+var_1E0], 3E8h
0x18001520e  movzx   edx, word ptr [rax+14h]
0x180015212  lea     rax, ??_7CUspShapingClient@@6B@; const CUspShapingClient::`vftable'
0x180015219  mov     [rbp+160h+var_130], rax
0x18001521d  lea     rax, ??_7CUspShapingFont@@6B@; const CUspShapingFont::`vftable'
0x180015224  mov     [rbp+160h+var_F0], rax
0x180015228  mov     [rbp+160h+var_128], ecx
0x18001522b  mov     [rbp+160h+var_D8], ecx
0x180015231  mov     [rbp+160h+var_110], ecx
0x180015234  movzx   ecx, word ptr [r10]
0x180015238  mov     eax, ecx
0x18001523a  mov     [rbp+160h+var_E8], rbx
0x18001523e  and     eax, 3FFh
0x180015243  mov     [rbp+160h+var_E0], r8
0x18001524a  movups  [rbp+160h+var_140], xmm0
0x18001524e  mov     [rbp+160h+var_11C], 746C6664h
0x180015255  mov     [rbp+160h+var_118], 746C6664h
0x18001525c  movzx   edi, word ptr [rdi+rax*8]
0x180015260  xor     eax, eax
0x180015262  cmp     dx, 40h ; '@'
0x180015266  mov     [rbp+160h+var_1B8], rbx
0x18001526a  movzx   edx, cx
0x18001526d  setz    al
0x180015270  mov     [rbp+160h+var_1B0], r11d
0x180015274  mov     [rbp+160h+var_114], eax
0x180015277  mov     ecx, edx
0x180015279  shr     ecx, 1
0x18001527b  mov     eax, edx
0x18001527d  and     eax, 400h
0x180015282  mov     [rbp+160h+var_1AC], r9d
0x180015286  and     ecx, 1800h
0x18001528c  movdqu  xmmword ptr [rbp+160h+ho], xmm0
0x180015291  or      ecx, eax
0x180015293  movdqu  xmmword ptr [rbp+160h+var_190], xmm1
0x180015298  movzx   eax, word ptr [r10+2]
0x18001529d  and     eax, 400h
0x1800152a2  shr     ecx, 0Ah
0x1800152a5  bts     eax, 0Dh
0x1800152a9  mov     [rbp+160h+var_178], 0FFFFFFFFh
0x1800152b0  shr     eax, 7
0x1800152b3  or      ecx, eax
0x1800152b5  mov     [rbp+160h+var_168], r8
0x1800152b9  cmp     edi, 0FFFFh
0x1800152bf  mov     [rbp+160h+var_10C], ecx
0x1800152c2  mov     ecx, 1
0x1800152c7  mov     [rbp+160h+var_154], 0FFFFFFFFh
0x1800152ce  cmovz   edi, ecx
0x1800152d1  mov     [rbp+160h+var_1A8], ecx
0x1800152d4  lea     rax, ??_7CUspShapingDrawingSurface@@6B@; const CUspShapingDrawingSurface::`vftable'
0x1800152db  mov     [rbp+160h+var_120], edi
0x1800152de  xor     r10d, r10d
0x1800152e1  mov     [rbp+160h+var_1C0], rax
0x1800152e5  and     edx, 3FFh
0x1800152eb  mov     [rbp+160h+var_174], r10
0x1800152ef  mov     [rbp+160h+var_158], edx
0x1800152f2  lea     rax, [rbp+160h+var_120]
0x1800152f6  mov     [rbp+160h+var_160], rax
0x1800152fa  test    rbx, rbx
0x1800152fd  jz      loc_18001569E
0x180015303  mov     rcx, rbx; hdc
0x180015306  mov     qword ptr [rbp+160h+pt.x], r10
0x18001530a  call    GetTextAlign
0x18001530f  lea     rdx, [rbp+160h+pt]; lppt
0x180015313  mov     rcx, rbx; hdc
0x180015316  mov     esi, eax
0x180015318  call    GetCurrentPositionEx
0x18001531d  mov     rcx, rbx; hdc
0x180015320  call    GetBkMode
0x180015325  mov     edx, esi
0x180015327  mov     rcx, rbx; hdc
0x18001532a  and     edx, 0FFFFFFF9h
0x18001532d  mov     edi, eax
0x18001532f  or      edx, 1; align
0x180015332  call    cs:__imp_SetTextAlign
0x180015338  mov     edx, 1; mode
0x18001533d  mov     rcx, rbx; hdc
0x180015340  call    cs:__imp_SetBkMode
0x180015346  xor     r9d, r9d; lppt
0x180015349  xor     r8d, r8d; y
0x18001534c  xor     edx, edx; x
0x18001534e  mov     rcx, rbx; hdc
0x180015351  call    cs:__imp_MoveToEx
0x180015357  lea     rax, [rbp+160h+var_1E0]
0x18001535b  xorps   xmm0, xmm0
0x18001535e  mov     [rsp+270h+lpDx], rax; lpDx
0x180015363  mov     r9d, 1004h; options
0x180015369  lea     rax, String; " "
0x180015370  mov     [rsp+270h+c], 1; c
0x180015378  mov     [rsp+270h+lpString], rax; lpString
0x18001537d  xor     r8d, r8d; y
0x180015380  lea     rax, [rbp+160h+rect]
0x180015384  xor     edx, edx; x
0x180015386  mov     rcx, rbx; hdc
0x180015389  mov     [rsp+270h+lprect], rax; lprect
0x18001538e  movdqu  xmmword ptr [rbp+160h+rect.left], xmm0
0x180015393  call    cs:__imp_ExtTextOutW
0x180015399  lea     rdx, [rbp+160h+var_180]; lppt
0x18001539d  mov     rcx, rbx; hdc
0x1800153a0  call    GetCurrentPositionEx
0x1800153a5  cmp     [rbp+160h+var_180.x], 0
0x1800153a9  jz      loc_1800154D1
0x1800153af  mov     r8d, [rbp+160h+pt.y]; y
0x1800153b3  xor     r9d, r9d; lppt
0x1800153b6  mov     edx, [rbp+160h+pt.x]; x
0x1800153b9  mov     rcx, rbx; hdc
0x1800153bc  call    cs:__imp_MoveToEx
0x1800153c2  mov     edx, esi; align
0x1800153c4  mov     rcx, rbx; hdc
0x1800153c7  call    cs:__imp_SetTextAlign
0x1800153cd  cmp     edi, 1
0x1800153d0  jz      short loc_1800153DD
0x1800153d2  mov     edx, edi; mode
0x1800153d4  mov     rcx, rbx; hdc
0x1800153d7  call    cs:__imp_SetBkMode
0x1800153dd  mov     rcx, rbx; hdc
0x1800153e0  call    GetTextAlign
0x1800153e5  mov     edi, [rbp+160h+var_120]
0x1800153e8  xor     r10d, r10d
0x1800153eb  mov     rsi, [rbp+160h+var_148]
0x1800153ef  mov     dword ptr [rbp+160h+var_174+4], eax
0x1800153f2  mov     ecx, [rbp+160h+arg_40]
0x1800153f8  cmp     edi, 17h
0x1800153fb  jz      loc_1800155CB
0x180015401  mov     eax, [rbp+160h+arg_20]
0x180015407  lea     r8, [rbp+160h+var_120]
0x18001540b  mov     [rsp+270h+var_1F0], r10d
0x180015413  lea     rdx, [rbp+160h+var_F0]
0x180015417  mov     [rsp+270h+var_1F8], r10d
0x18001541c  xor     r9d, r9d
0x18001541f  mov     dword ptr [rbp+160h+var_140+8], eax
0x180015422  lea     rax, [rbp+160h+var_140]
0x180015426  mov     [rsp+270h+var_200], rax
0x18001542b  lea     rax, [rbp+160h+var_1C0]
0x18001542f  mov     [rsp+270h+var_208], rax
0x180015434  mov     [rsp+270h+var_210], rsi
0x180015439  mov     [rsp+270h+var_218], r14
0x18001543e  mov     [rsp+270h+var_220], r15
0x180015443  mov     [rsp+270h+var_228], ecx
0x180015447  lea     rcx, [rbp+160h+var_130]
0x18001544b  mov     [rsp+270h+var_230], r10
0x180015450  mov     [rsp+270h+lpDx], r13
0x180015455  mov     [rsp+270h+c], r10d
0x18001545a  mov     [rsp+270h+lpString], r10
0x18001545f  mov     [rsp+270h+lprect], r10
0x180015464  mov     qword ptr [rbp+160h+var_140], r12
0x180015468  call    cs:__imp_ShapingDrawGlyphs
0x18001546e  test    eax, eax
0x180015470  jnz     short loc_1800154B8
0x180015472  cmp     [rbp+160h+ho], 0
0x180015477  lea     rax, ??_7CUspShapingDrawingSurface@@6B@; const CUspShapingDrawingSurface::`vftable'
0x18001547e  mov     [rbp+160h+var_1C0], rax
0x180015482  jnz     loc_1800156B6
0x180015488  cmp     [rbp+160h+var_190], 0
0x18001548d  jnz     loc_1800156D3
0x180015493  xor     eax, eax
0x180015495  mov     rcx, [rbp+160h+var_50]
0x18001549c  xor     rcx, rsp; StackCookie
0x18001549f  call    __security_check_cookie
0x1800154a4  add     rsp, 238h
0x1800154ab  pop     r15
0x1800154ad  pop     r14
0x1800154af  pop     r13
0x1800154b1  pop     r12
0x1800154b3  pop     rdi
0x1800154b4  pop     rsi
0x1800154b5  pop     rbx
0x1800154b6  pop     rbp
0x1800154b7  retn
0x1800154b8  lea     rcx, [rbp+160h+var_1C0]; this
0x1800154bc  cmp     eax, 0FFFFFFFEh
0x1800154bf  jnz     loc_1800155E5
0x1800154c5  call    ??1CUspShapingDrawingSurface@@QEAA@XZ; CUspShapingDrawingSurface::~CUspShapingDrawingSurface(void)
0x1800154ca  mov     eax, 8007000Eh
0x1800154cf  jmp     short loc_180015495
0x1800154d1  cmp     [rbp+160h+var_180.y], 0
0x1800154d5  jnz     loc_1800153AF
0x1800154db  mov     eax, [rbp+160h+var_1E0]
0x1800154de  mov     edx, 0A0000h
0x1800154e3  mov     rcx, rbx
0x1800154e6  mov     [rbp+160h+var_180.x], eax
0x1800154e9  call    GetDCObject
0x1800154ee  mov     [rbp+160h+h], rax
0x1800154f2  test    rax, rax
0x1800154f5  jz      loc_1800153AF
0x1800154fb  mov     rcx, rbx; hdc
0x1800154fe  call    CreateCompatibleDC
0x180015503  mov     [rbp+160h+hdc], rax
0x180015507  test    rax, rax
0x18001550a  jz      loc_1800153AF
0x180015510  mov     rdx, [rbp+160h+h]; h
0x180015514  mov     rcx, rax; hdc
0x180015517  call    cs:__imp_SelectObject
0x18001551d  mov     rcx, rbx; hdc
0x180015520  call    GetGraphicsMode
0x180015525  cmp     eax, 2
0x180015528  jz      loc_180015676
0x18001552e  mov     rcx, [rbp+160h+hdc]; hdc
0x180015532  call    GetTextAlign
0x180015537  mov     rcx, [rbp+160h+hdc]; hdc
0x18001553b  and     eax, 0FFFFFFF9h
0x18001553e  or      eax, 1
0x180015541  mov     edx, eax; align
0x180015543  call    cs:__imp_SetTextAlign
0x180015549  mov     rcx, [rbp+160h+hdc]; hdc
0x18001554d  mov     edx, 1; mode
0x180015552  call    cs:__imp_SetBkMode
0x180015558  mov     rcx, [rbp+160h+hdc]; hdc
0x18001555c  xor     r9d, r9d; lppt
0x18001555f  xor     r8d, r8d; y
0x180015562  xor     edx, edx; x
0x180015564  call    cs:__imp_MoveToEx
0x18001556a  mov     rcx, [rbp+160h+hdc]; hdc
0x18001556e  lea     rax, [rbp+160h+var_1E0]
0x180015572  mov     [rsp+270h+lpDx], rax; lpDx
0x180015577  mov     r9d, 1000h; options
0x18001557d  lea     rax, String; " "
0x180015584  mov     [rsp+270h+c], 1; c
0x18001558c  mov     [rsp+270h+lpString], rax; lpString
0x180015591  xor     r8d, r8d; y
0x180015594  lea     rax, [rbp+160h+rect]
0x180015598  xor     edx, edx; x
0x18001559a  mov     [rsp+270h+lprect], rax; lprect
0x18001559f  call    cs:__imp_ExtTextOutW
0x1800155a5  mov     rcx, [rbp+160h+hdc]; hdc
0x1800155a9  lea     rdx, [rbp+160h+var_180]; lppt
0x1800155ad  call    GetCurrentPositionEx
0x1800155b2  cmp     [rbp+160h+var_180.x], 0
0x1800155b6  jz      loc_180015689
0x1800155bc  mov     rcx, [rbp+160h+hdc]; hdc
0x1800155c0  call    cs:__imp_DeleteDC
0x1800155c6  jmp     loc_1800153AF
0x1800155cb  test    r14, r14
0x1800155ce  mov     r8, r14
0x1800155d1  mov     r9d, r10d
0x1800155d4  cmovz   r8, r15
0x1800155d8  test    ecx, ecx
0x1800155da  jg      short loc_180015604
0x1800155dc  mov     [rbp+160h+var_154], r9d
0x1800155e0  jmp     loc_180015401
0x1800155e5  cmp     [rbp+160h+var_D8], 8000000Ah
0x1800155ef  jnz     loc_1800156A7
0x1800155f5  call    ??1CUspShapingDrawingSurface@@QEAA@XZ; CUspShapingDrawingSurface::~CUspShapingDrawingSurface(void)
0x1800155fa  mov     eax, 8000000Ah
0x1800155ff  jmp     loc_180015495
0x180015604  mov     edx, r10d
0x180015607  cmp     ecx, 8
0x18001560a  jb      short loc_180015664
0x18001560c  mov     r9d, ecx
0x18001560f  xorps   xmm2, xmm2
0x180015612  and     r9d, 0FFFFFFF8h
0x180015616  xorps   xmm1, xmm1
0x180015619  movsxd  rax, edx
0x18001561c  add     edx, 8
0x18001561f  movdqu  xmm0, xmmword ptr [r8+rax*4]
0x180015625  paddd   xmm2, xmm0
0x180015629  movdqu  xmm0, xmmword ptr [r8+rax*4+10h]
0x180015630  paddd   xmm1, xmm0
0x180015634  cmp     edx, r9d
0x180015637  jl      short loc_180015619
0x180015639  paddd   xmm1, xmm2
0x18001563d  movdqa  xmm0, xmm1
0x180015641  psrldq  xmm0, 8
0x180015646  paddd   xmm1, xmm0
0x18001564a  movdqa  xmm0, xmm1
0x18001564e  psrldq  xmm0, 4
0x180015653  paddd   xmm1, xmm0
0x180015657  movd    r9d, xmm1
0x18001565c  cmp     edx, ecx
0x18001565e  jge     loc_1800155DC
0x180015664  movsxd  rax, edx
0x180015667  inc     edx
0x180015669  add     r9d, [r8+rax*4]
  ... truncated ...
```
