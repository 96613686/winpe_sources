# _C3DPrintShellExtension::Execute_::_1_::dtor$3

- ea: `0x18000a529`
- end: `0x18000a535`
- name: `_C3DPrintShellExtension::Execute_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005404`

## pseudocode

```c
__int64 __fastcall C3DPrintShellExtension::Execute_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 88);
}

```

## disassembly

```asm
0x18000a529  lea     rcx, [rdx+58h]
0x18000a530  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
