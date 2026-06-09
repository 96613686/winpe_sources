# _DeliveryOptimizationUser::_BuildToastXml_::_1_::dtor$0

- ea: `0x18000ddd9`
- end: `0x18000dde5`
- name: `_DeliveryOptimizationUser::_BuildToastXml_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180008d88`

## pseudocode

```c
__int64 __fastcall DeliveryOptimizationUser::_BuildToastXml_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 56));
}

```

## disassembly

```asm
0x18000ddd9  lea     rcx, [rdx+38h]
0x18000dde0  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
