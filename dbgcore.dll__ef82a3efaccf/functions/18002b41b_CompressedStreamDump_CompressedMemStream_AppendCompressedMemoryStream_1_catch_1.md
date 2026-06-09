# _CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream_::_1_::catch$1

- ea: `0x18002b41b`
- end: `0x18002b462`
- name: `_CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001ddd8`
- `0x1800289b8`
- `0x18002c010`

## string_xrefs

- `0x18002b43b`: `AppendCompressedMemoryStream`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rax

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 48) + 8LL))(*(_QWORD *)(a2 + 48));
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)4,
    (int)"%s: standard exception: %s.\n",
    "AppendCompressedMemoryStream",
    v2);
  return &loc_18001DF62;
}

```

## disassembly

```asm
0x18002b41b  mov     [rsp+arg_8], rdx
0x18002b420  push    rbp
0x18002b421  sub     rsp, 20h
0x18002b425  mov     rbp, rdx
0x18002b428  mov     rcx, [rbp+30h]
0x18002b42c  mov     rax, [rcx]
0x18002b42f  mov     rax, [rax+8]
0x18002b433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b438  mov     r9, rax
0x18002b43b  lea     r8, aAppendcompress; "AppendCompressedMemoryStream"
0x18002b442  lea     rdx, aSStandardExcep; "%s: standard exception: %s.\n"
0x18002b449  mov     ecx, 4; this
0x18002b44e  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18002b453  nop
0x18002b454  lea     rax, loc_18001DF62
0x18002b45b  add     rsp, 20h
0x18002b45f  pop     rbp
0x18002b460  retn
```
