# CImageList::GlobalUninit(void)

- ea: `0x180081650`
- end: `0x1800816ef`
- name: `?GlobalUninit@CImageList@@SAXXZ`
- size: `159`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18007f2e8`
- `0x180081554`

## callees

- `0x180081650`
- `0x180081db0`
- `0x180082a7c`
- `0x180082ad0`
- `0x18008698c`

## import_xrefs

- `GDI32!DeleteObject` at `0x180081665`
- `GDI32!DeleteObject` at `0x1800816d9`
- `GDI32!DeleteObject` at `0x180081665`
- `GDI32!DeleteObject` at `0x1800816d9`
- `GDI32!DeleteDC` at `0x180081693`
- `GDI32!DeleteDC` at `0x1800816bc`
- `GDI32!DeleteDC` at `0x180081693`
- `GDI32!DeleteDC` at `0x1800816bc`

## pseudocode

```c
void CImageList::GlobalUninit(void)
{
  TerminateDitherBrush();
  if ( g_hbrStripe )
  {
    DeleteObject(g_hbrStripe);
    g_hbrStripe = 0;
  }
  ImageList_DeleteDragBitmaps();
  if ( g_hdcDst )
  {
    CImageList::SelectDstBitmap(0);
    DeleteDC(g_hdcDst);
    g_hdcDst = 0;
  }
  if ( g_hdcSrc )
  {
    CImageList::SelectSrcBitmap(0);
    DeleteDC(g_hdcSrc);
    g_hdcSrc = 0;
  }
  if ( g_hbmWork )
  {
    DeleteObject(g_hbmWork);
    g_hbmWork = 0;
  }
}

```

## disassembly

```asm
0x180081650  sub     rsp, 28h
0x180081654  call    TerminateDitherBrush
0x180081659  mov     rcx, cs:?g_hbrStripe@@3PEAUHBRUSH__@@EA; ho
0x180081660  test    rcx, rcx
0x180081663  jz      short loc_180081676
0x180081665  call    cs:__imp_DeleteObject
0x18008166b  mov     cs:?g_hbrStripe@@3PEAUHBRUSH__@@EA, 0; HBRUSH__ * g_hbrStripe
0x180081676  call    ?ImageList_DeleteDragBitmaps@@YAXXZ; ImageList_DeleteDragBitmaps(void)
0x18008167b  cmp     cs:?g_hdcDst@@3PEAUHDC__@@EA, 0; HDC__ * g_hdcDst
0x180081683  jz      short loc_1800816A4
0x180081685  xor     ecx, ecx; HBITMAP
0x180081687  call    ?SelectDstBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectDstBitmap(HBITMAP__ *)
0x18008168c  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x180081693  call    cs:__imp_DeleteDC
0x180081699  mov     cs:?g_hdcDst@@3PEAUHDC__@@EA, 0; HDC__ * g_hdcDst
0x1800816a4  cmp     cs:?g_hdcSrc@@3PEAUHDC__@@EA, 0; HDC__ * g_hdcSrc
0x1800816ac  jz      short loc_1800816CD
0x1800816ae  xor     ecx, ecx; HBITMAP
0x1800816b0  call    ?SelectSrcBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectSrcBitmap(HBITMAP__ *)
0x1800816b5  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x1800816bc  call    cs:__imp_DeleteDC
0x1800816c2  mov     cs:?g_hdcSrc@@3PEAUHDC__@@EA, 0; HDC__ * g_hdcSrc
0x1800816cd  mov     rcx, cs:?g_hbmWork@@3PEAUHBITMAP__@@EA; ho
0x1800816d4  test    rcx, rcx
0x1800816d7  jz      short loc_1800816EA
0x1800816d9  call    cs:__imp_DeleteObject
0x1800816df  mov     cs:?g_hbmWork@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmWork
0x1800816ea  add     rsp, 28h
0x1800816ee  retn
```
