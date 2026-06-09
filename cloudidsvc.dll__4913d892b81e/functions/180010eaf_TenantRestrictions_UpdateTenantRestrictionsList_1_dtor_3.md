# _TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$3

- ea: `0x180010eaf`
- end: `0x180010ebb`
- name: `_TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a8e0`

## pseudocode

```c
__int64 __fastcall TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::unordered_map<std::wstring,std::wstring>::~unordered_map<std::wstring,std::wstring>(a2 + 112);
}

```

## disassembly

```asm
0x180010eaf  lea     rcx, [rdx+70h]
0x180010eb6  jmp     ??1?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::wstring>::~unordered_map<std::wstring,std::wstring>(void)
```
