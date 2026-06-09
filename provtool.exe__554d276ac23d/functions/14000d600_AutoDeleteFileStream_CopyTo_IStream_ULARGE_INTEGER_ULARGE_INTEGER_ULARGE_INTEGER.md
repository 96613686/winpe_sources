# AutoDeleteFileStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x14000d600`
- end: `0x14000d623`
- name: `?CopyTo@AutoDeleteFileStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `35`
- prototype: `__int64 __fastcall(AutoDeleteFileStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140010010`

## pseudocode

```c
__int64 __fastcall AutoDeleteFileStream::CopyTo(
        AutoDeleteFileStream *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  return (*(__int64 (__fastcall **)(_QWORD, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *))(**((_QWORD **)this + 6) + 56LL))(
           *((_QWORD *)this + 6),
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x14000d600  sub     rsp, 38h
0x14000d604  mov     rcx, [rcx+30h]
0x14000d608  mov     r10, [rsp+38h+arg_20]
0x14000d60d  mov     [rsp+38h+var_18], r10
0x14000d612  mov     rax, [rcx]
0x14000d615  mov     rax, [rax+38h]
0x14000d619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d61e  add     rsp, 38h
0x14000d622  retn
```
