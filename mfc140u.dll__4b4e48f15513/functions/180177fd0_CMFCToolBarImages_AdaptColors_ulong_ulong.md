# CMFCToolBarImages::AdaptColors(ulong,ulong)

- ea: `0x180177fd0`
- end: `0x1801784eb`
- name: `?AdaptColors@CMFCToolBarImages@@QEAAXKK@Z`
- size: `1307`
- prototype: `void __fastcall(CMFCToolBarImages *this, unsigned int clrBase, unsigned int clrTone)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180135300`

## callees

- `0x18005d5b0`
- `0x18005d820`
- `0x18006cab0`
- `0x180177fd0`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aef40`
- `0x1802c4640`

## import_xrefs

- `GDI32!SetPixel` at `0x180178447`
- `GDI32!SetPixel` at `0x180178447`
- `GDI32!BitBlt` at `0x18017832c`
- `GDI32!BitBlt` at `0x18017832c`
- `GDI32!CreateCompatibleBitmap` at `0x180178237`
- `GDI32!CreateCompatibleBitmap` at `0x180178237`
- `GDI32!GetPixel` at `0x18017839f`
- `GDI32!GetPixel` at `0x18017839f`
- `GDI32!DeleteObject` at `0x1801782f7`
- `GDI32!DeleteObject` at `0x180178490`
- `GDI32!DeleteObject` at `0x1801784b1`
- `GDI32!DeleteObject` at `0x1801784ce`
- `GDI32!DeleteObject` at `0x1801782f7`
- `GDI32!DeleteObject` at `0x180178490`
- `GDI32!DeleteObject` at `0x1801784b1`
- `GDI32!DeleteObject` at `0x1801784ce`
- `GDI32!SelectObject` at `0x180178212`
- `GDI32!SelectObject` at `0x180178251`
- `GDI32!SelectObject` at `0x1801782d8`
- `GDI32!SelectObject` at `0x1801782ee`
- `GDI32!SelectObject` at `0x180178476`
- `GDI32!SelectObject` at `0x180178483`
- `GDI32!SelectObject` at `0x180178212`
- `GDI32!SelectObject` at `0x180178251`
- `GDI32!SelectObject` at `0x1801782d8`
- `GDI32!SelectObject` at `0x1801782ee`
- `GDI32!SelectObject` at `0x180178476`
- `GDI32!SelectObject` at `0x180178483`
- `GDI32!CreateCompatibleDC` at `0x1801781d9`
- `GDI32!CreateCompatibleDC` at `0x1801782bf`
- `GDI32!CreateCompatibleDC` at `0x1801781d9`
- `GDI32!CreateCompatibleDC` at `0x1801782bf`
- `GDI32!GetObjectW` at `0x1801780a5`
- `GDI32!GetObjectW` at `0x1801781f8`
- `GDI32!GetObjectW` at `0x1801780a5`
- `GDI32!GetObjectW` at `0x1801781f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CMFCToolBarImages::AdaptColors(CMFCToolBarImages *this, unsigned int clrBase, unsigned int clrTone)
{
  CMFCToolBarImages *v4; // rsi
  double v5; // xmm10_8
  double v6; // xmm11_8
  double v7; // xmm9_8
  double v8; // xmm8_8
  int v9; // esi
  int v10; // ecx
  int bmWidthBytes; // edx
  unsigned __int8 *v12; // rdi
  double v13; // xmm4_8
  double v14; // xmm2_8
  long double v15; // xmm3_8
  double v16; // xmm1_8
  unsigned int v17; // eax
  HDC CompatibleDC; // rax
  HBITMAP__ *m_hbmImageWell; // rdx
  HGDIOBJ v20; // rdi
  int v21; // r13d
  int cy; // r14d
  CDC_vtbl *CompatibleBitmap; // r12
  HDC v24; // rax
  int v25; // r15d
  int v26; // r12d
  int v27; // esi
  int i; // r14d
  COLORREF Pixel; // eax
  double v30; // xmm4_8
  double v31; // xmm2_8
  long double v32; // xmm3_8
  double v33; // xmm1_8
  COLORREF v34; // eax
  HGDIOBJ *p_m_hbmImageLight; // rdi
  HGDIOBJ *p_m_hbmImageShadow; // rdi
  double L; // [rsp+58h] [rbp-B0h] BYREF
  long double S; // [rsp+60h] [rbp-A8h] BYREF
  long double H; // [rsp+68h] [rbp-A0h] BYREF
  long double dSrcH; // [rsp+70h] [rbp-98h] BYREF
  long double dDestL; // [rsp+78h] [rbp-90h] BYREF
  CDC memDCSrc; // [rsp+80h] [rbp-88h] BYREF
  CDC memDCDst; // [rsp+A0h] [rbp-68h] BYREF
  int v44; // [rsp+C0h] [rbp-48h]
  CMFCToolBarImages *v45; // [rsp+C8h] [rbp-40h]
  tagBITMAP bmp; // [rsp+D0h] [rbp-38h] BYREF
  tagDIBSECTION pv; // [rsp+F0h] [rbp-18h] BYREF

  v4 = this;
  v45 = this;
  CDrawingManager::RGBtoHSL(clrBase, &dDestL, &dSrcH, &S);
  CDrawingManager::RGBtoHSL(clrTone, &L, &H, (long double *)&memDCSrc);
  v5 = L;
  v6 = L - dDestL;
  v7 = *(double *)&memDCSrc.__vftable - S;
  v8 = H - dSrcH;
  if ( v4->m_nBitsPerPixel == 32 )
  {
    if ( GetObjectW(v4->m_hbmImageWell, 104, &pv.dsBm.bmHeight) )
    {
      if ( WORD1(pv.dsBm.bmBits) == 32 )
      {
        if ( *(_QWORD *)&pv.dsBmih.biSize )
        {
          v9 = 0;
          v10 = *(_DWORD *)&pv.dsBm.bmPlanes;
          bmWidthBytes = pv.dsBm.bmWidthBytes;
          if ( pv.dsBm.bmWidthBytes * *(_DWORD *)&pv.dsBm.bmPlanes > 0 )
          {
            v12 = (unsigned __int8 *)(*(_QWORD *)&pv.dsBmih.biSize + 2LL);
            do
            {
              if ( v12[1] )
              {
                CDrawingManager::RGBtoHSL(*v12 | (*(v12 - 2) << 16) | (*(v12 - 1) << 8), &dSrcH, &H, &S);
                v13 = fmin(1.0, dSrcH + v6);
                if ( v13 < 0.0 )
                  v13 = 0.0;
                v14 = fmin(1.0, H + v8);
                if ( v14 < 0.0 )
                  v14 = 0.0;
                v15 = S;
                v16 = fmin(1.0, S + v7);
                if ( v16 < 0.0 )
                  v16 = 0.0;
                if ( v5 <= 0.5 )
                  v15 = v16;
                v17 = CDrawingManager::HLStoRGB_ONE(v13, v15, v14);
                *v12 = v17;
                *(v12 - 1) = BYTE1(v17);
                *(v12 - 2) = BYTE2(v17);
                v10 = *(_DWORD *)&pv.dsBm.bmPlanes;
                bmWidthBytes = pv.dsBm.bmWidthBytes;
              }
              ++v9;
              v12 += 4;
            }
            while ( v9 < bmWidthBytes * v10 );
          }
        }
      }
    }
  }
  else
  {
    memDCSrc.m_hDC = (HDC__ *)CDC::`vftable';
    *(_OWORD *)&memDCSrc.m_hAttribDC = 0;
    LODWORD(memDCDst.__vftable) = 0;
    CompatibleDC = CreateCompatibleDC(0);
    CDC::Attach((CDC *)&memDCSrc.m_hDC, CompatibleDC);
    if ( GetObjectW(v4->m_hbmImageWell, 32, &bmp.bmHeight) )
    {
      m_hbmImageWell = v4->m_hbmImageWell;
      if ( m_hbmImageWell )
      {
        v20 = SelectObject(memDCSrc.m_hAttribDC, m_hbmImageWell);
        if ( v20 )
        {
          v21 = bmp.bmWidthBytes;
          cy = *(_DWORD *)&bmp.bmPlanes;
          LODWORD(L) = *(_DWORD *)&bmp.bmPlanes;
          CompatibleBitmap = (CDC_vtbl *)CreateCompatibleBitmap(
                                           memDCSrc.m_hAttribDC,
                                           bmp.bmWidthBytes,
                                           *(int *)&bmp.bmPlanes);
          memDCSrc.__vftable = CompatibleBitmap;
          if ( CompatibleBitmap )
          {
            memDCDst.m_hDC = (HDC__ *)CDC::`vftable';
            *(_OWORD *)&memDCDst.m_hAttribDC = 0;
            v44 = 0;
            v24 = CreateCompatibleDC(memDCSrc.m_hAttribDC);
            CDC::Attach((CDC *)&memDCDst.m_hDC, v24);
            *(_QWORD *)&bmp.bmType = SelectObject(memDCDst.m_hAttribDC, CompatibleBitmap);
            if ( *(_QWORD *)&bmp.bmType )
            {
              BitBlt(memDCDst.m_hAttribDC, 0, 0, v21, cy, memDCSrc.m_hAttribDC, 0, 0, 0xCC0020u);
              LODWORD(dDestL) = v4->m_clrTransparent;
              if ( LODWORD(dDestL) == -1 )
              {
                if ( !afxGlobalData.m_bInitialized )
                {
                  AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
                  afxGlobalData.m_bInitialized = 1;
                }
                LODWORD(dDestL) = afxGlobalData.clrBtnFace;
              }
              v25 = 0;
              if ( v21 > 0 )
              {
                v26 = LODWORD(L);
                v27 = LODWORD(dDestL);
                do
                {
                  for ( i = 0; i < v26; ++i )
                  {
                    Pixel = GetPixel(memDCDst.m_hAttribDC, v25, i);
                    LODWORD(L) = Pixel;
                    if ( Pixel != v27 )
                    {
                      CDrawingManager::RGBtoHSL(Pixel, &dSrcH, &H, &S);
                      v30 = fmin(1.0, dSrcH + v6);
                      if ( v30 < 0.0 )
                        v30 = 0.0;
                      v31 = fmin(1.0, H + v8);
                      if ( v31 < 0.0 )
                        v31 = 0.0;
                      v32 = S;
                      v33 = fmin(1.0, S + v7);
                      if ( v33 < 0.0 )
                        v33 = 0.0;
                      if ( v5 <= 0.5 )
                        v32 = v33;
                      v34 = CDrawingManager::HLStoRGB_ONE(v30, v32, v31);
                      if ( LODWORD(L) != v34 )
                        SetPixel(memDCDst.m_hAttribDC, v25, i, v34);
                    }
                  }
                  ++v25;
                }
                while ( v25 < v21 );
                v4 = v45;
                CompatibleBitmap = memDCSrc.__vftable;
              }
              SelectObject(memDCDst.m_hAttribDC, *(HGDIOBJ *)&bmp.bmType);
              SelectObject(memDCSrc.m_hAttribDC, v20);
              DeleteObject(v4->m_hbmImageWell);
              v4->m_hbmImageWell = (HBITMAP__ *)CompatibleBitmap;
              p_m_hbmImageLight = (HGDIOBJ *)&v4->m_hbmImageLight;
              if ( v4 == (CMFCToolBarImages *)-168LL )
                goto LABEL_57;
              if ( *p_m_hbmImageLight )
                DeleteObject(*p_m_hbmImageLight);
              *p_m_hbmImageLight = 0;
              p_m_hbmImageShadow = (HGDIOBJ *)&v4->m_hbmImageShadow;
              if ( v4 == (CMFCToolBarImages *)-176LL )
LABEL_57:
                AfxThrowInvalidArgException();
              if ( *p_m_hbmImageShadow )
                DeleteObject(*p_m_hbmImageShadow);
              *p_m_hbmImageShadow = 0;
            }
            else
            {
              SelectObject(memDCSrc.m_hAttribDC, v20);
              DeleteObject(CompatibleBitmap);
            }
            CDC::~CDC((CDC *)&memDCDst.m_hDC);
          }
          else
          {
            SelectObject(memDCSrc.m_hAttribDC, v20);
          }
        }
      }
    }
    CDC::~CDC((CDC *)&memDCSrc.m_hDC);
  }
}

