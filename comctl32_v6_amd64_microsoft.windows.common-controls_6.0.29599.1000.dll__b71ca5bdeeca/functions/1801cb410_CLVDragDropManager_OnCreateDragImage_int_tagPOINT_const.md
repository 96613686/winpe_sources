# CLVDragDropManager::OnCreateDragImage(int,tagPOINT * const)

- ea: `0x1801cb410`
- end: `0x1801cb992`
- name: `?OnCreateDragImage@CLVDragDropManager@@QEAAPEAU_IMAGELIST@@HQEAUtagPOINT@@@Z`
- size: `1410`
- prototype: `struct _IMAGELIST *__fastcall(CLVDragDropManager *__hidden this, int, struct tagPOINT *const)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801332a0`

## callees

- `0x18000f5b8`
- `0x18001aa40`
- `0x180027a2c`
- `0x1800286c0`
- `0x180029010`
- `0x1800303a0`
- `0x180030740`
- `0x180031a40`
- `0x180035bc0`
- `0x18003b700`
- `0x18003ec80`
- `0x1800bfd50`
- `0x180114520`
- `0x180114ebc`
- `0x18011f01c`
- `0x180127e24`
- `0x18012a628`
- `0x1801cb410`

## import_xrefs

- `GDI32!DeleteObject` at `0x1801cb93f`
- `GDI32!DeleteObject` at `0x1801cb94d`
- `GDI32!DeleteObject` at `0x1801cb95b`
- `GDI32!DeleteObject` at `0x1801cb93f`
- `GDI32!DeleteObject` at `0x1801cb94d`
- `GDI32!DeleteObject` at `0x1801cb95b`
- `GDI32!PatBlt` at `0x1801cb712`
- `GDI32!PatBlt` at `0x1801cb79a`
- `GDI32!PatBlt` at `0x1801cb7ca`
- `GDI32!PatBlt` at `0x1801cb712`
- `GDI32!PatBlt` at `0x1801cb79a`
- `GDI32!PatBlt` at `0x1801cb7ca`
- `GDI32!SelectObject` at `0x1801cb6b2`
- `GDI32!SelectObject` at `0x1801cb6ec`
- `GDI32!SelectObject` at `0x1801cb77a`
- `GDI32!SelectObject` at `0x1801cb7d8`
- `GDI32!SelectObject` at `0x1801cb7e8`
- `GDI32!SelectObject` at `0x1801cb6b2`
- `GDI32!SelectObject` at `0x1801cb6ec`
- `GDI32!SelectObject` at `0x1801cb77a`
- `GDI32!SelectObject` at `0x1801cb7d8`
- `GDI32!SelectObject` at `0x1801cb7e8`
- `GDI32!CreateCompatibleDC` at `0x1801cb63e`
- `GDI32!CreateCompatibleDC` at `0x1801cb63e`
- `GDI32!SetLayout` at `0x1801cb6a0`
- `GDI32!SetLayout` at `0x1801cb6a0`
- `GDI32!CreateBitmap` at `0x1801cb67c`
- `GDI32!CreateBitmap` at `0x1801cb67c`
- `USER32!InflateRect` at `0x1801cb5ff`
- `USER32!InflateRect` at `0x1801cb5ff`
- `USER32!GetSystemMetrics` at `0x1801cb5e3`
- `USER32!GetSystemMetrics` at `0x1801cb5e3`
- `USER32!UpdateWindow` at `0x1801cb4d6`
- `USER32!UpdateWindow` at `0x1801cb4d6`
- `USER32!GetSystemMetricsForDpi` at `0x1801cb582`
- `USER32!GetSystemMetricsForDpi` at `0x1801cb595`
- `USER32!GetSystemMetricsForDpi` at `0x1801cb582`
- `USER32!GetSystemMetricsForDpi` at `0x1801cb595`

## pseudocode

