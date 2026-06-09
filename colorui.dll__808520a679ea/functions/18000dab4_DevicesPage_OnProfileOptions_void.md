# DevicesPage::OnProfileOptions(void)

- ea: `0x18000dab4`
- end: `0x18000dc03`
- name: `?OnProfileOptions@DevicesPage@@AEAAJXZ`
- size: `335`
- prototype: `signed int __fastcall(DevicesPage *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cd90`

## callees

- `0x18000dab4`
- `0x180018500`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000daf9`
- `KERNEL32!GetLastError` at `0x18000db43`
- `KERNEL32!GetLastError` at `0x18000dbd0`
- `KERNEL32!GetLastError` at `0x18000daf9`
- `KERNEL32!GetLastError` at `0x18000db43`
- `KERNEL32!GetLastError` at `0x18000dbd0`
- `USER32!RemoveMenu` at `0x18000db8b`
- `USER32!RemoveMenu` at `0x18000db9c`
- `USER32!RemoveMenu` at `0x18000db8b`
- `USER32!RemoveMenu` at `0x18000db9c`
- `USER32!TrackPopupMenuEx` at `0x18000dbc6`
- `USER32!TrackPopupMenuEx` at `0x18000dbc6`
- `USER32!GetWindowRect` at `0x18000daef`
- `USER32!GetWindowRect` at `0x18000daef`
- `USER32!LoadMenuW` at `0x18000db34`
- `USER32!LoadMenuW` at `0x18000db34`
- `USER32!GetDlgItem` at `0x18000dae1`
- `USER32!GetDlgItem` at `0x18000dae1`
- `USER32!GetSubMenu` at `0x18000db6c`
- `USER32!GetSubMenu` at `0x18000db6c`

## pseudocode

```c
signed int __fastcall DevicesPage::OnProfileOptions(DevicesPage *this)
{
  HWND v2; // rcx
  HWND DlgItem; // rax
  signed int LastError; // eax
  int v5; // ebx
  signed int result; // eax
  signed int v7; // edi
  HMENU MenuW; // rax
  signed int v9; // eax
  HMENU SubMenu; // rax
  HMENU v11; // r14
  struct tagRECT Rect; // [rsp+30h] [rbp-48h] BYREF

  v2 = (HWND)*((_QWORD *)this + 1);
  Rect = 0;
  DlgItem = GetDlgItem(v2, 1117);
  if ( !GetWindowRect(DlgItem, &Rect) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( !LastError )
      return -2147467259;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return v5;
  }
  v7 = 0;
  v5 = -2147467259;
  if ( !*((_QWORD *)this + 6) )
  {
    MenuW = LoadMenuW(*((HINSTANCE *)this + 2), (LPCWSTR)0x45E);
    *((_QWORD *)this + 6) = MenuW;
    if ( !MenuW )
    {
      v9 = GetLastError();
      v7 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v7 = (unsigned __int16)v9 | 0x80070000;
      }
      else
      {
        v7 = -2147467259;
      }
      if ( v7 < 0 )
        return v7;
    }
  }
  SubMenu = GetSubMenu(*((HMENU *)this + 6), 0);
  v11 = SubMenu;
  if ( !SubMenu )
    return v5;
  if ( *((_DWORD *)this + 18) != 1 )
  {
    RemoveMenu(SubMenu, 0x45Fu, 0);
    RemoveMenu(v11, 0x460u, 0);
  }
  if ( TrackPopupMenuEx(v11, 2u, Rect.left, Rect.bottom, *((HWND *)this + 1), 0) )
    return v7;
  result = GetLastError();
  if ( !result )
    return v5;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000dab4  push    rbx
