# CenterPopupWindow(HWND__ *,HWND__ *)

- ea: `0x180029620`
- end: `0x180029765`
- name: `?CenterPopupWindow@@YAXPEAUHWND__@@0@Z`
- size: `325`
- prototype: `void __fastcall(HWND hWnd, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025800`

## callees

- `0x180029620`
- `0x180031070`

## import_xrefs

- `USER32!GetParent` at `0x180029671`
- `USER32!GetParent` at `0x180029671`
- `USER32!GetDesktopWindow` at `0x18002967f`
- `USER32!GetDesktopWindow` at `0x18002967f`
- `USER32!GetSystemMetrics` at `0x180029654`
- `USER32!GetSystemMetrics` at `0x180029661`
- `USER32!GetSystemMetrics` at `0x180029654`
- `USER32!GetSystemMetrics` at `0x180029661`
- `USER32!GetWindowRect` at `0x18002969d`
- `USER32!GetWindowRect` at `0x1800296aa`
- `USER32!GetWindowRect` at `0x18002969d`
- `USER32!GetWindowRect` at `0x1800296aa`
- `USER32!MoveWindow` at `0x18002973e`
- `USER32!MoveWindow` at `0x18002973e`

## pseudocode

```c
void __fastcall CenterPopupWindow(HWND hWnd, HWND Parent)
{
  int SystemMetrics; // edi
  int v5; // ebx
  int v6; // r9d
  int nHeight; // r8d
  int v8; // r11d
  int v9; // r10d
  int v10; // eax
  LONG v11; // edi
  int v12; // eax
  LONG v13; // ebx
  struct tagRECT Rect; // [rsp+30h] [rbp-30h] BYREF
  struct tagRECT v15; // [rsp+40h] [rbp-20h] BYREF

  if ( hWnd )
  {
    SystemMetrics = GetSystemMetrics(0);
    v5 = GetSystemMetrics(1);
    if ( !Parent )
    {
      Parent = GetParent(hWnd);
      if ( !Parent )
        Parent = GetDesktopWindow();
    }
    Rect = 0;
    v15 = 0;
    GetWindowRect(hWnd, &Rect);
    GetWindowRect(Parent, &v15);
    v6 = Rect.right - Rect.left;
    nHeight = Rect.bottom - Rect.top;
    v8 = (v15.right - v15.left) / 2 + v15.left;
    v9 = (v15.bottom - v15.top) / 2 + v15.top;
    v10 = (Rect.right - Rect.left) / 2;
    if ( v10 + v8 <= SystemMetrics )
    {
      v11 = v8 - v10;
      if ( v8 - v10 < 0 )
        v11 = 0;
    }
    else
    {
      v11 = SystemMetrics - v6;
    }
    Rect.left = v11;
    v12 = nHeight / 2;
    if ( nHeight / 2 + v9 <= v5 )
    {
      v13 = v9 - v12;
      if ( v9 - v12 < 0 )
        v13 = 0;
    }
    else
    {
      v13 = v5 - nHeight;
    }
    Rect.top = v13;
    MoveWindow(hWnd, v11, v13, v6, nHeight, 1);
  }
}

```

## disassembly

