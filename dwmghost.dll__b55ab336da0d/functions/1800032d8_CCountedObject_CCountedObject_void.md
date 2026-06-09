# CCountedObject::CCountedObject(void)

- ea: `0x1800032d8`
- end: `0x1800032ee`
- name: `??0CCountedObject@@IEAA@XZ`
- size: `22`
- prototype: `CCountedObject *__fastcall(CCountedObject *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180005f24`
- `0x1800079f4`
- `0x1800082bc`
- `0x180008ce0`

## pseudocode

```c
CCountedObject *__fastcall CCountedObject::CCountedObject(CCountedObject *this)
{
  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &CCountedObject::`vftable';
  return this;
}

```

## disassembly

```asm
0x1800032d8  lea     rax, ??_7CCountedObject@@6B@; const CCountedObject::`vftable'
0x1800032df  mov     qword ptr [rcx+8], 1
0x1800032e7  mov     [rcx], rax
0x1800032ea  mov     rax, rcx
0x1800032ed  retn
```
