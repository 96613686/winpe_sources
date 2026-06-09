# ResizeWindow(CHHWinType *,bool)

- ea: `0x18007236c`
- end: `0x1800725e6`
- name: `?ResizeWindow@@YAXPEAVCHHWinType@@_N@Z`
- size: `634`
- prototype: `void __fastcall(struct CHHWinType *, bool)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180050158`
- `0x180058874`
- `0x18006fe30`
- `0x180070230`

## callees

- `0x180018b10`
- `0x18004f8dc`
- `0x180058818`
- `0x18005f374`
- `0x18007236c`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `USER32!MoveWindow` at `0x1800723d2`
- `USER32!MoveWindow` at `0x180072443`
- `USER32!MoveWindow` at `0x18007258e`
- `USER32!MoveWindow` at `0x1800723d2`
- `USER32!MoveWindow` at `0x180072443`
- `USER32!MoveWindow` at `0x18007258e`
- `USER32!GetClientRect` at `0x180072474`
- `USER32!GetClientRect` at `0x180072482`
- `USER32!GetClientRect` at `0x180072493`
- `USER32!GetClientRect` at `0x180072474`
- `USER32!GetClientRect` at `0x180072482`
- `USER32!GetClientRect` at `0x180072493`
- `USER32!SetWindowPos` at `0x1800724d8`
- `USER32!SetWindowPos` at `0x180072522`
- `USER32!SetWindowPos` at `0x1800724d8`
- `USER32!SetWindowPos` at `0x180072522`
- `USER32!InvalidateRect` at `0x180072534`
- `USER32!InvalidateRect` at `0x180072546`
- `USER32!InvalidateRect` at `0x180072534`
- `USER32!InvalidateRect` at `0x180072546`

## pseudocode

```c
void __fastcall ResizeWindow(struct CHHWinType *a1, char a2)
{
  CContainer *v3; // rcx
  HWND v4; // rcx
  HWND v5; // rcx
  int v6; // ebx
  HWND *v7; // rbx
  CTabControl *v8; // rcx
  __int64 v9; // rcx
  CSizeBar *v10; // rcx
  struct tagRECT Rect; // [rsp+40h] [rbp-40h] BYREF
  struct tagRECT v12; // [rsp+50h] [rbp-30h] BYREF
  struct tagRECT v13; // [rsp+60h] [rbp-20h] BYREF

  if ( a1 )
  {
    if ( *((_QWORD *)a1 + 13) )
    {
      if ( a2 )
        CHHWinType::CalcHtmlPaneRect(a1);
      MoveWindow(
        *((HWND *)a1 + 13),
        *((_DWORD *)a1 + 29),
        *((_DWORD *)a1 + 30),
        *((_DWORD *)a1 + 31) - *((_DWORD *)a1 + 29),
        *((_DWORD *)a1 + 32) - *((_DWORD *)a1 + 30),
        1);
      v3 = (CContainer *)*((_QWORD *)a1 + 75);
      if ( v3 )
        CContainer::SizeIt(v3, *((_DWORD *)a1 + 31) - *((_DWORD *)a1 + 29), *((_DWORD *)a1 + 32) - *((_DWORD *)a1 + 30));
    }
    v4 = (HWND)*((_QWORD *)a1 + 12);
    if ( v4 && !*((_DWORD *)a1 + 43) )
    {
      MoveWindow(
        v4,
        *((_DWORD *)a1 + 128),
        *((_DWORD *)a1 + 129),
        *((_DWORD *)a1 + 130) - *((_DWORD *)a1 + 128),
        *((_DWORD *)a1 + 131) - *((_DWORD *)a1 + 129),
        1);
      if ( *((_QWORD *)a1 + 80) )
      {
        v5 = (HWND)*((_QWORD *)a1 + 81);
        Rect = 0;
        v13 = 0;
        v12 = 0;
        GetClientRect(v5, &Rect);
        GetClientRect(*((HWND *)a1 + 11), &v13);
        GetClientRect(*((HWND *)a1 + 80), &v12);
        v6 = v13.bottom + 5;
        SetWindowPos(
          *((HWND *)a1 + 81),
          0,
          *((_DWORD *)a1 + 128) + 6,
          v13.bottom + 5,
          *((_DWORD *)a1 + 130) - *((_DWORD *)a1 + 128) - 8,
          Rect.bottom - Rect.top,
          4u);
        SetWindowPos(
          *((HWND *)a1 + 80),
          0,
          *((_DWORD *)a1 + 128) + 6,
          v6 - Rect.top + Rect.bottom + 2,
          *((_DWORD *)a1 + 130) - *((_DWORD *)a1 + 128) - 8,
          v12.bottom - v12.top,
          4u);
        InvalidateRect(*((HWND *)a1 + 81), 0, 0);
        InvalidateRect(*((HWND *)a1 + 80), 0, 0);
      }
      v7 = (HWND *)*((_QWORD *)a1 + 74);
      if ( v7 )
      {
        v8 = (CTabControl *)*((_QWORD *)a1 + 74);
        Rect = 0;
        CTabControl::CalcSize(v8, &Rect);
        MoveWindow(*v7, Rect.left, Rect.top, Rect.right - Rect.left, Rect.bottom - Rect.top, 1);
      }
      v9 = *((_QWORD *)a1 + *((int *)a1 + 44) + 42);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
      v10 = (CSizeBar *)*((_QWORD *)a1 + 40);
      if ( v10 )
        CSizeBar::ResizeWindow(v10);
    }
  }
}

```

