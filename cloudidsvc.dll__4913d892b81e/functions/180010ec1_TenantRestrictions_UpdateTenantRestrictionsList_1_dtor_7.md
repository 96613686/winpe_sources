# _TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$7

- ea: `0x180010ec1`
- end: `0x180010ecd`
- name: `_TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$7`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a73c`

## pseudocode

```c
__int64 __fastcall TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 544);
}

```

## disassembly

```asm
0x180010ec1  lea     rcx, [rdx+220h]
0x180010ec8  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
