# CStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x18000d2b0`
- end: `0x18000d2df`
- name: `?CopyTo@CStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `47`
- prototype: `__int64 __fastcall(CStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000d2b0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CStream::CopyTo(
        CStream *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  __int64 v5; // rcx

  v5 = *((_QWORD *)this + 3);
  if ( v5 )
    return (*(__int64 (__fastcall **)(__int64, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *))(*(_QWORD *)v5 + 56LL))(
             v5,
             a2,
             a3,
             a4,
             a5);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000d2b0  sub     rsp, 38h
0x18000d2b4  mov     rcx, [rcx+18h]
0x18000d2b8  test    rcx, rcx
0x18000d2bb  jz      short loc_18000D2D5
0x18000d2bd  mov     rax, [rcx]
0x18000d2c0  mov     r10, [rsp+38h+arg_20]
0x18000d2c5  mov     [rsp+38h+var_18], r10
0x18000d2ca  mov     rax, [rax+38h]
0x18000d2ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2d3  jmp     short loc_18000D2DA
0x18000d2d5  mov     eax, 80004005h
0x18000d2da  add     rsp, 38h
0x18000d2de  retn
```
