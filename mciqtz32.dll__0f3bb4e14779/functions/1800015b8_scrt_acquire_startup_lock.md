# __scrt_acquire_startup_lock

- ea: `0x1800015b8`
- end: `0x1800015f1`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001148`
- `0x180001248`

## callees

- `0x1800015b8`
- `0x180001c58`

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
0x1800015b8  sub     rsp, 28h
0x1800015bc  call    __scrt_is_ucrt_dll_in_use
0x1800015c1  test    eax, eax
0x1800015c3  jz      short loc_1800015E6
0x1800015c5  mov     rax, gs:30h
0x1800015ce  mov     rcx, [rax+8]
0x1800015d2  jmp     short loc_1800015D9
0x1800015d4  cmp     rcx, rax
0x1800015d7  jz      short loc_1800015ED
0x1800015d9  xor     eax, eax
0x1800015db  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800015e4  jnz     short loc_1800015D4
0x1800015e6  xor     al, al
0x1800015e8  add     rsp, 28h
0x1800015ec  retn
0x1800015ed  mov     al, 1
0x1800015ef  jmp     short loc_1800015E8
```
