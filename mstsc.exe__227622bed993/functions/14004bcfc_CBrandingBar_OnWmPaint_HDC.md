# CBrandingBar::OnWmPaint(HDC__ *)

- ea: `0x14004bcfc`
- end: `0x14004bd7f`
- name: `?OnWmPaint@CBrandingBar@@QEAAXPEAUHDC__@@@Z`
- size: `131`
- prototype: `void(CBrandingBar *__hidden this, HDC)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140023ba0`
- `0x14004a0fc`
- `0x140052d34`

## callees

- `0x14004bcfc`

## import_xrefs

- `GDI32!DeleteDC` at `0x14004bd69`
- `GDI32!DeleteDC` at `0x14004bd69`
- `GDI32!BitBlt` at `0x14004bd60`
- `GDI32!BitBlt` at `0x14004bd60`
- `GDI32!CreateCompatibleDC` at `0x14004bd14`
- `GDI32!CreateCompatibleDC` at `0x14004bd14`
- `GDI32!SelectObject` at `0x14004bd29`
- `GDI32!SelectObject` at `0x14004bd29`

## pseudocode

```c
void __fastcall CBrandingBar::OnWmPaint(CBrandingBar *this, HDC a2)
{
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rbx

  CompatibleDC = CreateCompatibleDC(a2);
  hdcSrc = CompatibleDC;
  if ( CompatibleDC )
  {
    SelectObject(CompatibleDC, *((HGDIOBJ *)this + 7));
    BitBlt(a2, 0, *((_DWORD *)this + 20), *((_DWORD *)this + 8), *((_DWORD *)this + 9), hdcSrc, 0, 0, 0xCC0020u);
    DeleteDC(hdcSrc);
  }
}

```

## disassembly

```asm
0x14004bcfc  mov     [rsp+arg_0], rbx
0x14004bd01  mov     [rsp+arg_8], rsi
0x14004bd06  push    rdi
0x14004bd07  sub     rsp, 50h
0x14004bd0b  mov     rdi, rcx
0x14004bd0e  mov     rsi, rdx
0x14004bd11  mov     rcx, rdx; hdc
0x14004bd14  call    cs:__imp_CreateCompatibleDC
0x14004bd1a  mov     rbx, rax
0x14004bd1d  test    rax, rax
0x14004bd20  jz      short loc_14004BD6F
0x14004bd22  mov     rdx, [rdi+38h]; h
0x14004bd26  mov     rcx, rax; hdc
0x14004bd29  call    cs:__imp_SelectObject
0x14004bd2f  mov     ecx, [rdi+24h]
0x14004bd32  xor     edx, edx; x
0x14004bd34  mov     r9d, [rdi+20h]; cx
0x14004bd38  mov     r8d, [rdi+50h]; y
0x14004bd3c  mov     [rsp+58h+rop], 0CC0020h; rop
0x14004bd44  mov     [rsp+58h+y1], 0; y1
0x14004bd4c  mov     [rsp+58h+x1], 0; x1
0x14004bd54  mov     [rsp+58h+hdcSrc], rbx; hdcSrc
0x14004bd59  mov     [rsp+58h+cy], ecx; cy
0x14004bd5d  mov     rcx, rsi; hdc
0x14004bd60  call    cs:__imp_BitBlt
0x14004bd66  mov     rcx, rbx; hdc
0x14004bd69  call    cs:__imp_DeleteDC
0x14004bd6f  mov     rbx, [rsp+58h+arg_0]
0x14004bd74  mov     rsi, [rsp+58h+arg_8]
0x14004bd79  add     rsp, 50h
0x14004bd7d  pop     rdi
0x14004bd7e  retn
```
