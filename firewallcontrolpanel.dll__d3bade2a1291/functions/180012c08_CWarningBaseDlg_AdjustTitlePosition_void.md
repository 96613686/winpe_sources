# CWarningBaseDlg::AdjustTitlePosition(void)

- ea: `0x180012c08`
- end: `0x180012dae`
- name: `?AdjustTitlePosition@CWarningBaseDlg@@IEAAXXZ`
- size: `422`
- prototype: `void __fastcall(CWarningBaseDlg *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800130d0`
- `0x180013574`

## callees

- `0x180011650`
- `0x180012c08`
- `0x180012db4`
- `0x180015cd0`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `USER32!GetWindowRect` at `0x180012ca8`
- `USER32!GetWindowRect` at `0x180012ce5`
- `USER32!GetWindowRect` at `0x180012ca8`
- `USER32!GetWindowRect` at `0x180012ce5`
- `USER32!GetWindowTextW` at `0x180012c70`
- `USER32!GetWindowTextW` at `0x180012c70`
- `USER32!MoveWindow` at `0x180012d81`
- `USER32!MoveWindow` at `0x180012d81`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWarningBaseDlg::AdjustTitlePosition(CWarningBaseDlg *this)
{
  HWND *v2; // rdi
  HWND *DlgItem; // rax
  HWND *v4; // rax
  int v5; // ebx
  HWND *v6; // rax
  HWND v7; // rdx
  HWND *v8; // rax
  _BYTE v9[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct tagRECT v10; // [rsp+38h] [rbp-C8h] BYREF
  struct tagRECT Rect; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR String[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(String, 0, 0x208u);
  v2 = (HWND *)((char *)this + 8);
  DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v9, 12201);
  GetWindowTextW(*DlgItem, String, 260);
  if ( String[0] )
  {
    Rect = 0;
    v4 = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v9, 12202);
    GetWindowRect(*v4, &Rect);
    ScreenToClientCoords(*v2, &Rect);
    v5 = Rect.top - 10;
    v10 = 0;
    v6 = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v9, 12201);
    GetWindowRect(*v6, &v10);
    ScreenToClientCoords(*v2, &v10);
    v10.bottom -= v10.top;
    v10.top = 0;
    ATL::CWindow::GetDlgItem((char *)this + 8, v9, 12201);
    CWarningBaseDlg::CalculateHeightForText(this, v7, String, &v10);
    v10.top = (v5 - v10.bottom) / 2;
    v10.bottom += v10.top;
    v8 = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v9, 12201);
    MoveWindow(*v8, v10.left, v10.top, v10.right - v10.left, v10.bottom - v10.top, 1);
  }
}

