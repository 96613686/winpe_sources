# __scrt_acquire_startup_lock

- ea: `0x180001e38`
- end: `0x180001e71`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800019c8`
- `0x180001ac8`

## callees

- `0x180001e38`
- `0x180002538`

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
0x180001e38  sub     rsp, 28h
0x180001e3c  call    __scrt_is_ucrt_dll_in_use
0x180001e41  test    eax, eax
0x180001e43  jz      short loc_180001E66
0x180001e45  mov     rax, gs:30h
0x180001e4e  mov     rcx, [rax+8]
0x180001e52  jmp     short loc_180001E59
0x180001e54  cmp     rcx, rax
0x180001e57  jz      short loc_180001E6D
0x180001e59  xor     eax, eax
0x180001e5b  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001e64  jnz     short loc_180001E54
0x180001e66  xor     al, al
0x180001e68  add     rsp, 28h
0x180001e6c  retn
0x180001e6d  mov     al, 1
0x180001e6f  jmp     short loc_180001E68
```
