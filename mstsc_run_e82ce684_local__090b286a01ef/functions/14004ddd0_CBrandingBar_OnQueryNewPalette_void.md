# CBrandingBar::OnQueryNewPalette(void)

- ea: `0x14004ddd0`
- end: `0x14004de64`
- name: `?OnQueryNewPalette@CBrandingBar@@QEAAHXZ`
- size: `148`
- prototype: `__int64 __fastcall(CBrandingBar *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140049fa0`

## callees

- `0x14004ddd0`

## import_xrefs

- `USER32!ReleaseDC` at `0x14004de45`
- `USER32!ReleaseDC` at `0x14004de45`
- `USER32!GetDC` at `0x14004dded`
- `USER32!GetDC` at `0x14004dded`
- `USER32!UpdateWindow` at `0x14004de24`
- `USER32!UpdateWindow` at `0x14004de24`
- `GDI32!UpdateColors` at `0x14004de1a`
- `GDI32!UpdateColors` at `0x14004de1a`
- `GDI32!RealizePalette` at `0x14004de11`
- `GDI32!RealizePalette` at `0x14004de11`
- `GDI32!SelectPalette` at `0x14004de05`
- `GDI32!SelectPalette` at `0x14004de38`
- `GDI32!SelectPalette` at `0x14004de05`
- `GDI32!SelectPalette` at `0x14004de38`

## pseudocode

```c
__int64 __fastcall CBrandingBar::OnQueryNewPalette(CBrandingBar *this)
{
  HDC DC; // rax
  HDC v3; // rdi
  HPALETTE v4; // rsi

  if ( !*((_QWORD *)this + 3) )
    return 0;
  DC = GetDC(*((HWND *)this + 1));
  v3 = DC;
  if ( !DC )
    return 0;
  v4 = SelectPalette(DC, *((HPALETTE *)this + 3), 0);
  RealizePalette(v3);
  UpdateColors(v3);
  UpdateWindow(*((HWND *)this + 1));
  if ( v4 )
    SelectPalette(v3, v4, 0);
  ReleaseDC(*((HWND *)this + 1), v3);
  return 1;
}

```

## disassembly

```asm
0x14004ddd0  mov     [rsp+arg_0], rbx
0x14004ddd5  mov     [rsp+arg_8], rsi
0x14004ddda  push    rdi
0x14004dddb  sub     rsp, 20h
0x14004dddf  cmp     qword ptr [rcx+18h], 0
0x14004dde4  mov     rbx, rcx
0x14004dde7  jz      short loc_14004DE52
0x14004dde9  mov     rcx, [rcx+8]; hWnd
0x14004dded  call    cs:__imp_GetDC
0x14004ddf3  mov     rdi, rax
0x14004ddf6  test    rax, rax
0x14004ddf9  jz      short loc_14004DE52
0x14004ddfb  mov     rdx, [rbx+18h]; hPal
0x14004ddff  xor     r8d, r8d; bForceBkgd
0x14004de02  mov     rcx, rax; hdc
0x14004de05  call    cs:__imp_SelectPalette
0x14004de0b  mov     rcx, rdi; hdc
0x14004de0e  mov     rsi, rax
0x14004de11  call    cs:__imp_RealizePalette
0x14004de17  mov     rcx, rdi; hdc
0x14004de1a  call    cs:__imp_UpdateColors
0x14004de20  mov     rcx, [rbx+8]; hWnd
0x14004de24  call    cs:__imp_UpdateWindow
0x14004de2a  test    rsi, rsi
0x14004de2d  jz      short loc_14004DE3E
0x14004de2f  xor     r8d, r8d; bForceBkgd
0x14004de32  mov     rdx, rsi; hPal
0x14004de35  mov     rcx, rdi; hdc
0x14004de38  call    cs:__imp_SelectPalette
0x14004de3e  mov     rcx, [rbx+8]; hWnd
0x14004de42  mov     rdx, rdi; hDC
0x14004de45  call    cs:__imp_ReleaseDC
0x14004de4b  mov     eax, 1
0x14004de50  jmp     short loc_14004DE54
0x14004de52  xor     eax, eax
0x14004de54  mov     rbx, [rsp+28h+arg_0]
0x14004de59  mov     rsi, [rsp+28h+arg_8]
0x14004de5e  add     rsp, 20h
0x14004de62  pop     rdi
0x14004de63  retn
```
