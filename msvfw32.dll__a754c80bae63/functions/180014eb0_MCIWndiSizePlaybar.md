# MCIWndiSizePlaybar

- ea: `0x180014eb0`
- end: `0x180014fb6`
- name: `MCIWndiSizePlaybar`
- size: `262`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180010cc0`
- `0x180012da8`
- `0x180014cc8`

## callees

- `0x1800014b0`
- `0x180014eb0`

## import_xrefs

- `USER32!SetWindowPos` at `0x180014f1d`
- `USER32!SetWindowPos` at `0x180014f91`
- `USER32!SetWindowPos` at `0x180014f1d`
- `USER32!SetWindowPos` at `0x180014f91`
- `USER32!SendMessageW` at `0x180014f48`
- `USER32!SendMessageW` at `0x180014f62`
- `USER32!SendMessageW` at `0x180014f48`
- `USER32!SendMessageW` at `0x180014f62`
- `USER32!ShowWindow` at `0x180014f2f`
- `USER32!ShowWindow` at `0x180014f2f`
- `USER32!GetClientRect` at `0x180014eeb`
- `USER32!GetClientRect` at `0x180014eeb`

## pseudocode

```c
void __fastcall MCIWndiSizePlaybar(__int64 a1)
{
  bool v1; // zf
  LONG bottom; // ebx
  LONG right; // edi
  int v5; // eax
  struct tagRECT Rect; // [rsp+40h] [rbp-28h] BYREF

  v1 = (*(_BYTE *)(a1 + 32) & 2) == 0;
  Rect = 0;
  if ( v1 )
  {
    GetClientRect(*(HWND *)a1, &Rect);
    bottom = Rect.bottom;
    right = Rect.right;
    SetWindowPos(*(HWND *)(a1 + 192), 0, 0, Rect.bottom - 26, Rect.right, 26, 4u);
    ShowWindow(*(HWND *)(a1 + 192), 5);
    v5 = SendMessageW(*(HWND *)(a1 + 192), 0x419u, 0x6Du, 0);
    SendMessageW(*(HWND *)(a1 + 192), 0x41Du, v5, (LPARAM)&Rect);
    SetWindowPos(*(HWND *)(a1 + 200), 0, Rect.right, bottom - 24, right - Rect.right, 26, 0);
  }
}

```

## disassembly

```asm
0x180014eb0  mov     [rsp+arg_8], rbx
0x180014eb5  mov     [rsp+arg_10], rsi
0x180014eba  push    rdi
0x180014ebb  sub     rsp, 60h
0x180014ebf  mov     rax, cs:__security_cookie
0x180014ec6  xor     rax, rsp
0x180014ec9  mov     [rsp+68h+var_18], rax
0x180014ece  test    byte ptr [rcx+20h], 2
0x180014ed2  xorps   xmm0, xmm0
0x180014ed5  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x180014eda  mov     rsi, rcx
0x180014edd  jnz     loc_180014F97
0x180014ee3  mov     rcx, [rcx]; hWnd
0x180014ee6  lea     rdx, [rsp+68h+Rect]; lpRect
0x180014eeb  call    cs:__imp_GetClientRect
0x180014ef1  mov     ebx, [rsp+68h+Rect.bottom]
0x180014ef5  xor     r8d, r8d; X
0x180014ef8  mov     edi, [rsp+68h+Rect.right]
0x180014efc  xor     edx, edx; hWndInsertAfter
0x180014efe  mov     rcx, [rsi+0C0h]; hWnd
0x180014f05  mov     [rsp+68h+uFlags], 4; uFlags
0x180014f0d  lea     r9d, [rbx-1Ah]; Y
0x180014f11  mov     [rsp+68h+cy], 1Ah; cy
0x180014f19  mov     [rsp+68h+var_48], edi; cx
0x180014f1d  call    cs:__imp_SetWindowPos
0x180014f23  mov     rcx, [rsi+0C0h]; hWnd
0x180014f2a  mov     edx, 5; nCmdShow
0x180014f2f  call    cs:__imp_ShowWindow
0x180014f35  mov     rcx, [rsi+0C0h]; hWnd
0x180014f3c  xor     r9d, r9d; lParam
0x180014f3f  mov     edx, 419h; Msg
0x180014f44  lea     r8d, [r9+6Dh]; wParam
0x180014f48  call    cs:__imp_SendMessageW
0x180014f4e  mov     rcx, [rsi+0C0h]; hWnd
0x180014f55  lea     r9, [rsp+68h+Rect]; lParam
0x180014f5a  movsxd  r8, eax; wParam
0x180014f5d  mov     edx, 41Dh; Msg
0x180014f62  call    cs:__imp_SendMessageW
0x180014f68  mov     r8d, [rsp+68h+Rect.right]; X
0x180014f6d  lea     r9d, [rbx-18h]; Y
0x180014f71  mov     rcx, [rsi+0C8h]; hWnd
0x180014f78  sub     edi, r8d
0x180014f7b  mov     [rsp+68h+uFlags], 0; uFlags
0x180014f83  xor     edx, edx; hWndInsertAfter
0x180014f85  mov     [rsp+68h+cy], 1Ah; cy
0x180014f8d  mov     [rsp+68h+var_48], edi; cx
0x180014f91  call    cs:__imp_SetWindowPos
0x180014f97  mov     rcx, [rsp+68h+var_18]
0x180014f9c  xor     rcx, rsp; StackCookie
0x180014f9f  call    __security_check_cookie
0x180014fa4  lea     r11, [rsp+68h+var_8]
0x180014fa9  mov     rbx, [r11+18h]
0x180014fad  mov     rsi, [r11+20h]
0x180014fb1  mov     rsp, r11
0x180014fb4  pop     rdi
0x180014fb5  retn
```
