# AfxDrawDitheredBitmap(CDC *,int,int,CBitmap const &,ulong,ulong)

- ea: `0x1802b1a70`
- end: `0x1802b1eb5`
- name: `?AfxDrawDitheredBitmap@@YAXPEAVCDC@@HHAEBVCBitmap@@KK@Z`
- size: `1093`
- prototype: `void __fastcall(CDC *pDC, int x, int y, const CBitmap *rSrc, unsigned int cr1, unsigned int cr2)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18001d090`
- `0x180139950`
- `0x18023d860`
- `0x1802aee60`
- `0x1802aeeb0`
- `0x1802af220`
- `0x1802b09a0`
- `0x1802b09d0`
- `0x1802b1a70`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `USER32!FillRect` at `0x1802b1d2e`
- `USER32!FillRect` at `0x1802b1d2e`
- `GDI32!CreateBitmap` at `0x1802b1b6f`
- `GDI32!CreateBitmap` at `0x1802b1be0`
- `GDI32!CreateBitmap` at `0x1802b1b6f`
- `GDI32!CreateBitmap` at `0x1802b1be0`
- `GDI32!DeleteDC` at `0x1802b1e6d`
- `GDI32!DeleteDC` at `0x1802b1e8e`
- `GDI32!DeleteDC` at `0x1802b1e6d`
- `GDI32!DeleteDC` at `0x1802b1e8e`
- `GDI32!CreatePatternBrush` at `0x1802b1b87`
- `GDI32!CreatePatternBrush` at `0x1802b1b87`
- `GDI32!BitBlt` at `0x1802b1c87`
- `GDI32!BitBlt` at `0x1802b1cca`
- `GDI32!BitBlt` at `0x1802b1d8a`
- `GDI32!BitBlt` at `0x1802b1dbe`
- `GDI32!BitBlt` at `0x1802b1def`
- `GDI32!BitBlt` at `0x1802b1c87`
- `GDI32!BitBlt` at `0x1802b1cca`
- `GDI32!BitBlt` at `0x1802b1d8a`
- `GDI32!BitBlt` at `0x1802b1dbe`
- `GDI32!BitBlt` at `0x1802b1def`
- `GDI32!GetPixel` at `0x1802b1c45`
- `GDI32!GetPixel` at `0x1802b1c45`
- `GDI32!DeleteObject` at `0x1802b1bc8`
- `GDI32!DeleteObject` at `0x1802b1bc8`
- `GDI32!SelectObject` at `0x1802b1bfc`
- `GDI32!SelectObject` at `0x1802b1c16`
- `GDI32!SelectObject` at `0x1802b1dfd`
- `GDI32!SelectObject` at `0x1802b1e14`
- `GDI32!SelectObject` at `0x1802b1bfc`
- `GDI32!SelectObject` at `0x1802b1c16`
- `GDI32!SelectObject` at `0x1802b1dfd`
- `GDI32!SelectObject` at `0x1802b1e14`
- `GDI32!CreateCompatibleDC` at `0x1802b1af4`
- `GDI32!CreateCompatibleDC` at `0x1802b1b1c`
- `GDI32!CreateCompatibleDC` at `0x1802b1af4`
- `GDI32!CreateCompatibleDC` at `0x1802b1b1c`
- `GDI32!GetObjectW` at `0x1802b1b43`
- `GDI32!GetObjectW` at `0x1802b1b43`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall AfxDrawDitheredBitmap(
        HDC__ *pDC,
        int x,
        int y,
        const CBitmap *rSrc,
        unsigned int cr1,
        unsigned int cr2)
{
  CDC *v9; // rsi
  HDC CompatibleDC; // rax
  HDC v11; // rcx
  HDC v12; // rax
  HBITMAP Bitmap; // rax
  HBRUSH PatternBrush; // rax
  void *m_hObject; // rbx
  CHandleMap *m_pmapHGDIOBJ; // rcx
  HBITMAP v17; // rax
  HGDIOBJ v18; // rax
  CGdiObject *v19; // r15
  HGDIOBJ v20; // rax
  CGdiObject *v21; // rax
  CGdiObject *v22; // r14
  COLORREF Pixel; // eax
  unsigned int v24; // ebx
  unsigned int v25; // edi
  unsigned int v26; // ebx
  HGDIOBJ v27; // rax
  HGDIOBJ v28; // rax
  HDC v29; // rax
  HDC v30; // rax
  CBitmap bmpMask; // [rsp+50h] [rbp-99h] BYREF
  CDC dcSrc; // [rsp+60h] [rbp-89h] BYREF
  tagBITMAP bm; // [rsp+80h] [rbp-69h] BYREF
  CBrush brChecker; // [rsp+A0h] [rbp-49h] BYREF
  CDC dcMask; // [rsp+B0h] [rbp-39h] BYREF
  RECT rc; // [rsp+D0h] [rbp-19h] BYREF

  v9 = (CDC *)pDC;
  dcSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcSrc.m_hDC, 0, 20);
  dcMask.__vftable = (CDC_vtbl *)CDC::`vftable';
  memset(&dcMask.m_hDC, 0, 20);
  bmpMask.m_hObject = 0;
  bmpMask.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  brChecker.m_hObject = 0;
  brChecker.__vftable = (CBrush_vtbl *)CBrush::`vftable';
  if ( pDC )
    pDC = (HDC__ *)*((_QWORD *)pDC + 1);
  CompatibleDC = CreateCompatibleDC(pDC);
  if ( CDC::Attach(&dcSrc, CompatibleDC) )
  {
    v11 = v9 ? v9->m_hDC : 0LL;
    v12 = CreateCompatibleDC(v11);
    if ( CDC::Attach(&dcMask, v12) )
    {
      if ( GetObjectW(rSrc->m_hObject, 32, &bm) )
      {
        Bitmap = CreateBitmap(8, 8, 1u, 1u, wPat);
        CGdiObject::Attach(&bmpMask, Bitmap);
        PatternBrush = CreatePatternBrush((HBITMAP)bmpMask.m_hObject);
        CGdiObject::Attach(&brChecker, PatternBrush);
        m_hObject = bmpMask.m_hObject;
        if ( bmpMask.m_hObject )
        {
          m_pmapHGDIOBJ = AfxGetModuleThreadState()->m_pmapHGDIOBJ;
          if ( m_pmapHGDIOBJ )
            CMapPtrToWord::RemoveKey((CMapPtrToWord *)&m_pmapHGDIOBJ->m_permanentMap, bmpMask.m_hObject);
          bmpMask.m_hObject = 0;
          DeleteObject(m_hObject);
        }
        v17 = CreateBitmap(bm.bmWidth, bm.bmHeight, 1u, 1u, 0);
        CGdiObject::Attach(&bmpMask, v17);
        v18 = SelectObject(dcSrc.m_hDC, rSrc->m_hObject);
        v19 = CGdiObject::FromHandle(v18);
        v20 = SelectObject(dcMask.m_hDC, bmpMask.m_hObject);
        v21 = CGdiObject::FromHandle(v20);
        v22 = v21;
        if ( v19 && v21 )
        {
          Pixel = GetPixel(dcSrc.m_hDC, 0, 0);
          v24 = CDC::SetBkColor(&dcSrc, Pixel);
          BitBlt(dcMask.m_hDC, 0, 0, bm.bmWidth, bm.bmHeight, dcSrc.m_hDC, 0, 0, 0xCC0020u);
          CDC::SetBkColor(&dcSrc, 0xFFFFFFu);
          BitBlt(dcMask.m_hDC, 0, 0, bm.bmWidth, bm.bmHeight, dcSrc.m_hDC, 0, 0, 0xEE0086u);
          CDC::SetBkColor(&dcSrc, v24);
          v25 = v9->SetTextColor(v9, cr1);
          v26 = v9->SetBkColor(v9, cr2);
          rc.left = x;
          rc.top = y;
          rc.right = x + bm.bmWidth;
          rc.bottom = y + bm.bmHeight;
          FillRect(v9->m_hDC, &rc, (HBRUSH)brChecker.m_hObject);
          v9->SetTextColor(v9, v25);
          v9->SetBkColor(v9, v26);
          BitBlt(v9->m_hDC, x, y, bm.bmWidth, bm.bmHeight, dcSrc.m_hDC, 0, 0, 0x660046u);
          BitBlt(v9->m_hDC, x, y, bm.bmWidth, bm.bmHeight, dcMask.m_hDC, 0, 0, 0x8800C6u);
          BitBlt(v9->m_hDC, x, y, bm.bmWidth, bm.bmHeight, dcSrc.m_hDC, 0, 0, 0x660046u);
          v27 = SelectObject(dcMask.m_hDC, v22->m_hObject);
          CGdiObject::FromHandle(v27);
          v28 = SelectObject(dcSrc.m_hDC, v19->m_hObject);
          CGdiObject::FromHandle(v28);
        }
      }
    }
  }
  brChecker.__vftable = (CBrush_vtbl *)CBrush::`vftable';
  CGdiObject::~CGdiObject(&brChecker);
  bmpMask.__vftable = (CBitmap_vtbl *)CBitmap::`vftable';
  CGdiObject::~CGdiObject(&bmpMask);
  dcMask.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( dcMask.m_hDC )
  {
    v29 = CDC::Detach(&dcMask);
    DeleteDC(v29);
  }
  dcSrc.__vftable = (CDC_vtbl *)CDC::`vftable';
  if ( dcSrc.m_hDC )
  {
    v30 = CDC::Detach(&dcSrc);
    DeleteDC(v30);
  }
}

```

