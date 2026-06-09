# CuipPaintDesktop(HDC__ *)

- ea: `0x140007250`
- end: `0x140007485`
- name: `?CuipPaintDesktop@@YAXPEAUHDC__@@@Z`
- size: `565`
- prototype: `void __fastcall(HDC hdc)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140006d00`

## callees

- `0x140007250`
- `0x14001e050`

## import_xrefs

- `GDI32!SelectObject` at `0x1400073c5`
- `GDI32!SelectObject` at `0x140007401`
- `GDI32!SelectObject` at `0x1400073c5`
- `GDI32!SelectObject` at `0x140007401`
- `GDI32!DeleteDC` at `0x14000740a`
- `GDI32!DeleteDC` at `0x14000740a`
- `GDI32!CreateDIBSection` at `0x1400073a1`
- `GDI32!CreateDIBSection` at `0x1400073a1`
- `GDI32!DeleteObject` at `0x140007413`
- `GDI32!DeleteObject` at `0x140007413`
- `GDI32!CreateCompatibleDC` at `0x1400073b1`
- `GDI32!CreateCompatibleDC` at `0x1400073b1`
- `GDI32!PatBlt` at `0x140007457`
- `GDI32!PatBlt` at `0x140007457`
- `GDI32!BitBlt` at `0x1400073f3`
- `GDI32!BitBlt` at `0x1400073f3`
- `USER32!SendMessageTimeoutW` at `0x140007339`
- `USER32!SendMessageTimeoutW` at `0x140007339`
- `USER32!GetWindowRect` at `0x14000729b`
- `USER32!GetWindowRect` at `0x14000729b`
- `USER32!GetShellWindow` at `0x140007279`
- `USER32!GetShellWindow` at `0x140007279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000741c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000741c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1400072e1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1400072e1`

## pseudocode

```c
void __fastcall CuipPaintDesktop(HDC hdc)
{
  HWND ShellWindow; // rax
  HWND v3; // rbx
  LONG v4; // r15d
  LONG v5; // r14d
  DWORD dwMaximumSizeLow; // edi
  HANDLE FileMappingW; // rsi
  BOOL v8; // ebp
  HBITMAP v9; // r13
  HDC CompatibleDC; // rax
  HDC v11; // rdi
  HGDIOBJ v12; // rbx
  ULONG_PTR dwResult; // [rsp+50h] [rbp-88h] BYREF
  void *ppvBits; // [rsp+58h] [rbp-80h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp-78h] BYREF
  BITMAPINFO pbmi; // [rsp+70h] [rbp-68h] BYREF

  ShellWindow = GetShellWindow();
  v3 = ShellWindow;
  if ( !ShellWindow )
    goto LABEL_10;
  Rect = 0;
  GetWindowRect(ShellWindow, &Rect);
  v4 = Rect.bottom - Rect.top;
  v5 = Rect.right - Rect.left;
  dwMaximumSizeLow = 4 * (Rect.right - Rect.left) * (Rect.bottom - Rect.top);
  FileMappingW = CreateFileMappingW(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   0,
                   4u,
                   0,
                   dwMaximumSizeLow,
                   L"Local\\Microsoft-Windows-DesktopBackground");
  if ( !FileMappingW )
    goto LABEL_10;
  v8 = 0;
  dwResult = 0;
  if ( SendMessageTimeoutW(v3, 0x34u, 6u, dwMaximumSizeLow, 2u, 0xBB8u, &dwResult) )
  {
    if ( dwResult )
    {
      pbmi.bmiHeader.biSize = 40;
      pbmi.bmiHeader.biWidth = v5;
      pbmi.bmiHeader.biHeight = v4;
      memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
      *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
      ppvBits = 0;
      v9 = CreateDIBSection(hdc, &pbmi, 0, &ppvBits, FileMappingW, 0);
      if ( v9 )
      {
        CompatibleDC = CreateCompatibleDC(0);
        v11 = CompatibleDC;
        if ( CompatibleDC )
        {
          v12 = SelectObject(CompatibleDC, v9);
          v8 = BitBlt(hdc, 0, 0, v5, v4, v11, 0, 0, 0xCC0020u);
          SelectObject(v11, v12);
          DeleteDC(v11);
        }
        DeleteObject(v9);
      }
    }
  }
  CloseHandle(FileMappingW);
  if ( !v8 )
LABEL_10:
    PatBlt(hdc, 0, 0, nWidth, nHeight, 0x42u);
}

```

