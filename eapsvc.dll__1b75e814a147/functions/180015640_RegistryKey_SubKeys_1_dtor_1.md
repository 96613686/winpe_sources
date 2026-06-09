# _RegistryKey::SubKeys_::_1_::dtor$1

- ea: `0x180015640`
- end: `0x18001564c`
- name: `_RegistryKey::SubKeys_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000cbec`

## pseudocode

```c
__int64 __fastcall RegistryKey::SubKeys_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return PodVector<wchar_t,-1>::~PodVector<wchar_t,-1>(a2 + 176);
}

```

## disassembly

```asm
0x180015640  lea     rcx, [rdx+0B0h]
0x180015647  jmp     ??1?$PodVector@_W$0?0@@QEAA@XZ; PodVector<wchar_t,-1>::~PodVector<wchar_t,-1>(void)
```
