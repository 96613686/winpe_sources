# _CNDFHelperClassRegistry::InitializeData_::_1_::dtor$2

- ea: `0x180013d9b`
- end: `0x180013da7`
- name: `_CNDFHelperClassRegistry::InitializeData_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800056f4`

## pseudocode

```c
__int64 __fastcall CNDFHelperClassRegistry::InitializeData_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::map<std::wstring,std::wstring>::~map<std::wstring,std::wstring>(a2 + 80);
}

```

## disassembly

```asm
0x180013d9b  lea     rcx, [rdx+50h]
0x180013da2  jmp     ??1?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::~map<std::wstring,std::wstring>(void)
```
