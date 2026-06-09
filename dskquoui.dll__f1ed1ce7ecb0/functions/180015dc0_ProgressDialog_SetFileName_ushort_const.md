# ProgressDialog::SetFileName(ushort const *)

- ea: `0x180015dc0`
- end: `0x180015ea4`
- name: `?SetFileName@ProgressDialog@@UEAAXPEBG@Z`
- size: `228`
- prototype: `void(ProgressDialog *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005ebc`

## callees

- `0x180001510`
- `0x180015dc0`
- `0x18001acac`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015e58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015e58`
- `USER32!SetWindowTextW` at `0x180015e4f`
- `USER32!SetWindowTextW` at `0x180015e4f`
- `USER32!DrawTextW` at `0x180015e43`
- `USER32!DrawTextW` at `0x180015e43`
- `USER32!GetDC` at `0x180015dfd`
- `USER32!GetDC` at `0x180015dfd`
- `USER32!ReleaseDC` at `0x180015e81`
- `USER32!ReleaseDC` at `0x180015e81`
- `USER32!GetClientRect` at `0x180015e26`
- `USER32!GetClientRect` at `0x180015e26`
- `USER32!GetDlgItem` at `0x180015df1`
- `USER32!GetDlgItem` at `0x180015df1`
- `USER32!ShowWindow` at `0x180015e66`
- `USER32!ShowWindow` at `0x180015e66`

## pseudocode

```c
void __fastcall ProgressDialog::SetFileName(ProgressDialog *this, const unsigned __int16 *a2)
{
  HWND v4; // rcx
  HWND DlgItem; // rdi
  HDC DC; // rbp
  WCHAR *v7; // rsi
  struct tagRECT Rect; // [rsp+30h] [rbp-38h] BYREF

  v4 = (HWND)*((_QWORD *)this + 5);
  if ( v4 )
  {
    DlgItem = GetDlgItem(v4, *((_DWORD *)this + 5));
    Rect = 0;
    DC = GetDC(DlgItem);
    v7 = StringDup(a2);
    if ( v7 )
    {
      GetClientRect(DlgItem, &Rect);
      DrawTextW(DC, v7, -1, &Rect, 0x14001u);
      SetWindowTextW(DlgItem, v7);
      LocalFree(v7);
      ShowWindow(DlgItem, 1);
    }
    (*(void (__fastcall **)(ProgressDialog *))(*(_QWORD *)this + 80LL))(this);
    ReleaseDC(DlgItem, DC);
  }
}

```

## disassembly

```asm
0x180015dc0  mov     [rsp+arg_10], rbx
0x180015dc5  push    rbp
0x180015dc6  push    rsi
0x180015dc7  push    rdi
0x180015dc8  sub     rsp, 50h
0x180015dcc  mov     rax, cs:__security_cookie
0x180015dd3  xor     rax, rsp
0x180015dd6  mov     [rsp+68h+var_28], rax
0x180015ddb  mov     rbx, rcx
0x180015dde  mov     rsi, rdx
0x180015de1  mov     rcx, [rcx+28h]; hDlg
0x180015de5  test    rcx, rcx
0x180015de8  jz      loc_180015E87
0x180015dee  mov     edx, [rbx+14h]; nIDDlgItem
0x180015df1  call    cs:__imp_GetDlgItem
0x180015df7  mov     rcx, rax; hWnd
0x180015dfa  mov     rdi, rax
0x180015dfd  call    cs:__imp_GetDC
0x180015e03  xorps   xmm0, xmm0
0x180015e06  mov     rcx, rsi; unsigned __int16 *
0x180015e09  movups  xmmword ptr [rsp+68h+Rect.left], xmm0
0x180015e0e  mov     rbp, rax
0x180015e11  call    ?StringDup@@YAPEAGPEBG@Z; StringDup(ushort const *)
0x180015e16  mov     rsi, rax
0x180015e19  test    rax, rax
0x180015e1c  jz      short loc_180015E6C
0x180015e1e  lea     rdx, [rsp+68h+Rect]; lpRect
0x180015e23  mov     rcx, rdi; hWnd
0x180015e26  call    cs:__imp_GetClientRect
0x180015e2c  lea     r9, [rsp+68h+Rect]; lprc
0x180015e31  mov     [rsp+68h+format], 14001h; format
0x180015e39  or      r8d, 0FFFFFFFFh; cchText
0x180015e3d  mov     rdx, rsi; lpchText
0x180015e40  mov     rcx, rbp; hdc
0x180015e43  call    cs:__imp_DrawTextW
0x180015e49  mov     rdx, rsi; lpString
0x180015e4c  mov     rcx, rdi; hWnd
0x180015e4f  call    cs:__imp_SetWindowTextW
0x180015e55  mov     rcx, rsi; hMem
0x180015e58  call    cs:__imp_LocalFree
0x180015e5e  mov     edx, 1; nCmdShow
0x180015e63  mov     rcx, rdi; hWnd
0x180015e66  call    cs:__imp_ShowWindow
0x180015e6c  mov     rax, [rbx]
0x180015e6f  mov     rcx, rbx
0x180015e72  mov     rax, [rax+50h]
0x180015e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e7b  mov     rdx, rbp; hDC
0x180015e7e  mov     rcx, rdi; hWnd
0x180015e81  call    cs:__imp_ReleaseDC
0x180015e87  mov     rcx, [rsp+68h+var_28]
0x180015e8c  xor     rcx, rsp; StackCookie
0x180015e8f  call    __security_check_cookie
0x180015e94  mov     rbx, [rsp+68h+arg_10]
0x180015e9c  add     rsp, 50h
0x180015ea0  pop     rdi
0x180015ea1  pop     rsi
0x180015ea2  pop     rbp
0x180015ea3  retn
```
