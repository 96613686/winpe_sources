# _RetryScheduler::AddTask_::_1_::dtor$18

- ea: `0x1400137f8`
- end: `0x140013804`
- name: `_RetryScheduler::AddTask_::_1_::dtor$18`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140010374`

## pseudocode

```c
HRESULT __fastcall RetryScheduler::AddTask_::_1_::dtor_18(__int64 a1, VARIANTARG *a2)
{
  return _variant_t::~_variant_t(a2 + 9);
}

```

## disassembly

```asm
0x1400137f8  lea     rcx, [rdx+0D8h]; pvarg
0x1400137ff  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
