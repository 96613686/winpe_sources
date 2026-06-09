# std::_Alloc_temporary2<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::~_Alloc_temporary2<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(void)

- ea: `0x140004fd8`
- end: `0x140004fe1`
- name: `??1?$_Alloc_temporary2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAA@XZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400106e1`

## callees

- `0x140005020`

## pseudocode

```c
__int64 __fastcall std::_Alloc_temporary2<std::allocator<std::wstring>>::~_Alloc_temporary2<std::allocator<std::wstring>>(
        __int64 a1)
{
  return std::wstring::~wstring(a1 + 8);
}

```

## disassembly

```asm
0x140004fd8  add     rcx, 8
0x140004fdc  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
