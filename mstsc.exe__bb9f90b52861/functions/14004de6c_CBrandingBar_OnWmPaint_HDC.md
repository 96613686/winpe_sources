# CBrandingBar::OnWmPaint(HDC__ *)

- ea: `0x14004de6c`
- end: `0x14004deef`
- name: `?OnWmPaint@CBrandingBar@@QEAAXPEAUHDC__@@@Z`
- size: `131`
- prototype: `void(CBrandingBar *__hidden this, HDC)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140023ba0`
- `0x14004c26c`
- `0x140054ea4`

## callees

- `0x14004de6c`

## import_xrefs

- `GDI32!DeleteDC` at `0x14004ded9`
- `GDI32!DeleteDC` at `0x14004ded9`
- `GDI32!BitBlt` at `0x14004ded0`
- `GDI32!BitBlt` at `0x14004ded0`
- `GDI32!CreateCompatibleDC` at `0x14004de84`
- `GDI32!CreateCompatibleDC` at `0x14004de84`
- `GDI32!SelectObject` at `0x14004de99`
- `GDI32!SelectObject` at `0x14004de99`

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
0x14004de6c  mov     [rsp+arg_0], rbx
0x14004de71  mov     [rsp+arg_8], rsi
0x14004de76  push    rdi
0x14004de77  sub     rsp, 50h
0x14004de7b  mov     rdi, rcx
0x14004de7e  mov     rsi, rdx
0x14004de81  mov     rcx, rdx; hdc
0x14004de84  call    cs:__imp_CreateCompatibleDC
0x14004de8a  mov     rbx, rax
0x14004de8d  test    rax, rax
0x14004de90  jz      short loc_14004DEDF
0x14004de92  mov     rdx, [rdi+38h]; h
0x14004de96  mov     rcx, rax; hdc
0x14004de99  call    cs:__imp_SelectObject
0x14004de9f  mov     ecx, [rdi+24h]
0x14004dea2  xor     edx, edx; x
0x14004dea4  mov     r9d, [rdi+20h]; cx
0x14004dea8  mov     r8d, [rdi+50h]; y
0x14004deac  mov     [rsp+58h+rop], 0CC0020h; rop
0x14004deb4  mov     [rsp+58h+y1], 0; y1
0x14004debc  mov     [rsp+58h+x1], 0; x1
0x14004dec4  mov     [rsp+58h+hdcSrc], rbx; hdcSrc
0x14004dec9  mov     [rsp+58h+cy], ecx; cy
0x14004decd  mov     rcx, rsi; hdc
0x14004ded0  call    cs:__imp_BitBlt
0x14004ded6  mov     rcx, rbx; hdc
0x14004ded9  call    cs:__imp_DeleteDC
0x14004dedf  mov     rbx, [rsp+58h+arg_0]
0x14004dee4  mov     rsi, [rsp+58h+arg_8]
0x14004dee9  add     rsp, 50h
0x14004deed  pop     rdi
0x14004deee  retn
```
