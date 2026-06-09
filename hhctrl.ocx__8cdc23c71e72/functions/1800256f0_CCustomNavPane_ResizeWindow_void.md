# CCustomNavPane::ResizeWindow(void)

- ea: `0x1800256f0`
- end: `0x1800257fd`
- name: `?ResizeWindow@CCustomNavPane@@UEAAXXZ`
- size: `269`
- prototype: `void __fastcall(CCustomNavPane *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180006708`
- `0x1800256f0`
- `0x180066f80`
- `0x180075c90`

## import_xrefs

- `USER32!ScreenToClient` at `0x18002579c`
- `USER32!ScreenToClient` at `0x18002579c`
- `USER32!MoveWindow` at `0x18002576d`
- `USER32!MoveWindow` at `0x18002576d`
- `USER32!SetWindowPos` at `0x1800257d9`
- `USER32!SetWindowPos` at `0x1800257d9`
- `USER32!GetWindowRect` at `0x180025782`
- `USER32!GetWindowRect` at `0x180025782`
- `USER32!GetParent` at `0x180025728`
- `USER32!GetParent` at `0x180025728`

## pseudocode

```c
void __fastcall CCustomNavPane::ResizeWindow(HWND *this)
{
  HWND Parent; // rax
  int v3; // r9d
  int v4; // r8d
  HWND v5; // rcx
  HWND v6; // rcx
  HWND v7; // rbx
  struct tagPOINT Point; // [rsp+40h] [rbp-30h] BYREF
  int X[4]; // [rsp+48h] [rbp-28h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-18h] BYREF

  if ( (unsigned int)IsValidWindow(this[1]) )
  {
    Parent = GetParent(this[1]);
    v3 = *((_DWORD *)this + 7);
    v4 = *((_DWORD *)this + 6);
    *(_OWORD *)X = 0;
    GetParentSize((LPRECT)X, Parent, v4, v3);
    MoveWindow(this[1], X[0], X[1], X[2] - X[0], X[3] - X[1], 0);
    v5 = this[1];
    Rect = 0;
    GetWindowRect(v5, &Rect);
    v6 = this[1];
    v7 = this[4];
    Point = 0;
    ScreenToClient(v6, &Point);
    SetWindowPos(v7, 0, Rect.left + Point.x, Rect.top + Point.y, Rect.right - Rect.left, Rect.bottom - Rect.top, 0x14u);
  }
}

```

## disassembly

```asm
0x1800256f0  mov     [rsp-8+arg_8], rbx
0x1800256f5  mov     [rsp-8+arg_10], rdi
0x1800256fa  push    rbp
0x1800256fb  mov     rbp, rsp
0x1800256fe  sub     rsp, 70h
0x180025702  mov     rax, cs:__security_cookie
0x180025709  xor     rax, rsp
0x18002570c  mov     [rbp+var_8], rax
0x180025710  mov     rdi, rcx
0x180025713  mov     rcx, [rcx+8]; HWND
0x180025717  call    ?IsValidWindow@@YAHPEAUHWND__@@@Z; IsValidWindow(HWND__ *)
0x18002571c  test    eax, eax
0x18002571e  jz      loc_1800257DF
0x180025724  mov     rcx, [rdi+8]; hWnd
0x180025728  call    cs:__imp_GetParent
0x18002572e  mov     r9d, [rdi+1Ch]; int
0x180025732  lea     rcx, [rbp+X]; lprc
0x180025736  mov     r8d, [rdi+18h]; int
0x18002573a  xorps   xmm0, xmm0
0x18002573d  mov     rdx, rax; hWnd
0x180025740  movups  xmmword ptr [rbp+X], xmm0
0x180025744  call    ?GetParentSize@@YAPEAUHWND__@@PEAUtagRECT@@PEAU1@HH@Z; GetParentSize(tagRECT *,HWND__ *,int,int)
0x180025749  mov     eax, [rbp+X+0Ch]
0x18002574c  mov     r8d, [rbp+X+4]; Y
0x180025750  sub     eax, r8d
0x180025753  mov     r9d, [rbp+X+8]
0x180025757  mov     edx, [rbp+X]; X
0x18002575a  sub     r9d, edx; nWidth
0x18002575d  mov     rcx, [rdi+8]; hWnd
0x180025761  mov     [rsp+70h+bRepaint], 0; bRepaint
0x180025769  mov     [rsp+70h+nHeight], eax; nHeight
0x18002576d  call    cs:__imp_MoveWindow
0x180025773  mov     rcx, [rdi+8]; hWnd
0x180025777  lea     rdx, [rbp+Rect]; lpRect
0x18002577b  xorps   xmm0, xmm0
0x18002577e  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180025782  call    cs:__imp_GetWindowRect
0x180025788  mov     rcx, [rdi+8]; hWnd
0x18002578c  lea     rdx, [rbp+Point]; lpPoint
0x180025790  mov     rbx, [rdi+20h]
0x180025794  mov     qword ptr [rbp+Point.x], 0
0x18002579c  call    cs:__imp_ScreenToClient
0x1800257a2  mov     r11d, [rbp+Rect.bottom]
0x1800257a6  xor     edx, edx; hWndInsertAfter
0x1800257a8  mov     r10d, [rbp+Rect.right]
0x1800257ac  mov     rcx, rbx; hWnd
0x1800257af  sub     r11d, [rbp+Rect.top]
0x1800257b3  mov     r9d, [rbp+Point.y]
0x1800257b7  mov     r8d, [rbp+Point.x]
0x1800257bb  sub     r10d, [rbp+Rect.left]
0x1800257bf  add     r9d, [rbp+Rect.top]; Y
0x1800257c3  add     r8d, [rbp+Rect.left]; X
0x1800257c7  mov     [rsp+70h+uFlags], 14h; uFlags
0x1800257cf  mov     [rsp+70h+bRepaint], r11d; cy
0x1800257d4  mov     [rsp+70h+nHeight], r10d; cx
0x1800257d9  call    cs:__imp_SetWindowPos
0x1800257df  mov     rcx, [rbp+var_8]
0x1800257e3  xor     rcx, rsp; StackCookie
0x1800257e6  call    __security_check_cookie
0x1800257eb  lea     r11, [rsp+70h+var_s0]
0x1800257f0  mov     rbx, [r11+18h]
0x1800257f4  mov     rdi, [r11+20h]
0x1800257f8  mov     rsp, r11
0x1800257fb  pop     rbp
0x1800257fc  retn
```
