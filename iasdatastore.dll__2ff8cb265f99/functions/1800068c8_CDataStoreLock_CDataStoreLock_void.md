# CDataStoreLock::~CDataStoreLock(void)

- ea: `0x1800068c8`
- end: `0x1800068d6`
- name: `??1CDataStoreLock@@QEAA@XZ`
- size: `14`
- prototype: `void __fastcall(CDataStoreLock *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e2d2`
- `0x18000e3dc`
- `0x18000e5e2`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800068cf`

## pseudocode

```c
void __fastcall CDataStoreLock::~CDataStoreLock(CDataStoreLock *this)
{
  LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)this + 8LL));
}

```

## disassembly

```asm
0x1800068c8  mov     rcx, [rcx]
0x1800068cb  add     rcx, 8
0x1800068cf  jmp     cs:__imp_LeaveCriticalSection
```
