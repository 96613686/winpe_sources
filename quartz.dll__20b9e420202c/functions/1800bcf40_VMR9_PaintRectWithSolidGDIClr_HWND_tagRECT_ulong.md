# VMR9::PaintRectWithSolidGDIClr(HWND__ *,tagRECT *,ulong)

- ea: `0x1800bcf40`
- end: `0x1800bcfbc`
- name: `?PaintRectWithSolidGDIClr@VMR9@@YAXPEAUHWND__@@PEAUtagRECT@@K@Z`
- size: `124`
- prototype: `void __fastcall(HWND hWnd, HWND lprc, COLORREF color, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800bd27c`
- `0x1800e5cbc`

## callees

- `0x1800bcf40`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800bcf94`
- `GDI32!DeleteObject` at `0x1800bcf94`
- `GDI32!CreateSolidBrush` at `0x1800bcf68`
- `GDI32!CreateSolidBrush` at `0x1800bcf68`
- `USER32!FillRect` at `0x1800bcf85`
- `USER32!FillRect` at `0x1800bcf85`
- `USER32!ReleaseDC` at `0x1800bcfa6`
- `USER32!ReleaseDC` at `0x1800bcfa6`
- `USER32!GetDC` at `0x1800bcf52`
- `USER32!GetDC` at `0x1800bcf52`

## pseudocode

```c
void __fastcall VMR9::PaintRectWithSolidGDIClr(HWND hWnd, const RECT *lprc, COLORREF color)
{
  HDC DC; // rdi
  HBRUSH SolidBrush; // rax
  HBRUSH v8; // rbx

  DC = GetDC(hWnd);
  if ( DC )
  {
    SolidBrush = CreateSolidBrush(color);
    v8 = SolidBrush;
    if ( SolidBrush )
    {
      FillRect(DC, lprc, SolidBrush);
      DeleteObject(v8);
    }
    ReleaseDC(hWnd, DC);
  }
}

```

## disassembly

```asm
0x1800bcf40  push    rbx
0x1800bcf42  push    rbp
0x1800bcf43  push    rsi
0x1800bcf44  push    rdi
0x1800bcf45  sub     rsp, 28h
0x1800bcf49  mov     ebx, r8d
0x1800bcf4c  mov     rbp, rdx
0x1800bcf4f  mov     rsi, rcx
0x1800bcf52  call    cs:__imp_GetDC
0x1800bcf59  nop     dword ptr [rax+rax+00h]
0x1800bcf5e  mov     rdi, rax
0x1800bcf61  test    rax, rax
0x1800bcf64  jz      short loc_1800BCFB2
0x1800bcf66  mov     ecx, ebx; color
0x1800bcf68  call    cs:__imp_CreateSolidBrush
0x1800bcf6f  nop     dword ptr [rax+rax+00h]
0x1800bcf74  mov     rbx, rax
0x1800bcf77  test    rax, rax
0x1800bcf7a  jz      short loc_1800BCFA0
0x1800bcf7c  mov     r8, rax; hbr
0x1800bcf7f  mov     rdx, rbp; lprc
0x1800bcf82  mov     rcx, rdi; hDC
0x1800bcf85  call    cs:__imp_FillRect
0x1800bcf8c  nop     dword ptr [rax+rax+00h]
0x1800bcf91  mov     rcx, rbx; ho
0x1800bcf94  call    cs:__imp_DeleteObject
0x1800bcf9b  nop     dword ptr [rax+rax+00h]
0x1800bcfa0  mov     rdx, rdi; hDC
0x1800bcfa3  mov     rcx, rsi; hWnd
0x1800bcfa6  call    cs:__imp_ReleaseDC
0x1800bcfad  nop     dword ptr [rax+rax+00h]
0x1800bcfb2  add     rsp, 28h
0x1800bcfb6  pop     rdi
0x1800bcfb7  pop     rsi
0x1800bcfb8  pop     rbp
0x1800bcfb9  pop     rbx
0x1800bcfba  retn
```
