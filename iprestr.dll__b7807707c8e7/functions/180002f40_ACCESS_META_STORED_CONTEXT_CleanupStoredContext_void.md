# ACCESS_META_STORED_CONTEXT::CleanupStoredContext(void)

- ea: `0x180002f40`
- end: `0x180002f5f`
- name: `?CleanupStoredContext@ACCESS_META_STORED_CONTEXT@@UEAAXXZ`
- size: `31`
- prototype: `void __fastcall(ACCESS_META_STORED_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002f40`
- `0x180005010`

## pseudocode

```c
void __fastcall ACCESS_META_STORED_CONTEXT::CleanupStoredContext(ACCESS_META_STORED_CONTEXT *this)
{
  if ( this )
    (*(void (__fastcall **)(ACCESS_META_STORED_CONTEXT *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
}

```

## disassembly

```asm
0x180002f40  sub     rsp, 28h
0x180002f44  test    rcx, rcx
0x180002f47  jz      short loc_180002F5A
0x180002f49  mov     rax, [rcx]
0x180002f4c  mov     edx, 1
0x180002f51  mov     rax, [rax+8]
0x180002f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f5a  add     rsp, 28h
0x180002f5e  retn
```
