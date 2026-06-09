# _ReadJsonFile_::_1_::dtor$14

- ea: `0x140018e7b`
- end: `0x140018e87`
- name: `_ReadJsonFile_::_1_::dtor$14`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140011f4c`

## pseudocode

```c
void __fastcall ReadJsonFile_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 432));
}

```

## disassembly

```asm
0x140018e7b  lea     rcx, [rdx+1B0h]; this
0x140018e82  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