0x18000dab6  push    rsi
0x18000dab7  push    rdi
0x18000dab8  push    r14
0x18000daba  sub     rsp, 58h
0x18000dabe  mov     rax, cs:__security_cookie
0x18000dac5  xor     rax, rsp
0x18000dac8  mov     [rsp+78h+var_38], rax
0x18000dacd  mov     rsi, rcx
0x18000dad0  xorps   xmm0, xmm0
0x18000dad3  mov     rcx, [rcx+8]; hDlg
0x18000dad7  mov     edx, 45Dh; nIDDlgItem
0x18000dadc  movups  xmmword ptr [rsp+78h+Rect.left], xmm0
0x18000dae1  call    cs:__imp_GetDlgItem
0x18000dae7  mov     rcx, rax; hWnd
0x18000daea  lea     rdx, [rsp+78h+Rect]; lpRect
0x18000daef  call    cs:__imp_GetWindowRect
0x18000daf5  test    eax, eax
0x18000daf7  jnz     short loc_18000DB1E
0x18000daf9  call    cs:__imp_GetLastError
0x18000daff  mov     ebx, eax
0x18000db01  test    eax, eax
0x18000db03  jz      short loc_18000DB12
0x18000db05  jle     short loc_18000DB17
0x18000db07  movzx   ebx, ax
0x18000db0a  or      ebx, 80070000h
0x18000db10  jmp     short loc_18000DB17
0x18000db12  mov     ebx, 80004005h
0x18000db17  mov     eax, ebx
0x18000db19  jmp     loc_18000DBEC
0x18000db1e  xor     edi, edi
0x18000db20  mov     ebx, 80004005h
0x18000db25  cmp     [rsi+30h], rdi
0x18000db29  jnz     short loc_18000DB66
0x18000db2b  mov     rcx, [rsi+10h]; hInstance
0x18000db2f  mov     edx, 45Eh; lpMenuName
0x18000db34  call    cs:__imp_LoadMenuW
0x18000db3a  mov     [rsi+30h], rax
0x18000db3e  test    rax, rax
0x18000db41  jnz     short loc_18000DB66
0x18000db43  call    cs:__imp_GetLastError
0x18000db49  mov     edi, eax
0x18000db4b  test    eax, eax
0x18000db4d  jz      short loc_18000DB5C
0x18000db4f  jle     short loc_18000DB5E
0x18000db51  movzx   edi, ax
0x18000db54  or      edi, 80070000h
0x18000db5a  jmp     short loc_18000DB5E
0x18000db5c  mov     edi, ebx
0x18000db5e  test    edi, edi
0x18000db60  js      loc_18000DBEA
0x18000db66  mov     rcx, [rsi+30h]; hMenu
0x18000db6a  xor     edx, edx; nPos
0x18000db6c  call    cs:__imp_GetSubMenu
0x18000db72  mov     r14, rax
0x18000db75  test    rax, rax
0x18000db78  jz      short loc_18000DB17
0x18000db7a  cmp     dword ptr [rsi+48h], 1
0x18000db7e  jz      short loc_18000DBA2
0x18000db80  xor     r8d, r8d; uFlags
0x18000db83  mov     edx, 45Fh; uPosition
0x18000db88  mov     rcx, rax; hMenu
0x18000db8b  call    cs:__imp_RemoveMenu
0x18000db91  xor     r8d, r8d; uFlags
0x18000db94  mov     edx, 460h; uPosition
0x18000db99  mov     rcx, r14; hMenu
0x18000db9c  call    cs:__imp_RemoveMenu
0x18000dba2  mov     rax, [rsi+8]
0x18000dba6  mov     edx, 2; uFlags
0x18000dbab  mov     r9d, [rsp+78h+Rect.bottom]; y
0x18000dbb0  mov     rcx, r14; hMenu
0x18000dbb3  mov     r8d, [rsp+78h+Rect.left]; x
0x18000dbb8  mov     [rsp+78h+lptpm], 0; lptpm
0x18000dbc1  mov     [rsp+78h+hwnd], rax; hwnd
0x18000dbc6  call    cs:__imp_TrackPopupMenuEx
0x18000dbcc  test    eax, eax
0x18000dbce  jnz     short loc_18000DBEA
0x18000dbd0  call    cs:__imp_GetLastError
0x18000dbd6  test    eax, eax
0x18000dbd8  jz      loc_18000DB17
0x18000dbde  jle     short loc_18000DBEC
0x18000dbe0  movzx   eax, ax
0x18000dbe3  or      eax, 80070000h
0x18000dbe8  jmp     short loc_18000DBEC
0x18000dbea  mov     eax, edi
0x18000dbec  mov     rcx, [rsp+78h+var_38]
0x18000dbf1  xor     rcx, rsp; StackCookie
0x18000dbf4  call    __security_check_cookie
0x18000dbf9  add     rsp, 58h
0x18000dbfd  pop     r14
0x18000dbff  pop     rdi
0x18000dc00  pop     rsi
0x18000dc01  pop     rbx
0x18000dc02  retn
```
