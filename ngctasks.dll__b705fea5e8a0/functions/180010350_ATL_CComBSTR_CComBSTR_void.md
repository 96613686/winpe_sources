# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180010350`
- end: `0x180010363`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `19`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `10`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800203d8`
- `0x1800203ea`
- `0x180020420`
- `0x1800204e6`
- `0x1800204f8`
- `0x1800206d8`
- `0x180020798`
- `0x180020898`
- `0x1800208bc`
- `0x1800208ce`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180010357`
- `OLEAUT32!__imp_SysFreeString` at `0x180010357`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180010350  sub     rsp, 28h
0x180010354  mov     rcx, [rcx]; bstrString
0x180010357  call    cs:__imp_SysFreeString
0x18001035d  nop
0x18001035e  add     rsp, 28h
0x180010362  retn
```
