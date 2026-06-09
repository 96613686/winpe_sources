# _DockCache::UnpairedDock_::_1_::dtor$0

- ea: `0x18001d401`
- end: `0x18001d40d`
- name: `_DockCache::UnpairedDock_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d450`

## pseudocode

```c
void __fastcall DockCache::UnpairedDock_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  InCritSec::~InCritSec((LPCRITICAL_SECTION *)(a2 + 96));
}

```

## disassembly

```asm
0x18001d401  lea     rcx, [rdx+60h]; this
0x18001d408  jmp     ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
```
