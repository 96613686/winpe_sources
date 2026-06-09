# CViewExpiringCertificatesDialog::SetInstructionTextAndResizeControls(void)

- ea: `0x180014f18`
- end: `0x180015097`
- name: `?SetInstructionTextAndResizeControls@CViewExpiringCertificatesDialog@@AEAAXXZ`
- size: `383`
- prototype: `void __fastcall(CViewExpiringCertificatesDialog *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014aac`

## callees

- `0x180001f4c`
- `0x180014440`
- `0x18001492c`
- `0x180014d6c`
- `0x180014f18`
- `0x180015224`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014f60`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180014f60`
- `USER32!GetWindowRect` at `0x180014fb9`
- `USER32!GetWindowRect` at `0x180014fb9`
- `USER32!SendMessageA` at `0x180014fd5`
- `USER32!SendMessageA` at `0x180014fd5`
- `USER32!SetWindowTextW` at `0x180014fa3`
- `USER32!SetWindowTextW` at `0x180014fa3`
- `USER32!MoveWindow` at `0x18001502a`
- `USER32!MoveWindow` at `0x18001502a`

## pseudocode

```c
void __fastcall CViewExpiringCertificatesDialog::SetInstructionTextAndResizeControls(
        CViewExpiringCertificatesDialog *this)
{
  HWND v2; // rsi
  int v3; // eax
  int v4; // edi
  int pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  struct tagRECT Rect; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[1024]; // [rsp+50h] [rbp-B0h] BYREF

  if ( !LoadStringW(hInstance, 0xD57u, Buffer, 1024) )
  {
    pExceptionObject = -2147023082;
    throw (long *)&pExceptionObject;
  }
  v2 = *(HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, &pExceptionObject, 103);
  SetWindowTextW(v2, Buffer);
  Rect = 0;
  GetWindowRect(v2, &Rect);
  v3 = SendMessageA(v2, 0x701u, Rect.right - Rect.left, 0);
  v4 = v3 - Rect.bottom + Rect.top;
  if ( v4 > 0 )
  {
    Rect.bottom = v3 + Rect.top;
    ATL::CWindow::ScreenToClient((CViewExpiringCertificatesDialog *)((char *)this + 8), &Rect);
    MoveWindow(v2, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 1);
    CViewExpiringCertificatesDialog::ShrinkControl(this, 104, v4);
    CViewExpiringCertificatesDialog::MoveControl(this, 0x69u, v4);
    CViewExpiringCertificatesDialog::MoveControl(this, 0x6Au, v4);
    CViewExpiringCertificatesDialog::ShrinkControl(this, 101, v4);
  }
}

```

## disassembly

