# _TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry_::_1_::dtor$2

- ea: `0x1800110b3`
- end: `0x1800110bf`
- name: `_TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a73c`

## pseudocode

```c
__int64 __fastcall TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring(a2 + 224);
}

```

## disassembly

```asm
0x1800110b3  lea     rcx, [rdx+0E0h]
0x1800110ba  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
