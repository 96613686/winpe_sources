# __acrt_uninitialize_stdio

- ea: `0x140132170`
- end: `0x1401321cb`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14008d6b0`
- `0x140132170`
- `0x1401494ec`
- `0x140152930`
- `0x1401529e4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1401321a1`
- `KERNEL32!DeleteCriticalSection` at `0x1401321a1`

## pseudocode

```c
__int64 _acrt_uninitialize_stdio()
{
  __int64 i; // rbx
  __int64 result; // rax

  flushall();
  fcloseall();
  for ( i = 0; i != 24; i += 8 )
  {
    _acrt_stdio_free_buffer_nolock(*(_QWORD *)(i + qword_14038BDD8));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(i + qword_14038BDD8) + 48LL));
  }
  result = sub_14008D6B0(qword_14038BDD8);
  qword_14038BDD8 = 0;
  return result;
}

```

## disassembly

```asm
0x140132170  push    rbx
0x140132172  sub     rsp, 20h
0x140132176  call    _flushall
0x14013217b  call    _fcloseall
0x140132180  xor     ebx, ebx
0x140132182  mov     rcx, cs:qword_14038BDD8
0x140132189  mov     rcx, [rbx+rcx]
0x14013218d  call    __acrt_stdio_free_buffer_nolock
0x140132192  mov     rax, cs:qword_14038BDD8
0x140132199  mov     rcx, [rbx+rax]
0x14013219d  add     rcx, 30h ; '0'; lpCriticalSection
0x1401321a1  call    cs:DeleteCriticalSection
0x1401321a7  add     rbx, 8
0x1401321ab  cmp     rbx, 18h
0x1401321af  jnz     short loc_140132182
0x1401321b1  mov     rcx, cs:qword_14038BDD8
0x1401321b8  call    sub_14008D6B0
0x1401321bd  and     cs:qword_14038BDD8, 0
0x1401321c5  add     rsp, 20h
0x1401321c9  pop     rbx
0x1401321ca  retn
```
