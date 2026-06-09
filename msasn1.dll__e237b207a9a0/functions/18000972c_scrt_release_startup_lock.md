# __scrt_release_startup_lock

- ea: `0x18000972c`
- end: `0x180009750`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008ff8`
- `0x1800090f8`

## callees

- `0x18000972c`
- `0x180009ae8`

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
0x18000972c  push    rbx
0x18000972e  sub     rsp, 20h
0x180009732  mov     bl, cl
0x180009734  call    __scrt_is_ucrt_dll_in_use
0x180009739  test    eax, eax
0x18000973b  jz      short loc_18000974A
0x18000973d  test    bl, bl
0x18000973f  jnz     short loc_18000974A
0x180009741  xor     eax, eax
0x180009743  xchg    rax, cs:__scrt_native_startup_lock
0x18000974a  add     rsp, 20h
0x18000974e  pop     rbx
0x18000974f  retn
```
