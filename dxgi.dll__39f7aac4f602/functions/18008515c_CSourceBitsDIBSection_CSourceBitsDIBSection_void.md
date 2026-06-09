# CSourceBitsDIBSection::~CSourceBitsDIBSection(void)

- ea: `0x18008515c`
- end: `0x1800851a5`
- name: `??1CSourceBitsDIBSection@@UEAA@XZ`
- size: `73`
- prototype: `void __fastcall(CSourceBitsDIBSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180085280`

## callees

- `0x18008515c`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18008518f`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18008518f`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18008517c`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18008517c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180085185`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180085185`

## pseudocode

```c
void __fastcall CSourceBitsDIBSection::~CSourceBitsDIBSection(CSourceBitsDIBSection *this)
{
  HDC v2; // rcx
  HGDIOBJ v3; // rax

  *(_QWORD *)this = &CSourceBitsDIBSection::`vftable';
  v2 = (HDC)*((_QWORD *)this + 2);
  if ( v2 )
  {
    v3 = SelectObject(v2, *((HGDIOBJ *)this + 1));
    DeleteObject(v3);
    DeleteDC(*((HDC *)this + 2));
  }
  *(_QWORD *)this = &CSourceBits::`vftable';
}

```

## disassembly

```asm
0x18008515c  push    rbx
0x18008515e  sub     rsp, 20h
0x180085162  lea     rax, ??_7CSourceBitsDIBSection@@6B@; const CSourceBitsDIBSection::`vftable'
0x180085169  mov     rbx, rcx
0x18008516c  mov     [rcx], rax
0x18008516f  mov     rcx, [rcx+10h]; hdc
0x180085173  test    rcx, rcx
0x180085176  jz      short loc_180085195
0x180085178  mov     rdx, [rbx+8]; h
0x18008517c  call    cs:__imp_SelectObject
0x180085182  mov     rcx, rax; ho
0x180085185  call    cs:__imp_DeleteObject
0x18008518b  mov     rcx, [rbx+10h]; hdc
0x18008518f  call    cs:__imp_DeleteDC
0x180085195  lea     rax, ??_7CSourceBits@@6B@; const CSourceBits::`vftable'
0x18008519c  mov     [rbx], rax
0x18008519f  add     rsp, 20h
0x1800851a3  pop     rbx
0x1800851a4  retn
```
