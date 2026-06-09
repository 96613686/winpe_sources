# _CMapsToastTaskHandler::ParseArguments_::_1_::dtor$1

- ea: `0x1800097c2`
- end: `0x1800097ce`
- name: `_CMapsToastTaskHandler::ParseArguments_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180002b64`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::ParseArguments_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::basic_istringstream<unsigned short>::`vbase destructor'(a2 + 96);
}

```

## disassembly

```asm
0x1800097c2  lea     rcx, [rdx+60h]
0x1800097c9  jmp     ??_D?$basic_istringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_istringstream<ushort>::`vbase destructor'(void)
```
