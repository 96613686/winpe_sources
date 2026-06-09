# __scrt_dllmain_crt_thread_detach

- ea: `0x180012d40`
- end: `0x180012d55`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800127d0`

## callees

- `0x180014b28`
- `0x180018398`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _acrt_thread_detach();
  _vcrt_thread_detach();
  return 1;
}

```

## disassembly

```asm
0x180012d40  sub     rsp, 28h
0x180012d44  call    __acrt_thread_detach
0x180012d49  call    __vcrt_thread_detach
0x180012d4e  mov     al, 1
0x180012d50  add     rsp, 28h
0x180012d54  retn
```
