# CenterWindow(HWND__ *,HWND__ *)

- ea: `0x1800122c0`
- end: `0x1800123ca`
- name: `?CenterWindow@@YAXPEAUHWND__@@0@Z`
- size: `266`
- prototype: `void __fastcall(HWND hWnd, HWND)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180011f10`
- `0x180026780`
- `0x180034a90`
- `0x180065140`

## callees

- `0x1800122c0`
- `0x180075c90`

## import_xrefs

- `USER32!SystemParametersInfoA` at `0x18001235d`
- `USER32!SystemParametersInfoA` at `0x18001235d`
- `USER32!MoveWindow` at `0x1800123a4`
- `USER32!MoveWindow` at `0x1800123a4`
- `USER32!GetDesktopWindow` at `0x1800122fa`
- `USER32!GetDesktopWindow` at `0x1800122fa`
- `USER32!GetWindowRect` at `0x180012307`
- `USER32!GetWindowRect` at `0x180012314`
- `USER32!GetWindowRect` at `0x180012307`
- `USER32!GetWindowRect` at `0x180012314`

## pseudocode

```c
void __fastcall CenterWindow(HWND hWnd, HWND a2)
{
  HWND DesktopWindow; // rax
  int v4; // r14d
  int nHeight; // esi
  LONG left; // edi
  LONG top; // ebx
  struct tagRECT pvParam; // [rsp+30h] [rbp-30h] BYREF
  struct tagRECT Rect; // [rsp+40h] [rbp-20h] BYREF

  DesktopWindow = hWnd;
  Rect = 0;
  pvParam = 0;
  if ( !hWnd )
    DesktopWindow = GetDesktopWindow();
  GetWindowRect(DesktopWindow, &Rect);
  GetWindowRect(a2, &pvParam);
  v4 = pvParam.right - pvParam.left;
  nHeight = pvParam.bottom - pvParam.top;
  left = (Rect.right - (pvParam.right - pvParam.left) - Rect.left) / 2 + Rect.left;
  top = (Rect.bottom - (pvParam.bottom - pvParam.top) - Rect.top) / 2 + Rect.top;
  SystemParametersInfoA(0x30u, 0, &pvParam, 0);
  if ( left < pvParam.left )
    left = pvParam.left;
  if ( top < pvParam.top )
    top = pvParam.top;
  if ( v4 + left > pvParam.right )
    left = pvParam.right - v4;
  if ( nHeight + top > pvParam.bottom )
    top = pvParam.bottom - nHeight;
  MoveWindow(a2, left, top, v4, nHeight, 1);
}

```

## disassembly

```asm
0x1800122c0  mov     [rsp-28h+arg_10], rbx
0x1800122c5  push    rbp
0x1800122c6  push    rsi
0x1800122c7  push    rdi
0x1800122c8  push    r14
0x1800122ca  push    r15
0x1800122cc  mov     rbp, rsp
0x1800122cf  sub     rsp, 60h
0x1800122d3  mov     rax, cs:__security_cookie
0x1800122da  xor     rax, rsp
0x1800122dd  mov     [rbp+var_10], rax
0x1800122e1  xorps   xmm0, xmm0
0x1800122e4  xorps   xmm1, xmm1
0x1800122e7  mov     r15, rdx
0x1800122ea  mov     rax, rcx
0x1800122ed  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1800122f1  movups  xmmword ptr [rbp+pvParam.left], xmm1
0x1800122f5  test    rcx, rcx
0x1800122f8  jnz     short loc_180012300
0x1800122fa  call    cs:__imp_GetDesktopWindow
0x180012300  lea     rdx, [rbp+Rect]; lpRect
0x180012304  mov     rcx, rax; hWnd
0x180012307  call    cs:__imp_GetWindowRect
0x18001230d  lea     rdx, [rbp+pvParam]; lpRect
0x180012311  mov     rcx, r15; hWnd
0x180012314  call    cs:__imp_GetWindowRect
0x18001231a  mov     ecx, [rbp+Rect.left]
0x18001231d  mov     r8d, 2
0x180012323  mov     r14d, [rbp+pvParam.right]
0x180012327  xor     r9d, r9d; fWinIni
0x18001232a  sub     r14d, [rbp+pvParam.left]
0x18001232e  mov     eax, [rbp+Rect.right]
0x180012331  mov     esi, [rbp+pvParam.bottom]
0x180012334  sub     eax, r14d
0x180012337  sub     esi, [rbp+pvParam.top]
0x18001233a  sub     eax, ecx
0x18001233c  cdq
0x18001233d  idiv    r8d
0x180012340  lea     edi, [rax+rcx]
0x180012343  mov     ecx, [rbp+Rect.top]
0x180012346  mov     eax, [rbp+Rect.bottom]
0x180012349  sub     eax, esi
0x18001234b  sub     eax, ecx
0x18001234d  cdq
0x18001234e  idiv    r8d
0x180012351  xor     edx, edx; uiParam
0x180012353  lea     r8, [rbp+pvParam]; pvParam
0x180012357  lea     ebx, [rax+rcx]
0x18001235a  lea     ecx, [rdx+30h]; uiAction
0x18001235d  call    cs:__imp_SystemParametersInfoA
0x180012363  cmp     edi, [rbp+pvParam.left]
0x180012366  cmovl   edi, [rbp+pvParam.left]
0x18001236a  cmp     ebx, [rbp+pvParam.top]
0x18001236d  cmovl   ebx, [rbp+pvParam.top]
0x180012371  lea     eax, [r14+rdi]
0x180012375  cmp     eax, [rbp+pvParam.right]
0x180012378  jle     short loc_180012380
0x18001237a  mov     edi, [rbp+pvParam.right]
0x18001237d  sub     edi, r14d
0x180012380  lea     eax, [rsi+rbx]
0x180012383  cmp     eax, [rbp+pvParam.bottom]
0x180012386  jle     short loc_18001238D
0x180012388  mov     ebx, [rbp+pvParam.bottom]
0x18001238b  sub     ebx, esi
0x18001238d  mov     [rsp+60h+bRepaint], 1; bRepaint
0x180012395  mov     r9d, r14d; nWidth
0x180012398  mov     r8d, ebx; Y
0x18001239b  mov     [rsp+60h+nHeight], esi; nHeight
0x18001239f  mov     edx, edi; X
0x1800123a1  mov     rcx, r15; hWnd
0x1800123a4  call    cs:__imp_MoveWindow
0x1800123aa  mov     rcx, [rbp+var_10]
0x1800123ae  xor     rcx, rsp; StackCookie
0x1800123b1  call    __security_check_cookie
0x1800123b6  mov     rbx, [rsp+60h+arg_10]
0x1800123be  add     rsp, 60h
0x1800123c2  pop     r15
0x1800123c4  pop     r14
0x1800123c6  pop     rdi
0x1800123c7  pop     rsi
0x1800123c8  pop     rbp
0x1800123c9  retn
```
