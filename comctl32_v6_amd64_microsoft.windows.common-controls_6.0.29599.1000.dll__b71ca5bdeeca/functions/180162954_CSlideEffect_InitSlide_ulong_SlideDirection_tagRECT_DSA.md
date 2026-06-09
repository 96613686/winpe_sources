# CSlideEffect::InitSlide(ulong,SlideDirection,tagRECT *,_DSA *)

- ea: `0x180162954`
- end: `0x180162ac2`
- name: `?InitSlide@CSlideEffect@@QEAAJKW4SlideDirection@@PEAUtagRECT@@PEAU_DSA@@@Z`
- size: `366`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800fec40`

## callees

- `0x18000d610`
- `0x180162954`
- `0x1801d1010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180162a39`
- `GDI32!DeleteObject` at `0x180162a39`
- `GDI32!CombineRgn` at `0x180162a23`
- `GDI32!CombineRgn` at `0x180162a68`
- `GDI32!CombineRgn` at `0x180162a23`
- `GDI32!CombineRgn` at `0x180162a68`
- `GDI32!CreateRectRgn` at `0x1801629a8`
- `GDI32!CreateRectRgn` at `0x1801629c8`
- `GDI32!CreateRectRgn` at `0x180162a86`
- `GDI32!CreateRectRgn` at `0x1801629a8`
- `GDI32!CreateRectRgn` at `0x1801629c8`
- `GDI32!CreateRectRgn` at `0x180162a86`
- `GDI32!CreateRectRgnIndirect` at `0x180162a43`
- `GDI32!CreateRectRgnIndirect` at `0x180162a43`
- `GDI32!SetRectRgn` at `0x180162a06`
- `GDI32!SetRectRgn` at `0x180162a06`

## pseudocode

```c
__int64 __fastcall CSlideEffect::InitSlide(__int64 a1, __int64 a2, int a3, __int128 *a4, __int64 a5)
{
  unsigned int v6; // ecx
  __int128 v7; // xmm0
  HRGN RectRgn; // rax
  HRGN v9; // rsi
  struct _DSA *v10; // rcx
  int v11; // edi
  int *ItemPtr; // rax
  HRGN RectRgnIndirect; // rax
  HRGN v14; // rax

  v6 = 0;
  *(_DWORD *)(a1 + 48) = 250;
  *(_DWORD *)(a1 + 208) = a3;
  if ( !a4 )
    a4 = (__int128 *)(a1 + 32);
  v7 = *a4;
  *(_QWORD *)(a1 + 232) = a5;
  *(_OWORD *)(a1 + 212) = v7;
  if ( a5 )
  {
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    *(_QWORD *)(a1 + 240) = RectRgn;
    if ( !RectRgn )
      goto LABEL_16;
    v9 = CreateRectRgn(0, 0, 0, 0);
    if ( !v9 )
      goto LABEL_16;
    v10 = *(struct _DSA **)(a1 + 232);
    if ( *(int *)v10 > 0 )
    {
      v11 = 0;
      do
      {
        ItemPtr = (int *)DSA_GetItemPtr(v10, v11);
        if ( SetRectRgn(v9, *ItemPtr, ItemPtr[1], ItemPtr[2], ItemPtr[3]) )
          CombineRgn(*(HRGN *)(a1 + 240), *(HRGN *)(a1 + 240), v9, 2);
        v10 = *(struct _DSA **)(a1 + 232);
        ++v11;
      }
      while ( v11 < *(_DWORD *)v10 );
    }
    DeleteObject(v9);
    RectRgnIndirect = CreateRectRgnIndirect((const RECT *)(a1 + 32));
    *(_QWORD *)(a1 + 248) = RectRgnIndirect;
    if ( RectRgnIndirect
      && CombineRgn(RectRgnIndirect, RectRgnIndirect, *(HRGN *)(a1 + 240), 4)
      && (*(_QWORD *)(a1 + 128) || (v14 = CreateRectRgn(0, 0, 0, 0), (*(_QWORD *)(a1 + 128) = v14) != 0)) )
    {
      return 0;
    }
    else
    {
LABEL_16:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      return (unsigned int)-2147467259;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180162954  mov     [rsp+arg_0], rbx
0x180162959  mov     [rsp+arg_8], rsi
0x18016295e  push    rdi
0x18016295f  sub     rsp, 30h
0x180162963  mov     rbx, rcx
0x180162966  xor     ecx, ecx; x1
0x180162968  mov     dword ptr [rbx+30h], 0FAh
0x18016296f  mov     [rbx+0D0h], r8d
0x180162976  test    r9, r9
0x180162979  jnz     short loc_18016297F
0x18016297b  lea     r9, [rbx+20h]
0x18016297f  movups  xmm0, xmmword ptr [r9]
0x180162983  mov     rax, [rsp+38h+arg_20]
0x180162988  mov     [rbx+0E8h], rax
0x18016298f  movdqu  xmmword ptr [rbx+0D4h], xmm0
0x180162997  test    rax, rax
0x18016299a  jz      loc_180162AB0
0x1801629a0  xor     r9d, r9d; y2
0x1801629a3  xor     r8d, r8d; x2
0x1801629a6  xor     edx, edx; y1
0x1801629a8  call    cs:__imp_CreateRectRgn
0x1801629ae  mov     [rbx+0F0h], rax
0x1801629b5  test    rax, rax
0x1801629b8  jz      loc_180162A9C
0x1801629be  xor     r9d, r9d; y2
0x1801629c1  xor     r8d, r8d; x2
0x1801629c4  xor     edx, edx; y1
0x1801629c6  xor     ecx, ecx; x1
0x1801629c8  call    cs:__imp_CreateRectRgn
0x1801629ce  mov     rsi, rax
0x1801629d1  test    rax, rax
0x1801629d4  jz      loc_180162A9C
0x1801629da  mov     rcx, [rbx+0E8h]; hdsa
0x1801629e1  cmp     dword ptr [rcx], 0
0x1801629e4  jle     short loc_180162A36
0x1801629e6  xor     edi, edi
0x1801629e8  mov     edx, edi; i
0x1801629ea  call    DSA_GetItemPtr
0x1801629ef  mov     rdx, rax
0x1801629f2  mov     rcx, rsi; hrgn
0x1801629f5  mov     eax, [rax+0Ch]
0x1801629f8  mov     r9d, [rdx+8]; right
0x1801629fc  mov     r8d, [rdx+4]; top
0x180162a00  mov     edx, [rdx]; left
0x180162a02  mov     [rsp+38h+bottom], eax; bottom
0x180162a06  call    cs:__imp_SetRectRgn
0x180162a0c  test    eax, eax
0x180162a0e  jz      short loc_180162A29
0x180162a10  mov     rcx, [rbx+0F0h]; hrgnDst
0x180162a17  mov     r9d, 2; iMode
0x180162a1d  mov     rdx, rcx; hrgnSrc1
0x180162a20  mov     r8, rsi; hrgnSrc2
0x180162a23  call    cs:__imp_CombineRgn
0x180162a29  mov     rcx, [rbx+0E8h]
0x180162a30  inc     edi
0x180162a32  cmp     edi, [rcx]
0x180162a34  jl      short loc_1801629E8
0x180162a36  mov     rcx, rsi; ho
0x180162a39  call    cs:__imp_DeleteObject
0x180162a3f  lea     rcx, [rbx+20h]; lprect
0x180162a43  call    cs:__imp_CreateRectRgnIndirect
0x180162a49  mov     [rbx+0F8h], rax
0x180162a50  test    rax, rax
0x180162a53  jz      short loc_180162A9C
0x180162a55  mov     r8, [rbx+0F0h]; hrgnSrc2
0x180162a5c  mov     r9d, 4; iMode
0x180162a62  mov     rdx, rax; hrgnSrc1
0x180162a65  mov     rcx, rax; hrgnDst
0x180162a68  call    cs:__imp_CombineRgn
0x180162a6e  test    eax, eax
0x180162a70  jz      short loc_180162A9C
0x180162a72  cmp     qword ptr [rbx+80h], 0
0x180162a7a  jnz     short loc_180162A98
0x180162a7c  xor     r9d, r9d; y2
0x180162a7f  xor     r8d, r8d; x2
0x180162a82  xor     edx, edx; y1
0x180162a84  xor     ecx, ecx; x1
0x180162a86  call    cs:__imp_CreateRectRgn
0x180162a8c  mov     [rbx+80h], rax
0x180162a93  test    rax, rax
0x180162a96  jz      short loc_180162A9C
0x180162a98  xor     ecx, ecx
0x180162a9a  jmp     short loc_180162AB0
0x180162a9c  mov     rax, [rbx]
0x180162a9f  mov     rcx, rbx
0x180162aa2  mov     rax, [rax+20h]
0x180162aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180162aab  mov     ecx, 80004005h
0x180162ab0  mov     rbx, [rsp+38h+arg_0]
0x180162ab5  mov     eax, ecx
0x180162ab7  mov     rsi, [rsp+38h+arg_8]
0x180162abc  add     rsp, 30h
0x180162ac0  pop     rdi
0x180162ac1  retn
```
