# CMFCToolBarImages::GrayImages(int)

- ea: `0x1801774e0`
- end: `0x1801778f5`
- name: `?GrayImages@CMFCToolBarImages@@QEAAHH@Z`
- size: `1045`
- prototype: `int __fastcall(CMFCToolBarImages *this, int nGrayImageLuminancePercentage)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180154c10`
- `0x180161ee0`
- `0x180174770`

## callees

- `0x180058f20`
- `0x18005d270`
- `0x18005d5b0`
- `0x18005d820`
- `0x18006cab0`
- `0x1801774e0`
- `0x1802aee60`
- `0x1802aef40`
- `0x1802c4640`

## import_xrefs

- `GDI32!CreateDIBSection` at `0x180177652`
- `GDI32!CreateDIBSection` at `0x180177652`
- `GDI32!BitBlt` at `0x1801776d0`
- `GDI32!BitBlt` at `0x1801776d0`
- `GDI32!DeleteObject` at `0x18017769a`
- `GDI32!DeleteObject` at `0x180177893`
- `GDI32!DeleteObject` at `0x18017769a`
- `GDI32!DeleteObject` at `0x180177893`
- `GDI32!SelectObject` at `0x1801775cb`
- `GDI32!SelectObject` at `0x180177668`
- `GDI32!SelectObject` at `0x18017767a`
- `GDI32!SelectObject` at `0x180177691`
- `GDI32!SelectObject` at `0x180177878`
- `GDI32!SelectObject` at `0x180177886`
- `GDI32!SelectObject` at `0x1801775cb`
- `GDI32!SelectObject` at `0x180177668`
- `GDI32!SelectObject` at `0x18017767a`
- `GDI32!SelectObject` at `0x180177691`
- `GDI32!SelectObject` at `0x180177878`
- `GDI32!SelectObject` at `0x180177886`
- `GDI32!CreateCompatibleDC` at `0x18017757d`
- `GDI32!CreateCompatibleDC` at `0x1801775f8`
- `GDI32!CreateCompatibleDC` at `0x18017757d`
- `GDI32!CreateCompatibleDC` at `0x1801775f8`
- `GDI32!GetObjectW` at `0x1801775a0`
- `GDI32!GetObjectW` at `0x1801776fa`
- `GDI32!GetObjectW` at `0x1801775a0`
- `GDI32!GetObjectW` at `0x1801776fa`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=15
__int64 __fastcall CMFCToolBarImages::GrayImages(CMFCToolBarImages *this, int nGrayImageLuminancePercentage)
{
  int v3; // ebx
  HDC CompatibleDC; // rax
  int bmWidthBytes; // r12d
  int v6; // r13d
  HBITMAP__ *m_hbmImageWell; // rdx
  HGDIOBJ v8; // rsi
  HDC v9; // rax
  HBITMAP v10; // rax
  HBITMAP__ *v11; // r14
  int m_nGrayImageLuminancePercentage; // r15d
  double v13; // xmm6_8
  unsigned __int8 *v14; // r15
  unsigned int v15; // eax
  unsigned int v16; // eax
  int v17; // r9d
  unsigned int m_clrTransparent; // r9d
  CRect S; // [rsp+50h] [rbp-B8h] BYREF
  CDC memDCSrc; // [rsp+60h] [rbp-A8h] BYREF
  CDrawingManager dm; // [rsp+80h] [rbp-88h] BYREF
  CDC memDCDst; // [rsp+90h] [rbp-78h] BYREF
  unsigned int *pBits; // [rsp+B0h] [rbp-58h]
  void *L; // [rsp+B8h] [rbp-50h] BYREF
  long double v26; // [rsp+C0h] [rbp-48h] BYREF
  tagBITMAP bmp; // [rsp+C8h] [rbp-40h] BYREF
  tagDIBSECTION pv; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE bi_8[40]; // [rsp+168h] [rbp+60h] OVERLAPPED BYREF

  this->m_bIsGray = 1;
  this->m_nGrayImageLuminancePercentage = nGrayImageLuminancePercentage;
  v3 = 0;
  if ( this->m_hbmImageWell )
  {
    if ( !afxGlobalData.m_bInitialized )
    {
      AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
      afxGlobalData.m_bInitialized = 1;
    }
    if ( afxGlobalData.m_nBitsPerPixel > 8 )
    {
      memDCSrc.m_hDC = (HDC__ *)CDC::`vftable';
      *(_OWORD *)&memDCSrc.m_hAttribDC = 0;
      LODWORD(dm.__vftable) = 0;
      CompatibleDC = CreateCompatibleDC(0);
      CDC::Attach((CDC *)&memDCSrc.m_hDC, CompatibleDC);
      if ( !GetObjectW(this->m_hbmImageWell, 32, &bmp.bmHeight) )
        goto LABEL_29;
      bmWidthBytes = bmp.bmWidthBytes;
      v6 = *(_DWORD *)&bmp.bmPlanes;
      m_hbmImageWell = this->m_hbmImageWell;
      if ( !m_hbmImageWell )
        goto LABEL_29;
      v8 = SelectObject(memDCSrc.m_hAttribDC, m_hbmImageWell);
      if ( !v8 )
        goto LABEL_29;
      memDCDst.m_hDC = (HDC__ *)CDC::`vftable';
      *(_OWORD *)&memDCDst.m_hAttribDC = 0;
      LODWORD(pBits) = 0;
      v9 = CreateCompatibleDC(memDCSrc.m_hAttribDC);
      CDC::Attach((CDC *)&memDCDst.m_hDC, v9);
      *(_DWORD *)bi_8 = 40;
      *(_DWORD *)&bi_8[4] = bmWidthBytes;
      *(_DWORD *)&bi_8[8] = v6;
      *(_QWORD *)&bi_8[12] = 2097153;
      *(_DWORD *)&bi_8[20] = bmWidthBytes * v6;
      *(_QWORD *)&bi_8[24] = 0;
      *(_QWORD *)&bi_8[32] = 0;
      L = 0;
      v10 = CreateDIBSection(memDCDst.m_hAttribDC, (const BITMAPINFO *)bi_8, 0, &L, 0, 0);
      v11 = v10;
      if ( v10 )
      {
        *(_QWORD *)&bmp.bmType = SelectObject(memDCDst.m_hAttribDC, v10);
        if ( *(_QWORD *)&bmp.bmType )
        {
          BitBlt(memDCDst.m_hAttribDC, 0, 0, bmWidthBytes, v6, memDCSrc.m_hAttribDC, 0, 0, 0xCC0020u);
          m_nGrayImageLuminancePercentage = this->m_nGrayImageLuminancePercentage;
          if ( m_nGrayImageLuminancePercentage <= 0 )
            m_nGrayImageLuminancePercentage = 130;
          if ( this->m_nBitsPerPixel == 32 )
          {
            if ( !GetObjectW(v11, 104, &pv.dsBm.bmHeight)
              || WORD1(pv.dsBm.bmBits) != 32
              || !*(_QWORD *)&pv.dsBmih.biSize )
            {
              goto LABEL_28;
            }
            if ( pv.dsBm.bmWidthBytes * *(_DWORD *)&pv.dsBm.bmPlanes > 0 )
            {
              v13 = (double)m_nGrayImageLuminancePercentage * 0.01;
              v14 = (unsigned __int8 *)(*(_QWORD *)&pv.dsBmih.biSize + 2LL);
              do
              {
                CDrawingManager::RGBtoHSL(
                  *v14 | (*(v14 - 2) << 16) | (*(v14 - 1) << 8),
                  (long double *)&dm.m_dc,
                  (long double *)&S.right,
                  &v26);
                v15 = CDrawingManager::HLStoRGB_ONE(*(long double *)&dm.m_dc, v26, 0.0);
                v16 = CDrawingManager::PixelAlpha(v15, v13, v13, v13);
                v17 = v14[1];
                *v14 = v17 * (unsigned int)(unsigned __int8)v16 / 0xFF;
                *(v14 - 1) = v17 * BYTE1(v16) / 0xFFu;
                *(v14 - 2) = v17 * (unsigned int)BYTE2(v16) / 0xFF;
                ++v3;
                v14 += 4;
              }
              while ( v3 < pv.dsBm.bmWidthBytes * *(_DWORD *)&pv.dsBm.bmPlanes );
            }
          }
          else
          {
            dm.m_dc = (CDC *)CDrawingManager::`vftable';
            memDCDst.__vftable = (CDC_vtbl *)&memDCDst.m_hDC;
            m_clrTransparent = this->m_clrTransparent;
            if ( m_clrTransparent == -1 )
            {
              if ( !afxGlobalData.m_bInitialized )
              {
                AFX_GLOBAL_DATA::Initialize(&afxGlobalData);
                afxGlobalData.m_bInitialized = 1;
              }
              m_clrTransparent = afxGlobalData.clrBtnFace;
            }
            *(_QWORD *)&S.right = 0;
            memDCSrc.__vftable = (CDC_vtbl *)__PAIR64__(v6, bmWidthBytes);
            CDrawingManager::GrayRect(
              (CDrawingManager *)&dm.m_dc,
              (CRect *)&S.right,
              m_nGrayImageLuminancePercentage,
              m_clrTransparent,
              0xFFFFFFFF);
          }
          SelectObject(memDCDst.m_hAttribDC, *(HGDIOBJ *)&bmp.bmType);
          SelectObject(memDCSrc.m_hAttribDC, v8);
          DeleteObject(this->m_hbmImageWell);
          this->m_hbmImageWell = v11;
          v3 = 1;
        }
        else
        {
          SelectObject(memDCSrc.m_hAttribDC, v8);
          DeleteObject(v11);
        }
      }
      else
      {
        SelectObject(memDCSrc.m_hAttribDC, v8);
      }
LABEL_28:
      CDC::~CDC((CDC *)&memDCDst.m_hDC);
LABEL_29:
      CDC::~CDC((CDC *)&memDCSrc.m_hDC);
      return (unsigned int)v3;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1801774e0  mov     rax, rsp
0x1801774e3  mov     [rax+10h], rbx
0x1801774e7  mov     [rax+18h], rsi
0x1801774eb  mov     [rax+20h], rdi
0x1801774ef  push    rbp
0x1801774f0  push    r12
0x1801774f2  push    r13
0x1801774f4  push    r14
0x1801774f6  push    r15
0x1801774f8  lea     rbp, [rax-0D8h]
0x1801774ff  sub     rsp, 1B0h
0x180177506  movaps  xmmword ptr [rax-38h], xmm6
0x18017750a  mov     rax, cs:__security_cookie
0x180177511  xor     rax, rsp
0x180177514  mov     [rbp+0D0h+var_40], rax
0x18017751b  mov     rdi, this
0x18017751e  mov     r14d, 1
0x180177524  mov     [this+34h], r14d
0x180177528  mov     [this+10h], nGrayImageLuminancePercentage
0x18017752b  xor     ebx, ebx
0x18017752d  cmp     [this+0A0h], rbx
0x180177534  jz      loc_1801778BD
0x18017753a  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x180177540  jnz     short loc_180177555
0x180177542  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180177549  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18017754e  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, r14d; AFX_GLOBAL_DATA afxGlobalData ...
0x180177555  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_nBitsPerPixel, 8; AFX_GLOBAL_DATA afxGlobalData ...
0x18017755c  jle     loc_1801778BD
0x180177562  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x180177569  mov     [rsp+1D0h+memDCSrc.m_hDC], rax
0x18017756e  xorps   xmm0, xmm0
0x180177571  movdqu  xmmword ptr [rsp+1D0h+memDCSrc.m_hAttribDC], xmm0
0x180177577  mov     dword ptr [rsp+1D0h+dm.__vftable], ebx
0x18017757b  xor     ecx, ecx; hdc
0x18017757d  call    cs:__imp_CreateCompatibleDC
0x180177583  mov     rdx, rax; hDC
0x180177586  lea     this, [rsp+1D0h+memDCSrc.m_hDC]; this
0x18017758b  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180177590  lea     r8, [rbp+0D0h+bmp.bmHeight]; pv
0x180177594  mov     nGrayImageLuminancePercentage, 20h ; ' '; c
0x180177599  mov     this, [rdi+0A0h]; h
0x1801775a0  call    cs:__imp_GetObjectW
0x1801775a6  test    eax, eax
0x1801775a8  jz      loc_1801778AF
0x1801775ae  mov     r12d, [rbp+0D0h+bmp.bmWidthBytes]
0x1801775b2  mov     r13d, dword ptr [rbp+0D0h+bmp.bmPlanes]
0x1801775b6  mov     rdx, [rdi+0A0h]; h
0x1801775bd  test    rdx, rdx
0x1801775c0  jz      loc_1801778AF
0x1801775c6  mov     this, [rsp+1D0h+memDCSrc.m_hAttribDC]; hdc
0x1801775cb  call    cs:__imp_SelectObject
0x1801775d1  mov     rsi, rax
0x1801775d4  test    rax, rax
0x1801775d7  jz      loc_1801778AF
0x1801775dd  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1801775e4  mov     [rbp+0D0h+memDCDst.m_hDC], rax
0x1801775e8  xorps   xmm0, xmm0
0x1801775eb  movdqu  xmmword ptr [rbp+0D0h+memDCDst.m_hAttribDC], xmm0
0x1801775f0  mov     dword ptr [rbp+0D0h+pBits], ebx
0x1801775f3  mov     this, [rsp+1D0h+memDCSrc.m_hAttribDC]; hdc
0x1801775f8  call    cs:__imp_CreateCompatibleDC
0x1801775fe  mov     rdx, rax; hDC
0x180177601  lea     this, [rbp+0D0h+memDCDst.m_hDC]; this
0x180177605  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18017760a  mov     [rbp+0D0h+bi.bmiHeader.biHeight], 28h ; '('
0x180177611  mov     dword ptr [rbp+0D0h+bi.bmiHeader.biPlanes], r12d
0x180177615  mov     [rbp+0D0h+bi.bmiHeader.biCompression], r13d
0x180177619  mov     qword ptr [rbp+0D0h+bi.bmiHeader.biSizeImage], 200001h
0x180177621  mov     eax, r13d
0x180177624  imul    eax, r12d
0x180177628  mov     [rbp+0D0h+bi.bmiHeader.biYPelsPerMeter], eax
0x18017762b  mov     qword ptr [rbp+0D0h+bi.bmiHeader.biClrUsed], rbx
0x18017762f  mov     qword ptr [rbp+0D0h+bi.bmiColors.rgbBlue], rbx
0x180177636  mov     [rbp+0D0h+L], rbx
0x18017763a  mov     [rsp+1D0h+offset], ebx; offset
0x18017763e  mov     [rsp+1D0h+hSection], rbx; hSection
0x180177643  lea     r9, [rbp+0D0h+L]; ppvBits
0x180177647  xor     r8d, r8d; usage
0x18017764a  lea     rdx, [rbp+0D0h+bi.bmiHeader.biHeight]; pbmi
0x18017764e  mov     this, [rbp+0D0h+memDCDst.m_hAttribDC]; hdc
0x180177652  call    cs:__imp_CreateDIBSection
0x180177658  mov     r14, rax
0x18017765b  test    rax, rax
0x18017765e  jnz     short loc_180177673
0x180177660  mov     rdx, rsi; h
0x180177663  mov     this, [rsp+1D0h+memDCSrc.m_hAttribDC]; hdc
0x180177668  call    cs:__imp_SelectObject
0x18017766e  jmp     loc_1801778A5
0x180177673  mov     rdx, r14; h
0x180177676  mov     this, [rbp+0D0h+memDCDst.m_hAttribDC]; hdc
0x18017767a  call    cs:__imp_SelectObject
0x180177680  mov     qword ptr [rbp+0D0h+bmp.bmType], rax
0x180177684  test    rax, rax
0x180177687  jnz     short loc_1801776A5
0x180177689  mov     rdx, rsi; h
0x18017768c  mov     this, [rsp+1D0h+memDCSrc.m_hAttribDC]; hdc
0x180177691  call    cs:__imp_SelectObject
0x180177697  mov     this, r14; ho
0x18017769a  call    cs:__imp_DeleteObject
0x1801776a0  jmp     loc_1801778A5
0x1801776a5  mov     [rsp+1D0h+rop], 0CC0020h; rop
0x1801776ad  mov     [rsp+1D0h+y1], ebx; y1
0x1801776b1  mov     [rsp+1D0h+x1], ebx; x1
0x1801776b5  mov     rax, [rsp+1D0h+memDCSrc.m_hAttribDC]
0x1801776ba  mov     qword ptr [rsp+1D0h+offset], rax; hdcSrc
0x1801776bf  mov     dword ptr [rsp+1D0h+hSection], r13d; cy
0x1801776c4  mov     r9d, r12d; cx
0x1801776c7  xor     r8d, r8d; y
0x1801776ca  xor     nGrayImageLuminancePercentage, nGrayImageLuminancePercentage; x
0x1801776cc  mov     this, [rbp+0D0h+memDCDst.m_hAttribDC]; hdc
0x1801776d0  call    cs:__imp_BitBlt
0x1801776d6  mov     r15d, [rdi+10h]
0x1801776da  mov     eax, 82h
0x1801776df  test    r15d, r15d
0x1801776e2  cmovle  r15d, eax
0x1801776e6  cmp     dword ptr [rdi+0Ch], 20h ; ' '
0x1801776ea  jnz     loc_1801777FA
0x1801776f0  lea     r8, [rbp+0D0h+pv.dsBm.bmHeight]; pv
0x1801776f4  lea     nGrayImageLuminancePercentage, [rax-1Ah]; c
0x1801776f7  mov     this, r14; h
0x1801776fa  call    cs:__imp_GetObjectW
0x180177700  test    eax, eax
0x180177702  jz      loc_1801778A5
0x180177708  mov     eax, 20h ; ' '
0x18017770d  cmp     word ptr [rbp+0D0h+pv.dsBm.bmBits+2], ax
0x180177711  jnz     loc_1801778A5
0x180177717  mov     this, qword ptr [rbp+0D0h+pv.dsBmih.biSize]
0x18017771b  test    this, this
0x18017771e  jz      loc_1801778A5
0x180177724  mov     eax, dword ptr [rbp+0D0h+pv.dsBm.bmPlanes]
0x180177727  imul    eax, [rbp+0D0h+pv.dsBm.bmWidthBytes]
0x18017772b  test    eax, eax
0x18017772d  jle     loc_180177870
0x180177733  movd    xmm6, r15d
0x180177738  cvtdq2pd xmm6, xmm6
0x18017773c  mulsd   xmm6, cs:__real@3f847ae147ae147b
0x180177744  lea     r15, [this+2]
0x180177748  mov     r12d, 80808081h
0x18017774e  movzx   ecx, byte ptr [r15-1]
0x180177753  shl     ecx, 8
0x180177756  movzx   eax, byte ptr [r15-2]
0x18017775b  shl     eax, 10h
0x18017775e  or      ecx, eax
0x180177760  movzx   eax, byte ptr [r15]
0x180177764  or      ecx, eax; rgb
0x180177766  lea     r9, [rbp+0D0h+var_118]; L
0x18017776a  lea     r8, [rsp+1D0h+S+8]; S
0x18017776f  lea     rdx, [rbp+0D0h+dm.m_dc]; H
0x180177773  call    ?RGBtoHSL@CDrawingManager@@SAXKPEAN00@Z; CDrawingManager::RGBtoHSL(ulong,double *,double *,double *)
0x180177778  xorps   xmm2, xmm2; S
0x18017777b  movsd   xmm1, [rbp+0D0h+var_118]; L
0x180177780  movsd   xmm0, [rbp+0D0h+dm.m_dc]; H
0x180177785  call    ?HLStoRGB_ONE@CDrawingManager@@SAKNNN@Z; CDrawingManager::HLStoRGB_ONE(double,double,double)
0x18017778a  mov     ecx, eax; srcPixel
0x18017778c  movaps  xmm3, xmm6; percentB
0x18017778f  movaps  xmm2, xmm6; percentG
0x180177792  movaps  xmm1, xmm6; percentR
0x180177795  call    ?PixelAlpha@CDrawingManager@@SAKKNNN@Z; CDrawingManager::PixelAlpha(ulong,double,double,double)
0x18017779a  mov     r8d, eax
0x18017779d  movzx   r9d, byte ptr [r15+1]
0x1801777a2  movzx   ecx, al
0x1801777a5  imul    ecx, r9d
0x1801777a9  mov     eax, r12d
0x1801777ac  mul     ecx
0x1801777ae  shr     nGrayImageLuminancePercentage, 7
0x1801777b1  mov     [r15], dl
0x1801777b4  movzx   ecx, r8w
0x1801777b8  shr     ecx, 8
0x1801777bb  imul    ecx, r9d
0x1801777bf  mov     eax, r12d
0x1801777c2  mul     ecx
0x1801777c4  shr     nGrayImageLuminancePercentage, 7
0x1801777c7  mov     [r15-1], dl
0x1801777cb  shr     r8d, 10h
0x1801777cf  movzx   ecx, r8b
0x1801777d3  imul    ecx, r9d
0x1801777d7  mov     eax, r12d
0x1801777da  mul     ecx
0x1801777dc  shr     nGrayImageLuminancePercentage, 7
0x1801777df  mov     [r15-2], dl
0x1801777e3  inc     ebx
0x1801777e5  lea     r15, [r15+4]
0x1801777e9  mov     eax, dword ptr [rbp+0D0h+pv.dsBm.bmPlanes]
0x1801777ec  imul    eax, [rbp+0D0h+pv.dsBm.bmWidthBytes]
0x1801777f0  cmp     ebx, eax
0x1801777f2  jl      loc_18017774E
0x1801777f8  jmp     short loc_180177870
0x1801777fa  lea     rax, ??_7CDrawingManager@@6B@; const CDrawingManager::`vftable'
0x180177801  mov     [rbp+0D0h+dm.m_dc], rax
0x180177805  lea     rax, [rbp+0D0h+memDCDst.m_hDC]
0x180177809  mov     [rbp+0D0h+memDCDst.__vftable], rax
0x18017780d  mov     r9d, [rdi+0D8h]
0x180177814  cmp     r9d, 0FFFFFFFFh
0x180177818  jnz     short loc_18017783F
0x18017781a  cmp     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, ebx; AFX_GLOBAL_DATA afxGlobalData ...
0x180177820  jnz     short loc_180177838
0x180177822  lea     this, ?afxGlobalData@@3UAFX_GLOBAL_DATA@@A; this
0x180177829  call    ?Initialize@AFX_GLOBAL_DATA@@QEAAXXZ; AFX_GLOBAL_DATA::Initialize(void)
0x18017782e  mov     cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.m_bInitialized, 1; AFX_GLOBAL_DATA afxGlobalData ...
0x180177838  mov     r9d, cs:?afxGlobalData@@3UAFX_GLOBAL_DATA@@A.clrBtnFace; AFX_GLOBAL_DATA afxGlobalData ...
0x18017783f  mov     qword ptr [rsp+1D0h+S+8], rbx
0x180177844  mov     dword ptr [rsp+1D0h+memDCSrc.__vftable], r12d
0x180177849  mov     dword ptr [rsp+1D0h+memDCSrc.__vftable+4], r13d
0x18017784e  movaps  xmm0, [rsp+1D0h+S+8]
0x180177853  movdqa  [rsp+1D0h+S+8], xmm0
0x180177859  or      dword ptr [rsp+1D0h+hSection], 0FFFFFFFFh
0x18017785e  mov     r8d, r15d
0x180177861  lea     rdx, [rsp+1D0h+S+8]
0x180177866  lea     this, [rbp+0D0h+dm.m_dc]
0x18017786a  call    ?GrayRect@CDrawingManager@@QEAAHVCRect@@HKK@Z; CDrawingManager::GrayRect(CRect,int,ulong,ulong)
0x18017786f  nop
0x180177870  mov     rdx, qword ptr [rbp+0D0h+bmp.bmType]; h
0x180177874  mov     this, [rbp+0D0h+memDCDst.m_hAttribDC]; hdc
0x180177878  call    cs:__imp_SelectObject
0x18017787e  mov     rdx, rsi; h
0x180177881  mov     this, [rsp+1D0h+memDCSrc.m_hAttribDC]; hdc
0x180177886  call    cs:__imp_SelectObject
0x18017788c  mov     this, [rdi+0A0h]; ho
0x180177893  call    cs:__imp_DeleteObject
0x180177899  mov     [rdi+0A0h], r14
0x1801778a0  mov     ebx, 1
0x1801778a5  lea     this, [rbp+0D0h+memDCDst.m_hDC]; this
0x1801778a9  call    ??1CDC@@UEAA@XZ; CDC::~CDC(void)
0x1801778ae  nop
0x1801778af  lea     this, [rsp+1D0h+memDCSrc.m_hDC]; this
0x1801778b4  call    ??1CDC@@UEAA@XZ; CDC::~CDC(void)
0x1801778b9  mov     eax, ebx
0x1801778bb  jmp     short loc_1801778C0
0x1801778bd  mov     eax, r14d
0x1801778c0  mov     this, [rbp+0D0h+var_40]
0x1801778c7  xor     this, rsp; StackCookie
0x1801778ca  call    __security_check_cookie
0x1801778cf  lea     r11, [rsp+1D0h+var_20]
0x1801778d7  mov     rbx, [r11+38h]
0x1801778db  mov     rsi, [r11+40h]
0x1801778df  mov     rdi, [r11+48h]
0x1801778e3  movaps  xmm6, xmmword ptr [r11-10h]
0x1801778e8  mov     rsp, r11
0x1801778eb  pop     r15
0x1801778ed  pop     r14
0x1801778ef  pop     r13
0x1801778f1  pop     r12
0x1801778f3  pop     rbp
0x1801778f4  retn
```
