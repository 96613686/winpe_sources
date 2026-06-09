# __scrt_release_startup_lock

- ea: `0x140001518`
- end: `0x14000153c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140001180`

## callees

- `0x140001518`
- `0x140001b5c`

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
0x140001518  push    rbx
0x14000151a  sub     rsp, 20h
0x14000151e  mov     bl, cl
0x140001520  call    __scrt_is_ucrt_dll_in_use
0x140001525  test    eax, eax
0x140001527  jz      short loc_140001536
0x140001529  test    bl, bl
0x14000152b  jnz     short loc_140001536
0x14000152d  xor     eax, eax
0x14000152f  xchg    rax, cs:__scrt_native_startup_lock
0x140001536  add     rsp, 20h
0x14000153a  pop     rbx
0x14000153b  retn
```
