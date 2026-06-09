# _CNDFHelperClassRegistry::InitializeData_::_1_::dtor$1

- ea: `0x180013d89`
- end: `0x180013d95`
- name: `_CNDFHelperClassRegistry::InitializeData_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800056b8`

## pseudocode

```c
__int64 __fastcall CNDFHelperClassRegistry::InitializeData_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::map<std::wstring,CNDFHelperClass *>::~map<std::wstring,CNDFHelperClass *>(a2 + 48);
}

```

## disassembly

```asm
0x180013d89  lea     rcx, [rdx+30h]
0x180013d90  jmp     ??1?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCNDFHelperClass@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,CNDFHelperClass *>::~map<std::wstring,CNDFHelperClass *>(void)
```
