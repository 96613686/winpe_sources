# _CXMLTag::CreateCustomPropertyNameFromTagName_::_1_::dtor$2

- ea: `0x1800234dc`
- end: `0x1800234e8`
- name: `_CXMLTag::CreateCustomPropertyNameFromTagName_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180011530`

## pseudocode

```c
__int64 __fastcall CXMLTag::CreateCustomPropertyNameFromTagName_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return TLMString<32,32,256>::~TLMString<32,32,256>(a2 + 192);
}

```

## disassembly

```asm
0x1800234dc  lea     rcx, [rdx+0C0h]
0x1800234e3  jmp     ??1?$TLMString@$0CA@$0CA@$0BAA@@@UEAA@XZ; TLMString<32,32,256>::~TLMString<32,32,256>(void)
```
