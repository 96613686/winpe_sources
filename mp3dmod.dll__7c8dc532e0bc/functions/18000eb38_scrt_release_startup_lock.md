# __scrt_release_startup_lock

- ea: `0x18000eb38`
- end: `0x18000eb5c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000e428`
- `0x18000e528`

## callees

- `0x18000eb38`
- `0x18000eed0`

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
0x18000eb38  push    rbx
0x18000eb3a  sub     rsp, 20h
0x18000eb3e  mov     bl, cl
0x18000eb40  call    __scrt_is_ucrt_dll_in_use
0x18000eb45  test    eax, eax
0x18000eb47  jz      short loc_18000EB56
0x18000eb49  test    bl, bl
0x18000eb4b  jnz     short loc_18000EB56
0x18000eb4d  xor     eax, eax
0x18000eb4f  xchg    rax, cs:__scrt_native_startup_lock
0x18000eb56  add     rsp, 20h
0x18000eb5a  pop     rbx
0x18000eb5b  retn
```
