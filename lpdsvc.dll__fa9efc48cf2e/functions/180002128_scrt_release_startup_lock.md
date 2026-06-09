# __scrt_release_startup_lock

- ea: `0x180002128`
- end: `0x18000214c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800019c8`
- `0x180001ac8`

## callees

- `0x180002128`
- `0x180002538`

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
0x180002128  push    rbx
0x18000212a  sub     rsp, 20h
0x18000212e  mov     bl, cl
0x180002130  call    __scrt_is_ucrt_dll_in_use
0x180002135  test    eax, eax
0x180002137  jz      short loc_180002146
0x180002139  test    bl, bl
0x18000213b  jnz     short loc_180002146
0x18000213d  xor     eax, eax
0x18000213f  xchg    rax, cs:__scrt_native_startup_lock
0x180002146  add     rsp, 20h
0x18000214a  pop     rbx
0x18000214b  retn
```
