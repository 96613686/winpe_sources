# LinkSubclassProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180012250`
- end: `0x180012560`
- name: `?LinkSubclassProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `784`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180011c7c`
- `0x180012250`
- `0x18001f020`
- `0x18003e5c0`

## import_xrefs

- `USER32!GetParent` at `0x1800122f6`
- `USER32!GetParent` at `0x1800122ff`
- `USER32!GetParent` at `0x1800123a4`
- `USER32!GetParent` at `0x1800123c9`
- `USER32!GetParent` at `0x1800123eb`
- `USER32!GetParent` at `0x180012420`
- `USER32!GetParent` at `0x18001252b`
- `USER32!GetParent` at `0x1800122f6`
- `USER32!GetParent` at `0x1800122ff`
- `USER32!GetParent` at `0x1800123a4`
- `USER32!GetParent` at `0x1800123c9`
- `USER32!GetParent` at `0x1800123eb`
- `USER32!GetParent` at `0x180012420`
- `USER32!GetParent` at `0x18001252b`
- `USER32!CallWindowProcA` at `0x18001237f`
- `USER32!CallWindowProcA` at `0x1800124fd`
- `USER32!CallWindowProcA` at `0x18001237f`
- `USER32!CallWindowProcA` at `0x1800124fd`
- `USER32!LoadCursorA` at `0x180012356`
- `USER32!LoadCursorA` at `0x1800124aa`
- `USER32!LoadCursorA` at `0x180012356`
- `USER32!LoadCursorA` at `0x1800124aa`
- `USER32!GetFocus` at `0x180012385`
- `USER32!GetFocus` at `0x18001240e`
- `USER32!GetFocus` at `0x180012385`
- `USER32!GetFocus` at `0x18001240e`
- `USER32!GetNextDlgTabItem` at `0x1800123fa`
- `USER32!GetNextDlgTabItem` at `0x1800123fa`
- `USER32!InvalidateRect` at `0x1800123b2`
- `USER32!InvalidateRect` at `0x18001242e`
- `USER32!InvalidateRect` at `0x1800123b2`
- `USER32!InvalidateRect` at `0x18001242e`
- `USER32!SendMessageA` at `0x180012313`
- `USER32!SendMessageA` at `0x18001246e`
- `USER32!SendMessageA` at `0x180012313`
- `USER32!SendMessageA` at `0x18001246e`
- `USER32!GetWindowLongPtrA` at `0x180012284`
- `USER32!GetWindowLongPtrA` at `0x180012348`
- `USER32!GetWindowLongPtrA` at `0x180012284`
- `USER32!GetWindowLongPtrA` at `0x180012348`
- `USER32!SetFocus` at `0x180012403`
- `USER32!SetFocus` at `0x18001250e`
- `USER32!SetFocus` at `0x180012403`
- `USER32!SetFocus` at `0x18001250e`
- `USER32!GetDlgItem` at `0x1800123d7`
- `USER32!GetDlgItem` at `0x1800123d7`
- `USER32!ReleaseCapture` at `0x1800124b9`
- `USER32!ReleaseCapture` at `0x1800124b9`
- `USER32!UpdateWindow` at `0x1800123bb`
- `USER32!UpdateWindow` at `0x180012437`
- `USER32!UpdateWindow` at `0x1800123bb`
- `USER32!UpdateWindow` at `0x180012437`
- `USER32!GetClientRect` at `0x18001247b`
- `USER32!GetClientRect` at `0x18001247b`
- `USER32!SetCursor` at `0x18001235f`
- `USER32!SetCursor` at `0x1800124b3`
- `USER32!SetCursor` at `0x18001235f`
- `USER32!SetCursor` at `0x1800124b3`
- `USER32!SetCapture` at `0x180012327`
- `USER32!SetCapture` at `0x180012327`

## pseudocode

