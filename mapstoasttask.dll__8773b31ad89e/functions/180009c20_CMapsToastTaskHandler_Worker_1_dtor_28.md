# _CMapsToastTaskHandler::Worker_::_1_::dtor$28

- ea: `0x180009c20`
- end: `0x180009c2c`
- name: `_CMapsToastTaskHandler::Worker_::_1_::dtor$28`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800027e4`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::Worker_::_1_::dtor_28(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 104));
}

```

## disassembly

```asm
0x180009c20  lea     rcx, [rdx+68h]
0x180009c27  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
