# _Cabinet::CreateCabSelected_::_1_::dtor$7

- ea: `0x1800140fc`
- end: `0x180014108`
- name: `_Cabinet::CreateCabSelected_::_1_::dtor$7`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800082b8`

## pseudocode

```c
void __fastcall Cabinet::CreateCabSelected_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  std::string::~string((char **)(a2 + 208));
}

```

## disassembly

```asm
0x1800140fc  lea     rcx, [rdx+0D0h]
0x180014103  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
```
