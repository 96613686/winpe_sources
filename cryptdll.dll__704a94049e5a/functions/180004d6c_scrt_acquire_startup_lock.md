# __scrt_acquire_startup_lock

- ea: `0x180004d6c`
- end: `0x180004da5`
- name: `__scrt_acquire_startup_lock`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004928`
- `0x180004a28`

## callees

- `0x180004d6c`
- `0x180005418`

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
0x180004d6c  sub     rsp, 28h
0x180004d70  call    __scrt_is_ucrt_dll_in_use
0x180004d75  test    eax, eax
0x180004d77  jz      short loc_180004D9A
0x180004d79  mov     rax, gs:30h
0x180004d82  mov     rcx, [rax+8]
0x180004d86  jmp     short loc_180004D8D
0x180004d88  cmp     rcx, rax
0x180004d8b  jz      short loc_180004DA1
0x180004d8d  xor     eax, eax
0x180004d8f  lock cmpxchg cs:__scrt_native_startup_lock, rcx
0x180004d98  jnz     short loc_180004D88
0x180004d9a  xor     al, al
0x180004d9c  add     rsp, 28h
0x180004da0  retn
0x180004da1  mov     al, 1
0x180004da3  jmp     short loc_180004D9C
```
