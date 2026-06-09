# _Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString_::_1_::dtor$2

- ea: `0x18000b033`
- end: `0x18000b03f`
- name: `_Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800085d0`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString_::_1_::dtor_2(
        __int64 a1,
        unsigned __int64 a2)
{
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>((void **)(a2 + 96), a2);
}

```

## disassembly

```asm
0x18000b033  lea     rcx, [rdx+60h]
0x18000b03a  jmp     ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
```
