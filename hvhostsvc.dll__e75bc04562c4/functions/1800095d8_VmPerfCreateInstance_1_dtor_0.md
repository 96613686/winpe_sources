# _VmPerfCreateInstance_::_1_::dtor$0

- ea: `0x1800095d8`
- end: `0x1800095e4`
- name: `_VmPerfCreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006ff4`

## pseudocode

```c
__int64 __fastcall VmPerfCreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 96);
}

```

## disassembly

```asm
0x1800095d8  lea     rcx, [rdx+60h]
0x1800095df  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
