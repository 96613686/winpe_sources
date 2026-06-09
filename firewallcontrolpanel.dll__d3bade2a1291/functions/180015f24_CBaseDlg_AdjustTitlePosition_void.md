# CBaseDlg::AdjustTitlePosition(void)

- ea: `0x180015f24`
- end: `0x1800160ca`
- name: `?AdjustTitlePosition@CBaseDlg@@IEAAXXZ`
- size: `422`
- prototype: `void __fastcall(CBaseDlg *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180016214`
- `0x1800163b4`

## callees

- `0x180011650`
- `0x180012db4`
- `0x180015cd0`
- `0x180015f24`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `USER32!GetWindowRect` at `0x180015fcc`
- `USER32!GetWindowRect` at `0x180016001`
- `USER32!GetWindowRect` at `0x180015fcc`
- `USER32!GetWindowRect` at `0x180016001`
- `USER32!GetWindowTextW` at `0x180015f9c`
- `USER32!GetWindowTextW` at `0x180015f9c`
- `USER32!MoveWindow` at `0x18001609d`
- `USER32!MoveWindow` at `0x18001609d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CBaseDlg::AdjustTitlePosition(CBaseDlg *this)
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
  Rect = 0;
  v10 = 0;
  DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v9, 1600);
  GetWindowTextW(*DlgItem, String, 260);
  if ( String[0] )
  {
    v4 = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v9, 1615);
    GetWindowRect(*v4, &Rect);
    ScreenToClientCoords(*v2, &Rect);
    v5 = Rect.top - 10;
    v6 = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v9, 1600);
    GetWindowRect(*v6, &v10);
    ScreenToClientCoords(*v2, &v10);
    v10.bottom -= v10.top;
    v10.top = 0;
    ATL::CWindow::GetDlgItem((char *)this + 8, v9, 1600);
    CWarningBaseDlg::CalculateHeightForText(this, v7, String, &v10);
    v10.top = (v5 - v10.bottom) / 2;
    v10.bottom += v10.top;
    v8 = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v9, 1600);
    MoveWindow(*v8, v10.left, v10.top, v10.right - v10.left, v10.bottom - v10.top, 1);
  }
}

```

## disassembly

