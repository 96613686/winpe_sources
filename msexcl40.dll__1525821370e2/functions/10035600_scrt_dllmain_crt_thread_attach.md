# ___scrt_dllmain_crt_thread_attach

- ea: `0x10035600`
- end: `0x1003561f`
- name: `___scrt_dllmain_crt_thread_attach`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x10035170`

## callees

- `0x10035600`
- `0x10035fb5`

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
0x10035600  call    ___scrt_stub_for_acrt_initialize
0x10035605  test    al, al
0x10035607  jnz     short loc_1003560C
0x10035609  xor     al, al
0x1003560b  retn
0x1003560c  call    ___scrt_stub_for_acrt_initialize
0x10035611  test    al, al
0x10035613  jnz     short loc_1003561C
0x10035615  call    ___scrt_stub_for_acrt_initialize
0x1003561a  jmp     short loc_10035609
0x1003561c  mov     al, 1
0x1003561e  retn
```
