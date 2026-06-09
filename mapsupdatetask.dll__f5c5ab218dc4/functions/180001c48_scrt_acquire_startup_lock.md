# __scrt_acquire_startup_lock

- ea: `0x180001c48`
- end: `0x180001c81`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800018c8`
- `0x1800019c8`

## callees

- `0x180001c48`
- `0x180002500`

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
0x180001c48  sub     rsp, 28h
0x180001c4c  call    __scrt_is_ucrt_dll_in_use
0x180001c51  test    eax, eax
0x180001c53  jz      short loc_180001C76
0x180001c55  mov     rax, gs:30h
0x180001c5e  mov     rcx, [rax+8]
0x180001c62  jmp     short loc_180001C69
0x180001c64  cmp     rcx, rax
0x180001c67  jz      short loc_180001C7D
0x180001c69  xor     eax, eax
0x180001c6b  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001c74  jnz     short loc_180001C64
0x180001c76  xor     al, al
0x180001c78  add     rsp, 28h
0x180001c7c  retn
0x180001c7d  mov     al, 1
0x180001c7f  jmp     short loc_180001C78
```
