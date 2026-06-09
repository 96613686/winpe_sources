# CCountedObject::~CCountedObject(void)

- ea: `0x1800033c0`
- end: `0x1800033cb`
- name: `??1CCountedObject@@MEAA@XZ`
- size: `11`
- prototype: `void __fastcall(CCountedObject *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180003470`
- `0x180005fe8`
- `0x180007a38`
- `0x180008314`
- `0x180008d54`

## pseudocode

```c
void __fastcall CCountedObject::~CCountedObject(CCountedObject *this)
{
  *(_QWORD *)this = &CCountedObject::`vftable';
}

```

## disassembly

```asm
0x1800033c0  lea     rax, ??_7CCountedObject@@6B@; const CCountedObject::`vftable'
0x1800033c7  mov     [rcx], rax
0x1800033ca  retn
```
