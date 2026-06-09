# CVideoWindow::OnEraseBackground(void)

- ea: `0x1800a458c`
- end: `0x1800a4703`
- name: `?OnEraseBackground@CVideoWindow@@AEAAXXZ`
- size: `375`
- prototype: `void __fastcall(CVideoWindow *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a47a0`

## callees

- `0x1800388a0`
- `0x1800a42f0`
- `0x1800a458c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800a46dc`
- `KERNEL32!LeaveCriticalSection` at `0x1800a46dc`
- `KERNEL32!EnterCriticalSection` at `0x1800a45da`
- `KERNEL32!EnterCriticalSection` at `0x1800a45da`
- `GDI32!DeleteObject` at `0x1800a4691`
- `GDI32!DeleteObject` at `0x1800a46a5`
- `GDI32!DeleteObject` at `0x1800a46b9`
- `GDI32!DeleteObject` at `0x1800a46cd`
- `GDI32!DeleteObject` at `0x1800a4691`
- `GDI32!DeleteObject` at `0x1800a46a5`
- `GDI32!DeleteObject` at `0x1800a46b9`
- `GDI32!DeleteObject` at `0x1800a46cd`
- `GDI32!CreateSolidBrush` at `0x1800a4669`
- `GDI32!CreateSolidBrush` at `0x1800a4669`
- `GDI32!FillRgn` at `0x1800a4682`
- `GDI32!FillRgn` at `0x1800a4682`
- `GDI32!CombineRgn` at `0x1800a4656`
- `GDI32!CombineRgn` at `0x1800a4656`
- `GDI32!CreateRectRgn` at `0x1800a4629`
- `GDI32!CreateRectRgn` at `0x1800a4629`
- `GDI32!CreateRectRgnIndirect` at `0x1800a45fc`
- `GDI32!CreateRectRgnIndirect` at `0x1800a4610`
- `GDI32!CreateRectRgnIndirect` at `0x1800a45fc`
- `GDI32!CreateRectRgnIndirect` at `0x1800a4610`
- `USER32!GetClientRect` at `0x1800a45c4`
- `USER32!GetClientRect` at `0x1800a45c4`

## pseudocode

```c
void __fastcall CVideoWindow::OnEraseBackground(CVideoWindow *this)
{
  HWND v2; // rcx
  HRGN v3; // rbp
  HRGN v4; // rdi
  HRGN RectRgn; // rax
  HBRUSH SolidBrush; // rsi
  HRGN v7; // rbx
  struct tagRECT Rect; // [rsp+20h] [rbp-68h] BYREF
  RECT rect; // [rsp+30h] [rbp-58h] BYREF

  v2 = (HWND)*((_QWORD *)this + 7);
  Rect = 0;
  rect = 0;
  GetClientRect(v2, &Rect);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  CVideoWindow::GetTargetRect((CVideoWindow *)((char *)this + 288), &rect);
  v3 = CreateRectRgnIndirect(&Rect);
  v4 = CreateRectRgnIndirect(&rect);
  RectRgn = CreateRectRgn(0, 0, 0, 0);
  SolidBrush = 0;
  v7 = RectRgn;
  if ( v3 )
  {
    if ( v4 && RectRgn )
    {
      CombineRgn(RectRgn, v3, v4, 4);
      SolidBrush = CreateSolidBrush(*((_DWORD *)this + 64));
      FillRgn(*((HDC *)this + 8), v7, SolidBrush);
    }
    DeleteObject(v3);
  }
  if ( v4 )
    DeleteObject(v4);
  if ( v7 )
    DeleteObject(v7);
  if ( SolidBrush )
    DeleteObject(SolidBrush);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
}

```

## disassembly

