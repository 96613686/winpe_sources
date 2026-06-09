# _RasEapCreateConnectionProperties2_::_1_::dtor$2

- ea: `0x180026276`
- end: `0x180026282`
- name: `_RasEapCreateConnectionProperties2_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012680`

## pseudocode

```c
HRESULT __fastcall RasEapCreateConnectionProperties2_::_1_::dtor_2(__int64 a1, VARIANTARG *a2)
{
  return ATL::CComVariant::~CComVariant(a2 + 3);
}

```

## disassembly

```asm
0x180026276  lea     rcx, [rdx+48h]; pvarg
0x18002627d  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
