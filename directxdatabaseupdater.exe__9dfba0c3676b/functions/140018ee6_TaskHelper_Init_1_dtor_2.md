# _TaskHelper::Init_::_1_::dtor$2

- ea: `0x140018ee6`
- end: `0x140018ef2`
- name: `_TaskHelper::Init_::_1_::dtor$2`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, VARIANTARG *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400136e0`

## pseudocode

```c
HRESULT __fastcall TaskHelper::Init_::_1_::dtor_2(__int64 a1, VARIANTARG *a2)
{
  return _variant_t::~_variant_t(a2 + 3);
}

```

## disassembly

```asm
0x140018ee6  lea     rcx, [rdx+48h]; pvarg
0x140018eed  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
