# GetCenteredWindow(HWND__ *,tagPOINT *)

- ea: `0x18003b8dc`
- end: `0x18003babd`
- name: `?GetCenteredWindow@@YAHPEAUHWND__@@PEAUtagPOINT@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(HWND hWnd, struct tagPOINT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003d7ec`

## callees

- `0x18003b8dc`
- `0x18003e5c0`

## import_xrefs

- `USER32!GetParent` at `0x18003b963`
- `USER32!GetParent` at `0x18003b9e3`
- `USER32!GetParent` at `0x18003b963`
- `USER32!GetParent` at `0x18003b9e3`
- `USER32!GetWindowRect` at `0x18003b980`
- `USER32!GetWindowRect` at `0x18003b9d8`
- `USER32!GetWindowRect` at `0x18003b980`
- `USER32!GetWindowRect` at `0x18003b9d8`
- `USER32!MapWindowPoints` at `0x18003ba13`
- `USER32!MapWindowPoints` at `0x18003ba13`
- `USER32!GetWindowLongPtrW` at `0x18003b94e`
- `USER32!GetWindowLongPtrW` at `0x18003b997`
- `USER32!GetWindowLongPtrW` at `0x18003b94e`
- `USER32!GetWindowLongPtrW` at `0x18003b997`
- `USER32!MonitorFromWindow` at `0x18003b92d`
- `USER32!MonitorFromWindow` at `0x18003b92d`
- `USER32!GetMonitorInfoW` at `0x18003b941`
- `USER32!GetMonitorInfoW` at `0x18003b941`
- `USER32!GetWindow` at `0x18003b970`
- `USER32!GetWindow` at `0x18003b970`
- `USER32!CopyRect` at `0x18003b9b6`
- `USER32!CopyRect` at `0x18003b9c9`
- `USER32!CopyRect` at `0x18003b9b6`
- `USER32!CopyRect` at `0x18003b9c9`
- `USER32!GetClientRect` at `0x18003b9f3`
- `USER32!GetClientRect` at `0x18003ba00`
- `USER32!GetClientRect` at `0x18003b9f3`
- `USER32!GetClientRect` at `0x18003ba00`

## pseudocode

```c
__int64 __fastcall GetCenteredWindow(HWND hWnd, struct tagPOINT *a2)
{
  HMONITOR v4; // rax
  int WindowLongPtrW; // eax
  __int64 v6; // r14
  HWND Parent; // rax
  HWND v8; // rdi
  HWND v9; // rbx
  int v10; // r9d
  int v11; // r11d
  LONG v12; // r10d
  int left; // edx
  LONG v14; // r8d
  int top; // ecx
  struct tagRECT v17; // [rsp+20h] [rbp-60h] BYREF
  struct tagRECT rcDst; // [rsp+30h] [rbp-50h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-40h] BYREF
  tagMONITORINFO mi; // [rsp+50h] [rbp-30h] BYREF

  Rect = 0;
  rcDst = 0;
  v17 = 0;
  memset(&mi, 0, sizeof(mi));
  v4 = MonitorFromWindow(hWnd, 2u);
  mi.cbSize = 40;
  GetMonitorInfoW(v4, &mi);
  WindowLongPtrW = GetWindowLongPtrW(hWnd, -16);
  v6 = WindowLongPtrW & 0x40000000;
  if ( (WindowLongPtrW & 0x40000000) != 0 )
    Parent = GetParent(hWnd);
  else
    Parent = GetWindow(hWnd, 4u);
  v8 = Parent;
  GetWindowRect(hWnd, &Rect);
  if ( v6 )
  {
    v9 = GetParent(hWnd);
    GetClientRect(v9, &rcDst);
    GetClientRect(v8, &v17);
    MapWindowPoints(v8, v9, (LPPOINT)&v17, 2u);
  }
  else
  {
    if ( v8 && (GetWindowLongPtrW(v8, -16) & 0x30000000) != 0x10000000 )
      v8 = 0;
    CopyRect(&rcDst, &mi.rcWork);
    if ( v8 )
      GetWindowRect(v8, &v17);
    else
      CopyRect(&v17, &mi.rcWork);
  }
  v10 = Rect.right - Rect.left;
  v11 = Rect.bottom - Rect.top;
  v12 = (v17.left + v17.right) / 2 - (Rect.right - Rect.left) / 2;
  left = rcDst.left;
  v14 = (v17.top + v17.bottom) / 2 - (Rect.bottom - Rect.top) / 2;
  if ( v12 >= rcDst.left )
  {
    left = (v17.left + v17.right) / 2 - (Rect.right - Rect.left) / 2;
    if ( v12 + v10 > rcDst.right )
      left = rcDst.right - v10;
  }
  top = rcDst.top;
  if ( v14 >= rcDst.top )
  {
    top = (v17.top + v17.bottom) / 2 - (Rect.bottom - Rect.top) / 2;
    if ( v14 + v11 > rcDst.bottom )
      top = rcDst.bottom - v11;
  }
  if ( a2 )
  {
    a2->x = left;
    a2->y = top;
  }
  return 1;
}

```

