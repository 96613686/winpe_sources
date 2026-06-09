# _FciCallbacks::CallbackFciFileOpen_::_1_::dtor$0

- ea: `0x180014274`
- end: `0x180014280`
- name: `_FciCallbacks::CallbackFciFileOpen_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800082b8`

## pseudocode

```c
void __fastcall FciCallbacks::CallbackFciFileOpen_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::string::~string((char **)(a2 + 80));
}

```

## disassembly

```asm
0x180014274  lea     rcx, [rdx+50h]
0x18001427b  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
```
