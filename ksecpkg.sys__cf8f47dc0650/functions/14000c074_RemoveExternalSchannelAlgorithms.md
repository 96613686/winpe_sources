# RemoveExternalSchannelAlgorithms

- ea: `0x14000c074`
- end: `0x14000c09b`
- name: `RemoveExternalSchannelAlgorithms`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140021cfc`

## callees

- `0x14000c074`
- `0x14000c9f0`
- `0x14000cdac`
- `0x14000d16c`
- `0x14000d510`

## pseudocode

```c
__int64 RemoveExternalSchannelAlgorithms()
{
  __int64 result; // rax

  if ( dword_140019530 )
  {
    FreeExternalHashAlgorithms();
    FreeExternalSignatureAlgorithms();
    FreeExternalKeyExchangeAlgorithms();
    return FreeExternalCipherAlgorithms();
  }
  return result;
}

```

## disassembly

```asm
0x14000c074  sub     rsp, 28h
0x14000c078  cmp     cs:dword_140019530, 0
0x14000c07f  jz      short loc_14000C095
0x14000c081  call    FreeExternalHashAlgorithms
0x14000c086  call    FreeExternalSignatureAlgorithms
0x14000c08b  call    FreeExternalKeyExchangeAlgorithms
0x14000c090  call    FreeExternalCipherAlgorithms
0x14000c095  add     rsp, 28h
0x14000c099  retn
```
