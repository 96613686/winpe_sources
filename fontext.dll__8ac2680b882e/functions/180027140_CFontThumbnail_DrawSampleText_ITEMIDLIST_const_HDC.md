# CFontThumbnail::_DrawSampleText(_ITEMIDLIST const *,HDC__ *)

- ea: `0x180027140`
- end: `0x1800274a7`
- name: `?_DrawSampleText@CFontThumbnail@@AEAAJPEFBU_ITEMIDLIST@@PEAUHDC__@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(CFontThumbnail *__hidden this, const struct _ITEMIDLIST *, HDC hdc)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180028198`

## callees

- `0x180002ee8`
- `0x1800229f8`
- `0x180027140`
- `0x1800274b0`
- `0x180027738`
- `0x180027cf4`
- `0x180027e58`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `GDI32!DeleteObject` at `0x180027302`
- `GDI32!DeleteObject` at `0x180027392`
- `GDI32!DeleteObject` at `0x180027472`
- `GDI32!DeleteObject` at `0x180027302`
- `GDI32!DeleteObject` at `0x180027392`
- `GDI32!DeleteObject` at `0x180027472`
- `GDI32!GetDeviceCaps` at `0x180027237`
- `GDI32!GetDeviceCaps` at `0x180027237`
- `GDI32!CreateFontIndirectW` at `0x18002725d`
- `GDI32!CreateFontIndirectW` at `0x18002725d`
- `GDI32!SelectObject` at `0x180027271`
- `GDI32!SelectObject` at `0x1800272f9`
- `GDI32!SelectObject` at `0x180027389`
- `GDI32!SelectObject` at `0x180027469`
- `GDI32!SelectObject` at `0x180027271`
- `GDI32!SelectObject` at `0x1800272f9`
- `GDI32!SelectObject` at `0x180027389`
- `GDI32!SelectObject` at `0x180027469`
- `GDI32!GetTextExtentPoint32W` at `0x1800272aa`
- `GDI32!GetTextExtentPoint32W` at `0x1800272aa`
- `GDI32!GetTextExtentPointI` at `0x180027298`
- `GDI32!GetTextExtentPointI` at `0x180027298`
- `GDI32!GetTextExtentExPointI` at `0x180027357`
- `GDI32!GetTextExtentExPointI` at `0x180027357`
- `GDI32!GetTextExtentExPointW` at `0x180027369`
- `GDI32!GetTextExtentExPointW` at `0x180027369`
- `GDI32!GetGlyphIndicesW` at `0x180027416`
- `GDI32!GetGlyphIndicesW` at `0x180027416`
- `KERNEL32!MulDiv` at `0x180027248`
- `KERNEL32!MulDiv` at `0x180027248`

## pseudocode

