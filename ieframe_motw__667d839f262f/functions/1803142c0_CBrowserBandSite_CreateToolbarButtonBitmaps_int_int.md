# CBrowserBandSite::_CreateToolbarButtonBitmaps(int,int)

- ea: `0x1803142c0`
- end: `0x18031446b`
- name: `?_CreateToolbarButtonBitmaps@CBrowserBandSite@@MEAAPEAUHBITMAP__@@HH@Z`
- size: `427`
- prototype: `HBITMAP(CBrowserBandSite *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1803152f0`
- `0x1803154a0`

## callees

- `0x1803142c0`
- `0x180441d98`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18031435b`
- `KERNEL32!MulDiv` at `0x18031436e`
- `KERNEL32!MulDiv` at `0x18031435b`
- `KERNEL32!MulDiv` at `0x18031436e`
- `GDI32!StretchBlt` at `0x1803143ff`
- `GDI32!StretchBlt` at `0x1803143ff`
- `GDI32!DeleteObject` at `0x180314436`
- `GDI32!DeleteObject` at `0x180314436`
- `GDI32!SelectObject` at `0x180314342`
- `GDI32!SelectObject` at `0x1803143b3`
- `GDI32!SelectObject` at `0x18031440e`
- `GDI32!SelectObject` at `0x180314428`
- `GDI32!SelectObject` at `0x180314342`
- `GDI32!SelectObject` at `0x1803143b3`
- `GDI32!SelectObject` at `0x18031440e`
- `GDI32!SelectObject` at `0x180314428`
- `GDI32!DeleteDC` at `0x180314417`
- `GDI32!DeleteDC` at `0x18031443f`
- `GDI32!DeleteDC` at `0x180314417`
- `GDI32!DeleteDC` at `0x18031443f`
- `GDI32!CreateCompatibleDC` at `0x18031432a`
- `GDI32!CreateCompatibleDC` at `0x180314380`
- `GDI32!CreateCompatibleDC` at `0x18031432a`
- `GDI32!CreateCompatibleDC` at `0x180314380`
- `GDI32!CreateCompatibleBitmap` at `0x18031439f`
- `GDI32!CreateCompatibleBitmap` at `0x18031439f`
- `USER32!ReleaseDC` at `0x18031444a`
- `USER32!ReleaseDC` at `0x18031444a`
- `USER32!GetDC` at `0x180314315`
- `USER32!GetDC` at `0x180314315`

## pseudocode

```c
HBITMAP __fastcall CBrowserBandSite::_CreateToolbarButtonBitmaps(CBrowserBandSite *this, int a2, int a3)
{
  HBITMAP MappedBitmap; // rbp
  HBITMAP v6; // r14
  HDC DC; // rax
  HDC v8; // rdi
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rsi
  int v11; // r12d
  HDC v12; // r15
  int v13; // r13d
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v15; // r12
  HGDIOBJ v16; // rbx
  int hDest; // [rsp+A8h] [rbp+10h]
  HGDIOBJ h; // [rsp+B8h] [rbp+20h]

  MappedBitmap = CreateMappedBitmap(g_hinst, 545, 0, 0, 0);
  v6 = MappedBitmap;
  if ( a2 != 96 || a3 != 96 )
  {
    DC = GetDC(0);
    v8 = DC;
    if ( DC )
    {
      CompatibleDC = CreateCompatibleDC(DC);
      hdcSrc = CompatibleDC;
      if ( CompatibleDC )
      {
        h = SelectObject(CompatibleDC, MappedBitmap);
        v11 = MulDiv(13, a2, 96);
        hDest = MulDiv(11, a3, 96);
        v12 = CreateCompatibleDC(v8);
        if ( v12 )
        {
          v13 = 3 * v11;
          CompatibleBitmap = CreateCompatibleBitmap(v8, 3 * v11, hDest);
          v15 = CompatibleBitmap;
          if ( CompatibleBitmap )
          {
            v16 = SelectObject(v12, CompatibleBitmap);
            StretchBlt(v12, 0, 0, v13, hDest, hdcSrc, 0, 0, 39, 11, 0xCC0020u);
            v6 = v15;
            SelectObject(v12, v16);
          }
          DeleteDC(v12);
        }
        SelectObject(hdcSrc, h);
        if ( v6 != MappedBitmap )
          DeleteObject(MappedBitmap);
        DeleteDC(hdcSrc);
      }
      ReleaseDC(0, v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1803142c0  mov     [rsp+arg_0], rbx
0x1803142c5  push    rbp
0x1803142c6  push    rsi
0x1803142c7  push    rdi
0x1803142c8  push    r12
0x1803142ca  push    r13
0x1803142cc  push    r14
0x1803142ce  push    r15
0x1803142d0  sub     rsp, 60h
0x1803142d4  mov     rcx, cs:g_hinst; hInstance
0x1803142db  mov     ebx, r8d
0x1803142de  mov     r15d, edx
0x1803142e1  mov     [rsp+98h+iNumMaps], 0; iNumMaps
0x1803142e9  xor     r8d, r8d; wFlags
0x1803142ec  mov     edx, 221h; idBitmap
0x1803142f1  xor     r9d, r9d; lpColorMap
0x1803142f4  call    CreateMappedBitmap
0x1803142f9  mov     r13d, 60h ; '`'
0x1803142ff  mov     rbp, rax
0x180314302  mov     r14, rax
0x180314305  cmp     r15d, r13d
0x180314308  jnz     short loc_180314313
0x18031430a  cmp     ebx, r13d
0x18031430d  jz      loc_180314450
0x180314313  xor     ecx, ecx; hWnd
0x180314315  call    cs:__imp_GetDC
0x18031431b  mov     rdi, rax
0x18031431e  test    rax, rax
0x180314321  jz      loc_180314450
0x180314327  mov     rcx, rax; hdc
0x18031432a  call    cs:__imp_CreateCompatibleDC
0x180314330  mov     rsi, rax
0x180314333  test    rax, rax
0x180314336  jz      loc_180314445
0x18031433c  mov     rdx, rbp; h
0x18031433f  mov     rcx, rax; hdc
0x180314342  call    cs:__imp_SelectObject
0x180314348  mov     r8d, r13d; nDenominator
0x18031434b  mov     edx, r15d; nNumerator
0x18031434e  mov     ecx, 0Dh; nNumber
0x180314353  mov     [rsp+98h+h], rax
0x18031435b  call    cs:__imp_MulDiv
0x180314361  mov     r8d, r13d; nDenominator
0x180314364  mov     edx, ebx; nNumerator
0x180314366  mov     ecx, 0Bh; nNumber
0x18031436b  mov     r12d, eax
0x18031436e  call    cs:__imp_MulDiv
0x180314374  mov     rcx, rdi; hdc
0x180314377  mov     [rsp+98h+hDest], eax
0x18031437e  mov     ebx, eax
0x180314380  call    cs:__imp_CreateCompatibleDC
0x180314386  mov     r15, rax
0x180314389  test    rax, rax
0x18031438c  jz      loc_18031441D
0x180314392  lea     r13d, [r12+r12*2]
0x180314396  mov     r8d, ebx; cy
0x180314399  mov     edx, r13d; cx
0x18031439c  mov     rcx, rdi; hdc
0x18031439f  call    cs:__imp_CreateCompatibleBitmap
0x1803143a5  mov     r12, rax
0x1803143a8  test    rax, rax
0x1803143ab  jz      short loc_180314414
0x1803143ad  mov     rdx, rax; h
0x1803143b0  mov     rcx, r15; hdc
0x1803143b3  call    cs:__imp_SelectObject
0x1803143b9  mov     [rsp+98h+rop], 0CC0020h; rop
0x1803143c1  mov     r9d, r13d; wDest
0x1803143c4  mov     [rsp+98h+hSrc], 0Bh; hSrc
0x1803143cc  mov     rbx, rax
0x1803143cf  mov     eax, [rsp+98h+hDest]
0x1803143d6  xor     r8d, r8d; yDest
0x1803143d9  mov     [rsp+98h+wSrc], 27h ; '''; wSrc
0x1803143e1  xor     edx, edx; xDest
0x1803143e3  mov     [rsp+98h+ySrc], 0; ySrc
0x1803143eb  mov     rcx, r15; hdcDest
0x1803143ee  mov     [rsp+98h+xSrc], 0; xSrc
0x1803143f6  mov     [rsp+98h+hdcSrc], rsi; hdcSrc
0x1803143fb  mov     [rsp+98h+iNumMaps], eax; hDest
0x1803143ff  call    cs:__imp_StretchBlt
0x180314405  mov     rdx, rbx; h
0x180314408  mov     rcx, r15; hdc
0x18031440b  mov     r14, r12
0x18031440e  call    cs:__imp_SelectObject
0x180314414  mov     rcx, r15; hdc
0x180314417  call    cs:__imp_DeleteDC
0x18031441d  mov     rdx, [rsp+98h+h]; h
0x180314425  mov     rcx, rsi; hdc
0x180314428  call    cs:__imp_SelectObject
0x18031442e  cmp     r14, rbp
0x180314431  jz      short loc_18031443C
0x180314433  mov     rcx, rbp; ho
0x180314436  call    cs:__imp_DeleteObject
0x18031443c  mov     rcx, rsi; hdc
0x18031443f  call    cs:__imp_DeleteDC
0x180314445  mov     rdx, rdi; hDC
0x180314448  xor     ecx, ecx; hWnd
0x18031444a  call    cs:__imp_ReleaseDC
0x180314450  mov     rbx, [rsp+98h+arg_0]
0x180314458  mov     rax, r14
0x18031445b  add     rsp, 60h
0x18031445f  pop     r15
0x180314461  pop     r14
0x180314463  pop     r13
0x180314465  pop     r12
0x180314467  pop     rdi
0x180314468  pop     rsi
0x180314469  pop     rbp
0x18031446a  retn
```
