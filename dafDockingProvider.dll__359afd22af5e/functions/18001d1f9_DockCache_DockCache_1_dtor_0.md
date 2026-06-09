# _DockCache::DockCache_::_1_::dtor$0

- ea: `0x18001d1f9`
- end: `0x18001d205`
- name: `_DockCache::DockCache_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d440`

## pseudocode

```c
void __fastcall DockCache::DockCache_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CritSec::~CritSec(*(LPCRITICAL_SECTION *)(a2 + 80));
}

```

## disassembly

```asm
0x18001d1f9  mov     rcx, [rdx+50h]; lpCriticalSection
0x18001d200  jmp     ??1CritSec@@QEAA@XZ; CritSec::~CritSec(void)
```