```c
__int64 __fastcall CFontThumbnail::_DrawSampleText(CFontThumbnail *this, const struct _ITEMIDLIST *a2, HDC hdc)
{
  int LogFontInfo; // eax
  unsigned int v7; // r12d
  int v8; // r14d
  int DeviceCaps; // eax
  int v10; // eax
  HFONT v11; // rax
  HFONT v12; // r15
  HGDIOBJ v13; // r13
  LONG cy; // ecx
  double v16; // xmm1_8
  int v17; // ebx
  int v18; // eax
  BOOL TextExtent; // eax
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // r8
  DWORD GlyphIndicesW; // eax
  int v25; // eax
  unsigned int lpnDx; // [rsp+28h] [rbp-D8h]
  int nFit; // [rsp+40h] [rbp-C0h] BYREF
  int nMaxExtent; // [rsp+44h] [rbp-BCh]
  int v30; // [rsp+48h] [rbp-B8h]
  struct tagSIZE psize; // [rsp+50h] [rbp-B0h] BYREF
  struct tagSIZE Size; // [rsp+58h] [rbp-A8h] BYREF
  struct tagRECT v33; // [rsp+60h] [rbp-A0h] BYREF
  LOGFONTW lf; // [rsp+70h] [rbp-90h] BYREF
  WCHAR String[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v36; // [rsp+E0h] [rbp-20h]
  __int128 v37; // [rsp+F0h] [rbp-10h]
  WORD pgi[24]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(&lf, 0, sizeof(lf));
  LogFontInfo = FID_GetLogFontInfo(a2, &lf);
  lf.lfCharSet = 1;
  lf.lfQuality = 0;
  v7 = LogFontInfo;
  if ( LogFontInfo >= 0 )
  {
    v7 = -2147467259;
    v33 = 0;
    *(_OWORD *)String = 0;
    v36 = 0;
    v37 = 0;
    CFontThumbnail::_GetSampleRect(this, a2, &v33);
    nMaxExtent = v33.right - v33.left;
    v30 = v33.bottom - v33.top;
    v8 = (v33.bottom - v33.top) / 2;
    CFontThumbnail::_GetSampleText(this, hdc, a2, &lf, String, lpnDx);
    while ( 1 )
    {
      do
      {
        if ( v8 <= 0 )
          return v7;
        psize = 0;
        DeviceCaps = GetDeviceCaps(hdc, 90);
        v10 = MulDiv(v8, DeviceCaps, 72);
        lf.lfWidth = 0;
        lf.lfHeight = -v10;
        v11 = CreateFontIndirectW(&lf);
        v12 = v11;
      }
      while ( !v11 );
      v13 = SelectObject(hdc, v11);
      if ( !(*((_DWORD *)this + 279)
           ? GetTextExtentPointI(hdc, (LPWORD)this + 560, *((_DWORD *)this + 282), &psize)
           : GetTextExtentPoint32W(hdc, String, 24, &psize)) )
        break;
      cy = 1;
      if ( psize.cy )
        cy = psize.cy;
      v16 = (double)v30 / (double)cy;
      if ( v16 >= 1.0 )
      {
        nFit = 0;
        Size = 0;
        if ( *((_DWORD *)this + 279) )
          TextExtent = GetTextExtentExPointI(
                         hdc,
                         (LPWORD)this + 560,
                         *((_DWORD *)this + 282),
                         nMaxExtent,
                         &nFit,
                         0,
                         &Size);
        else
          TextExtent = GetTextExtentExPointW(hdc, String, 24, nMaxExtent, &nFit, 0, &Size);
        if ( !TextExtent )
          goto LABEL_42;
        if ( nFit )
        {
          v20 = *((unsigned int *)this + 279);
          v21 = -1;
          if ( !(_DWORD)v20 )
          {
            v22 = -1;
            do
              ++v22;
            while ( String[v22] );
            if ( nFit < (int)v22 )
            {
              if ( (unsigned __int64)(2LL * nFit) >= 0x30 )
                _report_rangecheckfailure(2LL * nFit, v20, String);
              String[nFit] = 0;
              goto LABEL_33;
            }
          }
          if ( nFit < *((_DWORD *)this + 282) )
            *((_DWORD *)this + 282) = nFit;
          if ( (_DWORD)v20 )
          {
            v25 = CFontThumbnail::_GlyphDrawSampleTextInRect(this, hdc, &v33);
LABEL_41:
            v7 = v25;
          }
          else
          {
LABEL_33:
            v23 = -1;
            do
              ++v23;
            while ( String[v23] );
            GlyphIndicesW = GetGlyphIndicesW(hdc, String, v23, pgi, 1u);
            if ( GlyphIndicesW != -1 )
            {
              do
                ++v21;
              while ( String[v21] );
              if ( v21 == GlyphIndicesW )
              {
                v25 = CFontThumbnail::_DrawSampleTextInRect((CFontThumbnail *)String, hdc, String, &v33);
                goto LABEL_41;
              }
            }
            String[0] = 0;
          }
LABEL_42:
          SelectObject(hdc, v13);
          DeleteObject(v12);
          return v7;
        }
        --v8;
LABEL_21:
        SelectObject(hdc, v13);
        DeleteObject(v12);
      }
      else
      {
        v17 = (int)((double)v8 * v16);
        SelectObject(hdc, v13);
        DeleteObject(v12);
        v18 = v8;
        v8 = v17 - 1;
        if ( v17 != v18 )
          v8 = v17;
      }
    }
    v8 = 0;
    goto LABEL_21;
  }
  return v7;
}

```

## disassembly

