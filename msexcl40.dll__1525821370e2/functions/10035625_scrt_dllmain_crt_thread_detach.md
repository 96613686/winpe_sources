# ___scrt_dllmain_crt_thread_detach

- ea: `0x10035625`
- end: `0x10035632`
- name: `___scrt_dllmain_crt_thread_detach`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x10035170`

## callees

- `0x10035fb5`

## pseudocode

```c
char __scrt_dllmain_crt_thread_detach()
{
  __scrt_stub_for_acrt_initialize();
  __scrt_stub_for_acrt_initialize();
  return 1;
}

```

## disassembly

```asm
0x10035625  call    ___scrt_stub_for_acrt_initialize
0x1003562a  call    ___scrt_stub_for_acrt_initialize
0x1003562f  mov     al, 1
0x10035631  retn
```
