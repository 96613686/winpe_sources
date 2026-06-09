# CMDIChildWndEx::OnTaskbarTabThumbnailStretch(HBITMAP__ *,CRect const &,HBITMAP__ *,CRect const &)

- ea: `0x180088a80`
- end: `0x180088c29`
- name: `?OnTaskbarTabThumbnailStretch@CMDIChildWndEx@@UEAAHPEAUHBITMAP__@@AEBVCRect@@01@Z`
- size: `425`
- prototype: `int __fastcall(CMDIChildWndEx *this, HBITMAP__ *hBmpDst, const CRect *rectDst, HBITMAP__ *hBmpSrc, const CRect *rectSrc)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180088a80`
- `0x180089efc`
- `0x18008a040`
- `0x18008a148`
- `0x18008a2a0`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b0630`
- `0x1802b06e0`

## import_xrefs

- `GDI32!DeleteDC` at `0x180088bec`
- `GDI32!DeleteDC` at `0x180088bec`
- `GDI32!SelectObject` at `0x180088b17`
- `GDI32!SelectObject` at `0x180088bce`
- `GDI32!SelectObject` at `0x180088b17`
- `GDI32!SelectObject` at `0x180088bce`
- `GDI32!CreateCompatibleDC` at `0x180088afe`
- `GDI32!CreateCompatibleDC` at `0x180088afe`
- `gdiplus!GdipDeleteGraphics` at `0x180088bb2`
- `gdiplus!GdipDeleteGraphics` at `0x180088bb2`
- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x180088b43`
- `gdiplus!GdipCreateBitmapFromHBITMAP` at `0x180088b43`
- `gdiplus!GdipDrawImageRectI` at `0x180088ba1`
- `gdiplus!GdipDrawImageRectI` at `0x180088ba1`
- `gdiplus!GdipSetInterpolationMode` at `0x180088b77`
- `gdiplus!GdipSetInterpolationMode` at `0x180088b77`
- `gdiplus!GdipCreateFromHDC` at `0x180088b65`
- `gdiplus!GdipCreateFromHDC` at `0x180088b65`
- `gdiplus!GdipDisposeImage` at `0x180088b51`
- `gdiplus!GdipDisposeImage` at `0x180088bbc`
- `gdiplus!GdipDisposeImage` at `0x180088b51`
- `gdiplus!GdipDisposeImage` at `0x180088bbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_BOOL8 __fastcall CMDIChildWndEx::OnTaskbarTabThumbnailStretch(
        CMDIChildWndEx *this,
        HBITMAP__ *hBmpDst,
        const CRect *rectDst,
        HBITMAP__ *hBmpSrc)
{
  HDC CompatibleDC; // rax
  HGDIOBJ v9; // rsi
  HDC__ *m_hAttribDC; // rbx
  BOOL v11; // edi
  CDC_vtbl *v12; // rbx
  HDC v13; // rax
  CDC dc; // [rsp+38h] [rbp-61h] BYREF
  CClientDC dcClient; // [rsp+58h] [rbp-41h] BYREF
  ATL::CImage image; // [rsp+80h] [rbp-19h] BYREF
  __int64 v18; // [rsp+110h] [rbp+77h] BYREF

  if ( !hBmpSrc || !hBmpDst )
    return 0;
  ATL::CImage::CImage((ATL::CImage *)&image.m_hBitmap);
  ATL::CImage::Attach((ATL::CImage *)&image.m_hBitmap, hBmpSrc, DIBOR_DEFAULT);
  CClientDC::CClientDC((CClientDC *)&dcClient.m_hDC, this);
  dc.m_hDC = (HDC__ *)CDC::`vftable';
  *(_OWORD *)&dc.m_hAttribDC = 0;
  LODWORD(dcClient.__vftable) = 0;
  CompatibleDC = CreateCompatibleDC(dcClient.m_hAttribDC);
  CDC::Attach((CDC *)&dc.m_hDC, CompatibleDC);
  v9 = SelectObject(dc.m_hAttribDC, hBmpDst);
  m_hAttribDC = dc.m_hAttribDC;
  if ( ATL::CImage::InitGDIPlus() )
  {
    v18 = 0;
    if ( !(unsigned int)GdipCreateBitmapFromHBITMAP(image.m_pBits, 0, &v18) )
    {
      dc.__vftable = 0;
      GdipCreateFromHDC(m_hAttribDC, &dc);
      v12 = dc.__vftable;
      GdipSetInterpolationMode(dc.__vftable, 7);
      v11 = GdipDrawImageRectI(v12, v18, (unsigned int)rectDst->left) == 0;
      GdipDeleteGraphics(v12);
      GdipDisposeImage(v18);
      goto LABEL_8;
    }
    GdipDisposeImage(v18);
  }
  v11 = 0;
