# ListView_OnEditLabel

- ea: `0x180075888`
- end: `0x180075a10`
- name: `ListView_OnEditLabel`
- size: `392`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180059f4c`
- `0x18005c0a0`

## callees

- `0x1800115f0`
- `0x180052cf8`
- `0x180053f50`
- `0x18005bcc0`
- `0x1800733e0`
- `0x1800736d4`
- `0x180075888`
- `0x180076674`
- `0x180076c20`

## import_xrefs

- `USER32!SendMessageW` at `0x18007592a`
- `USER32!SendMessageW` at `0x18007592a`
- `USER32!ShowWindow` at `0x18007595e`
- `USER32!ShowWindow` at `0x18007595e`
- `USER32!SetWindowLongPtrW` at `0x180075903`
- `USER32!SetWindowLongPtrW` at `0x180075903`
- `USER32!SetFocus` at `0x18007594a`
- `USER32!SetFocus` at `0x18007594a`
- `USER32!GetFocus` at `0x1800758c2`
- `USER32!GetFocus` at `0x1800758c2`
- `USER32!InvalidateRect` at `0x1800759d9`
- `USER32!InvalidateRect` at `0x1800759d9`
- `USER32!UpdateWindow` at `0x1800759e2`
- `USER32!UpdateWindow` at `0x1800759e2`

## pseudocode

```c
__int64 __fastcall ListView_OnEditLabel(__int64 a1, unsigned int a2)
{
  HWND v4; // rbx
  HWND v5; // rcx
  LONG_PTR v6; // rax
  bool v7; // zf
  RECT Rect; // [rsp+30h] [rbp-38h] BYREF

  ListView_DismissEdit(a1);
  if ( (*(_DWORD *)(a1 + 16) & 0x200) == 0 )
    return 0;
  v4 = *(HWND *)a1;
  if ( GetFocus() != v4 || a2 == -1 )
    return 0;
  ListView_DoOnEditLabel(a1);
  v5 = *(HWND *)(a1 + 328);
  if ( v5 )
  {
    v6 = SetWindowLongPtrW(v5, -4, (LONG_PTR)ListView_EditWndProc);
    v7 = g_fDBCSInputEnabled == 0;
    *(_QWORD *)(a1 + 344) = v6;
    if ( !v7 && SendMessageW(*(HWND *)(a1 + 328), 0xD5u, 0, 0) < 13 )
      *(_DWORD *)(a1 + 72) |= 0x4000u;
    ListView_SetEditSize(a1);
    SetFocus(*(HWND *)(a1 + 328));
    ShowWindow(*(HWND *)(a1 + 328), 5);
    ListView_InvalidateItemEx(a1, a2, 1, 5u, 0);
    RescrollEditWindow(*(_QWORD *)(a1 + 328));
    if ( (*(_BYTE *)(a1 + 16) & 3) == 0 )
    {
      Rect = 0;
      ListView_GetRects(a1, a2, 0, (int)&Rect, 0, 0);
      ListView_UnfoldRects(a1, a2, 0, &Rect, 0, 0);
      InvalidateRect(*(HWND *)a1, &Rect, 1);
      UpdateWindow(*(HWND *)a1);
    }
  }
  return *(_QWORD *)(a1 + 328);
}

