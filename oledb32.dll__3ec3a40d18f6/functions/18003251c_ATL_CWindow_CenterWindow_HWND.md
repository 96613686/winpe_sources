# ATL::CWindow::CenterWindow(HWND__ *)

- ea: `0x18003251c`
- end: `0x1800326e3`
- name: `?CenterWindow@CWindow@ATL@@QEAAHPEAUHWND__@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(ATL::CWindow *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180050020`
- `0x18005ae40`

## callees

- `0x18003251c`
- `0x18007e700`

## import_xrefs

- `USER32!SetWindowPos` at `0x1800326b9`
- `USER32!SetWindowPos` at `0x1800326b9`
- `USER32!MapWindowPoints` at `0x180032627`
- `USER32!MapWindowPoints` at `0x180032627`
- `USER32!GetClientRect` at `0x180032607`
- `USER32!GetClientRect` at `0x180032614`
- `USER32!GetClientRect` at `0x180032607`
- `USER32!GetClientRect` at `0x180032614`
- `USER32!SystemParametersInfoW` at `0x1800325cf`
- `USER32!SystemParametersInfoW` at `0x1800325cf`
- `USER32!GetWindowRect` at `0x180032584`
- `USER32!GetWindowRect` at `0x1800325ec`
- `USER32!GetWindowRect` at `0x180032584`
- `USER32!GetWindowRect` at `0x1800325ec`
- `USER32!GetParent` at `0x180032560`
- `USER32!GetParent` at `0x1800325f7`
- `USER32!GetParent` at `0x180032560`
- `USER32!GetParent` at `0x1800325f7`
- `USER32!GetWindowLongW` at `0x18003254d`
- `USER32!GetWindowLongW` at `0x1800325ad`
- `USER32!GetWindowLongW` at `0x18003254d`
- `USER32!GetWindowLongW` at `0x1800325ad`
- `USER32!GetWindow` at `0x18003256d`
- `USER32!GetWindow` at `0x18003256d`

## pseudocode

```c
BOOL __fastcall ATL::CWindow::CenterWindow(HWND *this, HWND a2)
{
  LONG WindowLongW; // eax
  HWND v4; // rcx
  int v5; // ebx
  HWND Parent; // rax
  HWND v7; // rcx
  HWND v8; // rdi
  HWND v9; // rbx
  int v10; // r9d
  int v11; // r11d
  LONG left; // r8d
  LONG v13; // r10d
  LONG v14; // ecx
  LONG top; // r9d
  struct tagRECT pvParam; // [rsp+40h] [rbp-40h] BYREF
  struct tagRECT v18; // [rsp+50h] [rbp-30h] BYREF
  tagRECT Rect; // [rsp+60h] [rbp-20h] BYREF

  WindowLongW = GetWindowLongW(*this, -16);
  v4 = *this;
  v5 = WindowLongW & 0x40000000;
  if ( (WindowLongW & 0x40000000) != 0 )
    Parent = GetParent(v4);
  else
    Parent = GetWindow(v4, 4u);
  v7 = *this;
  v8 = Parent;
  Rect = 0;
  GetWindowRect(v7, &Rect);
  pvParam = 0;
  v18 = 0;
  if ( v5 )
  {
    v9 = GetParent(*this);
    GetClientRect(v9, &pvParam);
    GetClientRect(v8, &v18);
    MapWindowPoints(v8, v9, (LPPOINT)&v18, 2u);
  }
  else
  {
    if ( v8 && (GetWindowLongW(v8, -16) & 0x30000000) != 0x10000000 )
      v8 = 0;
    SystemParametersInfoW(0x30u, 0, &pvParam, 0);
    if ( v8 )
      GetWindowRect(v8, &v18);
    else
      v18 = pvParam;
  }
  v10 = Rect.right - Rect.left;
  v11 = Rect.bottom - Rect.top;
  left = pvParam.left;
  v13 = (v18.left + v18.right) / 2 - (Rect.right - Rect.left) / 2;
  v14 = (v18.top + v18.bottom) / 2 - (Rect.bottom - Rect.top) / 2;
  if ( v13 >= pvParam.left )
  {
    left = (v18.left + v18.right) / 2 - (Rect.right - Rect.left) / 2;
    if ( v13 + v10 > pvParam.right )
      left = pvParam.right - v10;
  }
  top = pvParam.top;
  if ( v14 >= pvParam.top )
  {
    top = (v18.top + v18.bottom) / 2 - (Rect.bottom - Rect.top) / 2;
    if ( v14 + v11 > pvParam.bottom )
      top = pvParam.bottom - v11;
  }
  return SetWindowPos(*this, 0, left, top, -1, -1, 0x15u);
}

```

