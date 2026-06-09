# _utils::CHelpPane::Open_::_1_::dtor$1

- ea: `0x180010a44`
- end: `0x180010a50`
- name: `_utils::CHelpPane::Open_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800098a0`

## pseudocode

```c
__int64 __fastcall utils::CHelpPane::Open_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IHxHelpPane>::~CComPtr<IHxHelpPane>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x180010a44  lea     rcx, [rdx+60h]
0x180010a4b  jmp     ??1?$CComPtr@UIHxHelpPane@@@ATL@@QEAA@XZ; ATL::CComPtr<IHxHelpPane>::~CComPtr<IHxHelpPane>(void)
```
