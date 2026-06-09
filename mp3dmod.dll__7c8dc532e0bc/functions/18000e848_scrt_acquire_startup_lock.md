# __scrt_acquire_startup_lock

- ea: `0x18000e848`
- end: `0x18000e881`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000e428`
- `0x18000e528`

## callees

- `0x18000e848`
- `0x18000eed0`

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
0x18000e848  sub     rsp, 28h
0x18000e84c  call    __scrt_is_ucrt_dll_in_use
0x18000e851  test    eax, eax
0x18000e853  jz      short loc_18000E876
0x18000e855  mov     rax, gs:30h
0x18000e85e  mov     rcx, [rax+8]
0x18000e862  jmp     short loc_18000E869
0x18000e864  cmp     rcx, rax
0x18000e867  jz      short loc_18000E87D
0x18000e869  xor     eax, eax
0x18000e86b  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x18000e874  jnz     short loc_18000E864
0x18000e876  xor     al, al
0x18000e878  add     rsp, 28h
0x18000e87c  retn
0x18000e87d  mov     al, 1
0x18000e87f  jmp     short loc_18000E878
```
