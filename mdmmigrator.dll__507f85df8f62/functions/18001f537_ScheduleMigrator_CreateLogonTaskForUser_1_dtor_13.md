# _ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$13

- ea: `0x18001f537`
- end: `0x18001f543`
- name: `_ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$13`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000abf8`

## pseudocode

```c
HRESULT __fastcall ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  return _variant_t::~_variant_t((VARIANTARG *)(a2 + 224));
}

```

## disassembly

```asm
0x18001f537  lea     rcx, [rdx+0E0h]; pvarg
0x18001f53e  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
