# CCriticalSection::~CCriticalSection(void)

- ea: `0x180014bec`
- end: `0x180014bfc`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180020428`
- `0x180020dcd`
- `0x180020e7f`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180014bf0`
- `KERNEL32!DeleteCriticalSection` at `0x180014bf0`

## pseudocode

```c
void __fastcall CCriticalSection::~CCriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180014bec  sub     rsp, 28h
0x180014bf0  call    cs:__imp_DeleteCriticalSection
0x180014bf6  nop
0x180014bf7  add     rsp, 28h
0x180014bfb  retn
```
