# CVMRVideoWindow::OnEraseBackground(void)

- ea: `0x180018b88`
- end: `0x180018d32`
- name: `?OnEraseBackground@CVMRVideoWindow@@AEAAXXZ`
- size: `426`
- prototype: `void __fastcall(CVMRVideoWindow *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018520`
- `0x1800259c0`

## callees

- `0x180018b88`
- `0x1800388a0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180018c1a`
- `KERNEL32!LeaveCriticalSection` at `0x180018d0b`
- `KERNEL32!LeaveCriticalSection` at `0x180018c1a`
- `KERNEL32!LeaveCriticalSection` at `0x180018d0b`
- `KERNEL32!EnterCriticalSection` at `0x180018bd6`
- `KERNEL32!EnterCriticalSection` at `0x180018be5`
- `KERNEL32!EnterCriticalSection` at `0x180018bd6`
- `KERNEL32!EnterCriticalSection` at `0x180018be5`
- `GDI32!DeleteObject` at `0x180018cc0`
- `GDI32!DeleteObject` at `0x180018cd4`
- `GDI32!DeleteObject` at `0x180018ce8`
- `GDI32!DeleteObject` at `0x180018cfc`
- `GDI32!DeleteObject` at `0x180018cc0`
- `GDI32!DeleteObject` at `0x180018cd4`
- `GDI32!DeleteObject` at `0x180018ce8`
- `GDI32!DeleteObject` at `0x180018cfc`
- `GDI32!CreateSolidBrush` at `0x180018c98`
- `GDI32!CreateSolidBrush` at `0x180018c98`
- `GDI32!FillRgn` at `0x180018cb1`
- `GDI32!FillRgn` at `0x180018cb1`
- `GDI32!CombineRgn` at `0x180018c85`
- `GDI32!CombineRgn` at `0x180018c85`
- `GDI32!CreateRectRgn` at `0x180018c58`
- `GDI32!CreateRectRgn` at `0x180018c58`
- `GDI32!CreateRectRgnIndirect` at `0x180018c2b`
- `GDI32!CreateRectRgnIndirect` at `0x180018c3f`
- `GDI32!CreateRectRgnIndirect` at `0x180018c2b`
- `GDI32!CreateRectRgnIndirect` at `0x180018c3f`
- `USER32!GetClientRect` at `0x180018bc0`
- `USER32!GetClientRect` at `0x180018bc0`

## pseudocode

```c
void __fastcall CVMRVideoWindow::OnEraseBackground(CVMRVideoWindow *this)
{
  HWND v2; // rcx
  __int64 v3; // rcx
  HRGN v4; // r15
  HRGN v5; // rdi
  HRGN RectRgn; // rax
  HBRUSH SolidBrush; // rsi
  HRGN v8; // rbx
  struct tagRECT Rect; // [rsp+20h] [rbp-68h] BYREF
  RECT rect; // [rsp+30h] [rbp-58h] BYREF

  v2 = (HWND)*((_QWORD *)this + 7);
  Rect = 0;
  rect = 0;
  GetClientRect(v2, &Rect);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v3 = *(_QWORD *)(*((_QWORD *)this + 42) + 456LL);
  if ( v3 )
    (*(void (__fastcall **)(__int64, _QWORD, RECT *))(*(_QWORD *)v3 + 56LL))(v3, 0, &rect);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  v4 = CreateRectRgnIndirect(&Rect);
  v5 = CreateRectRgnIndirect(&rect);
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  SolidBrush = 0;
  v8 = RectRgn;
  if ( v4 )
  {
    if ( v5 && RectRgn )
    {
      CombineRgn(RectRgn, v4, v5, 4);
      SolidBrush = CreateSolidBrush(*((_DWORD *)this + 62));
      FillRgn(*((HDC *)this + 8), v8, SolidBrush);
    }
    DeleteObject(v4);
  }
  if ( v5 )
    DeleteObject(v5);
  if ( v8 )
    DeleteObject(v8);
  if ( SolidBrush )
    DeleteObject(SolidBrush);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
}

```

## disassembly

