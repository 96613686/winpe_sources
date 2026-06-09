# __acrt_uninitialize_stdio

- ea: `0x18001b400`
- end: `0x18001b45b`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180019608`
- `0x18001b400`
- `0x18001cae8`
- `0x18001cc18`
- `0x18001cccc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001b431`
- `KERNEL32!DeleteCriticalSection` at `0x18001b431`

## pseudocode

```c
void _acrt_uninitialize_stdio()
{
  __int64 i; // rbx

  flushall();
  fcloseall();
  for ( i = 0; i != 24; i += 8 )
  {
    _acrt_stdio_free_buffer_nolock(*(_QWORD *)((char *)_piob + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)((char *)_piob + i) + 48LL));
  }
  free_base(_piob);
  _piob = 0;
}

```

## disassembly

```asm
0x18001b400  push    rbx
0x18001b402  sub     rsp, 20h
0x18001b406  call    _flushall
0x18001b40b  call    _fcloseall
0x18001b410  xor     ebx, ebx
0x18001b412  mov     rcx, cs:__piob
0x18001b419  mov     rcx, [rbx+rcx]
0x18001b41d  call    __acrt_stdio_free_buffer_nolock
0x18001b422  mov     rax, cs:__piob
0x18001b429  mov     rcx, [rbx+rax]
0x18001b42d  add     rcx, 30h ; '0'; lpCriticalSection
0x18001b431  call    cs:__imp_DeleteCriticalSection
0x18001b437  add     rbx, 8
0x18001b43b  cmp     rbx, 18h
0x18001b43f  jnz     short loc_18001B412
0x18001b441  mov     rcx, cs:__piob; Block
0x18001b448  call    _free_base
0x18001b44d  and     cs:__piob, 0
0x18001b455  add     rsp, 20h
0x18001b459  pop     rbx
0x18001b45a  retn
```