## disassembly

```asm
0x140007250  mov     [rsp+arg_18], rbx
0x140007255  push    rsi
0x140007256  push    rdi
0x140007257  push    r12
0x140007259  push    r14
0x14000725b  push    r15
0x14000725d  sub     rsp, 0B0h
0x140007264  mov     rax, cs:__security_cookie
0x14000726b  xor     rax, rsp
0x14000726e  mov     [rsp+0D8h+var_38], rax
0x140007276  mov     r12, rcx
0x140007279  call    cs:__imp_GetShellWindow
0x14000727f  mov     rbx, rax
0x140007282  test    rax, rax
0x140007285  jz      loc_140007436
0x14000728b  xorps   xmm0, xmm0
0x14000728e  lea     rdx, [rsp+0D8h+Rect]; lpRect
0x140007293  mov     rcx, rax; hWnd
0x140007296  movups  xmmword ptr [rsp+0D8h+Rect.left], xmm0
0x14000729b  call    cs:__imp_GetWindowRect
0x1400072a1  mov     r15d, [rsp+0D8h+Rect.bottom]
0x1400072a6  lea     rax, Name; "Local\\Microsoft-Windows-DesktopBackgro"...
0x1400072ad  sub     r15d, [rsp+0D8h+Rect.top]
0x1400072b2  xor     r9d, r9d; dwMaximumSizeHigh
0x1400072b5  mov     r14d, [rsp+0D8h+Rect.right]
0x1400072ba  mov     edi, r15d
0x1400072bd  sub     r14d, [rsp+0D8h+Rect.left]
0x1400072c2  xor     edx, edx; lpFileMappingAttributes
0x1400072c4  mov     [rsp+0D8h+lpName], rax; lpName
0x1400072c9  mov     rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1400072d0  imul    edi, r14d
0x1400072d4  mov     r8d, 4; flProtect
0x1400072da  shl     edi, 2
0x1400072dd  mov     [rsp+0D8h+dwMaximumSizeLow], edi; dwMaximumSizeLow
0x1400072e1  call    cs:__imp_CreateFileMappingW
0x1400072e7  mov     rsi, rax
0x1400072ea  test    rax, rax
0x1400072ed  jz      loc_140007436
0x1400072f3  mov     [rsp+0D8h+arg_8], rbp
0x1400072fb  lea     rax, [rsp+0D8h+dwResult]
0x140007300  mov     [rsp+0D8h+lpdwResult], rax; lpdwResult
0x140007305  mov     edx, 34h ; '4'; Msg
0x14000730a  mov     [rsp+0D8h+arg_10], r13
0x140007312  mov     r8d, 6; wParam
0x140007318  xor     r13d, r13d
0x14000731b  mov     dword ptr [rsp+0D8h+lpName], 0BB8h; uTimeout
0x140007323  mov     r9d, edi; lParam
0x140007326  mov     rcx, rbx; hWnd
0x140007329  mov     ebp, r13d
0x14000732c  mov     [rsp+0D8h+dwResult], r13
0x140007331  mov     [rsp+0D8h+dwMaximumSizeLow], 2; fuFlags
0x140007339  call    cs:__imp_SendMessageTimeoutW
0x14000733f  test    rax, rax
0x140007342  jz      loc_140007419
0x140007348  cmp     [rsp+0D8h+dwResult], rbp
0x14000734d  jz      loc_140007419
0x140007353  xorps   xmm0, xmm0
0x140007356  mov     dword ptr [rsp+0D8h+lpName], r13d; offset
0x14000735b  lea     r9, [rsp+0D8h+ppvBits]; ppvBits
0x140007360  mov     qword ptr [rsp+0D8h+pbmi.bmiHeader.biClrImportant], r13
0x140007368  xor     r8d, r8d; usage
0x14000736b  mov     [rsp+0D8h+pbmi.bmiHeader.biSize], 28h ; '('
0x140007373  lea     rdx, [rsp+0D8h+pbmi]; pbmi
0x140007378  mov     [rsp+0D8h+pbmi.bmiHeader.biWidth], r14d
0x14000737d  mov     rcx, r12; hdc
0x140007380  mov     [rsp+0D8h+pbmi.bmiHeader.biHeight], r15d
0x140007385  movdqu  xmmword ptr [rsp+0D8h+pbmi.bmiHeader.biSizeImage], xmm0
0x14000738e  mov     qword ptr [rsp+0D8h+pbmi.bmiHeader.biPlanes], 200001h
0x140007397  mov     [rsp+0D8h+ppvBits], r13
0x14000739c  mov     qword ptr [rsp+0D8h+dwMaximumSizeLow], rsi; hSection
0x1400073a1  call    cs:__imp_CreateDIBSection
0x1400073a7  mov     r13, rax
0x1400073aa  test    rax, rax
0x1400073ad  jz      short loc_140007419
0x1400073af  xor     ecx, ecx; hdc
0x1400073b1  call    cs:__imp_CreateCompatibleDC
0x1400073b7  mov     rdi, rax
0x1400073ba  test    rax, rax
0x1400073bd  jz      short loc_140007410
0x1400073bf  mov     rdx, r13; h
0x1400073c2  mov     rcx, rax; hdc
0x1400073c5  call    cs:__imp_SelectObject
0x1400073cb  mov     [rsp+0D8h+rop], 0CC0020h; rop
0x1400073d3  mov     r9d, r14d; cx
0x1400073d6  mov     [rsp+0D8h+y1], ebp; y1
0x1400073da  xor     r8d, r8d; y
0x1400073dd  mov     dword ptr [rsp+0D8h+lpdwResult], ebp; x1
0x1400073e1  xor     edx, edx; x
0x1400073e3  mov     [rsp+0D8h+lpName], rdi; hdcSrc
0x1400073e8  mov     rcx, r12; hdc
0x1400073eb  mov     [rsp+0D8h+dwMaximumSizeLow], r15d; cy
0x1400073f0  mov     rbx, rax
0x1400073f3  call    cs:__imp_BitBlt
0x1400073f9  mov     rdx, rbx; h
0x1400073fc  mov     rcx, rdi; hdc
0x1400073ff  mov     ebp, eax
0x140007401  call    cs:__imp_SelectObject
0x140007407  mov     rcx, rdi; hdc
0x14000740a  call    cs:__imp_DeleteDC
0x140007410  mov     rcx, r13; ho
0x140007413  call    cs:__imp_DeleteObject
0x140007419  mov     rcx, rsi; hObject
0x14000741c  call    cs:__imp_CloseHandle
0x140007422  mov     r13, [rsp+0D8h+arg_10]
0x14000742a  test    ebp, ebp
0x14000742c  mov     rbp, [rsp+0D8h+arg_8]
0x140007434  jnz     short loc_14000745D
0x140007436  mov     eax, cs:nHeight
0x14000743c  xor     r8d, r8d; y
0x14000743f  mov     r9d, cs:nWidth; w
0x140007446  xor     edx, edx; x
0x140007448  mov     dword ptr [rsp+0D8h+lpName], 42h ; 'B'; rop
0x140007450  mov     rcx, r12; hdc
0x140007453  mov     [rsp+0D8h+dwMaximumSizeLow], eax; h
0x140007457  call    cs:__imp_PatBlt
0x14000745d  mov     rcx, [rsp+0D8h+var_38]
0x140007465  xor     rcx, rsp; StackCookie
0x140007468  call    __security_check_cookie
0x14000746d  mov     rbx, [rsp+0D8h+arg_18]
0x140007475  add     rsp, 0B0h
0x14000747c  pop     r15
0x14000747e  pop     r14
0x140007480  pop     r12
0x140007482  pop     rdi
0x140007483  pop     rsi
0x140007484  retn
```
