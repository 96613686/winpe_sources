# CBrandingBar::OnQueryNewPalette(void)

- ea: `0x14004bc60`
- end: `0x14004bcf4`
- name: `?OnQueryNewPalette@CBrandingBar@@QEAAHXZ`
- size: `148`
- prototype: `__int64 __fastcall(CBrandingBar *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140047e30`

## callees

- `0x14004bc60`

## import_xrefs

- `USER32!ReleaseDC` at `0x14004bcd5`
- `USER32!ReleaseDC` at `0x14004bcd5`
- `USER32!GetDC` at `0x14004bc7d`
- `USER32!GetDC` at `0x14004bc7d`
- `USER32!UpdateWindow` at `0x14004bcb4`
- `USER32!UpdateWindow` at `0x14004bcb4`
- `GDI32!UpdateColors` at `0x14004bcaa`
- `GDI32!UpdateColors` at `0x14004bcaa`
- `GDI32!RealizePalette` at `0x14004bca1`
- `GDI32!RealizePalette` at `0x14004bca1`
- `GDI32!SelectPalette` at `0x14004bc95`
- `GDI32!SelectPalette` at `0x14004bcc8`
- `GDI32!SelectPalette` at `0x14004bc95`
- `GDI32!SelectPalette` at `0x14004bcc8`

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
0x14004bc60  mov     [rsp+arg_0], rbx
0x14004bc65  mov     [rsp+arg_8], rsi
0x14004bc6a  push    rdi
0x14004bc6b  sub     rsp, 20h
0x14004bc6f  cmp     qword ptr [rcx+18h], 0
0x14004bc74  mov     rbx, rcx
0x14004bc77  jz      short loc_14004BCE2
0x14004bc79  mov     rcx, [rcx+8]; hWnd
0x14004bc7d  call    cs:__imp_GetDC
0x14004bc83  mov     rdi, rax
0x14004bc86  test    rax, rax
0x14004bc89  jz      short loc_14004BCE2
0x14004bc8b  mov     rdx, [rbx+18h]; hPal
0x14004bc8f  xor     r8d, r8d; bForceBkgd
0x14004bc92  mov     rcx, rax; hdc
0x14004bc95  call    cs:__imp_SelectPalette
0x14004bc9b  mov     rcx, rdi; hdc
0x14004bc9e  mov     rsi, rax
0x14004bca1  call    cs:__imp_RealizePalette
0x14004bca7  mov     rcx, rdi; hdc
0x14004bcaa  call    cs:__imp_UpdateColors
0x14004bcb0  mov     rcx, [rbx+8]; hWnd
0x14004bcb4  call    cs:__imp_UpdateWindow
0x14004bcba  test    rsi, rsi
0x14004bcbd  jz      short loc_14004BCCE
0x14004bcbf  xor     r8d, r8d; bForceBkgd
0x14004bcc2  mov     rdx, rsi; hPal
0x14004bcc5  mov     rcx, rdi; hdc
0x14004bcc8  call    cs:__imp_SelectPalette
0x14004bcce  mov     rcx, [rbx+8]; hWnd
0x14004bcd2  mov     rdx, rdi; hDC
0x14004bcd5  call    cs:__imp_ReleaseDC
0x14004bcdb  mov     eax, 1
0x14004bce0  jmp     short loc_14004BCE4
0x14004bce2  xor     eax, eax
0x14004bce4  mov     rbx, [rsp+28h+arg_0]
0x14004bce9  mov     rsi, [rsp+28h+arg_8]
0x14004bcee  add     rsp, 20h
0x14004bcf2  pop     rdi
0x14004bcf3  retn
```
