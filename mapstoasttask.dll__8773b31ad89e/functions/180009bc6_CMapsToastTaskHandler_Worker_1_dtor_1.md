# _CMapsToastTaskHandler::Worker_::_1_::dtor$1

- ea: `0x180009bc6`
- end: `0x180009bd2`
- name: `_CMapsToastTaskHandler::Worker_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800027e4`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::Worker_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 200));
}

```

## disassembly

```asm
0x180009bc6  lea     rcx, [rdx+0C8h]
0x180009bcd  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
