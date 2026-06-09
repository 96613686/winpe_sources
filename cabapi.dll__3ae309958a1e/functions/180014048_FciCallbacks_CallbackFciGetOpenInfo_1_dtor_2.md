# _FciCallbacks::CallbackFciGetOpenInfo_::_1_::dtor$2

- ea: `0x180014048`
- end: `0x180014054`
- name: `_FciCallbacks::CallbackFciGetOpenInfo_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003648`

## pseudocode

```c
__int64 __fastcall FciCallbacks::CallbackFciGetOpenInfo_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring((char **)(a2 + 96));
}

```

## disassembly

```asm
0x180014048  lea     rcx, [rdx+60h]
0x18001404f  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
