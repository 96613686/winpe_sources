# CViewExpiringCertificatesDialog::MoveControl(int,int)

- ea: `0x18001492c`
- end: `0x1800149d6`
- name: `?MoveControl@CViewExpiringCertificatesDialog@@AEAAXHH@Z`
- size: `170`
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

- `USER32!GetWindowRect` at `0x18001496e`
- `USER32!GetWindowRect` at `0x18001496e`
- `USER32!MoveWindow` at `0x1800149b8`
- `USER32!MoveWindow` at `0x1800149b8`

## pseudocode

```c
void __fastcall CViewExpiringCertificatesDialog::MoveControl(
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
  MoveWindow(hWnd, Rect.left, a3 + Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 1);
}

```

## disassembly

```asm
0x18001492c  mov     [rsp+arg_18], rbx
0x180014931  push    rdi
0x180014932  sub     rsp, 50h
0x180014936  mov     rax, cs:__security_cookie
0x18001493d  xor     rax, rsp
0x180014940  mov     [rsp+58h+var_10], rax
0x180014945  mov     edi, r8d
0x180014948  lea     rbx, [rcx+8]
0x18001494c  mov     r8d, edx
0x18001494f  xorps   xmm0, xmm0
0x180014952  lea     rdx, [rsp+58h+hWnd]
0x180014957  mov     rcx, rbx
0x18001495a  movups  xmmword ptr [rsp+58h+Rect.left], xmm0
0x18001495f  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180014964  mov     rcx, [rsp+58h+hWnd]; hWnd
0x180014969  lea     rdx, [rsp+58h+Rect]; lpRect
0x18001496e  call    cs:__imp_GetWindowRect
0x180014974  lea     rdx, [rsp+58h+Rect]; struct tagRECT *
0x180014979  mov     rcx, rbx; this
0x18001497c  call    ?ScreenToClient@CWindow@ATL@@QEBAHPEAUtagRECT@@@Z; ATL::CWindow::ScreenToClient(tagRECT *)
0x180014981  mov     eax, [rsp+58h+Rect.bottom]
0x180014985  mov     r8d, [rsp+58h+Rect.top]
0x18001498a  add     eax, edi
0x18001498c  mov     r9d, [rsp+58h+Rect.right]
0x180014991  add     r8d, edi; Y
0x180014994  mov     edx, [rsp+58h+Rect.left]; X
0x180014998  sub     r9d, edx; nWidth
0x18001499b  mov     rcx, [rsp+58h+hWnd]; hWnd
0x1800149a0  mov     [rsp+58h+Rect.bottom], eax
0x1800149a4  sub     eax, r8d
0x1800149a7  mov     [rsp+58h+bRepaint], 1; bRepaint
0x1800149af  mov     [rsp+58h+nHeight], eax; nHeight
0x1800149b3  mov     [rsp+58h+Rect.top], r8d
0x1800149b8  call    cs:__imp_MoveWindow
0x1800149be  mov     rcx, [rsp+58h+var_10]
0x1800149c3  xor     rcx, rsp; StackCookie
0x1800149c6  call    __security_check_cookie
0x1800149cb  mov     rbx, [rsp+58h+arg_18]
0x1800149d0  add     rsp, 50h
0x1800149d4  pop     rdi
0x1800149d5  retn
```
