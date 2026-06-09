# _CClassFactory::CreateProvidersIfNeeded_::_1_::dtor$2

- ea: `0x18001d10f`
- end: `0x18001d11b`
- name: `_CClassFactory::CreateProvidersIfNeeded_::_1_::dtor$2`
- size: `12`
- prototype: `unsigned int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800086f0`

## pseudocode

```c
unsigned int __fastcall CClassFactory::CreateProvidersIfNeeded_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ComPtr<DockingProviders>::~ComPtr<DockingProviders>((DockingProviders **)(a2 + 72));
}

```

## disassembly

```asm
0x18001d10f  lea     rcx, [rdx+48h]
0x18001d116  jmp     ??1?$ComPtr@VDockingProviders@@@@QEAA@XZ; ComPtr<DockingProviders>::~ComPtr<DockingProviders>(void)
```
