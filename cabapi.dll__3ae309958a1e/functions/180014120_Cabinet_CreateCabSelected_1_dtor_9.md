# _Cabinet::CreateCabSelected_::_1_::dtor$9

- ea: `0x180014120`
- end: `0x18001412c`
- name: `_Cabinet::CreateCabSelected_::_1_::dtor$9`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800082b8`

## pseudocode

```c
void __fastcall Cabinet::CreateCabSelected_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  std::string::~string((char **)(a2 + 368));
}

```

## disassembly

```asm
0x180014120  lea     rcx, [rdx+170h]
0x180014127  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
```
