# _MSXML2::IXMLDOMNode::Getxml_::_1_::dtor$1

- ea: `0x18000e764`
- end: `0x18000e770`
- name: `_MSXML2::IXMLDOMNode::Getxml_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callees

- `0x180002360`

## pseudocode

```c
void __fastcall MSXML2::IXMLDOMNode::Getxml_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 80));
}

```

## disassembly

```asm
0x18000e764  mov     rcx, [rdx+50h]; Block
0x18000e76b  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
