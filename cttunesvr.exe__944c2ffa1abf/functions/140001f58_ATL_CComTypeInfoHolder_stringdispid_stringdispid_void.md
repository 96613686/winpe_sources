# ATL::CComTypeInfoHolder::stringdispid::~stringdispid(void)

- ea: `0x140001f58`
- end: `0x140001f62`
- name: `??1stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(ATL::CComTypeInfoHolder::stringdispid *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002c40`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140001f5b`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::stringdispid::~stringdispid(BSTR *this)
{
  SysFreeString(*this);
}

```

## disassembly

```asm
0x140001f58  mov     rcx, [rcx]
0x140001f5b  jmp     cs:__imp_SysFreeString
```
