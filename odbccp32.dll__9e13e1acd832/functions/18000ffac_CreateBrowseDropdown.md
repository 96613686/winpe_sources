# CreateBrowseDropdown

- ea: `0x18000ffac`
- end: `0x180010139`
- name: `CreateBrowseDropdown`
- size: `397`
- prototype: `__int64 __fastcall(HWND hwnd)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c440`

## callees

- `0x18000ffac`
- `0x180010140`
- `0x1800109f4`
- `0x180014ae0`
- `0x180015010`

## import_xrefs

- `USER32!LoadCursorA` at `0x18001000d`
- `USER32!LoadCursorA` at `0x18001000d`
- `USER32!SetCursor` at `0x180010016`
- `USER32!SetCursor` at `0x18001010a`
- `USER32!SetCursor` at `0x180010016`
- `USER32!SetCursor` at `0x18001010a`
- `USER32!GetWindowLongPtrW` at `0x18001003b`
- `USER32!GetWindowLongPtrW` at `0x18001003b`
- `USER32!SendMessageW` at `0x18001002d`
- `USER32!SendMessageW` at `0x18001002d`
- `USER32!GetDlgItem` at `0x18000fffd`
- `USER32!GetDlgItem` at `0x18000fffd`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180010083`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180010083`
- `SHELL32!SHGetMalloc` at `0x180010053`
- `SHELL32!SHGetMalloc` at `0x180010053`
- `SHELL32!SHGetDesktopFolder` at `0x18001006f`
- `SHELL32!SHGetDesktopFolder` at `0x18001006f`

## pseudocode

```c
__int64 __fastcall CreateBrowseDropdown(HWND hwnd)
{
  HWND DlgItem; // rsi
  HCURSOR CursorA; // rax
  HCURSOR v4; // r14
  LONG_PTR WindowLongPtrW; // rax
  unsigned int v6; // ebx
  IMalloc *ppMalloc; // [rsp+40h] [rbp-C0h] BYREF
  IShellFolder *ppshf; // [rsp+48h] [rbp-B8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+50h] [rbp-B0h] BYREF
  int v11[132]; // [rsp+60h] [rbp-A0h] BYREF

  ppshf = 0;
  ppidl = 0;
  ppMalloc = 0;
  DlgItem = GetDlgItem(hwnd, 1887);
  CursorA = LoadCursorA(0, (LPCSTR)0x7F02);
  v4 = SetCursor(CursorA);
  SendMessageW(DlgItem, 0x14Bu, 0, 0);
  WindowLongPtrW = GetWindowLongPtrW(hwnd, 16);
  GetPathFromIDList(WindowLongPtrW, v11);
  if ( SHGetMalloc(&ppMalloc) >= 0 )
  {
    v6 = -1;
    if ( SHGetDesktopFolder(&ppshf) >= 0 && SHGetSpecialFolderLocation(hwnd, 0, &ppidl) >= 0 )
    {
      EnumFolderObjects((int)DlgItem, (int)ppshf, (int)v11, 0, (__int64)ppMalloc, 1, ppidl);
      v6 = 0;
    }
    if ( ppshf )
      ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
    if ( ppidl )
      ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Free)(ppMalloc);
    if ( ppMalloc )
      ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  else
  {
    v6 = 1;
  }
  SetCursor(v4);
  return v6;
}

```

## disassembly

