# _ProvPackage::RemovePackage_::_1_::dtor$0

- ea: `0x14000ed9e`
- end: `0x14000edaa`
- name: `_ProvPackage::RemovePackage_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003938`

## pseudocode

```c
__int64 __fastcall ProvPackage::RemovePackage_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(*(_QWORD *)(a2 + 64));
}

```

## disassembly

```asm
0x14000ed9e  mov     rcx, [rdx+40h]
0x14000eda5  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
