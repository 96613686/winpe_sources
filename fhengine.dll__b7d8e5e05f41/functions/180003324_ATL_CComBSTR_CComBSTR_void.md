# ATL::CComBSTR::~CComBSTR(void)

- ea: `0x180003324`
- end: `0x18000332e`
- name: `??1CComBSTR@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(BSTR *this)`
- caller_count: `14`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180031ea1`
- `0x180031f1f`
- `0x180031f55`
- `0x180031f67`
- `0x18003220d`
- `0x18003272b`
- `0x18003273d`
- `0x18003274f`
- `0x180032761`
- `0x180032785`
- `0x180032809`
- `0x180032a9e`
- `0x180032f51`
- `0x180032f63`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180003327`

## pseudocode

```c
void __fastcall ATL::CComBSTR::~CComBSTR(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x180003324  mov     rcx, [rcx]
0x180003327  jmp     cs:__imp_SysFreeString
```
