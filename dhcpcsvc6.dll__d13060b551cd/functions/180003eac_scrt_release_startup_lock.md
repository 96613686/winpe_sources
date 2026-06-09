# __scrt_release_startup_lock

- ea: `0x180003eac`
- end: `0x180003ed0`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003778`
- `0x180003878`

## callees

- `0x180003eac`
- `0x180004268`

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
0x180003eac  push    rbx
0x180003eae  sub     rsp, 20h
0x180003eb2  mov     bl, cl
0x180003eb4  call    __scrt_is_ucrt_dll_in_use
0x180003eb9  test    eax, eax
0x180003ebb  jz      short loc_180003ECA
0x180003ebd  test    bl, bl
0x180003ebf  jnz     short loc_180003ECA
0x180003ec1  xor     eax, eax
0x180003ec3  xchg    rax, cs:__scrt_native_startup_lock
0x180003eca  add     rsp, 20h
0x180003ece  pop     rbx
0x180003ecf  retn
```
