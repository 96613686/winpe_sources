# DWriteCore::Binding::Windows::GdiBitmap::GdiBitmap(HDC__ *,uint,uint)

- ea: `0x1802939c0`
- end: `0x180293a38`
- name: `??0GdiBitmap@Windows@Binding@DWriteCore@@QEAA@PEAUHDC__@@II@Z`
- size: `120`
- prototype: `__int64 __fastcall(DWriteCore::Binding::Windows::GdiBitmap *__hidden this, HDC, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18028f78c`

## callees

- `0x180293b18`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180293a1b`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180293a1b`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1802939e8`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x1802939e8`
- `ext-ms-win-gdi-draw-l1-1-0!SetGraphicsMode` at `0x180293a0d`
- `ext-ms-win-gdi-draw-l1-1-0!SetGraphicsMode` at `0x180293a0d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180293a24`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180293a24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWriteCore::Binding::Windows::GdiBitmap *__fastcall DWriteCore::Binding::Windows::GdiBitmap::GdiBitmap(
        DWriteCore::Binding::Windows::GdiBitmap *this,
        HDC a2,
        unsigned int a3,
        unsigned int a4)
{
  HDC CompatibleDC; // rax
  HGDIOBJ v8; // rax

  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &DWriteCore::Binding::Windows::GdiBitmap::`vftable';
  CompatibleDC = CreateCompatibleDC(0);
  *((_QWORD *)this + 2) = CompatibleDC;
  DWriteCore::Binding::Windows::GdiBitmap::CreateBitmap((char *)this + 24, CompatibleDC, a3, a4);
  SetGraphicsMode(*((HDC *)this + 2), 2);
  v8 = SelectObject(*((HDC *)this + 2), *((HGDIOBJ *)this + 3));
  DeleteObject(v8);
  return this;
}

```

## disassembly

```asm
0x1802939c0  mov     [rsp+arg_0], rcx
0x1802939c5  push    rbx
0x1802939c6  push    rsi
0x1802939c7  push    rdi
0x1802939c8  push    r14
0x1802939ca  sub     rsp, 28h
0x1802939ce  mov     edi, r9d
0x1802939d1  mov     esi, r8d
0x1802939d4  mov     r14, rcx
0x1802939d7  xor     eax, eax
0x1802939d9  mov     [rcx+8], eax
0x1802939dc  lea     rax, ??_7GdiBitmap@Windows@Binding@DWriteCore@@6B@; const DWriteCore::Binding::Windows::GdiBitmap::`vftable'
0x1802939e3  mov     [rcx], rax
0x1802939e6  xor     ecx, ecx; hdc
0x1802939e8  call    cs:__imp_CreateCompatibleDC
0x1802939ee  mov     [r14+10h], rax
0x1802939f2  mov     r9d, edi
0x1802939f5  mov     r8d, esi
0x1802939f8  mov     rdx, rax
0x1802939fb  lea     rcx, [r14+18h]
0x1802939ff  call    ?CreateBitmap@GdiBitmap@Windows@Binding@DWriteCore@@CA?AUBitmap@1234@PEAUHDC__@@II@Z; DWriteCore::Binding::Windows::GdiBitmap::CreateBitmap(HDC__ *,uint,uint)
0x180293a04  mov     edx, 2; iMode
0x180293a09  mov     rcx, [r14+10h]; hdc
0x180293a0d  call    cs:__imp_SetGraphicsMode
0x180293a13  mov     rdx, [r14+18h]; h
0x180293a17  mov     rcx, [r14+10h]; hdc
0x180293a1b  call    cs:__imp_SelectObject
0x180293a21  mov     rcx, rax; ho
0x180293a24  call    cs:__imp_DeleteObject
0x180293a2a  nop
0x180293a2b  mov     rax, r14
0x180293a2e  add     rsp, 28h
0x180293a32  pop     r14
0x180293a34  pop     rdi
0x180293a35  pop     rsi
0x180293a36  pop     rbx
0x180293a37  retn
```
