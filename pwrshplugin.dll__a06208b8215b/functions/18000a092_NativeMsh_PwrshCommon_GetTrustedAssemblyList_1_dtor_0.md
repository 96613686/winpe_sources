# _NativeMsh::PwrshCommon::GetTrustedAssemblyList_::_1_::dtor$0

- ea: `0x18000a092`
- end: `0x18000a09e`
- name: `_NativeMsh::PwrshCommon::GetTrustedAssemblyList_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800051c8`

## pseudocode

```c
__int64 __fastcall NativeMsh::PwrshCommon::GetTrustedAssemblyList_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 48);
}

```

## disassembly

```asm
0x18000a092  lea     rcx, [rdx+30h]
0x18000a099  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
