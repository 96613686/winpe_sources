# InCritSec::~InCritSec(void)

- ea: `0x18000d450`
- end: `0x18000d45a`
- name: `??1InCritSec@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(LPCRITICAL_SECTION *this)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ced2`
- `0x18001cff5`
- `0x18001d007`
- `0x18001d145`
- `0x18001d2ff`
- `0x18001d311`
- `0x18001d323`
- `0x18001d401`
- `0x18001d4f1`
- `0x18001d5cf`
- `0x18001d7e1`
- `0x18001e1b1`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d453`

## pseudocode

```c
void __fastcall InCritSec::~InCritSec(LPCRITICAL_SECTION *this)
{
  LeaveCriticalSection(*this);
}

```

## disassembly

```asm
0x18000d450  mov     rcx, [rcx]
0x18000d453  jmp     cs:__imp_LeaveCriticalSection
```
