# SvchostPushServiceGlobals

- ea: `0x180006430`
- end: `0x180006438`
- name: `SvchostPushServiceGlobals`
- size: `8`
- prototype: `void __fastcall(struct _SVCHOST_GLOBAL_DATA *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(struct _SVCHOST_GLOBAL_DATA *a1)
{
  g_SvcHostGlobals = a1;
}

```

## disassembly

```asm
0x180006430  mov     cs:?g_SvcHostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, rcx; _SVCHOST_GLOBAL_DATA * g_SvcHostGlobals
0x180006437  retn
```
