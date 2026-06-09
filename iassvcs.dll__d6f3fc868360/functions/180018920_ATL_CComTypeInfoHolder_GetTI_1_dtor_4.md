# _ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$4

- ea: `0x180018920`
- end: `0x18001892c`
- name: `_ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d768`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>((__int64 *)(a2 + 72));
}

```

## disassembly

```asm
0x180018920  lea     rcx, [rdx+48h]
0x180018927  jmp     ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
```
