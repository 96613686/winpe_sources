# __scrt_release_startup_lock

- ea: `0x180001838`
- end: `0x18000185c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800010e8`
- `0x1800011e8`

## callees

- `0x180001838`
- `0x180001bd0`

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
0x180001838  push    rbx
0x18000183a  sub     rsp, 20h
0x18000183e  mov     bl, cl
0x180001840  call    __scrt_is_ucrt_dll_in_use
0x180001845  test    eax, eax
0x180001847  jz      short loc_180001856
0x180001849  test    bl, bl
0x18000184b  jnz     short loc_180001856
0x18000184d  xor     eax, eax
0x18000184f  xchg    rax, cs:__scrt_native_startup_lock
0x180001856  add     rsp, 20h
0x18000185a  pop     rbx
0x18000185b  retn
```
