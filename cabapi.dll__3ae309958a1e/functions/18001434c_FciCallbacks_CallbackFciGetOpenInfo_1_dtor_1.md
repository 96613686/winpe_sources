# _FciCallbacks::CallbackFciGetOpenInfo_::_1_::dtor$1

- ea: `0x18001434c`
- end: `0x180014358`
- name: `_FciCallbacks::CallbackFciGetOpenInfo_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800082b8`

## pseudocode

```c
void __fastcall FciCallbacks::CallbackFciGetOpenInfo_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::string::~string((char **)(a2 + 136));
}

```

## disassembly

```asm
0x18001434c  lea     rcx, [rdx+88h]
0x180014353  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
```
