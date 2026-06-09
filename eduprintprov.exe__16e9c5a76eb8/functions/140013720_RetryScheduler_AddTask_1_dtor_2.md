# _RetryScheduler::AddTask_::_1_::dtor$2

- ea: `0x140013720`
- end: `0x14001372c`
- name: `_RetryScheduler::AddTask_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140010374`

## pseudocode

```c
HRESULT __fastcall RetryScheduler::AddTask_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return _variant_t::~_variant_t((VARIANTARG *)(a2 + 104));
}

```

## disassembly

```asm
0x140013720  lea     rcx, [rdx+68h]; pvarg
0x140013727  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
