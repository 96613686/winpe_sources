# wistd::__function::__func__lambda_3f78a9971162bd1363a0366959f5b7c1__void___cdecl(enum_wil::RegistryChangeKind)_::operator()

- ea: `0x180008370`
- end: `0x180008379`
- name: `wistd::__function::__func__lambda_3f78a9971162bd1363a0366959f5b7c1__void___cdecl(enum_wil::RegistryChangeKind)_::operator()`
- size: `9`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180008908`

## pseudocode

```c
void __fastcall wistd::__function::__func__lambda_3f78a9971162bd1363a0366959f5b7c1__void___cdecl_enum_wil::RegistryChangeKind__::operator()(
        __int64 a1)
{
  HvSysConfigTimer::UpdateSysConfigTimer(*(HvSysConfigTimer **)(a1 + 8));
}

```

## disassembly

```asm
0x180008370  mov     rcx, [rcx+8]; this
0x180008374  jmp     ?UpdateSysConfigTimer@HvSysConfigTimer@@AEAAXXZ; HvSysConfigTimer::UpdateSysConfigTimer(void)
```
