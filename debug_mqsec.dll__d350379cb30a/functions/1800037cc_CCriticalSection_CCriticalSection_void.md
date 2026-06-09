# CCriticalSection::~CCriticalSection(void)

- ea: `0x1800037cc`
- end: `0x1800037dc`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002fd99`
- `0x18002ffdb`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800037d0`
- `KERNEL32!DeleteCriticalSection` at `0x1800037d0`

## pseudocode

```c
void __fastcall CCriticalSection::~CCriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800037cc  sub     rsp, 28h
0x1800037d0  call    cs:__imp_DeleteCriticalSection
0x1800037d6  nop
0x1800037d7  add     rsp, 28h
0x1800037db  retn
```
