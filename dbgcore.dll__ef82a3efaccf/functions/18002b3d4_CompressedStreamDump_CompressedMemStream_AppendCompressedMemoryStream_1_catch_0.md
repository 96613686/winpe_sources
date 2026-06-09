# _CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream_::_1_::catch$0

- ea: `0x18002b3d4`
- end: `0x18002b41b`
- name: `_CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream_::_1_::catch$0`
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

- `0x18002b3f4`: `AppendCompressedMemoryStream`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall CompressedStreamDump::CompressedMemStream::AppendCompressedMemoryStream_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rax

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 40) + 8LL))(*(_QWORD *)(a2 + 40));
  CompressedStreamDump::LogMessage(
    (CompressedStreamDump *)4,
    (int)"%s: memory allocation error: %s.\n",
    "AppendCompressedMemoryStream",
    v2);
  return &loc_18001DF5A;
}

```

## disassembly

```asm
0x18002b3d4  mov     [rsp+arg_8], rdx
0x18002b3d9  push    rbp
0x18002b3da  sub     rsp, 20h
0x18002b3de  mov     rbp, rdx
0x18002b3e1  mov     rcx, [rbp+28h]
0x18002b3e5  mov     rax, [rcx]
0x18002b3e8  mov     rax, [rax+8]
0x18002b3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3f1  mov     r9, rax
0x18002b3f4  lea     r8, aAppendcompress; "AppendCompressedMemoryStream"
0x18002b3fb  lea     rdx, aSMemoryAllocat; "%s: memory allocation error: %s.\n"
0x18002b402  mov     ecx, 4; this
0x18002b407  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x18002b40c  nop
0x18002b40d  lea     rax, loc_18001DF5A
0x18002b414  add     rsp, 20h
0x18002b418  pop     rbp
0x18002b419  retn
```