```

## disassembly

```asm
0x180075888  mov     [rsp+arg_18], rbx
0x18007588d  push    rbp
0x18007588e  push    rsi
0x18007588f  push    rdi
0x180075890  sub     rsp, 50h
0x180075894  mov     rax, cs:__security_cookie
0x18007589b  xor     rax, rsp
0x18007589e  mov     [rsp+68h+var_28], rax
0x1800758a3  mov     esi, edx
0x1800758a5  mov     rbp, r8
0x1800758a8  xor     edx, edx
0x1800758aa  mov     rdi, rcx
0x1800758ad  call    ListView_DismissEdit
0x1800758b2  test    dword ptr [rdi+10h], 200h
0x1800758b9  jz      loc_1800759F1
0x1800758bf  mov     rbx, [rdi]
0x1800758c2  call    cs:__imp_GetFocus
0x1800758c8  cmp     rax, rbx
0x1800758cb  jnz     loc_1800759F1
0x1800758d1  cmp     esi, 0FFFFFFFFh
0x1800758d4  jz      loc_1800759F1
0x1800758da  mov     r8, rbp
0x1800758dd  mov     edx, esi
0x1800758df  mov     rcx, rdi; int
0x1800758e2  call    ListView_DoOnEditLabel
0x1800758e7  mov     rcx, [rdi+148h]; hWnd
0x1800758ee  xor     ebp, ebp
0x1800758f0  test    rcx, rcx
0x1800758f3  jz      loc_1800759E8
0x1800758f9  lea     r8, ListView_EditWndProc; dwNewLong
0x180075900  lea     edx, [rbp-4]; nIndex
0x180075903  call    cs:__imp_SetWindowLongPtrW
0x180075909  cmp     cs:g_fDBCSInputEnabled, ebp
0x18007590f  mov     [rdi+158h], rax
0x180075916  jz      short loc_18007593B
0x180075918  mov     rcx, [rdi+148h]; hWnd
0x18007591f  xor     r9d, r9d; lParam
0x180075922  xor     r8d, r8d; wParam
0x180075925  mov     edx, 0D5h; Msg
0x18007592a  call    cs:__imp_SendMessageW
0x180075930  cmp     rax, 0Dh
0x180075934  jge     short loc_18007593B
0x180075936  bts     dword ptr [rdi+48h], 0Eh
0x18007593b  mov     rcx, rdi; int
0x18007593e  call    ListView_SetEditSize
0x180075943  mov     rcx, [rdi+148h]; hWnd
0x18007594a  call    cs:__imp_SetFocus
0x180075950  mov     rcx, [rdi+148h]; hWnd
0x180075957  mov     ebx, 5
0x18007595c  mov     edx, ebx; nCmdShow
0x18007595e  call    cs:__imp_ShowWindow
0x180075964  mov     r9d, ebx
0x180075967  mov     dword ptr [rsp+68h+lprcDst], ebp; int
0x18007596b  mov     edx, esi
0x18007596d  mov     rcx, rdi; int
0x180075970  lea     ebx, [r9-4]
0x180075974  mov     r8d, ebx
0x180075977  call    ListView_InvalidateItemEx
0x18007597c  mov     rcx, [rdi+148h]
0x180075983  call    RescrollEditWindow
0x180075988  test    byte ptr [rdi+10h], 3
0x18007598c  jnz     short loc_1800759E8
0x18007598e  xorps   xmm0, xmm0
0x180075991  mov     [rsp+68h+var_40], rbp; LPRECT
0x180075996  lea     r9, [rsp+68h+Rect]; int
0x18007599b  mov     [rsp+68h+lprcDst], rbp; lprcDst
0x1800759a0  xor     r8d, r8d; int
0x1800759a3  mov     edx, esi; int
0x1800759a5  mov     rcx, rdi; int
0x1800759a8  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x1800759ad  call    ListView_GetRects
0x1800759b2  lea     r9, [rsp+68h+Rect]
0x1800759b7  mov     [rsp+68h+var_40], rbp
0x1800759bc  xor     r8d, r8d
0x1800759bf  mov     [rsp+68h+lprcDst], rbp
0x1800759c4  mov     edx, esi
0x1800759c6  mov     rcx, rdi
0x1800759c9  call    ListView_UnfoldRects
0x1800759ce  mov     rcx, [rdi]; hWnd
0x1800759d1  lea     rdx, [rsp+68h+Rect]; lpRect
0x1800759d6  mov     r8d, ebx; bErase
0x1800759d9  call    cs:__imp_InvalidateRect
0x1800759df  mov     rcx, [rdi]; hWnd
0x1800759e2  call    cs:__imp_UpdateWindow
0x1800759e8  mov     rax, [rdi+148h]
0x1800759ef  jmp     short loc_1800759F3
0x1800759f1  xor     eax, eax
0x1800759f3  mov     rcx, [rsp+68h+var_28]
0x1800759f8  xor     rcx, rsp; StackCookie
0x1800759fb  call    __security_check_cookie
0x180075a00  mov     rbx, [rsp+68h+arg_18]
0x180075a08  add     rsp, 50h
0x180075a0c  pop     rdi
0x180075a0d  pop     rsi
0x180075a0e  pop     rbp
0x180075a0f  retn
```
