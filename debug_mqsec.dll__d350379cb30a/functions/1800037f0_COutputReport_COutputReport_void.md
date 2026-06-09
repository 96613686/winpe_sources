# COutputReport::~COutputReport(void)

- ea: `0x1800037f0`
- end: `0x180003800`
- name: `??1COutputReport@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(COutputReport *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800037f4`
- `KERNEL32!DeleteCriticalSection` at `0x1800037f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall COutputReport::~COutputReport(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800037f0  sub     rsp, 28h
0x1800037f4  call    cs:__imp_DeleteCriticalSection
0x1800037fa  nop
0x1800037fb  add     rsp, 28h
0x1800037ff  retn
```
