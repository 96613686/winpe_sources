# CInfoWindow::_OnPaint(HWND__ *)

- ea: `0x18008aea8`
- end: `0x18008b01c`
- name: `?_OnPaint@CInfoWindow@@AEAAXPEAUHWND__@@@Z`
- size: `372`
- prototype: `void(CInfoWindow *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18008ad50`

## callees

- `0x18008aea8`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18008af1b`
- `GDI32!CreateCompatibleDC` at `0x18008af1b`
- `GDI32!SelectObject` at `0x18008af4b`
- `GDI32!SelectObject` at `0x18008af4b`
- `GDI32!BitBlt` at `0x18008afbf`
- `GDI32!BitBlt` at `0x18008afbf`
- `GDI32!DeleteDC` at `0x18008afdd`
- `GDI32!DeleteDC` at `0x18008afdd`
- `GDI32!DeleteObject` at `0x18008afd4`
- `GDI32!DeleteObject` at `0x18008afd4`
- `GDI32!SaveDC` at `0x18008af27`
- `GDI32!SaveDC` at `0x18008af27`
- `GDI32!CreateCompatibleBitmap` at `0x18008af3c`
- `GDI32!CreateCompatibleBitmap` at `0x18008af3c`
- `GDI32!RestoreDC` at `0x18008afcb`
- `GDI32!RestoreDC` at `0x18008afcb`
- `USER32!GetSysColorBrush` at `0x18008af54`
- `USER32!GetSysColorBrush` at `0x18008af7b`
- `USER32!GetSysColorBrush` at `0x18008af54`
- `USER32!GetSysColorBrush` at `0x18008af7b`
- `USER32!GetClientRect` at `0x18008af08`
- `USER32!GetClientRect` at `0x18008af08`
- `USER32!FillRect` at `0x18008af65`
- `USER32!FillRect` at `0x18008af65`
- `USER32!BeginPaint` at `0x18008aef7`
- `USER32!BeginPaint` at `0x18008aef7`
- `USER32!EndPaint` at `0x18008afeb`
- `USER32!EndPaint` at `0x18008afeb`
- `USER32!FrameRect` at `0x18008af8c`
- `USER32!FrameRect` at `0x18008af8c`

## pseudocode

```c
void __fastcall CInfoWindow::_OnPaint(CInfoWindow *this, HWND a2)
{
  HDC v4; // rbp
  LONG right; // r15d
  LONG cy; // r12d
  HDC hdcSrc; // rbx
  int v8; // r13d
  HBITMAP CompatibleBitmap; // r14
  HBRUSH SysColorBrush; // rax
  int v11; // ecx
  HBRUSH v12; // rax
  struct tagRECT Rect; // [rsp+50h] [rbp-A8h] BYREF
  struct tagPAINTSTRUCT Paint; // [rsp+60h] [rbp-98h] BYREF

  memset_0(&Paint, 0, sizeof(Paint));
  Rect = 0;
  v4 = BeginPaint(a2, &Paint);
  GetClientRect(a2, &Rect);
  right = Rect.right;
  cy = Rect.bottom;
  hdcSrc = CreateCompatibleDC(v4);
  v8 = SaveDC(hdcSrc);
  CompatibleBitmap = CreateCompatibleBitmap(v4, Rect.right, Rect.bottom);
  SelectObject(hdcSrc, CompatibleBitmap);
  SysColorBrush = GetSysColorBrush(*((_DWORD *)this + 12));
  FillRect(hdcSrc, &Rect, SysColorBrush);
  if ( *((_DWORD *)this + 10) )
    v11 = *((_DWORD *)this + 11);
  else
    v11 = 16;
  v12 = GetSysColorBrush(v11);
  FrameRect(hdcSrc, &Rect, v12);
  BitBlt(v4, 0, 0, right, cy, hdcSrc, 0, 0, 0xCC0020u);
  RestoreDC(hdcSrc, v8);
  DeleteObject(CompatibleBitmap);
  DeleteDC(hdcSrc);
  EndPaint(a2, &Paint);
}

