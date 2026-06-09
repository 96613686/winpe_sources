# _RetryScheduler::AddTask_::_1_::dtor$17

- ea: `0x1400137e6`
- end: `0x1400137f2`
- name: `_RetryScheduler::AddTask_::_1_::dtor$17`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140010374`

## pseudocode

```c
HRESULT __fastcall RetryScheduler::AddTask_::_1_::dtor_17(__int64 a1, __int64 a2)
{
  return _variant_t::~_variant_t((VARIANTARG *)(a2 + 160));
}

```

## disassembly

```asm
0x1400137e6  lea     rcx, [rdx+0A0h]; pvarg
0x1400137ed  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
