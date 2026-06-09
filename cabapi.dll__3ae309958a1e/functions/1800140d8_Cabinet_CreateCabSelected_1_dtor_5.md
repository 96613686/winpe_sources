# _Cabinet::CreateCabSelected_::_1_::dtor$5

- ea: `0x1800140d8`
- end: `0x1800140e4`
- name: `_Cabinet::CreateCabSelected_::_1_::dtor$5`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800082b8`

## pseudocode

```c
void __fastcall Cabinet::CreateCabSelected_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  std::string::~string((char **)(a2 + 240));
}

```

## disassembly

```asm
0x1800140d8  lea     rcx, [rdx+0F0h]
0x1800140df  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
```
