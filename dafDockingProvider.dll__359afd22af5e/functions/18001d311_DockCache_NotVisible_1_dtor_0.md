# _DockCache::NotVisible_::_1_::dtor$0

- ea: `0x18001d311`
- end: `0x18001d31d`
- name: `_DockCache::NotVisible_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d450`

## pseudocode

```c
void __fastcall DockCache::NotVisible_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  InCritSec::~InCritSec((LPCRITICAL_SECTION *)(a2 + 120));
}

```

## disassembly

```asm
0x18001d311  lea     rcx, [rdx+78h]; this
0x18001d318  jmp     ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
```
