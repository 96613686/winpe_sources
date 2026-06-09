# _WritePackageMetadata_::_1_::dtor$1

- ea: `0x1800189df`
- end: `0x1800189eb`
- name: `_WritePackageMetadata_::_1_::dtor$1`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800103c0`

## pseudocode

```c
_QWORD *__fastcall WritePackageMetadata_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IXmlWriter>::~ComPtr<IXmlWriter>((_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x1800189df  lea     rcx, [rdx+60h]
0x1800189e6  jmp     ??1?$ComPtr@UIXmlWriter@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IXmlWriter>::~ComPtr<IXmlWriter>(void)
```
