# __scrt_release_startup_lock

- ea: `0x18000505c`
- end: `0x180005080`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004928`
- `0x180004a28`

## callees

- `0x18000505c`
- `0x180005418`

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
0x18000505c  push    rbx
0x18000505e  sub     rsp, 20h
0x180005062  mov     bl, cl
0x180005064  call    __scrt_is_ucrt_dll_in_use
0x180005069  test    eax, eax
0x18000506b  jz      short loc_18000507A
0x18000506d  test    bl, bl
0x18000506f  jnz     short loc_18000507A
0x180005071  xor     eax, eax
0x180005073  xchg    rax, cs:__scrt_native_startup_lock
0x18000507a  add     rsp, 20h
0x18000507e  pop     rbx
0x18000507f  retn
```
