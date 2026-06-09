# __scrt_release_startup_lock

- ea: `0x180001a54`
- end: `0x180001a78`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001298`
- `0x180001398`

## callees

- `0x180001a54`
- `0x180001eb8`

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
0x180001a54  push    rbx
0x180001a56  sub     rsp, 20h
0x180001a5a  mov     bl, cl
0x180001a5c  call    __scrt_is_ucrt_dll_in_use
0x180001a61  test    eax, eax
0x180001a63  jz      short loc_180001A72
0x180001a65  test    bl, bl
0x180001a67  jnz     short loc_180001A72
0x180001a69  xor     eax, eax
0x180001a6b  xchg    rax, cs:__scrt_native_startup_lock
0x180001a72  add     rsp, 20h
0x180001a76  pop     rbx
0x180001a77  retn
```
