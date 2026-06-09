# AboutDlgProc(x,x,x,x)

- ea: `0x1000f240`
- end: `0x1000f47b`
- name: `_AboutDlgProc@16`
- size: `571`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1000edb0`
- `0x1000f076`
- `0x1000f240`
- `0x10012b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x1000f300`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x1000f300`
- `GDI32!GetObjectA` at `0x1000f389`
- `GDI32!GetObjectA` at `0x1000f389`
- `GDI32!DeleteDC` at `0x1000f450`
- `GDI32!DeleteDC` at `0x1000f450`
- `GDI32!CreateCompatibleDC` at `0x1000f3b4`
- `GDI32!CreateCompatibleDC` at `0x1000f3b4`
- `GDI32!SelectObject` at `0x1000f3cd`
- `GDI32!SelectObject` at `0x1000f449`
- `GDI32!SelectObject` at `0x1000f3cd`
- `GDI32!SelectObject` at `0x1000f449`
- `GDI32!BitBlt` at `0x1000f43d`
- `GDI32!BitBlt` at `0x1000f43d`
- `GDI32!DeleteObject` at `0x1000f299`
- `GDI32!DeleteObject` at `0x1000f299`
- `USER32!EndPaint` at `0x1000f45c`
- `USER32!EndPaint` at `0x1000f45c`
- `USER32!GetDlgItem` at `0x1000f3dd`
- `USER32!GetDlgItem` at `0x1000f3dd`
- `USER32!SendDlgItemMessageA` at `0x1000f2e9`
- `USER32!SendDlgItemMessageA` at `0x1000f341`
- `USER32!SendDlgItemMessageA` at `0x1000f361`
- `USER32!SendDlgItemMessageA` at `0x1000f2e9`
- `USER32!SendDlgItemMessageA` at `0x1000f341`
- `USER32!SendDlgItemMessageA` at `0x1000f361`
- `USER32!SetWindowTextA` at `0x1000f2c7`
- `USER32!SetWindowTextA` at `0x1000f2c7`
- `USER32!LoadBitmapA` at `0x1000f372`
- `USER32!LoadBitmapA` at `0x1000f372`
- `USER32!EndDialog` at `0x1000f2a2`
- `USER32!EndDialog` at `0x1000f2a2`
- `USER32!BeginPaint` at `0x1000f39d`
- `USER32!BeginPaint` at `0x1000f39d`
- `USER32!GetWindowRect` at `0x1000f3e4`
- `USER32!GetWindowRect` at `0x1000f3e4`
- `USER32!ScreenToClient` at `0x1000f3f0`
- `USER32!ScreenToClient` at `0x1000f3fc`
- `USER32!ScreenToClient` at `0x1000f3f0`
- `USER32!ScreenToClient` at `0x1000f3fc`

## string_xrefs

- `0x1000f34c`: `LegalCopyright`
- `0x1000f367`: `SMACLOGO`

## pseudocode

