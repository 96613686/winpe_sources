# _RegistryHelper::ExpandName_::_1_::dtor$1

- ea: `0x18001f3f4`
- end: `0x18001f400`
- name: `_RegistryHelper::ExpandName_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180007798`

## pseudocode

```c
__int64 __fastcall RegistryHelper::ExpandName_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>((void *)(a2 + 112));
}

```

## disassembly

```asm
0x18001f3f4  lea     rcx, [rdx+70h]
0x18001f3fb  jmp     ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
```