## disassembly

```asm
0x18003b8dc  mov     [rsp-28h+arg_10], rbx
0x18003b8e1  push    rbp
0x18003b8e2  push    rsi
0x18003b8e3  push    rdi
0x18003b8e4  push    r14
0x18003b8e6  push    r15
0x18003b8e8  mov     rbp, rsp
0x18003b8eb  sub     rsp, 80h
0x18003b8f2  mov     rax, cs:__security_cookie
0x18003b8f9  xor     rax, rsp
0x18003b8fc  mov     [rbp+var_8], rax
0x18003b900  xorps   xmm1, xmm1
0x18003b903  xor     eax, eax
0x18003b905  xorps   xmm0, xmm0
0x18003b908  mov     qword ptr [rbp+mi.rcWork.bottom], rax
0x18003b90c  mov     rsi, rdx
0x18003b90f  mov     rbx, rcx
0x18003b912  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18003b916  lea     r15d, [rax+2]
0x18003b91a  mov     edx, r15d; dwFlags
0x18003b91d  movups  xmmword ptr [rbp+rcDst.left], xmm1
0x18003b921  movups  xmmword ptr [rbp+var_60.left], xmm0
0x18003b925  movups  xmmword ptr [rbp+mi.cbSize], xmm1
0x18003b929  movups  xmmword ptr [rbp+mi.rcMonitor.bottom], xmm1
0x18003b92d  call    cs:__imp_MonitorFromWindow
0x18003b933  lea     rdx, [rbp+mi]; lpmi
0x18003b937  mov     [rbp+mi.cbSize], 28h ; '('
0x18003b93e  mov     rcx, rax; hMonitor
0x18003b941  call    cs:__imp_GetMonitorInfoW
0x18003b947  lea     edx, [r15-12h]; nIndex
0x18003b94b  mov     rcx, rbx; hWnd
0x18003b94e  call    cs:__imp_GetWindowLongPtrW
0x18003b954  mov     r14, rax
0x18003b957  mov     rcx, rbx; hWnd
0x18003b95a  and     r14d, 40000000h
0x18003b961  jz      short loc_18003B96B
0x18003b963  call    cs:__imp_GetParent
0x18003b969  jmp     short loc_18003B976
0x18003b96b  mov     edx, 4; uCmd
0x18003b970  call    cs:__imp_GetWindow
0x18003b976  lea     rdx, [rbp+Rect]; lpRect
0x18003b97a  mov     rcx, rbx; hWnd
0x18003b97d  mov     rdi, rax
0x18003b980  call    cs:__imp_GetWindowRect
0x18003b986  test    r14, r14
0x18003b989  jnz     short loc_18003B9E0
0x18003b98b  test    rdi, rdi
0x18003b98e  jz      short loc_18003B9AE
0x18003b990  lea     edx, [r14-10h]; nIndex
0x18003b994  mov     rcx, rdi; hWnd
0x18003b997  call    cs:__imp_GetWindowLongPtrW
0x18003b99d  xor     ecx, ecx
0x18003b99f  and     eax, 30000000h
0x18003b9a4  cmp     rax, 10000000h
0x18003b9aa  cmovnz  rdi, rcx
0x18003b9ae  lea     rdx, [rbp+mi.rcWork]; lprcSrc
0x18003b9b2  lea     rcx, [rbp+rcDst]; lprcDst
0x18003b9b6  call    cs:__imp_CopyRect
0x18003b9bc  test    rdi, rdi
0x18003b9bf  jnz     short loc_18003B9D1
0x18003b9c1  lea     rdx, [rbp+mi.rcWork]; lprcSrc
0x18003b9c5  lea     rcx, [rbp+var_60]; lprcDst
0x18003b9c9  call    cs:__imp_CopyRect
0x18003b9cf  jmp     short loc_18003BA19
0x18003b9d1  lea     rdx, [rbp+var_60]; lpRect
0x18003b9d5  mov     rcx, rdi; hWnd
0x18003b9d8  call    cs:__imp_GetWindowRect
0x18003b9de  jmp     short loc_18003BA19
0x18003b9e0  mov     rcx, rbx; hWnd
0x18003b9e3  call    cs:__imp_GetParent
0x18003b9e9  mov     rcx, rax; hWnd
0x18003b9ec  lea     rdx, [rbp+rcDst]; lpRect
0x18003b9f0  mov     rbx, rax
0x18003b9f3  call    cs:__imp_GetClientRect
0x18003b9f9  lea     rdx, [rbp+var_60]; lpRect
0x18003b9fd  mov     rcx, rdi; hWnd
0x18003ba00  call    cs:__imp_GetClientRect
0x18003ba06  mov     r9d, r15d; cPoints
0x18003ba09  lea     r8, [rbp+var_60]; lpPoints
0x18003ba0d  mov     rdx, rbx; hWndTo
0x18003ba10  mov     rcx, rdi; hWndFrom
0x18003ba13  call    cs:__imp_MapWindowPoints
0x18003ba19  mov     eax, [rbp+var_60.right]
0x18003ba1c  add     eax, [rbp+var_60.left]
0x18003ba1f  mov     r9d, [rbp+Rect.right]
0x18003ba23  cdq
0x18003ba24  sub     r9d, [rbp+Rect.left]
0x18003ba28  mov     r11d, [rbp+Rect.bottom]
0x18003ba2c  sub     r11d, [rbp+Rect.top]
0x18003ba30  idiv    r15d
0x18003ba33  mov     r10d, eax
0x18003ba36  mov     eax, r9d
0x18003ba39  cdq
0x18003ba3a  idiv    r15d
0x18003ba3d  sub     r10d, eax
0x18003ba40  mov     eax, [rbp+var_60.bottom]
0x18003ba43  add     eax, [rbp+var_60.top]
0x18003ba46  cdq
0x18003ba47  idiv    r15d
0x18003ba4a  mov     r8d, eax
0x18003ba4d  mov     eax, r11d
0x18003ba50  cdq
0x18003ba51  idiv    r15d
0x18003ba54  mov     edx, [rbp+rcDst.left]
0x18003ba57  sub     r8d, eax
0x18003ba5a  cmp     r10d, edx
0x18003ba5d  jl      short loc_18003BA71
0x18003ba5f  lea     eax, [r10+r9]
0x18003ba63  mov     edx, r10d
0x18003ba66  cmp     eax, [rbp+rcDst.right]
0x18003ba69  jle     short loc_18003BA71
0x18003ba6b  mov     edx, [rbp+rcDst.right]
0x18003ba6e  sub     edx, r9d
0x18003ba71  mov     ecx, [rbp+rcDst.top]
0x18003ba74  cmp     r8d, ecx
0x18003ba77  jl      short loc_18003BA8B
0x18003ba79  lea     eax, [r8+r11]
0x18003ba7d  mov     ecx, r8d
0x18003ba80  cmp     eax, [rbp+rcDst.bottom]
0x18003ba83  jle     short loc_18003BA8B
0x18003ba85  mov     ecx, [rbp+rcDst.bottom]
0x18003ba88  sub     ecx, r11d
0x18003ba8b  test    rsi, rsi
0x18003ba8e  jz      short loc_18003BA95
0x18003ba90  mov     [rsi], edx
0x18003ba92  mov     [rsi+4], ecx
0x18003ba95  mov     eax, 1
0x18003ba9a  mov     rcx, [rbp+var_8]
0x18003ba9e  xor     rcx, rsp; StackCookie
0x18003baa1  call    __security_check_cookie
0x18003baa6  mov     rbx, [rsp+80h+arg_10]
0x18003baae  add     rsp, 80h
0x18003bab5  pop     r15
0x18003bab7  pop     r14
0x18003bab9  pop     rdi
0x18003baba  pop     rsi
0x18003babb  pop     rbp
0x18003babc  retn
```
