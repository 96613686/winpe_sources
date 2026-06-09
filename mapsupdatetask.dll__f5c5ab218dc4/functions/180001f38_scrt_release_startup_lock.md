# __scrt_release_startup_lock

- ea: `0x180001f38`
- end: `0x180001f5c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800018c8`
- `0x1800019c8`

## callees

- `0x180001f38`
- `0x180002500`

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
0x180001f38  push    rbx
0x180001f3a  sub     rsp, 20h
0x180001f3e  mov     bl, cl
0x180001f40  call    __scrt_is_ucrt_dll_in_use
0x180001f45  test    eax, eax
0x180001f47  jz      short loc_180001F56
0x180001f49  test    bl, bl
0x180001f4b  jnz     short loc_180001F56
0x180001f4d  xor     eax, eax
0x180001f4f  xchg    rax, cs:__scrt_native_startup_lock
0x180001f56  add     rsp, 20h
0x180001f5a  pop     rbx
0x180001f5b  retn
```
