# _WriteNewElement_::_1_::dtor$1

- ea: `0x1800189bb`
- end: `0x1800189c7`
- name: `_WriteNewElement_::_1_::dtor$1`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800103c0`

## pseudocode

```c
_QWORD *__fastcall WriteNewElement_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IXmlWriter>::~ComPtr<IXmlWriter>((_QWORD *)(a2 + 120));
}

```

## disassembly

```asm
0x1800189bb  lea     rcx, [rdx+78h]
0x1800189c2  jmp     ??1?$ComPtr@UIXmlWriter@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IXmlWriter>::~ComPtr<IXmlWriter>(void)
```
