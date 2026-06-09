# __scrt_acquire_startup_lock

- ea: `0x180002cf8`
- end: `0x180002d31`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002998`
- `0x180002a98`

## callees

- `0x180002cf8`
- `0x18000355c`

## pseudocode

```c
char _scrt_acquire_startup_lock()
{
  PVOID StackBase; // rcx
  signed __int64 v1; // rax

  if ( _scrt_is_ucrt_dll_in_use() )
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
0x180002cf8  sub     rsp, 28h
0x180002cfc  call    __scrt_is_ucrt_dll_in_use
0x180002d01  test    eax, eax
0x180002d03  jz      short loc_180002D26
0x180002d05  mov     rax, gs:30h
0x180002d0e  mov     rcx, [rax+8]
0x180002d12  jmp     short loc_180002D19
0x180002d14  cmp     rcx, rax
0x180002d17  jz      short loc_180002D2D
0x180002d19  xor     eax, eax
0x180002d1b  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180002d24  jnz     short loc_180002D14
0x180002d26  xor     al, al
0x180002d28  add     rsp, 28h
0x180002d2c  retn
0x180002d2d  mov     al, 1
0x180002d2f  jmp     short loc_180002D28
```
