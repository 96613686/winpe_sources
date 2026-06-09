# __scrt_acquire_startup_lock

- ea: `0x180001658`
- end: `0x180001691`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001208`
- `0x180001308`

## callees

- `0x180001658`
- `0x180001d4c`

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
0x180001658  sub     rsp, 28h
0x18000165c  call    __scrt_is_ucrt_dll_in_use
0x180001661  test    eax, eax
0x180001663  jz      short loc_180001686
0x180001665  mov     rax, gs:30h
0x18000166e  mov     rcx, [rax+8]
0x180001672  jmp     short loc_180001679
0x180001674  cmp     rcx, rax
0x180001677  jz      short loc_18000168D
0x180001679  xor     eax, eax
0x18000167b  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001684  jnz     short loc_180001674
0x180001686  xor     al, al
0x180001688  add     rsp, 28h
0x18000168c  retn
0x18000168d  mov     al, 1
0x18000168f  jmp     short loc_180001688
```
