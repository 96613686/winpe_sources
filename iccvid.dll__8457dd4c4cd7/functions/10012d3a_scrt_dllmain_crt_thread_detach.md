# ___scrt_dllmain_crt_thread_detach

- ea: `0x10012d3a`
- end: `0x10012d47`
- name: `___scrt_dllmain_crt_thread_detach`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100127b0`

## callees

- `0x100134f0`

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
0x10012d3a  call    ___scrt_stub_for_acrt_initialize
0x10012d3f  call    ___scrt_stub_for_acrt_initialize
0x10012d44  mov     al, 1
0x10012d46  retn
```
