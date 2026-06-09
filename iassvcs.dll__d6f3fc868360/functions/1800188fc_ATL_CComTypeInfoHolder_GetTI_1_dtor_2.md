# _ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$2

- ea: `0x1800188fc`
- end: `0x180018908`
- name: `_ATL::CComTypeInfoHolder::GetTI_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d768`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x1800188fc  lea     rcx, [rdx+40h]
0x180018903  jmp     ??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ; ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)
```
