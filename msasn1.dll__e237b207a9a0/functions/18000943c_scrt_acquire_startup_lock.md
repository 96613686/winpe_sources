# __scrt_acquire_startup_lock

- ea: `0x18000943c`
- end: `0x180009475`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008ff8`
- `0x1800090f8`

## callees

- `0x18000943c`
- `0x180009ae8`

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
0x18000943c  sub     rsp, 28h
0x180009440  call    __scrt_is_ucrt_dll_in_use
0x180009445  test    eax, eax
0x180009447  jz      short loc_18000946A
0x180009449  mov     rax, gs:30h
0x180009452  mov     rcx, [rax+8]
0x180009456  jmp     short loc_18000945D
0x180009458  cmp     rcx, rax
0x18000945b  jz      short loc_180009471
0x18000945d  xor     eax, eax
0x18000945f  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180009468  jnz     short loc_180009458
0x18000946a  xor     al, al
0x18000946c  add     rsp, 28h
0x180009470  retn
0x180009471  mov     al, 1
0x180009473  jmp     short loc_18000946C
```
