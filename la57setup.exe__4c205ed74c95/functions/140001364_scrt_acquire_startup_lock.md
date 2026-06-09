# __scrt_acquire_startup_lock

- ea: `0x140001364`
- end: `0x14000139d`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001180`

## callees

- `0x140001364`
- `0x140001b5c`

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
0x140001364  sub     rsp, 28h
0x140001368  call    __scrt_is_ucrt_dll_in_use
0x14000136d  test    eax, eax
0x14000136f  jz      short loc_140001392
0x140001371  mov     rax, gs:30h
0x14000137a  mov     rcx, [rax+8]
0x14000137e  jmp     short loc_140001385
0x140001380  cmp     rcx, rax
0x140001383  jz      short loc_140001399
0x140001385  xor     eax, eax
0x140001387  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x140001390  jnz     short loc_140001380
0x140001392  xor     al, al
0x140001394  add     rsp, 28h
0x140001398  retn
0x140001399  mov     al, 1
0x14000139b  jmp     short loc_140001394
```
