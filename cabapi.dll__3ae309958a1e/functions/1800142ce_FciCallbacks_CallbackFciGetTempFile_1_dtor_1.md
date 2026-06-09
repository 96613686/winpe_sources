# _FciCallbacks::CallbackFciGetTempFile_::_1_::dtor$1

- ea: `0x1800142ce`
- end: `0x1800142da`
- name: `_FciCallbacks::CallbackFciGetTempFile_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800082b8`

## pseudocode

```c
void __fastcall FciCallbacks::CallbackFciGetTempFile_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::string::~string((char **)(a2 + 88));
}

```

## disassembly

```asm
0x1800142ce  lea     rcx, [rdx+58h]
0x1800142d5  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
```
