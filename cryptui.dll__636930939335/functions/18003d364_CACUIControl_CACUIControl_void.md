# CACUIControl::~CACUIControl(void)

- ea: `0x18003d364`
- end: `0x18003d399`
- name: `??1CACUIControl@@UEAA@XZ`
- size: `53`
- prototype: `void __fastcall(CACUIControl *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18003c518`
- `0x18003cf50`
- `0x18003d3a0`

## callees

- `0x18003b2e8`

## import_xrefs

- `GDI32!DeleteObject` at `0x18003d37b`
- `GDI32!DeleteObject` at `0x18003d385`
- `GDI32!DeleteObject` at `0x18003d37b`
- `GDI32!DeleteObject` at `0x18003d385`

## pseudocode

```c
void __fastcall CACUIControl::~CACUIControl(HGDIOBJ *this)
{
  *this = &CACUIControl::`vftable';
  DeleteObject(this[7]);
  DeleteObject(this[8]);
  CACUIToolTip::Destroy((CACUIToolTip *)(this + 3));
}

```

## disassembly

```asm
0x18003d364  push    rbx
0x18003d366  sub     rsp, 20h
0x18003d36a  lea     rax, ??_7CACUIControl@@6B@; const CACUIControl::`vftable'
0x18003d371  mov     rbx, rcx
0x18003d374  mov     [rcx], rax
0x18003d377  mov     rcx, [rcx+38h]; ho
0x18003d37b  call    cs:__imp_DeleteObject
0x18003d381  mov     rcx, [rbx+40h]; ho
0x18003d385  call    cs:__imp_DeleteObject
0x18003d38b  lea     rcx, [rbx+18h]; this
0x18003d38f  add     rsp, 20h
0x18003d393  pop     rbx
0x18003d394  jmp     ?Destroy@CACUIToolTip@@QEAAXXZ; CACUIToolTip::Destroy(void)
```