```asm
0x180029620  test    rcx, rcx
0x180029623  jz      locret_180029764
0x180029629  mov     [rsp-18h+arg_10], rbx
0x18002962e  mov     [rsp-18h+arg_18], rsi
0x180029633  push    rbp
0x180029634  push    rdi
0x180029635  push    r14
0x180029637  mov     rbp, rsp
0x18002963a  sub     rsp, 60h
0x18002963e  mov     rax, cs:__security_cookie
0x180029645  xor     rax, rsp
0x180029648  mov     [rbp+var_10], rax
0x18002964c  mov     r14, rcx
0x18002964f  mov     rsi, rdx
0x180029652  xor     ecx, ecx; nIndex
0x180029654  call    cs:__imp_GetSystemMetrics
0x18002965a  mov     ecx, 1; nIndex
0x18002965f  mov     edi, eax
0x180029661  call    cs:__imp_GetSystemMetrics
0x180029667  mov     ebx, eax
0x180029669  test    rsi, rsi
0x18002966c  jnz     short loc_180029688
0x18002966e  mov     rcx, r14; hWnd
0x180029671  call    cs:__imp_GetParent
0x180029677  mov     rsi, rax
0x18002967a  test    rax, rax
0x18002967d  jnz     short loc_180029688
0x18002967f  call    cs:__imp_GetDesktopWindow
0x180029685  mov     rsi, rax
0x180029688  xorps   xmm0, xmm0
0x18002968b  lea     rdx, [rbp+Rect]; lpRect
0x18002968f  xorps   xmm1, xmm1
0x180029692  mov     rcx, r14; hWnd
0x180029695  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180029699  movups  xmmword ptr [rbp+var_20.left], xmm1
0x18002969d  call    cs:__imp_GetWindowRect
0x1800296a3  lea     rdx, [rbp+var_20]; lpRect
0x1800296a7  mov     rcx, rsi; hWnd
0x1800296aa  call    cs:__imp_GetWindowRect
0x1800296b0  mov     ecx, [rbp+var_20.left]
0x1800296b3  mov     esi, 2
0x1800296b8  mov     eax, [rbp+var_20.right]
0x1800296bb  mov     r9d, [rbp+Rect.right]
0x1800296bf  sub     eax, ecx
0x1800296c1  sub     r9d, [rbp+Rect.left]; nWidth
0x1800296c5  cdq
0x1800296c6  mov     r8d, [rbp+Rect.bottom]
0x1800296ca  sub     r8d, [rbp+Rect.top]
0x1800296ce  idiv    esi
0x1800296d0  lea     r11d, [rax+rcx]
0x1800296d4  mov     ecx, [rbp+var_20.top]
0x1800296d7  mov     eax, [rbp+var_20.bottom]
0x1800296da  sub     eax, ecx
0x1800296dc  cdq
0x1800296dd  idiv    esi
0x1800296df  lea     r10d, [rax+rcx]
0x1800296e3  mov     eax, r9d
0x1800296e6  cdq
0x1800296e7  idiv    esi
0x1800296e9  lea     ecx, [rax+r11]
0x1800296ed  cmp     ecx, edi
0x1800296ef  jle     short loc_1800296F6
0x1800296f1  sub     edi, r9d
0x1800296f4  jmp     short loc_180029703
0x1800296f6  mov     edi, r11d
0x1800296f9  sub     edi, eax
0x1800296fb  mov     eax, 0
0x180029700  cmovs   edi, eax
0x180029703  mov     eax, r8d
0x180029706  mov     [rbp+Rect.left], edi
0x180029709  cdq
0x18002970a  idiv    esi
0x18002970c  lea     ecx, [rax+r10]
0x180029710  cmp     ecx, ebx
0x180029712  jle     short loc_180029719
0x180029714  sub     ebx, r8d
0x180029717  jmp     short loc_180029726
0x180029719  mov     ebx, r10d
0x18002971c  sub     ebx, eax
0x18002971e  mov     eax, 0
0x180029723  cmovs   ebx, eax
0x180029726  mov     [rsp+60h+bRepaint], 1; bRepaint
0x18002972e  mov     edx, edi; X
0x180029730  mov     [rsp+60h+nHeight], r8d; nHeight
0x180029735  mov     rcx, r14; hWnd
0x180029738  mov     r8d, ebx; Y
0x18002973b  mov     [rbp+Rect.top], ebx
0x18002973e  call    cs:__imp_MoveWindow
0x180029744  mov     rcx, [rbp+var_10]
0x180029748  xor     rcx, rsp; StackCookie
0x18002974b  call    __security_check_cookie
0x180029750  lea     r11, [rsp+60h+var_s0]
0x180029755  mov     rbx, [r11+30h]
0x180029759  mov     rsi, [r11+38h]
0x18002975d  mov     rsp, r11
0x180029760  pop     r14
0x180029762  pop     rdi
0x180029763  pop     rbp
0x180029764  retn
```
