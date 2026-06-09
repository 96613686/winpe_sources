# PaintWithPaletteBitmap

- ea: `0x18001e120`
- end: `0x18001e29b`
- name: `PaintWithPaletteBitmap`
- size: `379`
- prototype: `__int64 __fastcall(HDC hdcDest)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ef50`
- `0x18001f60c`

## callees

- `0x18001e120`

## import_xrefs

- `GDI32!StretchBlt` at `0x18001e234`
- `GDI32!StretchBlt` at `0x18001e27a`
- `GDI32!StretchBlt` at `0x18001e234`
- `GDI32!StretchBlt` at `0x18001e27a`
- `GDI32!CreateCompatibleDC` at `0x18001e161`
- `GDI32!CreateCompatibleDC` at `0x18001e161`
- `GDI32!SelectObject` at `0x18001e170`
- `GDI32!SelectObject` at `0x18001e170`
- `GDI32!BitBlt` at `0x18001e1e8`
- `GDI32!BitBlt` at `0x18001e1e8`
- `GDI32!GetObjectW` at `0x18001e158`
- `GDI32!GetObjectW` at `0x18001e158`
- `GDI32!DeleteDC` at `0x18001e283`
- `GDI32!DeleteDC` at `0x18001e283`
- `GDI32!SelectPalette` at `0x18001e184`
- `GDI32!SelectPalette` at `0x18001e184`
- `GDI32!RealizePalette` at `0x18001e18d`
- `GDI32!RealizePalette` at `0x18001e18d`

## pseudocode

```c
BOOL __fastcall PaintWithPaletteBitmap(HDC hdcDest, int *a2, HPALETTE a3, void *a4)
{
  HDC hdcSrc; // rbp
  int v9; // r15d
  int v10; // r12d
  int v11; // r8d
  int v12; // ebx
  int cy; // esi
  _OWORD pv[5]; // [rsp+60h] [rbp-58h] BYREF

  memset(pv, 0, 32);
  GetObjectW(a4, 32, pv);
  hdcSrc = CreateCompatibleDC(hdcDest);
  SelectObject(hdcSrc, a4);
  if ( a3 )
  {
    SelectPalette(hdcDest, a3, 0);
    RealizePalette(hdcDest);
  }
  v9 = a2[2] - *a2;
  v10 = v9;
  v11 = a2[1];
  v12 = a2[3] - v11;
  cy = v12;
  if ( SDWORD1(pv[0]) < v9 )
    v10 = DWORD1(pv[0]);
  if ( SDWORD2(pv[0]) < v12 )
    cy = DWORD2(pv[0]);
  BitBlt(hdcDest, *a2, v11, v10, cy, hdcSrc, 0, 0, 0xCC0020u);
  if ( v10 < v9 )
    StretchBlt(hdcDest, v10 + *a2, a2[1], v9 - v10, cy, hdcSrc, 0, 0, 1, 1, 0xCC0020u);
  if ( cy < v12 )
    StretchBlt(hdcDest, *a2, cy, v9, v12 - cy, hdcSrc, 0, 0, 1, 1, 0xCC0020u);
  return DeleteDC(hdcSrc);
}

```

## disassembly

