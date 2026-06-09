# DIRLIST_CONFIG::CleanupStoredContext(void)

- ea: `0x180002940`
- end: `0x18000295f`
- name: `?CleanupStoredContext@DIRLIST_CONFIG@@UEAAXXZ`
- size: `31`
- prototype: `void __fastcall(DIRLIST_CONFIG *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002940`
- `0x180004010`

## pseudocode

```c
void __fastcall DIRLIST_CONFIG::CleanupStoredContext(DIRLIST_CONFIG *this)
{
  if ( this )
    (*(void (__fastcall **)(DIRLIST_CONFIG *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
}

```

## disassembly

```asm
0x180002940  sub     rsp, 28h
0x180002944  test    rcx, rcx
0x180002947  jz      short loc_18000295A
0x180002949  mov     rax, [rcx]
0x18000294c  mov     edx, 1
0x180002951  mov     rax, [rax+8]
0x180002955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000295a  add     rsp, 28h
0x18000295e  retn
```
