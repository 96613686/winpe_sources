# _ReadJsonFile_::_1_::dtor$5

- ea: `0x140018e33`
- end: `0x140018e3f`
- name: `_ReadJsonFile_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140011fe4`

## pseudocode

```c
__int64 __fastcall ReadJsonFile_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::basic_ifstream<unsigned short>::`vbase destructor'(a2 + 128);
}

```

## disassembly

```asm
0x140018e33  lea     rcx, [rdx+80h]
0x140018e3a  jmp     ??_D?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ifstream<ushort>::`vbase destructor'(void)
```
