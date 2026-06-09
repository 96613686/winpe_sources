# IopLiveDumpTraceChunkCRCMismatchWrite

- ea: `0x1405e1ae4`
- end: `0x1405e1b77`
- name: `IopLiveDumpTraceChunkCRCMismatchWrite`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14044f30c`

## callees

- `0x1405e1ca8`

## string_xrefs

- `0x1405e1b1a`: `WriteComplete`
- `0x1405e1b2d`: `WriteBufferCRC`
- `0x1405e1b38`: `WriteLength`
- `0x1405e1aff`: `ChunkCRCMismatchWrite`

## pseudocode

```c
__int64 __fastcall IopLiveDumpTraceChunkCRCMismatchWrite(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  _QWORD v7[6]; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v8[6]; // [rsp+50h] [rbp-30h] BYREF

  v7[0] = a1;
  v8[0] = L"ChunkIndex";
  v7[1] = a2;
  v8[1] = L"ChunkCRC";
  v7[3] = a4;
  v8[2] = L"WriteComplete";
  v8[3] = L"WriteBufferCRC";
  v8[4] = L"WriteLength";
  v8[5] = L"ByteOffset";
  v7[2] = a3;
  v7[4] = a5;
  v7[5] = a6;
  return IopLiveDumpTraceEventGeneric((__int64)L"ChunkCRCMismatchWrite", 6, (__int64)v8, (__int64)v7);
}

```

## disassembly

```asm
0x1405e1ae4  push    rbp
0x1405e1ae6  mov     rbp, rsp
0x1405e1ae9  sub     rsp, 80h
0x1405e1af0  lea     rax, aChunkindex; "ChunkIndex"
0x1405e1af7  mov     [rbp+var_60], rcx
0x1405e1afb  mov     [rbp+var_30], rax
0x1405e1aff  lea     rcx, aChunkcrcmismat; "ChunkCRCMismatchWrite"
0x1405e1b06  lea     rax, aChunkcrc; "ChunkCRC"
0x1405e1b0d  mov     [rbp+var_58], rdx
0x1405e1b11  mov     [rbp+var_28], rax
0x1405e1b15  mov     edx, 6
0x1405e1b1a  lea     rax, aWritecomplete; "WriteComplete"
0x1405e1b21  mov     [rbp+var_48], r9
0x1405e1b25  mov     [rbp+var_20], rax
0x1405e1b29  lea     r9, [rbp+var_60]
0x1405e1b2d  lea     rax, aWritebuffercrc; "WriteBufferCRC"
0x1405e1b34  mov     [rbp+var_18], rax
0x1405e1b38  lea     rax, aWritelength; "WriteLength"
0x1405e1b3f  mov     [rbp+var_10], rax
0x1405e1b43  lea     rax, aByteoffset; "ByteOffset"
0x1405e1b4a  mov     [rbp+var_8], rax
0x1405e1b4e  movsxd  rax, r8d
0x1405e1b51  lea     r8, [rbp+var_30]
0x1405e1b55  mov     [rbp+var_50], rax
0x1405e1b59  mov     eax, [rbp+arg_20]
0x1405e1b5c  mov     [rbp+var_40], rax
0x1405e1b60  mov     rax, [rbp+arg_28]
0x1405e1b64  mov     [rbp+var_38], rax
0x1405e1b68  call    IopLiveDumpTraceEventGeneric
0x1405e1b6d  add     rsp, 80h
0x1405e1b74  pop     rbp
0x1405e1b75  retn
```
