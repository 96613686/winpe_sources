# _NativeMsh::PwrshCommon::TryLoadCoreCLR_::_1_::dtor$0

- ea: `0x18000a0b6`
- end: `0x18000a0c2`
- name: `_NativeMsh::PwrshCommon::TryLoadCoreCLR_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800051c8`

## pseudocode

```c
__int64 __fastcall NativeMsh::PwrshCommon::TryLoadCoreCLR_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 56);
}

```

## disassembly

```asm
0x18000a0b6  lea     rcx, [rdx+38h]
0x18000a0bd  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