```c
INT_PTR __stdcall AboutDlgProc(HWND hDlg, UINT a2, WPARAM a3, LPARAM a4)
{
  HRESULT v4; // eax
  int v5; // ecx
  HBITMAP BitmapA; // eax
  HDC CompatibleDC; // eax
  HGDIOBJ v9; // edi
  HWND DlgItem; // eax
  size_t v11; // [esp+0h] [ebp-F0h]
  size_t *v12; // [esp+4h] [ebp-ECh]
  HDC hdcSrc; // [esp+10h] [ebp-E0h]
  char psz[4]; // [esp+14h] [ebp-DCh] BYREF
  tagPAINTSTRUCT Paint; // [esp+18h] [ebp-D8h] BYREF
  struct tagRECT Rect; // [esp+58h] [ebp-98h] BYREF
  CHAR String[132]; // [esp+68h] [ebp-88h] BYREF

  if ( a2 == 15 )
  {
    BeginPaint(hDlg, &Paint);
    if ( h )
    {
      CompatibleDC = CreateCompatibleDC(Paint.hdc);
      hdcSrc = CompatibleDC;
      if ( CompatibleDC )
      {
        v9 = SelectObject(CompatibleDC, h);
        DlgItem = GetDlgItem(hDlg, 120);
        GetWindowRect(DlgItem, &Rect);
        ScreenToClient(hDlg, (LPPOINT)&Rect);
        ScreenToClient(hDlg, (LPPOINT)&Rect.right);
        Rect.left = (Rect.right - dword_10014998) >> 1;
        Rect.top = (Rect.top - cy) >> 1;
        BitBlt(Paint.hdc, Rect.left, Rect.top, dword_10014998, cy, hdcSrc, 0, 0, 0xCC0020u);
        SelectObject(hdcSrc, v9);
        DeleteDC(hdcSrc);
      }
    }
    EndPaint(hDlg, &Paint);
    return 0;
  }
  if ( a2 != 272 )
  {
    if ( a2 == 273 && (a3 == 1 || a3 == 2) )
    {
      if ( h )
        DeleteObject(h);
      EndDialog(hDlg, 0);
    }
    return 0;
  }
  GetDriverVersionInfo("ProductName", String, 128);
  SetWindowTextA(hDlg, String);
  GetDriverVersionInfo("FileDescription", String, 128);
  SendDlgItemMessageA(hDlg, 120, 0xCu, 0, (LPARAM)String);
  LoadStringA(ghModule, 0x2EE3u, String, 128);
  v4 = StringLengthWorkerA(psz, v11, v12);
  v5 = *(_DWORD *)psz;
  if ( v4 < 0 )
    v5 = 0;
  GetDriverVersionInfo("FileVersion", &String[v5], 128 - v5);
  SendDlgItemMessageA(hDlg, 121, 0xCu, 0, (LPARAM)String);
  GetDriverVersionInfo("LegalCopyright", String, 128);
  SendDlgItemMessageA(hDlg, 122, 0xCu, 0, (LPARAM)String);
  BitmapA = LoadBitmapA(ghModule, "SMACLOGO");
  h = BitmapA;
  if ( BitmapA )
    GetObjectA(BitmapA, 24, &dword_10014994);
  return 1;
}

```

## disassembly

