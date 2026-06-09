# CCriticalSection::~CCriticalSection(void)

- ea: `0x180003868`
- end: `0x180003878`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180027d04`
- `0x180027f68`
- `0x180027f7e`
- `0x18002802b`
- `0x1800280a3`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000386c`
- `KERNEL32!DeleteCriticalSection` at `0x18000386c`

## pseudocode

```c
void __fastcall CCriticalSection::~CCriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180003868  sub     rsp, 28h
0x18000386c  call    cs:__imp_DeleteCriticalSection
0x180003872  nop
0x180003873  add     rsp, 28h
0x180003877  retn
```
