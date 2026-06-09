# OleUIDrawShading(tagRECT *,HDC__ *)

- ea: `0x18015229c`
- end: `0x18015241f`
- name: `?OleUIDrawShading@@YAXPEAUtagRECT@@PEAUHDC__@@@Z`
- size: `387`
- prototype: `void(struct tagRECT *, HDC)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1801fb730`

## callees

- `0x18013ce80`
- `0x18015229c`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180152338`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801523ce`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180152338`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801523ce`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x180152362`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x1801523bc`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x180152362`
- `ext-ms-win-gdi-draw-l1-1-1!SetBkColor` at `0x1801523bc`
- `ext-ms-win-gdi-draw-l1-1-1!PatBlt` at `0x18015239a`
- `ext-ms-win-gdi-draw-l1-1-1!PatBlt` at `0x18015239a`
- `ext-ms-win-gdi-draw-l1-1-1!CreatePatternBrush` at `0x18015231a`
- `ext-ms-win-gdi-draw-l1-1-1!CreatePatternBrush` at `0x18015231a`
- `ext-ms-win-gdi-draw-l1-1-0!CreateBitmap` at `0x1801522ff`
- `ext-ms-win-gdi-draw-l1-1-0!CreateBitmap` at `0x1801522ff`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x18015234f`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x1801523ab`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x18015234f`
- `ext-ms-win-gdi-font-l1-1-1!SetTextColor` at `0x1801523ab`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801523dd`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801523ec`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801523dd`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801523ec`

## pseudocode

```c
void __fastcall OleUIDrawShading(struct tagRECT *a1, HDC a2)
{
  HBITMAP Bitmap; // rax
  HBITMAP v5; // rbp
  HBRUSH PatternBrush; // rax
  HBRUSH v7; // r14
  HGDIOBJ v8; // rsi
  COLORREF v9; // edi
  COLORREF v10; // ebx
  _DWORD v11[4]; // [rsp+30h] [rbp-48h] BYREF

  v11[0] = 2228241;
  v11[1] = 8912964;
  v11[2] = 2228241;
  v11[3] = 8912964;
  Bitmap = CreateBitmap(8, 8, 1u, 1u, v11);
  v5 = Bitmap;
  if ( Bitmap )
  {
    PatternBrush = CreatePatternBrush(Bitmap);
    v7 = PatternBrush;
    if ( PatternBrush )
    {
      v8 = SelectObject(a2, PatternBrush);
      v9 = SetTextColor(a2, 0xFFFFFFu);
      v10 = SetBkColor(a2, 0);
      PatBlt(a2, a1->left, a1->top, a1->right - a1->left, a1->bottom - a1->top, 0xA000C9u);
      SetTextColor(a2, v9);
      SetBkColor(a2, v10);
      SelectObject(a2, v8);
      DeleteObject(v7);
    }
    DeleteObject(v5);
  }
}

```

## disassembly

