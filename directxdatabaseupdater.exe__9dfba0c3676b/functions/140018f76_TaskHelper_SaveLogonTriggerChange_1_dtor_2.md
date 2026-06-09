# _TaskHelper::SaveLogonTriggerChange_::_1_::dtor$2

- ea: `0x140018f76`
- end: `0x140018f82`
- name: `_TaskHelper::SaveLogonTriggerChange_::_1_::dtor$2`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400136e0`

## pseudocode

```c
HRESULT __fastcall TaskHelper::SaveLogonTriggerChange_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return _variant_t::~_variant_t((VARIANTARG *)(a2 + 128));
}

```

## disassembly

```asm
0x140018f76  lea     rcx, [rdx+80h]; pvarg
0x140018f7d  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
