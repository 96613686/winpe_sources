# _EapHost::ECPDeviceManager::CheckECPComponentDevice_::_1_::dtor$0

- ea: `0x180015e2d`
- end: `0x180015e39`
- name: `_EapHost::ECPDeviceManager::CheckECPComponentDevice_::_1_::dtor$0`
- size: `12`
- prototype: `HRESULT __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800115ec`

## pseudocode

```c
HRESULT __fastcall EapHost::ECPDeviceManager::CheckECPComponentDevice_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return EapHost::PropVariantWrapper::~PropVariantWrapper((PROPVARIANT *)(a2 + 48));
}

```

## disassembly

```asm
0x180015e2d  lea     rcx, [rdx+30h]; pvar
0x180015e34  jmp     ??1PropVariantWrapper@EapHost@@QEAA@XZ; EapHost::PropVariantWrapper::~PropVariantWrapper(void)
```
