# CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_ExtractKey(void const *)

- ea: `0x180007590`
- end: `0x180007595`
- name: `?_ExtractKey@?$CTypedHashTable@VOUTPUT_CACHE@@VOUTPUT_ENTRY@@PEAVOUTPUT_KEY@@VCLKRHashTable@@@@CA?B_KPEBX@Z`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CTypedHashTable<OUTPUT_CACHE,OUTPUT_ENTRY,OUTPUT_KEY *,CLKRHashTable>::_ExtractKey(__int64 a1)
{
  return a1 + 8;
}

```

## disassembly

```asm
0x180007590  lea     rax, [rcx+8]
0x180007594  retn
```
