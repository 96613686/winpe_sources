# ImageList_GetWorkDC(HDC__ *,int,int)

- ea: `0x180081e68`
- end: `0x180081f6d`
- name: `?ImageList_GetWorkDC@@YAPEAUHDC__@@PEAU1@HH@Z`
- size: `261`
- prototype: `HDC __fastcall(HDC hdc, int cx, int cy)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800806a0`

## callees

- `0x180081e68`
- `0x180082ad0`
- `0x180084018`

## import_xrefs

- `GDI32!CreateCompatibleBitmap` at `0x180081edd`
- `GDI32!CreateCompatibleBitmap` at `0x180081edd`
- `GDI32!GetStockObject` at `0x180081f2c`
- `GDI32!GetStockObject` at `0x180081f2c`
- `GDI32!GetObjectW` at `0x180081efe`
- `GDI32!GetObjectW` at `0x180081efe`
- `GDI32!GetDeviceCaps` at `0x180081e94`
- `GDI32!GetDeviceCaps` at `0x180081f1b`
- `GDI32!GetDeviceCaps` at `0x180081e94`
- `GDI32!GetDeviceCaps` at `0x180081f1b`
- `GDI32!SelectPalette` at `0x180081f40`
- `GDI32!SelectPalette` at `0x180081f53`
- `GDI32!SelectPalette` at `0x180081f40`
- `GDI32!SelectPalette` at `0x180081f53`

## pseudocode

```c
HDC __fastcall ImageList_GetWorkDC(HDC hdc, int cx, int cy)
{
  HBITMAP v5; // rcx
  int v7; // ebx
  HBITMAP CompatibleBitmap; // rax
  HPALETTE StockObject; // rax
  HPALETTE v10; // rax

  v5 = (HBITMAP)g_hbmWork;
  if ( g_hbmWork )
  {
    v7 = (unsigned __int16)word_1800A5B12;
    if ( GetDeviceCaps(hdc, 12) == v7 && dword_1800A5B04 >= cx && dword_1800A5B08 >= cy )
      goto LABEL_10;
    v5 = (HBITMAP)g_hbmWork;
  }
  CImageList::_DeleteBitmap(v5);
  g_hbmWork = 0;
  if ( !cx || !cy )
    return 0;
  CompatibleBitmap = CreateCompatibleBitmap(hdc, cx, cy);
  g_hbmWork = CompatibleBitmap;
  if ( CompatibleBitmap )
  {
    GetObjectW(CompatibleBitmap, 32, &g_bmWork);
LABEL_10:
    CompatibleBitmap = (HBITMAP)g_hbmWork;
  }
  CImageList::SelectSrcBitmap(CompatibleBitmap);
  if ( (GetDeviceCaps(hdc, 38) & 0x100) != 0 )
  {
    StockObject = (HPALETTE)GetStockObject(15);
    v10 = SelectPalette(hdc, StockObject, 1);
    SelectPalette(g_hdcSrc, v10, 1);
  }
  return g_hdcSrc;
}

```

## disassembly

```asm
0x180081e68  push    rbx
0x180081e6a  push    rbp
0x180081e6b  push    rsi
0x180081e6c  push    rdi
0x180081e6d  sub     rsp, 28h
0x180081e71  mov     rbp, rcx
0x180081e74  mov     edi, r8d
0x180081e77  mov     rcx, cs:?g_hbmWork@@3PEAUHBITMAP__@@EA; HBITMAP__ * g_hbmWork
0x180081e7e  mov     esi, edx
0x180081e80  test    rcx, rcx
0x180081e83  jz      short loc_180081EB5
0x180081e85  movzx   ebx, cs:word_1800A5B12
0x180081e8c  mov     edx, 0Ch; index
0x180081e91  mov     rcx, rbp; hdc
0x180081e94  call    cs:__imp_GetDeviceCaps
0x180081e9a  cmp     eax, ebx
0x180081e9c  jnz     short loc_180081EAE
0x180081e9e  cmp     cs:dword_1800A5B04, esi
0x180081ea4  jl      short loc_180081EAE
0x180081ea6  cmp     cs:dword_1800A5B08, edi
0x180081eac  jge     short loc_180081F04
0x180081eae  mov     rcx, cs:?g_hbmWork@@3PEAUHBITMAP__@@EA; ho
0x180081eb5  call    ?_DeleteBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::_DeleteBitmap(HBITMAP__ *)
0x180081eba  mov     cs:?g_hbmWork@@3PEAUHBITMAP__@@EA, 0; HBITMAP__ * g_hbmWork
0x180081ec5  test    esi, esi
0x180081ec7  jz      loc_180081F62
0x180081ecd  test    edi, edi
0x180081ecf  jz      loc_180081F62
0x180081ed5  mov     r8d, edi; cy
0x180081ed8  mov     edx, esi; cx
0x180081eda  mov     rcx, rbp; hdc
0x180081edd  call    cs:__imp_CreateCompatibleBitmap
0x180081ee3  mov     cs:?g_hbmWork@@3PEAUHBITMAP__@@EA, rax; HBITMAP__ * g_hbmWork
0x180081eea  test    rax, rax
0x180081eed  jz      short loc_180081F0B
0x180081eef  lea     r8, ?g_bmWork@@3UtagBITMAP@@A; pv
0x180081ef6  mov     edx, 20h ; ' '; c
0x180081efb  mov     rcx, rax; h
0x180081efe  call    cs:__imp_GetObjectW
0x180081f04  mov     rax, cs:?g_hbmWork@@3PEAUHBITMAP__@@EA; HBITMAP__ * g_hbmWork
0x180081f0b  mov     rcx, rax; HBITMAP
0x180081f0e  call    ?SelectSrcBitmap@CImageList@@SAXPEAUHBITMAP__@@@Z; CImageList::SelectSrcBitmap(HBITMAP__ *)
0x180081f13  mov     edx, 26h ; '&'; index
0x180081f18  mov     rcx, rbp; hdc
0x180081f1b  call    cs:__imp_GetDeviceCaps
0x180081f21  bt      eax, 8
0x180081f25  jnb     short loc_180081F59
0x180081f27  mov     ecx, 0Fh; i
0x180081f2c  call    cs:__imp_GetStockObject
0x180081f32  mov     ebx, 1
0x180081f37  mov     rcx, rbp; hdc
0x180081f3a  mov     rdx, rax; hPal
0x180081f3d  mov     r8d, ebx; bForceBkgd
0x180081f40  call    cs:__imp_SelectPalette
0x180081f46  mov     rcx, cs:?g_hdcSrc@@3PEAUHDC__@@EA; hdc
0x180081f4d  mov     r8d, ebx; bForceBkgd
0x180081f50  mov     rdx, rax; hPal
0x180081f53  call    cs:__imp_SelectPalette
0x180081f59  mov     rax, cs:?g_hdcSrc@@3PEAUHDC__@@EA; HDC__ * g_hdcSrc
0x180081f60  jmp     short loc_180081F64
0x180081f62  xor     eax, eax
0x180081f64  add     rsp, 28h
0x180081f68  pop     rdi
0x180081f69  pop     rsi
0x180081f6a  pop     rbp
0x180081f6b  pop     rbx
0x180081f6c  retn
```
