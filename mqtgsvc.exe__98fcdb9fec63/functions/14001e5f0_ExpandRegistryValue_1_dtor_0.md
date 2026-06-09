# _ExpandRegistryValue_::_1_::dtor$0

- ea: `0x14001e5f0`
- end: `0x14001e5fc`
- name: `_ExpandRegistryValue_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ee64`

## pseudocode

```c
__int64 __fastcall ExpandRegistryValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return SP<wchar_t>::~SP<wchar_t>(a2 + 56);
}

```

## disassembly

```asm
0x14001e5f0  lea     rcx, [rdx+38h]
0x14001e5f7  jmp     ??1?$SP@_W@@QEAA@XZ; SP<wchar_t>::~SP<wchar_t>(void)
```
