# CMFCSLock::~CMFCSLock(void)

- ea: `0x18002167c`
- end: `0x18002168c`
- name: `??1CMFCSLock@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(CMFCSLock *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002136c`
- `0x180021620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021680`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180021680`

## pseudocode

```c
void __fastcall CMFCSLock::~CMFCSLock(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18002167c  sub     rsp, 28h
0x180021680  call    cs:__imp_DeleteCriticalSection
0x180021686  nop
0x180021687  add     rsp, 28h
0x18002168b  retn
```