```asm
0x18001e120  push    rbx
0x18001e122  push    rbp
0x18001e123  push    rsi
0x18001e124  push    rdi
0x18001e125  push    r12
0x18001e127  push    r14
0x18001e129  push    r15
0x18001e12b  sub     rsp, 80h
0x18001e132  xorps   xmm0, xmm0
0x18001e135  mov     rsi, r8
0x18001e138  mov     r14, rdx
0x18001e13b  lea     r8, [rsp+0B8h+pv]; pv
0x18001e140  mov     rdi, rcx
0x18001e143  mov     edx, 20h ; ' '; c
0x18001e148  mov     rcx, r9; h
0x18001e14b  mov     rbx, r9
0x18001e14e  movups  [rsp+0B8h+pv], xmm0
0x18001e153  movups  [rsp+0B8h+var_48], xmm0
0x18001e158  call    cs:__imp_GetObjectW
0x18001e15e  mov     rcx, rdi; hdc
0x18001e161  call    cs:__imp_CreateCompatibleDC
0x18001e167  mov     rcx, rax; hdc
0x18001e16a  mov     rdx, rbx; h
0x18001e16d  mov     rbp, rax
0x18001e170  call    cs:__imp_SelectObject
0x18001e176  test    rsi, rsi
0x18001e179  jz      short loc_18001E193
0x18001e17b  xor     r8d, r8d; bForceBkgd
0x18001e17e  mov     rdx, rsi; hPal
0x18001e181  mov     rcx, rdi; hdc
0x18001e184  call    cs:__imp_SelectPalette
0x18001e18a  mov     rcx, rdi; hdc
0x18001e18d  call    cs:__imp_RealizePalette
0x18001e193  mov     r15d, [r14+8]
0x18001e197  mov     rcx, rdi; hdc
0x18001e19a  sub     r15d, [r14]
0x18001e19d  mov     ebx, [r14+0Ch]
0x18001e1a1  mov     r12d, r15d
0x18001e1a4  mov     r8d, [r14+4]; y
0x18001e1a8  sub     ebx, r8d
0x18001e1ab  cmp     dword ptr [rsp+0B8h+pv+4], r15d
0x18001e1b0  mov     esi, ebx
0x18001e1b2  mov     edx, [r14]; x
0x18001e1b5  cmovl   r12d, dword ptr [rsp+0B8h+pv+4]
0x18001e1bb  cmp     dword ptr [rsp+0B8h+pv+8], ebx
0x18001e1bf  mov     r9d, r12d; cx
0x18001e1c2  mov     [rsp+0B8h+rop], 0CC0020h; rop
0x18001e1ca  cmovl   esi, dword ptr [rsp+0B8h+pv+8]
0x18001e1cf  mov     [rsp+0B8h+y1], 0; y1
0x18001e1d7  mov     [rsp+0B8h+x1], 0; x1
0x18001e1df  mov     [rsp+0B8h+hdcSrc], rbp; hdcSrc
0x18001e1e4  mov     [rsp+0B8h+cy], esi; cy
0x18001e1e8  call    cs:__imp_BitBlt
0x18001e1ee  mov     ecx, 1
0x18001e1f3  cmp     r12d, r15d
0x18001e1f6  jge     short loc_18001E23F
0x18001e1f8  mov     edx, [r14]
0x18001e1fb  mov     r9d, r15d
0x18001e1fe  mov     r8d, [r14+4]; yDest
0x18001e202  sub     r9d, r12d; wDest
0x18001e205  mov     [rsp+0B8h+var_68], 0CC0020h; rop
0x18001e20d  add     edx, r12d; xDest
0x18001e210  mov     [rsp+0B8h+hSrc], ecx; hSrc
0x18001e214  mov     [rsp+0B8h+rop], ecx; wSrc
0x18001e218  mov     rcx, rdi; hdcDest
0x18001e21b  mov     [rsp+0B8h+y1], 0; ySrc
0x18001e223  mov     [rsp+0B8h+x1], 0; xSrc
0x18001e22b  mov     [rsp+0B8h+hdcSrc], rbp; hdcSrc
0x18001e230  mov     [rsp+0B8h+cy], esi; hDest
0x18001e234  call    cs:__imp_StretchBlt
0x18001e23a  mov     ecx, 1
0x18001e23f  cmp     esi, ebx
0x18001e241  jge     short loc_18001E280
0x18001e243  mov     edx, [r14]; xDest
0x18001e246  sub     ebx, esi
0x18001e248  mov     [rsp+0B8h+var_68], 0CC0020h; rop
0x18001e250  mov     r9d, r15d; wDest
0x18001e253  mov     [rsp+0B8h+hSrc], ecx; hSrc
0x18001e257  mov     r8d, esi; yDest
0x18001e25a  mov     [rsp+0B8h+rop], ecx; wSrc
0x18001e25e  mov     rcx, rdi; hdcDest
0x18001e261  mov     [rsp+0B8h+y1], 0; ySrc
0x18001e269  mov     [rsp+0B8h+x1], 0; xSrc
0x18001e271  mov     [rsp+0B8h+hdcSrc], rbp; hdcSrc
0x18001e276  mov     [rsp+0B8h+cy], ebx; hDest
0x18001e27a  call    cs:__imp_StretchBlt
0x18001e280  mov     rcx, rbp; hdc
0x18001e283  call    cs:__imp_DeleteDC
0x18001e289  add     rsp, 80h
0x18001e290  pop     r15
0x18001e292  pop     r14
0x18001e294  pop     r12
0x18001e296  pop     rdi
0x18001e297  pop     rsi
0x18001e298  pop     rbp
0x18001e299  pop     rbx
0x18001e29a  retn
```
