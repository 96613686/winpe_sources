# DlgTemplate::CenterWindow(HWND__ *)

- ea: `0x18000b290`
- end: `0x18000b3f3`
- name: `?CenterWindow@DlgTemplate@@AEAAHPEAUHWND__@@@Z`
- size: `355`
- prototype: `__int64 __fastcall(DlgTemplate *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b54c`

## callees

- `0x18000b290`
- `0x18001b550`

## import_xrefs

- `USER32!GetWindow` at `0x18000b2d4`
- `USER32!GetWindow` at `0x18000b2d4`
- `USER32!GetWindowRect` at `0x18000b2e5`
- `USER32!GetWindowRect` at `0x18000b343`
- `USER32!GetWindowRect` at `0x18000b2e5`
- `USER32!GetWindowRect` at `0x18000b343`
- `USER32!GetWindowLongW` at `0x18000b304`
- `USER32!GetWindowLongW` at `0x18000b304`
- `USER32!SystemParametersInfoW` at `0x18000b326`
- `USER32!SystemParametersInfoW` at `0x18000b326`
- `USER32!SetWindowPos` at `0x18000b3c9`
- `USER32!SetWindowPos` at `0x18000b3c9`

## pseudocode

```c
BOOL __fastcall DlgTemplate::CenterWindow(DlgTemplate *this, HWND a2)
{
  HWND v3; // rcx
  HWND Window; // rbx
  int v5; // edi
  int v6; // esi
  int v7; // r9d
  int left; // r8d
  int v9; // ecx
  int top; // r9d
  struct tagRECT pvParam; // [rsp+40h] [rbp-40h] BYREF
  struct tagRECT v13; // [rsp+50h] [rbp-30h] BYREF
  tagRECT Rect; // [rsp+60h] [rbp-20h] BYREF

  v3 = (HWND)*((_QWORD *)this + 1);
  pvParam = 0;
  v13 = 0;
  Rect = 0;
  Window = GetWindow(v3, 4u);
  GetWindowRect(*((HWND *)this + 1), &Rect);
  v5 = Rect.right - Rect.left;
  v6 = Rect.bottom - Rect.top;
  if ( Window && (GetWindowLongW(Window, -16) & 0x30000000) != 0x10000000 )
    Window = 0;
  SystemParametersInfoW(0x30u, 0, &pvParam, 0);
  if ( Window )
    GetWindowRect(Window, &v13);
  else
    v13 = pvParam;
  v7 = (v13.left + v13.right) / 2 - v5 / 2;
  left = pvParam.left;
  v9 = (v13.top + v13.bottom) / 2 - v6 / 2;
  if ( v7 >= pvParam.left )
  {
    left = (v13.left + v13.right) / 2 - v5 / 2;
    if ( v7 + v5 > pvParam.right )
      left = pvParam.right - v5;
  }
  top = pvParam.top;
  if ( v9 >= pvParam.top )
  {
    top = (v13.top + v13.bottom) / 2 - v6 / 2;
    if ( v9 + v6 > pvParam.bottom )
      top = pvParam.bottom - v6;
  }
  return SetWindowPos(*((HWND *)this + 1), 0, left, top, -1, -1, 0x15u);
}

```

## disassembly

