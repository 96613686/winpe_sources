# __scrt_dllmain_crt_thread_attach

- ea: `0x180012d18`
- end: `0x180012d40`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800127d0`

## callees

- `0x180012d18`
- `0x180014b14`
- `0x180014b28`
- `0x180018384`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !_acrt_thread_attach() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180012d18  sub     rsp, 28h
0x180012d1c  call    __vcrt_thread_attach
0x180012d21  test    al, al
0x180012d23  jnz     short loc_180012D29
0x180012d25  xor     al, al
0x180012d27  jmp     short loc_180012D3B
0x180012d29  call    __acrt_thread_attach
0x180012d2e  test    al, al
0x180012d30  jnz     short loc_180012D39
0x180012d32  call    __vcrt_thread_detach
0x180012d37  jmp     short loc_180012D25
0x180012d39  mov     al, 1
0x180012d3b  add     rsp, 28h
0x180012d3f  retn
```