```

## disassembly

```asm
0x180012c08  mov     [rsp-8+arg_8], rbx
0x180012c0d  mov     [rsp-8+arg_10], rsi
0x180012c12  push    rbp
0x180012c13  push    rdi
0x180012c14  push    r15
0x180012c16  lea     rbp, [rsp-180h]
0x180012c1e  sub     rsp, 280h
0x180012c25  mov     rax, cs:__security_cookie
0x180012c2c  xor     rax, rsp
0x180012c2f  mov     [rbp+190h+var_20], rax
0x180012c36  mov     rsi, rcx
0x180012c39  xor     edx, edx; Val
0x180012c3b  lea     rcx, [rsp+290h+String]; void *
0x180012c40  mov     r8d, 208h; Size
0x180012c46  call    memset_0
0x180012c4b  lea     rdi, [rsi+8]
0x180012c4f  mov     r8d, 2FA9h
0x180012c55  mov     rcx, rdi
0x180012c58  lea     rdx, [rsp+290h+var_260]
0x180012c5d  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180012c62  mov     r8d, 104h; nMaxCount
0x180012c68  lea     rdx, [rsp+290h+String]; lpString
0x180012c6d  mov     rcx, [rax]; hWnd
0x180012c70  call    cs:__imp_GetWindowTextW
0x180012c76  xor     r15d, r15d
0x180012c79  cmp     [rsp+290h+String], r15w
0x180012c7f  jz      loc_180012D87
0x180012c85  xorps   xmm0, xmm0
0x180012c88  lea     rdx, [rsp+290h+var_260]
0x180012c8d  mov     r8d, 2FAAh
0x180012c93  mov     rcx, rdi
0x180012c96  movups  xmmword ptr [rsp+290h+Rect.left], xmm0
0x180012c9b  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180012ca0  lea     rdx, [rsp+290h+Rect]; lpRect
0x180012ca5  mov     rcx, [rax]; hWnd
0x180012ca8  call    cs:__imp_GetWindowRect
0x180012cae  mov     rcx, [rdi]; hWndTo
0x180012cb1  lea     rdx, [rsp+290h+Rect]; struct tagRECT *
0x180012cb6  call    ?ScreenToClientCoords@@YAXPEAUHWND__@@PEAUtagRECT@@@Z; ScreenToClientCoords(HWND__ *,tagRECT *)
0x180012cbb  mov     ebx, [rsp+290h+Rect.top]
0x180012cbf  lea     rdx, [rsp+290h+var_260]
0x180012cc4  xorps   xmm0, xmm0
0x180012cc7  mov     r8d, 2FA9h
0x180012ccd  mov     rcx, rdi
0x180012cd0  add     ebx, 0FFFFFFF6h
0x180012cd3  movups  xmmword ptr [rsp+290h+var_258.left], xmm0
0x180012cd8  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180012cdd  lea     rdx, [rsp+290h+var_258]; lpRect
0x180012ce2  mov     rcx, [rax]; hWnd
0x180012ce5  call    cs:__imp_GetWindowRect
0x180012ceb  mov     rcx, [rdi]; hWndTo
0x180012cee  lea     rdx, [rsp+290h+var_258]; struct tagRECT *
0x180012cf3  call    ?ScreenToClientCoords@@YAXPEAUHWND__@@PEAUtagRECT@@@Z; ScreenToClientCoords(HWND__ *,tagRECT *)
0x180012cf8  mov     edx, [rsp+290h+var_258.top]
0x180012cfc  mov     r8d, 2FA9h
0x180012d02  sub     [rsp+290h+var_258.bottom], edx
0x180012d06  mov     rcx, rdi
0x180012d09  lea     rdx, [rsp+290h+var_260]
0x180012d0e  mov     [rsp+290h+var_258.top], r15d
0x180012d13  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180012d18  lea     r9, [rsp+290h+var_258]; struct tagRECT *
0x180012d1d  mov     rcx, rsi; this
0x180012d20  lea     r8, [rsp+290h+String]; unsigned __int16 *
0x180012d25  call    ?CalculateHeightForText@CWarningBaseDlg@@IEAAXPEAUHWND__@@PEBGAEAUtagRECT@@@Z; CWarningBaseDlg::CalculateHeightForText(HWND__ *,ushort const *,tagRECT &)
0x180012d2a  mov     r9d, [rsp+290h+var_258.bottom]
0x180012d2f  lea     ecx, [r15+2]
0x180012d33  sub     ebx, r9d
0x180012d36  mov     r8d, 2FA9h
0x180012d3c  mov     eax, ebx
0x180012d3e  cdq
0x180012d3f  idiv    ecx
0x180012d41  lea     rdx, [rsp+290h+var_260]
0x180012d46  mov     rcx, rdi
0x180012d49  add     r9d, eax
0x180012d4c  mov     [rsp+290h+var_258.top], eax
0x180012d50  mov     [rsp+290h+var_258.bottom], r9d
0x180012d55  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180012d5a  mov     ecx, [rsp+290h+var_258.bottom]
0x180012d5e  mov     r8d, [rsp+290h+var_258.top]; Y
0x180012d63  sub     ecx, r8d
0x180012d66  mov     r9d, [rsp+290h+var_258.right]
0x180012d6b  mov     edx, [rsp+290h+var_258.left]; X
0x180012d6f  sub     r9d, edx; nWidth
0x180012d72  mov     [rsp+290h+bRepaint], 1; bRepaint
0x180012d7a  mov     [rsp+290h+nHeight], ecx; nHeight
0x180012d7e  mov     rcx, [rax]; hWnd
0x180012d81  call    cs:__imp_MoveWindow
0x180012d87  mov     rcx, [rbp+190h+var_20]
0x180012d8e  xor     rcx, rsp; StackCookie
0x180012d91  call    __security_check_cookie
0x180012d96  lea     r11, [rsp+290h+var_10]
0x180012d9e  mov     rbx, [r11+28h]
0x180012da2  mov     rsi, [r11+30h]
0x180012da6  mov     rsp, r11
0x180012da9  pop     r15
0x180012dab  pop     rdi
0x180012dac  pop     rbp
0x180012dad  retn
```
