# ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)

- ea: `0x1800020cc`
- end: `0x1800020d6`
- name: `??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComTypeInfoHolder::stringdispid *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180015790`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800020cf`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::stringdispid::~stringdispid(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x1800020cc  mov     rcx, [rcx]
0x1800020cf  jmp     cs:__imp_SysFreeString
```