## disassembly

```asm
0x18003251c  mov     [rsp-18h+arg_8], rbx
0x180032521  mov     [rsp-18h+arg_10], rsi
0x180032526  push    rbp
0x180032527  push    rdi
0x180032528  push    r15
0x18003252a  mov     rbp, rsp
0x18003252d  sub     rsp, 80h
0x180032534  mov     rax, cs:__security_cookie
0x18003253b  xor     rax, rsp
0x18003253e  mov     [rbp+var_10], rax
0x180032542  mov     rsi, rcx
0x180032545  mov     edx, 0FFFFFFF0h; nIndex
0x18003254a  mov     rcx, [rcx]; hWnd
0x18003254d  call    cs:__imp_GetWindowLongW
0x180032553  mov     rcx, [rsi]; hWnd
0x180032556  mov     ebx, eax
0x180032558  and     ebx, 40000000h
0x18003255e  jz      short loc_180032568
0x180032560  call    cs:__imp_GetParent
0x180032566  jmp     short loc_180032573
0x180032568  mov     edx, 4; uCmd
0x18003256d  call    cs:__imp_GetWindow
0x180032573  mov     rcx, [rsi]; hWnd
0x180032576  lea     rdx, [rbp+Rect]; lpRect
0x18003257a  xorps   xmm0, xmm0
0x18003257d  mov     rdi, rax
0x180032580  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180032584  call    cs:__imp_GetWindowRect
0x18003258a  xorps   xmm0, xmm0
0x18003258d  xorps   xmm1, xmm1
0x180032590  mov     r15d, 2
0x180032596  movups  [rbp+pvParam], xmm0
0x18003259a  movups  xmmword ptr [rbp+var_30.left], xmm1
0x18003259e  test    ebx, ebx
0x1800325a0  jnz     short loc_1800325F4
0x1800325a2  test    rdi, rdi
0x1800325a5  jz      short loc_1800325C3
0x1800325a7  lea     edx, [rbx-10h]; nIndex
0x1800325aa  mov     rcx, rdi; hWnd
0x1800325ad  call    cs:__imp_GetWindowLongW
0x1800325b3  xor     ecx, ecx
0x1800325b5  and     eax, 30000000h
0x1800325ba  cmp     eax, 10000000h
0x1800325bf  cmovnz  rdi, rcx
0x1800325c3  xor     edx, edx; uiParam
0x1800325c5  lea     r8, [rbp+pvParam]; pvParam
0x1800325c9  xor     r9d, r9d; fWinIni
0x1800325cc  lea     ecx, [rdx+30h]; uiAction
0x1800325cf  call    cs:__imp_SystemParametersInfoW
0x1800325d5  test    rdi, rdi
0x1800325d8  jnz     short loc_1800325E5
0x1800325da  movaps  xmm0, [rbp+pvParam]
0x1800325de  movdqa  xmmword ptr [rbp+var_30.left], xmm0
0x1800325e3  jmp     short loc_18003262D
0x1800325e5  lea     rdx, [rbp+var_30]; lpRect
0x1800325e9  mov     rcx, rdi; hWnd
0x1800325ec  call    cs:__imp_GetWindowRect
0x1800325f2  jmp     short loc_18003262D
0x1800325f4  mov     rcx, [rsi]; hWnd
0x1800325f7  call    cs:__imp_GetParent
0x1800325fd  mov     rcx, rax; hWnd
0x180032600  lea     rdx, [rbp+pvParam]; lpRect
0x180032604  mov     rbx, rax
0x180032607  call    cs:__imp_GetClientRect
0x18003260d  lea     rdx, [rbp+var_30]; lpRect
0x180032611  mov     rcx, rdi; hWnd
0x180032614  call    cs:__imp_GetClientRect
0x18003261a  mov     r9d, r15d; cPoints
0x18003261d  lea     r8, [rbp+var_30]; lpPoints
0x180032621  mov     rdx, rbx; hWndTo
0x180032624  mov     rcx, rdi; hWndFrom
0x180032627  call    cs:__imp_MapWindowPoints
0x18003262d  mov     eax, [rbp+var_30.right]
0x180032630  add     eax, [rbp+var_30.left]
0x180032633  mov     r9d, [rbp+Rect.right]
0x180032637  cdq
0x180032638  sub     r9d, [rbp+Rect.left]
0x18003263c  mov     r11d, [rbp+Rect.bottom]
0x180032640  sub     r11d, [rbp+Rect.top]
0x180032644  mov     r8d, dword ptr [rbp+pvParam]
0x180032648  idiv    r15d
0x18003264b  mov     r10d, eax
0x18003264e  mov     eax, r9d
0x180032651  cdq
0x180032652  idiv    r15d
0x180032655  sub     r10d, eax
0x180032658  mov     eax, [rbp+var_30.bottom]
0x18003265b  add     eax, [rbp+var_30.top]
0x18003265e  cdq
0x18003265f  idiv    r15d
0x180032662  mov     ecx, eax
0x180032664  mov     eax, r11d
0x180032667  cdq
0x180032668  idiv    r15d
0x18003266b  sub     ecx, eax
0x18003266d  cmp     r10d, r8d
0x180032670  jl      short loc_180032685
0x180032672  lea     eax, [r10+r9]
0x180032676  mov     r8d, r10d
0x180032679  cmp     eax, dword ptr [rbp+pvParam+8]
0x18003267c  jle     short loc_180032685
0x18003267e  mov     r8d, dword ptr [rbp+pvParam+8]
0x180032682  sub     r8d, r9d; X
0x180032685  mov     r9d, dword ptr [rbp+pvParam+4]
0x180032689  cmp     ecx, r9d
0x18003268c  jl      short loc_1800326A1
0x18003268e  lea     eax, [rcx+r11]
0x180032692  mov     r9d, ecx
0x180032695  cmp     eax, dword ptr [rbp+pvParam+0Ch]
0x180032698  jle     short loc_1800326A1
0x18003269a  mov     r9d, dword ptr [rbp+pvParam+0Ch]
0x18003269e  sub     r9d, r11d; Y
0x1800326a1  mov     rcx, [rsi]; hWnd
0x1800326a4  or      eax, 0FFFFFFFFh
0x1800326a7  mov     [rsp+80h+uFlags], 15h; uFlags
0x1800326af  xor     edx, edx; hWndInsertAfter
0x1800326b1  mov     [rsp+80h+cy], eax; cy
0x1800326b5  mov     [rsp+80h+var_60], eax; cx
0x1800326b9  call    cs:__imp_SetWindowPos
0x1800326bf  mov     rcx, [rbp+var_10]
0x1800326c3  xor     rcx, rsp; StackCookie
0x1800326c6  call    __security_check_cookie
0x1800326cb  lea     r11, [rsp+80h+var_s0]
0x1800326d3  mov     rbx, [r11+28h]
0x1800326d7  mov     rsi, [r11+30h]
0x1800326db  mov     rsp, r11
0x1800326de  pop     r15
0x1800326e0  pop     rdi
0x1800326e1  pop     rbp
0x1800326e2  retn
```
