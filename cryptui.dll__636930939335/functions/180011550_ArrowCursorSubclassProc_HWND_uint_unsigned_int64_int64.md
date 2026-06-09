# ArrowCursorSubclassProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180011550`
- end: `0x1800116f2`
- name: `?ArrowCursorSubclassProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `418`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180011550`
- `0x180011c7c`

## import_xrefs

- `USER32!GetParent` at `0x180011629`
- `USER32!GetParent` at `0x180011643`
- `USER32!GetParent` at `0x18001165d`
- `USER32!GetParent` at `0x18001167f`
- `USER32!GetParent` at `0x180011688`
- `USER32!GetParent` at `0x180011629`
- `USER32!GetParent` at `0x180011643`
- `USER32!GetParent` at `0x18001165d`
- `USER32!GetParent` at `0x18001167f`
- `USER32!GetParent` at `0x180011688`
- `USER32!CallWindowProcA` at `0x1800115f2`
- `USER32!CallWindowProcA` at `0x1800116e7`
- `USER32!CallWindowProcA` at `0x1800115f2`
- `USER32!CallWindowProcA` at `0x1800116e7`
- `USER32!LoadCursorA` at `0x1800115c4`
- `USER32!LoadCursorA` at `0x1800115c4`
- `USER32!GetFocus` at `0x1800115f8`
- `USER32!GetFocus` at `0x1800115f8`
- `USER32!GetNextDlgTabItem` at `0x18001166c`
- `USER32!GetNextDlgTabItem` at `0x18001166c`
- `USER32!InvalidateRect` at `0x180011615`
- `USER32!InvalidateRect` at `0x180011615`
- `USER32!GetWindowLongPtrA` at `0x18001156b`
- `USER32!GetWindowLongPtrA` at `0x18001156b`
- `USER32!SetFocus` at `0x18001169d`
- `USER32!SetFocus` at `0x18001169d`
- `USER32!GetDlgItem` at `0x180011637`
- `USER32!GetDlgItem` at `0x180011651`
- `USER32!GetDlgItem` at `0x180011694`
- `USER32!GetDlgItem` at `0x180011637`
- `USER32!GetDlgItem` at `0x180011651`
- `USER32!GetDlgItem` at `0x180011694`
- `USER32!UpdateWindow` at `0x18001161e`
- `USER32!UpdateWindow` at `0x18001161e`
- `USER32!SetCursor` at `0x1800115cd`
- `USER32!SetCursor` at `0x1800115cd`

## pseudocode

```c
LRESULT __fastcall ArrowCursorSubclassProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  LRESULT (__stdcall *WindowLongPtrA)(HWND, UINT, WPARAM, LPARAM); // rcx
  bool v9; // zf
  HCURSOR CursorA; // rax
  HWND Parent; // rax
  HWND DlgItem; // rbx
  HWND v14; // rax
  HWND v15; // rsi
  HWND v16; // rax
  HWND NextDlgTabItem; // rax
  HWND v18; // rax
  HWND v19; // rax

  WindowLongPtrA = (LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM))GetWindowLongPtrA(hWnd, -21);
  if ( Msg > 0x201 )
  {
    if ( Msg == 515 || Msg == 518 || Msg == 519 || Msg == 520 )
      return 1;
    v9 = Msg == 521;
    goto LABEL_24;
  }
  switch ( Msg )
  {
    case 0x201u:
      return 1;
    case 7u:
      Parent = GetParent(hWnd);
      DlgItem = GetDlgItem(Parent, 105);
      v14 = GetParent(hWnd);
      v15 = GetDlgItem(v14, 106);
      v16 = GetParent(hWnd);
      NextDlgTabItem = GetNextDlgTabItem(v16, hWnd, 0);
      if ( NextDlgTabItem == DlgItem && hWnd == v15 )
      {
        v18 = GetParent(hWnd);
        v19 = GetParent(v18);
        NextDlgTabItem = GetDlgItem(v19, 1);
      }
      SetFocus(NextDlgTabItem);
      return 1;
    case 8u:
      InvalidateRect(hWnd, 0, 1);
      UpdateWindow(hWnd);
      return 1;
    case 0xFu:
      CallWindowProcA(WindowLongPtrA, hWnd, 0xFu, wParam, lParam);
      if ( hWnd == GetFocus() )
        DrawFocusRectangle(hWnd);
      return 1;
    case 0x20u:
      CursorA = LoadCursorA(0, (LPCSTR)0x7F00);
      SetCursor(CursorA);
      return 1;
    case 0xB1u:
      return 1;
    case 0x102u:
      v9 = wParam == 32;
LABEL_24:
      if ( !v9 )
        return CallWindowProcA(WindowLongPtrA, hWnd, Msg, wParam, lParam);
      return 1;
  }
  return CallWindowProcA(WindowLongPtrA, hWnd, Msg, wParam, lParam);
}

```

## disassembly

