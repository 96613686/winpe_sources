# _CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream_::_1_::catch$2

- ea: `0x18002b462`
- end: `0x18002b496`
- name: `_CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream_::_1_::catch$2`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001ddd8`
- `0x1800289b8`

## string_xrefs

- `0x18002b46f`: `AppendCompressedMemoryStream`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream_::_1_::catch_2()
{
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)4,
    (int)"%s: unknown exception occured.\n",
    "AppendCompressedMemoryStream");
  return &loc_18001DF5A;
}

```

## disassembly

```asm
0x18002b462  mov     [rsp+arg_8], rdx
0x18002b467  push    rbp
0x18002b468  sub     rsp, 20h
0x18002b46c  mov     rbp, rdx
0x18002b46f  lea     r8, aAppendcompress; "AppendCompressedMemoryStream"
0x18002b476  lea     rdx, aSUnknownExcept; "%s: unknown exception occured.\n"
0x18002b47d  mov     ecx, 4; this
0x18002b482  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18002b487  nop
0x18002b488  lea     rax, loc_18001DF5A
0x18002b48f  add     rsp, 20h
0x18002b493  pop     rbp
0x18002b494  retn
```
