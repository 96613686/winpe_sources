# _TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry_::_1_::dtor$7

- ea: `0x1800110fb`
- end: `0x180011107`
- name: `_TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a73c`

## pseudocode

```c
__int64 __fastcall TenantRestrictionsHelpers::FlushTenantRestrictionsDataToRegistry_::_1_::dtor_7(
        __int64 a1,
        __int64 a2)
{
  return std::wstring::~wstring(a2 + 256);
}

```

## disassembly

```asm
0x1800110fb  lea     rcx, [rdx+100h]
0x180011102  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
