# _RasEapCreateUserProperties2_::_1_::dtor$2

- ea: `0x1800262ac`
- end: `0x1800262b8`
- name: `_RasEapCreateUserProperties2_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012680`

## pseudocode

```c
HRESULT __fastcall RasEapCreateUserProperties2_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComVariant::~CComVariant((VARIANTARG *)(a2 + 104));
}

```

## disassembly

```asm
0x1800262ac  lea     rcx, [rdx+68h]; pvarg
0x1800262b3  jmp     ??1CComVariant@ATL@@QEAA@XZ; ATL::CComVariant::~CComVariant(void)
```
