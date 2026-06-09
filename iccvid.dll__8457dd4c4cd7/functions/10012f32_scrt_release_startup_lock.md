# ___scrt_release_startup_lock

- ea: `0x10012f32`
- end: `0x10012f51`
- name: `___scrt_release_startup_lock`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1001280b`
- `0x1001291b`

## callees

- `0x10012f32`
- `0x100133f1`

## pseudocode

```c
__int32 __cdecl __scrt_release_startup_lock(char a1)
{
  __int32 result; // eax

  result = __scrt_is_ucrt_dll_in_use();
  if ( result )
  {
    if ( !a1 )
      return _InterlockedExchange(&__scrt_native_startup_lock, 0);
  }
  return result;
}

```

## disassembly

```asm
0x10012f32  mov     edi, edi
0x10012f34  push    ebp
0x10012f35  mov     ebp, esp
0x10012f37  call    ___scrt_is_ucrt_dll_in_use
0x10012f3c  test    eax, eax
0x10012f3e  jz      short loc_10012F4F
0x10012f40  cmp     [ebp+arg_0], 0
0x10012f44  jnz     short loc_10012F4F
0x10012f46  xor     eax, eax
0x10012f48  mov     ecx, offset ___scrt_native_startup_lock
0x10012f4d  xchg    eax, [ecx]
0x10012f4f  pop     ebp
0x10012f50  retn
```
