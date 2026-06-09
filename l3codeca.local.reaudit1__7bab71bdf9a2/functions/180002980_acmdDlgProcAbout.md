# acmdDlgProcAbout

- ea: `0x180002980`
- end: `0x180002b62`
- name: `acmdDlgProcAbout`
- size: `482`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001400`
- `0x1800028f4`
- `0x180002980`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002b12`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180002b12`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x180002aac`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x180002aac`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x180002a65`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x180002a65`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x180002a4f`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x180002a4f`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x180002a94`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x180002a94`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SetDlgItemTextW` at `0x180002afb`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SetDlgItemTextW` at `0x180002b25`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SetDlgItemTextW` at `0x180002afb`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!SetDlgItemTextW` at `0x180002b25`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180002a03`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180002a14`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180002a25`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180002a03`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180002a14`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180002a25`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x1800029b9`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x1800029b9`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x180002abb`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x180002abb`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180002b33`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180002b33`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180002a44`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180002a5a`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180002aa4`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180002a44`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180002a5a`
- `ext-ms-win-rtcore-ntuser-syscolors-l1-1-0!GetSysColor` at `0x180002aa4`

## pseudocode

```c
INT_PTR __fastcall acmdDlgProcAbout(HWND a1, int a2, HDC a3, HWND a4)
{
  void *WindowLongPtrW; // rax
  void *v9; // r14
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  HWND DlgItem; // rbx
  HWND v16; // r15
  HWND v17; // rax
  int v18; // ecx
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD SysColor; // eax
  HBRUSH SolidBrush; // rax
  wchar_t pszDest[64]; // [rsp+30h] [rbp-B8h] BYREF

  WindowLongPtrW = (void *)GetWindowLongPtrW(a1, 16);
  v9 = WindowLongPtrW;
  v10 = a2 - 2;
  if ( v10 )
  {
    v11 = v10 - 270;
    if ( !v11 )
    {
      SysColor = GetSysColor(15);
      SolidBrush = CreateSolidBrush(SysColor);
      SetWindowLongPtrW(a1, 16, (LONG_PTR)SolidBrush);
      StringCchPrintfW(pszDest, 0x3Cu, L"%d.%d (Build %d)");
      SetDlgItemTextW(a1, 25052, pszDest);
      LoadStringW(*((HINSTANCE *)a4 + 3), 0x627Au, pszDest, 60);
      SetDlgItemTextW(a1, 25051, pszDest);
      return 1;
    }
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 36;
      if ( !v13 || (v14 = v13 - 1) == 0 )
      {
        v18 = 8;
LABEL_11:
        v19 = GetSysColor(v18);
        SetTextColor(a3, v19);
        v20 = GetSysColor(15);
        SetBkColor(a3, v20);
        return (INT_PTR)v9;
      }
      if ( v14 == 2 )
      {
        DlgItem = GetDlgItem(a1, 25050);
        v16 = GetDlgItem(a1, 25051);
        v17 = GetDlgItem(a1, 25053);
        if ( a4 == DlgItem || a4 == v16 || (v18 = 8, a4 == v17) )
          v18 = 13;
        goto LABEL_11;
      }
    }
    else if ( (unsigned __int64)a3 - 1 <= 1 )
    {
      EndDialog(a1, a3 == (HDC)1);
    }
  }
  else
  {
    DeleteObject(WindowLongPtrW);
  }
  return 0;
}

```

## disassembly