```c
struct _IMAGELIST *__fastcall CLVDragDropManager::OnCreateDragImage(
        CLVDragDropManager *this,
        int a2,
        struct tagPOINT *const a3)
{
  __int64 v3; // r13
  HBITMAP Bitmap; // r12
  __int64 v7; // rcx
  int v8; // eax
  CLVFocusManager *v9; // rcx
  struct CImageList *DrawStateForItem; // rax
  CListView *v11; // rcx
  unsigned int **v12; // r15
  struct _IMAGELIST *v13; // rsi
  int SystemMetricsForDpi; // ebx
  int v15; // ebx
  int SystemMetrics; // eax
  LONG left; // edx
  int v18; // ebx
  int v19; // r15d
  LONG top; // eax
  HDC CompatibleDC; // r14
  HBITMAP ColorBitmap; // r15
  __int64 v23; // rcx
  int v24; // ebx
  int v25; // ebx
  void *v26; // rax
  struct _IMAGELIST *v27; // rbx
  __int64 v28; // rcx
  int v29; // edx
  int v31; // [rsp+50h] [rbp-B0h]
  int v32; // [rsp+50h] [rbp-B0h]
  int nHeight; // [rsp+54h] [rbp-ACh]
  struct CImageList *v34; // [rsp+58h] [rbp-A8h] BYREF
  HGDIOBJ h; // [rsp+60h] [rbp-A0h]
  _DWORD v36[4]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h]
  int w[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v39[4]; // [rsp+90h] [rbp-70h] BYREF
  int v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  HDC v42; // [rsp+E8h] [rbp-18h]
  __int64 v43; // [rsp+100h] [rbp+0h]
  int v44; // [rsp+128h] [rbp+28h]
  struct tagRECT v45; // [rsp+150h] [rbp+50h] BYREF
  __int64 v46; // [rsp+160h] [rbp+60h] BYREF
  struct tagRECT v47; // [rsp+168h] [rbp+68h] BYREF
  struct tagRECT rc; // [rsp+178h] [rbp+78h] BYREF
  struct tagRECT rcDst; // [rsp+188h] [rbp+88h] BYREF
  struct tagLVITEMW v50; // [rsp+1A0h] [rbp+A0h] BYREF

  v3 = a2;
  v45 = 0;
  rc = 0;
  v47 = 0;
  memset_0(&v50, 0, sizeof(v50));
  Bitmap = 0;
  v46 = 0;
  memset_0(v39, 0, 0xC0u);
  rcDst = 0;
  if ( !a3 )
    return 0;
  v7 = *((_QWORD *)this + 2);
  if ( (int)v3 >= **(_DWORD **)(v7 + 512) )
    return 0;
  v8 = *(_DWORD *)(v7 + 128);
  v9 = *(CLVFocusManager **)(v7 + 384);
  v31 = v8;
  if ( *((_DWORD *)v9 + 4) == (_DWORD)v3 )
  {
    CLVFocusManager::OnSetHotItem(v9, -1, -1);
    UpdateWindow(*(HWND *)(*((_QWORD *)this + 2) + 96LL));
  }
  DrawStateForItem = CLVItemStore::GetDrawStateForItem(*(CLVItemStore **)(*((_QWORD *)this + 2) + 512LL), v3);
  v11 = (CListView *)*((_QWORD *)this + 2);
  v34 = DrawStateForItem;
  v12 = (unsigned int **)DrawStateForItem;
  *(_QWORD *)w = 0;
  if ( !CListView::ItemToItemIndex(v11, v3, (struct tagLVITEMINDEX *)w)
    || !(unsigned int)CLVView::GetRects(
                        *(CLVView **)(*((_QWORD *)this + 2) + 608LL),
                        (struct CLVDrawState *)v12,
                        w[0],
                        w[1],
                        0,
                        &rc,
                        &v47,
                        &v45,
                        &rcDst) )
  {
    return 0;
  }
  v13 = 0;
  if ( !*(_WORD *)(*((_QWORD *)this + 2) + 164LL) )
  {
    SystemMetricsForDpi = GetSystemMetricsForDpi(38, *v12[10]);
    v15 = SystemMetricsForDpi - GetSystemMetricsForDpi(11, *v12[10]);
    CLVIconView::UnfoldRects(
      *(CLVIconView **)(*((_QWORD *)this + 2) + 624LL),
      (struct CLVDrawState *)v12,
      v3,
      w[1],
      &rc,
      &v47,
      &v45,
      &rcDst);
    SystemMetrics = GetSystemMetrics(6);
    InflateRect(&rc, v15 / -2, -SystemMetrics);
  }
  left = v45.left;
  v18 = v45.right - v45.left;
  LODWORD(v46) = v45.left - rcDst.left;
  v19 = v45.bottom - v45.top;
  top = v45.top;
  a3->y = v45.top;
  HIDWORD(v46) = top - rcDst.top;
  w[0] = v18;
  nHeight = v19;
  a3->x = left;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    ColorBitmap = (HBITMAP)CreateColorBitmap(v18, v19);
    if ( ColorBitmap )
    {
      Bitmap = CreateBitmap(v18, nHeight, 1u, 1u, 0);
      if ( Bitmap )
      {
        v32 = v31 & 0x400000;
        if ( v32 )
          SetLayout(CompatibleDC, 1u);
        SelectObject(CompatibleDC, *((HGDIOBJ *)v34 + 5));
        v39[0] = *((_QWORD *)this + 2);
        v43 = v3;
        v39[2] = &v46;
        v41 = 0;
        v42 = CompatibleDC;
        v39[3] = 0;
        v44 = -1;
        v40 = 2177;
        h = SelectObject(CompatibleDC, ColorBitmap);
        PatBlt(CompatibleDC, 0, 0, v18, nHeight, 0x42u);
        v23 = *((_QWORD *)this + 2);
        v24 = *(_DWORD *)(v23 + 180);
        *(_DWORD *)(v23 + 180) = -1;
        *(_DWORD *)(*((_QWORD *)this + 2) + 168LL) |= 0x20000u;
        CLVDrawItemManager::DrawItem(*(CLVDrawItemManager **)(*((_QWORD *)this + 2) + 376LL), (struct LVDRAWITEM *)v39);
        *(_DWORD *)(*((_QWORD *)this + 2) + 168LL) &= ~0x20000u;
        *(_DWORD *)(*((_QWORD *)this + 2) + 180LL) = v24;
        if ( v32 )
          MirrorBitmapInDC(CompatibleDC, ColorBitmap);
        SelectObject(CompatibleDC, Bitmap);
        v25 = w[0];
        PatBlt(CompatibleDC, 0, 0, w[0], nHeight, 0xFF0062u);
        PatBlt(CompatibleDC, v47.left - v45.left, v47.top - v45.top, v47.right - v47.left, v47.bottom - v47.top, 0x42u);
        SelectObject(CompatibleDC, h);
        SelectObject(CompatibleDC, g_hfontSystem);
        v26 = *(void **)((char *)v34
                       + (-(__int64)((*(_WORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2) + 408LL) + 8LL) + 164LL)
                                    & 0xFFFB) != 0)
                        & 0xFFFFFFFFFFFFFFF8uLL)
                       + 64);
        v36[2] = 0;
        v37 = 0;
        v34 = 0;
        *(_QWORD *)w = 0;
        h = v26;
        v36[0] = v25;
        v36[1] = nHeight;
        v36[3] = 1;
        HIMAGELIST_QueryInterface((HIMAGELIST)v26, &GUID_46eb5926_582e_4017_9fdf_e8998daa0950, (void **)w);
        CImageList::CloneAttributes(*(struct IImageList **)w, (const struct ILCLONEATTRIBUTES *)v36, &v34);
        SafeRelease<IImageListPriv2>(w);
        v13 = v34;
        if ( v34 )
        {
          v13 = (struct CImageList *)((char *)v34 + 16);
          if ( v34 != (struct CImageList *)-16LL )
          {
            ImageList_SetBkColor(v13, 0xFFFFFFFF);
            ImageList_Add(v13, ColorBitmap, Bitmap);
            v27 = (struct _IMAGELIST *)h;
            if ( h )
            {
              v28 = *((_QWORD *)this + 2);
              v50.iItem = v3;
              v50.iSubItem = 0;
              v50.mask = 10;
              v50.stateMask = 3840;
              CLVItemStore::OnGetItem(*(CLVItemStore **)(v28 + 512), &v50);
              ImageList_CopyDitherImage(
                (int)v13,
                v29,
                rc.left - v45.left,
                rc.top - v45.top,
                v27,
                v50.iImage,
                v50.state & 0xF00 | (*(_DWORD *)(*((_QWORD *)this + 2) + 128LL) >> 15) & 0x80);
            }
          }
        }
      }
    }
    DeleteObject(CompatibleDC);
    if ( ColorBitmap )
      DeleteObject(ColorBitmap);
    if ( Bitmap )
      DeleteObject(Bitmap);
  }
  return v13;
}

```