```asm
0x18000b290  mov     [rsp-18h+arg_8], rbx
0x18000b295  mov     [rsp-18h+arg_10], rsi
0x18000b29a  push    rbp
0x18000b29b  push    rdi
0x18000b29c  push    r14
0x18000b29e  mov     rbp, rsp
0x18000b2a1  sub     rsp, 80h
0x18000b2a8  mov     rax, cs:__security_cookie
0x18000b2af  xor     rax, rsp
0x18000b2b2  mov     [rbp+var_10], rax
0x18000b2b6  xorps   xmm0, xmm0
0x18000b2b9  mov     r14, rcx
0x18000b2bc  mov     rcx, [rcx+8]; hWnd
0x18000b2c0  xorps   xmm1, xmm1
0x18000b2c3  mov     edx, 4; uCmd
0x18000b2c8  movups  [rbp+pvParam], xmm0
0x18000b2cc  movups  xmmword ptr [rbp+var_30.left], xmm1
0x18000b2d0  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18000b2d4  call    cs:__imp_GetWindow
0x18000b2da  mov     rcx, [r14+8]; hWnd
0x18000b2de  lea     rdx, [rbp+Rect]; lpRect
0x18000b2e2  mov     rbx, rax
0x18000b2e5  call    cs:__imp_GetWindowRect
0x18000b2eb  mov     edi, [rbp+Rect.right]
0x18000b2ee  mov     esi, [rbp+Rect.bottom]
0x18000b2f1  sub     edi, [rbp+Rect.left]
0x18000b2f4  sub     esi, [rbp+Rect.top]
0x18000b2f7  test    rbx, rbx
0x18000b2fa  jz      short loc_18000B31A
0x18000b2fc  mov     edx, 0FFFFFFF0h; nIndex
0x18000b301  mov     rcx, rbx; hWnd
0x18000b304  call    cs:__imp_GetWindowLongW
0x18000b30a  xor     ecx, ecx
0x18000b30c  and     eax, 30000000h
0x18000b311  cmp     eax, 10000000h
0x18000b316  cmovnz  rbx, rcx
0x18000b31a  xor     edx, edx; uiParam
0x18000b31c  lea     r8, [rbp+pvParam]; pvParam
0x18000b320  xor     r9d, r9d; fWinIni
0x18000b323  lea     ecx, [rdx+30h]; uiAction
0x18000b326  call    cs:__imp_SystemParametersInfoW
0x18000b32c  test    rbx, rbx
0x18000b32f  jnz     short loc_18000B33C
0x18000b331  movaps  xmm0, [rbp+pvParam]
0x18000b335  movdqa  xmmword ptr [rbp+var_30.left], xmm0
0x18000b33a  jmp     short loc_18000B349
0x18000b33c  lea     rdx, [rbp+var_30]; lpRect
0x18000b340  mov     rcx, rbx; hWnd
0x18000b343  call    cs:__imp_GetWindowRect
0x18000b349  mov     eax, [rbp+var_30.right]
0x18000b34c  mov     r8d, 2
0x18000b352  add     eax, [rbp+var_30.left]
0x18000b355  cdq
0x18000b356  idiv    r8d
0x18000b359  mov     r9d, eax
0x18000b35c  mov     eax, edi
0x18000b35e  cdq
0x18000b35f  idiv    r8d
0x18000b362  sub     r9d, eax
0x18000b365  mov     eax, [rbp+var_30.bottom]
0x18000b368  add     eax, [rbp+var_30.top]
0x18000b36b  cdq
0x18000b36c  idiv    r8d
0x18000b36f  mov     ecx, eax
0x18000b371  mov     eax, esi
0x18000b373  cdq
0x18000b374  idiv    r8d
0x18000b377  mov     r8d, dword ptr [rbp+pvParam]
0x18000b37b  sub     ecx, eax
0x18000b37d  cmp     r9d, r8d
0x18000b380  jl      short loc_18000B395
0x18000b382  lea     eax, [r9+rdi]
0x18000b386  mov     r8d, r9d
0x18000b389  cmp     eax, dword ptr [rbp+pvParam+8]
0x18000b38c  jle     short loc_18000B395
0x18000b38e  mov     r8d, dword ptr [rbp+pvParam+8]
0x18000b392  sub     r8d, edi; X
0x18000b395  mov     r9d, dword ptr [rbp+pvParam+4]
0x18000b399  cmp     ecx, r9d
0x18000b39c  jl      short loc_18000B3B0
0x18000b39e  lea     eax, [rcx+rsi]
0x18000b3a1  mov     r9d, ecx
0x18000b3a4  cmp     eax, dword ptr [rbp+pvParam+0Ch]
0x18000b3a7  jle     short loc_18000B3B0
0x18000b3a9  mov     r9d, dword ptr [rbp+pvParam+0Ch]
0x18000b3ad  sub     r9d, esi; Y
0x18000b3b0  mov     rcx, [r14+8]; hWnd
0x18000b3b4  or      eax, 0FFFFFFFFh
0x18000b3b7  mov     [rsp+80h+uFlags], 15h; uFlags
0x18000b3bf  xor     edx, edx; hWndInsertAfter
0x18000b3c1  mov     [rsp+80h+cy], eax; cy
0x18000b3c5  mov     [rsp+80h+var_60], eax; cx
0x18000b3c9  call    cs:__imp_SetWindowPos
0x18000b3cf  mov     rcx, [rbp+var_10]
0x18000b3d3  xor     rcx, rsp; StackCookie
0x18000b3d6  call    __security_check_cookie
0x18000b3db  lea     r11, [rsp+80h+var_s0]
0x18000b3e3  mov     rbx, [r11+28h]
0x18000b3e7  mov     rsi, [r11+30h]
0x18000b3eb  mov     rsp, r11
0x18000b3ee  pop     r14
0x18000b3f0  pop     rdi
0x18000b3f1  pop     rbp
0x18000b3f2  retn
```
