# _CMapsToastTaskHandler::Worker_::_1_::dtor$5

- ea: `0x180009c0e`
- end: `0x180009c1a`
- name: `_CMapsToastTaskHandler::Worker_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800027e4`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::Worker_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 168));
}

```

## disassembly

```asm
0x180009c0e  lea     rcx, [rdx+0A8h]
0x180009c15  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
