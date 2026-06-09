# ___scrt_dllmain_crt_thread_attach

- ea: `0x10012d15`
- end: `0x10012d34`
- name: `___scrt_dllmain_crt_thread_attach`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x100127b0`

## callees

- `0x10012d15`
- `0x100134f0`

## pseudocode

```c
char __scrt_dllmain_crt_thread_attach()
{
  if ( !(unsigned __int8)__scrt_stub_for_acrt_initialize() )
    return 0;
  if ( !(unsigned __int8)__scrt_stub_for_acrt_initialize() )
  {
    __scrt_stub_for_acrt_initialize();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x10012d15  call    ___scrt_stub_for_acrt_initialize
0x10012d1a  test    al, al
0x10012d1c  jnz     short loc_10012D21
0x10012d1e  xor     al, al
0x10012d20  retn
0x10012d21  call    ___scrt_stub_for_acrt_initialize
0x10012d26  test    al, al
0x10012d28  jnz     short loc_10012D31
0x10012d2a  call    ___scrt_stub_for_acrt_initialize
0x10012d2f  jmp     short loc_10012D1E
0x10012d31  mov     al, 1
0x10012d33  retn
```
