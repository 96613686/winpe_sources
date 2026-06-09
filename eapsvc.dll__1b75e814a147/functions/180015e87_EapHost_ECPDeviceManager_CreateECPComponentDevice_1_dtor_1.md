# _EapHost::ECPDeviceManager::CreateECPComponentDevice_::_1_::dtor$1

- ea: `0x180015e87`
- end: `0x180015e93`
- name: `_EapHost::ECPDeviceManager::CreateECPComponentDevice_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cc0c`

## pseudocode

```c
__int64 __fastcall EapHost::ECPDeviceManager::CreateECPComponentDevice_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return PodVector<wchar_t *,0>::~PodVector<wchar_t *,0>(a2 + 80);
}

```

## disassembly

```asm
0x180015e87  lea     rcx, [rdx+50h]
0x180015e8e  jmp     ??1?$PodVector@PEA_W$0A@@@QEAA@XZ; PodVector<wchar_t *,0>::~PodVector<wchar_t *,0>(void)
```
