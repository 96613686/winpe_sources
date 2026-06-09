# _UninstallRemainingUnusedLanguageResources_::_1_::dtor$2

- ea: `0x1400103b7`
- end: `0x1400103c3`
- name: `_UninstallRemainingUnusedLanguageResources_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000513c`

## pseudocode

```c
void __fastcall UninstallRemainingUnusedLanguageResources_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>(a2 + 56);
}

```

## disassembly

```asm
0x1400103b7  lea     rcx, [rdx+38h]
0x1400103be  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
