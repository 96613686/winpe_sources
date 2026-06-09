# _RegistryKey::QueryValue_::_1_::dtor$0_0

- ea: `0x18001561c`
- end: `0x180015628`
- name: `_RegistryKey::QueryValue_::_1_::dtor$0_0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000cbec`

## pseudocode

```c
__int64 __fastcall RegistryKey::QueryValue_::_1_::dtor_0_0(__int64 a1, __int64 a2)
{
  return PodVector<wchar_t,-1>::~PodVector<wchar_t,-1>(a2 + 64);
}

```

## disassembly

```asm
0x18001561c  lea     rcx, [rdx+40h]
0x180015623  jmp     ??1?$PodVector@_W$0?0@@QEAA@XZ; PodVector<wchar_t,-1>::~PodVector<wchar_t,-1>(void)
```
