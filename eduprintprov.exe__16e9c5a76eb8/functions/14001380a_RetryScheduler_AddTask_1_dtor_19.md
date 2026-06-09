# _RetryScheduler::AddTask_::_1_::dtor$19

- ea: `0x14001380a`
- end: `0x140013816`
- name: `_RetryScheduler::AddTask_::_1_::dtor$19`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140010374`

## pseudocode

```c
HRESULT __fastcall RetryScheduler::AddTask_::_1_::dtor_19(__int64 a1, VARIANTARG *a2)
{
  return _variant_t::~_variant_t(a2 + 8);
}

```

## disassembly

```asm
0x14001380a  lea     rcx, [rdx+0C0h]; pvarg
0x140013811  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
