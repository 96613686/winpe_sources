# __scrt_release_startup_lock

- ea: `0x18000199c`
- end: `0x1800019c0`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001268`
- `0x180001368`

## callees

- `0x18000199c`
- `0x180001db8`

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
0x18000199c  push    rbx
0x18000199e  sub     rsp, 20h
0x1800019a2  mov     bl, cl
0x1800019a4  call    __scrt_is_ucrt_dll_in_use
0x1800019a9  test    eax, eax
0x1800019ab  jz      short loc_1800019BA
0x1800019ad  test    bl, bl
0x1800019af  jnz     short loc_1800019BA
0x1800019b1  xor     eax, eax
0x1800019b3  xchg    rax, cs:__scrt_native_startup_lock
0x1800019ba  add     rsp, 20h
0x1800019be  pop     rbx
0x1800019bf  retn
```
