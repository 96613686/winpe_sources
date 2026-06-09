# CImageList::GlobalInit(void)

- ea: `0x180081554`
- end: `0x180081649`
- name: `?GlobalInit@CImageList@@SAHXZ`
- size: `245`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007fe80`
- `0x180082280`

## callees

- `0x180081554`
- `0x180081650`
- `0x18008691c`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180081580`
- `GDI32!CreateCompatibleDC` at `0x180081590`
- `GDI32!CreateCompatibleDC` at `0x180081580`
- `GDI32!CreateCompatibleDC` at `0x180081590`
- `GDI32!SelectObject` at `0x1800815d4`
- `GDI32!SelectObject` at `0x1800815eb`
- `GDI32!SelectObject` at `0x1800815d4`
- `GDI32!SelectObject` at `0x1800815eb`
- `GDI32!DeleteObject` at `0x180081604`
- `GDI32!DeleteObject` at `0x180081604`
- `GDI32!CreatePatternBrush` at `0x1800815f4`
- `GDI32!CreatePatternBrush` at `0x1800815f4`
- `GDI32!CreateBitmap` at `0x1800815bc`
- `GDI32!CreateBitmap` at `0x1800815bc`
- `USER32!GetDC` at `0x180081574`
- `USER32!GetDC` at `0x180081574`
- `USER32!ReleaseDC` at `0x18008160f`
- `USER32!ReleaseDC` at `0x18008160f`

## pseudocode

```c
__int64 CImageList::GlobalInit(void)
{
  HDC DC; // rsi
  HBITMAP Bitmap; // rax
  HBITMAP v3; // rdi

  if ( g_hdcDst )
    return 1;
  DC = GetDC(0);
  g_hdcSrc = CreateCompatibleDC(DC);
  g_hdcDst = CreateCompatibleDC(DC);
  InitDitherBrush();
  Bitmap = CreateBitmap(8, 8, 1u, 1u, qword_18009B118);
  v3 = Bitmap;
  if ( Bitmap )
  {
    g_hbmDcDeselect = SelectObject(g_hdcDst, Bitmap);
    SelectObject(g_hdcDst, g_hbmDcDeselect);
    g_hbrStripe = CreatePatternBrush(v3);
    DeleteObject(v3);
  }
  ReleaseDC(0, DC);
  if ( g_hdcSrc )
  {
    if ( g_hdcDst && g_hbrMonoDither )
      return 1;
  }
  CImageList::GlobalUninit();
  return 0;
}

```

## disassembly

```asm
0x180081554  mov     [rsp+arg_0], rsi
0x180081559  push    rdi
0x18008155a  sub     rsp, 30h
0x18008155e  cmp     cs:?g_hdcDst@@3PEAUHDC__@@EA, 0; HDC__ * g_hdcDst
0x180081566  jz      short loc_180081572
0x180081568  mov     eax, 1
0x18008156d  jmp     loc_18008163E
0x180081572  xor     ecx, ecx; hWnd
0x180081574  call    cs:__imp_GetDC
0x18008157a  mov     rcx, rax; hdc
0x18008157d  mov     rsi, rax
0x180081580  call    cs:__imp_CreateCompatibleDC
0x180081586  mov     rcx, rsi; hdc
0x180081589  mov     cs:?g_hdcSrc@@3PEAUHDC__@@EA, rax; HDC__ * g_hdcSrc
0x180081590  call    cs:__imp_CreateCompatibleDC
0x180081596  mov     cs:?g_hdcDst@@3PEAUHDC__@@EA, rax; HDC__ * g_hdcDst
0x18008159d  call    InitDitherBrush
0x1800815a2  mov     ecx, 8; nWidth
0x1800815a7  lea     rax, qword_18009B118
0x1800815ae  mov     edx, ecx; nHeight
0x1800815b0  mov     [rsp+38h+lpBits], rax; lpBits
0x1800815b5  lea     r9d, [rcx-7]; nBitCount
0x1800815b9  mov     r8d, r9d; nPlanes
0x1800815bc  call    cs:__imp_CreateBitmap
0x1800815c2  mov     rdi, rax
0x1800815c5  test    rax, rax
0x1800815c8  jz      short loc_18008160A
0x1800815ca  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x1800815d1  mov     rdx, rax; h
0x1800815d4  call    cs:__imp_SelectObject
0x1800815da  mov     rcx, cs:?g_hdcDst@@3PEAUHDC__@@EA; hdc
0x1800815e1  mov     rdx, rax; h
0x1800815e4  mov     cs:?g_hbmDcDeselect@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * g_hbmDcDeselect
0x1800815eb  call    cs:__imp_SelectObject
0x1800815f1  mov     rcx, rdi; hbm
0x1800815f4  call    cs:__imp_CreatePatternBrush
0x1800815fa  mov     rcx, rdi; ho
0x1800815fd  mov     cs:?g_hbrStripe@@3PEAUHBRUSH__@@EA, rax; HBRUSH__ * g_hbrStripe
0x180081604  call    cs:__imp_DeleteObject
0x18008160a  mov     rdx, rsi; hDC
0x18008160d  xor     ecx, ecx; hWnd
0x18008160f  call    cs:__imp_ReleaseDC
0x180081615  cmp     cs:?g_hdcSrc@@3PEAUHDC__@@EA, 0; HDC__ * g_hdcSrc
0x18008161d  jz      short loc_180081637
0x18008161f  cmp     cs:?g_hdcDst@@3PEAUHDC__@@EA, 0; HDC__ * g_hdcDst
0x180081627  jz      short loc_180081637
0x180081629  cmp     cs:g_hbrMonoDither, 0
0x180081631  jnz     loc_180081568
0x180081637  call    ?GlobalUninit@CImageList@@SAXXZ; CImageList::GlobalUninit(void)
0x18008163c  xor     eax, eax
0x18008163e  mov     rsi, [rsp+38h+arg_0]
0x180081643  add     rsp, 30h
0x180081647  pop     rdi
0x180081648  retn
```
