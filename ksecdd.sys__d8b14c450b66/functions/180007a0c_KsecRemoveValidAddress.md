# KsecRemoveValidAddress

- ea: `0x180007a0c`
- end: `0x180007a20`
- name: `KsecRemoveValidAddress`
- size: `20`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001f610`
- `0x18001f9e4`
- `0x180020b14`
- `0x180022e18`
- `0x180027a18`

## callees

- `0x180005718`

## pseudocode

```c
_BOOL8 __fastcall KsecRemoveValidAddress(unsigned __int8 *a1)
{
  return KsecRemoveValidAddressCommon(a1, 8u);
}

```

## disassembly

```asm
0x180007a0c  sub     rsp, 28h
0x180007a10  mov     edx, 8
0x180007a15  call    KsecRemoveValidAddressCommon
0x180007a1a  add     rsp, 28h
0x180007a1e  retn
```