```c
LRESULT __fastcall LinkSubclassProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  LONG_PTR WindowLongPtrA; // rsi
  HWND v9; // rax
  HWND v10; // rax
  __int64 v11; // rdx
  HINSTANCE v12; // rcx
  HCURSOR v13; // rax
  HWND v14; // rax
  HWND Parent; // rax
  HWND v16; // rax
  HWND NextDlgTabItem; // rax
  HWND v18; // rax
  HWND v19; // rcx
  HCURSOR CursorA; // rax
  UINT v22; // ebx
  const WCHAR *v23; // rdi
  HWND v24; // rax
  LPARAM v25[4]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v26; // [rsp+50h] [rbp-30h]
  struct tagRECT Rect; // [rsp+60h] [rbp-20h] BYREF

  WindowLongPtrA = GetWindowLongPtrA(hWnd, -21);
  if ( Msg > 0x200 )
  {
    if ( Msg != 513 )
    {
      if ( Msg == 515 || Msg == 518 || Msg == 519 || Msg - 520 < 2 )
        return 1;
      return CallWindowProcA(*(WNDPROC *)(WindowLongPtrA + 8), hWnd, Msg, wParam, lParam);
    }
    goto LABEL_35;
  }
  switch ( Msg )
  {
    case 0x200u:
      v19 = *(HWND *)(WindowLongPtrA + 24);
      v25[1] = 512;
      v25[0] = (LPARAM)hWnd;
      v25[2] = wParam;
      Rect = 0;
      v25[3] = lParam;
      v26 = 0;
      SendMessageA(v19, 0x407u, 0, (LPARAM)v25);
      GetClientRect(hWnd, &Rect);
      if ( (unsigned __int16)lParam > Rect.right - Rect.left || WORD1(lParam) > Rect.bottom - Rect.top )
      {
        CursorA = LoadCursorA(0, (LPCSTR)0x7F00);
        SetCursor(CursorA);
        ReleaseCapture();
        *(_DWORD *)(WindowLongPtrA + 40) = 0;
      }
      return 1;
    case 7u:
      Parent = GetParent(hWnd);
      if ( hWnd == GetDlgItem(Parent, 118) && *(_DWORD *)(WindowLongPtrA + 48) )
      {
        v16 = GetParent(hWnd);
        NextDlgTabItem = GetNextDlgTabItem(v16, hWnd, 0);
        SetFocus(NextDlgTabItem);
        return 1;
      }
      if ( hWnd != GetFocus() )
        return CallWindowProcA(*(WNDPROC *)(WindowLongPtrA + 8), hWnd, Msg, wParam, lParam);
      v18 = GetParent(hWnd);
      InvalidateRect(v18, 0, 0);
      UpdateWindow(hWnd);
      goto LABEL_16;
    case 8u:
      v14 = GetParent(hWnd);
      InvalidateRect(v14, 0, 0);
      UpdateWindow(hWnd);
LABEL_15:
      v11 = 32512;
      v12 = 0;
LABEL_17:
      v13 = LoadCursorA(v12, (LPCSTR)v11);
      SetCursor(v13);
      return 1;
    case 0xFu:
      CallWindowProcA(*(WNDPROC *)(WindowLongPtrA + 8), hWnd, 0xFu, wParam, lParam);
      if ( hWnd == GetFocus() )
        DrawFocusRectangle(hWnd);
      return 1;
    case 0x20u:
      if ( !*(_DWORD *)(WindowLongPtrA + 40) )
      {
        SetCapture(hWnd);
        *(_DWORD *)(WindowLongPtrA + 40) = 1;
      }
      if ( *(_DWORD *)(WindowLongPtrA + 48) )
        goto LABEL_15;
LABEL_16:
      v12 = (HINSTANCE)GetWindowLongPtrA(hWnd, -6);
      v11 = 104;
      goto LABEL_17;
  }
  if ( Msg != 177 )
  {
    if ( Msg != 258 )
      return CallWindowProcA(*(WNDPROC *)(WindowLongPtrA + 8), hWnd, Msg, wParam, lParam);
    if ( wParam != 32 )
    {
      if ( wParam == 27 )
      {
        v9 = GetParent(hWnd);
        v10 = GetParent(v9);
        SendMessageA(v10, 0x10u, 0, 0);
        return 1;
      }
      return CallWindowProcA(*(WNDPROC *)(WindowLongPtrA + 8), hWnd, Msg, wParam, lParam);
    }
LABEL_35:
    if ( !*(_DWORD *)(WindowLongPtrA + 48) )
    {
      SetFocus(hWnd);
      if ( *(_DWORD *)(WindowLongPtrA + 16) == 105 || *(_DWORD *)(WindowLongPtrA + 16) == 106 )
      {
        v22 = *(_DWORD *)(WindowLongPtrA + 44);
        v23 = *(const WCHAR **)(WindowLongPtrA + 32);
        v24 = GetParent(*(HWND *)WindowLongPtrA);
        CryptuiGoLink(v24, v23, v22);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180012250  push    rbp
0x180012252  push    rbx
0x180012253  push    rsi
0x180012254  push    rdi
0x180012255  push    r12
0x180012257  push    r14
0x180012259  push    r15
0x18001225b  mov     rbp, rsp
0x18001225e  sub     rsp, 80h
0x180012265  mov     rax, cs:__security_cookie
0x18001226c  xor     rax, rsp
0x18001226f  mov     [rbp+var_10], rax
0x180012273  mov     r14d, edx
0x180012276  mov     rdi, r9
0x180012279  mov     edx, 0FFFFFFEBh; nIndex
0x18001227e  mov     r15, r8
0x180012281  mov     rbx, rcx
0x180012284  call    cs:__imp_GetWindowLongPtrA
0x18001228a  mov     rsi, rax
0x18001228d  mov     r12d, 1
0x180012293  mov     eax, 200h
0x180012298  cmp     r14d, eax
0x18001229b  ja      loc_1800124C8
0x1800122a1  jz      loc_180012442
0x1800122a7  mov     ecx, r14d
0x1800122aa  sub     ecx, 7
0x1800122ad  jz      loc_1800123C6
0x1800122b3  sub     ecx, r12d
0x1800122b6  jz      loc_1800123A1
0x1800122bc  sub     ecx, 7
0x1800122bf  jz      loc_18001236A
0x1800122c5  sub     ecx, 11h
0x1800122c8  jz      short loc_18001231E
0x1800122ca  sub     ecx, 91h
0x1800122d0  jz      loc_18001253F
0x1800122d6  cmp     ecx, 51h ; 'Q'
0x1800122d9  jnz     loc_1800124EB
0x1800122df  cmp     r15, 20h ; ' '
0x1800122e3  jz      loc_180012505
0x1800122e9  cmp     r15, 1Bh
0x1800122ed  jnz     loc_1800124EB
0x1800122f3  mov     rcx, rbx; hWnd
0x1800122f6  call    cs:__imp_GetParent
0x1800122fc  mov     rcx, rax; hWnd
0x1800122ff  call    cs:__imp_GetParent
0x180012305  xor     r9d, r9d; lParam
0x180012308  lea     edx, [r12+0Fh]; Msg
0x18001230d  mov     rcx, rax; hWnd
0x180012310  xor     r8d, r8d; wParam
0x180012313  call    cs:__imp_SendMessageA
0x180012319  jmp     loc_18001253F
0x18001231e  cmp     dword ptr [rsi+28h], 0
0x180012322  jnz     short loc_180012331
0x180012324  mov     rcx, rbx; hWnd
0x180012327  call    cs:__imp_SetCapture
0x18001232d  mov     [rsi+28h], r12d
0x180012331  cmp     dword ptr [rsi+30h], 0
0x180012335  jz      short loc_180012340
0x180012337  mov     edx, 7F00h
0x18001233c  xor     ecx, ecx
0x18001233e  jmp     short loc_180012356
0x180012340  mov     edx, 0FFFFFFFAh; nIndex
0x180012345  mov     rcx, rbx; hWnd
0x180012348  call    cs:__imp_GetWindowLongPtrA
0x18001234e  mov     rcx, rax; hInstance
0x180012351  mov     edx, 68h ; 'h'; lpCursorName
0x180012356  call    cs:__imp_LoadCursorA
0x18001235c  mov     rcx, rax; hCursor
0x18001235f  call    cs:__imp_SetCursor
0x180012365  jmp     loc_18001253F
0x18001236a  mov     rcx, [rsi+8]; lpPrevWndFunc
0x18001236e  mov     r9, r15; wParam
0x180012371  mov     r8d, 0Fh; Msg
0x180012377  mov     [rsp+80h+lParam], rdi; lParam
0x18001237c  mov     rdx, rbx; hWnd
0x18001237f  call    cs:__imp_CallWindowProcA
0x180012385  call    cs:__imp_GetFocus
0x18001238b  cmp     rbx, rax
0x18001238e  jnz     loc_18001253F
0x180012394  mov     rcx, rbx; hWnd
0x180012397  call    DrawFocusRectangle
0x18001239c  jmp     loc_18001253F
0x1800123a1  mov     rcx, rbx; hWnd
0x1800123a4  call    cs:__imp_GetParent
0x1800123aa  xor     r8d, r8d; bErase
0x1800123ad  xor     edx, edx; lpRect
0x1800123af  mov     rcx, rax; hWnd
0x1800123b2  call    cs:__imp_InvalidateRect
0x1800123b8  mov     rcx, rbx; hWnd
0x1800123bb  call    cs:__imp_UpdateWindow
0x1800123c1  jmp     loc_180012337
0x1800123c6  mov     rcx, rbx; hWnd
0x1800123c9  call    cs:__imp_GetParent
0x1800123cf  mov     rcx, rax; hDlg
0x1800123d2  mov     edx, 76h ; 'v'; nIDDlgItem
0x1800123d7  call    cs:__imp_GetDlgItem
0x1800123dd  cmp     rbx, rax
0x1800123e0  jnz     short loc_18001240E
0x1800123e2  cmp     dword ptr [rsi+30h], 0
0x1800123e6  jz      short loc_18001240E
0x1800123e8  mov     rcx, rbx; hWnd
0x1800123eb  call    cs:__imp_GetParent
0x1800123f1  xor     r8d, r8d; bPrevious
0x1800123f4  mov     rdx, rbx; hCtl
0x1800123f7  mov     rcx, rax; hDlg
0x1800123fa  call    cs:__imp_GetNextDlgTabItem
0x180012400  mov     rcx, rax; hWnd
0x180012403  call    cs:__imp_SetFocus
0x180012409  jmp     loc_18001253F
0x18001240e  call    cs:__imp_GetFocus
0x180012414  cmp     rbx, rax
0x180012417  jnz     loc_1800124EB
0x18001241d  mov     rcx, rbx; hWnd
0x180012420  call    cs:__imp_GetParent
0x180012426  xor     r8d, r8d; bErase
0x180012429  xor     edx, edx; lpRect
0x18001242b  mov     rcx, rax; hWnd
0x18001242e  call    cs:__imp_InvalidateRect
0x180012434  mov     rcx, rbx; hWnd
0x180012437  call    cs:__imp_UpdateWindow
0x18001243d  jmp     loc_180012340
0x180012442  mov     rcx, [rsi+18h]; hWnd
0x180012446  lea     r9, [rbp+var_50]; lParam
0x18001244a  xorps   xmm0, xmm0
0x18001244d  mov     [rbp+var_48], rax
0x180012451  xor     r8d, r8d; wParam
0x180012454  mov     [rbp+var_50], rbx
0x180012458  mov     edx, 407h; Msg
0x18001245d  mov     [rbp+var_40], r15
0x180012461  movups  xmmword ptr [rbp+Rect.left], xmm0
0x180012465  mov     [rbp+var_38], rdi
0x180012469  movdqu  [rbp+var_30], xmm0
0x18001246e  call    cs:__imp_SendMessageA
0x180012474  lea     rdx, [rbp+Rect]; lpRect
0x180012478  mov     rcx, rbx; hWnd
0x18001247b  call    cs:__imp_GetClientRect
0x180012481  mov     ecx, [rbp+Rect.right]
0x180012484  sub     ecx, [rbp+Rect.left]
0x180012487  movzx   eax, di
0x18001248a  cmp     eax, ecx
0x18001248c  jg      short loc_1800124A3
0x18001248e  mov     eax, [rbp+Rect.bottom]
0x180012491  sub     eax, [rbp+Rect.top]
0x180012494  shr     rdi, 10h
0x180012498  movzx   ecx, di
0x18001249b  cmp     ecx, eax
0x18001249d  jle     loc_18001253F
0x1800124a3  mov     edx, 7F00h; lpCursorName
0x1800124a8  xor     ecx, ecx; hInstance
0x1800124aa  call    cs:__imp_LoadCursorA
0x1800124b0  mov     rcx, rax; hCursor
0x1800124b3  call    cs:__imp_SetCursor
0x1800124b9  call    cs:__imp_ReleaseCapture
0x1800124bf  mov     dword ptr [rsi+28h], 0
0x1800124c6  jmp     short loc_18001253F
0x1800124c8  mov     eax, r14d
0x1800124cb  sub     eax, 201h
0x1800124d0  jz      short loc_180012505
0x1800124d2  sub     eax, 2
0x1800124d5  jz      short loc_18001253F
0x1800124d7  sub     eax, 3
0x1800124da  jz      short loc_18001253F
0x1800124dc  sub     eax, r12d
0x1800124df  jz      short loc_18001253F
0x1800124e1  sub     eax, r12d
0x1800124e4  jz      short loc_18001253F
0x1800124e6  cmp     eax, r12d
0x1800124e9  jz      short loc_18001253F
0x1800124eb  mov     rcx, [rsi+8]; lpPrevWndFunc
0x1800124ef  mov     r9, r15; wParam
0x1800124f2  mov     r8d, r14d; Msg
0x1800124f5  mov     [rsp+80h+lParam], rdi; lParam
0x1800124fa  mov     rdx, rbx; hWnd
0x1800124fd  call    cs:__imp_CallWindowProcA
0x180012503  jmp     short loc_180012542
0x180012505  cmp     dword ptr [rsi+30h], 0
0x180012509  jnz     short loc_18001253F
0x18001250b  mov     rcx, rbx; hWnd
0x18001250e  call    cs:__imp_SetFocus
0x180012514  mov     ecx, [rsi+10h]
0x180012517  sub     ecx, 69h ; 'i'
0x18001251a  jz      short loc_180012521
0x18001251c  cmp     ecx, r12d
0x18001251f  jnz     short loc_18001253F
0x180012521  mov     rcx, [rsi]; hWnd
0x180012524  mov     ebx, [rsi+2Ch]
0x180012527  mov     rdi, [rsi+20h]
0x18001252b  call    cs:__imp_GetParent
0x180012531  mov     r8d, ebx; wRemoveMsg
0x180012534  mov     rdx, rdi; lpFile
0x180012537  mov     rcx, rax; hwnd
0x18001253a  call    ?CryptuiGoLink@@YAXPEAUHWND__@@PEAGH@Z; CryptuiGoLink(HWND__ *,ushort *,int)
0x18001253f  mov     rax, r12
0x180012542  mov     rcx, [rbp+var_10]
0x180012546  xor     rcx, rsp; StackCookie
0x180012549  call    __security_check_cookie
0x18001254e  add     rsp, 80h
0x180012555  pop     r15
0x180012557  pop     r14
0x180012559  pop     r12
0x18001255b  pop     rdi
0x18001255c  pop     rsi
0x18001255d  pop     rbx
0x18001255e  pop     rbp
0x18001255f  retn
```
