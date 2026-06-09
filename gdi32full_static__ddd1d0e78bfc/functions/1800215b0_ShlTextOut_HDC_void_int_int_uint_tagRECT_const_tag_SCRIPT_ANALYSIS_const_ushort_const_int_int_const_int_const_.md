# ShlTextOut(HDC__ *,void * *,int,int,uint,tagRECT const *,tag_SCRIPT_ANALYSIS const *,ushort const *,int,int const *,int const *,tagGOFFSET const *)

- ea: `0x1800215b0`
- end: `0x180021b7d`
- name: `?ShlTextOut@@YAJPEAUHDC__@@PEAPEAXHHIPEBUtagRECT@@PEBUtag_SCRIPT_ANALYSIS@@PEBGHPEBH5PEBUtagGOFFSET@@@Z`
- size: `1485`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, void **@<rdx>, int@<r8d>, int@<r9d>, unsigned int, const struct tagRECT *, const struct tag_SCRIPT_ANALYSIS *, const unsigned __int16 *, int, const int *, const int *, const struct tagGOFFSET *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180020a90`

## callees

- `0x180006a28`
- `0x1800200a0`
- `0x180020224`
- `0x1800209d0`
- `0x1800215b0`
- `0x180021e50`
- `0x180022b20`
- `0x18002ade0`
- `0x180032f20`
- `0x18007f800`

## import_xrefs

- `GDI32!DeleteDC` at `0x180021a2f`
- `GDI32!DeleteDC` at `0x180021a2f`
- `GDI32!ExtTextOutW` at `0x1800217c5`
- `GDI32!ExtTextOutW` at `0x180021a08`
- `GDI32!ExtTextOutW` at `0x1800217c5`
- `GDI32!ExtTextOutW` at `0x180021a08`
- `GDI32!MoveToEx` at `0x18002177d`
- `GDI32!MoveToEx` at `0x1800217f4`
- `GDI32!MoveToEx` at `0x1800219c7`
- `GDI32!MoveToEx` at `0x18002177d`
- `GDI32!MoveToEx` at `0x1800217f4`
- `GDI32!MoveToEx` at `0x1800219c7`
- `GDI32!SelectObject` at `0x180021968`
- `GDI32!SelectObject` at `0x180021b33`
- `GDI32!SelectObject` at `0x180021b5c`
- `GDI32!SelectObject` at `0x180021968`
- `GDI32!SelectObject` at `0x180021b33`
- `GDI32!SelectObject` at `0x180021b5c`
- `GDI32!SetBkMode` at `0x180021766`
- `GDI32!SetBkMode` at `0x18002181b`
- `GDI32!SetBkMode` at `0x1800219af`
- `GDI32!SetBkMode` at `0x180021766`
- `GDI32!SetBkMode` at `0x18002181b`
- `GDI32!SetBkMode` at `0x1800219af`
- `GDI32!SetTextAlign` at `0x180021752`
- `GDI32!SetTextAlign` at `0x180021805`
- `GDI32!SetTextAlign` at `0x18002199a`
- `GDI32!SetTextAlign` at `0x180021752`
- `GDI32!SetTextAlign` at `0x180021805`
- `GDI32!SetTextAlign` at `0x18002199a`
- `GDI32!DeleteObject` at `0x180021b43`
- `GDI32!DeleteObject` at `0x180021b6c`
- `GDI32!DeleteObject` at `0x180021b43`
- `GDI32!DeleteObject` at `0x180021b6c`
- `TextShaping!ShapingDrawGlyphs` at `0x1800218b2`
- `TextShaping!ShapingDrawGlyphs` at `0x1800218b2`

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
0x1800215b0  push    rbp
0x1800215b2  push    rbx
0x1800215b3  push    rsi
0x1800215b4  push    rdi
0x1800215b5  push    r12
0x1800215b7  push    r13
0x1800215b9  push    r14
0x1800215bb  push    r15
0x1800215bd  lea     rbp, [rsp-128h]
0x1800215c5  sub     rsp, 238h
0x1800215cc  mov     rax, cs:__security_cookie
0x1800215d3  xor     rax, rsp
0x1800215d6  mov     [rbp+160h+var_50], rax
0x1800215dd  mov     r10, [rbp+160h+arg_30]
0x1800215e4  lea     rdi, ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport
0x1800215eb  mov     rsi, [rbp+160h+arg_58]
0x1800215f2  mov     rbx, rcx
0x1800215f5  mov     r14, [rbp+160h+arg_50]
0x1800215fc  xor     ecx, ecx
0x1800215fe  mov     r15, [rbp+160h+arg_48]
0x180021605  mov     r11d, r8d
0x180021608  mov     r8, [rdx]
0x18002160b  xorps   xmm0, xmm0
0x18002160e  mov     r12, [rbp+160h+arg_28]
0x180021615  xorps   xmm1, xmm1
0x180021618  mov     r13, [rbp+160h+arg_38]
0x18002161f  mov     [rbp+160h+var_148], rsi
0x180021623  mov     rax, [r8+50h]
0x180021627  mov     [rbp+160h+var_1E0], 3E8h
0x18002162e  movzx   edx, word ptr [rax+14h]
0x180021632  lea     rax, ??_7CUspShapingClient@@6B@; const CUspShapingClient::`vftable'
0x180021639  mov     [rbp+160h+var_130], rax
0x18002163d  lea     rax, ??_7CUspShapingFont@@6B@; const CUspShapingFont::`vftable'
0x180021644  mov     [rbp+160h+var_F0], rax
0x180021648  mov     [rbp+160h+var_128], ecx
0x18002164b  mov     [rbp+160h+var_D8], ecx
0x180021651  mov     [rbp+160h+var_110], ecx
0x180021654  movzx   ecx, word ptr [r10]
0x180021658  mov     eax, ecx
0x18002165a  mov     [rbp+160h+var_E8], rbx
0x18002165e  and     eax, 3FFh
0x180021663  mov     [rbp+160h+var_E0], r8
0x18002166a  movups  [rbp+160h+var_140], xmm0
0x18002166e  mov     [rbp+160h+var_11C], 746C6664h
0x180021675  mov     [rbp+160h+var_118], 746C6664h
0x18002167c  movzx   edi, word ptr [rdi+rax*8]
0x180021680  xor     eax, eax
0x180021682  cmp     dx, 40h ; '@'
0x180021686  mov     [rbp+160h+var_1B8], rbx
0x18002168a  movzx   edx, cx
0x18002168d  setz    al
0x180021690  mov     [rbp+160h+var_1B0], r11d
0x180021694  mov     [rbp+160h+var_114], eax
0x180021697  mov     ecx, edx
0x180021699  shr     ecx, 1
0x18002169b  mov     eax, edx
0x18002169d  and     eax, 400h
0x1800216a2  mov     [rbp+160h+var_1AC], r9d
0x1800216a6  and     ecx, 1800h
0x1800216ac  movdqu  xmmword ptr [rbp+160h+ho], xmm0
0x1800216b1  or      ecx, eax
0x1800216b3  movdqu  xmmword ptr [rbp+160h+var_190], xmm1
0x1800216b8  movzx   eax, word ptr [r10+2]
0x1800216bd  and     eax, 400h
0x1800216c2  shr     ecx, 0Ah
0x1800216c5  bts     eax, 0Dh
0x1800216c9  mov     [rbp+160h+var_178], 0FFFFFFFFh
0x1800216d0  shr     eax, 7
0x1800216d3  or      ecx, eax
0x1800216d5  mov     [rbp+160h+var_168], r8
0x1800216d9  cmp     edi, 0FFFFh
0x1800216df  mov     [rbp+160h+var_10C], ecx
0x1800216e2  mov     ecx, 1
0x1800216e7  mov     [rbp+160h+var_154], 0FFFFFFFFh
0x1800216ee  cmovz   edi, ecx
0x1800216f1  mov     [rbp+160h+var_1A8], ecx
0x1800216f4  lea     rax, ??_7CUspShapingDrawingSurface@@6B@; const CUspShapingDrawingSurface::`vftable'
0x1800216fb  mov     [rbp+160h+var_120], edi
0x1800216fe  xor     r10d, r10d
0x180021701  mov     [rbp+160h+var_1C0], rax
0x180021705  and     edx, 3FFh
0x18002170b  mov     [rbp+160h+var_174], r10
0x18002170f  mov     [rbp+160h+var_158], edx
0x180021712  lea     rax, [rbp+160h+var_120]
0x180021716  mov     [rbp+160h+var_160], rax
0x18002171a  test    rbx, rbx
0x18002171d  jz      loc_180021B13
0x180021723  mov     rcx, rbx; hdc
0x180021726  mov     qword ptr [rbp+160h+pt.x], r10
0x18002172a  call    GetTextAlign
0x18002172f  lea     rdx, [rbp+160h+pt]; lppt
0x180021733  mov     rcx, rbx; hdc
0x180021736  mov     esi, eax
0x180021738  call    GetCurrentPositionEx
0x18002173d  mov     rcx, rbx; hdc
0x180021740  call    GetBkMode
0x180021745  mov     edx, esi
0x180021747  mov     rcx, rbx; hdc
0x18002174a  and     edx, 0FFFFFFF9h
0x18002174d  mov     edi, eax
0x18002174f  or      edx, 1; align
0x180021752  call    cs:__imp_SetTextAlign
0x180021759  nop     dword ptr [rax+rax+00h]
0x18002175e  mov     edx, 1; mode
0x180021763  mov     rcx, rbx; hdc
0x180021766  call    cs:__imp_SetBkMode
0x18002176d  nop     dword ptr [rax+rax+00h]
0x180021772  xor     r9d, r9d; lppt
0x180021775  xor     r8d, r8d; y
0x180021778  xor     edx, edx; x
0x18002177a  mov     rcx, rbx; hdc
0x18002177d  call    cs:__imp_MoveToEx
0x180021784  nop     dword ptr [rax+rax+00h]
0x180021789  lea     rax, [rbp+160h+var_1E0]
0x18002178d  xorps   xmm0, xmm0
0x180021790  mov     [rsp+270h+lpDx], rax; lpDx
0x180021795  mov     r9d, 1004h; options
0x18002179b  lea     rax, String; " "
0x1800217a2  mov     [rsp+270h+c], 1; c
0x1800217aa  mov     [rsp+270h+lpString], rax; lpString
0x1800217af  xor     r8d, r8d; y
0x1800217b2  lea     rax, [rbp+160h+rect]
0x1800217b6  xor     edx, edx; x
0x1800217b8  mov     rcx, rbx; hdc
0x1800217bb  mov     [rsp+270h+lprect], rax; lprect
0x1800217c0  movdqu  xmmword ptr [rbp+160h+rect.left], xmm0
0x1800217c5  call    cs:__imp_ExtTextOutW
0x1800217cc  nop     dword ptr [rax+rax+00h]
0x1800217d1  lea     rdx, [rbp+160h+var_180]; lppt
0x1800217d5  mov     rcx, rbx; hdc
0x1800217d8  call    GetCurrentPositionEx
0x1800217dd  cmp     [rbp+160h+var_180.x], 0
0x1800217e1  jz      loc_180021922
0x1800217e7  mov     r8d, [rbp+160h+pt.y]; y
0x1800217eb  xor     r9d, r9d; lppt
0x1800217ee  mov     edx, [rbp+160h+pt.x]; x
0x1800217f1  mov     rcx, rbx; hdc
0x1800217f4  call    cs:__imp_MoveToEx
0x1800217fb  nop     dword ptr [rax+rax+00h]
0x180021800  mov     edx, esi; align
0x180021802  mov     rcx, rbx; hdc
0x180021805  call    cs:__imp_SetTextAlign
0x18002180c  nop     dword ptr [rax+rax+00h]
0x180021811  cmp     edi, 1
0x180021814  jz      short loc_180021827
0x180021816  mov     edx, edi; mode
0x180021818  mov     rcx, rbx; hdc
0x18002181b  call    cs:__imp_SetBkMode
0x180021822  nop     dword ptr [rax+rax+00h]
0x180021827  mov     rcx, rbx; hdc
0x18002182a  call    GetTextAlign
0x18002182f  mov     edi, [rbp+160h+var_120]
0x180021832  xor     r10d, r10d
0x180021835  mov     rsi, [rbp+160h+var_148]
0x180021839  mov     dword ptr [rbp+160h+var_174+4], eax
0x18002183c  mov     ecx, [rbp+160h+arg_40]
0x180021842  cmp     edi, 17h
0x180021845  jz      loc_180021A40
0x18002184b  mov     eax, [rbp+160h+arg_20]
0x180021851  lea     r8, [rbp+160h+var_120]
0x180021855  mov     [rsp+270h+var_1F0], r10d
0x18002185d  lea     rdx, [rbp+160h+var_F0]
0x180021861  mov     [rsp+270h+var_1F8], r10d
0x180021866  xor     r9d, r9d
0x180021869  mov     dword ptr [rbp+160h+var_140+8], eax
0x18002186c  lea     rax, [rbp+160h+var_140]
0x180021870  mov     [rsp+270h+var_200], rax
0x180021875  lea     rax, [rbp+160h+var_1C0]
0x180021879  mov     [rsp+270h+var_208], rax
0x18002187e  mov     [rsp+270h+var_210], rsi
0x180021883  mov     [rsp+270h+var_218], r14
0x180021888  mov     [rsp+270h+var_220], r15
0x18002188d  mov     [rsp+270h+var_228], ecx
0x180021891  lea     rcx, [rbp+160h+var_130]
0x180021895  mov     [rsp+270h+var_230], r10
0x18002189a  mov     [rsp+270h+lpDx], r13
0x18002189f  mov     [rsp+270h+c], r10d
0x1800218a4  mov     [rsp+270h+lpString], r10
0x1800218a9  mov     [rsp+270h+lprect], r10
0x1800218ae  mov     qword ptr [rbp+160h+var_140], r12
0x1800218b2  call    cs:__imp_ShapingDrawGlyphs
0x1800218b9  nop     dword ptr [rax+rax+00h]
0x1800218be  test    eax, eax
0x1800218c0  jnz     short loc_180021909
0x1800218c2  cmp     [rbp+160h+ho], 0
0x1800218c7  lea     rax, ??_7CUspShapingDrawingSurface@@6B@; const CUspShapingDrawingSurface::`vftable'
0x1800218ce  mov     [rbp+160h+var_1C0], rax
0x1800218d2  jnz     loc_180021B2B
0x1800218d8  cmp     [rbp+160h+var_190], 0
0x1800218dd  jnz     loc_180021B54
0x1800218e3  xor     eax, eax
0x1800218e5  mov     rcx, [rbp+160h+var_50]
0x1800218ec  xor     rcx, rsp; StackCookie
0x1800218ef  call    __security_check_cookie
0x1800218f4  add     rsp, 238h
0x1800218fb  pop     r15
0x1800218fd  pop     r14
0x1800218ff  pop     r13
0x180021901  pop     r12
0x180021903  pop     rdi
0x180021904  pop     rsi
0x180021905  pop     rbx
0x180021906  pop     rbp
0x180021907  retn
0x180021909  lea     rcx, [rbp+160h+var_1C0]; this
0x18002190d  cmp     eax, 0FFFFFFFEh
0x180021910  jnz     loc_180021A5A
0x180021916  call    ??1CUspShapingDrawingSurface@@QEAA@XZ; CUspShapingDrawingSurface::~CUspShapingDrawingSurface(void)
0x18002191b  mov     eax, 8007000Eh
0x180021920  jmp     short loc_1800218E5
0x180021922  cmp     [rbp+160h+var_180.y], 0
0x180021926  jnz     loc_1800217E7
0x18002192c  mov     eax, [rbp+160h+var_1E0]
0x18002192f  mov     edx, 0A0000h
0x180021934  mov     rcx, rbx
0x180021937  mov     [rbp+160h+var_180.x], eax
0x18002193a  call    GetDCObject
0x18002193f  mov     [rbp+160h+h], rax
0x180021943  test    rax, rax
0x180021946  jz      loc_1800217E7
0x18002194c  mov     rcx, rbx; hdc
0x18002194f  call    CreateCompatibleDC
0x180021954  mov     [rbp+160h+hdc], rax
0x180021958  test    rax, rax
0x18002195b  jz      loc_1800217E7
0x180021961  mov     rdx, [rbp+160h+h]; h
0x180021965  mov     rcx, rax; hdc
0x180021968  call    cs:__imp_SelectObject
0x18002196f  nop     dword ptr [rax+rax+00h]
0x180021974  mov     rcx, rbx; hdc
0x180021977  call    GetGraphicsMode
0x18002197c  cmp     eax, 2
0x18002197f  jz      loc_180021AEB
0x180021985  mov     rcx, [rbp+160h+hdc]; hdc
0x180021989  call    GetTextAlign
0x18002198e  mov     rcx, [rbp+160h+hdc]; hdc
0x180021992  and     eax, 0FFFFFFF9h
0x180021995  or      eax, 1
0x180021998  mov     edx, eax; align
0x18002199a  call    cs:__imp_SetTextAlign
0x1800219a1  nop     dword ptr [rax+rax+00h]
0x1800219a6  mov     rcx, [rbp+160h+hdc]; hdc
0x1800219aa  mov     edx, 1; mode
0x1800219af  call    cs:__imp_SetBkMode
0x1800219b6  nop     dword ptr [rax+rax+00h]
0x1800219bb  mov     rcx, [rbp+160h+hdc]; hdc
0x1800219bf  xor     r9d, r9d; lppt
0x1800219c2  xor     r8d, r8d; y
0x1800219c5  xor     edx, edx; x
0x1800219c7  call    cs:__imp_MoveToEx
0x1800219ce  nop     dword ptr [rax+rax+00h]
0x1800219d3  mov     rcx, [rbp+160h+hdc]; hdc
0x1800219d7  lea     rax, [rbp+160h+var_1E0]
0x1800219db  mov     [rsp+270h+lpDx], rax; lpDx
0x1800219e0  mov     r9d, 1000h; options
0x1800219e6  lea     rax, String; " "
0x1800219ed  mov     [rsp+270h+c], 1; c
0x1800219f5  mov     [rsp+270h+lpString], rax; lpString
0x1800219fa  xor     r8d, r8d; y
0x1800219fd  lea     rax, [rbp+160h+rect]
0x180021a01  xor     edx, edx; x
0x180021a03  mov     [rsp+270h+lprect], rax; lprect
0x180021a08  call    cs:__imp_ExtTextOutW
0x180021a0f  nop     dword ptr [rax+rax+00h]
0x180021a14  mov     rcx, [rbp+160h+hdc]; hdc
0x180021a18  lea     rdx, [rbp+160h+var_180]; lppt
0x180021a1c  call    GetCurrentPositionEx
0x180021a21  cmp     [rbp+160h+var_180.x], 0
0x180021a25  jz      loc_180021AFE
0x180021a2b  mov     rcx, [rbp+160h+hdc]; hdc
0x180021a2f  call    cs:__imp_DeleteDC
0x180021a36  nop     dword ptr [rax+rax+00h]
0x180021a3b  jmp     loc_1800217E7
0x180021a40  test    r14, r14
0x180021a43  mov     r8, r14
0x180021a46  mov     r9d, r10d
0x180021a49  cmovz   r8, r15
0x180021a4d  test    ecx, ecx
0x180021a4f  jg      short loc_180021A79
0x180021a51  mov     [rbp+160h+var_154], r9d
0x180021a55  jmp     loc_18002184B
0x180021a5a  cmp     [rbp+160h+var_D8], 8000000Ah
0x180021a64  jnz     loc_180021B1C
0x180021a6a  call    ??1CUspShapingDrawingSurface@@QEAA@XZ; CUspShapingDrawingSurface::~CUspShapingDrawingSurface(void)
0x180021a6f  mov     eax, 8000000Ah
0x180021a74  jmp     loc_1800218E5
0x180021a79  mov     edx, r10d
0x180021a7c  cmp     ecx, 8
0x180021a7f  jb      short loc_180021AD9
0x180021a81  mov     r9d, ecx
0x180021a84  xorps   xmm2, xmm2
0x180021a87  and     r9d, 0FFFFFFF8h
0x180021a8b  xorps   xmm1, xmm1
0x180021a8e  movsxd  rax, edx
0x180021a91  add     edx, 8
0x180021a94  movdqu  xmm0, xmmword ptr [r8+rax*4]
0x180021a9a  paddd   xmm2, xmm0
0x180021a9e  movdqu  xmm0, xmmword ptr [r8+rax*4+10h]
0x180021aa5  paddd   xmm1, xmm0
0x180021aa9  cmp     edx, r9d
  ... truncated ...
```
