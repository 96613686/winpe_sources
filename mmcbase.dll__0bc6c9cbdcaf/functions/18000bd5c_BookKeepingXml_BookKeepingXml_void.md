# BookKeepingXml::~BookKeepingXml(void)

- ea: `0x18000bd5c`
- end: `0x18000bd6b`
- name: `??1BookKeepingXml@@UEAA@XZ`
- size: `15`
- prototype: `void __fastcall(BookKeepingXml *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001bd1b`

## callees

- `0x18000c68c`

## pseudocode

```c
void __fastcall BookKeepingXml::~BookKeepingXml(BookKeepingXml *this)
{
  *(_QWORD *)this = &BookKeepingXml::`vftable';
  BookKeepingXml::Empty(this);
}

```

## disassembly

```asm
0x18000bd5c  lea     rax, ??_7BookKeepingXml@@6B@; const BookKeepingXml::`vftable'
0x18000bd63  mov     [rcx], rax
0x18000bd66  jmp     ?Empty@BookKeepingXml@@QEAAXXZ; BookKeepingXml::Empty(void)
```
