# _ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$12

- ea: `0x18001f525`
- end: `0x18001f531`
- name: `_ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$12`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000abf8`

## pseudocode

```c
HRESULT __fastcall ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  return _variant_t::~_variant_t((VARIANTARG *)(a2 + 248));
}

```

## disassembly

```asm
0x18001f525  lea     rcx, [rdx+0F8h]; pvarg
0x18001f52c  jmp     ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
```