```

## disassembly

```asm
0x18008aea8  mov     [rsp+arg_10], rbx
0x18008aead  push    rbp
0x18008aeae  push    rsi
0x18008aeaf  push    rdi
0x18008aeb0  push    r12
0x18008aeb2  push    r13
0x18008aeb4  push    r14
0x18008aeb6  push    r15
0x18008aeb8  sub     rsp, 0C0h
0x18008aebf  mov     rax, cs:__security_cookie
0x18008aec6  xor     rax, rsp
0x18008aec9  mov     [rsp+0F8h+var_48], rax
0x18008aed1  mov     rsi, rdx
0x18008aed4  mov     rdi, rcx
0x18008aed7  xor     edx, edx; Val
0x18008aed9  lea     rcx, [rsp+0F8h+Paint]; void *
0x18008aede  lea     r8d, [rdx+48h]; Size
0x18008aee2  call    memset_0
0x18008aee7  xorps   xmm0, xmm0
0x18008aeea  lea     rdx, [rsp+0F8h+Paint]; lpPaint
0x18008aeef  mov     rcx, rsi; hWnd
0x18008aef2  movups  xmmword ptr [rsp+0F8h+Rect.left], xmm0
0x18008aef7  call    cs:__imp_BeginPaint
0x18008aefd  lea     rdx, [rsp+0F8h+Rect]; lpRect
0x18008af02  mov     rcx, rsi; hWnd
0x18008af05  mov     rbp, rax
0x18008af08  call    cs:__imp_GetClientRect
0x18008af0e  mov     r15d, [rsp+0F8h+Rect.right]
0x18008af13  mov     rcx, rbp; hdc
0x18008af16  mov     r12d, [rsp+0F8h+Rect.bottom]
0x18008af1b  call    cs:__imp_CreateCompatibleDC
0x18008af21  mov     rcx, rax; hdc
0x18008af24  mov     rbx, rax
0x18008af27  call    cs:__imp_SaveDC
0x18008af2d  mov     r8d, [rsp+0F8h+Rect.bottom]; cy
0x18008af32  mov     rcx, rbp; hdc
0x18008af35  mov     edx, [rsp+0F8h+Rect.right]; cx
0x18008af39  mov     r13d, eax
0x18008af3c  call    cs:__imp_CreateCompatibleBitmap
0x18008af42  mov     rdx, rax; h
0x18008af45  mov     rcx, rbx; hdc
0x18008af48  mov     r14, rax
0x18008af4b  call    cs:__imp_SelectObject
0x18008af51  mov     ecx, [rdi+30h]; nIndex
0x18008af54  call    cs:__imp_GetSysColorBrush
0x18008af5a  lea     rdx, [rsp+0F8h+Rect]; lprc
0x18008af5f  mov     rcx, rbx; hDC
0x18008af62  mov     r8, rax; hbr
0x18008af65  call    cs:__imp_FillRect
0x18008af6b  cmp     dword ptr [rdi+28h], 0
0x18008af6f  jz      short loc_18008AF76
0x18008af71  mov     ecx, [rdi+2Ch]
0x18008af74  jmp     short loc_18008AF7B
0x18008af76  mov     ecx, 10h; nIndex
0x18008af7b  call    cs:__imp_GetSysColorBrush
0x18008af81  lea     rdx, [rsp+0F8h+Rect]; lprc
0x18008af86  mov     rcx, rbx; hDC
0x18008af89  mov     r8, rax; hbr
0x18008af8c  call    cs:__imp_FrameRect
0x18008af92  mov     [rsp+0F8h+rop], 0CC0020h; rop
0x18008af9a  mov     r9d, r15d; cx
0x18008af9d  mov     [rsp+0F8h+y1], 0; y1
0x18008afa5  xor     r8d, r8d; y
0x18008afa8  mov     [rsp+0F8h+x1], 0; x1
0x18008afb0  xor     edx, edx; x
0x18008afb2  mov     [rsp+0F8h+hdcSrc], rbx; hdcSrc
0x18008afb7  mov     rcx, rbp; hdc
0x18008afba  mov     [rsp+0F8h+cy], r12d; cy
0x18008afbf  call    cs:__imp_BitBlt
0x18008afc5  mov     edx, r13d; nSavedDC
0x18008afc8  mov     rcx, rbx; hdc
0x18008afcb  call    cs:__imp_RestoreDC
0x18008afd1  mov     rcx, r14; ho
0x18008afd4  call    cs:__imp_DeleteObject
0x18008afda  mov     rcx, rbx; hdc
0x18008afdd  call    cs:__imp_DeleteDC
0x18008afe3  lea     rdx, [rsp+0F8h+Paint]; lpPaint
0x18008afe8  mov     rcx, rsi; hWnd
0x18008afeb  call    cs:__imp_EndPaint
0x18008aff1  mov     rcx, [rsp+0F8h+var_48]
0x18008aff9  xor     rcx, rsp; StackCookie
0x18008affc  call    __security_check_cookie
0x18008b001  mov     rbx, [rsp+0F8h+arg_10]
0x18008b009  add     rsp, 0C0h
0x18008b010  pop     r15
0x18008b012  pop     r14
0x18008b014  pop     r13
0x18008b016  pop     r12
0x18008b018  pop     rdi
0x18008b019  pop     rsi
0x18008b01a  pop     rbp
0x18008b01b  retn
```
