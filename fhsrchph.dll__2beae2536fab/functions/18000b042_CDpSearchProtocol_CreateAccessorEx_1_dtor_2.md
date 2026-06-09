# _CDpSearchProtocol::CreateAccessorEx_::_1_::dtor$2

- ea: `0x18000b042`
- end: `0x18000b04e`
- name: `_CDpSearchProtocol::CreateAccessorEx_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002fb8`

## pseudocode

```c
__int64 __fastcall CDpSearchProtocol::CreateAccessorEx_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IUrlAccessor2>::~CComPtr<IUrlAccessor2>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x18000b042  lea     rcx, [rdx+30h]
0x18000b049  jmp     ??1?$CComPtr@UIUrlAccessor2@@@ATL@@QEAA@XZ; ATL::CComPtr<IUrlAccessor2>::~CComPtr<IUrlAccessor2>(void)
```
