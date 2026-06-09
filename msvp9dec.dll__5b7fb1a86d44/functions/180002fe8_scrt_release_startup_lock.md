# __scrt_release_startup_lock

- ea: `0x180002fe8`
- end: `0x18000300c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002998`
- `0x180002a98`

## callees

- `0x180002fe8`
- `0x18000355c`

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
0x180002fe8  push    rbx
0x180002fea  sub     rsp, 20h
0x180002fee  mov     bl, cl
0x180002ff0  call    __scrt_is_ucrt_dll_in_use
0x180002ff5  test    eax, eax
0x180002ff7  jz      short loc_180003006
0x180002ff9  test    bl, bl
0x180002ffb  jnz     short loc_180003006
0x180002ffd  xor     eax, eax
0x180002fff  xchg    rax, cs:__scrt_native_startup_lock
0x180003006  add     rsp, 20h
0x18000300a  pop     rbx
0x18000300b  retn
```