```asm
0x180011550  push    rbx
0x180011552  push    rbp
0x180011553  push    rsi
0x180011554  push    rdi
0x180011555  push    r14
0x180011557  sub     rsp, 30h
0x18001155b  mov     ebx, edx
0x18001155d  mov     rbp, r9
0x180011560  mov     edx, 0FFFFFFEBh; nIndex
0x180011565  mov     rsi, r8
0x180011568  mov     rdi, rcx
0x18001156b  call    cs:__imp_GetWindowLongPtrA
0x180011571  mov     rcx, rax; lpPrevWndFunc
0x180011574  mov     r14d, 1
0x18001157a  mov     eax, 201h
0x18001157f  cmp     ebx, eax
0x180011581  ja      loc_1800116A8
0x180011587  jz      short loc_1800115D3
0x180011589  mov     edx, ebx
0x18001158b  sub     edx, 7
0x18001158e  jz      loc_180011626
0x180011594  sub     edx, r14d
0x180011597  jz      short loc_18001160D
0x180011599  sub     edx, 7
0x18001159c  jz      short loc_1800115E1
0x18001159e  sub     edx, 11h
0x1800115a1  jz      short loc_1800115BD
0x1800115a3  sub     edx, 91h
0x1800115a9  jz      short loc_1800115D3
0x1800115ab  cmp     edx, 51h ; 'Q'
0x1800115ae  jnz     loc_1800116D9
0x1800115b4  cmp     rsi, 20h ; ' '
0x1800115b8  jmp     loc_1800116D3
0x1800115bd  mov     edx, 7F00h; lpCursorName
0x1800115c2  xor     ecx, ecx; hInstance
0x1800115c4  call    cs:__imp_LoadCursorA
0x1800115ca  mov     rcx, rax; hCursor
0x1800115cd  call    cs:__imp_SetCursor
0x1800115d3  mov     rax, r14
0x1800115d6  add     rsp, 30h
0x1800115da  pop     r14
0x1800115dc  pop     rdi
0x1800115dd  pop     rsi
0x1800115de  pop     rbp
0x1800115df  pop     rbx
0x1800115e0  retn
0x1800115e1  mov     r9, rsi; wParam
0x1800115e4  mov     [rsp+58h+lParam], rbp; lParam
0x1800115e9  mov     r8d, 0Fh; Msg
0x1800115ef  mov     rdx, rdi; hWnd
0x1800115f2  call    cs:__imp_CallWindowProcA
0x1800115f8  call    cs:__imp_GetFocus
0x1800115fe  cmp     rdi, rax
0x180011601  jnz     short loc_1800115D3
0x180011603  mov     rcx, rdi; hWnd
0x180011606  call    DrawFocusRectangle
0x18001160b  jmp     short loc_1800115D3
0x18001160d  mov     r8d, r14d; bErase
0x180011610  xor     edx, edx; lpRect
0x180011612  mov     rcx, rdi; hWnd
0x180011615  call    cs:__imp_InvalidateRect
0x18001161b  mov     rcx, rdi; hWnd
0x18001161e  call    cs:__imp_UpdateWindow
0x180011624  jmp     short loc_1800115D3
0x180011626  mov     rcx, rdi; hWnd
0x180011629  call    cs:__imp_GetParent
0x18001162f  mov     rcx, rax; hDlg
0x180011632  mov     edx, 69h ; 'i'; nIDDlgItem
0x180011637  call    cs:__imp_GetDlgItem
0x18001163d  mov     rcx, rdi; hWnd
0x180011640  mov     rbx, rax
0x180011643  call    cs:__imp_GetParent
0x180011649  mov     rcx, rax; hDlg
0x18001164c  mov     edx, 6Ah ; 'j'; nIDDlgItem
0x180011651  call    cs:__imp_GetDlgItem
0x180011657  mov     rcx, rdi; hWnd
0x18001165a  mov     rsi, rax
0x18001165d  call    cs:__imp_GetParent
0x180011663  xor     r8d, r8d; bPrevious
0x180011666  mov     rdx, rdi; hCtl
0x180011669  mov     rcx, rax; hDlg
0x18001166c  call    cs:__imp_GetNextDlgTabItem
0x180011672  cmp     rax, rbx
0x180011675  jnz     short loc_18001169A
0x180011677  cmp     rdi, rsi
0x18001167a  jnz     short loc_18001169A
0x18001167c  mov     rcx, rdi; hWnd
0x18001167f  call    cs:__imp_GetParent
0x180011685  mov     rcx, rax; hWnd
0x180011688  call    cs:__imp_GetParent
0x18001168e  mov     rcx, rax; hDlg
0x180011691  mov     edx, r14d; nIDDlgItem
0x180011694  call    cs:__imp_GetDlgItem
0x18001169a  mov     rcx, rax; hWnd
0x18001169d  call    cs:__imp_SetFocus
0x1800116a3  jmp     loc_1800115D3
0x1800116a8  mov     eax, ebx
0x1800116aa  sub     eax, 203h
0x1800116af  jz      loc_1800115D3
0x1800116b5  sub     eax, 3
0x1800116b8  jz      loc_1800115D3
0x1800116be  sub     eax, r14d
0x1800116c1  jz      loc_1800115D3
0x1800116c7  sub     eax, r14d
0x1800116ca  jz      loc_1800115D3
0x1800116d0  cmp     eax, r14d
0x1800116d3  jz      loc_1800115D3
0x1800116d9  mov     r9, rsi; wParam
0x1800116dc  mov     [rsp+58h+lParam], rbp; lParam
0x1800116e1  mov     r8d, ebx; Msg
0x1800116e4  mov     rdx, rdi; hWnd
0x1800116e7  call    cs:__imp_CallWindowProcA
0x1800116ed  jmp     loc_1800115D6
```
