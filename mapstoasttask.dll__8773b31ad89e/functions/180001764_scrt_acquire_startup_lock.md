# __scrt_acquire_startup_lock

- ea: `0x180001764`
- end: `0x18000179d`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001298`
- `0x180001398`

## callees

- `0x180001764`
- `0x180001eb8`

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
0x180001764  sub     rsp, 28h
0x180001768  call    __scrt_is_ucrt_dll_in_use
0x18000176d  test    eax, eax
0x18000176f  jz      short loc_180001792
0x180001771  mov     rax, gs:30h
0x18000177a  mov     rcx, [rax+8]
0x18000177e  jmp     short loc_180001785
0x180001780  cmp     rcx, rax
0x180001783  jz      short loc_180001799
0x180001785  xor     eax, eax
0x180001787  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001790  jnz     short loc_180001780
0x180001792  xor     al, al
0x180001794  add     rsp, 28h
0x180001798  retn
0x180001799  mov     al, 1
0x18000179b  jmp     short loc_180001794
```
