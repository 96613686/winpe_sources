# __scrt_acquire_startup_lock

- ea: `0x18000159c`
- end: `0x1800015d5`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001158`
- `0x180001258`

## callees

- `0x18000159c`
- `0x180001c48`

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
0x18000159c  sub     rsp, 28h
0x1800015a0  call    __scrt_is_ucrt_dll_in_use
0x1800015a5  test    eax, eax
0x1800015a7  jz      short loc_1800015CA
0x1800015a9  mov     rax, gs:30h
0x1800015b2  mov     rcx, [rax+8]
0x1800015b6  jmp     short loc_1800015BD
0x1800015b8  cmp     rcx, rax
0x1800015bb  jz      short loc_1800015D1
0x1800015bd  xor     eax, eax
0x1800015bf  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800015c8  jnz     short loc_1800015B8
0x1800015ca  xor     al, al
0x1800015cc  add     rsp, 28h
0x1800015d0  retn
0x1800015d1  mov     al, 1
0x1800015d3  jmp     short loc_1800015CC
```
