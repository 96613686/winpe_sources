# __scrt_acquire_startup_lock

- ea: `0x180003bbc`
- end: `0x180003bf5`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003778`
- `0x180003878`

## callees

- `0x180003bbc`
- `0x180004268`

## pseudocode

```c
char _scrt_acquire_startup_lock()
{
  PVOID StackBase; // rcx
  signed __int64 v1; // rax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    StackBase = NtCurrentTeb()->NtTib.StackBase;
    while ( 1 )
    {
      v1 = _InterlockedCompareExchange64(&_scrt_native_startup_lock, (signed __int64)StackBase, 0);
      if ( !v1 )
        break;
      if ( StackBase == (PVOID)v1 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003bbc  sub     rsp, 28h
0x180003bc0  call    __scrt_is_ucrt_dll_in_use
0x180003bc5  test    eax, eax
0x180003bc7  jz      short loc_180003BEA
0x180003bc9  mov     rax, gs:30h
0x180003bd2  mov     rcx, [rax+8]
0x180003bd6  jmp     short loc_180003BDD
0x180003bd8  cmp     rcx, rax
0x180003bdb  jz      short loc_180003BF1
0x180003bdd  xor     eax, eax
0x180003bdf  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180003be8  jnz     short loc_180003BD8
0x180003bea  xor     al, al
0x180003bec  add     rsp, 28h
0x180003bf0  retn
0x180003bf1  mov     al, 1
0x180003bf3  jmp     short loc_180003BEC
```