```

## disassembly

```asm
0x180177fd0  mov     rax, rsp
0x180177fd3  mov     [rax+10h], rbx
0x180177fd7  mov     [rax+18h], rsi
0x180177fdb  mov     [rax+20h], rdi
0x180177fdf  push    rbp
0x180177fe0  push    r12
0x180177fe2  push    r13
0x180177fe4  push    r14
0x180177fe6  push    r15
0x180177fe8  lea     rbp, [rax-0F8h]
0x180177fef  sub     rsp, 1D0h
0x180177ff6  movaps  xmmword ptr [rax-38h], xmm6
0x180177ffa  movaps  xmmword ptr [rax-48h], xmm7
0x180177ffe  movaps  xmmword ptr [rax-58h], xmm8
0x180178003  movaps  xmmword ptr [rax-68h], xmm9
0x180178008  movaps  xmmword ptr [rax-78h], xmm10
0x18017800d  movaps  xmmword ptr [rax-88h], xmm11
0x180178015  mov     rax, cs:__security_cookie
0x18017801c  xor     rax, rsp
0x18017801f  mov     [rbp+0F0h+var_90], rax
0x180178023  mov     ebx, clrTone
0x180178026  mov     eax, clrBase
0x180178028  mov     rsi, this
0x18017802b  mov     [rbp+0F0h+var_130], this
0x18017802f  lea     r9, [rsp+1F0h+S]; L
0x180178034  lea     r8, [rsp+1F0h+dSrcH]; S
0x180178039  lea     rdx, [rsp+1F0h+dDestL]; H
0x18017803e  mov     ecx, eax; rgb
0x180178040  call    ?RGBtoHSL@CDrawingManager@@SAXKPEAN00@Z; CDrawingManager::RGBtoHSL(ulong,double *,double *,double *)
0x180178045  lea     r9, [rsp+1F0h+memDCSrc]; L
0x18017804a  lea     r8, [rsp+1F0h+H]; S
0x18017804f  lea     rdx, [rsp+1F0h+L]; H
0x180178054  mov     ecx, ebx; rgb
0x180178056  call    ?RGBtoHSL@CDrawingManager@@SAXKPEAN00@Z; CDrawingManager::RGBtoHSL(ulong,double *,double *,double *)
0x18017805b  movsd   xmm10, [rsp+1F0h+L]
0x180178062  movaps  xmm11, xmm10
0x180178066  subsd   xmm11, [rsp+1F0h+dDestL]
0x18017806d  movsd   xmm9, [rsp+1F0h+memDCSrc.__vftable]
0x180178074  subsd   xmm9, [rsp+1F0h+S]
0x18017807b  movsd   xmm8, [rsp+1F0h+H]
0x180178082  subsd   xmm8, [rsp+1F0h+dSrcH]
0x180178089  mov     edi, 20h ; ' '
0x18017808e  cmp     [rsi+0Ch], edi
0x180178091  jnz     loc_1801781BF
0x180178097  lea     r8, [rbp+0F0h+pv.dsBm.bmHeight]; pv
0x18017809b  lea     clrBase, [rdi+48h]; c
0x18017809e  mov     this, [rsi+0A0h]; h
0x1801780a5  call    cs:__imp_GetObjectW
0x1801780ab  xor     ebx, ebx
0x1801780ad  test    eax, eax
0x1801780af  jz      loc_180178261
0x1801780b5  cmp     word ptr [rbp+0F0h+pv.dsBm.bmBits+2], di
0x1801780b9  jnz     loc_180178261
0x1801780bf  mov     rdi, qword ptr [rbp+0F0h+pv.dsBmih.biSize]
0x1801780c3  test    rdi, rdi
0x1801780c6  jz      loc_180178261
0x1801780cc  mov     esi, ebx
0x1801780ce  mov     ecx, dword ptr [rbp+0F0h+pv.dsBm.bmPlanes]
0x1801780d1  mov     eax, ecx
0x1801780d3  mov     clrBase, [rbp+0F0h+pv.dsBm.bmWidthBytes]
0x1801780d6  imul    eax, clrBase
0x1801780d9  test    eax, eax
0x1801780db  jle     loc_180178261
0x1801780e1  add     rdi, 2
0x1801780e5  movsd   xmm7, cs:__real@3ff0000000000000
0x1801780ed  xorps   xmm6, xmm6
0x1801780f0  cmp     [rdi+1], bl
0x1801780f3  jz      loc_1801781A7
0x1801780f9  movzx   ecx, byte ptr [rdi-1]
0x1801780fd  shl     ecx, 8
0x180178100  movzx   eax, byte ptr [rdi-2]
0x180178104  shl     eax, 10h
0x180178107  or      ecx, eax
0x180178109  movzx   eax, byte ptr [rdi]
0x18017810c  or      ecx, eax; rgb
0x18017810e  lea     r9, [rsp+1F0h+S]; L
0x180178113  lea     r8, [rsp+1F0h+H]; S
0x180178118  lea     rdx, [rsp+1F0h+dSrcH]; H
0x18017811d  call    ?RGBtoHSL@CDrawingManager@@SAXKPEAN00@Z; CDrawingManager::RGBtoHSL(ulong,double *,double *,double *)
0x180178122  movsd   xmm0, [rsp+1F0h+dSrcH]
0x180178128  addsd   xmm0, xmm11
0x18017812d  movaps  xmm4, xmm7
0x180178130  minsd   xmm4, xmm0
0x180178134  comisd  xmm6, xmm4
0x180178138  jbe     short loc_18017813D
0x18017813a  movaps  xmm4, xmm6
0x18017813d  movsd   xmm0, [rsp+1F0h+H]
0x180178143  addsd   xmm0, xmm8
0x180178148  movaps  xmm2, xmm7
0x18017814b  minsd   xmm2, xmm0
0x18017814f  comisd  xmm6, xmm2
0x180178153  jbe     short loc_180178158
0x180178155  movaps  xmm2, xmm6; S
0x180178158  movsd   xmm3, [rsp+1F0h+S]
0x18017815e  movaps  xmm0, xmm3
0x180178161  addsd   xmm0, xmm9
0x180178166  movaps  xmm1, xmm7
0x180178169  minsd   xmm1, xmm0
0x18017816d  comisd  xmm6, xmm1
0x180178171  jbe     short loc_180178176
0x180178173  movaps  xmm1, xmm6
0x180178176  comisd  xmm10, cs:__real@3fe0000000000000
0x18017817f  ja      short loc_180178184
0x180178181  movaps  xmm3, xmm1
0x180178184  movaps  xmm1, xmm3; L
0x180178187  movaps  xmm0, xmm4; H
0x18017818a  call    ?HLStoRGB_ONE@CDrawingManager@@SAKNNN@Z; CDrawingManager::HLStoRGB_ONE(double,double,double)
0x18017818f  mov     [rdi], al
0x180178191  movzx   ecx, ax
0x180178194  shr     cx, 8
0x180178198  mov     [rdi-1], cl
0x18017819b  shr     eax, 10h
0x18017819e  mov     [rdi-2], al
0x1801781a1  mov     ecx, dword ptr [rbp+0F0h+pv.dsBm.bmPlanes]
0x1801781a4  mov     clrBase, [rbp+0F0h+pv.dsBm.bmWidthBytes]
0x1801781a7  inc     esi
0x1801781a9  add     rdi, 4
0x1801781ad  mov     eax, ecx
0x1801781af  imul    eax, clrBase
0x1801781b2  cmp     esi, eax
0x1801781b4  jl      loc_1801780F0
0x1801781ba  jmp     loc_180178261
0x1801781bf  lea     r15, ??_7CDC@@6B@; const CDC::`vftable'
0x1801781c6  mov     [rbp+0F0h+memDCSrc.m_hDC], r15
0x1801781ca  xorps   xmm0, xmm0
0x1801781cd  movdqu  xmmword ptr [rbp+0F0h+memDCSrc.m_hAttribDC], xmm0
0x1801781d2  xor     ebx, ebx
0x1801781d4  mov     dword ptr [rbp+0F0h+memDCDst.__vftable], ebx
0x1801781d7  xor     ecx, ecx; hdc
0x1801781d9  call    cs:__imp_CreateCompatibleDC
0x1801781df  mov     rdx, rax; hDC
0x1801781e2  lea     this, [rbp+0F0h+memDCSrc.m_hDC]; this
0x1801781e6  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1801781eb  lea     r8, [rbp+0F0h+bmp.bmHeight]; pv
0x1801781ef  mov     clrBase, edi; c
0x1801781f1  mov     this, [rsi+0A0h]; h
0x1801781f8  call    cs:__imp_GetObjectW
0x1801781fe  test    eax, eax
0x180178200  jz      short loc_180178258
0x180178202  mov     rdx, [rsi+0A0h]; h
0x180178209  test    rdx, rdx
0x18017820c  jz      short loc_180178258
0x18017820e  mov     this, [rbp+0F0h+memDCSrc.m_hAttribDC]; hdc
0x180178212  call    cs:__imp_SelectObject
0x180178218  mov     rdi, rax
0x18017821b  test    rax, rax
0x18017821e  jz      short loc_180178258
0x180178220  mov     r13d, [rbp+0F0h+bmp.bmWidthBytes]
0x180178224  mov     r14d, dword ptr [rbp+0F0h+bmp.bmPlanes]
0x180178228  mov     dword ptr [rsp+1F0h+L], r14d
0x18017822d  mov     clrTone, r14d; cy
0x180178230  mov     clrBase, r13d; cx
0x180178233  mov     this, [rbp+0F0h+memDCSrc.m_hAttribDC]; hdc
0x180178237  call    cs:__imp_CreateCompatibleBitmap
0x18017823d  mov     r12, rax
0x180178240  mov     [rsp+1F0h+memDCSrc.__vftable], rax
0x180178245  test    rax, rax
0x180178248  jnz     short loc_1801782AC
0x18017824a  mov     rdx, rdi; h
0x18017824d  mov     this, [rbp+0F0h+memDCSrc.m_hAttribDC]; hdc
0x180178251  call    cs:__imp_SelectObject
0x180178257  nop
0x180178258  lea     this, [rbp+0F0h+memDCSrc.m_hDC]; this
0x18017825c  call    ??1CDC@@UEAA@XZ; CDC::~CDC(void)
0x180178261  mov     this, [rbp+0F0h+var_90]
0x180178265  xor     this, rsp; StackCookie
0x180178268  call    __security_check_cookie
0x18017826d  lea     r11, [rsp+1F0h+var_20]
0x180178275  mov     rbx, [r11+38h]
0x180178279  mov     rsi, [r11+40h]
0x18017827d  mov     rdi, [r11+48h]
0x180178281  movaps  xmm6, xmmword ptr [r11-10h]
0x180178286  movaps  xmm7, xmmword ptr [r11-20h]
0x18017828b  movaps  xmm8, xmmword ptr [r11-30h]
0x180178290  movaps  xmm9, xmmword ptr [r11-40h]
0x180178295  movaps  xmm10, xmmword ptr [r11-50h]
0x18017829a  movaps  xmm11, xmmword ptr [r11-60h]
0x18017829f  mov     rsp, r11
0x1801782a2  pop     r15
0x1801782a4  pop     r14
0x1801782a6  pop     r13
0x1801782a8  pop     r12
0x1801782aa  pop     rbp
0x1801782ab  retn
0x1801782ac  mov     [rbp+0F0h+memDCDst.m_hDC], r15
0x1801782b0  xorps   xmm0, xmm0
0x1801782b3  movdqu  xmmword ptr [rbp+0F0h+memDCDst.m_hAttribDC], xmm0
0x1801782b8  mov     [rbp+0F0h+var_138], ebx
0x1801782bb  mov     this, [rbp+0F0h+memDCSrc.m_hAttribDC]; hdc
0x1801782bf  call    cs:__imp_CreateCompatibleDC
0x1801782c5  mov     rdx, rax; hDC
0x1801782c8  lea     this, [rbp+0F0h+memDCDst.m_hDC]; this
0x1801782cc  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1801782d1  mov     rdx, r12; h
0x1801782d4  mov     this, [rbp+0F0h+memDCDst.m_hAttribDC]; hdc
0x1801782d8  call    cs:__imp_SelectObject
0x1801782de  mov     qword ptr [rbp+0F0h+bmp.bmType], rax
0x1801782e2  test    rax, rax
0x1801782e5  jnz     short loc_180178302
0x1801782e7  mov     rdx, rdi; h
0x1801782ea  mov     this, [rbp+0F0h+memDCSrc.m_hAttribDC]; hdc
0x1801782ee  call    cs:__imp_SelectObject
0x1801782f4  mov     this, r12; ho
0x1801782f7  call    cs:__imp_DeleteObject
0x1801782fd  jmp     loc_1801784D7
0x180178302  mov     [rsp+1F0h+rop], 0CC0020h; rop
0x18017830a  mov     [rsp+1F0h+y1], ebx; y1
0x18017830e  mov     [rsp+1F0h+x1], ebx; x1
0x180178312  mov     rax, [rbp+0F0h+memDCSrc.m_hAttribDC]
0x180178316  mov     [rsp+1F0h+hdcSrc], rax; hdcSrc
0x18017831b  mov     [rsp+1F0h+cy], r14d; cy
0x180178320  mov     r9d, r13d; cx
0x180178323  xor     clrTone, clrTone; y
0x180178326  xor     clrBase, clrBase; x
0x180178328  mov     this, [rbp+0F0h+memDCDst.m_hAttribDC]; hdc
0x18017832c  call    cs:__imp_BitBlt
0x180178332  mov     eax, [rsi+0D8h]
0x180178338  mov     dword ptr [rsp+1F0h+dDestL], eax
0x18017833c  cmp     eax, 0FFFFFFFFh
0x18017833f  jnz     short loc_180178369
0x180178341  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x180178347  jnz     short loc_18017835F
0x180178349  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180178350  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x180178355  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x18017835f  mov     eax, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnFace; AFX_GLOBAL_DATA afxGlobalData ...
0x180178365  mov     dword ptr [rsp+1F0h+dDestL], eax
0x180178369  mov     r15d, ebx
0x18017836c  test    r13d, r13d
0x18017836f  jle     loc_18017846E
0x180178375  movsd   xmm7, cs:__real@3ff0000000000000
0x18017837d  xorps   xmm6, xmm6
0x180178380  mov     r12d, dword ptr [rsp+1F0h+L]
0x180178385  mov     esi, dword ptr [rsp+1F0h+dDestL]
0x180178389  mov     r14d, ebx
0x18017838c  test    r12d, r12d
0x18017838f  jle     loc_180178459
0x180178395  mov     clrTone, r14d; y
0x180178398  mov     clrBase, r15d; x
0x18017839b  mov     this, [rbp+0F0h+memDCDst.m_hAttribDC]; hdc
0x18017839f  call    cs:__imp_GetPixel
0x1801783a5  mov     dword ptr [rsp+1F0h+L], eax
0x1801783a9  cmp     eax, esi
0x1801783ab  jz      loc_18017844D
0x1801783b1  lea     r9, [rsp+1F0h+S]; L
0x1801783b6  lea     r8, [rsp+1F0h+H]; S
0x1801783bb  lea     rdx, [rsp+1F0h+dSrcH]; H
0x1801783c0  mov     ecx, eax; rgb
0x1801783c2  call    ?RGBtoHSL@CDrawingManager@@SAXKPEAN00@Z; CDrawingManager::RGBtoHSL(ulong,double *,double *,double *)
0x1801783c7  movsd   xmm0, [rsp+1F0h+dSrcH]
0x1801783cd  addsd   xmm0, xmm11
0x1801783d2  movaps  xmm4, xmm7
0x1801783d5  minsd   xmm4, xmm0
0x1801783d9  comisd  xmm6, xmm4
0x1801783dd  jbe     short loc_1801783E2
0x1801783df  movaps  xmm4, xmm6
0x1801783e2  movsd   xmm0, [rsp+1F0h+H]
0x1801783e8  addsd   xmm0, xmm8
0x1801783ed  movaps  xmm2, xmm7
0x1801783f0  minsd   xmm2, xmm0
0x1801783f4  comisd  xmm6, xmm2
0x1801783f8  jbe     short loc_1801783FD
0x1801783fa  movaps  xmm2, xmm6; S
0x1801783fd  movsd   xmm3, [rsp+1F0h+S]
0x180178403  movaps  xmm0, xmm3
0x180178406  addsd   xmm0, xmm9
0x18017840b  movaps  xmm1, xmm7
0x18017840e  minsd   xmm1, xmm0
0x180178412  comisd  xmm6, xmm1
0x180178416  jbe     short loc_18017841B
0x180178418  movaps  xmm1, xmm6
0x18017841b  comisd  xmm10, cs:__real@3fe0000000000000
0x180178424  ja      short loc_180178429
0x180178426  movaps  xmm3, xmm1
0x180178429  movaps  xmm1, xmm3; L
0x18017842c  movaps  xmm0, xmm4; H
0x18017842f  call    ?HLStoRGB_ONE@CDrawingManager@@SAKNNN@Z; CDrawingManager::HLStoRGB_ONE(double,double,double)
0x180178434  cmp     dword ptr [rsp+1F0h+L], eax
0x180178438  jz      short loc_18017844D
0x18017843a  mov     r9d, eax; color
0x18017843d  mov     clrTone, r14d; y
0x180178440  mov     clrBase, r15d; x
0x180178443  mov     this, [rbp+0F0h+memDCDst.m_hAttribDC]; hdc
0x180178447  call    cs:__imp_SetPixel
0x18017844d  inc     r14d
0x180178450  cmp     r14d, r12d
0x180178453  jl      loc_180178395
0x180178459  inc     r15d
0x18017845c  cmp     r15d, r13d
0x18017845f  jl      loc_180178389
0x180178465  mov     rsi, [rbp+0F0h+var_130]
0x180178469  mov     r12, [rsp+1F0h+memDCSrc.__vftable]
0x18017846e  mov     rdx, qword ptr [rbp+0F0h+bmp.bmType]; h
0x180178472  mov     this, [rbp+0F0h+memDCDst.m_hAttribDC]; hdc
0x180178476  call    cs:__imp_SelectObject
0x18017847c  mov     rdx, rdi; h
0x18017847f  mov     this, [rbp+0F0h+memDCSrc.m_hAttribDC]; hdc
0x180178483  call    cs:__imp_SelectObject
0x180178489  mov     this, [rsi+0A0h]; ho
0x180178490  call    cs:__imp_DeleteObject
  ... truncated ...
```
