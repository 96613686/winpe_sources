# _GetCanonicalUNCPath_::_1_::dtor$4

- ea: `0x1800140ea`
- end: `0x1800140f6`
- name: `_GetCanonicalUNCPath_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003648`

## pseudocode

```c
__int64 __fastcall GetCanonicalUNCPath_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 176));
}

```

## disassembly

```asm
0x1800140ea  lea     rcx, [rdx+0B0h]
0x1800140f1  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
