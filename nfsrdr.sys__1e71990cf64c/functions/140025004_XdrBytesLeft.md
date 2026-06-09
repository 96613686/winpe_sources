# XdrBytesLeft

- ea: `0x140025004`
- end: `0x14002503a`
- name: `XdrBytesLeft`
- size: `54`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c818`
- `0x14000ce48`
- `0x14000d3e4`
- `0x140014ff4`
- `0x14002372c`
- `0x140038a68`
- `0x140038aec`
- `0x140038c94`
- `0x140038d28`

## callees

- `0x14001f834`
- `0x14001f860`
- `0x140025004`

## pseudocode

```c
__int64 __fastcall XdrBytesLeft(__int64 a1)
{
  _DWORD *NextBufferDescriptor; // r10
  __int64 v2; // r10
  __int64 v3; // r11
  unsigned int v4; // r9d

  NextBufferDescriptor = *(_DWORD **)(a1 + 72);
  do
  {
    OncRpcBufMgrGetDescriptorValidLengthRemaining(NextBufferDescriptor);
    NextBufferDescriptor = (_DWORD *)OncRpcBufMgrGetNextBufferDescriptor(v3, v2);
  }
  while ( NextBufferDescriptor );
  return v4;
}

```

## disassembly

```asm
0x140025004  sub     rsp, 28h
0x140025008  mov     r10, [rcx+48h]
0x14002500c  lea     r11, [rcx+20h]
0x140025010  xor     r9d, r9d
0x140025013  mov     rcx, r10
0x140025016  call    OncRpcBufMgrGetDescriptorValidLengthRemaining
0x14002501b  mov     rdx, r10
0x14002501e  mov     rcx, r11
0x140025021  add     r9d, eax
0x140025024  call    OncRpcBufMgrGetNextBufferDescriptor
0x140025029  mov     r10, rax
0x14002502c  test    rax, rax
0x14002502f  jnz     short loc_140025013
0x140025031  mov     eax, r9d
0x140025034  add     rsp, 28h
0x140025038  retn
```
