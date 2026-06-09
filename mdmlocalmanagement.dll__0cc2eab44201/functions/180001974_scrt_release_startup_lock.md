# __scrt_release_startup_lock

- ea: `0x180001974`
- end: `0x180001998`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001338`
- `0x180001438`

## callees

- `0x180001974`
- `0x180001ed0`

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
0x180001974  push    rbx
0x180001976  sub     rsp, 20h
0x18000197a  mov     bl, cl
0x18000197c  call    __scrt_is_ucrt_dll_in_use
0x180001981  test    eax, eax
0x180001983  jz      short loc_180001992
0x180001985  test    bl, bl
0x180001987  jnz     short loc_180001992
0x180001989  xor     eax, eax
0x18000198b  xchg    rax, cs:__scrt_native_startup_lock
0x180001992  add     rsp, 20h
0x180001996  pop     rbx
0x180001997  retn
```