```asm
0x1800a458c  push    rbx
0x1800a458e  push    rbp
0x1800a458f  push    rsi
0x1800a4590  push    rdi
0x1800a4591  push    r14
0x1800a4593  push    r15
0x1800a4595  sub     rsp, 58h
0x1800a4599  mov     rax, cs:__security_cookie
0x1800a45a0  xor     rax, rsp
0x1800a45a3  mov     [rsp+88h+var_48], rax
0x1800a45a8  mov     r14, rcx
0x1800a45ab  lea     rdx, [rsp+88h+Rect]; lpRect
0x1800a45b0  mov     rcx, [rcx+38h]; hWnd
0x1800a45b4  xorps   xmm0, xmm0
0x1800a45b7  xorps   xmm1, xmm1
0x1800a45ba  movups  xmmword ptr [rsp+88h+Rect.left], xmm0
0x1800a45bf  movups  xmmword ptr [rsp+88h+rect.left], xmm1
0x1800a45c4  call    cs:__imp_GetClientRect
0x1800a45cb  nop     dword ptr [rax+rax+00h]
0x1800a45d0  lea     r15, [r14+90h]
0x1800a45d7  mov     rcx, r15; lpCriticalSection
0x1800a45da  call    cs:__imp_EnterCriticalSection
0x1800a45e1  nop     dword ptr [rax+rax+00h]
0x1800a45e6  lea     rcx, [r14+120h]; this
0x1800a45ed  lea     rdx, [rsp+88h+rect]; struct tagRECT *
0x1800a45f2  call    ?GetTargetRect@CVideoWindow@@UEAAJPEAUtagRECT@@@Z; CVideoWindow::GetTargetRect(tagRECT *)
0x1800a45f7  lea     rcx, [rsp+88h+Rect]; lprect
0x1800a45fc  call    cs:__imp_CreateRectRgnIndirect
0x1800a4603  nop     dword ptr [rax+rax+00h]
0x1800a4608  lea     rcx, [rsp+88h+rect]; lprect
0x1800a460d  mov     rbp, rax
0x1800a4610  call    cs:__imp_CreateRectRgnIndirect
0x1800a4617  nop     dword ptr [rax+rax+00h]
0x1800a461c  xor     r9d, r9d; y2
0x1800a461f  xor     r8d, r8d; x2
0x1800a4622  xor     edx, edx; y1
0x1800a4624  xor     ecx, ecx; x1
0x1800a4626  mov     rdi, rax
0x1800a4629  call    cs:__imp_CreateRectRgn
0x1800a4630  nop     dword ptr [rax+rax+00h]
0x1800a4635  xor     esi, esi
0x1800a4637  mov     rbx, rax
0x1800a463a  test    rbp, rbp
0x1800a463d  jz      short loc_1800A469D
0x1800a463f  test    rdi, rdi
0x1800a4642  jz      short loc_1800A468E
0x1800a4644  test    rax, rax
0x1800a4647  jz      short loc_1800A468E
0x1800a4649  lea     r9d, [rsi+4]; iMode
0x1800a464d  mov     r8, rdi; hrgnSrc2
0x1800a4650  mov     rdx, rbp; hrgnSrc1
0x1800a4653  mov     rcx, rax; hrgnDst
0x1800a4656  call    cs:__imp_CombineRgn
0x1800a465d  nop     dword ptr [rax+rax+00h]
0x1800a4662  mov     ecx, [r14+100h]; color
0x1800a4669  call    cs:__imp_CreateSolidBrush
0x1800a4670  nop     dword ptr [rax+rax+00h]
0x1800a4675  mov     rcx, [r14+40h]; hdc
0x1800a4679  mov     rdx, rbx; hrgn
0x1800a467c  mov     r8, rax; hbr
0x1800a467f  mov     rsi, rax
0x1800a4682  call    cs:__imp_FillRgn
0x1800a4689  nop     dword ptr [rax+rax+00h]
0x1800a468e  mov     rcx, rbp; ho
0x1800a4691  call    cs:__imp_DeleteObject
0x1800a4698  nop     dword ptr [rax+rax+00h]
0x1800a469d  test    rdi, rdi
0x1800a46a0  jz      short loc_1800A46B1
0x1800a46a2  mov     rcx, rdi; ho
0x1800a46a5  call    cs:__imp_DeleteObject
0x1800a46ac  nop     dword ptr [rax+rax+00h]
0x1800a46b1  test    rbx, rbx
0x1800a46b4  jz      short loc_1800A46C5
0x1800a46b6  mov     rcx, rbx; ho
0x1800a46b9  call    cs:__imp_DeleteObject
0x1800a46c0  nop     dword ptr [rax+rax+00h]
0x1800a46c5  test    rsi, rsi
0x1800a46c8  jz      short loc_1800A46D9
0x1800a46ca  mov     rcx, rsi; ho
0x1800a46cd  call    cs:__imp_DeleteObject
0x1800a46d4  nop     dword ptr [rax+rax+00h]
0x1800a46d9  mov     rcx, r15; lpCriticalSection
0x1800a46dc  call    cs:__imp_LeaveCriticalSection
0x1800a46e3  nop     dword ptr [rax+rax+00h]
0x1800a46e8  mov     rcx, [rsp+88h+var_48]
0x1800a46ed  xor     rcx, rsp; StackCookie
0x1800a46f0  call    __security_check_cookie
0x1800a46f5  add     rsp, 58h
0x1800a46f9  pop     r15
0x1800a46fb  pop     r14
0x1800a46fd  pop     rdi
0x1800a46fe  pop     rsi
0x1800a46ff  pop     rbp
0x1800a4700  pop     rbx
0x1800a4701  retn
```
