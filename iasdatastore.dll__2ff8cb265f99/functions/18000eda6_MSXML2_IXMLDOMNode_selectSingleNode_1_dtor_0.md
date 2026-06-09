# _MSXML2::IXMLDOMNode::selectSingleNode_::_1_::dtor$0

- ea: `0x18000eda6`
- end: `0x18000edb2`
- name: `_MSXML2::IXMLDOMNode::selectSingleNode_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800076dc`

## pseudocode

```c
void __fastcall MSXML2::IXMLDOMNode::selectSingleNode_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  _bstr_t::~_bstr_t(*(_bstr_t **)(a2 + 80));
}

```

## disassembly

```asm
0x18000eda6  mov     rcx, [rdx+50h]; this
0x18000edad  jmp     ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
```
