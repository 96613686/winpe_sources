# _CXMLTag::CreateCustomPropertyNameFromTagName_::_1_::dtor$1

- ea: `0x1800234ca`
- end: `0x1800234d6`
- name: `_CXMLTag::CreateCustomPropertyNameFromTagName_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180011530`

## pseudocode

```c
__int64 __fastcall CXMLTag::CreateCustomPropertyNameFromTagName_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return TLMString<32,32,256>::~TLMString<32,32,256>(a2 + 96);
}

```

## disassembly

```asm
0x1800234ca  lea     rcx, [rdx+60h]
0x1800234d1  jmp     ??1?$TLMString@$0CA@$0CA@$0BAA@@@UEAA@XZ; TLMString<32,32,256>::~TLMString<32,32,256>(void)
```
