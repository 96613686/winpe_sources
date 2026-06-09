# _CXMLTag::CreateCustomPropertyNameFromTagName_::_1_::dtor$0

- ea: `0x1800234b8`
- end: `0x1800234c4`
- name: `_CXMLTag::CreateCustomPropertyNameFromTagName_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180011d24`

## pseudocode

```c
void __fastcall CXMLTag::CreateCustomPropertyNameFromTagName_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)(a2 + 72));
}

```

## disassembly

```asm
0x1800234b8  lea     rcx, [rdx+48h]
0x1800234bf  jmp     ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
```
