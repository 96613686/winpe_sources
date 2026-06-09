# CWarningBaseDlg::UpdateBackground(void)

- ea: `0x180013d4c`
- end: `0x180013df9`
- name: `?UpdateBackground@CWarningBaseDlg@@IEAAXXZ`
- size: `173`
- prototype: `void __fastcall(CWarningBaseDlg *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180012030`
- `0x180013574`
- `0x180013960`
- `0x1800163b4`

## callees

- `0x180013d4c`

## import_xrefs

- `USER32!GetSysColor` at `0x180013d78`
- `USER32!GetSysColor` at `0x180013dd1`
- `USER32!GetSysColor` at `0x180013d78`
- `USER32!GetSysColor` at `0x180013dd1`
- `USER32!InvalidateRect` at `0x180013ded`
- `USER32!InvalidateRect` at `0x180013ded`
- `GDI32!CreateSolidBrush` at `0x180013d80`
- `GDI32!CreateSolidBrush` at `0x180013dd9`
- `GDI32!CreateSolidBrush` at `0x180013d80`
- `GDI32!CreateSolidBrush` at `0x180013dd9`
- `GDI32!DeleteObject` at `0x180013d5e`
- `GDI32!DeleteObject` at `0x180013d6d`
- `GDI32!DeleteObject` at `0x180013d5e`
- `GDI32!DeleteObject` at `0x180013d6d`
- `UxTheme!GetThemeColor` at `0x180013dbc`
- `UxTheme!GetThemeColor` at `0x180013dbc`
- `UxTheme!IsThemeActive` at `0x180013d92`
- `UxTheme!IsThemeActive` at `0x180013d92`

## pseudocode

```c
void __fastcall CWarningBaseDlg::UpdateBackground(CWarningBaseDlg *this)
{
  void *v2; // rcx
  void *v3; // rcx
  COLORREF SysColor; // eax
  void *v5; // rcx
  COLORREF v6; // ecx
  COLORREF pColor; // [rsp+40h] [rbp+8h] BYREF

  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
    DeleteObject(v2);
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
    DeleteObject(v3);
  SysColor = GetSysColor(15);
  *((_QWORD *)this + 8) = CreateSolidBrush(SysColor);
  pColor = 0;
  if ( IsThemeActive() && (v5 = (void *)*((_QWORD *)this + 12)) != 0 && GetThemeColor(v5, 1, 0, 3802, &pColor) >= 0 )
    v6 = pColor;
  else
    v6 = GetSysColor(5);
  *((_QWORD *)this + 9) = CreateSolidBrush(v6);
  InvalidateRect(*((HWND *)this + 1), 0, 1);
}

```

## disassembly

```asm
0x180013d4c  push    rbx
0x180013d4e  sub     rsp, 30h
0x180013d52  mov     rbx, rcx
0x180013d55  mov     rcx, [rcx+40h]; ho
0x180013d59  test    rcx, rcx
0x180013d5c  jz      short loc_180013D64
0x180013d5e  call    cs:__imp_DeleteObject
0x180013d64  mov     rcx, [rbx+48h]; ho
0x180013d68  test    rcx, rcx
0x180013d6b  jz      short loc_180013D73
0x180013d6d  call    cs:__imp_DeleteObject
0x180013d73  mov     ecx, 0Fh; nIndex
0x180013d78  call    cs:__imp_GetSysColor
0x180013d7e  mov     ecx, eax; color
0x180013d80  call    cs:__imp_CreateSolidBrush
0x180013d86  mov     [rbx+40h], rax
0x180013d8a  mov     [rsp+38h+arg_0], 0
0x180013d92  call    cs:__imp_IsThemeActive
0x180013d98  test    eax, eax
0x180013d9a  jz      short loc_180013DCC
0x180013d9c  mov     rcx, [rbx+60h]; hTheme
0x180013da0  test    rcx, rcx
0x180013da3  jz      short loc_180013DCC
0x180013da5  xor     r8d, r8d; iStateId
0x180013da8  lea     rax, [rsp+38h+arg_0]
0x180013dad  mov     r9d, 0EDAh; iPropId
0x180013db3  mov     [rsp+38h+pColor], rax; pColor
0x180013db8  lea     edx, [r8+1]; iPartId
0x180013dbc  call    cs:__imp_GetThemeColor
0x180013dc2  test    eax, eax
0x180013dc4  js      short loc_180013DCC
0x180013dc6  mov     ecx, [rsp+38h+arg_0]
0x180013dca  jmp     short loc_180013DD9
0x180013dcc  mov     ecx, 5; nIndex
0x180013dd1  call    cs:__imp_GetSysColor
0x180013dd7  mov     ecx, eax; color
0x180013dd9  call    cs:__imp_CreateSolidBrush
0x180013ddf  xor     edx, edx; lpRect
0x180013de1  mov     [rbx+48h], rax
0x180013de5  mov     rcx, [rbx+8]; hWnd
0x180013de9  lea     r8d, [rdx+1]; bErase
0x180013ded  call    cs:__imp_InvalidateRect
0x180013df3  add     rsp, 30h
0x180013df7  pop     rbx
0x180013df8  retn
```
