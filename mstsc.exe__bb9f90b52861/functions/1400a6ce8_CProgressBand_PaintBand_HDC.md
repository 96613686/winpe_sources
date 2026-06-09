# CProgressBand::PaintBand(HDC__ *)

- ea: `0x1400a6ce8`
- end: `0x1400a6e8f`
- name: `?PaintBand@CProgressBand@@AEAAHPEAUHDC__@@@Z`
- size: `423`
- prototype: `int(CProgressBand *__hidden this, HDC)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400a6c24`
- `0x1400a6c44`

## callees

- `0x1400a6ce8`
- `0x140113390`

## import_xrefs

- `USER32!GetClientRect` at `0x1400a6d3f`
- `USER32!GetClientRect` at `0x1400a6d3f`
- `GDI32!DeleteDC` at `0x1400a6e5e`
- `GDI32!DeleteDC` at `0x1400a6e5e`
- `GDI32!StretchBlt` at `0x1400a6dd6`
- `GDI32!StretchBlt` at `0x1400a6e2d`
- `GDI32!StretchBlt` at `0x1400a6dd6`
- `GDI32!StretchBlt` at `0x1400a6e2d`
- `GDI32!CreateCompatibleDC` at `0x1400a6d21`
- `GDI32!CreateCompatibleDC` at `0x1400a6d21`
- `GDI32!SelectObject` at `0x1400a6d6d`
- `GDI32!SelectObject` at `0x1400a6e3e`
- `GDI32!SelectObject` at `0x1400a6d6d`
- `GDI32!SelectObject` at `0x1400a6e3e`
- `GDI32!RealizePalette` at `0x1400a6d60`
- `GDI32!RealizePalette` at `0x1400a6d60`
- `GDI32!SelectPalette` at `0x1400a6d54`
- `GDI32!SelectPalette` at `0x1400a6e55`
- `GDI32!SelectPalette` at `0x1400a6d54`
- `GDI32!SelectPalette` at `0x1400a6e55`

## pseudocode

```c
__int64 __fastcall CProgressBand::PaintBand(CProgressBand *this, HDC a2)
{
  HDC hdcSrc; // rbp
  HPALETTE v5; // r15
  HPALETTE v6; // rdx
  HGDIOBJ v7; // r12
  int v8; // edi
  int v9; // eax
  int wSrc; // ebx
  int hDest; // [rsp+20h] [rbp-88h]
  struct tagRECT Rect; // [rsp+60h] [rbp-48h] BYREF

  Rect = 0;
  hdcSrc = CreateCompatibleDC(a2);
  if ( hdcSrc )
  {
    v5 = 0;
    GetClientRect(*((HWND *)this + 1), &Rect);
    v6 = (HPALETTE)*((_QWORD *)this + 8);
    if ( v6 )
    {
      v5 = SelectPalette(a2, v6, 0);
      RealizePalette(a2);
    }
    v7 = SelectObject(hdcSrc, *((HGDIOBJ *)this + 4));
    v8 = Rect.right - Rect.left + 1;
    v9 = *((_DWORD *)this + 12) - *((_DWORD *)this + 10);
    wSrc = v9;
    if ( v9 >= v8 )
      wSrc = Rect.right - Rect.left + 1;
    StretchBlt(
      a2,
      *((_DWORD *)this + 14),
      *((_DWORD *)this + 6),
      v8,
      *((_DWORD *)this + 13) - *((_DWORD *)this + 11),
      hdcSrc,
      (v9 - wSrc) / 2,
      0,
      wSrc,
      *((_DWORD *)this + 13) - *((_DWORD *)this + 11),
      0xCC0020u);
    hDest = *((_DWORD *)this + 13) - *((_DWORD *)this + 11);
    StretchBlt(
      a2,
      *((_DWORD *)this + 14) - v8,
      *((_DWORD *)this + 6),
      v8,
      hDest,
      hdcSrc,
      (*((_DWORD *)this + 12) - wSrc - *((_DWORD *)this + 10)) / 2,
      0,
      wSrc,
      hDest,
      0xCC0020u);
    if ( v7 )
      SelectObject(hdcSrc, v7);
    if ( v5 )
      SelectPalette(a2, v5, 1);
    DeleteDC(hdcSrc);
  }
  return 0;
}

```

## disassembly

