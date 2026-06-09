# CCriticalSection::~CCriticalSection(void)

- ea: `0x14000ac84`
- end: `0x14000ac94`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14001dc53`
- `0x14001dccd`
- `0x14001ed66`
- `0x14001ee06`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000ac88`
- `KERNEL32!DeleteCriticalSection` at `0x14000ac88`

## pseudocode

```c
void __fastcall CCriticalSection::~CCriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x14000ac84  sub     rsp, 28h
0x14000ac88  call    cs:__imp_DeleteCriticalSection
0x14000ac8e  nop
0x14000ac8f  add     rsp, 28h
0x14000ac93  retn
```
