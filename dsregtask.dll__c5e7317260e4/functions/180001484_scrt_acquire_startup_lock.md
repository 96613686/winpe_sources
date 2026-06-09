# __scrt_acquire_startup_lock

- ea: `0x180001484`
- end: `0x1800014bd`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: `char()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001148`
- `0x180001248`

## callees

- `0x180001484`
- `0x180001c98`

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
0x180001484  sub     rsp, 28h
0x180001488  call    __scrt_is_ucrt_dll_in_use
0x18000148d  test    eax, eax
0x18000148f  jz      short loc_1800014B2
0x180001491  mov     rax, gs:30h
0x18000149a  mov     rcx, [rax+8]
0x18000149e  jmp     short loc_1800014A5
0x1800014a0  cmp     rcx, rax
0x1800014a3  jz      short loc_1800014B9
0x1800014a5  xor     eax, eax
0x1800014a7  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1800014b0  jnz     short loc_1800014A0
0x1800014b2  xor     al, al
0x1800014b4  add     rsp, 28h
0x1800014b8  retn
0x1800014b9  mov     al, 1
0x1800014bb  jmp     short loc_1800014B4
```
