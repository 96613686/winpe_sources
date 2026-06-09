# ___scrt_dllmain_uninitialize_critical

- ea: `0x10012db2`
- end: `0x10012dbf`
- name: `___scrt_dllmain_uninitialize_critical`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1001291b`

## callees

- `0x100134f0`

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
0x10012db2  push    0
0x10012db4  call    ___scrt_stub_for_acrt_initialize
0x10012db9  pop     ecx
0x10012dba  jmp     ___scrt_stub_for_acrt_initialize
```