## disassembly

```asm
0x18007236c  test    rcx, rcx
0x18007236f  jz      locret_1800725E5
0x180072375  mov     [rsp-8+arg_8], rbx
0x18007237a  mov     [rsp-8+arg_10], rdi
0x18007237f  push    rbp
0x180072380  mov     rbp, rsp
0x180072383  sub     rsp, 80h
0x18007238a  mov     rax, cs:__security_cookie
0x180072391  xor     rax, rsp
0x180072394  mov     [rbp+var_10], rax
0x180072398  cmp     qword ptr [rcx+68h], 0
0x18007239d  mov     rdi, rcx
0x1800723a0  jz      short loc_1800723FA
0x1800723a2  test    dl, dl
0x1800723a4  jz      short loc_1800723AB
0x1800723a6  call    ?CalcHtmlPaneRect@CHHWinType@@QEAAXXZ; CHHWinType::CalcHtmlPaneRect(void)
0x1800723ab  mov     eax, [rdi+80h]
0x1800723b1  mov     r9d, [rdi+7Ch]
0x1800723b5  sub     eax, [rdi+78h]
0x1800723b8  mov     edx, [rdi+74h]; X
0x1800723bb  sub     r9d, edx; nWidth
0x1800723be  mov     r8d, [rdi+78h]; Y
0x1800723c2  mov     rcx, [rdi+68h]; hWnd
0x1800723c6  mov     [rsp+80h+bRepaint], 1; bRepaint
0x1800723ce  mov     [rsp+80h+nHeight], eax; nHeight
0x1800723d2  call    cs:__imp_MoveWindow
0x1800723d8  mov     rcx, [rdi+258h]; this
0x1800723df  test    rcx, rcx
0x1800723e2  jz      short loc_1800723FA
0x1800723e4  mov     r8d, [rdi+80h]
0x1800723eb  mov     edx, [rdi+7Ch]
0x1800723ee  sub     r8d, [rdi+78h]; int
0x1800723f2  sub     edx, [rdi+74h]; int
0x1800723f5  call    ?SizeIt@CContainer@@QEAAXHH@Z; CContainer::SizeIt(int,int)
0x1800723fa  mov     rcx, [rdi+60h]; hWnd
0x1800723fe  test    rcx, rcx
0x180072401  jz      loc_1800725C5
0x180072407  cmp     dword ptr [rdi+0ACh], 0
0x18007240e  jnz     loc_1800725C5
0x180072414  mov     eax, [rdi+20Ch]
0x18007241a  mov     r9d, [rdi+208h]
0x180072421  sub     eax, [rdi+204h]
0x180072427  mov     edx, [rdi+200h]; X
0x18007242d  sub     r9d, edx; nWidth
0x180072430  mov     r8d, [rdi+204h]; Y
0x180072437  mov     [rsp+80h+bRepaint], 1; bRepaint
0x18007243f  mov     [rsp+80h+nHeight], eax; nHeight
0x180072443  call    cs:__imp_MoveWindow
0x180072449  cmp     qword ptr [rdi+280h], 0
0x180072451  jz      loc_18007254C
0x180072457  mov     rcx, [rdi+288h]; hWnd
0x18007245e  lea     rdx, [rbp+Rect]; lpRect
0x180072462  xorps   xmm0, xmm0
0x180072465  xorps   xmm1, xmm1
0x180072468  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18007246c  movups  xmmword ptr [rbp+var_20.left], xmm1
0x180072470  movups  xmmword ptr [rbp+var_30.left], xmm0
0x180072474  call    cs:__imp_GetClientRect
0x18007247a  mov     rcx, [rdi+58h]; hWnd
0x18007247e  lea     rdx, [rbp+var_20]; lpRect
0x180072482  call    cs:__imp_GetClientRect
0x180072488  mov     rcx, [rdi+280h]; hWnd
0x18007248f  lea     rdx, [rbp+var_30]; lpRect
0x180072493  call    cs:__imp_GetClientRect
0x180072499  mov     ecx, [rbp+Rect.bottom]
0x18007249c  xor     edx, edx; hWndInsertAfter
0x18007249e  mov     r8d, [rdi+200h]
0x1800724a5  sub     ecx, [rbp+Rect.top]
0x1800724a8  mov     eax, [rdi+208h]
0x1800724ae  mov     ebx, [rbp+var_20.bottom]
0x1800724b1  sub     eax, r8d
0x1800724b4  mov     [rsp+80h+uFlags], 4; uFlags
0x1800724bc  sub     eax, 8
0x1800724bf  mov     [rsp+80h+bRepaint], ecx; cy
0x1800724c3  add     ebx, 5
0x1800724c6  mov     rcx, [rdi+288h]; hWnd
0x1800724cd  add     r8d, 6; X
0x1800724d1  mov     r9d, ebx; Y
0x1800724d4  mov     [rsp+80h+nHeight], eax; cx
0x1800724d8  call    cs:__imp_SetWindowPos
0x1800724de  mov     edx, [rbp+var_30.bottom]
0x1800724e1  mov     r8d, [rdi+200h]
0x1800724e8  sub     edx, [rbp+var_30.top]
0x1800724eb  mov     eax, [rdi+208h]
0x1800724f1  mov     r9d, [rbp+Rect.bottom]
0x1800724f5  sub     eax, r8d
0x1800724f8  sub     ebx, [rbp+Rect.top]
0x1800724fb  add     r9d, 2
0x1800724ff  mov     rcx, [rdi+280h]; hWnd
0x180072506  sub     eax, 8
0x180072509  mov     [rsp+80h+uFlags], 4; uFlags
0x180072511  add     r9d, ebx; Y
0x180072514  mov     [rsp+80h+bRepaint], edx; cy
0x180072518  add     r8d, 6; X
0x18007251c  xor     edx, edx; hWndInsertAfter
0x18007251e  mov     [rsp+80h+nHeight], eax; cx
0x180072522  call    cs:__imp_SetWindowPos
0x180072528  mov     rcx, [rdi+288h]; hWnd
0x18007252f  xor     r8d, r8d; bErase
0x180072532  xor     edx, edx; lpRect
0x180072534  call    cs:__imp_InvalidateRect
0x18007253a  mov     rcx, [rdi+280h]; hWnd
0x180072541  xor     r8d, r8d; bErase
0x180072544  xor     edx, edx; lpRect
0x180072546  call    cs:__imp_InvalidateRect
0x18007254c  mov     rbx, [rdi+250h]
0x180072553  test    rbx, rbx
0x180072556  jz      short loc_180072594
0x180072558  xorps   xmm0, xmm0
0x18007255b  lea     rdx, [rbp+Rect]; struct tagRECT *
0x18007255f  mov     rcx, rbx; this
0x180072562  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180072566  call    ?CalcSize@CTabControl@@IEAAXPEAUtagRECT@@@Z; CTabControl::CalcSize(tagRECT *)
0x18007256b  mov     eax, [rbp+Rect.bottom]
0x18007256e  mov     r8d, [rbp+Rect.top]; Y
0x180072572  sub     eax, r8d
0x180072575  mov     r9d, [rbp+Rect.right]
0x180072579  mov     edx, [rbp+Rect.left]; X
0x18007257c  sub     r9d, edx; nWidth
0x18007257f  mov     rcx, [rbx]; hWnd
0x180072582  mov     [rsp+80h+bRepaint], 1; bRepaint
0x18007258a  mov     [rsp+80h+nHeight], eax; nHeight
0x18007258e  call    cs:__imp_MoveWindow
0x180072594  movsxd  rax, dword ptr [rdi+0B0h]
0x18007259b  mov     rcx, [rdi+rax*8+150h]
0x1800725a3  test    rcx, rcx
0x1800725a6  jz      short loc_1800725B4
0x1800725a8  mov     rax, [rcx]
0x1800725ab  mov     rax, [rax+18h]
0x1800725af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725b4  mov     rcx, [rdi+140h]; this
0x1800725bb  test    rcx, rcx
0x1800725be  jz      short loc_1800725C5
0x1800725c0  call    ?ResizeWindow@CSizeBar@@QEAAXXZ; CSizeBar::ResizeWindow(void)
0x1800725c5  mov     rcx, [rbp+var_10]
0x1800725c9  xor     rcx, rsp; StackCookie
0x1800725cc  call    __security_check_cookie
0x1800725d1  lea     r11, [rsp+80h+var_s0]
0x1800725d9  mov     rbx, [r11+18h]
0x1800725dd  mov     rdi, [r11+20h]
0x1800725e1  mov     rsp, r11
0x1800725e4  pop     rbp
0x1800725e5  retn
```
