# COleObject::DrawDib(HDC__ *,tagRECT *)

- ea: `0x1801fb640`
- end: `0x1801fb72a`
- name: `?DrawDib@COleObject@@AEAAXPEAUHDC__@@PEAUtagRECT@@@Z`
- size: `234`
- prototype: `void __fastcall(void **this, HDC, struct tagRECT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801fb730`

## callees

- `0x1801fb4b0`
- `0x1801fb640`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801fb703`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801fb703`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801fb68a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801fb68a`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801fb712`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1801fb712`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801fb66e`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1801fb66e`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fb6a0`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1801fb6a0`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x1801fb6f4`
- `ext-ms-win-gdi-draw-l1-1-0!StretchBlt` at `0x1801fb6f4`

## pseudocode

```c
void __fastcall COleObject::DrawDib(void **this, HDC a2, struct tagRECT *a3)
{
  HDC hdcSrc; // rbp
  int *v7; // rbx

  if ( !this[15] )
    COleObject::CreateDib(this, a2);
  if ( this[15] )
  {
    hdcSrc = CreateCompatibleDC(a2);
    if ( hdcSrc )
    {
      v7 = (int *)GlobalLock(this[14]);
      SelectObject(hdcSrc, this[15]);
      StretchBlt(
        a2,
        a3->left,
        a3->top,
        a3->right - a3->left,
        a3->bottom - a3->top,
        hdcSrc,
        0,
        0,
        v7[1],
        v7[2],
        0xCC0020u);
      GlobalUnlock(v7);
      DeleteDC(hdcSrc);
    }
  }
}

```

## disassembly

```asm
0x1801fb640  push    rbx
0x1801fb642  push    rbp
0x1801fb643  push    rsi
0x1801fb644  push    rdi
0x1801fb645  push    r14
0x1801fb647  sub     rsp, 60h
0x1801fb64b  cmp     qword ptr [rcx+78h], 0
0x1801fb650  mov     r14, r8
0x1801fb653  mov     rsi, rdx
0x1801fb656  mov     rdi, rcx
0x1801fb659  jnz     short loc_1801FB660
0x1801fb65b  call    ?CreateDib@COleObject@@AEAAXPEAUHDC__@@@Z; COleObject::CreateDib(HDC__ *)
0x1801fb660  cmp     qword ptr [rdi+78h], 0
0x1801fb665  jz      loc_1801FB71E
0x1801fb66b  mov     rcx, rsi; hdc
0x1801fb66e  call    cs:__imp_CreateCompatibleDC
0x1801fb675  nop     dword ptr [rax+rax+00h]
0x1801fb67a  mov     rbp, rax
0x1801fb67d  test    rax, rax
0x1801fb680  jz      loc_1801FB71E
0x1801fb686  mov     rcx, [rdi+70h]; hMem
0x1801fb68a  call    cs:__imp_GlobalLock
0x1801fb691  nop     dword ptr [rax+rax+00h]
0x1801fb696  mov     rdx, [rdi+78h]; h
0x1801fb69a  mov     rcx, rbp; hdc
0x1801fb69d  mov     rbx, rax
0x1801fb6a0  call    cs:__imp_SelectObject
0x1801fb6a7  nop     dword ptr [rax+rax+00h]
0x1801fb6ac  mov     ecx, [rbx+8]
0x1801fb6af  mov     r10d, [r14+0Ch]
0x1801fb6b3  mov     r8d, [r14+4]; yDest
0x1801fb6b7  sub     r10d, r8d
0x1801fb6ba  mov     r9d, [r14+8]
0x1801fb6be  sub     r9d, [r14]; wDest
0x1801fb6c1  mov     edx, [r14]; xDest
0x1801fb6c4  mov     [rsp+88h+rop], 0CC0020h; rop
0x1801fb6cc  mov     [rsp+88h+hSrc], ecx; hSrc
0x1801fb6d0  mov     ecx, [rbx+4]
0x1801fb6d3  mov     [rsp+88h+wSrc], ecx; wSrc
0x1801fb6d7  mov     rcx, rsi; hdcDest
0x1801fb6da  mov     [rsp+88h+ySrc], 0; ySrc
0x1801fb6e2  mov     [rsp+88h+xSrc], 0; xSrc
0x1801fb6ea  mov     [rsp+88h+hdcSrc], rbp; hdcSrc
0x1801fb6ef  mov     [rsp+88h+hDest], r10d; hDest
0x1801fb6f4  call    cs:__imp_StretchBlt
0x1801fb6fb  nop     dword ptr [rax+rax+00h]
0x1801fb700  mov     rcx, rbx; hMem
0x1801fb703  call    cs:__imp_GlobalUnlock
0x1801fb70a  nop     dword ptr [rax+rax+00h]
0x1801fb70f  mov     rcx, rbp; hdc
0x1801fb712  call    cs:__imp_DeleteDC
0x1801fb719  nop     dword ptr [rax+rax+00h]
0x1801fb71e  add     rsp, 60h
0x1801fb722  pop     r14
0x1801fb724  pop     rdi
0x1801fb725  pop     rsi
0x1801fb726  pop     rbp
0x1801fb727  pop     rbx
0x1801fb728  retn
```