```asm
0x18000ffac  mov     [rsp-8+arg_8], rbx
0x18000ffb1  mov     [rsp-8+arg_10], rsi
0x18000ffb6  push    rbp
0x18000ffb7  push    rdi
0x18000ffb8  push    r14
0x18000ffba  lea     rbp, [rsp-180h]
0x18000ffc2  sub     rsp, 280h
0x18000ffc9  mov     rax, cs:__security_cookie
0x18000ffd0  xor     rax, rsp
0x18000ffd3  mov     [rbp+190h+var_20], rax
0x18000ffda  mov     edx, 75Fh; nIDDlgItem
0x18000ffdf  mov     [rsp+290h+ppshf], 0
0x18000ffe8  mov     rdi, rcx
0x18000ffeb  mov     [rsp+290h+ppidl], 0
0x18000fff4  mov     [rsp+290h+ppMalloc], 0
0x18000fffd  call    cs:__imp_GetDlgItem
0x180010003  mov     edx, 7F02h; lpCursorName
0x180010008  xor     ecx, ecx; hInstance
0x18001000a  mov     rsi, rax
0x18001000d  call    cs:__imp_LoadCursorA
0x180010013  mov     rcx, rax; hCursor
0x180010016  call    cs:__imp_SetCursor
0x18001001c  xor     r9d, r9d; lParam
0x18001001f  xor     r8d, r8d; wParam
0x180010022  mov     edx, 14Bh; Msg
0x180010027  mov     rcx, rsi; hWnd
0x18001002a  mov     r14, rax
0x18001002d  call    cs:__imp_SendMessageW
0x180010033  mov     edx, 10h; nIndex
0x180010038  mov     rcx, rdi; hWnd
0x18001003b  call    cs:__imp_GetWindowLongPtrW
0x180010041  mov     rcx, rax
0x180010044  lea     rdx, [rsp+290h+var_230]
0x180010049  call    GetPathFromIDList
0x18001004e  lea     rcx, [rsp+290h+ppMalloc]; ppMalloc
0x180010053  call    cs:__imp_SHGetMalloc
0x180010059  test    eax, eax
0x18001005b  jns     short loc_180010067
0x18001005d  mov     ebx, 1
0x180010062  jmp     loc_180010107
0x180010067  lea     rcx, [rsp+290h+ppshf]; ppshf
0x18001006c  or      ebx, 0FFFFFFFFh
0x18001006f  call    cs:__imp_SHGetDesktopFolder
0x180010075  test    eax, eax
0x180010077  js      short loc_1800100C0
0x180010079  lea     r8, [rsp+290h+ppidl]; ppidl
0x18001007e  xor     edx, edx; csidl
0x180010080  mov     rcx, rdi; hwnd
0x180010083  call    cs:__imp_SHGetSpecialFolderLocation
0x180010089  test    eax, eax
0x18001008b  js      short loc_1800100C0
0x18001008d  mov     rax, [rsp+290h+ppidl]
0x180010092  lea     r8, [rsp+290h+var_230]; int
0x180010097  mov     rdx, [rsp+290h+ppshf]; int
0x18001009c  xor     r9d, r9d; int
0x18001009f  mov     [rsp+290h+Buf2], rax; Buf2
0x1800100a4  mov     rcx, rsi; int
0x1800100a7  mov     rax, [rsp+290h+ppMalloc]
0x1800100ac  mov     [rsp+290h+var_268], 1; int
0x1800100b4  mov     [rsp+290h+var_270], rax; __int64
0x1800100b9  call    EnumFolderObjects
0x1800100be  xor     ebx, ebx
0x1800100c0  mov     rcx, [rsp+290h+ppshf]
0x1800100c5  test    rcx, rcx
0x1800100c8  jz      short loc_1800100D6
0x1800100ca  mov     rax, [rcx]
0x1800100cd  mov     rax, [rax+10h]
0x1800100d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d6  mov     rdx, [rsp+290h+ppidl]
0x1800100db  test    rdx, rdx
0x1800100de  jz      short loc_1800100F1
0x1800100e0  mov     rcx, [rsp+290h+ppMalloc]
0x1800100e5  mov     rax, [rcx]
0x1800100e8  mov     rax, [rax+28h]
0x1800100ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100f1  mov     rcx, [rsp+290h+ppMalloc]
0x1800100f6  test    rcx, rcx
0x1800100f9  jz      short loc_180010107
0x1800100fb  mov     rdx, [rcx]
0x1800100fe  mov     rax, [rdx+10h]
0x180010102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010107  mov     rcx, r14; hCursor
0x18001010a  call    cs:__imp_SetCursor
0x180010110  mov     eax, ebx
0x180010112  mov     rcx, [rbp+190h+var_20]
0x180010119  xor     rcx, rsp; StackCookie
0x18001011c  call    __security_check_cookie
0x180010121  lea     r11, [rsp+290h+var_10]
0x180010129  mov     rbx, [r11+28h]
0x18001012d  mov     rsi, [r11+30h]
0x180010131  mov     rsp, r11
0x180010134  pop     r14
0x180010136  pop     rdi
0x180010137  pop     rbp
0x180010138  retn
```