```asm
0x18015229c  mov     r11, rsp
0x18015229f  mov     [r11+18h], rbx
0x1801522a3  mov     [r11+20h], rbp
0x1801522a7  push    rsi
0x1801522a8  push    rdi
0x1801522a9  push    r12
0x1801522ab  push    r14
0x1801522ad  push    r15
0x1801522af  sub     rsp, 50h
0x1801522b3  mov     rax, cs:__security_cookie
0x1801522ba  xor     rax, rsp
0x1801522bd  mov     [rsp+78h+var_38], rax
0x1801522c2  mov     r8d, 1; nPlanes
0x1801522c8  mov     [rsp+78h+var_48], 220011h
0x1801522d0  mov     r12, rcx
0x1801522d3  mov     [rsp+78h+var_44], 880044h
0x1801522db  mov     r15, rdx
0x1801522de  mov     [rsp+78h+var_40], 220011h
0x1801522e6  lea     rax, [r11-48h]
0x1801522ea  mov     [rsp+78h+var_3C], 880044h
0x1801522f2  lea     ecx, [r8+7]; nWidth
0x1801522f6  mov     [r11-58h], rax
0x1801522fa  mov     edx, ecx; nHeight
0x1801522fc  mov     r9d, r8d; nBitCount
0x1801522ff  call    cs:__imp_CreateBitmap
0x180152306  nop     dword ptr [rax+rax+00h]
0x18015230b  mov     rbp, rax
0x18015230e  test    rax, rax
0x180152311  jz      loc_1801523F8
0x180152317  mov     rcx, rax; hbm
0x18015231a  call    cs:__imp_CreatePatternBrush
0x180152321  nop     dword ptr [rax+rax+00h]
0x180152326  mov     r14, rax
0x180152329  test    rax, rax
0x18015232c  jz      loc_1801523E9
0x180152332  mov     rdx, rax; h
0x180152335  mov     rcx, r15; hdc
0x180152338  call    cs:__imp_SelectObject
0x18015233f  nop     dword ptr [rax+rax+00h]
0x180152344  mov     edx, 0FFFFFFh; color
0x180152349  mov     rcx, r15; hdc
0x18015234c  mov     rsi, rax
0x18015234f  call    cs:__imp_SetTextColor
0x180152356  nop     dword ptr [rax+rax+00h]
0x18015235b  xor     edx, edx; color
0x18015235d  mov     rcx, r15; hdc
0x180152360  mov     edi, eax
0x180152362  call    cs:__imp_SetBkColor
0x180152369  nop     dword ptr [rax+rax+00h]
0x18015236e  mov     r10d, [r12+0Ch]
0x180152373  mov     rcx, r15; hdc
0x180152376  mov     r8d, [r12+4]; y
0x18015237b  mov     ebx, eax
0x18015237d  mov     r9d, [r12+8]
0x180152382  sub     r10d, r8d
0x180152385  sub     r9d, [r12]; w
0x180152389  mov     edx, [r12]; x
0x18015238d  mov     [rsp+78h+rop], 0A000C9h; rop
0x180152395  mov     [rsp+78h+h], r10d; h
0x18015239a  call    cs:__imp_PatBlt
0x1801523a1  nop     dword ptr [rax+rax+00h]
0x1801523a6  mov     edx, edi; color
0x1801523a8  mov     rcx, r15; hdc
0x1801523ab  call    cs:__imp_SetTextColor
0x1801523b2  nop     dword ptr [rax+rax+00h]
0x1801523b7  mov     edx, ebx; color
0x1801523b9  mov     rcx, r15; hdc
0x1801523bc  call    cs:__imp_SetBkColor
0x1801523c3  nop     dword ptr [rax+rax+00h]
0x1801523c8  mov     rdx, rsi; h
0x1801523cb  mov     rcx, r15; hdc
0x1801523ce  call    cs:__imp_SelectObject
0x1801523d5  nop     dword ptr [rax+rax+00h]
0x1801523da  mov     rcx, r14; ho
0x1801523dd  call    cs:__imp_DeleteObject
0x1801523e4  nop     dword ptr [rax+rax+00h]
0x1801523e9  mov     rcx, rbp; ho
0x1801523ec  call    cs:__imp_DeleteObject
0x1801523f3  nop     dword ptr [rax+rax+00h]
0x1801523f8  mov     rcx, [rsp+78h+var_38]
0x1801523fd  xor     rcx, rsp; StackCookie
0x180152400  call    __security_check_cookie
0x180152405  lea     r11, [rsp+78h+var_28]
0x18015240a  mov     rbx, [r11+40h]
0x18015240e  mov     rbp, [r11+48h]
0x180152412  mov     rsp, r11
0x180152415  pop     r15
0x180152417  pop     r14
0x180152419  pop     r12
0x18015241b  pop     rdi
0x18015241c  pop     rsi
0x18015241d  retn
```
