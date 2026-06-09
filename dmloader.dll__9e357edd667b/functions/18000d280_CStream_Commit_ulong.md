# CStream::Commit(ulong)

- ea: `0x18000d280`
- end: `0x18000d29b`
- name: `?Commit@CStream@@UEAAJK@Z`
- size: `27`
- prototype: `__int64 __fastcall(CStream *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000d280`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CStream::Commit(CStream *this)
{
  __int64 v1; // rcx

  v1 = *((_QWORD *)this + 3);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 64LL))(v1);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000d280  mov     rcx, [rcx+18h]
0x18000d284  test    rcx, rcx
0x18000d287  jz      short loc_18000D295
0x18000d289  mov     rax, [rcx]
0x18000d28c  mov     rax, [rax+40h]
0x18000d290  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000d295  mov     eax, 80004005h
0x18000d29a  retn
```
