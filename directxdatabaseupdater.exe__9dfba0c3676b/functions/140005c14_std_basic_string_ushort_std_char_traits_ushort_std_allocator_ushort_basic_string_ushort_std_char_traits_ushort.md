# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140005c14`
- end: `0x140005c19`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140018648`
- `0x140018670`
- `0x140018682`
- `0x1400189e2`
- `0x1400189f4`
- `0x140018a60`
- `0x140018b33`
- `0x140018b62`
- `0x140018b91`
- `0x140018c45`
- `0x140018c57`
- `0x140018e45`
- `0x140019148`

## callees

- `0x14000df28`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::wstring::~wstring(__int64 a1)
{
  return std::wstring::_Tidy_deallocate(a1);
}

```

## disassembly

```asm
0x140005c14  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
