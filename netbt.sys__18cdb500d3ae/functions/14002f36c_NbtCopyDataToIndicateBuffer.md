# NbtCopyDataToIndicateBuffer

- ea: `0x14002f36c`
- end: `0x14002f3cd`
- name: `NbtCopyDataToIndicateBuffer`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14001dc00`

## import_xrefs

- `TDI!TdiCopyBufferToMdl` at `0x14002f3b0`
- `TDI!TdiCopyBufferToMdl` at `0x14002f3b0`

## pseudocode

```c
__int64 __fastcall NbtCopyDataToIndicateBuffer(__int64 a1, unsigned int a2, void *a3)
{
  ULONG DestinationOffset; // eax
  ULONG v6; // r8d
  __int64 result; // rax
  ULONG BytesCopied; // [rsp+48h] [rbp+10h] BYREF

  DestinationOffset = *(_DWORD *)(a1 + 280);
  BytesCopied = 0;
  v6 = 132 - DestinationOffset;
  if ( a2 < 132 - DestinationOffset )
    v6 = a2;
  TdiCopyBufferToMdl(a3, 0, v6, *(PMDL *)(a1 + 240), DestinationOffset, &BytesCopied);
  result = BytesCopied;
  *(_DWORD *)(a1 + 280) += BytesCopied;
  return result;
}

```

## disassembly

```asm
0x14002f36c  push    rbx
0x14002f36e  sub     rsp, 30h
0x14002f372  mov     eax, [rcx+118h]
0x14002f378  mov     r10, r8
0x14002f37b  mov     rbx, rcx
0x14002f37e  mov     [rsp+38h+arg_8], 0
0x14002f386  mov     r8d, 84h
0x14002f38c  lea     rcx, [rsp+38h+arg_8]
0x14002f391  sub     r8d, eax
0x14002f394  mov     [rsp+38h+BytesCopied], rcx; BytesCopied
0x14002f399  cmp     edx, r8d
0x14002f39c  mov     [rsp+38h+DestinationOffset], eax; DestinationOffset
0x14002f3a0  mov     r9, [rbx+0F0h]; DestinationMdlChain
0x14002f3a7  mov     rcx, r10; SourceBuffer
0x14002f3aa  cmovb   r8d, edx; SourceBytesToCopy
0x14002f3ae  xor     edx, edx; SourceOffset
0x14002f3b0  call    cs:__imp_TdiCopyBufferToMdl
0x14002f3b7  nop     dword ptr [rax+rax+00h]
0x14002f3bc  mov     eax, [rsp+38h+arg_8]
0x14002f3c0  add     [rbx+118h], eax
0x14002f3c6  add     rsp, 30h
0x14002f3ca  pop     rbx
0x14002f3cb  retn
```
