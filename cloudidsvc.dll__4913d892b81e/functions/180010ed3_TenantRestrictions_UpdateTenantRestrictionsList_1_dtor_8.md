# _TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$8

- ea: `0x180010ed3`
- end: `0x180010edf`
- name: `_TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$8`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a73c`

## pseudocode

```c
__int64 __fastcall TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 512);
}

```

## disassembly

```asm
0x180010ed3  lea     rcx, [rdx+200h]
0x180010eda  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