## disassembly

```asm
0x1802b1a70  push    rbp
0x1802b1a72  push    rbx
0x1802b1a73  push    rsi
0x1802b1a74  push    rdi
0x1802b1a75  push    r12
0x1802b1a77  push    r13
0x1802b1a79  push    r14
0x1802b1a7b  push    r15
0x1802b1a7d  lea     rbp, [rsp-0Fh]
0x1802b1a82  sub     rsp, 0F8h
0x1802b1a89  mov     rax, cs:__security_cookie
0x1802b1a90  xor     rax, rsp
0x1802b1a93  mov     [rbp+47h+var_50], rax
0x1802b1a97  mov     rdi, rSrc
0x1802b1a9a  mov     r13d, y
0x1802b1a9d  mov     r12d, x
0x1802b1aa0  mov     rsi, pDC
0x1802b1aa3  lea     rax, ??_7CDC@@6B@; const CDC::`vftable'
0x1802b1aaa  mov     [rsp+130h+dcSrc.__vftable], rax
0x1802b1aaf  xorps   xmm0, xmm0
0x1802b1ab2  movdqu  xmmword ptr [rsp+130h+dcSrc.m_hDC], xmm0
0x1802b1ab8  and     [rbp+47h+dcSrc.m_bPrinting], 0
0x1802b1abc  mov     [rbp+47h+dcMask.__vftable], rax
0x1802b1ac0  movdqu  xmmword ptr [rbp+47h+dcMask.m_hDC], xmm0
0x1802b1ac5  and     [rbp+47h+dcMask.m_bPrinting], 0
0x1802b1ac9  and     [rsp+130h+bmpMask.m_hObject], 0
0x1802b1acf  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1802b1ad6  mov     [rsp+130h+bmpMask.__vftable], rax
0x1802b1adb  and     [rbp+47h+brChecker.m_hObject], 0
0x1802b1ae0  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x1802b1ae7  mov     [rbp+47h+brChecker.__vftable], rax
0x1802b1aeb  test    pDC, pDC
0x1802b1aee  jz      short loc_1802B1AF4
0x1802b1af0  mov     pDC, [pDC+8]; hdc
0x1802b1af4  call    cs:__imp_CreateCompatibleDC
0x1802b1afa  mov     rdx, rax; hDC
0x1802b1afd  lea     pDC, [rsp+130h+dcSrc]; this
0x1802b1b02  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802b1b07  test    eax, eax
0x1802b1b09  jz      loc_1802B1E23
0x1802b1b0f  test    rsi, rsi
0x1802b1b12  jnz     short loc_1802B1B18
0x1802b1b14  xor     ecx, ecx
0x1802b1b16  jmp     short loc_1802B1B1C
0x1802b1b18  mov     pDC, [rsi+8]; hdc
0x1802b1b1c  call    cs:__imp_CreateCompatibleDC
0x1802b1b22  mov     rdx, rax; hDC
0x1802b1b25  lea     pDC, [rbp+47h+dcMask]; this
0x1802b1b29  call    ?Attach@CDC@@QEAAHPEAUHDC__@@@Z; CDC::Attach(HDC__ *)
0x1802b1b2e  test    eax, eax
0x1802b1b30  jz      loc_1802B1E23
0x1802b1b36  lea     r8, [rbp+47h+bm]; pv
0x1802b1b3a  mov     x, 20h ; ' '; c
0x1802b1b3f  mov     pDC, [rdi+8]; h
0x1802b1b43  call    cs:__imp_GetObjectW
0x1802b1b49  test    eax, eax
0x1802b1b4b  jz      loc_1802B1E23
0x1802b1b51  lea     rax, wPat
0x1802b1b58  mov     [rsp+130h+lpBits], rax; lpBits
0x1802b1b5d  mov     r14d, 1
0x1802b1b63  mov     r9d, r14d; nBitCount
0x1802b1b66  mov     y, r14d; nPlanes
0x1802b1b69  lea     ecx, [r14+7]; nWidth
0x1802b1b6d  mov     x, ecx; nHeight
0x1802b1b6f  call    cs:__imp_CreateBitmap
0x1802b1b75  mov     rdx, rax; hObject
0x1802b1b78  lea     pDC, [rsp+130h+bmpMask]; this
0x1802b1b7d  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b1b82  mov     pDC, [rsp+130h+bmpMask.m_hObject]; hbm
0x1802b1b87  call    cs:__imp_CreatePatternBrush
0x1802b1b8d  mov     rdx, rax; hObject
0x1802b1b90  lea     pDC, [rbp+47h+brChecker]; this
0x1802b1b94  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b1b99  mov     rbx, [rsp+130h+bmpMask.m_hObject]
0x1802b1b9e  test    rbx, rbx
0x1802b1ba1  jz      short loc_1802B1BCE
0x1802b1ba3  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x1802b1ba8  mov     pDC, [rax+40h]
0x1802b1bac  test    pDC, pDC
0x1802b1baf  jz      short loc_1802B1BBF
0x1802b1bb1  add     pDC, 28h ; '('; this
0x1802b1bb5  mov     rdx, [rsp+130h+bmpMask.m_hObject]; key
0x1802b1bba  call    ?RemoveKey@CMapPtrToWord@@QEAAHPEAX@Z; CMapPtrToWord::RemoveKey(void *)
0x1802b1bbf  and     [rsp+130h+bmpMask.m_hObject], 0
0x1802b1bc5  mov     pDC, rbx; ho
0x1802b1bc8  call    cs:__imp_DeleteObject
0x1802b1bce  and     [rsp+130h+lpBits], 0
0x1802b1bd4  mov     r9d, r14d; nBitCount
0x1802b1bd7  mov     y, r14d; nPlanes
0x1802b1bda  mov     x, [rbp+47h+bm.bmHeight]; nHeight
0x1802b1bdd  mov     ecx, [rbp+47h+bm.bmWidth]; nWidth
0x1802b1be0  call    cs:__imp_CreateBitmap
0x1802b1be6  mov     rdx, rax; hObject
0x1802b1be9  lea     pDC, [rsp+130h+bmpMask]; this
0x1802b1bee  call    ?Attach@CGdiObject@@QEAAHPEAX@Z; CGdiObject::Attach(void *)
0x1802b1bf3  mov     rdx, [rdi+8]; h
0x1802b1bf7  mov     pDC, [rsp+130h+dcSrc.m_hDC]; hdc
0x1802b1bfc  call    cs:__imp_SelectObject
0x1802b1c02  mov     pDC, rax; h
0x1802b1c05  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b1c0a  mov     r15, rax
0x1802b1c0d  mov     rdx, [rsp+130h+bmpMask.m_hObject]; h
0x1802b1c12  mov     pDC, [rbp+47h+dcMask.m_hDC]; hdc
0x1802b1c16  call    cs:__imp_SelectObject
0x1802b1c1c  mov     pDC, rax; h
0x1802b1c1f  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b1c24  mov     r14, rax
0x1802b1c27  xor     edi, edi
0x1802b1c29  test    r15, r15
0x1802b1c2c  jz      loc_1802B1E23
0x1802b1c32  test    rax, rax
0x1802b1c35  jz      loc_1802B1E23
0x1802b1c3b  xor     y, y; y
0x1802b1c3e  xor     x, x; x
0x1802b1c40  mov     pDC, [rsp+130h+dcSrc.m_hDC]; hdc
0x1802b1c45  call    cs:__imp_GetPixel
0x1802b1c4b  mov     x, eax; crColor
0x1802b1c4d  lea     pDC, [rsp+130h+dcSrc]; this
0x1802b1c52  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b1c57  mov     ebx, eax
0x1802b1c59  mov     [rsp+130h+rop], 0CC0020h; rop
0x1802b1c61  mov     [rsp+130h+y1], edi; y1
0x1802b1c65  mov     [rsp+130h+x1], edi; x1
0x1802b1c69  mov     pDC, [rsp+130h+dcSrc.m_hDC]
0x1802b1c6e  mov     [rsp+130h+hdcSrc], pDC; hdcSrc
0x1802b1c73  mov     ecx, [rbp+47h+bm.bmHeight]
0x1802b1c76  mov     dword ptr [rsp+130h+lpBits], ecx; cy
0x1802b1c7a  mov     r9d, [rbp+47h+bm.bmWidth]; cx
0x1802b1c7e  xor     y, y; y
0x1802b1c81  xor     x, x; x
0x1802b1c83  mov     pDC, [rbp+47h+dcMask.m_hDC]; hdc
0x1802b1c87  call    cs:__imp_BitBlt
0x1802b1c8d  mov     x, 0FFFFFFh; crColor
0x1802b1c92  lea     pDC, [rsp+130h+dcSrc]; this
0x1802b1c97  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b1c9c  mov     [rsp+130h+rop], 0EE0086h; rop
0x1802b1ca4  mov     [rsp+130h+y1], edi; y1
0x1802b1ca8  mov     [rsp+130h+x1], edi; x1
0x1802b1cac  mov     rax, [rsp+130h+dcSrc.m_hDC]
0x1802b1cb1  mov     [rsp+130h+hdcSrc], rax; hdcSrc
0x1802b1cb6  mov     eax, [rbp+47h+bm.bmHeight]
0x1802b1cb9  mov     dword ptr [rsp+130h+lpBits], eax; cy
0x1802b1cbd  mov     r9d, [rbp+47h+bm.bmWidth]; cx
0x1802b1cc1  xor     y, y; y
0x1802b1cc4  xor     x, x; x
0x1802b1cc6  mov     pDC, [rbp+47h+dcMask.m_hDC]; hdc
0x1802b1cca  call    cs:__imp_BitBlt
0x1802b1cd0  mov     x, ebx; crColor
0x1802b1cd2  lea     pDC, [rsp+130h+dcSrc]; this
0x1802b1cd7  call    ?SetBkColor@CDC@@UEAAKK@Z; CDC::SetBkColor(ulong)
0x1802b1cdc  mov     rax, [rsi]
0x1802b1cdf  mov     x, [rbp+47h+arg_20]
0x1802b1ce2  mov     pDC, rsi
0x1802b1ce5  mov     rax, [rax+70h]
0x1802b1ce9  call    cs:__guard_dispatch_icall_fptr
0x1802b1cef  mov     edi, eax
0x1802b1cf1  mov     pDC, [rsi]
0x1802b1cf4  mov     rax, [pDC+68h]
0x1802b1cf8  mov     x, [rbp+47h+arg_28]
0x1802b1cfb  mov     pDC, rsi
0x1802b1cfe  call    cs:__guard_dispatch_icall_fptr
0x1802b1d04  mov     ebx, eax
0x1802b1d06  mov     y, [rbp+47h+bm.bmHeight]
0x1802b1d0a  add     y, r13d
0x1802b1d0d  mov     x, [rbp+47h+bm.bmWidth]
0x1802b1d10  add     x, r12d
0x1802b1d13  mov     [rbp+47h+rc.left], r12d
0x1802b1d17  mov     [rbp+47h+rc.top], r13d
0x1802b1d1b  mov     [rbp+47h+rc.right], x
0x1802b1d1e  mov     [rbp+47h+rc.bottom], y
0x1802b1d22  mov     r8, [rbp+47h+brChecker.m_hObject]; hbr
0x1802b1d26  lea     rdx, [rbp+47h+rc]; lprc
0x1802b1d2a  mov     pDC, [rsi+8]; hDC
0x1802b1d2e  call    cs:__imp_FillRect
0x1802b1d34  mov     pDC, [rsi]
0x1802b1d37  mov     rax, [pDC+70h]
0x1802b1d3b  mov     x, edi
0x1802b1d3d  mov     pDC, rsi
0x1802b1d40  call    cs:__guard_dispatch_icall_fptr
0x1802b1d46  mov     rax, [rsi]
0x1802b1d49  mov     x, ebx
0x1802b1d4b  mov     pDC, rsi
0x1802b1d4e  mov     rax, [rax+68h]
0x1802b1d52  call    cs:__guard_dispatch_icall_fptr
0x1802b1d58  mov     ebx, 660046h
0x1802b1d5d  mov     [rsp+130h+rop], ebx; rop
0x1802b1d61  xor     edi, edi
0x1802b1d63  mov     [rsp+130h+y1], edi; y1
0x1802b1d67  mov     [rsp+130h+x1], edi; x1
0x1802b1d6b  mov     rax, [rsp+130h+dcSrc.m_hDC]
0x1802b1d70  mov     [rsp+130h+hdcSrc], rax; hdcSrc
0x1802b1d75  mov     eax, [rbp+47h+bm.bmHeight]
0x1802b1d78  mov     dword ptr [rsp+130h+lpBits], eax; cy
0x1802b1d7c  mov     r9d, [rbp+47h+bm.bmWidth]; cx
0x1802b1d80  mov     y, r13d; y
0x1802b1d83  mov     x, r12d; x
0x1802b1d86  mov     pDC, [rsi+8]; hdc
0x1802b1d8a  call    cs:__imp_BitBlt
0x1802b1d90  mov     [rsp+130h+rop], 8800C6h; rop
0x1802b1d98  mov     [rsp+130h+y1], edi; y1
0x1802b1d9c  mov     [rsp+130h+x1], edi; x1
0x1802b1da0  mov     rax, [rbp+47h+dcMask.m_hDC]
0x1802b1da4  mov     [rsp+130h+hdcSrc], rax; hdcSrc
0x1802b1da9  mov     eax, [rbp+47h+bm.bmHeight]
0x1802b1dac  mov     dword ptr [rsp+130h+lpBits], eax; cy
0x1802b1db0  mov     r9d, [rbp+47h+bm.bmWidth]; cx
0x1802b1db4  mov     y, r13d; y
0x1802b1db7  mov     x, r12d; x
0x1802b1dba  mov     pDC, [rsi+8]; hdc
0x1802b1dbe  call    cs:__imp_BitBlt
0x1802b1dc4  mov     [rsp+130h+rop], ebx; rop
0x1802b1dc8  mov     [rsp+130h+y1], edi; y1
0x1802b1dcc  mov     [rsp+130h+x1], edi; x1
0x1802b1dd0  mov     rax, [rsp+130h+dcSrc.m_hDC]
0x1802b1dd5  mov     [rsp+130h+hdcSrc], rax; hdcSrc
0x1802b1dda  mov     eax, [rbp+47h+bm.bmHeight]
0x1802b1ddd  mov     dword ptr [rsp+130h+lpBits], eax; cy
0x1802b1de1  mov     r9d, [rbp+47h+bm.bmWidth]; cx
0x1802b1de5  mov     y, r13d; y
0x1802b1de8  mov     x, r12d; x
0x1802b1deb  mov     pDC, [rsi+8]; hdc
0x1802b1def  call    cs:__imp_BitBlt
0x1802b1df5  mov     rdx, [r14+8]; h
0x1802b1df9  mov     pDC, [rbp+47h+dcMask.m_hDC]; hdc
0x1802b1dfd  call    cs:__imp_SelectObject
0x1802b1e03  mov     pDC, rax; h
0x1802b1e06  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b1e0b  mov     rdx, [r15+8]; h
0x1802b1e0f  mov     pDC, [rsp+130h+dcSrc.m_hDC]; hdc
0x1802b1e14  call    cs:__imp_SelectObject
0x1802b1e1a  mov     pDC, rax; h
0x1802b1e1d  call    ?FromHandle@CGdiObject@@SAPEAV1@PEAX@Z; CGdiObject::FromHandle(void *)
0x1802b1e22  nop
0x1802b1e23  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x1802b1e2a  mov     [rbp+47h+brChecker.__vftable], rax
0x1802b1e2e  lea     pDC, [rbp+47h+brChecker]; this
0x1802b1e32  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b1e37  nop
0x1802b1e38  lea     rax, ??_7CBitmap@@6B@; const CBitmap::`vftable'
0x1802b1e3f  mov     [rsp+130h+bmpMask.__vftable], rax
0x1802b1e44  lea     pDC, [rsp+130h+bmpMask]; this
0x1802b1e49  call    ??1CGdiObject@@UEAA@XZ; CGdiObject::~CGdiObject(void)
0x1802b1e4e  nop
0x1802b1e4f  lea     rbx, ??_7CDC@@6B@; const CDC::`vftable'
0x1802b1e56  mov     [rbp+47h+dcMask.__vftable], rbx
0x1802b1e5a  cmp     [rbp+47h+dcMask.m_hDC], 0
0x1802b1e5f  jz      short loc_1802B1E74
0x1802b1e61  lea     pDC, [rbp+47h+dcMask]; this
0x1802b1e65  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1802b1e6a  mov     pDC, rax; hdc
0x1802b1e6d  call    cs:__imp_DeleteDC
0x1802b1e73  nop
0x1802b1e74  mov     [rsp+130h+dcSrc.__vftable], rbx
0x1802b1e79  cmp     [rsp+130h+dcSrc.m_hDC], 0
0x1802b1e7f  jz      short loc_1802B1E95
0x1802b1e81  lea     pDC, [rsp+130h+dcSrc]; this
0x1802b1e86  call    ?Detach@CDC@@QEAAPEAUHDC__@@XZ; CDC::Detach(void)
0x1802b1e8b  mov     pDC, rax; hdc
0x1802b1e8e  call    cs:__imp_DeleteDC
0x1802b1e94  nop
0x1802b1e95  mov     pDC, [rbp+47h+var_50]
0x1802b1e99  xor     pDC, rsp; StackCookie
0x1802b1e9c  call    __security_check_cookie
0x1802b1ea1  add     rsp, 0F8h
0x1802b1ea8  pop     r15
0x1802b1eaa  pop     r14
0x1802b1eac  pop     r13
0x1802b1eae  pop     r12
0x1802b1eb0  pop     rdi
0x1802b1eb1  pop     rsi
0x1802b1eb2  pop     rbx
0x1802b1eb3  pop     rbp
0x1802b1eb4  retn
```
