# CenterPopupWindow(HWND__ *,HWND__ *)

- ea: `0x18001a9d4`
- end: `0x18001ab1c`
- name: `?CenterPopupWindow@@YAXPEAUHWND__@@0@Z`
- size: `328`
- prototype: `void __fastcall(HWND hWnd, HWND)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180015940`
- `0x180019bf0`

## callees

- `0x180001510`
- `0x18001a9d4`

## import_xrefs

- `USER32!GetParent` at `0x18001aa25`
- `USER32!GetParent` at `0x18001aa25`
- `USER32!GetSystemMetrics` at `0x18001aa08`
- `USER32!GetSystemMetrics` at `0x18001aa15`
- `USER32!GetSystemMetrics` at `0x18001aa08`
- `USER32!GetSystemMetrics` at `0x18001aa15`
- `USER32!MoveWindow` at `0x18001aaf5`
- `USER32!MoveWindow` at `0x18001aaf5`
- `USER32!GetDesktopWindow` at `0x18001aa33`
- `USER32!GetDesktopWindow` at `0x18001aa33`
- `USER32!GetWindowRect` at `0x18001aa51`
- `USER32!GetWindowRect` at `0x18001aa5e`
- `USER32!GetWindowRect` at `0x18001aa51`
- `USER32!GetWindowRect` at `0x18001aa5e`

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
0x18001a9d4  test    rcx, rcx
0x18001a9d7  jz      locret_18001AB1B
0x18001a9dd  mov     [rsp-18h+arg_10], rbx
0x18001a9e2  mov     [rsp-18h+arg_18], rsi
0x18001a9e7  push    rbp
0x18001a9e8  push    rdi
0x18001a9e9  push    r14
0x18001a9eb  mov     rbp, rsp
0x18001a9ee  sub     rsp, 60h
0x18001a9f2  mov     rax, cs:__security_cookie
0x18001a9f9  xor     rax, rsp
0x18001a9fc  mov     [rbp+var_10], rax
0x18001aa00  mov     r14, rcx
0x18001aa03  mov     rsi, rdx
0x18001aa06  xor     ecx, ecx; nIndex
0x18001aa08  call    cs:__imp_GetSystemMetrics
0x18001aa0e  mov     ecx, 1; nIndex
0x18001aa13  mov     edi, eax
0x18001aa15  call    cs:__imp_GetSystemMetrics
0x18001aa1b  mov     ebx, eax
0x18001aa1d  test    rsi, rsi
0x18001aa20  jnz     short loc_18001AA3C
0x18001aa22  mov     rcx, r14; hWnd
0x18001aa25  call    cs:__imp_GetParent
0x18001aa2b  mov     rsi, rax
0x18001aa2e  test    rax, rax
0x18001aa31  jnz     short loc_18001AA3C
0x18001aa33  call    cs:__imp_GetDesktopWindow
0x18001aa39  mov     rsi, rax
0x18001aa3c  xorps   xmm0, xmm0
0x18001aa3f  lea     rdx, [rbp+Rect]; lpRect
0x18001aa43  xorps   xmm1, xmm1
0x18001aa46  mov     rcx, r14; hWnd
0x18001aa49  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18001aa4d  movups  xmmword ptr [rbp+var_20.left], xmm1
0x18001aa51  call    cs:__imp_GetWindowRect
0x18001aa57  lea     rdx, [rbp+var_20]; lpRect
0x18001aa5b  mov     rcx, rsi; hWnd
0x18001aa5e  call    cs:__imp_GetWindowRect
0x18001aa64  mov     ecx, [rbp+var_20.left]
0x18001aa67  mov     eax, [rbp+var_20.right]
0x18001aa6a  mov     r9d, [rbp+Rect.right]
0x18001aa6e  sub     eax, ecx
0x18001aa70  sub     r9d, [rbp+Rect.left]; nWidth
0x18001aa74  cdq
0x18001aa75  mov     r8d, [rbp+Rect.bottom]
0x18001aa79  sub     eax, edx
0x18001aa7b  sub     r8d, [rbp+Rect.top]
0x18001aa7f  sar     eax, 1
0x18001aa81  lea     r11d, [rax+rcx]
0x18001aa85  mov     ecx, [rbp+var_20.top]
0x18001aa88  mov     eax, [rbp+var_20.bottom]
0x18001aa8b  sub     eax, ecx
0x18001aa8d  cdq
0x18001aa8e  sub     eax, edx
0x18001aa90  sar     eax, 1
0x18001aa92  lea     r10d, [rax+rcx]
0x18001aa96  mov     eax, r9d
0x18001aa99  cdq
0x18001aa9a  sub     eax, edx
0x18001aa9c  sar     eax, 1
0x18001aa9e  lea     ecx, [rax+r11]
0x18001aaa2  cmp     ecx, edi
0x18001aaa4  jle     short loc_18001AAAB
0x18001aaa6  sub     edi, r9d
0x18001aaa9  jmp     short loc_18001AAB8
0x18001aaab  mov     edi, r11d
0x18001aaae  sub     edi, eax
0x18001aab0  mov     eax, 0
0x18001aab5  cmovs   edi, eax
0x18001aab8  mov     eax, r8d
0x18001aabb  mov     [rbp+Rect.left], edi
0x18001aabe  cdq
0x18001aabf  sub     eax, edx
0x18001aac1  sar     eax, 1
0x18001aac3  lea     ecx, [rax+r10]
0x18001aac7  cmp     ecx, ebx
0x18001aac9  jle     short loc_18001AAD0
0x18001aacb  sub     ebx, r8d
0x18001aace  jmp     short loc_18001AADD
0x18001aad0  mov     ebx, r10d
0x18001aad3  sub     ebx, eax
0x18001aad5  mov     eax, 0
0x18001aada  cmovs   ebx, eax
0x18001aadd  mov     [rsp+60h+bRepaint], 1; bRepaint
0x18001aae5  mov     edx, edi; X
0x18001aae7  mov     [rsp+60h+nHeight], r8d; nHeight
0x18001aaec  mov     rcx, r14; hWnd
0x18001aaef  mov     r8d, ebx; Y
0x18001aaf2  mov     [rbp+Rect.top], ebx
0x18001aaf5  call    cs:__imp_MoveWindow
0x18001aafb  mov     rcx, [rbp+var_10]
0x18001aaff  xor     rcx, rsp; StackCookie
0x18001ab02  call    __security_check_cookie
0x18001ab07  lea     r11, [rsp+60h+var_s0]
0x18001ab0c  mov     rbx, [r11+30h]
0x18001ab10  mov     rsi, [r11+38h]
0x18001ab14  mov     rsp, r11
0x18001ab17  pop     r14
0x18001ab19  pop     rdi
0x18001ab1a  pop     rbp
0x18001ab1b  retn
```
