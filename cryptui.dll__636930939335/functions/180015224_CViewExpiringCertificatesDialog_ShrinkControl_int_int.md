# CViewExpiringCertificatesDialog::ShrinkControl(int,int)

- ea: `0x180015224`
- end: `0x1800152c8`
- name: `?ShrinkControl@CViewExpiringCertificatesDialog@@AEAAXHH@Z`
- size: `164`
- prototype: `void __fastcall(CViewExpiringCertificatesDialog *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180014f18`

## callees

- `0x180014440`
- `0x180014d6c`
- `0x18003e5c0`

## import_xrefs

- `USER32!GetWindowRect` at `0x180015266`
- `USER32!GetWindowRect` at `0x180015266`
- `USER32!MoveWindow` at `0x1800152aa`
- `USER32!MoveWindow` at `0x1800152aa`

## pseudocode

```c
void __fastcall CViewExpiringCertificatesDialog::ShrinkControl(
        CViewExpiringCertificatesDialog *this,
        unsigned int a2,
        int a3)
{
  ATL::CWindow *v4; // rbx
  HWND hWnd; // [rsp+30h] [rbp-28h] BYREF
  struct tagRECT Rect; // [rsp+38h] [rbp-20h] BYREF

  v4 = (CViewExpiringCertificatesDialog *)((char *)this + 8);
  Rect = 0;
  ATL::CWindow::GetDlgItem((char *)this + 8, &hWnd, a2);
  GetWindowRect(hWnd, &Rect);
  ATL::CWindow::ScreenToClient(v4, &Rect);
  MoveWindow(hWnd, Rect.left, a3 + Rect.top, Rect.right - Rect.left, Rect.bottom - (a3 + Rect.top), 1);
}

```

## disassembly

```asm
0x180015224  mov     [rsp+arg_18], rbx
0x180015229  push    rdi
0x18001522a  sub     rsp, 50h
0x18001522e  mov     rax, cs:__security_cookie
0x180015235  xor     rax, rsp
0x180015238  mov     [rsp+58h+var_10], rax
0x18001523d  mov     edi, r8d
0x180015240  lea     rbx, [rcx+8]
0x180015244  mov     r8d, edx
0x180015247  xorps   xmm0, xmm0
0x18001524a  lea     rdx, [rsp+58h+hWnd]
0x18001524f  mov     rcx, rbx
0x180015252  movups  xmmword ptr [rsp+58h+Rect.left], xmm0
0x180015257  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18001525c  mov     rcx, [rsp+58h+hWnd]; hWnd
0x180015261  lea     rdx, [rsp+58h+Rect]; lpRect
0x180015266  call    cs:__imp_GetWindowRect
0x18001526c  lea     rdx, [rsp+58h+Rect]; struct tagRECT *
0x180015271  mov     rcx, rbx; this
0x180015274  call    ?ScreenToClient@CWindow@ATL@@QEBAHPEAUtagRECT@@@Z; ATL::CWindow::ScreenToClient(tagRECT *)
0x180015279  mov     r8d, [rsp+58h+Rect.top]
0x18001527e  mov     eax, [rsp+58h+Rect.bottom]
0x180015282  add     r8d, edi; Y
0x180015285  mov     r9d, [rsp+58h+Rect.right]
0x18001528a  sub     eax, r8d
0x18001528d  mov     edx, [rsp+58h+Rect.left]; X
0x180015291  sub     r9d, edx; nWidth
0x180015294  mov     rcx, [rsp+58h+hWnd]; hWnd
0x180015299  mov     [rsp+58h+bRepaint], 1; bRepaint
0x1800152a1  mov     [rsp+58h+nHeight], eax; nHeight
0x1800152a5  mov     [rsp+58h+Rect.top], r8d
0x1800152aa  call    cs:__imp_MoveWindow
0x1800152b0  mov     rcx, [rsp+58h+var_10]
0x1800152b5  xor     rcx, rsp; StackCookie
0x1800152b8  call    __security_check_cookie
0x1800152bd  mov     rbx, [rsp+58h+arg_18]
0x1800152c2  add     rsp, 50h
0x1800152c6  pop     rdi
0x1800152c7  retn
```
