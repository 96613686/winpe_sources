# _UninstallRemainingUnusedLanguageResources_::_1_::dtor$0

- ea: `0x140010393`
- end: `0x14001039f`
- name: `_UninstallRemainingUnusedLanguageResources_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x14000513c`

## pseudocode

```c
void __fastcall UninstallRemainingUnusedLanguageResources_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::vector<std::wstring>::~vector<std::wstring>(a2 + 104);
}

```

## disassembly

```asm
0x140010393  lea     rcx, [rdx+68h]
0x14001039a  jmp     ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
```
