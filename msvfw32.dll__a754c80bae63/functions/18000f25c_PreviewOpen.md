# PreviewOpen

- ea: `0x18000f25c`
- end: `0x18000f381`
- name: `PreviewOpen`
- size: `293`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ed20`

## callees

- `0x1800014b0`
- `0x180001d62`
- `0x180010730`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x18000f353`
- `GDI32!CreateFontIndirectW` at `0x18000f353`
- `USER32!ScreenToClient` at `0x18000f307`
- `USER32!ScreenToClient` at `0x18000f314`
- `USER32!ScreenToClient` at `0x18000f307`
- `USER32!ScreenToClient` at `0x18000f314`
- `USER32!GetClientRect` at `0x18000f2df`
- `USER32!GetClientRect` at `0x18000f2df`
- `USER32!GetDlgItem` at `0x18000f2ed`
- `USER32!GetDlgItem` at `0x18000f2ed`
- `USER32!GetWindowRect` at `0x18000f2fa`
- `USER32!GetWindowRect` at `0x18000f2fa`
- `USER32!SystemParametersInfoW` at `0x18000f349`
- `USER32!SystemParametersInfoW` at `0x18000f349`
- `USER32!SetPropW` at `0x18000f2b3`
- `USER32!SetPropW` at `0x18000f2b3`

## pseudocode

```c
__int64 __fastcall PreviewOpen(HWND hWnd, __int64 a2)
{
  __int64 v4; // rsi
  HWND DlgItem; // rax
  struct tagRECT Rect; // [rsp+20h] [rbp-39h] BYREF
  LOGFONTW pvParam; // [rsp+30h] [rbp-29h] BYREF

  memset_0(&pvParam, 0, sizeof(pvParam));
  v4 = *(_QWORD *)(a2 + 112);
  Rect = 0;
  *(_QWORD *)(a2 + 112) = *(_QWORD *)(v4 + 24);
  SetPropW(hWnd, L"PreviewStuff", (HANDLE)v4);
  *(_QWORD *)(v4 + 8) = hWnd;
  *(_QWORD *)(v4 + 16) = a2;
  *(_QWORD *)(v4 + 96) = MCIWndCreateW(hWnd, 0, 0x40804008u, 0);
  GetClientRect(hWnd, (LPRECT)(v4 + 48));
  DlgItem = GetDlgItem(hWnd, 2);
  GetWindowRect(DlgItem, &Rect);
  ScreenToClient(hWnd, (LPPOINT)&Rect);
  ScreenToClient(hWnd, (LPPOINT)&Rect.right);
  *(_DWORD *)(v4 + 52) = Rect.bottom + 4;
  *(_DWORD *)(v4 + 48) = Rect.left;
  *(_DWORD *)(v4 + 56) = Rect.right;
  *(_DWORD *)(v4 + 60) += Rect.top - Rect.bottom - 12;
  SystemParametersInfoW(0x1Fu, 0x5Cu, &pvParam, 0);
  *(_QWORD *)(v4 + 104) = CreateFontIndirectW(&pvParam);
  return 1;
}

```

## disassembly

```asm
0x18000f25c  mov     [rsp-8+arg_10], rbx
0x18000f261  push    rbp
0x18000f262  push    rsi
0x18000f263  push    rdi
0x18000f264  lea     rbp, [rsp-47h]
0x18000f269  sub     rsp, 0A0h
0x18000f270  mov     rax, cs:__security_cookie
0x18000f277  xor     rax, rsp
0x18000f27a  mov     [rbp+57h+var_20], rax
0x18000f27e  mov     rbx, rdx
0x18000f281  mov     rdi, rcx
0x18000f284  xor     edx, edx; Val
0x18000f286  lea     rcx, [rbp+57h+pvParam]; void *
0x18000f28a  lea     r8d, [rdx+5Ch]; Size
0x18000f28e  call    memset_0
0x18000f293  mov     rsi, [rbx+70h]
0x18000f297  lea     rdx, aPreviewstuff; "PreviewStuff"
0x18000f29e  xorps   xmm0, xmm0
0x18000f2a1  mov     r8, rsi; hData
0x18000f2a4  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18000f2a8  mov     rcx, rdi; hWnd
0x18000f2ab  mov     rax, [rsi+18h]
0x18000f2af  mov     [rbx+70h], rax
0x18000f2b3  call    cs:__imp_SetPropW
0x18000f2b9  xor     r9d, r9d; szFile
0x18000f2bc  mov     [rsi+8], rdi
0x18000f2c0  xor     edx, edx; hInstance
0x18000f2c2  mov     [rsi+10h], rbx
0x18000f2c6  mov     r8d, 40804008h; dwStyle
0x18000f2cc  mov     rcx, rdi; hwndParent
0x18000f2cf  call    MCIWndCreateW
0x18000f2d4  lea     rdx, [rsi+30h]; lpRect
0x18000f2d8  mov     [rsi+60h], rax
0x18000f2dc  mov     rcx, rdi; hWnd
0x18000f2df  call    cs:__imp_GetClientRect
0x18000f2e5  mov     edx, 2; nIDDlgItem
0x18000f2ea  mov     rcx, rdi; hDlg
0x18000f2ed  call    cs:__imp_GetDlgItem
0x18000f2f3  mov     rcx, rax; hWnd
0x18000f2f6  lea     rdx, [rbp+57h+Rect]; lpRect
0x18000f2fa  call    cs:__imp_GetWindowRect
0x18000f300  lea     rdx, [rbp+57h+Rect]; lpPoint
0x18000f304  mov     rcx, rdi; hWnd
0x18000f307  call    cs:__imp_ScreenToClient
0x18000f30d  lea     rdx, [rbp+57h+Rect.right]; lpPoint
0x18000f311  mov     rcx, rdi; hWnd
0x18000f314  call    cs:__imp_ScreenToClient
0x18000f31a  mov     eax, [rbp+57h+Rect.bottom]
0x18000f31d  lea     r8, [rbp+57h+pvParam]; pvParam
0x18000f321  add     eax, 4
0x18000f324  xor     r9d, r9d; fWinIni
0x18000f327  mov     [rsi+34h], eax
0x18000f32a  mov     eax, [rbp+57h+Rect.left]
0x18000f32d  mov     [rsi+30h], eax
0x18000f330  mov     eax, [rbp+57h+Rect.right]
0x18000f333  lea     edx, [r9+5Ch]; uiParam
0x18000f337  mov     [rsi+38h], eax
0x18000f33a  lea     ecx, [rdx-3Dh]; uiAction
0x18000f33d  mov     eax, [rbp+57h+Rect.top]
0x18000f340  sub     eax, [rbp+57h+Rect.bottom]
0x18000f343  sub     eax, 0Ch
0x18000f346  add     [rsi+3Ch], eax
0x18000f349  call    cs:__imp_SystemParametersInfoW
0x18000f34f  lea     rcx, [rbp+57h+pvParam]; lplf
0x18000f353  call    cs:__imp_CreateFontIndirectW
0x18000f359  mov     [rsi+68h], rax
0x18000f35d  mov     eax, 1
0x18000f362  mov     rcx, [rbp+57h+var_20]
0x18000f366  xor     rcx, rsp; StackCookie
0x18000f369  call    __security_check_cookie
0x18000f36e  mov     rbx, [rsp+0B0h+arg_10]
0x18000f376  add     rsp, 0A0h
0x18000f37d  pop     rdi
0x18000f37e  pop     rsi
0x18000f37f  pop     rbp
0x18000f380  retn
```
