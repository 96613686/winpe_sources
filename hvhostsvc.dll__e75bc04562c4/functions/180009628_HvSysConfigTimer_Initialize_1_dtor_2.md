# _HvSysConfigTimer::Initialize_::_1_::dtor$2

- ea: `0x180009628`
- end: `0x180009634`
- name: `_HvSysConfigTimer::Initialize_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180008204`

## pseudocode

```c
__int64 __fastcall HvSysConfigTimer::Initialize_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wistd::function<void (enum wil::RegistryChangeKind)>::~function<void (enum wil::RegistryChangeKind)>(a2 + 56);
}

```

## disassembly

```asm
0x180009628  lea     rcx, [rdx+38h]
0x18000962f  jmp     ??1?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEAA@XZ; wistd::function<void (wil::RegistryChangeKind)>::~function<void (wil::RegistryChangeKind)>(void)
```