```asm
0x1000f240  mov     edi, edi
0x1000f242  push    ebp
0x1000f243  mov     ebp, esp
0x1000f245  and     esp, 0FFFFFFF8h
0x1000f248  sub     esp, 0E4h
0x1000f24e  mov     eax, ___security_cookie
0x1000f253  xor     eax, esp
0x1000f255  mov     [esp+0E4h+var_4], eax
0x1000f25c  mov     eax, [ebp+arg_4]
0x1000f25f  push    ebx
0x1000f260  mov     ebx, [ebp+hDlg]
0x1000f263  push    esi; pcchLength
0x1000f264  push    edi; cchMax
0x1000f265  sub     eax, 0Fh
0x1000f268  jz      loc_1000F397
0x1000f26e  sub     eax, 101h
0x1000f273  jz      short loc_1000F2AD
0x1000f275  sub     eax, 1
0x1000f278  jnz     loc_1000F462
0x1000f27e  mov     eax, [ebp+arg_8]
0x1000f281  sub     eax, 1
0x1000f284  jz      short loc_1000F28F
0x1000f286  sub     eax, 1
0x1000f289  jnz     loc_1000F462
0x1000f28f  mov     eax, h
0x1000f294  test    eax, eax
0x1000f296  jz      short loc_1000F29F
0x1000f298  push    eax; ho
0x1000f299  call    ds:__imp__DeleteObject@4; DeleteObject(x)
0x1000f29f  push    0; nResult
0x1000f2a1  push    ebx; hDlg
0x1000f2a2  call    ds:__imp__EndDialog@8; EndDialog(x,x)
0x1000f2a8  jmp     loc_1000F462
0x1000f2ad  mov     edi, 80h
0x1000f2b2  lea     edx, [esp+0F0h+String]
0x1000f2b6  push    edi
0x1000f2b7  mov     ecx, offset aProductname; "ProductName"
0x1000f2bc  call    _GetDriverVersionInfo@12; GetDriverVersionInfo(x,x,x)
0x1000f2c1  lea     eax, [esp+0F0h+String]
0x1000f2c5  push    eax; lpString
0x1000f2c6  push    ebx; hWnd
0x1000f2c7  call    ds:__imp__SetWindowTextA@8; SetWindowTextA(x,x)
0x1000f2cd  push    edi
0x1000f2ce  lea     edx, [esp+0F4h+String]
0x1000f2d2  mov     ecx, offset aFiledescriptio; "FileDescription"
0x1000f2d7  call    _GetDriverVersionInfo@12; GetDriverVersionInfo(x,x,x)
0x1000f2dc  lea     eax, [esp+0F0h+String]
0x1000f2e0  xor     esi, esi
0x1000f2e2  push    eax; lParam
0x1000f2e3  push    esi; wParam
0x1000f2e4  push    0Ch; Msg
0x1000f2e6  push    78h ; 'x'; nIDDlgItem
0x1000f2e8  push    ebx; hDlg
0x1000f2e9  call    ds:__imp__SendDlgItemMessageA@20; SendDlgItemMessageA(x,x,x,x,x)
0x1000f2ef  push    edi; cchBufferMax
0x1000f2f0  lea     eax, [esp+0F4h+String]
0x1000f2f4  push    eax; lpBuffer
0x1000f2f5  push    2EE3h; uID
0x1000f2fa  push    _ghModule; hInstance
0x1000f300  call    ds:__imp__LoadStringA@16; LoadStringA(x,x,x,x)
0x1000f306  lea     eax, [esp+0F0h+psz]
0x1000f30a  mov     edx, edi
0x1000f30c  push    eax; psz
0x1000f30d  lea     ecx, [esp+0F4h+String]
0x1000f311  call    StringLengthWorkerA
0x1000f316  mov     ecx, dword ptr [esp+0F0h+psz]
0x1000f31a  xor     edx, edx
0x1000f31c  test    eax, eax
0x1000f31e  mov     eax, edi
0x1000f320  cmovs   ecx, edx
0x1000f323  lea     edx, [esp+0F0h+String]
0x1000f327  sub     eax, ecx
0x1000f329  add     edx, ecx
0x1000f32b  push    eax
0x1000f32c  mov     ecx, offset aFileversion; "FileVersion"
0x1000f331  call    _GetDriverVersionInfo@12; GetDriverVersionInfo(x,x,x)
0x1000f336  lea     eax, [esp+0F0h+String]
0x1000f33a  push    eax; lParam
0x1000f33b  push    esi; wParam
0x1000f33c  push    0Ch; Msg
0x1000f33e  push    79h ; 'y'; nIDDlgItem
0x1000f340  push    ebx; hDlg
0x1000f341  call    ds:__imp__SendDlgItemMessageA@20; SendDlgItemMessageA(x,x,x,x,x)
0x1000f347  push    edi
0x1000f348  lea     edx, [esp+0F4h+String]
0x1000f34c  mov     ecx, offset aLegalcopyright; "LegalCopyright"
0x1000f351  call    _GetDriverVersionInfo@12; GetDriverVersionInfo(x,x,x)
0x1000f356  lea     eax, [esp+0F0h+String]
0x1000f35a  push    eax; lParam
0x1000f35b  push    esi; wParam
0x1000f35c  push    0Ch; Msg
0x1000f35e  push    7Ah ; 'z'; nIDDlgItem
0x1000f360  push    ebx; hDlg
0x1000f361  call    ds:__imp__SendDlgItemMessageA@20; SendDlgItemMessageA(x,x,x,x,x)
0x1000f367  push    offset BitmapName; "SMACLOGO"
0x1000f36c  push    _ghModule; hInstance
0x1000f372  call    ds:__imp__LoadBitmapA@8; LoadBitmapA(x,x)
0x1000f378  mov     h, eax
0x1000f37d  test    eax, eax
0x1000f37f  jz      short loc_1000F38F
0x1000f381  push    offset dword_10014994; pv
0x1000f386  push    18h; c
0x1000f388  push    eax; h
0x1000f389  call    ds:__imp__GetObjectA@12; GetObjectA(x,x,x)
0x1000f38f  xor     eax, eax
0x1000f391  inc     eax
0x1000f392  jmp     loc_1000F464
0x1000f397  lea     eax, [esp+0F0h+Paint]
0x1000f39b  push    eax; lpPaint
0x1000f39c  push    ebx; hWnd
0x1000f39d  call    ds:__imp__BeginPaint@8; BeginPaint(x,x)
0x1000f3a3  cmp     h, 0
0x1000f3aa  jz      loc_1000F456
0x1000f3b0  push    [esp+0F0h+Paint.hdc]; hdc
0x1000f3b4  call    ds:__imp__CreateCompatibleDC@4; CreateCompatibleDC(x)
0x1000f3ba  mov     [esp+0F0h+hdcSrc], eax
0x1000f3be  test    eax, eax
0x1000f3c0  jz      loc_1000F456
0x1000f3c6  push    h; h
0x1000f3cc  push    eax; hdc
0x1000f3cd  call    ds:__imp__SelectObject@8; SelectObject(x,x)
0x1000f3d3  mov     edi, eax
0x1000f3d5  lea     eax, [esp+0F0h+Rect]
0x1000f3d9  push    eax; lpRect
0x1000f3da  push    78h ; 'x'; nIDDlgItem
0x1000f3dc  push    ebx; hDlg
0x1000f3dd  call    ds:__imp__GetDlgItem@8; GetDlgItem(x,x)
0x1000f3e3  push    eax; hWnd
0x1000f3e4  call    ds:__imp__GetWindowRect@8; GetWindowRect(x,x)
0x1000f3ea  lea     eax, [esp+0F0h+Rect]
0x1000f3ee  push    eax; lpPoint
0x1000f3ef  push    ebx; hWnd
0x1000f3f0  call    ds:__imp__ScreenToClient@8; ScreenToClient(x,x)
0x1000f3f6  lea     eax, [esp+0F0h+Rect.right]
0x1000f3fa  push    eax; lpPoint
0x1000f3fb  push    ebx; hWnd
0x1000f3fc  call    ds:__imp__ScreenToClient@8; ScreenToClient(x,x)
0x1000f402  mov     ecx, [esp+0F0h+Rect.top]
0x1000f406  mov     eax, cy
0x1000f40b  sub     ecx, eax
0x1000f40d  mov     esi, [esp+0F0h+Rect.right]
0x1000f411  mov     edx, dword_10014998
0x1000f417  sub     esi, edx
0x1000f419  push    0CC0020h; rop
0x1000f41e  push    0; y1
0x1000f420  push    0; x1
0x1000f422  push    [esp+0FCh+hdcSrc]; hdcSrc
0x1000f426  sar     ecx, 1
0x1000f428  push    eax; cy
0x1000f429  push    edx; cx
0x1000f42a  push    ecx; y
0x1000f42b  sar     esi, 1
0x1000f42d  push    esi; x
0x1000f42e  push    [esp+110h+Paint.hdc]; hdc
0x1000f432  mov     [esp+114h+Rect.left], esi
0x1000f436  mov     [esp+114h+Rect.top], ecx
0x1000f43d  call    ds:__imp__BitBlt@36; BitBlt(x,x,x,x,x,x,x,x,x)
0x1000f443  mov     esi, [esp+0F0h+hdcSrc]
0x1000f447  push    edi; h
0x1000f448  push    esi; hdc
0x1000f449  call    ds:__imp__SelectObject@8; SelectObject(x,x)
0x1000f44f  push    esi; hdc
0x1000f450  call    ds:__imp__DeleteDC@4; DeleteDC(x)
0x1000f456  lea     eax, [esp+0F0h+Paint]
0x1000f45a  push    eax; lpPaint
0x1000f45b  push    ebx; hWnd
0x1000f45c  call    ds:__imp__EndPaint@8; EndPaint(x,x)
0x1000f462  xor     eax, eax
0x1000f464  mov     ecx, [esp+0F0h+var_4]
0x1000f46b  pop     edi
0x1000f46c  pop     esi
0x1000f46d  pop     ebx
0x1000f46e  xor     ecx, esp; StackCookie
0x1000f470  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000f475  mov     esp, ebp
0x1000f477  pop     ebp
0x1000f478  retn    10h
```
