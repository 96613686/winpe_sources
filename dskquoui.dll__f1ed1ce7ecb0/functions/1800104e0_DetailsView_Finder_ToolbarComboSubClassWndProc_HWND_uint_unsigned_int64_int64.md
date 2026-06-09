# DetailsView::Finder::ToolbarComboSubClassWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1800104e0`
- end: `0x180010583`
- name: `?ToolbarComboSubClassWndProc@Finder@DetailsView@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `163`
- prototype: `__int64 __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800104e0`
- `0x18001058c`

## import_xrefs

- `USER32!GetParent` at `0x18001051b`
- `USER32!GetParent` at `0x180010524`
- `USER32!GetParent` at `0x18001052d`
- `USER32!GetParent` at `0x180010543`
- `USER32!GetParent` at `0x18001051b`
- `USER32!GetParent` at `0x180010524`
- `USER32!GetParent` at `0x18001052d`
- `USER32!GetParent` at `0x180010543`
- `USER32!GetWindowLongPtrW` at `0x1800104fb`
- `USER32!GetWindowLongPtrW` at `0x1800104fb`
- `USER32!SetFocus` at `0x180010536`
- `USER32!SetFocus` at `0x180010536`
- `USER32!CallWindowProcW` at `0x180010572`
- `USER32!CallWindowProcW` at `0x180010572`

## pseudocode

```c
LRESULT __fastcall DetailsView::Finder::ToolbarComboSubClassWndProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  LONG_PTR WindowLongPtrW; // rax
  DetailsView::Finder *v9; // rsi
  HWND v10; // rcx
  HWND v11; // rax
  HWND Parent; // rbx
  int v14; // eax

  WindowLongPtrW = GetWindowLongPtrW(hWnd, -21);
  v9 = (DetailsView::Finder *)WindowLongPtrW;
  if ( Msg == 258 )
  {
    if ( wParam == 13 )
    {
      Parent = GetParent(hWnd);
      v14 = DetailsView::Finder::UserNameEntered(v9, Parent);
      v10 = Parent;
      if ( !v14 )
        goto LABEL_6;
      goto LABEL_5;
    }
    if ( wParam == 27 )
    {
      v10 = GetParent(hWnd);
LABEL_5:
      v11 = GetParent(v10);
      v10 = GetParent(v11);
LABEL_6:
      SetFocus(v10);
      return 0;
    }
  }
  return CallWindowProcW(*(WNDPROC *)(WindowLongPtrW + 24), hWnd, Msg, wParam, lParam);
}

```

## disassembly

```asm
0x1800104e0  push    rbx
0x1800104e2  push    rbp
0x1800104e3  push    rsi
0x1800104e4  push    rdi
0x1800104e5  push    r14
0x1800104e7  sub     rsp, 30h
0x1800104eb  mov     ebp, edx
0x1800104ed  mov     r14, r9
0x1800104f0  mov     edx, 0FFFFFFEBh; nIndex
0x1800104f5  mov     rbx, r8
0x1800104f8  mov     rdi, rcx
0x1800104fb  call    cs:__imp_GetWindowLongPtrW
0x180010501  mov     rsi, rax
0x180010504  cmp     ebp, 102h
0x18001050a  jnz     short loc_180010560
0x18001050c  cmp     rbx, 0Dh
0x180010510  jz      short loc_180010540
0x180010512  cmp     rbx, 1Bh
0x180010516  jnz     short loc_180010560
0x180010518  mov     rcx, rdi; hWnd
0x18001051b  call    cs:__imp_GetParent
0x180010521  mov     rcx, rax; hWnd
0x180010524  call    cs:__imp_GetParent
0x18001052a  mov     rcx, rax; hWnd
0x18001052d  call    cs:__imp_GetParent
0x180010533  mov     rcx, rax; hWnd
0x180010536  call    cs:__imp_SetFocus
0x18001053c  xor     eax, eax
0x18001053e  jmp     short loc_180010578
0x180010540  mov     rcx, rdi; hWnd
0x180010543  call    cs:__imp_GetParent
0x180010549  mov     rdx, rax; HWND
0x18001054c  mov     rcx, rsi; this
0x18001054f  mov     rbx, rax
0x180010552  call    ?UserNameEntered@Finder@DetailsView@@AEAAHPEAUHWND__@@@Z; DetailsView::Finder::UserNameEntered(HWND__ *)
0x180010557  mov     rcx, rbx
0x18001055a  test    eax, eax
0x18001055c  jz      short loc_180010536
0x18001055e  jmp     short loc_180010524
0x180010560  mov     rcx, [rax+18h]; lpPrevWndFunc
0x180010564  mov     r9, rbx; wParam
0x180010567  mov     r8d, ebp; Msg
0x18001056a  mov     [rsp+58h+lParam], r14; lParam
0x18001056f  mov     rdx, rdi; hWnd
0x180010572  call    cs:__imp_CallWindowProcW
0x180010578  add     rsp, 30h
0x18001057c  pop     r14
0x18001057e  pop     rdi
0x18001057f  pop     rsi
0x180010580  pop     rbp
0x180010581  pop     rbx
0x180010582  retn
```
