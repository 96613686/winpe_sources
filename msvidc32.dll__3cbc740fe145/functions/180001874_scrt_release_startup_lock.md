# __scrt_release_startup_lock

- ea: `0x180001874`
- end: `0x180001898`
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

- `0x180001874`
- `0x180001c10`

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
0x180001874  push    rbx
0x180001876  sub     rsp, 20h
0x18000187a  mov     bl, cl
0x18000187c  call    __scrt_is_ucrt_dll_in_use
0x180001881  test    eax, eax
0x180001883  jz      short loc_180001892
0x180001885  test    bl, bl
0x180001887  jnz     short loc_180001892
0x180001889  xor     eax, eax
0x18000188b  xchg    rax, cs:__scrt_native_startup_lock
0x180001892  add     rsp, 20h
0x180001896  pop     rbx
0x180001897  retn
```