LABEL_8:
  if ( v9 )
    SelectObject(dc.m_hAttribDC, v9);
  dc.m_hDC = (HDC__ *)CDC::`vftable';
  if ( dc.m_hAttribDC )
  {
    v13 = CDC::Detach((CDC *)&dc.m_hDC);
    DeleteDC(v13);
  }
  CClientDC::~CClientDC((CClientDC *)&dcClient.m_hDC);
  ATL::CImage::~CImage((ATL::CImage *)&image.m_hBitmap);
  return v11;
}

```

## disassembly

```asm
0x180088a80  mov     rax, rsp
0x180088a83  mov     [rax+8], rbx
0x180088a87  mov     [rax+10h], rsi
0x180088a8b  mov     [rax+18h], rdi
0x180088a8f  push    rbp
0x180088a90  push    r12
0x180088a92  push    r14
0x180088a94  lea     rbp, [rax-57h]
0x180088a98  sub     rsp, 0D0h
0x180088a9f  mov     rdi, hBmpSrc
0x180088aa2  mov     r14, rectDst
0x180088aa5  mov     rbx, hBmpDst
0x180088aa8  mov     rsi, this
0x180088aab  test    hBmpSrc, hBmpSrc
0x180088aae  jz      loc_180088C0A
0x180088ab4  test    hBmpDst, hBmpDst
0x180088ab7  jz      loc_180088C0A
0x180088abd  lea     this, [rbp+4Fh+image.m_hBitmap]; this
0x180088ac1  call    ??0CImage@ATL@@QEAA@XZ; ATL::CImage::CImage(void)
0x180088ac6  nop
0x180088ac7  xor     r8d, r8d; eOrientation
0x180088aca  mov     hBmpDst, rdi; hBitmap
0x180088acd  lea     this, [rbp+4Fh+image.m_hBitmap]; this
0x180088ad1  call    ?Attach@CImage@ATL@@QEAAXPEAUHBITMAP__@@W4DIBOrientation@12@@Z; ATL::CImage::Attach(HBITMAP__ *,ATL::CImage::DIBOrientation)
0x180088ad6  mov     hBmpDst, rsi; pWnd
0x180088ad9  lea     this, [rbp+4Fh+dcClient.m_hDC]; this
0x180088add  call    ??0CClientDC@@QEAA@PEAVCWnd@@@Z; CClientDC::CClientDC(CWnd *)
0x180088ae2  nop
0x180088ae3  lea     r12, ??_7CDC@@6B@; const CDC::`vftable'
0x180088aea  mov     [rbp+4Fh+dc.m_hDC], r12
0x180088aee  xorps   xmm0, xmm0
0x180088af1  movdqu  xmmword ptr [rbp+4Fh+dc.m_hAttribDC], xmm0
0x180088af6  and     dword ptr [rbp+4Fh+dcClient.__vftable], 0
0x180088afa  mov     this, [rbp+4Fh+dcClient.m_hAttribDC]; hdc
0x180088afe  call    cs:__imp_CreateCompatibleDC
0x180088b04  mov     hBmpDst, rax; hDC
0x180088b07  lea     this, [rbp+4Fh+dc.m_hDC]; this
0x180088b0b  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x180088b10  mov     hBmpDst, rbx; h
0x180088b13  mov     this, [rbp+4Fh+dc.m_hAttribDC]; hdc
0x180088b17  call    cs:__imp_SelectObject
0x180088b1d  mov     rsi, rax
0x180088b20  mov     rbx, [rbp+4Fh+dc.m_hAttribDC]
0x180088b24  call    ?InitGDIPlus@CImage@ATL@@CA_NXZ; ATL::CImage::InitGDIPlus(void)
0x180088b29  test    al, al
0x180088b2b  jnz     short loc_180088B34
0x180088b2d  xor     edi, edi
0x180088b2f  jmp     loc_180088BC2
0x180088b34  and     [rbp+4Fh+arg_18], 0
0x180088b39  lea     rectDst, [rbp+4Fh+arg_18]
0x180088b3d  xor     edx, edx
0x180088b3f  mov     this, [rbp+4Fh+image.m_pBits]
0x180088b43  call    cs:__imp_GdipCreateBitmapFromHBITMAP
0x180088b49  test    eax, eax
0x180088b4b  jz      short loc_180088B59
0x180088b4d  mov     this, [rbp+4Fh+arg_18]
0x180088b51  call    cs:__imp_GdipDisposeImage
0x180088b57  jmp     short loc_180088B2D
0x180088b59  and     [rbp+4Fh+dc.__vftable], 0
0x180088b5e  lea     hBmpDst, [rbp+4Fh+dc]
0x180088b62  mov     this, rbx
0x180088b65  call    cs:__imp_GdipCreateFromHDC
0x180088b6b  mov     rbx, [rbp+4Fh+dc.__vftable]
0x180088b6f  mov     edx, 7
0x180088b74  mov     this, rbx
0x180088b77  call    cs:__imp_GdipSetInterpolationMode
0x180088b7d  mov     r9d, [r14+4]
0x180088b81  mov     edx, [r14+0Ch]
0x180088b85  sub     edx, r9d
0x180088b88  mov     eax, [r14+8]
0x180088b8c  sub     eax, [r14]
0x180088b8f  mov     [rsp+0E0h+var_B8], edx
0x180088b93  mov     [rsp+0E0h+var_C0], eax
0x180088b97  mov     r8d, [r14]
0x180088b9a  mov     hBmpDst, [rbp+4Fh+arg_18]
0x180088b9e  mov     this, rbx
0x180088ba1  call    cs:__imp_GdipDrawImageRectI
0x180088ba7  xor     edi, edi
0x180088ba9  test    eax, eax
0x180088bab  setz    dil
0x180088baf  mov     this, rbx
0x180088bb2  call    cs:__imp_GdipDeleteGraphics
0x180088bb8  mov     this, [rbp+4Fh+arg_18]
0x180088bbc  call    cs:__imp_GdipDisposeImage
0x180088bc2  test    rsi, rsi
0x180088bc5  jz      short loc_180088BD5
0x180088bc7  mov     hBmpDst, rsi; h
0x180088bca  mov     this, [rbp+4Fh+dc.m_hAttribDC]; hdc
0x180088bce  call    cs:__imp_SelectObject
0x180088bd4  nop
0x180088bd5  mov     [rbp+4Fh+dc.m_hDC], r12
0x180088bd9  cmp     [rbp+4Fh+dc.m_hAttribDC], 0
0x180088bde  jz      short loc_180088BF3
0x180088be0  lea     this, [rbp+4Fh+dc.m_hDC]; this
0x180088be4  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x180088be9  mov     this, rax; hdc
0x180088bec  call    cs:__imp_DeleteDC
0x180088bf2  nop
0x180088bf3  lea     this, [rbp+4Fh+dcClient.m_hDC]; this
0x180088bf7  call    ??1CClientDC@@UEAA@XZ; CClientDC::~CClientDC(void)
0x180088bfc  nop
0x180088bfd  lea     this, [rbp+4Fh+image.m_hBitmap]; this
0x180088c01  call    ??1CImage@ATL@@UEAA@XZ; ATL::CImage::~CImage(void)
0x180088c06  mov     eax, edi
0x180088c08  jmp     short loc_180088C0C
0x180088c0a  xor     eax, eax
0x180088c0c  lea     r11, [rsp+0E0h+var_10]
0x180088c14  mov     rbx, [r11+20h]
0x180088c18  mov     rsi, [r11+28h]
0x180088c1c  mov     rdi, [r11+30h]
0x180088c20  mov     rsp, r11
0x180088c23  pop     r14
0x180088c25  pop     r12
0x180088c27  pop     rbp
0x180088c28  retn
```