## disassembly

```asm
0x1801cb410  mov     [rsp-8+arg_18], rbx
0x1801cb415  push    rbp
0x1801cb416  push    rsi
0x1801cb417  push    rdi
0x1801cb418  push    r12
0x1801cb41a  push    r13
0x1801cb41c  push    r14
0x1801cb41e  push    r15
0x1801cb420  lea     rbp, [rsp-110h]
0x1801cb428  sub     rsp, 210h
0x1801cb42f  mov     rax, cs:__security_cookie
0x1801cb436  xor     rax, rsp
0x1801cb439  mov     [rbp+140h+var_40], rax
0x1801cb440  xorps   xmm0, xmm0
0x1801cb443  movsxd  r13, edx
0x1801cb446  xor     edx, edx; Val
0x1801cb448  mov     r14, r8
0x1801cb44b  mov     rdi, rcx
0x1801cb44e  xorps   xmm1, xmm1
0x1801cb451  lea     rcx, [rbp+140h+var_A0]; void *
0x1801cb458  movups  xmmword ptr [rbp+140h+var_F0.left], xmm0
0x1801cb45c  lea     r8d, [rdx+58h]; Size
0x1801cb460  movups  xmmword ptr [rbp+140h+rc.left], xmm1
0x1801cb464  movups  xmmword ptr [rbp+140h+var_D8.left], xmm0
0x1801cb468  call    memset_0
0x1801cb46d  xor     r12d, r12d
0x1801cb470  lea     rcx, [rbp+140h+var_1B0]; void *
0x1801cb474  xor     edx, edx; Val
0x1801cb476  mov     [rbp+140h+var_E0], r12
0x1801cb47a  mov     r8d, 0C0h; Size
0x1801cb480  call    memset_0
0x1801cb485  xorps   xmm0, xmm0
0x1801cb488  movups  xmmword ptr [rbp+140h+rcDst.left], xmm0
0x1801cb48f  test    r14, r14
0x1801cb492  jz      loc_1801CB966
0x1801cb498  mov     rcx, [rdi+10h]
0x1801cb49c  mov     rax, [rcx+200h]
0x1801cb4a3  cmp     r13d, [rax]
0x1801cb4a6  jge     loc_1801CB966
0x1801cb4ac  mov     eax, [rcx+80h]
0x1801cb4b2  mov     rcx, [rcx+180h]; this
0x1801cb4b9  mov     [rsp+240h+var_1F0], eax
0x1801cb4bd  cmp     [rcx+10h], r13d
0x1801cb4c1  jnz     short loc_1801CB4DC
0x1801cb4c3  or      edx, 0FFFFFFFFh; int
0x1801cb4c6  mov     r8d, edx; int
0x1801cb4c9  call    ?OnSetHotItem@CLVFocusManager@@QEAAXHH@Z
0x1801cb4ce  mov     rcx, [rdi+10h]
0x1801cb4d2  mov     rcx, [rcx+60h]; hWnd
0x1801cb4d6  call    cs:__imp_UpdateWindow
0x1801cb4dc  mov     rcx, [rdi+10h]
0x1801cb4e0  mov     edx, r13d; int
0x1801cb4e3  mov     rcx, [rcx+200h]; this
0x1801cb4ea  call    ?GetDrawStateForItem@CLVItemStore@@QEAAPEAVCLVDrawState@@H@Z
0x1801cb4ef  mov     rcx, [rdi+10h]; this
0x1801cb4f3  lea     r8, [rbp+140h+w]; struct tagLVITEMINDEX *
0x1801cb4f7  mov     edx, r13d; int
0x1801cb4fa  mov     [rsp+240h+var_1E8], rax
0x1801cb4ff  mov     r15, rax
0x1801cb502  mov     qword ptr [rbp+140h+w], r12
0x1801cb506  call    ?ItemToItemIndex@CListView@@QEAAHHPEAUtagLVITEMINDEX@@@Z
0x1801cb50b  test    eax, eax
0x1801cb50d  jz      loc_1801CB966
0x1801cb513  mov     rcx, [rdi+10h]
0x1801cb517  lea     rax, [rbp+140h+rcDst]
0x1801cb51e  mov     r9d, [rbp+140h+w+4]; int
0x1801cb522  mov     rdx, r15; struct CLVDrawState *
0x1801cb525  mov     r8d, [rbp+140h+w]; int
0x1801cb529  mov     [rsp+240h+var_200], rax; struct tagRECT *
0x1801cb52e  lea     rax, [rbp+140h+var_F0]
0x1801cb532  mov     rcx, [rcx+260h]; this
0x1801cb539  mov     [rsp+240h+lprcDst], rax; struct tagRECT *
0x1801cb53e  lea     rax, [rbp+140h+var_D8]
0x1801cb542  mov     [rsp+240h+var_210], rax; struct tagRECT *
0x1801cb547  lea     rax, [rbp+140h+rc]
0x1801cb54b  mov     qword ptr [rsp+240h+rop], rax; LPRECT
0x1801cb550  mov     dword ptr [rsp+240h+lpBits], r12d; unsigned int
0x1801cb555  call    ?GetRects@CLVView@@QEAAHPEAVCLVDrawState@@HHKPEAUtagRECT@@111@Z
0x1801cb55a  test    eax, eax
0x1801cb55c  jz      loc_1801CB966
0x1801cb562  mov     rax, [rdi+10h]
0x1801cb566  mov     rsi, r12
0x1801cb569  cmp     [rax+0A4h], r12w
0x1801cb571  jnz     loc_1801CB605
0x1801cb577  mov     rdx, [r15+50h]
0x1801cb57b  mov     ecx, 26h ; '&'
0x1801cb580  mov     edx, [rdx]
0x1801cb582  call    cs:__imp_GetSystemMetricsForDpi
0x1801cb588  mov     rdx, [r15+50h]
0x1801cb58c  mov     ecx, 0Bh
0x1801cb591  mov     ebx, eax
0x1801cb593  mov     edx, [rdx]
0x1801cb595  call    cs:__imp_GetSystemMetricsForDpi
0x1801cb59b  mov     rcx, [rdi+10h]
0x1801cb59f  mov     r8d, r13d; int
0x1801cb5a2  mov     r9d, [rbp+140h+w+4]; int
0x1801cb5a6  sub     ebx, eax
0x1801cb5a8  lea     rax, [rbp+140h+rcDst]
0x1801cb5af  mov     rdx, r15; struct CLVDrawState *
0x1801cb5b2  mov     [rsp+240h+lprcDst], rax; lprcDst
0x1801cb5b7  lea     rax, [rbp+140h+var_F0]
0x1801cb5bb  mov     rcx, [rcx+270h]; this
0x1801cb5c2  mov     [rsp+240h+var_210], rax; struct tagRECT *
0x1801cb5c7  lea     rax, [rbp+140h+var_D8]
0x1801cb5cb  mov     qword ptr [rsp+240h+rop], rax; lprc
0x1801cb5d0  lea     rax, [rbp+140h+rc]
0x1801cb5d4  mov     [rsp+240h+lpBits], rax; lprcSrc1
0x1801cb5d9  call    ?UnfoldRects@CLVIconView@@QEAAHPEAVCLVDrawState@@HHPEBUtagRECT@@PEAU3@22@Z
0x1801cb5de  mov     ecx, 6; nIndex
0x1801cb5e3  call    cs:__imp_GetSystemMetrics
0x1801cb5e9  mov     r8d, eax
0x1801cb5ec  mov     ecx, 0FFFFFFFEh
0x1801cb5f1  mov     eax, ebx
0x1801cb5f3  neg     r8d; dy
0x1801cb5f6  cdq
0x1801cb5f7  idiv    ecx
0x1801cb5f9  lea     rcx, [rbp+140h+rc]; lprc
0x1801cb5fd  mov     edx, eax; dx
0x1801cb5ff  call    cs:__imp_InflateRect
0x1801cb605  mov     ecx, [rbp+140h+var_F0.top]
0x1801cb608  mov     edx, [rbp+140h+var_F0.left]
0x1801cb60b  mov     eax, edx
0x1801cb60d  sub     eax, [rbp+140h+rcDst.left]
0x1801cb613  mov     ebx, [rbp+140h+var_F0.right]
0x1801cb616  mov     r15d, [rbp+140h+var_F0.bottom]
0x1801cb61a  sub     ebx, edx
0x1801cb61c  mov     dword ptr [rbp+140h+var_E0], eax
0x1801cb61f  sub     r15d, ecx
0x1801cb622  mov     eax, ecx
0x1801cb624  mov     [r14+4], ecx
0x1801cb628  sub     eax, [rbp+140h+rcDst.top]
0x1801cb62e  xor     ecx, ecx; hdc
0x1801cb630  mov     dword ptr [rbp+140h+var_E0+4], eax
0x1801cb633  mov     [rbp+140h+w], ebx
0x1801cb636  mov     [rsp+240h+nHeight], r15d
0x1801cb63b  mov     [r14], edx
0x1801cb63e  call    cs:__imp_CreateCompatibleDC
0x1801cb644  mov     r14, rax
0x1801cb647  test    rax, rax
0x1801cb64a  jz      loc_1801CB961
0x1801cb650  mov     edx, r15d; cy
0x1801cb653  mov     ecx, ebx; cx
0x1801cb655  call    CreateColorBitmap
0x1801cb65a  mov     r15, rax
0x1801cb65d  test    rax, rax
0x1801cb660  jz      loc_1801CB93C
0x1801cb666  mov     edx, [rsp+240h+nHeight]; nHeight
0x1801cb66a  mov     eax, 1
0x1801cb66f  mov     r9d, eax; nBitCount
0x1801cb672  mov     [rsp+240h+lpBits], rsi; lpBits
0x1801cb677  mov     r8d, eax; nPlanes
0x1801cb67a  mov     ecx, ebx; nWidth
0x1801cb67c  call    cs:__imp_CreateBitmap
0x1801cb682  mov     r12, rax
0x1801cb685  test    rax, rax
0x1801cb688  jz      loc_1801CB93C
0x1801cb68e  and     [rsp+240h+var_1F0], 400000h
0x1801cb696  jz      short loc_1801CB6A6
0x1801cb698  mov     edx, 1; l
0x1801cb69d  mov     rcx, r14; hdc
0x1801cb6a0  call    cs:__imp_SetLayout
0x1801cb6a6  mov     rax, [rsp+240h+var_1E8]
0x1801cb6ab  mov     rcx, r14; hdc
0x1801cb6ae  mov     rdx, [rax+28h]; h
0x1801cb6b2  call    cs:__imp_SelectObject
0x1801cb6b8  mov     rax, [rdi+10h]
0x1801cb6bc  mov     rdx, r15; h
0x1801cb6bf  mov     [rbp+140h+var_1B0], rax
0x1801cb6c3  mov     rcx, r14; hdc
0x1801cb6c6  lea     rax, [rbp+140h+var_E0]
0x1801cb6ca  mov     [rbp+140h+var_140], r13
0x1801cb6ce  mov     [rbp+140h+var_1A0], rax
0x1801cb6d2  mov     [rbp+140h+var_188], rsi
0x1801cb6d6  mov     [rbp+140h+var_158], r14
0x1801cb6da  mov     [rbp+140h+var_198], rsi
0x1801cb6de  mov     [rbp+140h+var_118], 0FFFFFFFFh
0x1801cb6e5  mov     [rbp+140h+var_190], 881h
0x1801cb6ec  call    cs:__imp_SelectObject
0x1801cb6f2  mov     esi, [rsp+240h+nHeight]
0x1801cb6f6  mov     r9d, ebx; w
0x1801cb6f9  xor     r8d, r8d; y
0x1801cb6fc  mov     [rsp+240h+rop], 42h ; 'B'; rop
0x1801cb704  xor     edx, edx; x
0x1801cb706  mov     [rsp+240h+h], rax
0x1801cb70b  mov     rcx, r14; hdc
0x1801cb70e  mov     dword ptr [rsp+240h+lpBits], esi; h
0x1801cb712  call    cs:__imp_PatBlt
0x1801cb718  mov     rcx, [rdi+10h]
0x1801cb71c  lea     rdx, [rbp+140h+var_1B0]; struct LVDRAWITEM *
0x1801cb720  mov     ebx, [rcx+0B4h]
0x1801cb726  mov     dword ptr [rcx+0B4h], 0FFFFFFFFh
0x1801cb730  mov     rcx, [rdi+10h]
0x1801cb734  bts     dword ptr [rcx+0A8h], 11h
0x1801cb73c  mov     rcx, [rdi+10h]
0x1801cb740  mov     rcx, [rcx+178h]; this
0x1801cb747  call    ?DrawItem@CLVDrawItemManager@@QEAAHPEAULVDRAWITEM@@@Z
0x1801cb74c  mov     rax, [rdi+10h]
0x1801cb750  btr     dword ptr [rax+0A8h], 11h
0x1801cb758  cmp     [rsp+240h+var_1F0], 0
0x1801cb75d  mov     rax, [rdi+10h]
0x1801cb761  mov     [rax+0B4h], ebx
0x1801cb767  jz      short loc_1801CB774
0x1801cb769  mov     rdx, r15; h
0x1801cb76c  mov     rcx, r14; hdc
0x1801cb76f  call    MirrorBitmapInDC
0x1801cb774  mov     rdx, r12; h
0x1801cb777  mov     rcx, r14; hdc
0x1801cb77a  call    cs:__imp_SelectObject
0x1801cb780  mov     ebx, [rbp+140h+w]
0x1801cb783  xor     r8d, r8d; y
0x1801cb786  mov     r9d, ebx; w
0x1801cb789  mov     [rsp+240h+rop], 0FF0062h; rop
0x1801cb791  xor     edx, edx; x
0x1801cb793  mov     dword ptr [rsp+240h+lpBits], esi; h
0x1801cb797  mov     rcx, r14; hdc
0x1801cb79a  call    cs:__imp_PatBlt
0x1801cb7a0  mov     r8d, [rbp+140h+var_D8.top]
0x1801cb7a4  mov     rcx, r14; hdc
0x1801cb7a7  mov     edx, [rbp+140h+var_D8.left]
0x1801cb7aa  mov     eax, [rbp+140h+var_D8.bottom]
0x1801cb7ad  mov     r9d, [rbp+140h+var_D8.right]
0x1801cb7b1  sub     eax, r8d
0x1801cb7b4  sub     r8d, [rbp+140h+var_F0.top]; y
0x1801cb7b8  sub     r9d, edx; w
0x1801cb7bb  sub     edx, [rbp+140h+var_F0.left]; x
0x1801cb7be  mov     [rsp+240h+rop], 42h ; 'B'; rop
0x1801cb7c6  mov     dword ptr [rsp+240h+lpBits], eax; h
0x1801cb7ca  call    cs:__imp_PatBlt
0x1801cb7d0  mov     rdx, [rsp+240h+h]; h
0x1801cb7d5  mov     rcx, r14; hdc
0x1801cb7d8  call    cs:__imp_SelectObject
0x1801cb7de  mov     rdx, cs:g_hfontSystem; h
0x1801cb7e5  mov     rcx, r14; hdc
0x1801cb7e8  call    cs:__imp_SelectObject
0x1801cb7ee  mov     rax, [rdi+10h]
0x1801cb7f2  lea     r8, [rbp+140h+w]; ppv
0x1801cb7f6  lea     rdx, _GUID_46eb5926_582e_4017_9fdf_e8998daa0950; riid
0x1801cb7fd  mov     rcx, [rax+198h]
0x1801cb804  mov     rax, [rcx+8]
0x1801cb808  mov     ecx, 0FFFBh
0x1801cb80d  and     cx, [rax+0A4h]
0x1801cb814  neg     cx
0x1801cb817  mov     rcx, [rsp+240h+var_1E8]
0x1801cb81c  sbb     rax, rax
0x1801cb81f  and     rax, 0FFFFFFFFFFFFFFF8h
0x1801cb823  mov     rax, [rax+rcx+40h]
0x1801cb828  xor     ecx, ecx
0x1801cb82a  mov     [rsp+240h+var_1D0], ecx
0x1801cb82e  mov     [rsp+240h+var_1C8], rcx
0x1801cb833  mov     [rsp+240h+var_1E8], rcx
0x1801cb838  mov     qword ptr [rbp+140h+w], rcx
0x1801cb83c  mov     rcx, rax; himl
0x1801cb83f  mov     [rsp+240h+h], rax
0x1801cb844  mov     [rsp+240h+var_1D8], ebx
0x1801cb848  mov     [rsp+240h+var_1D4], esi
0x1801cb84c  mov     [rsp+240h+var_1CC], 1
0x1801cb854  call    HIMAGELIST_QueryInterface
0x1801cb859  mov     rcx, qword ptr [rbp+140h+w]; struct IImageList *
0x1801cb85d  lea     r8, [rsp+240h+var_1E8]; struct CImageList **
0x1801cb862  lea     rdx, [rsp+240h+var_1D8]; struct ILCLONEATTRIBUTES *
0x1801cb867  call    ?CloneAttributes@CImageList@@KAJPEAUIImageList@@PEBUILCLONEATTRIBUTES@@PEAPEAV1@@Z
0x1801cb86c  lea     rcx, [rbp+140h+w]
0x1801cb870  call    ??$SafeRelease@UIImageListPriv2@@@@YAXPEAPEAUIImageListPriv2@@@Z
0x1801cb875  mov     rsi, [rsp+240h+var_1E8]
0x1801cb87a  test    rsi, rsi
0x1801cb87d  jz      loc_1801CB93C
0x1801cb883  add     rsi, 10h
0x1801cb887  jz      loc_1801CB93C
0x1801cb88d  or      edx, 0FFFFFFFFh; clrBk
0x1801cb890  mov     rcx, rsi; himl
0x1801cb893  call    ImageList_SetBkColor
0x1801cb898  mov     r8, r12; hbmMask
0x1801cb89b  mov     rdx, r15; hbmImage
0x1801cb89e  mov     rcx, rsi; himl
0x1801cb8a1  call    ImageList_Add
0x1801cb8a6  mov     rbx, [rsp+240h+h]
0x1801cb8ab  test    rbx, rbx
0x1801cb8ae  jz      loc_1801CB93C
0x1801cb8b4  mov     rcx, [rdi+10h]
0x1801cb8b8  lea     rdx, [rbp+140h+var_A0]; struct tagLVITEMW *
0x1801cb8bf  mov     [rbp+140h+var_A0.iItem], r13d
0x1801cb8c6  mov     r13d, 0F00h
0x1801cb8cc  mov     [rbp+140h+var_A0.iSubItem], 0
0x1801cb8d6  mov     [rbp+140h+var_A0.mask], 0Ah
0x1801cb8e0  mov     [rbp+140h+var_A0.stateMask], r13d
0x1801cb8e7  mov     rcx, [rcx+200h]; this
0x1801cb8ee  call    ?OnGetItem@CLVItemStore@@QEAAHPEAUtagLVITEMW@@@Z
0x1801cb8f3  mov     rax, [rdi+10h]
0x1801cb8f7  mov     r9d, [rbp+140h+rc.top]
0x1801cb8fb  mov     r8d, [rbp+140h+rc.left]
0x1801cb8ff  sub     r9d, [rbp+140h+var_F0.top]; int
0x1801cb903  mov     ecx, [rax+80h]
0x1801cb909  mov     eax, [rbp+140h+var_A0.state]
0x1801cb90f  sub     r8d, [rbp+140h+var_F0.left]; int
0x1801cb913  and     eax, r13d
0x1801cb916  shr     ecx, 0Fh
0x1801cb919  and     ecx, 80h
0x1801cb91f  or      ecx, eax
0x1801cb921  mov     eax, [rbp+140h+var_A0.iImage]
0x1801cb927  mov     dword ptr [rsp+240h+var_210], ecx; int
  ... truncated ...
```
