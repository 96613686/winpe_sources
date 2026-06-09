# _DelegationConfig::s_GetAvailablePackages_::_1_::dtor$0

- ea: `0x180019581`
- end: `0x18001958d`
- name: `_DelegationConfig::s_GetAvailablePackages_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800150c8`

## pseudocode

```c
__int64 __fastcall DelegationConfig::s_GetAvailablePackages_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::unique_call<void (*)(void),&void CoUninitialize(void),1>::~unique_call<void (*)(void),&void CoUninitialize(void),1>(a2 + 32);
}

```

## disassembly

```asm
0x180019581  lea     rcx, [rdx+20h]
0x180019588  jmp     ??1?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@wil@@QEAA@XZ; wil::unique_call<void (*)(void),&CoUninitialize(void),1>::~unique_call<void (*)(void),&CoUninitialize(void),1>(void)
```
