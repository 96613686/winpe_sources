# Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageResourceResolverStatics>::~ComPtr<Windows::Internal::StateRepository::IPackageResourceResolverStatics>(void)

- ea: `0x14000e878`
- end: `0x14000e87d`
- name: `??1?$ComPtr@UIPackageResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001e1c0`
- `0x14001e1e0`
- `0x14001e200`
- `0x14001e2c8`
- `0x14001e2da`
- `0x14001e389`
- `0x14001e39b`

## callees

- `0x14000e884`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageResourceResolverStatics>::~ComPtr<Windows::Internal::StateRepository::IPackageResourceResolverStatics>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(a1);
}

```

## disassembly

```asm
0x14000e878  jmp     ?InternalRelease@?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(void)
```