```asm
0x180002980  mov     [rsp+arg_8], rbx
0x180002985  push    rbp
0x180002986  push    rsi
0x180002987  push    rdi
0x180002988  push    r14
0x18000298a  push    r15
0x18000298c  sub     rsp, 0C0h
0x180002993  mov     rax, cs:__security_cookie
0x18000299a  xor     rax, rsp
0x18000299d  mov     [rsp+0E8h+var_38], rax
0x1800029a5  mov     ebx, edx
0x1800029a7  mov     r15d, 10h
0x1800029ad  mov     edx, r15d; nIndex
0x1800029b0  mov     rbp, r9
0x1800029b3  mov     rdi, r8
0x1800029b6  mov     rsi, rcx
0x1800029b9  call    cs:__imp_GetWindowLongPtrW
0x1800029bf  mov     r14, rax
0x1800029c2  sub     ebx, 2
0x1800029c5  jz      loc_180002B30
0x1800029cb  sub     ebx, 10Eh
0x1800029d1  jz      loc_180002A9F
0x1800029d7  sub     ebx, 1
0x1800029da  jz      loc_180002A7A
0x1800029e0  sub     ebx, 24h ; '$'
0x1800029e3  jz      loc_180002A73
0x1800029e9  sub     ebx, 1
0x1800029ec  jz      loc_180002A73
0x1800029f2  cmp     ebx, 2
0x1800029f5  jnz     loc_180002B39
0x1800029fb  mov     edx, 61DAh; nIDDlgItem
0x180002a00  mov     rcx, rsi; hDlg
0x180002a03  call    cs:__imp_GetDlgItem
0x180002a09  mov     edx, 61DBh; nIDDlgItem
0x180002a0e  mov     rcx, rsi; hDlg
0x180002a11  mov     rbx, rax
0x180002a14  call    cs:__imp_GetDlgItem
0x180002a1a  mov     edx, 61DDh; nIDDlgItem
0x180002a1f  mov     rcx, rsi; hDlg
0x180002a22  mov     r15, rax
0x180002a25  call    cs:__imp_GetDlgItem
0x180002a2b  cmp     rbp, rbx
0x180002a2e  jz      short loc_180002A3F
0x180002a30  cmp     rbp, r15
0x180002a33  jz      short loc_180002A3F
0x180002a35  mov     ecx, 8
0x180002a3a  cmp     rbp, rax
0x180002a3d  jnz     short loc_180002A44
0x180002a3f  mov     ecx, 0Dh; nIndex
0x180002a44  call    cs:__imp_GetSysColor
0x180002a4a  mov     edx, eax; color
0x180002a4c  mov     rcx, rdi; hdc
0x180002a4f  call    cs:__imp_SetTextColor
0x180002a55  mov     ecx, 0Fh; nIndex
0x180002a5a  call    cs:__imp_GetSysColor
0x180002a60  mov     edx, eax; color
0x180002a62  mov     rcx, rdi; hdc
0x180002a65  call    cs:__imp_SetBkColor
0x180002a6b  mov     rax, r14
0x180002a6e  jmp     loc_180002B3B
0x180002a73  mov     ecx, 8
0x180002a78  jmp     short loc_180002A44
0x180002a7a  lea     rax, [rdi-1]
0x180002a7e  cmp     rax, 1
0x180002a82  ja      loc_180002B39
0x180002a88  xor     edx, edx
0x180002a8a  mov     rcx, rsi; hDlg
0x180002a8d  cmp     rdi, 1
0x180002a91  setz    dl; nResult
0x180002a94  call    cs:__imp_EndDialog
0x180002a9a  jmp     loc_180002B39
0x180002a9f  mov     ecx, 0Fh; nIndex
0x180002aa4  call    cs:__imp_GetSysColor
0x180002aaa  mov     ecx, eax; color
0x180002aac  call    cs:__imp_CreateSolidBrush
0x180002ab2  mov     edx, r15d; nIndex
0x180002ab5  mov     rcx, rsi; hWnd
0x180002ab8  mov     r8, rax; dwNewLong
0x180002abb  call    cs:__imp_SetWindowLongPtrW
0x180002ac1  mov     r9d, 1
0x180002ac7  mov     [rsp+0E8h+var_C0], 191h
0x180002acf  lea     r8, aDDBuildD; "%d.%d (Build %d)"
0x180002ad6  mov     [rsp+0E8h+var_C8], 9
0x180002ade  lea     rcx, [rsp+0E8h+pszDest]; pszDest
0x180002ae3  lea     ebx, [r9+3Bh]
0x180002ae7  mov     edx, ebx; cchDest
0x180002ae9  call    StringCchPrintfW
0x180002aee  lea     r8, [rsp+0E8h+pszDest]; lpString
0x180002af3  mov     edx, 61DCh; nIDDlgItem
0x180002af8  mov     rcx, rsi; hDlg
0x180002afb  call    cs:__imp_SetDlgItemTextW
0x180002b01  mov     rcx, [rbp+18h]; hInstance
0x180002b05  lea     r8, [rsp+0E8h+pszDest]; lpBuffer
0x180002b0a  mov     r9d, ebx; cchBufferMax
0x180002b0d  mov     edx, 627Ah; uID
0x180002b12  call    cs:__imp_LoadStringW
0x180002b18  lea     r8, [rsp+0E8h+pszDest]; lpString
0x180002b1d  mov     edx, 61DBh; nIDDlgItem
0x180002b22  mov     rcx, rsi; hDlg
0x180002b25  call    cs:__imp_SetDlgItemTextW
0x180002b2b  lea     eax, [rbx-3Bh]
0x180002b2e  jmp     short loc_180002B3B
0x180002b30  mov     rcx, r14; ho
0x180002b33  call    cs:__imp_DeleteObject
0x180002b39  xor     eax, eax
0x180002b3b  mov     rcx, [rsp+0E8h+var_38]
0x180002b43  xor     rcx, rsp; StackCookie
0x180002b46  call    __security_check_cookie
0x180002b4b  mov     rbx, [rsp+0E8h+arg_8]
0x180002b53  add     rsp, 0C0h
0x180002b5a  pop     r15
0x180002b5c  pop     r14
0x180002b5e  pop     rdi
0x180002b5f  pop     rsi
0x180002b60  pop     rbp
0x180002b61  retn
```
