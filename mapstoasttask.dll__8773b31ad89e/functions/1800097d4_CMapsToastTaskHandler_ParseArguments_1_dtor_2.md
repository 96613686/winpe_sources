# _CMapsToastTaskHandler::ParseArguments_::_1_::dtor$2

- ea: `0x1800097d4`
- end: `0x1800097e0`
- name: `_CMapsToastTaskHandler::ParseArguments_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800027e4`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::ParseArguments_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 376));
}

```

## disassembly

```asm
0x1800097d4  lea     rcx, [rdx+178h]
0x1800097db  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
