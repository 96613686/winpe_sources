# _CMapsToastTaskHandler::ParseArguments_::_1_::dtor$0

- ea: `0x1800097b0`
- end: `0x1800097bc`
- name: `_CMapsToastTaskHandler::ParseArguments_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800027e4`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::ParseArguments_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 344));
}

```

## disassembly

```asm
0x1800097b0  lea     rcx, [rdx+158h]
0x1800097b7  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
