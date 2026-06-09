# ___scrt_dllmain_uninitialize_critical

- ea: `0x1003569d`
- end: `0x100356aa`
- name: `___scrt_dllmain_uninitialize_critical`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100352db`

## callees

- `0x10035fb5`

## pseudocode

```c
int __cdecl __scrt_dllmain_uninitialize_critical(int a1)
{
  __scrt_stub_for_acrt_initialize(0);
  return __scrt_stub_for_acrt_initialize(a1);
}

```

## disassembly

```asm
0x1003569d  push    0
0x1003569f  call    ___scrt_stub_for_acrt_initialize
0x100356a4  pop     ecx
0x100356a5  jmp     ___scrt_stub_for_acrt_initialize
```
