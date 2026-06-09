# ConfigureDlgProc(x,x,x,x)

- ea: `0x1000f4d0`
- end: `0x1000f754`
- name: `_ConfigureDlgProc@16`
- size: `644`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1000edb0`
- `0x1000f076`
- `0x1000f4d0`
- `0x10012b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x1000f5a8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringA` at `0x1000f5a8`
- `GDI32!GetObjectA` at `0x1000f672`
- `GDI32!GetObjectA` at `0x1000f672`
- `GDI32!DeleteDC` at `0x1000f71e`
- `GDI32!DeleteDC` at `0x1000f71e`
- `GDI32!CreateCompatibleDC` at `0x1000f688`
- `GDI32!CreateCompatibleDC` at `0x1000f688`
- `GDI32!SelectObject` at `0x1000f69c`
- `GDI32!SelectObject` at `0x1000f717`
- `GDI32!SelectObject` at `0x1000f69c`
- `GDI32!SelectObject` at `0x1000f717`
- `GDI32!BitBlt` at `0x1000f70f`
- `GDI32!BitBlt` at `0x1000f70f`
- `GDI32!DeleteObject` at `0x1000f735`
- `GDI32!DeleteObject` at `0x1000f735`
- `USER32!EndPaint` at `0x1000f72e`
- `USER32!EndPaint` at `0x1000f72e`
- `USER32!GetDlgItem` at `0x1000f6ac`
- `USER32!GetDlgItem` at `0x1000f6ac`
- `USER32!SendDlgItemMessageA` at `0x1000f52f`
- `USER32!SendDlgItemMessageA` at `0x1000f58e`
- `USER32!SendDlgItemMessageA` at `0x1000f5f2`
- `USER32!SendDlgItemMessageA` at `0x1000f618`
- `USER32!SendDlgItemMessageA` at `0x1000f629`
- `USER32!SendDlgItemMessageA` at `0x1000f63d`
- `USER32!SendDlgItemMessageA` at `0x1000f52f`
- `USER32!SendDlgItemMessageA` at `0x1000f58e`
- `USER32!SendDlgItemMessageA` at `0x1000f5f2`
- `USER32!SendDlgItemMessageA` at `0x1000f618`
- `USER32!SendDlgItemMessageA` at `0x1000f629`
- `USER32!SendDlgItemMessageA` at `0x1000f63d`
- `USER32!SetWindowTextA` at `0x1000f568`
- `USER32!SetWindowTextA` at `0x1000f568`
- `USER32!LoadBitmapA` at `0x1000f656`
- `USER32!LoadBitmapA` at `0x1000f656`
- `USER32!EndDialog` at `0x1000f537`
- `USER32!EndDialog` at `0x1000f537`
- `USER32!BeginPaint` at `0x1000f67e`
- `USER32!BeginPaint` at `0x1000f67e`
- `USER32!GetWindowRect` at `0x1000f6b3`
- `USER32!GetWindowRect` at `0x1000f6b3`
- `USER32!ScreenToClient` at `0x1000f6bf`
- `USER32!ScreenToClient` at `0x1000f6cb`
- `USER32!ScreenToClient` at `0x1000f6bf`
- `USER32!ScreenToClient` at `0x1000f6cb`

## string_xrefs

- `0x1000f600`: `LegalCopyright`
- `0x1000f64b`: `SMACLOGO`

## pseudocode

```c
INT_PTR __stdcall ConfigureDlgProc(HWND hDlg, UINT a2, WPARAM a3, WPARAM a4)
{
  HRESULT v4; // eax
  int v5; // ecx
  HBITMAP BitmapA; // ebx
  HDC CompatibleDC; // eax
  HGDIOBJ v9; // esi
  HWND DlgItem; // eax
  LRESULT v11; // [esp-4h] [ebp-10Ch]
  size_t v12; // [esp+0h] [ebp-108h]
  size_t *v13; // [esp+4h] [ebp-104h]
  char psz[4]; // [esp+Ch] [ebp-FCh] BYREF
  HDC hdcSrc; // [esp+10h] [ebp-F8h]
  HBITMAP v16; // [esp+14h] [ebp-F4h]
  _BYTE pv[4]; // [esp+18h] [ebp-F0h] BYREF
  int v18; // [esp+1Ch] [ebp-ECh]
  int cy; // [esp+20h] [ebp-E8h]
  struct tagPAINTSTRUCT Paint; // [esp+30h] [ebp-D8h] BYREF
  struct tagRECT Rect; // [esp+70h] [ebp-98h] BYREF
  CHAR String[132]; // [esp+80h] [ebp-88h] BYREF

  if ( a2 == 15 )
  {
    BitmapA = LoadBitmapA(ghModule, "SMACLOGO");
    v16 = BitmapA;
    if ( BitmapA )
    {
      GetObjectA(BitmapA, 24, pv);
      BeginPaint(hDlg, &Paint);
      CompatibleDC = CreateCompatibleDC(Paint.hdc);
      hdcSrc = CompatibleDC;
      if ( CompatibleDC )
      {
        v9 = SelectObject(CompatibleDC, BitmapA);
        DlgItem = GetDlgItem(hDlg, 120);
        GetWindowRect(DlgItem, &Rect);
        ScreenToClient(hDlg, (LPPOINT)&Rect);
        ScreenToClient(hDlg, (LPPOINT)&Rect.right);
        Rect.left = (Rect.right - v18) >> 1;
        Rect.top = (Rect.top - cy) >> 1;
        BitBlt(Paint.hdc, Rect.left, Rect.top, v18, cy, hdcSrc, 0, 0, 0xCC0020u);
        SelectObject(hdcSrc, v9);
        DeleteDC(hdcSrc);
        BitmapA = v16;
      }
      EndPaint(hDlg, &Paint);
      DeleteObject(BitmapA);
    }
    return 0;
  }
  if ( a2 != 272 )
  {
    if ( a2 == 273 )
    {
      if ( a3 == 1 )
      {
        v11 = SendDlgItemMessageA(hDlg, 102, 0xF0u, 0, 0);
        EndDialog(hDlg, v11);
      }
      else if ( a3 == 2 )
      {
        EndDialog(hDlg, 2);
      }
    }
    return 0;
  }
  *(_DWORD *)psz = 0;
  GetDriverVersionInfo("ProductName", String, 128);
  SetWindowTextA(hDlg, String);
  GetDriverVersionInfo("FileDescription", String, 128);
  SendDlgItemMessageA(hDlg, 120, 0xCu, 0, (LPARAM)String);
  LoadStringA(ghModule, 0x2EE3u, String, 128);
  v4 = StringLengthWorkerA(psz, v12, v13);
  v5 = *(_DWORD *)psz;
  if ( v4 < 0 )
    v5 = 0;
  GetDriverVersionInfo("FileVersion", &String[v5], 128 - v5);
  SendDlgItemMessageA(hDlg, 121, 0xCu, 0, (LPARAM)String);
  GetDriverVersionInfo("LegalCopyright", String, 128);
  SendDlgItemMessageA(hDlg, 122, 0xCu, 0, (LPARAM)String);
  SendDlgItemMessageA(hDlg, 102, 0xF1u, a4, 0);
  SendDlgItemMessageA(hDlg, 101, 0xF1u, a4 == 0, 0);
  return 1;
}

