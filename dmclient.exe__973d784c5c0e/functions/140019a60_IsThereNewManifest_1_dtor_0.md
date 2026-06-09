# _IsThereNewManifest_::_1_::dtor$0

- ea: `0x140019a60`
- end: `0x140019a6c`
- name: `_IsThereNewManifest_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000de6c`

## pseudocode

```c
__int64 __fastcall IsThereNewManifest_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 152);
}

```

## disassembly

```asm
0x140019a60  lea     rcx, [rdx+98h]
0x140019a67  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