```asm
0x1400a6ce8  mov     [rsp+arg_10], rbx
0x1400a6ced  mov     [rsp+arg_18], rbp
0x1400a6cf2  push    rsi
0x1400a6cf3  push    rdi
0x1400a6cf4  push    r12
0x1400a6cf6  push    r14
0x1400a6cf8  push    r15
0x1400a6cfa  sub     rsp, 80h
0x1400a6d01  mov     rax, cs:__security_cookie
0x1400a6d08  xor     rax, rsp
0x1400a6d0b  mov     [rsp+0A8h+var_38], rax
0x1400a6d10  mov     r14, rcx
0x1400a6d13  xorps   xmm0, xmm0
0x1400a6d16  mov     rcx, rdx; hdc
0x1400a6d19  mov     rsi, rdx
0x1400a6d1c  movups  xmmword ptr [rsp+0A8h+Rect.left], xmm0
0x1400a6d21  call    cs:__imp_CreateCompatibleDC
0x1400a6d27  mov     rbp, rax
0x1400a6d2a  test    rax, rax
0x1400a6d2d  jz      loc_1400A6E64
0x1400a6d33  mov     rcx, [r14+8]; hWnd
0x1400a6d37  lea     rdx, [rsp+0A8h+Rect]; lpRect
0x1400a6d3c  xor     r15d, r15d
0x1400a6d3f  call    cs:__imp_GetClientRect
0x1400a6d45  mov     rdx, [r14+40h]; hPal
0x1400a6d49  test    rdx, rdx
0x1400a6d4c  jz      short loc_1400A6D66
0x1400a6d4e  xor     r8d, r8d; bForceBkgd
0x1400a6d51  mov     rcx, rsi; hdc
0x1400a6d54  call    cs:__imp_SelectPalette
0x1400a6d5a  mov     rcx, rsi; hdc
0x1400a6d5d  mov     r15, rax
0x1400a6d60  call    cs:__imp_RealizePalette
0x1400a6d66  mov     rdx, [r14+20h]; h
0x1400a6d6a  mov     rcx, rbp; hdc
0x1400a6d6d  call    cs:__imp_SelectObject
0x1400a6d73  mov     edi, [rsp+0A8h+Rect.right]
0x1400a6d77  mov     r8d, 2
0x1400a6d7d  sub     edi, [rsp+0A8h+Rect.left]
0x1400a6d81  mov     r12, rax
0x1400a6d84  mov     eax, [r14+30h]
0x1400a6d88  inc     edi
0x1400a6d8a  sub     eax, [r14+28h]
0x1400a6d8e  mov     r9d, edi; wDest
0x1400a6d91  mov     ecx, [r14+34h]
0x1400a6d95  cmp     eax, edi
0x1400a6d97  mov     ebx, eax
0x1400a6d99  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x1400a6da1  cmovge  ebx, edi
0x1400a6da4  sub     ecx, [r14+2Ch]
0x1400a6da8  mov     [rsp+0A8h+hSrc], ecx; hSrc
0x1400a6dac  sub     eax, ebx
0x1400a6dae  mov     [rsp+0A8h+wSrc], ebx; wSrc
0x1400a6db2  cdq
0x1400a6db3  idiv    r8d
0x1400a6db6  mov     r8d, [r14+18h]; yDest
0x1400a6dba  mov     edx, [r14+38h]; xDest
0x1400a6dbe  mov     [rsp+0A8h+ySrc], 0; ySrc
0x1400a6dc6  mov     [rsp+0A8h+xSrc], eax; xSrc
0x1400a6dca  mov     [rsp+0A8h+hdcSrc], rbp; hdcSrc
0x1400a6dcf  mov     [rsp+0A8h+hDest], ecx; hDest
0x1400a6dd3  mov     rcx, rsi; hdcDest
0x1400a6dd6  call    cs:__imp_StretchBlt
0x1400a6ddc  mov     eax, [r14+30h]
0x1400a6de0  mov     r8d, 2
0x1400a6de6  mov     ecx, [r14+34h]
0x1400a6dea  sub     eax, ebx
0x1400a6dec  sub     eax, [r14+28h]
0x1400a6df0  mov     r9d, edi; wDest
0x1400a6df3  sub     ecx, [r14+2Ch]
0x1400a6df7  cdq
0x1400a6df8  idiv    r8d
0x1400a6dfb  mov     edx, [r14+38h]
0x1400a6dff  mov     r8d, [r14+18h]; yDest
0x1400a6e03  sub     edx, edi; xDest
0x1400a6e05  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x1400a6e0d  mov     [rsp+0A8h+hSrc], ecx; hSrc
0x1400a6e11  mov     [rsp+0A8h+wSrc], ebx; wSrc
0x1400a6e15  mov     [rsp+0A8h+ySrc], 0; ySrc
0x1400a6e1d  mov     [rsp+0A8h+xSrc], eax; xSrc
0x1400a6e21  mov     [rsp+0A8h+hdcSrc], rbp; hdcSrc
0x1400a6e26  mov     [rsp+0A8h+hDest], ecx; hDest
0x1400a6e2a  mov     rcx, rsi; hdcDest
0x1400a6e2d  call    cs:__imp_StretchBlt
0x1400a6e33  test    r12, r12
0x1400a6e36  jz      short loc_1400A6E44
0x1400a6e38  mov     rdx, r12; h
0x1400a6e3b  mov     rcx, rbp; hdc
0x1400a6e3e  call    cs:__imp_SelectObject
0x1400a6e44  test    r15, r15
0x1400a6e47  jz      short loc_1400A6E5B
0x1400a6e49  mov     r8d, 1; bForceBkgd
0x1400a6e4f  mov     rdx, r15; hPal
0x1400a6e52  mov     rcx, rsi; hdc
0x1400a6e55  call    cs:__imp_SelectPalette
0x1400a6e5b  mov     rcx, rbp; hdc
0x1400a6e5e  call    cs:__imp_DeleteDC
0x1400a6e64  xor     eax, eax
0x1400a6e66  mov     rcx, [rsp+0A8h+var_38]
0x1400a6e6b  xor     rcx, rsp; StackCookie
0x1400a6e6e  call    __security_check_cookie
0x1400a6e73  lea     r11, [rsp+0A8h+var_28]
0x1400a6e7b  mov     rbx, [r11+40h]
0x1400a6e7f  mov     rbp, [r11+48h]
0x1400a6e83  mov     rsp, r11
0x1400a6e86  pop     r15
0x1400a6e88  pop     r14
0x1400a6e8a  pop     r12
0x1400a6e8c  pop     rdi
0x1400a6e8d  pop     rsi
0x1400a6e8e  retn
```