```

## disassembly

```asm
0x1000f4d0  mov     edi, edi
0x1000f4d2  push    ebp
0x1000f4d3  mov     ebp, esp
0x1000f4d5  and     esp, 0FFFFFFF8h
0x1000f4d8  sub     esp, 0FCh
0x1000f4de  mov     eax, ___security_cookie
0x1000f4e3  xor     eax, esp
0x1000f4e5  mov     [esp+0FCh+var_4], eax
0x1000f4ec  mov     eax, [ebp+arg_4]
0x1000f4ef  push    ebx
0x1000f4f0  push    esi; pcchLength
0x1000f4f1  push    edi; cchMax
0x1000f4f2  mov     edi, [ebp+hDlg]
0x1000f4f5  sub     eax, 0Fh
0x1000f4f8  jz      loc_1000F64B
0x1000f4fe  sub     eax, 101h
0x1000f503  jz      short loc_1000F542
0x1000f505  sub     eax, 1
0x1000f508  jnz     loc_1000F73B
0x1000f50e  mov     eax, [ebp+arg_8]
0x1000f511  sub     eax, 1
0x1000f514  jz      short loc_1000F523
0x1000f516  sub     eax, 1
0x1000f519  jnz     loc_1000F73B
0x1000f51f  push    2
0x1000f521  jmp     short loc_1000F536
0x1000f523  xor     ebx, ebx
0x1000f525  push    ebx; lParam
0x1000f526  push    ebx; wParam
0x1000f527  push    0F0h; Msg
0x1000f52c  push    66h ; 'f'; nIDDlgItem
0x1000f52e  push    edi; hDlg
0x1000f52f  call    ds:__imp__SendDlgItemMessageA@20; SendDlgItemMessageA(x,x,x,x,x)
0x1000f535  push    eax; nResult
0x1000f536  push    edi; hDlg
0x1000f537  call    ds:__imp__EndDialog@8; EndDialog(x,x)
0x1000f53d  jmp     loc_1000F73B
0x1000f542  mov     esi, 80h
0x1000f547  lea     edx, [esp+108h+String]
0x1000f54e  xor     ebx, ebx
0x1000f550  mov     ecx, offset aProductname; "ProductName"
0x1000f555  push    esi
0x1000f556  mov     dword ptr [esp+10Ch+psz], ebx
0x1000f55a  call    _GetDriverVersionInfo@12; GetDriverVersionInfo(x,x,x)
0x1000f55f  lea     eax, [esp+108h+String]
0x1000f566  push    eax; lpString
0x1000f567  push    edi; hWnd
0x1000f568  call    ds:__imp__SetWindowTextA@8; SetWindowTextA(x,x)
0x1000f56e  push    esi
0x1000f56f  lea     edx, [esp+10Ch+String]
0x1000f576  mov     ecx, offset aFiledescriptio; "FileDescription"
0x1000f57b  call    _GetDriverVersionInfo@12; GetDriverVersionInfo(x,x,x)
0x1000f580  lea     eax, [esp+108h+String]
0x1000f587  push    eax; lParam
0x1000f588  push    ebx; wParam
0x1000f589  push    0Ch; Msg
0x1000f58b  push    78h ; 'x'; nIDDlgItem
0x1000f58d  push    edi; hDlg
0x1000f58e  call    ds:__imp__SendDlgItemMessageA@20; SendDlgItemMessageA(x,x,x,x,x)
0x1000f594  push    esi; cchBufferMax
0x1000f595  lea     eax, [esp+10Ch+String]
0x1000f59c  push    eax; lpBuffer
0x1000f59d  push    2EE3h; uID
0x1000f5a2  push    _ghModule; hInstance
0x1000f5a8  call    ds:__imp__LoadStringA@16; LoadStringA(x,x,x,x)
0x1000f5ae  lea     eax, [esp+108h+psz]
0x1000f5b2  mov     edx, esi
0x1000f5b4  push    eax; psz
0x1000f5b5  lea     ecx, [esp+10Ch+String]
0x1000f5bc  call    StringLengthWorkerA
0x1000f5c1  mov     ecx, dword ptr [esp+108h+psz]
0x1000f5c5  xor     edx, edx
0x1000f5c7  test    eax, eax
0x1000f5c9  mov     eax, esi
0x1000f5cb  cmovs   ecx, edx
0x1000f5ce  lea     edx, [esp+108h+String]
0x1000f5d5  sub     eax, ecx
0x1000f5d7  add     edx, ecx
0x1000f5d9  push    eax
0x1000f5da  mov     ecx, offset aFileversion; "FileVersion"
0x1000f5df  call    _GetDriverVersionInfo@12; GetDriverVersionInfo(x,x,x)
0x1000f5e4  lea     eax, [esp+108h+String]
0x1000f5eb  push    eax; lParam
0x1000f5ec  push    ebx; wParam
0x1000f5ed  push    0Ch; Msg
0x1000f5ef  push    79h ; 'y'; nIDDlgItem
0x1000f5f1  push    edi; hDlg
0x1000f5f2  call    ds:__imp__SendDlgItemMessageA@20; SendDlgItemMessageA(x,x,x,x,x)
0x1000f5f8  push    esi
0x1000f5f9  lea     edx, [esp+10Ch+String]
0x1000f600  mov     ecx, offset aLegalcopyright; "LegalCopyright"
0x1000f605  call    _GetDriverVersionInfo@12; GetDriverVersionInfo(x,x,x)
0x1000f60a  lea     eax, [esp+108h+String]
0x1000f611  push    eax; lParam
0x1000f612  push    ebx; wParam
0x1000f613  push    0Ch; Msg
0x1000f615  push    7Ah ; 'z'; nIDDlgItem
0x1000f617  push    edi; hDlg
0x1000f618  call    ds:__imp__SendDlgItemMessageA@20; SendDlgItemMessageA(x,x,x,x,x)
0x1000f61e  push    ebx; lParam
0x1000f61f  push    [ebp+arg_C]; wParam
0x1000f622  add     esi, 71h ; 'q'
0x1000f625  push    esi; Msg
0x1000f626  push    66h ; 'f'; nIDDlgItem
0x1000f628  push    edi; hDlg
0x1000f629  call    ds:__imp__SendDlgItemMessageA@20; SendDlgItemMessageA(x,x,x,x,x)
0x1000f62f  xor     eax, eax
0x1000f631  cmp     [ebp+arg_C], eax
0x1000f634  push    ebx; lParam
0x1000f635  setz    al
0x1000f638  push    eax; wParam
0x1000f639  push    esi; Msg
0x1000f63a  push    65h ; 'e'; nIDDlgItem
0x1000f63c  push    edi; hDlg
0x1000f63d  call    ds:__imp__SendDlgItemMessageA@20; SendDlgItemMessageA(x,x,x,x,x)
0x1000f643  xor     eax, eax
0x1000f645  inc     eax
0x1000f646  jmp     loc_1000F73D
0x1000f64b  push    offset BitmapName; "SMACLOGO"
0x1000f650  push    _ghModule; hInstance
0x1000f656  call    ds:__imp__LoadBitmapA@8; LoadBitmapA(x,x)
0x1000f65c  mov     ebx, eax
0x1000f65e  mov     [esp+108h+var_F4], ebx
0x1000f662  test    ebx, ebx
0x1000f664  jz      loc_1000F73B
0x1000f66a  lea     eax, [esp+108h+pv]
0x1000f66e  push    eax; pv
0x1000f66f  push    18h; c
0x1000f671  push    ebx; h
0x1000f672  call    ds:__imp__GetObjectA@12; GetObjectA(x,x,x)
0x1000f678  lea     eax, [esp+108h+Paint]
0x1000f67c  push    eax; lpPaint
0x1000f67d  push    edi; hWnd
0x1000f67e  call    ds:__imp__BeginPaint@8; BeginPaint(x,x)
0x1000f684  push    [esp+108h+Paint.hdc]; hdc
0x1000f688  call    ds:__imp__CreateCompatibleDC@4; CreateCompatibleDC(x)
0x1000f68e  mov     [esp+108h+hdcSrc], eax
0x1000f692  test    eax, eax
0x1000f694  jz      loc_1000F728
0x1000f69a  push    ebx; h
0x1000f69b  push    eax; hdc
0x1000f69c  call    ds:__imp__SelectObject@8; SelectObject(x,x)
0x1000f6a2  mov     esi, eax
0x1000f6a4  lea     eax, [esp+108h+Rect]
0x1000f6a8  push    eax; lpRect
0x1000f6a9  push    78h ; 'x'; nIDDlgItem
0x1000f6ab  push    edi; hDlg
0x1000f6ac  call    ds:__imp__GetDlgItem@8; GetDlgItem(x,x)
0x1000f6b2  push    eax; hWnd
0x1000f6b3  call    ds:__imp__GetWindowRect@8; GetWindowRect(x,x)
0x1000f6b9  lea     eax, [esp+108h+Rect]
0x1000f6bd  push    eax; lpPoint
0x1000f6be  push    edi; hWnd
0x1000f6bf  call    ds:__imp__ScreenToClient@8; ScreenToClient(x,x)
0x1000f6c5  lea     eax, [esp+108h+Rect.right]
0x1000f6c9  push    eax; lpPoint
0x1000f6ca  push    edi; hWnd
0x1000f6cb  call    ds:__imp__ScreenToClient@8; ScreenToClient(x,x)
0x1000f6d1  mov     eax, [esp+108h+Rect.top]
0x1000f6d5  xor     ebx, ebx
0x1000f6d7  mov     ecx, [esp+108h+Rect.right]
0x1000f6db  sub     eax, [esp+108h+cy]
0x1000f6df  sub     ecx, [esp+108h+var_EC]
0x1000f6e3  push    0CC0020h; rop
0x1000f6e8  push    ebx; y1
0x1000f6e9  push    ebx; x1
0x1000f6ea  mov     ebx, [esp+114h+hdcSrc]
0x1000f6ee  push    ebx; hdcSrc
0x1000f6ef  push    [esp+118h+cy]; cy
0x1000f6f3  sar     eax, 1
0x1000f6f5  push    [esp+11Ch+var_EC]; cx
0x1000f6f9  sar     ecx, 1
0x1000f6fb  push    eax; y
0x1000f6fc  push    ecx; x
0x1000f6fd  push    [esp+128h+Paint.hdc]; hdc
0x1000f701  mov     [esp+12Ch+Rect.left], ecx
0x1000f708  mov     [esp+12Ch+Rect.top], eax
0x1000f70f  call    ds:__imp__BitBlt@36; BitBlt(x,x,x,x,x,x,x,x,x)
0x1000f715  push    esi; h
0x1000f716  push    ebx; hdc
0x1000f717  call    ds:__imp__SelectObject@8; SelectObject(x,x)
0x1000f71d  push    ebx; hdc
0x1000f71e  call    ds:__imp__DeleteDC@4; DeleteDC(x)
0x1000f724  mov     ebx, [esp+108h+var_F4]
0x1000f728  lea     eax, [esp+108h+Paint]
0x1000f72c  push    eax; lpPaint
0x1000f72d  push    edi; hWnd
0x1000f72e  call    ds:__imp__EndPaint@8; EndPaint(x,x)
0x1000f734  push    ebx; ho
0x1000f735  call    ds:__imp__DeleteObject@4; DeleteObject(x)
0x1000f73b  xor     eax, eax
0x1000f73d  mov     ecx, [esp+108h+var_4]
0x1000f744  pop     edi
0x1000f745  pop     esi
0x1000f746  pop     ebx
0x1000f747  xor     ecx, esp; StackCookie
0x1000f749  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000f74e  mov     esp, ebp
0x1000f750  pop     ebp
0x1000f751  retn    10h
```
