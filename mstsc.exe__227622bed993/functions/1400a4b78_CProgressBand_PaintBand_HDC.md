# CProgressBand::PaintBand(HDC__ *)

- ea: `0x1400a4b78`
- end: `0x1400a4d1f`
- name: `?PaintBand@CProgressBand@@AEAAHPEAUHDC__@@@Z`
- size: `423`
- prototype: `int(CProgressBand *__hidden this, HDC)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400a4ab4`
- `0x1400a4ad4`

## callees

- `0x1400a4b78`
- `0x140111220`

## import_xrefs

- `USER32!GetClientRect` at `0x1400a4bcf`
- `USER32!GetClientRect` at `0x1400a4bcf`
- `GDI32!DeleteDC` at `0x1400a4cee`
- `GDI32!DeleteDC` at `0x1400a4cee`
- `GDI32!StretchBlt` at `0x1400a4c66`
- `GDI32!StretchBlt` at `0x1400a4cbd`
- `GDI32!StretchBlt` at `0x1400a4c66`
- `GDI32!StretchBlt` at `0x1400a4cbd`
- `GDI32!CreateCompatibleDC` at `0x1400a4bb1`
- `GDI32!CreateCompatibleDC` at `0x1400a4bb1`
- `GDI32!SelectObject` at `0x1400a4bfd`
- `GDI32!SelectObject` at `0x1400a4cce`
- `GDI32!SelectObject` at `0x1400a4bfd`
- `GDI32!SelectObject` at `0x1400a4cce`
- `GDI32!RealizePalette` at `0x1400a4bf0`
- `GDI32!RealizePalette` at `0x1400a4bf0`
- `GDI32!SelectPalette` at `0x1400a4be4`
- `GDI32!SelectPalette` at `0x1400a4ce5`
- `GDI32!SelectPalette` at `0x1400a4be4`
- `GDI32!SelectPalette` at `0x1400a4ce5`

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
0x1400a4b78  mov     [rsp+arg_10], rbx
0x1400a4b7d  mov     [rsp+arg_18], rbp
0x1400a4b82  push    rsi
0x1400a4b83  push    rdi
0x1400a4b84  push    r12
0x1400a4b86  push    r14
0x1400a4b88  push    r15
0x1400a4b8a  sub     rsp, 80h
0x1400a4b91  mov     rax, cs:__security_cookie
0x1400a4b98  xor     rax, rsp
0x1400a4b9b  mov     [rsp+0A8h+var_38], rax
0x1400a4ba0  mov     r14, rcx
0x1400a4ba3  xorps   xmm0, xmm0
0x1400a4ba6  mov     rcx, rdx; hdc
0x1400a4ba9  mov     rsi, rdx
0x1400a4bac  movups  xmmword ptr [rsp+0A8h+Rect.left], xmm0
0x1400a4bb1  call    cs:__imp_CreateCompatibleDC
0x1400a4bb7  mov     rbp, rax
0x1400a4bba  test    rax, rax
0x1400a4bbd  jz      loc_1400A4CF4
0x1400a4bc3  mov     rcx, [r14+8]; hWnd
0x1400a4bc7  lea     rdx, [rsp+0A8h+Rect]; lpRect
0x1400a4bcc  xor     r15d, r15d
0x1400a4bcf  call    cs:__imp_GetClientRect
0x1400a4bd5  mov     rdx, [r14+40h]; hPal
0x1400a4bd9  test    rdx, rdx
0x1400a4bdc  jz      short loc_1400A4BF6
0x1400a4bde  xor     r8d, r8d; bForceBkgd
0x1400a4be1  mov     rcx, rsi; hdc
0x1400a4be4  call    cs:__imp_SelectPalette
0x1400a4bea  mov     rcx, rsi; hdc
0x1400a4bed  mov     r15, rax
0x1400a4bf0  call    cs:__imp_RealizePalette
0x1400a4bf6  mov     rdx, [r14+20h]; h
0x1400a4bfa  mov     rcx, rbp; hdc
0x1400a4bfd  call    cs:__imp_SelectObject
0x1400a4c03  mov     edi, [rsp+0A8h+Rect.right]
0x1400a4c07  mov     r8d, 2
0x1400a4c0d  sub     edi, [rsp+0A8h+Rect.left]
0x1400a4c11  mov     r12, rax
0x1400a4c14  mov     eax, [r14+30h]
0x1400a4c18  inc     edi
0x1400a4c1a  sub     eax, [r14+28h]
0x1400a4c1e  mov     r9d, edi; wDest
0x1400a4c21  mov     ecx, [r14+34h]
0x1400a4c25  cmp     eax, edi
0x1400a4c27  mov     ebx, eax
0x1400a4c29  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x1400a4c31  cmovge  ebx, edi
0x1400a4c34  sub     ecx, [r14+2Ch]
0x1400a4c38  mov     [rsp+0A8h+hSrc], ecx; hSrc
0x1400a4c3c  sub     eax, ebx
0x1400a4c3e  mov     [rsp+0A8h+wSrc], ebx; wSrc
0x1400a4c42  cdq
0x1400a4c43  idiv    r8d
0x1400a4c46  mov     r8d, [r14+18h]; yDest
0x1400a4c4a  mov     edx, [r14+38h]; xDest
0x1400a4c4e  mov     [rsp+0A8h+ySrc], 0; ySrc
0x1400a4c56  mov     [rsp+0A8h+xSrc], eax; xSrc
0x1400a4c5a  mov     [rsp+0A8h+hdcSrc], rbp; hdcSrc
0x1400a4c5f  mov     [rsp+0A8h+hDest], ecx; hDest
0x1400a4c63  mov     rcx, rsi; hdcDest
0x1400a4c66  call    cs:__imp_StretchBlt
0x1400a4c6c  mov     eax, [r14+30h]
0x1400a4c70  mov     r8d, 2
0x1400a4c76  mov     ecx, [r14+34h]
0x1400a4c7a  sub     eax, ebx
0x1400a4c7c  sub     eax, [r14+28h]
0x1400a4c80  mov     r9d, edi; wDest
0x1400a4c83  sub     ecx, [r14+2Ch]
0x1400a4c87  cdq
0x1400a4c88  idiv    r8d
0x1400a4c8b  mov     edx, [r14+38h]
0x1400a4c8f  mov     r8d, [r14+18h]; yDest
0x1400a4c93  sub     edx, edi; xDest
0x1400a4c95  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x1400a4c9d  mov     [rsp+0A8h+hSrc], ecx; hSrc
0x1400a4ca1  mov     [rsp+0A8h+wSrc], ebx; wSrc
0x1400a4ca5  mov     [rsp+0A8h+ySrc], 0; ySrc
0x1400a4cad  mov     [rsp+0A8h+xSrc], eax; xSrc
0x1400a4cb1  mov     [rsp+0A8h+hdcSrc], rbp; hdcSrc
0x1400a4cb6  mov     [rsp+0A8h+hDest], ecx; hDest
0x1400a4cba  mov     rcx, rsi; hdcDest
0x1400a4cbd  call    cs:__imp_StretchBlt
0x1400a4cc3  test    r12, r12
0x1400a4cc6  jz      short loc_1400A4CD4
0x1400a4cc8  mov     rdx, r12; h
0x1400a4ccb  mov     rcx, rbp; hdc
0x1400a4cce  call    cs:__imp_SelectObject
0x1400a4cd4  test    r15, r15
0x1400a4cd7  jz      short loc_1400A4CEB
0x1400a4cd9  mov     r8d, 1; bForceBkgd
0x1400a4cdf  mov     rdx, r15; hPal
0x1400a4ce2  mov     rcx, rsi; hdc
0x1400a4ce5  call    cs:__imp_SelectPalette
0x1400a4ceb  mov     rcx, rbp; hdc
0x1400a4cee  call    cs:__imp_DeleteDC
0x1400a4cf4  xor     eax, eax
0x1400a4cf6  mov     rcx, [rsp+0A8h+var_38]
0x1400a4cfb  xor     rcx, rsp; StackCookie
0x1400a4cfe  call    __security_check_cookie
0x1400a4d03  lea     r11, [rsp+0A8h+var_28]
0x1400a4d0b  mov     rbx, [r11+40h]
0x1400a4d0f  mov     rbp, [r11+48h]
0x1400a4d13  mov     rsp, r11
0x1400a4d16  pop     r15
0x1400a4d18  pop     r14
0x1400a4d1a  pop     r12
0x1400a4d1c  pop     rdi
0x1400a4d1d  pop     rsi
0x1400a4d1e  retn
```
