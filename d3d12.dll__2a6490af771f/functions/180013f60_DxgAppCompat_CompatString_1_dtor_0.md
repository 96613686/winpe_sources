# _DxgAppCompat::CompatString_::_1_::dtor$0

- ea: `0x180013f60`
- end: `0x180013f6c`
- name: `_DxgAppCompat::CompatString_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007104`

## pseudocode

```c
__int64 __fastcall DxgAppCompat::CompatString_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::string::~string(a2 + 40);
}

```

## disassembly

```asm
0x180013f60  lea     rcx, [rdx+28h]
0x180013f67  jmp     ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
```