```asm
0x180014f18  mov     [rsp-8+arg_8], rbx
0x180014f1d  mov     [rsp-8+arg_10], rsi
0x180014f22  push    rbp
0x180014f23  push    rdi
0x180014f24  push    r14
0x180014f26  lea     rbp, [rsp-760h]
0x180014f2e  sub     rsp, 860h
0x180014f35  mov     rax, cs:__security_cookie
0x180014f3c  xor     rax, rsp
0x180014f3f  mov     [rbp+770h+var_20], rax
0x180014f46  mov     rbx, rcx
0x180014f49  lea     r8, [rsp+870h+Buffer]; lpBuffer
0x180014f4e  mov     rcx, cs:hInstance; hInstance
0x180014f55  mov     r9d, 400h; cchBufferMax
0x180014f5b  mov     edx, 0D57h; uID
0x180014f60  call    cs:__imp_LoadStringW
0x180014f66  test    eax, eax
0x180014f68  jnz     short loc_180014F84
0x180014f6a  lea     rdx, _TI1J; pThrowInfo
0x180014f71  mov     [rsp+870h+pExceptionObject], 80070716h
0x180014f79  lea     rcx, [rsp+870h+pExceptionObject]; pExceptionObject
0x180014f7e  call    _CxxThrowException_0
0x180014f84  mov     r8d, 67h ; 'g'
0x180014f8a  lea     rdx, [rsp+870h+pExceptionObject]
0x180014f8f  lea     rcx, [rbx+8]
0x180014f93  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180014f98  lea     rdx, [rsp+870h+Buffer]; lpString
0x180014f9d  mov     rsi, [rax]
0x180014fa0  mov     rcx, rsi; hWnd
0x180014fa3  call    cs:__imp_SetWindowTextW
0x180014fa9  xorps   xmm0, xmm0
0x180014fac  lea     rdx, [rsp+870h+Rect]; lpRect
0x180014fb1  mov     rcx, rsi; hWnd
0x180014fb4  movups  xmmword ptr [rsp+870h+Rect.left], xmm0
0x180014fb9  call    cs:__imp_GetWindowRect
0x180014fbf  mov     eax, [rsp+870h+Rect.right]
0x180014fc3  xor     r9d, r9d; lParam
0x180014fc6  sub     eax, [rsp+870h+Rect.left]
0x180014fca  mov     edx, 701h; Msg
0x180014fcf  movsxd  r8, eax; wParam
0x180014fd2  mov     rcx, rsi; hWnd
0x180014fd5  call    cs:__imp_SendMessageA
0x180014fdb  mov     edx, [rsp+870h+Rect.bottom]
0x180014fdf  sub     eax, edx
0x180014fe1  mov     edi, [rsp+870h+Rect.top]
0x180014fe5  add     edi, eax
0x180014fe7  test    edi, edi
0x180014fe9  jle     loc_180015070
0x180014fef  add     edx, edi
0x180014ff1  lea     rcx, [rbx+8]; this
0x180014ff5  mov     [rsp+870h+Rect.bottom], edx
0x180014ff9  lea     rdx, [rsp+870h+Rect]; struct tagRECT *
0x180014ffe  call    ?ScreenToClient@CWindow@ATL@@QEBAHPEAUtagRECT@@@Z; ATL::CWindow::ScreenToClient(tagRECT *)
0x180015003  mov     eax, [rsp+870h+Rect.bottom]
0x180015007  mov     rcx, rsi; hWnd
0x18001500a  mov     r8d, [rsp+870h+Rect.top]; Y
0x18001500f  sub     eax, r8d
0x180015012  mov     r9d, [rsp+870h+Rect.right]
0x180015017  mov     edx, [rsp+870h+Rect.left]; X
0x18001501b  sub     r9d, edx; nWidth
0x18001501e  mov     [rsp+870h+bRepaint], 1; bRepaint
0x180015026  mov     [rsp+870h+nHeight], eax; nHeight
0x18001502a  call    cs:__imp_MoveWindow
0x180015030  mov     r8d, edi; int
0x180015033  mov     edx, 68h ; 'h'; int
0x180015038  mov     rcx, rbx; this
0x18001503b  call    ?ShrinkControl@CViewExpiringCertificatesDialog@@AEAAXHH@Z; CViewExpiringCertificatesDialog::ShrinkControl(int,int)
0x180015040  mov     r8d, edi; int
0x180015043  mov     edx, 69h ; 'i'; int
0x180015048  mov     rcx, rbx; this
0x18001504b  call    ?MoveControl@CViewExpiringCertificatesDialog@@AEAAXHH@Z; CViewExpiringCertificatesDialog::MoveControl(int,int)
0x180015050  mov     r8d, edi; int
0x180015053  mov     edx, 6Ah ; 'j'; int
0x180015058  mov     rcx, rbx; this
0x18001505b  call    ?MoveControl@CViewExpiringCertificatesDialog@@AEAAXHH@Z; CViewExpiringCertificatesDialog::MoveControl(int,int)
0x180015060  mov     r8d, edi; int
0x180015063  mov     edx, 65h ; 'e'; int
0x180015068  mov     rcx, rbx; this
0x18001506b  call    ?ShrinkControl@CViewExpiringCertificatesDialog@@AEAAXHH@Z; CViewExpiringCertificatesDialog::ShrinkControl(int,int)
0x180015070  mov     rcx, [rbp+770h+var_20]
0x180015077  xor     rcx, rsp; StackCookie
0x18001507a  call    __security_check_cookie
0x18001507f  lea     r11, [rsp+870h+var_10]
0x180015087  mov     rbx, [r11+28h]
0x18001508b  mov     rsi, [r11+30h]
0x18001508f  mov     rsp, r11
0x180015092  pop     r14
0x180015094  pop     rdi
0x180015095  pop     rbp
0x180015096  retn
```
