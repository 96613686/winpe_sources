# _TaskHelper::Init_::_1_::dtor$3

- ea: `0x140018ef8`
- end: `0x140018f04`
- name: `_TaskHelper::Init_::_1_::dtor$3`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, VARIANTARG *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400136e0`

## pseudocode

```c
HRESULT __fastcall TaskHelper::Init_::_1_::dtor_3(__int64 a1, VARIANTARG *a2)
{
  return _variant_t::~_variant_t(a2 + 2);
}

```

## disassembly

```asm
0x140018ef8  lea     rcx, [rdx+30h]; pvarg
0x140018eff  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
