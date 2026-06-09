# _CLRConfig::TrimWhiteSpace_::_1_::dtor$0

- ea: `0x1400155dd`
- end: `0x1400155e9`
- name: `_CLRConfig::TrimWhiteSpace_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000a994`

## pseudocode

```c
__int64 __fastcall CLRConfig::TrimWhiteSpace_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return NewArrayHolder<unsigned short>::~NewArrayHolder<unsigned short>(a2 + 32);
}

```

## disassembly

```asm
0x1400155dd  lea     rcx, [rdx+20h]
0x1400155e4  jmp     ??1?$NewArrayHolder@G@@QEAA@XZ; NewArrayHolder<ushort>::~NewArrayHolder<ushort>(void)
```
