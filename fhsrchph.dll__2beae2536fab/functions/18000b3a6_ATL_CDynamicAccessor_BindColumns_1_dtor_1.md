# _ATL::CDynamicAccessor::BindColumns_::_1_::dtor$1

- ea: `0x18000b3a6`
- end: `0x18000b3b2`
- name: `_ATL::CDynamicAccessor::BindColumns_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002fb8`

## pseudocode

```c
__int64 __fastcall ATL::CDynamicAccessor::BindColumns_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IUrlAccessor2>::~CComPtr<IUrlAccessor2>((__int64 *)(a2 + 320));
}

```

## disassembly

```asm
0x18000b3a6  lea     rcx, [rdx+140h]
0x18000b3ad  jmp     ??1?$CComPtr@UIUrlAccessor2@@@ATL@@QEAA@XZ; ATL::CComPtr<IUrlAccessor2>::~CComPtr<IUrlAccessor2>(void)
```
