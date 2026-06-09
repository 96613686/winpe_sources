# _CXMLTag::InitStatChunk_::_1_::dtor$0

- ea: `0x180023494`
- end: `0x1800234a0`
- name: `_CXMLTag::InitStatChunk_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000aef4`

## pseudocode

```c
__int64 __fastcall CXMLTag::InitStatChunk_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return TLMString<32,32,1024>::~TLMString<32,32,1024>(a2 + 96);
}

```

## disassembly

```asm
0x180023494  lea     rcx, [rdx+60h]
0x18002349b  jmp     ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
```
