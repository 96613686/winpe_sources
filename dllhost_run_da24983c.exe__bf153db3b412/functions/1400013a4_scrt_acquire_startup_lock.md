# __scrt_acquire_startup_lock

- ea: `0x1400013a4`
- end: `0x1400013dd`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400011d0`

## callees

- `0x1400013a4`
- `0x140001bdc`

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
0x1400013a4  sub     rsp, 28h
0x1400013a8  call    __scrt_is_ucrt_dll_in_use
0x1400013ad  test    eax, eax
0x1400013af  jz      short loc_1400013D2
0x1400013b1  mov     rax, gs:30h
0x1400013ba  mov     rcx, [rax+8]
0x1400013be  jmp     short loc_1400013C5
0x1400013c0  cmp     rcx, rax
0x1400013c3  jz      short loc_1400013D9
0x1400013c5  xor     eax, eax
0x1400013c7  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x1400013d0  jnz     short loc_1400013C0
0x1400013d2  xor     al, al
0x1400013d4  add     rsp, 28h
0x1400013d8  retn
0x1400013d9  mov     al, 1
0x1400013db  jmp     short loc_1400013D4
```