```asm
0x180027140  mov     rax, rsp
0x180027143  mov     [rax+20h], rbx
0x180027147  push    rbp
0x180027148  push    rsi
0x180027149  push    rdi
0x18002714a  push    r12
0x18002714c  push    r13
0x18002714e  push    r14
0x180027150  push    r15
0x180027152  lea     rbp, [rsp-50h]
0x180027157  sub     rsp, 150h
0x18002715e  movaps  xmmword ptr [rax-48h], xmm6
0x180027162  mov     rax, cs:__security_cookie
0x180027169  xor     rax, rsp
0x18002716c  mov     [rbp+80h+var_50], rax
0x180027170  mov     rbx, rdx
0x180027173  mov     rdi, r8
0x180027176  xor     edx, edx; Val
0x180027178  mov     rsi, rcx
0x18002717b  lea     rcx, [rsp+180h+lf]; void *
0x180027180  lea     r8d, [rdx+5Ch]; Size
0x180027184  call    memset_0
0x180027189  lea     rdx, [rsp+180h+lf]; struct tagLOGFONTW *
0x18002718e  mov     rcx, rbx; struct _ITEMIDLIST *
0x180027191  call    ?FID_GetLogFontInfo@@YAJPEFBU_ITEMIDLIST@@PEAUtagLOGFONTW@@@Z; FID_GetLogFontInfo(_ITEMIDLIST const *,tagLOGFONTW *)
0x180027196  xor     r14d, r14d
0x180027199  mov     [rbp+80h+lf.lfCharSet], 1
0x18002719d  mov     [rbp+80h+lf.lfQuality], r14b
0x1800271a1  mov     r12d, eax
0x1800271a4  test    eax, eax
0x1800271a6  js      loc_180027478
0x1800271ac  xorps   xmm1, xmm1
0x1800271af  lea     r8, [rsp+180h+var_120]; struct tagRECT *
0x1800271b4  xorps   xmm0, xmm0
0x1800271b7  mov     rdx, rbx; struct _ITEMIDLIST *
0x1800271ba  mov     rcx, rsi; this
0x1800271bd  mov     r12d, 80004005h
0x1800271c3  movups  xmmword ptr [rsp+180h+var_120.left], xmm0
0x1800271c8  movups  xmmword ptr [rbp+80h+String], xmm1
0x1800271cc  movups  [rbp+80h+var_A0], xmm1
0x1800271d0  movups  [rbp+80h+var_90], xmm1
0x1800271d4  call    ?_GetSampleRect@CFontThumbnail@@AEAAXPEFBU_ITEMIDLIST@@PEAUtagRECT@@@Z; CFontThumbnail::_GetSampleRect(_ITEMIDLIST const *,tagRECT *)
0x1800271d9  mov     eax, [rsp+180h+var_120.right]
0x1800271dd  lea     ecx, [r14+2]
0x1800271e1  sub     eax, [rsp+180h+var_120.left]
0x1800271e5  lea     r9, [rsp+180h+lf]; lplf
0x1800271ea  mov     [rsp+180h+nMaxExtent], eax
0x1800271ee  mov     r8, rbx; struct _ITEMIDLIST *
0x1800271f1  mov     eax, [rsp+180h+var_120.bottom]
0x1800271f5  sub     eax, [rsp+180h+var_120.top]
0x1800271f9  mov     [rsp+180h+var_138], eax
0x1800271fd  cdq
0x1800271fe  idiv    ecx
0x180027200  mov     rdx, rdi; hdc
0x180027203  mov     rcx, rsi; this
0x180027206  mov     r14d, eax
0x180027209  lea     rax, [rbp+80h+String]
0x18002720d  mov     [rsp+180h+lpnFit], rax; unsigned __int16 *
0x180027212  call    ?_GetSampleText@CFontThumbnail@@AEAAXPEAUHDC__@@PEFBU_ITEMIDLIST@@PEAUtagLOGFONTW@@PEAGK@Z; CFontThumbnail::_GetSampleText(HDC__ *,_ITEMIDLIST const *,tagLOGFONTW *,ushort *,ulong)
0x180027217  movsd   xmm6, cs:__real@3ff0000000000000
0x18002721f  xor     ebx, ebx
0x180027221  test    r14d, r14d
0x180027224  jle     loc_180027478
0x18002722a  mov     edx, 5Ah ; 'Z'; index
0x18002722f  mov     qword ptr [rsp+180h+psize.cx], rbx
0x180027234  mov     rcx, rdi; hdc
0x180027237  call    cs:__imp_GetDeviceCaps
0x18002723d  mov     r8d, 48h ; 'H'; nDenominator
0x180027243  mov     ecx, r14d; nNumber
0x180027246  mov     edx, eax; nNumerator
0x180027248  call    cs:__imp_MulDiv
0x18002724e  lea     rcx, [rsp+180h+lf]; lplf
0x180027253  mov     [rsp+180h+lf.lfWidth], ebx
0x180027257  neg     eax
0x180027259  mov     [rsp+180h+lf.lfHeight], eax
0x18002725d  call    cs:__imp_CreateFontIndirectW
0x180027263  mov     r15, rax
0x180027266  test    rax, rax
0x180027269  jz      short loc_180027221
0x18002726b  mov     rdx, rax; h
0x18002726e  mov     rcx, rdi; hdc
0x180027271  call    cs:__imp_SelectObject
0x180027277  lea     r9, [rsp+180h+psize]; psizl
0x18002727c  mov     r13, rax
0x18002727f  mov     rcx, rdi; hdc
0x180027282  cmp     [rsi+45Ch], ebx
0x180027288  jz      short loc_1800272A0
0x18002728a  mov     r8d, [rsi+468h]; cgi
0x180027291  lea     rdx, [rsi+460h]; pgiIn
0x180027298  call    cs:__imp_GetTextExtentPointI
0x18002729e  jmp     short loc_1800272B0
0x1800272a0  mov     r8d, 18h; c
0x1800272a6  lea     rdx, [rbp+80h+String]; lpString
0x1800272aa  call    cs:__imp_GetTextExtentPoint32W
0x1800272b0  test    eax, eax
0x1800272b2  jz      loc_18002739D
0x1800272b8  mov     eax, [rsp+180h+psize.cy]
0x1800272bc  mov     ecx, 1
0x1800272c1  movd    xmm1, [rsp+180h+var_138]
0x1800272c7  test    eax, eax
0x1800272c9  cvtdq2pd xmm1, xmm1
0x1800272cd  cmovnz  ecx, eax
0x1800272d0  movd    xmm0, ecx
0x1800272d4  mov     rcx, rdi; hdc
0x1800272d7  cvtdq2pd xmm0, xmm0
0x1800272db  divsd   xmm1, xmm0
0x1800272df  comisd  xmm6, xmm1
0x1800272e3  jbe     short loc_18002731A
0x1800272e5  movd    xmm0, r14d
0x1800272ea  mov     rdx, r13; h
0x1800272ed  cvtdq2pd xmm0, xmm0
0x1800272f1  mulsd   xmm0, xmm1
0x1800272f5  cvttsd2si ebx, xmm0
0x1800272f9  call    cs:__imp_SelectObject
0x1800272ff  mov     rcx, r15; ho
0x180027302  call    cs:__imp_DeleteObject
0x180027308  mov     eax, r14d
0x18002730b  lea     r14d, [rbx-1]
0x18002730f  cmp     ebx, eax
0x180027311  cmovnz  r14d, ebx
0x180027315  jmp     loc_18002721F
0x18002731a  lea     rax, [rsp+180h+Size]
0x18002731f  mov     r9d, [rsp+180h+nMaxExtent]; nMaxExtent
0x180027324  mov     [rsp+180h+lpSize], rax; lpSize
0x180027329  lea     rax, [rsp+180h+nFit]
0x18002732e  mov     [rsp+180h+lpnDx], rbx; lpnDx
0x180027333  mov     [rsp+180h+lpnFit], rax; lpnFit
0x180027338  mov     [rsp+180h+nFit], ebx
0x18002733c  mov     qword ptr [rsp+180h+Size.cx], rbx
0x180027341  cmp     [rsi+45Ch], ebx
0x180027347  jz      short loc_18002735F
0x180027349  mov     r8d, [rsi+468h]; cwchString
0x180027350  lea     rdx, [rsi+460h]; lpwszString
0x180027357  call    cs:__imp_GetTextExtentExPointI
0x18002735d  jmp     short loc_18002736F
0x18002735f  mov     r8d, 18h; cchString
0x180027365  lea     rdx, [rbp+80h+String]; lpszString
0x180027369  call    cs:__imp_GetTextExtentExPointW
0x18002736f  test    eax, eax
0x180027371  jz      loc_180027463
0x180027377  movsxd  rax, [rsp+180h+nFit]
0x18002737c  test    eax, eax
0x18002737e  jnz     short loc_1800273A2
0x180027380  dec     r14d
0x180027383  mov     rdx, r13; h
0x180027386  mov     rcx, rdi; hdc
0x180027389  call    cs:__imp_SelectObject
0x18002738f  mov     rcx, r15; ho
0x180027392  call    cs:__imp_DeleteObject
0x180027398  jmp     loc_180027221
0x18002739d  mov     r14d, ebx
0x1800273a0  jmp     short loc_180027383
0x1800273a2  mov     edx, [rsi+45Ch]
0x1800273a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800273ac  xor     r14d, r14d
0x1800273af  test    edx, edx
0x1800273b1  jnz     short loc_1800273E0
0x1800273b3  lea     r8, [rbp+80h+String]
0x1800273b7  mov     rcx, rbx
0x1800273ba  inc     rcx
0x1800273bd  cmp     [r8+rcx*2], r14w
0x1800273c2  jnz     short loc_1800273BA
0x1800273c4  cmp     eax, ecx
0x1800273c6  jge     short loc_1800273E0
0x1800273c8  lea     rcx, [rax+rax]
0x1800273cc  cmp     rcx, 30h ; '0'
0x1800273d0  jnb     short loc_1800273DA
0x1800273d2  mov     [rbp+rcx+80h+String], r14w
0x1800273d8  jmp     short loc_1800273F2
0x1800273da  call    __report_rangecheckfailure
0x1800273e0  cmp     eax, [rsi+468h]
0x1800273e6  jge     short loc_1800273EE
0x1800273e8  mov     [rsi+468h], eax
0x1800273ee  test    edx, edx
0x1800273f0  jnz     short loc_180027450
0x1800273f2  lea     rax, [rbp+80h+String]
0x1800273f6  mov     r8, rbx
0x1800273f9  inc     r8; c
0x1800273fc  cmp     [rax+r8*2], r14w
0x180027401  jnz     short loc_1800273F9
0x180027403  lea     r9, [rbp+80h+pgi]; pgi
0x180027407  mov     dword ptr [rsp+180h+lpnFit], 1; fl
0x18002740f  lea     rdx, [rbp+80h+String]; lpstr
0x180027413  mov     rcx, rdi; hdc
0x180027416  call    cs:__imp_GetGlyphIndicesW
0x18002741c  cmp     eax, 0FFFFFFFFh
0x18002741f  jz      short loc_180027449
0x180027421  lea     rcx, [rbp+80h+String]; this
0x180027425  inc     rbx
0x180027428  cmp     [rcx+rbx*2], r14w
0x18002742d  jnz     short loc_180027425
0x18002742f  mov     eax, eax
0x180027431  cmp     rbx, rax
0x180027434  jnz     short loc_180027449
0x180027436  lea     r9, [rsp+180h+var_120]; struct tagRECT *
0x18002743b  mov     rdx, rdi; HDC
0x18002743e  lea     r8, [rbp+80h+String]; unsigned __int16 *
0x180027442  call    ?_DrawSampleTextInRect@CFontThumbnail@@AEAAJPEAUHDC__@@PEBGPEAUtagRECT@@@Z; CFontThumbnail::_DrawSampleTextInRect(HDC__ *,ushort const *,tagRECT *)
0x180027447  jmp     short loc_180027460
0x180027449  mov     [rbp+80h+String], r14w
0x18002744e  jmp     short loc_180027463
0x180027450  lea     r8, [rsp+180h+var_120]; struct tagRECT *
0x180027455  mov     rdx, rdi; HDC
0x180027458  mov     rcx, rsi; this
0x18002745b  call    ?_GlyphDrawSampleTextInRect@CFontThumbnail@@AEAAJPEAUHDC__@@PEAUtagRECT@@@Z; CFontThumbnail::_GlyphDrawSampleTextInRect(HDC__ *,tagRECT *)
0x180027460  mov     r12d, eax
0x180027463  mov     rdx, r13; h
0x180027466  mov     rcx, rdi; hdc
0x180027469  call    cs:__imp_SelectObject
0x18002746f  mov     rcx, r15; ho
0x180027472  call    cs:__imp_DeleteObject
0x180027478  mov     eax, r12d
0x18002747b  mov     rcx, [rbp+80h+var_50]
0x18002747f  xor     rcx, rsp; StackCookie
0x180027482  call    __security_check_cookie
0x180027487  lea     r11, [rsp+180h+var_30]
0x18002748f  mov     rbx, [r11+58h]
0x180027493  movaps  xmm6, xmmword ptr [r11-10h]
0x180027498  mov     rsp, r11
0x18002749b  pop     r15
0x18002749d  pop     r14
0x18002749f  pop     r13
0x1800274a1  pop     r12
0x1800274a3  pop     rdi
0x1800274a4  pop     rsi
0x1800274a5  pop     rbp
0x1800274a6  retn
```
