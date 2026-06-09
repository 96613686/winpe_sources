# __scrt_release_startup_lock

- ea: `0x18000188c`
- end: `0x1800018b0`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011f8`
- `0x1800012f8`

## callees

- `0x18000188c`
- `0x180001f7c`

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
0x18000188c  push    rbx
0x18000188e  sub     rsp, 20h
0x180001892  mov     bl, cl
0x180001894  call    __scrt_is_ucrt_dll_in_use
0x180001899  test    eax, eax
0x18000189b  jz      short loc_1800018AA
0x18000189d  test    bl, bl
0x18000189f  jnz     short loc_1800018AA
0x1800018a1  xor     eax, eax
0x1800018a3  xchg    rax, cs:__scrt_native_startup_lock
0x1800018aa  add     rsp, 20h
0x1800018ae  pop     rbx
0x1800018af  retn
```
