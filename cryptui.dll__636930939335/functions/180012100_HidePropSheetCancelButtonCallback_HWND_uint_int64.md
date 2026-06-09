# HidePropSheetCancelButtonCallback(HWND__ *,uint,__int64)

- ea: `0x180012100`
- end: `0x1800121c3`
- name: `?HidePropSheetCancelButtonCallback@@YAHPEAUHWND__@@I_J@Z`
- size: `195`
- prototype: `__int64 __fastcall(HWND hWndTo, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180012100`
- `0x18003e5c0`

## import_xrefs

- `USER32!GetWindowRect` at `0x180012150`
- `USER32!GetWindowRect` at `0x180012150`
- `USER32!MapWindowPoints` at `0x180012166`
- `USER32!MapWindowPoints` at `0x180012166`
- `USER32!ShowWindow` at `0x180012171`
- `USER32!ShowWindow` at `0x180012171`
- `USER32!GetDlgItem` at `0x18001212e`
- `USER32!GetDlgItem` at `0x18001213f`
- `USER32!GetDlgItem` at `0x18001212e`
- `USER32!GetDlgItem` at `0x18001213f`
- `USER32!MoveWindow` at `0x18001219e`
- `USER32!MoveWindow` at `0x18001219e`

## pseudocode

```c
__int64 __fastcall HidePropSheetCancelButtonCallback(HWND hWndTo, int a2)
{
  HWND DlgItem; // rdi
  HWND v4; // rbx
  struct tagRECT Rect; // [rsp+30h] [rbp-28h] BYREF

  Rect = 0;
  if ( a2 == 1 )
  {
    DlgItem = GetDlgItem(hWndTo, 1);
    v4 = GetDlgItem(hWndTo, 2);
    GetWindowRect(v4, &Rect);
    MapWindowPoints(0, hWndTo, (LPPOINT)&Rect, 2u);
    ShowWindow(v4, 0);
    MoveWindow(DlgItem, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180012100  mov     [rsp+arg_8], rbx
0x180012105  mov     [rsp+arg_10], rsi
0x18001210a  push    rdi
0x18001210b  sub     rsp, 50h
0x18001210f  mov     rax, cs:__security_cookie
0x180012116  xor     rax, rsp
0x180012119  mov     [rsp+58h+var_18], rax
0x18001211e  xorps   xmm0, xmm0
0x180012121  mov     rsi, rcx
0x180012124  movups  xmmword ptr [rsp+58h+Rect.left], xmm0
0x180012129  cmp     edx, 1
0x18001212c  jnz     short loc_1800121A4
0x18001212e  call    cs:__imp_GetDlgItem
0x180012134  mov     edx, 2; nIDDlgItem
0x180012139  mov     rcx, rsi; hDlg
0x18001213c  mov     rdi, rax
0x18001213f  call    cs:__imp_GetDlgItem
0x180012145  mov     rcx, rax; hWnd
0x180012148  lea     rdx, [rsp+58h+Rect]; lpRect
0x18001214d  mov     rbx, rax
0x180012150  call    cs:__imp_GetWindowRect
0x180012156  mov     r9d, 2; cPoints
0x18001215c  lea     r8, [rsp+58h+Rect]; lpPoints
0x180012161  mov     rdx, rsi; hWndTo
0x180012164  xor     ecx, ecx; hWndFrom
0x180012166  call    cs:__imp_MapWindowPoints
0x18001216c  xor     edx, edx; nCmdShow
0x18001216e  mov     rcx, rbx; hWnd
0x180012171  call    cs:__imp_ShowWindow
0x180012177  mov     eax, [rsp+58h+Rect.bottom]
0x18001217b  mov     rcx, rdi; hWnd
0x18001217e  mov     r8d, [rsp+58h+Rect.top]; Y
0x180012183  sub     eax, r8d
0x180012186  mov     r9d, [rsp+58h+Rect.right]
0x18001218b  mov     edx, [rsp+58h+Rect.left]; X
0x18001218f  sub     r9d, edx; nWidth
0x180012192  mov     [rsp+58h+bRepaint], 0; bRepaint
0x18001219a  mov     [rsp+58h+nHeight], eax; nHeight
0x18001219e  call    cs:__imp_MoveWindow
0x1800121a4  xor     eax, eax
0x1800121a6  mov     rcx, [rsp+58h+var_18]
0x1800121ab  xor     rcx, rsp; StackCookie
0x1800121ae  call    __security_check_cookie
0x1800121b3  mov     rbx, [rsp+58h+arg_8]
0x1800121b8  mov     rsi, [rsp+58h+arg_10]
0x1800121bd  add     rsp, 50h
0x1800121c1  pop     rdi
0x1800121c2  retn
```
