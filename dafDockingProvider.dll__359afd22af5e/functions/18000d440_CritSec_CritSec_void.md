# CritSec::~CritSec(void)

- ea: `0x18000d440`
- end: `0x18000d447`
- name: `??1CritSec@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18001cebc`
- `0x18001d0b4`
- `0x18001d0f9`
- `0x18001d1f9`
- `0x18001d9c6`
- `0x18001dcbd`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d440`

## pseudocode

```c
// attributes: thunk
void __stdcall CritSec::~CritSec(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000d440  jmp     cs:__imp_DeleteCriticalSection
```
