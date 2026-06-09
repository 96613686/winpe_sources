# LVSeeThruScroll

- ea: `0x180050dbc`
- end: `0x180050eb2`
- name: `LVSeeThruScroll`
- size: `246`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180054630`
- `0x180074e00`

## callees

- `0x180050dbc`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180050e10`
- `GDI32!CreateCompatibleDC` at `0x180050e10`
- `GDI32!CreateCompatibleBitmap` at `0x180050e29`
- `GDI32!CreateCompatibleBitmap` at `0x180050e29`
- `GDI32!SelectObject` at `0x180050e38`
- `GDI32!SelectObject` at `0x180050e38`
- `GDI32!BitBlt` at `0x180050e7d`
- `GDI32!BitBlt` at `0x180050e7d`
- `GDI32!DeleteObject` at `0x180050eab`
- `GDI32!DeleteDC` at `0x180050e92`
- `GDI32!DeleteDC` at `0x180050e92`
- `USER32!GetDC` at `0x180050dd6`
- `USER32!GetDC` at `0x180050dd6`
- `USER32!ReleaseDC` at `0x180050e89`
- `USER32!ReleaseDC` at `0x180050e89`
- `USER32!SendMessageW` at `0x180050e4f`
- `USER32!SendMessageW` at `0x180050e4f`

## pseudocode

```c
BOOL __fastcall LVSeeThruScroll(__int64 a1, int *a2)
{
  HDC DC; // rax
  HDC v5; // r13
  int v6; // ebp
  int y1; // r15d
  int cy; // r14d
  int x1; // r12d
  HDC hdcSrc; // rdi
  HBITMAP CompatibleBitmap; // rbx

  DC = GetDC(*(HWND *)a1);
  v5 = DC;
  if ( a2 )
  {
    x1 = *a2;
    v6 = a2[2] - *a2;
    y1 = a2[1];
    cy = a2[3] - y1;
  }
  else
  {
    v6 = *(_DWORD *)(a1 + 164);
    y1 = 0;
    cy = *(_DWORD *)(a1 + 168);
    x1 = 0;
  }
  hdcSrc = CreateCompatibleDC(DC);
  CompatibleBitmap = CreateCompatibleBitmap(v5, *(_DWORD *)(a1 + 164), *(_DWORD *)(a1 + 168));
  SelectObject(hdcSrc, CompatibleBitmap);
  SendMessageW(*(HWND *)a1, 0x317u, (WPARAM)hdcSrc, 12);
  BitBlt(v5, x1, y1, v6, cy, hdcSrc, x1, y1, 0xCC0020u);
  ReleaseDC(*(HWND *)a1, v5);
  DeleteDC(hdcSrc);
  return DeleteObject(CompatibleBitmap);
}

```

## disassembly

```asm
0x180050dbc  push    rbx
0x180050dbe  push    rbp
0x180050dbf  push    rsi
0x180050dc0  push    rdi
0x180050dc1  push    r12
0x180050dc3  push    r13
0x180050dc5  push    r14
0x180050dc7  push    r15
0x180050dc9  sub     rsp, 58h
0x180050dcd  mov     rsi, rcx
0x180050dd0  mov     rbx, rdx
0x180050dd3  mov     rcx, [rcx]; hWnd
0x180050dd6  call    cs:__imp_GetDC
0x180050ddc  mov     r13, rax
0x180050ddf  test    rbx, rbx
0x180050de2  jnz     short loc_180050DF9
0x180050de4  mov     ebp, [rsi+0A4h]
0x180050dea  xor     r15d, r15d
0x180050ded  mov     r14d, [rsi+0A8h]
0x180050df4  xor     r12d, r12d
0x180050df7  jmp     short loc_180050E0D
0x180050df9  mov     ebp, [rbx+8]
0x180050dfc  mov     r12d, [rbx]
0x180050dff  sub     ebp, r12d
0x180050e02  mov     r14d, [rbx+0Ch]
0x180050e06  mov     r15d, [rbx+4]
0x180050e0a  sub     r14d, r15d
0x180050e0d  mov     rcx, r13; hdc
0x180050e10  call    cs:__imp_CreateCompatibleDC
0x180050e16  mov     r8d, [rsi+0A8h]; cy
0x180050e1d  mov     rcx, r13; hdc
0x180050e20  mov     edx, [rsi+0A4h]; cx
0x180050e26  mov     rdi, rax
0x180050e29  call    cs:__imp_CreateCompatibleBitmap
0x180050e2f  mov     rdx, rax; h
0x180050e32  mov     rcx, rdi; hdc
0x180050e35  mov     rbx, rax
0x180050e38  call    cs:__imp_SelectObject
0x180050e3e  mov     rcx, [rsi]; hWnd
0x180050e41  mov     r9d, 0Ch; lParam
0x180050e47  mov     r8, rdi; wParam
0x180050e4a  mov     edx, 317h; Msg
0x180050e4f  call    cs:__imp_SendMessageW
0x180050e55  mov     [rsp+98h+rop], 0CC0020h; rop
0x180050e5d  mov     r9d, ebp; cx
0x180050e60  mov     [rsp+98h+y1], r15d; y1
0x180050e65  mov     r8d, r15d; y
0x180050e68  mov     [rsp+98h+x1], r12d; x1
0x180050e6d  mov     edx, r12d; x
0x180050e70  mov     [rsp+98h+hdcSrc], rdi; hdcSrc
0x180050e75  mov     rcx, r13; hdc
0x180050e78  mov     [rsp+98h+cy], r14d; cy
0x180050e7d  call    cs:__imp_BitBlt
0x180050e83  mov     rcx, [rsi]; hWnd
0x180050e86  mov     rdx, r13; hDC
0x180050e89  call    cs:__imp_ReleaseDC
0x180050e8f  mov     rcx, rdi; hdc
0x180050e92  call    cs:__imp_DeleteDC
0x180050e98  mov     rcx, rbx
0x180050e9b  add     rsp, 58h
0x180050e9f  pop     r15
0x180050ea1  pop     r14
0x180050ea3  pop     r13
0x180050ea5  pop     r12
0x180050ea7  pop     rdi
0x180050ea8  pop     rsi
0x180050ea9  pop     rbp
0x180050eaa  pop     rbx
0x180050eab  jmp     cs:__imp_DeleteObject
```
