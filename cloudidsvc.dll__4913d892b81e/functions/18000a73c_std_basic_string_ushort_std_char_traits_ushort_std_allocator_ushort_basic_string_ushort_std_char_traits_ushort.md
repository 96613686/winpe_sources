# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x18000a73c`
- end: `0x18000a741`
- name: `??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `29`
- callee_count: `1`
- tags: ``

## callers

- `0x180010c82`
- `0x180010cd2`
- `0x180010d13`
- `0x180010d54`
- `0x180010e0d`
- `0x180010e1f`
- `0x180010e31`
- `0x180010e43`
- `0x180010e55`
- `0x180010e67`
- `0x180010ec1`
- `0x180010ed3`
- `0x180011063`
- `0x1800110b3`
- `0x1800110c5`
- `0x1800110d7`
- `0x1800110fb`
- `0x18001110d`
- `0x1800111f5`
- `0x180011221`
- `0x180011257`
- `0x180011283`
- `0x180011295`
- `0x1800112a7`
- `0x180011349`
- `0x180011362`
- `0x18001147e`
- `0x1800114b4`
- `0x1800114c6`

## callees

- `0x18000c498`

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
0x18000a73c  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
