# _TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$20

- ea: `0x180010f09`
- end: `0x180010f15`
- name: `_TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor$20`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a9e0`

## pseudocode

```c
__int64 __fastcall TenantRestrictions::UpdateTenantRestrictionsList_::_1_::dtor_20(__int64 a1, __int64 a2)
{
  return std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x180010f09  lea     rcx, [rdx+30h]
0x180010f10  jmp     ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(void)
```
