# ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)

- ea: `0x140001888`
- end: `0x140001892`
- name: `??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComTypeInfoHolder::stringdispid *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001a10`
- `0x1400023fc`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000188b`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::stringdispid::~stringdispid(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x140001888  mov     rcx, [rcx]
0x14000188b  jmp     cs:__imp_SysFreeString
```
