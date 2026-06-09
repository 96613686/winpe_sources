# __scrt_release_startup_lock

- ea: `0x1800018a8`
- end: `0x1800018cc`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001148`
- `0x180001248`

## callees

- `0x1800018a8`
- `0x180001c58`

## pseudocode

```c
__int64 __fastcall _scrt_release_startup_lock(char a1)
{
  __int64 result; // rax

  result = _scrt_is_ucrt_dll_in_use();
  if ( (_DWORD)result )
  {
    if ( !a1 )
      return _InterlockedExchange64(&_scrt_native_startup_lock, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1800018a8  push    rbx
0x1800018aa  sub     rsp, 20h
0x1800018ae  mov     bl, cl
0x1800018b0  call    __scrt_is_ucrt_dll_in_use
0x1800018b5  test    eax, eax
0x1800018b7  jz      short loc_1800018C6
0x1800018b9  test    bl, bl
0x1800018bb  jnz     short loc_1800018C6
0x1800018bd  xor     eax, eax
0x1800018bf  xchg    rax, cs:__scrt_native_startup_lock
0x1800018c6  add     rsp, 20h
0x1800018ca  pop     rbx
0x1800018cb  retn
```
