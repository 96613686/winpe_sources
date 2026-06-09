# CImageList::_CreateMirroredBitmap(HBITMAP__ *)

- ea: `0x180083ed0`
- end: `0x180084011`
- name: `?_CreateMirroredBitmap@CImageList@@QEAAPEAUHBITMAP__@@PEAU2@@Z`
- size: `321`
- prototype: `HBITMAP(CImageList *__hidden this, HBITMAP)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18007f3e0`
- `0x18007f470`
- `0x1800827b0`

## callees

- `0x180083ed0`
- `0x1800852a0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180083f17`
- `GDI32!CreateCompatibleDC` at `0x180083f42`
- `GDI32!CreateCompatibleDC` at `0x180083f17`
- `GDI32!CreateCompatibleDC` at `0x180083f42`
- `GDI32!SelectObject` at `0x180083f76`
- `GDI32!SelectObject` at `0x180083f85`
- `GDI32!SelectObject` at `0x180083fda`
- `GDI32!SelectObject` at `0x180083fe6`
- `GDI32!SelectObject` at `0x180083f76`
- `GDI32!SelectObject` at `0x180083f85`
- `GDI32!SelectObject` at `0x180083fda`
- `GDI32!SelectObject` at `0x180083fe6`
- `GDI32!BitBlt` at `0x180083fce`
- `GDI32!BitBlt` at `0x180083fce`
- `GDI32!GetObjectW` at `0x180083eff`
- `GDI32!GetObjectW` at `0x180083eff`
- `GDI32!SetLayout` at `0x180083f96`
- `GDI32!SetLayout` at `0x180083f96`
- `GDI32!DeleteDC` at `0x180083f53`
- `GDI32!DeleteDC` at `0x180083fef`
- `GDI32!DeleteDC` at `0x180083ff8`
- `GDI32!DeleteDC` at `0x180083f53`
- `GDI32!DeleteDC` at `0x180083fef`
- `GDI32!DeleteDC` at `0x180083ff8`
- `USER32!GetDC` at `0x180083f0b`
- `USER32!GetDC` at `0x180083f0b`
- `USER32!ReleaseDC` at `0x180083f2a`
- `USER32!ReleaseDC` at `0x180084003`
- `USER32!ReleaseDC` at `0x180083f2a`
- `USER32!ReleaseDC` at `0x180084003`

## pseudocode

```c
HBITMAP __fastcall CImageList::_CreateMirroredBitmap(CImageList *this, HBITMAP a2)
{
  HDC DC; // rsi
  HDC hdcSrc; // rbp
  HDC CompatibleDC; // r15
  void *ColorBitmap; // r14
  HGDIOBJ v8; // rdi
  HGDIOBJ v9; // rbx
  _OWORD pv[5]; // [rsp+50h] [rbp-58h] BYREF

  memset(pv, 0, 32);
  if ( !a2 || !GetObjectW(a2, 32, pv) )
    return 0;
  DC = GetDC(0);
  hdcSrc = CreateCompatibleDC(DC);
  if ( !hdcSrc )
  {
LABEL_4:
    ReleaseDC(0, DC);
    return 0;
  }
  CompatibleDC = CreateCompatibleDC(DC);
  if ( !CompatibleDC )
  {
    DeleteDC(hdcSrc);
    goto LABEL_4;
  }
  ColorBitmap = (void *)CreateColorBitmap(SDWORD1(pv[0]), SDWORD2(pv[0]));
  if ( ColorBitmap )
  {
    v8 = SelectObject(hdcSrc, a2);
    v9 = SelectObject(CompatibleDC, ColorBitmap);
    SetLayout(CompatibleDC, 1u);
    BitBlt(CompatibleDC, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), hdcSrc, 0, 0, 0xCC0020u);
    SelectObject(hdcSrc, v8);
    SelectObject(hdcSrc, v9);
  }
  DeleteDC(CompatibleDC);
  DeleteDC(hdcSrc);
  ReleaseDC(0, DC);
  return (HBITMAP)ColorBitmap;
}

```

## disassembly