```asm
0x180018b88  push    rbx
0x180018b8a  push    rbp
0x180018b8b  push    rsi
0x180018b8c  push    rdi
0x180018b8d  push    r14
0x180018b8f  push    r15
0x180018b91  sub     rsp, 58h
0x180018b95  mov     rax, cs:__security_cookie
0x180018b9c  xor     rax, rsp
0x180018b9f  mov     [rsp+88h+var_48], rax
0x180018ba4  mov     r14, rcx
0x180018ba7  lea     rdx, [rsp+88h+Rect]; lpRect
0x180018bac  mov     rcx, [rcx+38h]; hWnd
0x180018bb0  xorps   xmm0, xmm0
0x180018bb3  xorps   xmm1, xmm1
0x180018bb6  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x180018bbb  movups  xmmword ptr [rsp+88h+rect.left], xmm1
0x180018bc0  call    cs:__imp_GetClientRect
0x180018bc7  nop     dword ptr [rax+rax+00h]
0x180018bcc  lea     rbp, [r14+90h]
0x180018bd3  mov     rcx, rbp; lpCriticalSection
0x180018bd6  call    cs:__imp_EnterCriticalSection
0x180018bdd  nop     dword ptr [rax+rax+00h]
0x180018be2  mov     rcx, rbp; lpCriticalSection
0x180018be5  call    cs:__imp_EnterCriticalSection
0x180018bec  nop     dword ptr [rax+rax+00h]
0x180018bf1  mov     rax, [r14+150h]
0x180018bf8  mov     rcx, [rax+1C8h]
0x180018bff  test    rcx, rcx
0x180018c02  jz      short loc_180018C17
0x180018c04  mov     rax, [rcx]
0x180018c07  lea     r8, [rsp+88h+rect]
0x180018c0c  xor     edx, edx
0x180018c0e  mov     rax, [rax+38h]
0x180018c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c17  mov     rcx, rbp; lpCriticalSection
0x180018c1a  call    cs:__imp_LeaveCriticalSection
0x180018c21  nop     dword ptr [rax+rax+00h]
0x180018c26  lea     rcx, [rsp+88h+Rect]; lprect
0x180018c2b  call    cs:__imp_CreateRectRgnIndirect
0x180018c32  nop     dword ptr [rax+rax+00h]
0x180018c37  lea     rcx, [rsp+88h+rect]; lprect
0x180018c3c  mov     r15, rax
0x180018c3f  call    cs:__imp_CreateRectRgnIndirect
0x180018c46  nop     dword ptr [rax+rax+00h]
0x180018c4b  xor     r9d, r9d; y2
0x180018c4e  xor     r8d, r8d; x2
0x180018c51  xor     edx, edx; y1
0x180018c53  xor     ecx, ecx; x1
0x180018c55  mov     rdi, rax
0x180018c58  call    cs:__imp_CreateRectRgn
0x180018c5f  nop     dword ptr [rax+rax+00h]
0x180018c64  xor     esi, esi
0x180018c66  mov     rbx, rax
0x180018c69  test    r15, r15
0x180018c6c  jz      short loc_180018CCC
0x180018c6e  test    rdi, rdi
0x180018c71  jz      short loc_180018CBD
0x180018c73  test    rax, rax
0x180018c76  jz      short loc_180018CBD
0x180018c78  lea     r9d, [rsi+4]; iMode
0x180018c7c  mov     r8, rdi; hrgnSrc2
0x180018c7f  mov     rdx, r15; hrgnSrc1
0x180018c82  mov     rcx, rax; hrgnDst
0x180018c85  call    cs:__imp_CombineRgn
0x180018c8c  nop     dword ptr [rax+rax+00h]
0x180018c91  mov     ecx, [r14+0F8h]; color
0x180018c98  call    cs:__imp_CreateSolidBrush
0x180018c9f  nop     dword ptr [rax+rax+00h]
0x180018ca4  mov     rcx, [r14+40h]; hdc
0x180018ca8  mov     rdx, rbx; hrgn
0x180018cab  mov     r8, rax; hbr
0x180018cae  mov     rsi, rax
0x180018cb1  call    cs:__imp_FillRgn
0x180018cb8  nop     dword ptr [rax+rax+00h]
0x180018cbd  mov     rcx, r15; ho
0x180018cc0  call    cs:__imp_DeleteObject
0x180018cc7  nop     dword ptr [rax+rax+00h]
0x180018ccc  test    rdi, rdi
0x180018ccf  jz      short loc_180018CE0
0x180018cd1  mov     rcx, rdi; ho
0x180018cd4  call    cs:__imp_DeleteObject
0x180018cdb  nop     dword ptr [rax+rax+00h]
0x180018ce0  test    rbx, rbx
0x180018ce3  jz      short loc_180018CF4
0x180018ce5  mov     rcx, rbx; ho
0x180018ce8  call    cs:__imp_DeleteObject
0x180018cef  nop     dword ptr [rax+rax+00h]
0x180018cf4  test    rsi, rsi
0x180018cf7  jz      short loc_180018D08
0x180018cf9  mov     rcx, rsi; ho
0x180018cfc  call    cs:__imp_DeleteObject
0x180018d03  nop     dword ptr [rax+rax+00h]
0x180018d08  mov     rcx, rbp; lpCriticalSection
0x180018d0b  call    cs:__imp_LeaveCriticalSection
0x180018d12  nop     dword ptr [rax+rax+00h]
0x180018d17  mov     rcx, [rsp+88h+var_48]
0x180018d1c  xor     rcx, rsp; StackCookie
0x180018d1f  call    __security_check_cookie
0x180018d24  add     rsp, 58h
0x180018d28  pop     r15
0x180018d2a  pop     r14
0x180018d2c  pop     rdi
0x180018d2d  pop     rsi
0x180018d2e  pop     rbp
0x180018d2f  pop     rbx
0x180018d30  retn
```
