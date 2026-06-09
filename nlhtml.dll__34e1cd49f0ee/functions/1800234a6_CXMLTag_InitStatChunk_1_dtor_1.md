# _CXMLTag::InitStatChunk_::_1_::dtor$1

- ea: `0x1800234a6`
- end: `0x1800234b2`
- name: `_CXMLTag::InitStatChunk_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000aef4`

## pseudocode

```c
__int64 __fastcall CXMLTag::InitStatChunk_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return TLMString<32,32,1024>::~TLMString<32,32,1024>(a2 + 192);
}

```

## disassembly

```asm
0x1800234a6  lea     rcx, [rdx+0C0h]
0x1800234ad  jmp     ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
```