```asm
0x180083ed0  push    rbx
0x180083ed2  push    rbp
0x180083ed3  push    rsi
0x180083ed4  push    rdi
0x180083ed5  push    r14
0x180083ed7  push    r15
0x180083ed9  sub     rsp, 78h
0x180083edd  xorps   xmm0, xmm0
0x180083ee0  mov     rbx, rdx
0x180083ee3  movups  [rsp+0A8h+pv], xmm0
0x180083ee8  movups  [rsp+0A8h+var_48], xmm0
0x180083eed  test    rdx, rdx
0x180083ef0  jz      short loc_180083F30
0x180083ef2  lea     r8, [rsp+0A8h+pv]; pv
0x180083ef7  mov     edx, 20h ; ' '; c
0x180083efc  mov     rcx, rbx; h
0x180083eff  call    cs:__imp_GetObjectW
0x180083f05  test    eax, eax
0x180083f07  jz      short loc_180083F30
0x180083f09  xor     ecx, ecx; hWnd
0x180083f0b  call    cs:__imp_GetDC
0x180083f11  mov     rcx, rax; hdc
0x180083f14  mov     rsi, rax
0x180083f17  call    cs:__imp_CreateCompatibleDC
0x180083f1d  mov     rbp, rax
0x180083f20  test    rax, rax
0x180083f23  jnz     short loc_180083F3F
0x180083f25  mov     rdx, rsi; hDC
0x180083f28  xor     ecx, ecx; hWnd
0x180083f2a  call    cs:__imp_ReleaseDC
0x180083f30  xor     eax, eax
0x180083f32  add     rsp, 78h
0x180083f36  pop     r15
0x180083f38  pop     r14
0x180083f3a  pop     rdi
0x180083f3b  pop     rsi
0x180083f3c  pop     rbp
0x180083f3d  pop     rbx
0x180083f3e  retn
0x180083f3f  mov     rcx, rsi; hdc
0x180083f42  call    cs:__imp_CreateCompatibleDC
0x180083f48  mov     r15, rax
0x180083f4b  test    rax, rax
0x180083f4e  jnz     short loc_180083F5B
0x180083f50  mov     rcx, rbp; hdc
0x180083f53  call    cs:__imp_DeleteDC
0x180083f59  jmp     short loc_180083F25
0x180083f5b  mov     edx, dword ptr [rsp+0A8h+pv+8]; cy
0x180083f5f  mov     ecx, dword ptr [rsp+0A8h+pv+4]; cx
0x180083f63  call    CreateColorBitmap
0x180083f68  mov     r14, rax
0x180083f6b  test    rax, rax
0x180083f6e  jz      short loc_180083FEC
0x180083f70  mov     rdx, rbx; h
0x180083f73  mov     rcx, rbp; hdc
0x180083f76  call    cs:__imp_SelectObject
0x180083f7c  mov     rdx, r14; h
0x180083f7f  mov     rcx, r15; hdc
0x180083f82  mov     rdi, rax
0x180083f85  call    cs:__imp_SelectObject
0x180083f8b  mov     edx, 1; l
0x180083f90  mov     rcx, r15; hdc
0x180083f93  mov     rbx, rax
0x180083f96  call    cs:__imp_SetLayout
0x180083f9c  mov     ecx, dword ptr [rsp+0A8h+pv+8]
0x180083fa0  xor     r8d, r8d; y
0x180083fa3  mov     r9d, dword ptr [rsp+0A8h+pv+4]; cx
0x180083fa8  xor     edx, edx; x
0x180083faa  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x180083fb2  mov     [rsp+0A8h+y1], 0; y1
0x180083fba  mov     [rsp+0A8h+x1], 0; x1
0x180083fc2  mov     [rsp+0A8h+hdcSrc], rbp; hdcSrc
0x180083fc7  mov     [rsp+0A8h+cy], ecx; cy
0x180083fcb  mov     rcx, r15; hdc
0x180083fce  call    cs:__imp_BitBlt
0x180083fd4  mov     rdx, rdi; h
0x180083fd7  mov     rcx, rbp; hdc
0x180083fda  call    cs:__imp_SelectObject
0x180083fe0  mov     rdx, rbx; h
0x180083fe3  mov     rcx, rbp; hdc
0x180083fe6  call    cs:__imp_SelectObject
0x180083fec  mov     rcx, r15; hdc
0x180083fef  call    cs:__imp_DeleteDC
0x180083ff5  mov     rcx, rbp; hdc
0x180083ff8  call    cs:__imp_DeleteDC
0x180083ffe  mov     rdx, rsi; hDC
0x180084001  xor     ecx, ecx; hWnd
0x180084003  call    cs:__imp_ReleaseDC
0x180084009  mov     rax, r14
0x18008400c  jmp     loc_180083F32
```
