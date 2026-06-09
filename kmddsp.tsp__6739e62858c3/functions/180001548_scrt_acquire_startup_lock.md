# __scrt_acquire_startup_lock

- ea: `0x180001548`
- end: `0x180001581`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800010e8`
- `0x1800011e8`

## callees

- `0x180001548`
- `0x180001bd0`

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
0x180001548  sub     rsp, 28h
0x18000154c  call    __scrt_is_ucrt_dll_in_use
0x180001551  test    eax, eax
0x180001553  jz      short loc_180001576
0x180001555  mov     rax, gs:30h
0x18000155e  mov     rcx, [rax+8]
0x180001562  jmp     short loc_180001569
0x180001564  cmp     rcx, rax
0x180001567  jz      short loc_18000157D
0x180001569  xor     eax, eax
0x18000156b  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180001574  jnz     short loc_180001564
0x180001576  xor     al, al
0x180001578  add     rsp, 28h
0x18000157c  retn
0x18000157d  mov     al, 1
0x18000157f  jmp     short loc_180001578
```
