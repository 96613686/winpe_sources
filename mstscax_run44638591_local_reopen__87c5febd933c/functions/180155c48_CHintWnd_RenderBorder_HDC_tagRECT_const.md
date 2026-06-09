# CHintWnd::RenderBorder(HDC__ *,tagRECT const *)

- ea: `0x180155c48`
- end: `0x180155d4a`
- name: `?RenderBorder@CHintWnd@@IEAAXPEAUHDC__@@PEBUtagRECT@@@Z`
- size: `258`
- prototype: `void(CHintWnd *__hidden this, HDC, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180155b7c`

## callees

- `0x180155c48`

## import_xrefs

- `GDI32!DeleteObject` at `0x180155d3a`
- `GDI32!DeleteObject` at `0x180155d3a`
- `GDI32!SelectObject` at `0x180155c7e`
- `GDI32!SelectObject` at `0x180155d2c`
- `GDI32!SelectObject` at `0x180155c7e`
- `GDI32!SelectObject` at `0x180155d2c`
- `GDI32!MoveToEx` at `0x180155c94`
- `GDI32!MoveToEx` at `0x180155cbb`
- `GDI32!MoveToEx` at `0x180155ce5`
- `GDI32!MoveToEx` at `0x180155d0b`
- `GDI32!MoveToEx` at `0x180155c94`
- `GDI32!MoveToEx` at `0x180155cbb`
- `GDI32!MoveToEx` at `0x180155ce5`
- `GDI32!MoveToEx` at `0x180155d0b`
- `GDI32!LineTo` at `0x180155ca5`
- `GDI32!LineTo` at `0x180155cce`
- `GDI32!LineTo` at `0x180155cf8`
- `GDI32!LineTo` at `0x180155d1b`
- `GDI32!LineTo` at `0x180155ca5`
- `GDI32!LineTo` at `0x180155cce`
- `GDI32!LineTo` at `0x180155cf8`
- `GDI32!LineTo` at `0x180155d1b`
- `GDI32!CreatePen` at `0x180155c6a`
- `GDI32!CreatePen` at `0x180155c6a`
- `USER32!GetSysColor` at `0x180155c5d`
- `USER32!GetSysColor` at `0x180155c5d`

## pseudocode

```c
void __fastcall CHintWnd::RenderBorder(CHintWnd *this, HDC a2, const struct tagRECT *a3)
{
  HGDIOBJ v3; // rsi
  COLORREF SysColor; // eax
  HPEN Pen; // rax
  HPEN v8; // rbx

  v3 = 0;
  SysColor = GetSysColor(6);
  Pen = CreatePen(0, 0, SysColor);
  v8 = Pen;
  if ( Pen )
    v3 = SelectObject(a2, Pen);
  MoveToEx(a2, a3->left, a3->top, 0);
  LineTo(a2, a3->right, a3->top);
  MoveToEx(a2, a3->right - 1, a3->top, 0);
  LineTo(a2, a3->right - 1, a3->bottom);
  MoveToEx(a2, a3->right, a3->bottom - 1, 0);
  LineTo(a2, a3->left, a3->bottom - 1);
  MoveToEx(a2, a3->left, a3->bottom, 0);
  LineTo(a2, a3->left, a3->top);
  if ( v3 )
    SelectObject(a2, v3);
  if ( v8 )
    DeleteObject(v8);
}

```

## disassembly

```asm
0x180155c48  push    rbx
0x180155c4a  push    rsi
0x180155c4b  push    rdi
0x180155c4c  push    r14
0x180155c4e  sub     rsp, 28h
0x180155c52  xor     esi, esi
0x180155c54  mov     r14, r8
0x180155c57  mov     rdi, rdx
0x180155c5a  lea     ecx, [rsi+6]; nIndex
0x180155c5d  call    cs:__imp_GetSysColor
0x180155c63  xor     edx, edx; cWidth
0x180155c65  xor     ecx, ecx; iStyle
0x180155c67  mov     r8d, eax; color
0x180155c6a  call    cs:__imp_CreatePen
0x180155c70  mov     rbx, rax
0x180155c73  test    rax, rax
0x180155c76  jz      short loc_180155C87
0x180155c78  mov     rdx, rax; h
0x180155c7b  mov     rcx, rdi; hdc
0x180155c7e  call    cs:__imp_SelectObject
0x180155c84  mov     rsi, rax
0x180155c87  mov     r8d, [r14+4]; y
0x180155c8b  xor     r9d, r9d; lppt
0x180155c8e  mov     edx, [r14]; x
0x180155c91  mov     rcx, rdi; hdc
0x180155c94  call    cs:__imp_MoveToEx
0x180155c9a  mov     r8d, [r14+4]; y
0x180155c9e  mov     rcx, rdi; hdc
0x180155ca1  mov     edx, [r14+8]; x
0x180155ca5  call    cs:__imp_LineTo
0x180155cab  mov     edx, [r14+8]
0x180155caf  xor     r9d, r9d; lppt
0x180155cb2  mov     r8d, [r14+4]; y
0x180155cb6  dec     edx; x
0x180155cb8  mov     rcx, rdi; hdc
0x180155cbb  call    cs:__imp_MoveToEx
0x180155cc1  mov     edx, [r14+8]
0x180155cc5  mov     rcx, rdi; hdc
0x180155cc8  mov     r8d, [r14+0Ch]; y
0x180155ccc  dec     edx; x
0x180155cce  call    cs:__imp_LineTo
0x180155cd4  mov     r8d, [r14+0Ch]
0x180155cd8  xor     r9d, r9d; lppt
0x180155cdb  mov     edx, [r14+8]; x
0x180155cdf  dec     r8d; y
0x180155ce2  mov     rcx, rdi; hdc
0x180155ce5  call    cs:__imp_MoveToEx
0x180155ceb  mov     r8d, [r14+0Ch]
0x180155cef  mov     rcx, rdi; hdc
0x180155cf2  mov     edx, [r14]; x
0x180155cf5  dec     r8d; y
0x180155cf8  call    cs:__imp_LineTo
0x180155cfe  mov     r8d, [r14+0Ch]; y
0x180155d02  xor     r9d, r9d; lppt
0x180155d05  mov     edx, [r14]; x
0x180155d08  mov     rcx, rdi; hdc
0x180155d0b  call    cs:__imp_MoveToEx
0x180155d11  mov     r8d, [r14+4]; y
0x180155d15  mov     rcx, rdi; hdc
0x180155d18  mov     edx, [r14]; x
0x180155d1b  call    cs:__imp_LineTo
0x180155d21  test    rsi, rsi
0x180155d24  jz      short loc_180155D32
0x180155d26  mov     rdx, rsi; h
0x180155d29  mov     rcx, rdi; hdc
0x180155d2c  call    cs:__imp_SelectObject
0x180155d32  test    rbx, rbx
0x180155d35  jz      short loc_180155D40
0x180155d37  mov     rcx, rbx; ho
0x180155d3a  call    cs:__imp_DeleteObject
0x180155d40  add     rsp, 28h
0x180155d44  pop     r14
0x180155d46  pop     rdi
0x180155d47  pop     rsi
0x180155d48  pop     rbx
0x180155d49  retn
```
