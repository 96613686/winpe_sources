# CDrawingManager::DrawShadow(CRect,int,int,int,CBitmap *,CBitmap *,ulong,int)

- ea: `0x18005aa00`
- end: `0x18005b130`
- name: `?DrawShadow@CDrawingManager@@QEAAHVCRect@@HHHPEAVCBitmap@@1KH@Z`
- size: `1840`
- prototype: `int __fastcall(CDrawingManager *this, CRect rect, int nDepth, int iMinBrightness, int iMaxBrightness, CBitmap *pBmpSaveBottom, CBitmap *pBmpSaveRight, unsigned int clrBase, int bRightShadow)`
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18018c390`
- `0x180193b20`
- `0x1801ae120`
- `0x1801b6bb0`
- `0x1801b7600`

## callees

- `0x18001d090`
- `0x180058150`
- `0x18005aa00`
- `0x18005d0e0`
- `0x180231d70`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802b09a0`
- `0x1802b09d0`

## import_xrefs

- `USER32!DrawStateW` at `0x18005aaf6`
- `USER32!DrawStateW` at `0x18005ab3a`
- `USER32!DrawStateW` at `0x18005aaf6`
- `USER32!DrawStateW` at `0x18005ab3a`
- `USER32!IsRectEmpty` at `0x18005aa4d`
- `USER32!IsRectEmpty` at `0x18005aa4d`
- `GDI32!DeleteDC` at `0x18005b0d4`
- `GDI32!DeleteDC` at `0x18005b116`
- `GDI32!DeleteDC` at `0x18005b0d4`
- `GDI32!DeleteDC` at `0x18005b116`
- `GDI32!BitBlt` at `0x18005acb1`
- `GDI32!BitBlt` at `0x18005af56`
- `GDI32!BitBlt` at `0x18005afef`
- `GDI32!BitBlt` at `0x18005b072`
- `GDI32!BitBlt` at `0x18005acb1`
- `GDI32!BitBlt` at `0x18005af56`
- `GDI32!BitBlt` at `0x18005afef`
- `GDI32!BitBlt` at `0x18005b072`
- `GDI32!CreateCompatibleBitmap` at `0x18005abde`
- `GDI32!CreateCompatibleBitmap` at `0x18005af76`
- `GDI32!CreateCompatibleBitmap` at `0x18005b00a`
- `GDI32!CreateCompatibleBitmap` at `0x18005abde`
- `GDI32!CreateCompatibleBitmap` at `0x18005af76`
- `GDI32!CreateCompatibleBitmap` at `0x18005b00a`
- `GDI32!DeleteObject` at `0x18005b097`
- `GDI32!DeleteObject` at `0x18005b097`
- `GDI32!SelectObject` at `0x18005ac17`
- `GDI32!SelectObject` at `0x18005ac67`
- `GDI32!SelectObject` at `0x18005af95`
- `GDI32!SelectObject` at `0x18005b024`
- `GDI32!SelectObject` at `0x18005b085`
- `GDI32!SelectObject` at `0x18005ac17`
- `GDI32!SelectObject` at `0x18005ac67`
- `GDI32!SelectObject` at `0x18005af95`
- `GDI32!SelectObject` at `0x18005b024`
- `GDI32!SelectObject` at `0x18005b085`
- `GDI32!CreateCompatibleDC` at `0x18005ab98`
- `GDI32!CreateCompatibleDC` at `0x18005ab98`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDrawingManager::DrawShadow(
        CDrawingManager *this,
        CRect *rect,
        unsigned int nDepth,
        int iMinBrightness,
        int iMaxBrightness,
        CBitmap *pBmpSaveBottom,
        CBitmap *pBmpSaveRight,
        unsigned int clrBase,
        int bRightShadow)
{
  __int64 cy; // rbx
  CDrawingManager *v11; // rsi
  CBitmap *v12; // r14
  int v13; // r15d
  int y; // ecx
  int v15; // r12d
  void *m_hObject; // r9
  int x; // eax
  int left; // eax
  CDC *m_dc; // rax
  HDC m_hDC; // rcx
  HDC CompatibleDC; // rax
  int v23; // r12d
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v25; // rax
  HBITMAP__ *v26; // rax
  int v27; // ecx
  HDC v28; // rax
  int v29; // r12d
  int v30; // r13d
  int v31; // edx
  int v32; // ecx
  int cx; // eax
  int v34; // r10d
  int v35; // r8d
  int v36; // esi
  int v37; // r14d
  int v38; // r15d
  int v39; // r14d
  int v40; // esi
  int v41; // r14d
  int v42; // esi
  int v43; // esi
  int v44; // r14d
  int v45; // r12d
  bool v46; // zf
  int v47; // edx
  HBITMAP v48; // rax
  HGDIOBJ v49; // rax
  int right; // edx
  CDC *v51; // rax
  HDC v52; // rcx
  HBITMAP v53; // rax
  HGDIOBJ v54; // rax
  int v55; // eax
  HDC v56; // rcx
  HGDIOBJ v57; // rax
  HDC v58; // rax
  HDC v59; // rax
  int v60; // [rsp+50h] [rbp-B0h]
  int v61; // [rsp+54h] [rbp-ACh]
  int v62; // [rsp+58h] [rbp-A8h]
  BOOL v63; // [rsp+5Ch] [rbp-A4h]
  int v64; // [rsp+60h] [rbp-A0h]
  int v65; // [rsp+64h] [rbp-9Ch]
  int v67; // [rsp+68h] [rbp-98h]
  CDC dcMem; // [rsp+70h] [rbp-90h] BYREF
  int v69; // [rsp+90h] [rbp-70h]
  int v70; // [rsp+94h] [rbp-6Ch]
  unsigned int *pBits; // [rsp+98h] [rbp-68h] BYREF
  CSize size; // [rsp+A0h] [rbp-60h] BYREF
  CGdiObject *v73; // [rsp+A8h] [rbp-58h]
  CBitmap bmpMem; // [rsp+B0h] [rbp-50h] BYREF
  int v75; // [rsp+C0h] [rbp-40h]
  RECT v76; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v77; // [rsp+E0h] [rbp-20h]
  CDrawingManager *v78; // [rsp+E8h] [rbp-18h]
  CBitmap *v79; // [rsp+F0h] [rbp-10h]
  CGdiObject *v80; // [rsp+F8h] [rbp-8h]
  HGDIOBJ ho; // [rsp+100h] [rbp+0h]

  cy = nDepth;
  v11 = this;
  v78 = this;
  v12 = pBmpSaveBottom;
  v79 = pBmpSaveBottom;
  v73 = pBmpSaveRight;
  if ( !nDepth || IsRectEmpty(rect) )
    return 1;
  v13 = rect->right - rect->left;
  v64 = v13;
  y = rect->top;
  v15 = rect->bottom - y;
  v61 = v15;
  v63 = bRightShadow == 0;
  if ( v73 )
  {
    m_hObject = v73->m_hObject;
    if ( m_hObject )
    {
      if ( pBmpSaveBottom && pBmpSaveBottom->m_hObject )
      {
        if ( bRightShadow )
          x = rect->right;
        else
          x = rect->left - cy;
        DrawStateW(v11->m_dc->m_hDC, 0, 0, (LPARAM)m_hObject, 0, x, y, cy, cy + v15, 4u);
        left = rect->left;
        if ( !bRightShadow )
          left -= cy;
        DrawStateW(v11->m_dc->m_hDC, 0, 0, (LPARAM)pBmpSaveBottom->m_hObject, 0, left, rect->bottom, cy + v13, cy, 4u);
        return 1;
      }
LABEL_72:
      AfxThrowInvalidArgException();
    }
  }
  if ( pBmpSaveBottom && pBmpSaveBottom->m_hObject )
    goto LABEL_72;
  dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcMem.m_hDC, 0, 20);
  m_dc = v11->m_dc;
  m_hDC = 0;
  if ( m_dc )
    m_hDC = m_dc->m_hDC;
  CompatibleDC = CreateCompatibleDC(m_hDC);
  if ( CDC::Attach(&dcMem, CompatibleDC) )
  {
    bmpMem.m_hObject = 0;
    bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
    v23 = cy + v15;
    CompatibleBitmap = CreateCompatibleBitmap(v11->m_dc->m_hDC, (int)cy + v13, v23);
    if ( CGdiObject::Attach(&bmpMem, CompatibleBitmap) )
    {
      v25 = SelectObject(dcMem.m_hDC, bmpMem.m_hObject);
      v80 = CGdiObject::FromHandle(v25);
      if ( !v80 )
        AfxThrowInvalidArgException();
      size.cx = cy + v13;
      size.cy = v23;
      v26 = CDrawingManager::CreateBitmap_32(&size, (void **)&pBits);
      ho = v26;
      if ( v26 )
      {
        if ( pBits )
        {
          SelectObject(dcMem.m_hDC, v26);
          v27 = rect->left;
          if ( !bRightShadow )
            v27 -= cy;
          v28 = (HDC)v11->m_dc;
          if ( v28 )
            v28 = (HDC)*((_QWORD *)v28 + 1);
          BitBlt(dcMem.m_hDC, 0, 0, cy + v13, v23, v28, v27, rect->top, 0xCC0020u);
          v75 = (iMaxBrightness - iMinBrightness) / (int)cy;
          v29 = v61;
          if ( (int)cy > 0 )
          {
            v30 = 2 * cy;
            v62 = 2 * cy;
            v31 = v13;
            v60 = v13;
            v65 = iMaxBrightness - (iMaxBrightness - iMinBrightness) / (int)cy * cy;
            v32 = v13 - cy;
            v70 = v13 - cy;
            cx = v61 - v13;
            size.cx = v61 - v13;
            v34 = v61 - v13 + 1;
            v69 = v34;
            v35 = cy - v13;
            v67 = cy - v13;
            v77 = cy;
            do
            {
              v36 = v29;
              v37 = v30 + v32 + cx;
              if ( v29 < v37 )
              {
                v38 = v35 + v31;
                do
                {
                  v76 = rect->tagRECT;
                  CDrawingManager::SetAlphaPixel(pBits, (CRect *)&v76, v38, v36++, v65, cy, clrBase, v63);
                }
                while ( v36 < v37 );
                v13 = v64;
                v29 = v61;
                v30 = v62;
                v31 = v60;
                v34 = v69;
              }
              v39 = v30;
              if ( v30 < v31 )
              {
                v40 = v60 + v34;
                do
                {
                  v76 = rect->tagRECT;
                  CDrawingManager::SetAlphaPixel(pBits, (CRect *)&v76, v39++, v40 - 1, iMaxBrightness, cy, clrBase, v63);
                }
                while ( v39 < v60 );
                v13 = v64;
                v29 = v61;
                v30 = v62;
                v31 = v60;
              }
              v41 = v30;
              if ( v30 < v31 + v69 )
              {
                v42 = v31 + v69;
                do
                {
                  v76 = rect->tagRECT;
                  CDrawingManager::SetAlphaPixel(pBits, (CRect *)&v76, v60, v41++, iMaxBrightness, cy, clrBase, v63);
                }
                while ( v41 < v42 );
                v13 = v64;
                v29 = v61;
                v30 = v62;
                v31 = v60;
              }
              v32 = v70;
              if ( v13 < v70 + v30 )
              {
                v43 = v31 + v67;
                v44 = v70 + v30;
                v45 = v13;
                do
                {
                  v76 = rect->tagRECT;
                  CDrawingManager::SetAlphaPixel(pBits, (CRect *)&v76, v45++, v43, v65, cy, clrBase, v63);
                }
                while ( v45 < v44 );
                v13 = v64;
                v29 = v61;
                v30 = v62;
                v31 = v60;
                v32 = v70;
              }
              iMaxBrightness -= v75;
              v60 = ++v31;
              v65 += v75;
              v62 = --v30;
              v46 = v77-- == 1;
              v35 = v67;
              cx = size.cx;
              v34 = size.cx + 1;
            }
            while ( !v46 );
            v11 = v78;
            v12 = v79;
          }
          v47 = rect->left;
          if ( !bRightShadow )
            v47 -= cy;
          BitBlt(v11->m_dc->m_hDC, v47, rect->top, cy + v13, cy + v29, dcMem.m_hDC, 0, 0, 0xCC0020u);
          if ( v73 )
          {
            v48 = CreateCompatibleBitmap(v11->m_dc->m_hDC, (int)cy + 1, (int)cy + v29);
            CGdiObject::Attach(v73, v48);
            v49 = SelectObject(dcMem.m_hDC, v73->m_hObject);
            CGdiObject::FromHandle(v49);
            if ( bRightShadow )
              right = rect->right;
            else
              right = 0;
            v51 = v11->m_dc;
            if ( v51 )
              v52 = v51->m_hDC;
            else
              v52 = 0;
            BitBlt(dcMem.m_hDC, 0, 0, cy, cy + v29, v52, right, rect->top, 0xCC0020u);
          }
          if ( v12 )
          {
            v53 = CreateCompatibleBitmap(v11->m_dc->m_hDC, (int)cy + v13, (int)cy + 1);
            CGdiObject::Attach(v12, v53);
            v54 = SelectObject(dcMem.m_hDC, v12->m_hObject);
            CGdiObject::FromHandle(v54);
            v55 = rect->left;
            if ( !bRightShadow )
              v55 -= cy;
            v56 = (HDC)v11->m_dc;
            if ( v56 )
              v56 = (HDC)*((_QWORD *)v56 + 1);
            BitBlt(dcMem.m_hDC, 0, 0, cy + v13, cy, v56, v55, rect->bottom, 0xCC0020u);
          }
          v57 = SelectObject(dcMem.m_hDC, v80->m_hObject);
          CGdiObject::FromHandle(v57);
          DeleteObject(ho);
          bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
          CGdiObject::~CGdiObject(&bmpMem);
          dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
          if ( dcMem.m_hDC )
          {
            v58 = CDC::Detach(&dcMem);
            DeleteDC(v58);
          }
          return 1;
        }
      }
    }
    bmpMem.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
    CGdiObject::~CGdiObject(&bmpMem);
    dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  }
  else
  {
    dcMem.__vftable = (CDC_vtbl *)CDC::`vftable';
  }
  if ( dcMem.m_hDC )
  {
    v59 = CDC::Detach(&dcMem);
    DeleteDC(v59);
  }
  return 0;
}

```

## disassembly

```asm
0x18005aa00  mov     [rsp-8+arg_18], rbx
0x18005aa05  push    rbp
0x18005aa06  push    rsi
0x18005aa07  push    rdi
0x18005aa08  push    r12
0x18005aa0a  push    r13
0x18005aa0c  push    r14
0x18005aa0e  push    r15
0x18005aa10  lea     rbp, [rsp-10h]
0x18005aa15  sub     rsp, 110h
0x18005aa1c  mov     [rsp+140h+var_D8], iMinBrightness
0x18005aa21  mov     ebx, nDepth
0x18005aa24  mov     rdi, rect
0x18005aa27  mov     rsi, this
0x18005aa2a  mov     [rbp+40h+var_58], this
0x18005aa2e  mov     r14, [rbp+40h+arg_28]
0x18005aa32  mov     [rbp+40h+var_50], r14
0x18005aa36  mov     rax, [rbp+40h+arg_30]
0x18005aa3d  mov     [rbp+40h+var_98], rax
0x18005aa41  test    nDepth, nDepth
0x18005aa44  jz      loc_18005AB40
0x18005aa4a  mov     this, rect; lprc
0x18005aa4d  call    cs:__imp_IsRectEmpty
0x18005aa53  xor     nDepth, nDepth; qfnCallBack
0x18005aa56  test    eax, eax
0x18005aa58  jnz     loc_18005AB40
0x18005aa5e  mov     eax, [rdi]
0x18005aa60  mov     r15d, [rdi+8]
0x18005aa64  sub     r15d, eax
0x18005aa67  mov     [rsp+140h+var_E0], r15d
0x18005aa6c  mov     ecx, [rdi+4]
0x18005aa6f  mov     r12d, [rdi+0Ch]
0x18005aa73  sub     r12d, ecx
0x18005aa76  mov     [rsp+140h+var_EC], r12d
0x18005aa7b  mov     edx, nDepth
0x18005aa7e  mov     r13d, [rbp+40h+arg_40]
0x18005aa85  test    r13d, r13d
0x18005aa88  setz    dl
0x18005aa8b  mov     [rsp+140h+var_E4], edx
0x18005aa8f  mov     rect, [rbp+40h+var_98]
0x18005aa93  test    rect, rect
0x18005aa96  jz      loc_18005AB60
0x18005aa9c  mov     r9, [rect+8]; lData
0x18005aaa0  test    r9, r9
0x18005aaa3  jz      loc_18005AB60
0x18005aaa9  test    r14, r14
0x18005aaac  jz      loc_18005B12A
0x18005aab2  cmp     [r14+8], r8
0x18005aab6  jz      loc_18005B12A
0x18005aabc  mov     r10, [rsi+8]
0x18005aac0  lea     edx, [rbx+r12]
0x18005aac4  test    r13d, r13d
0x18005aac7  jnz     short loc_18005AACD
0x18005aac9  sub     eax, ebx
0x18005aacb  jmp     short loc_18005AAD0
0x18005aacd  mov     eax, [rdi+8]
0x18005aad0  mov     r12d, 4
0x18005aad6  mov     [rsp+140h+uFlags], r12d; uFlags
0x18005aadb  mov     [rsp+140h+cy], edx; cy
0x18005aadf  mov     [rsp+140h+y1], ebx; cx
0x18005aae3  mov     [rsp+140h+y], ecx; y
0x18005aae7  mov     [rsp+140h+x], eax; x
0x18005aaeb  mov     [rsp+140h+wData], r8; wData
0x18005aaf0  xor     edx, edx; hbrFore
0x18005aaf2  mov     this, [r10+8]; hdc
0x18005aaf6  call    cs:__imp_DrawStateW
0x18005aafc  mov     this, [rsi+8]
0x18005ab00  lea     edx, [rbx+r15]
0x18005ab04  mov     nDepth, [rdi+0Ch]
0x18005ab08  mov     eax, [rdi]
0x18005ab0a  test    r13d, r13d
0x18005ab0d  jnz     short loc_18005AB11
0x18005ab0f  sub     eax, ebx
0x18005ab11  mov     [rsp+140h+uFlags], r12d; uFlags
0x18005ab16  mov     [rsp+140h+cy], ebx; cy
0x18005ab1a  mov     [rsp+140h+y1], edx; cx
0x18005ab1e  mov     [rsp+140h+y], nDepth; y
0x18005ab23  mov     [rsp+140h+x], eax; x
0x18005ab27  and     [rsp+140h+wData], 0
0x18005ab2d  mov     r9, [r14+8]; lData
0x18005ab31  xor     nDepth, nDepth; qfnCallBack
0x18005ab34  xor     edx, edx; hbrFore
0x18005ab36  mov     this, [this+8]; hdc
0x18005ab3a  call    cs:__imp_DrawStateW
0x18005ab40  mov     eax, 1
0x18005ab45  mov     rbx, [rsp+140h+arg_18]
0x18005ab4d  add     rsp, 110h
0x18005ab54  pop     r15
0x18005ab56  pop     r14
0x18005ab58  pop     r13
0x18005ab5a  pop     r12
0x18005ab5c  pop     rdi
0x18005ab5d  pop     rsi
0x18005ab5e  pop     rbp
0x18005ab5f  retn
0x18005ab60  test    r14, r14
0x18005ab63  jz      short loc_18005AB6F
0x18005ab65  cmp     [r14+8], r8
0x18005ab69  jnz     loc_18005B12A
0x18005ab6f  lea     r13, ??_7CDC@@6B@; const CDC::`vftable'
0x18005ab76  mov     [rsp+140h+dcMem.__vftable], r13
0x18005ab7b  xorps   xmm0, xmm0
0x18005ab7e  movdqu  xmmword ptr [rsp+140h+dcMem.m_hDC], xmm0
0x18005ab84  mov     [rbp+40h+dcMem.m_bPrinting], nDepth
0x18005ab88  mov     rax, [rsi+8]
0x18005ab8c  test    rax, rax
0x18005ab8f  mov     this, r8
0x18005ab92  jz      short loc_18005AB98
0x18005ab94  mov     this, [rax+8]; hdc
0x18005ab98  call    cs:__imp_CreateCompatibleDC
0x18005ab9e  mov     rect, rax; hDC
0x18005aba1  lea     this, [rsp+140h+dcMem]; this
0x18005aba6  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x18005abab  test    eax, eax
0x18005abad  jnz     short loc_18005ABB9
0x18005abaf  mov     [rsp+140h+dcMem.__vftable], r13
0x18005abb4  jmp     loc_18005B101
0x18005abb9  and     [rbp+40h+bmpMem.m_hObject], 0
0x18005abbe  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005abc5  mov     [rbp+40h+bmpMem.__vftable], rax
0x18005abc9  mov     this, [rsi+8]
0x18005abcd  add     r12d, ebx
0x18005abd0  lea     r13d, [rbx+r15]
0x18005abd4  mov     nDepth, r12d; cy
0x18005abd7  mov     edx, r13d; cx
0x18005abda  mov     this, [this+8]; hdc
0x18005abde  call    cs:__imp_CreateCompatibleBitmap
0x18005abe4  mov     rect, rax; hObject
0x18005abe7  lea     this, [rbp+40h+bmpMem]; this
0x18005abeb  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x18005abf0  test    eax, eax
0x18005abf2  jnz     short loc_18005AC0E
0x18005abf4  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x18005abfb  mov     [rbp+40h+bmpMem.__vftable], rax
0x18005abff  lea     this, [rbp+40h+bmpMem]; this
0x18005ac03  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x18005ac08  nop
0x18005ac09  jmp     loc_18005B0F5
0x18005ac0e  mov     rect, [rbp+40h+bmpMem.m_hObject]; h
0x18005ac12  mov     this, [rsp+140h+dcMem.m_hDC]; hdc
0x18005ac17  call    cs:__imp_SelectObject
0x18005ac1d  mov     this, rax; h
0x18005ac20  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x18005ac25  mov     [rbp+40h+var_48], rax
0x18005ac29  test    rax, rax
0x18005ac2c  jz      loc_18005B124
0x18005ac32  mov     [rbp+40h+size.cx], r13d
0x18005ac36  mov     [rbp+40h+size.cy], r12d
0x18005ac3a  lea     rect, [rbp+40h+pBits]; pBits
0x18005ac3e  lea     this, [rbp+40h+size]; size
0x18005ac42  call    ?CreateBitmap_32@CDrawingManager@@SAPEAUHBITMAP__@@AEBVCSize@@PEAPEAX@Z; CDrawingManager::CreateBitmap_32(CSize const &,void * *)
0x18005ac47  mov     [rbp+40h+ho], rax
0x18005ac4b  test    rax, rax
0x18005ac4e  jz      loc_18005B0E0
0x18005ac54  cmp     [rbp+40h+pBits], 0
0x18005ac59  jz      loc_18005B0E0
0x18005ac5f  mov     rect, rax; h
0x18005ac62  mov     this, [rsp+140h+dcMem.m_hDC]; hdc
0x18005ac67  call    cs:__imp_SelectObject
0x18005ac6d  mov     edx, [rdi+4]
0x18005ac70  mov     ecx, [rdi]
0x18005ac72  cmp     [rbp+40h+arg_40], 0
0x18005ac79  jnz     short loc_18005AC7D
0x18005ac7b  sub     ecx, ebx
0x18005ac7d  mov     rax, [rsi+8]
0x18005ac81  test    rax, rax
0x18005ac84  jz      short loc_18005AC8A
0x18005ac86  mov     rax, [rax+8]
0x18005ac8a  mov     [rsp+140h+cy], 0CC0020h; rop
0x18005ac92  mov     [rsp+140h+y1], edx; y1
0x18005ac96  mov     [rsp+140h+y], ecx; x1
0x18005ac9a  mov     qword ptr [rsp+140h+x], rax; hdcSrc
0x18005ac9f  mov     dword ptr [rsp+140h+wData], r12d; cy
0x18005aca4  mov     iMinBrightness, r13d; cx
0x18005aca7  xor     nDepth, nDepth; y
0x18005acaa  xor     edx, edx; x
0x18005acac  mov     this, [rsp+140h+dcMem.m_hDC]; hdc
0x18005acb1  call    cs:__imp_BitBlt
0x18005acb7  mov     nDepth, [rbp+40h+arg_20]
0x18005acbb  mov     eax, nDepth
0x18005acbe  sub     eax, [rsp+140h+var_D8]
0x18005acc2  cdq
0x18005acc3  idiv    ebx
0x18005acc5  mov     iMinBrightness, eax
0x18005acc8  mov     [rbp+40h+var_80], eax
0x18005accb  mov     r12d, [rsp+140h+var_EC]
0x18005acd0  test    ebx, ebx
0x18005acd2  jle     loc_18005AF11
0x18005acd8  lea     r13d, [rbx+rbx]
0x18005acdc  mov     [rsp+140h+var_E8], r13d
0x18005ace1  mov     edx, r15d
0x18005ace4  mov     [rsp+140h+var_F0], edx
0x18005ace8  mov     ecx, ebx
0x18005acea  imul    ecx, iMinBrightness
0x18005acee  sub     nDepth, ecx
0x18005acf1  mov     [rsp+140h+var_DC], nDepth
0x18005acf6  mov     ecx, ebx
0x18005acf8  sub     ecx, r13d
0x18005acfb  add     ecx, r15d
0x18005acfe  mov     [rbp+40h+var_AC], ecx
0x18005ad01  mov     eax, r12d
0x18005ad04  sub     eax, r15d
0x18005ad07  mov     [rbp+40h+size.cx], eax
0x18005ad0a  lea     r10d, [rax+1]
0x18005ad0e  mov     [rbp+40h+var_B0], r10d
0x18005ad12  mov     nDepth, ebx
0x18005ad15  sub     nDepth, r15d
0x18005ad18  mov     [rsp+140h+var_D8], nDepth
0x18005ad1d  mov     [rbp+40h+var_60], rbx
0x18005ad21  mov     esi, r12d
0x18005ad24  lea     r14d, [this+rax]
0x18005ad28  add     r14d, r13d
0x18005ad2b  cmp     r12d, r14d
0x18005ad2e  jge     short loc_18005AD8F
0x18005ad30  lea     r15d, [r8+rect]
0x18005ad34  mov     r12d, [rsp+140h+var_DC]
0x18005ad39  mov     r13d, [rbp+40h+x1]
0x18005ad40  movups  xmm0, xmmword ptr [rdi]
0x18005ad43  movdqu  [rbp+40h+var_70], xmm0
0x18005ad48  mov     eax, [rsp+140h+var_E4]
0x18005ad4c  mov     [rsp+140h+y1], eax
0x18005ad50  mov     [rsp+140h+y], r13d
0x18005ad55  mov     [rsp+140h+x], ebx
0x18005ad59  mov     dword ptr [rsp+140h+wData], r12d
0x18005ad5e  mov     iMinBrightness, esi
0x18005ad61  mov     nDepth, r15d
0x18005ad64  lea     rect, [rbp+40h+var_70]
0x18005ad68  mov     this, [rbp+40h+pBits]
0x18005ad6c  call    ?SetAlphaPixel@CDrawingManager@@SAXPEAKVCRect@@HHHHKH@Z; CDrawingManager::SetAlphaPixel(ulong *,CRect,int,int,int,int,ulong,int)
0x18005ad71  inc     esi
0x18005ad73  cmp     esi, r14d
0x18005ad76  jl      short loc_18005AD40
0x18005ad78  mov     r15d, [rsp+140h+var_E0]
0x18005ad7d  mov     r12d, [rsp+140h+var_EC]
0x18005ad82  mov     r13d, [rsp+140h+var_E8]
0x18005ad87  mov     edx, [rsp+140h+var_F0]
0x18005ad8b  mov     r10d, [rbp+40h+var_B0]
0x18005ad8f  mov     r14d, r13d
0x18005ad92  cmp     r13d, edx
0x18005ad95  jge     short loc_18005ADF8
0x18005ad97  mov     r12d, [rsp+140h+var_F0]
0x18005ad9c  lea     esi, [r12+r10]
0x18005ada0  mov     r15d, [rbp+40h+arg_20]
0x18005ada4  mov     r13d, [rbp+40h+x1]
0x18005adab  movups  xmm0, xmmword ptr [rdi]
0x18005adae  movdqu  [rbp+40h+var_70], xmm0
0x18005adb3  mov     eax, [rsp+140h+var_E4]
0x18005adb7  mov     [rsp+140h+y1], eax
0x18005adbb  mov     [rsp+140h+y], r13d
0x18005adc0  mov     [rsp+140h+x], ebx
0x18005adc4  mov     dword ptr [rsp+140h+wData], r15d
0x18005adc9  lea     iMinBrightness, [rsi-1]
0x18005adcd  mov     nDepth, r14d
0x18005add0  lea     rect, [rbp+40h+var_70]
0x18005add4  mov     this, [rbp+40h+pBits]
0x18005add8  call    ?SetAlphaPixel@CDrawingManager@@SAXPEAKVCRect@@HHHHKH@Z; CDrawingManager::SetAlphaPixel(ulong *,CRect,int,int,int,int,ulong,int)
0x18005addd  inc     r14d
0x18005ade0  cmp     r14d, r12d
0x18005ade3  jl      short loc_18005ADAB
0x18005ade5  mov     r15d, [rsp+140h+var_E0]
0x18005adea  mov     r12d, [rsp+140h+var_EC]
0x18005adef  mov     r13d, [rsp+140h+var_E8]
0x18005adf4  mov     edx, [rsp+140h+var_F0]
0x18005adf8  mov     r14d, r13d
0x18005adfb  mov     eax, [rbp+40h+var_B0]
0x18005adfe  add     eax, edx
0x18005ae00  cmp     r13d, eax
0x18005ae03  jge     short loc_18005AE63
0x18005ae05  mov     r12d, [rsp+140h+var_F0]
0x18005ae0a  mov     esi, eax
0x18005ae0c  mov     r15d, [rbp+40h+arg_20]
0x18005ae10  mov     r13d, [rbp+40h+x1]
0x18005ae17  movups  xmm0, xmmword ptr [rdi]
0x18005ae1a  movdqu  [rbp+40h+var_70], xmm0
0x18005ae1f  mov     eax, [rsp+140h+var_E4]
0x18005ae23  mov     [rsp+140h+y1], eax
0x18005ae27  mov     [rsp+140h+y], r13d
0x18005ae2c  mov     [rsp+140h+x], ebx
0x18005ae30  mov     dword ptr [rsp+140h+wData], r15d
0x18005ae35  mov     iMinBrightness, r14d
0x18005ae38  mov     nDepth, r12d
0x18005ae3b  lea     rect, [rbp+40h+var_70]
0x18005ae3f  mov     this, [rbp+40h+pBits]
0x18005ae43  call    ?SetAlphaPixel@CDrawingManager@@SAXPEAKVCRect@@HHHHKH@Z; CDrawingManager::SetAlphaPixel(ulong *,CRect,int,int,int,int,ulong,int)
0x18005ae48  inc     r14d
0x18005ae4b  cmp     r14d, esi
0x18005ae4e  jl      short loc_18005AE17
0x18005ae50  mov     r15d, [rsp+140h+var_E0]
0x18005ae55  mov     r12d, [rsp+140h+var_EC]
0x18005ae5a  mov     r13d, [rsp+140h+var_E8]
0x18005ae5f  mov     edx, [rsp+140h+var_F0]
0x18005ae63  mov     ecx, [rbp+40h+var_AC]
0x18005ae66  lea     eax, [this+r13]
0x18005ae6a  cmp     r15d, eax
0x18005ae6d  jge     short loc_18005AED7
0x18005ae6f  mov     esi, [rsp+140h+var_D8]
0x18005ae73  add     esi, edx
0x18005ae75  lea     r14d, [this+r13]
0x18005ae79  mov     r12d, r15d
0x18005ae7c  mov     r15d, [rsp+140h+var_DC]
  ... truncated ...
```
