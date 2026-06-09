# Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(void)

- ea: `0x180015930`
- end: `0x180015935`
- name: `??1?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019c9a`
- `0x180019cac`
- `0x180019cbe`
- `0x180019ce2`
- `0x180019cf4`
- `0x180019d06`

## callees

- `0x180005590`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180015930  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
