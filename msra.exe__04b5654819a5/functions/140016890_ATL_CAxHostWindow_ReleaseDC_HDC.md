# ATL::CAxHostWindow::ReleaseDC(HDC__ *)

- ea: `0x140016890`
- end: `0x14001696d`
- name: `?ReleaseDC@CAxHostWindow@ATL@@UEAAJPEAUHDC__@@@Z`
- size: `221`
- prototype: `int(ATL::CAxHostWindow *__hidden this, HDC)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140016890`
- `0x14004ad80`

## import_xrefs

- `GDI32!BitBlt` at `0x140016919`
- `GDI32!BitBlt` at `0x140016919`
- `GDI32!DeleteDC` at `0x140016928`
- `GDI32!DeleteDC` at `0x140016928`
- `USER32!ReleaseDC` at `0x14001693f`
- `USER32!ReleaseDC` at `0x14001693f`
- `USER32!GetClientRect` at `0x1400168d0`
- `USER32!GetClientRect` at `0x1400168d0`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::ReleaseDC(ATL::CAxHostWindow *this, HDC a2)
{
  bool v2; // zf
  HWND v5; // rcx
  struct tagRECT Rect; // [rsp+50h] [rbp-28h] BYREF

  v2 = *((_QWORD *)this + 11) == 0;
  *((_BYTE *)this + 96) = 1;
  if ( !v2 )
  {
    v5 = (HWND)*((_QWORD *)this - 10);
    Rect = 0;
    GetClientRect(v5, &Rect);
    BitBlt(
      *((HDC *)this + 11),
      Rect.left,
      Rect.top,
      Rect.right - Rect.left,
      Rect.bottom - Rect.top,
      a2,
      0,
      0,
      0xCC0020u);
    DeleteDC(a2);
    a2 = (HDC)*((_QWORD *)this + 11);
  }
  ReleaseDC(*((HWND *)this - 10), a2);
  return 0;
}

```

## disassembly

```asm
0x140016890  mov     [rsp+arg_10], rbx
0x140016895  mov     [rsp+arg_18], rsi
0x14001689a  push    rdi
0x14001689b  sub     rsp, 70h
0x14001689f  mov     rax, cs:__security_cookie
0x1400168a6  xor     rax, rsp
0x1400168a9  mov     [rsp+78h+var_18], rax
0x1400168ae  cmp     qword ptr [rcx+58h], 0
0x1400168b3  mov     rsi, rdx
0x1400168b6  mov     rdi, rcx
0x1400168b9  mov     byte ptr [rcx+60h], 1
0x1400168bd  jz      short loc_140016938
0x1400168bf  mov     rcx, [rcx-50h]; hWnd
0x1400168c3  lea     rdx, [rsp+78h+Rect]; lpRect
0x1400168c8  xorps   xmm0, xmm0
0x1400168cb  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x1400168d0  call    cs:__imp_GetClientRect
0x1400168d7  nop     dword ptr [rax+rax+00h]
0x1400168dc  mov     eax, [rsp+78h+Rect.bottom]
0x1400168e0  mov     r8d, [rsp+78h+Rect.top]; y
0x1400168e5  sub     eax, r8d
0x1400168e8  mov     r9d, [rsp+78h+Rect.right]
0x1400168ed  mov     edx, [rsp+78h+Rect.left]; x
0x1400168f1  sub     r9d, edx; cx
0x1400168f4  mov     rcx, [rdi+58h]; hdc
0x1400168f8  mov     [rsp+78h+rop], 0CC0020h; rop
0x140016900  mov     [rsp+78h+y1], 0; y1
0x140016908  mov     [rsp+78h+x1], 0; x1
0x140016910  mov     [rsp+78h+hdcSrc], rsi; hdcSrc
0x140016915  mov     [rsp+78h+cy], eax; cy
0x140016919  call    cs:__imp_BitBlt
0x140016920  nop     dword ptr [rax+rax+00h]
0x140016925  mov     rcx, rsi; hdc
0x140016928  call    cs:__imp_DeleteDC
0x14001692f  nop     dword ptr [rax+rax+00h]
0x140016934  mov     rsi, [rdi+58h]
0x140016938  mov     rcx, [rdi-50h]; hWnd
0x14001693c  mov     rdx, rsi; hDC
0x14001693f  call    cs:__imp_ReleaseDC
0x140016946  nop     dword ptr [rax+rax+00h]
0x14001694b  xor     eax, eax
0x14001694d  mov     rcx, [rsp+78h+var_18]
0x140016952  xor     rcx, rsp; StackCookie
0x140016955  call    __security_check_cookie
0x14001695a  lea     r11, [rsp+78h+var_8]
0x14001695f  mov     rbx, [r11+20h]
0x140016963  mov     rsi, [r11+28h]
0x140016967  mov     rsp, r11
0x14001696a  pop     rdi
0x14001696b  retn
```
