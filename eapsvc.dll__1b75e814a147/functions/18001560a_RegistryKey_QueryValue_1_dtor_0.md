# _RegistryKey::QueryValue_::_1_::dtor$0

- ea: `0x18001560a`
- end: `0x180015616`
- name: `_RegistryKey::QueryValue_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000cc0c`

## pseudocode

```c
__int64 __fastcall RegistryKey::QueryValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return PodVector<wchar_t *,0>::~PodVector<wchar_t *,0>(a2 + 48);
}

```

## disassembly

```asm
0x18001560a  lea     rcx, [rdx+30h]
0x180015611  jmp     ??1?$PodVector@PEA_W$0A@@@QEAA@XZ; PodVector<wchar_t *,0>::~PodVector<wchar_t *,0>(void)
```
