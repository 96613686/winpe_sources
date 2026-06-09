# CCriticalSection::~CCriticalSection(void)

- ea: `0x180013210`
- end: `0x180013220`
- name: `??1CCriticalSection@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(CCriticalSection *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180024905`
- `0x180024973`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180013214`
- `KERNEL32!DeleteCriticalSection` at `0x180013214`

## pseudocode

```c
void __fastcall CCriticalSection::~CCriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180013210  sub     rsp, 28h
0x180013214  call    cs:__imp_DeleteCriticalSection
0x18001321a  nop
0x18001321b  add     rsp, 28h
0x18001321f  retn
```