```asm
0x180015f24  mov     [rsp-8+arg_8], rbx
0x180015f29  mov     [rsp-8+arg_10], rsi
0x180015f2e  push    rbp
0x180015f2f  push    rdi
0x180015f30  push    r15
0x180015f32  lea     rbp, [rsp-180h]
0x180015f3a  sub     rsp, 280h
0x180015f41  mov     rax, cs:__security_cookie
0x180015f48  xor     rax, rsp
0x180015f4b  mov     [rbp+190h+var_20], rax
0x180015f52  mov     rsi, rcx
0x180015f55  xor     edx, edx; Val
0x180015f57  lea     rcx, [rsp+290h+String]; void *
0x180015f5c  mov     r8d, 208h; Size
0x180015f62  call    memset_0
0x180015f67  xorps   xmm0, xmm0
0x180015f6a  lea     rdi, [rsi+8]
0x180015f6e  xorps   xmm1, xmm1
0x180015f71  lea     rdx, [rsp+290h+var_260]
0x180015f76  mov     rcx, rdi
0x180015f79  mov     r8d, 640h
0x180015f7f  movups  xmmword ptr [rsp+290h+Rect.left], xmm0
0x180015f84  movups  xmmword ptr [rsp+290h+var_258.left], xmm1
0x180015f89  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180015f8e  mov     r8d, 104h; nMaxCount
0x180015f94  lea     rdx, [rsp+290h+String]; lpString
0x180015f99  mov     rcx, [rax]; hWnd
0x180015f9c  call    cs:__imp_GetWindowTextW
0x180015fa2  xor     r15d, r15d
0x180015fa5  cmp     [rsp+290h+String], r15w
0x180015fab  jz      loc_1800160A3
0x180015fb1  mov     r8d, 64Fh
0x180015fb7  lea     rdx, [rsp+290h+var_260]
0x180015fbc  mov     rcx, rdi
0x180015fbf  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180015fc4  lea     rdx, [rsp+290h+Rect]; lpRect
0x180015fc9  mov     rcx, [rax]; hWnd
0x180015fcc  call    cs:__imp_GetWindowRect
0x180015fd2  mov     rcx, [rdi]; hWndTo
0x180015fd5  lea     rdx, [rsp+290h+Rect]; struct tagRECT *
0x180015fda  call    ?ScreenToClientCoords@@YAXPEAUHWND__@@PEAUtagRECT@@@Z; ScreenToClientCoords(HWND__ *,tagRECT *)
0x180015fdf  mov     ebx, [rsp+290h+Rect.top]
0x180015fe3  lea     rdx, [rsp+290h+var_260]
0x180015fe8  mov     r8d, 640h
0x180015fee  mov     rcx, rdi
0x180015ff1  add     ebx, 0FFFFFFF6h
0x180015ff4  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180015ff9  lea     rdx, [rsp+290h+var_258]; lpRect
0x180015ffe  mov     rcx, [rax]; hWnd
0x180016001  call    cs:__imp_GetWindowRect
0x180016007  mov     rcx, [rdi]; hWndTo
0x18001600a  lea     rdx, [rsp+290h+var_258]; struct tagRECT *
0x18001600f  call    ?ScreenToClientCoords@@YAXPEAUHWND__@@PEAUtagRECT@@@Z; ScreenToClientCoords(HWND__ *,tagRECT *)
0x180016014  mov     edx, [rsp+290h+var_258.top]
0x180016018  mov     r8d, 640h
0x18001601e  sub     [rsp+290h+var_258.bottom], edx
0x180016022  mov     rcx, rdi
0x180016025  lea     rdx, [rsp+290h+var_260]
0x18001602a  mov     [rsp+290h+var_258.top], r15d
0x18001602f  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180016034  lea     r9, [rsp+290h+var_258]; struct tagRECT *
0x180016039  mov     rcx, rsi; this
0x18001603c  lea     r8, [rsp+290h+String]; unsigned __int16 *
0x180016041  call    ?CalculateHeightForText@CWarningBaseDlg@@IEAAXPEAUHWND__@@PEBGAEAUtagRECT@@@Z; CWarningBaseDlg::CalculateHeightForText(HWND__ *,ushort const *,tagRECT &)
0x180016046  mov     r9d, [rsp+290h+var_258.bottom]
0x18001604b  lea     ecx, [r15+2]
0x18001604f  sub     ebx, r9d
0x180016052  mov     r8d, 640h
0x180016058  mov     eax, ebx
0x18001605a  cdq
0x18001605b  idiv    ecx
0x18001605d  lea     rdx, [rsp+290h+var_260]
0x180016062  mov     rcx, rdi
0x180016065  add     r9d, eax
0x180016068  mov     [rsp+290h+var_258.top], eax
0x18001606c  mov     [rsp+290h+var_258.bottom], r9d
0x180016071  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180016076  mov     ecx, [rsp+290h+var_258.bottom]
0x18001607a  mov     r8d, [rsp+290h+var_258.top]; Y
0x18001607f  sub     ecx, r8d
0x180016082  mov     r9d, [rsp+290h+var_258.right]
0x180016087  mov     edx, [rsp+290h+var_258.left]; X
0x18001608b  sub     r9d, edx; nWidth
0x18001608e  mov     [rsp+290h+bRepaint], 1; bRepaint
0x180016096  mov     [rsp+290h+nHeight], ecx; nHeight
0x18001609a  mov     rcx, [rax]; hWnd
0x18001609d  call    cs:__imp_MoveWindow
0x1800160a3  mov     rcx, [rbp+190h+var_20]
0x1800160aa  xor     rcx, rsp; StackCookie
0x1800160ad  call    __security_check_cookie
0x1800160b2  lea     r11, [rsp+290h+var_10]
0x1800160ba  mov     rbx, [r11+28h]
0x1800160be  mov     rsi, [r11+30h]
0x1800160c2  mov     rsp, r11
0x1800160c5  pop     r15
0x1800160c7  pop     rdi
0x1800160c8  pop     rbp
0x1800160c9  retn
```
