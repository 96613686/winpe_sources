# __scrt_release_startup_lock

- ea: `0x140001558`
- end: `0x14000157c`
- name: `__scrt_release_startup_lock`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400011d0`

## callees

- `0x140001558`
- `0x140001bdc`

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
0x140001558  push    rbx
0x14000155a  sub     rsp, 20h
0x14000155e  mov     bl, cl
0x140001560  call    __scrt_is_ucrt_dll_in_use
0x140001565  test    eax, eax
0x140001567  jz      short loc_140001576
0x140001569  test    bl, bl
0x14000156b  jnz     short loc_140001576
0x14000156d  xor     eax, eax
0x14000156f  xchg    rax, cs:__scrt_native_startup_lock
0x140001576  add     rsp, 20h
0x14000157a  pop     rbx
0x14000157b  retn
```
