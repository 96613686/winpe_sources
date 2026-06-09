# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x1800050d0`
- end: `0x1800050d8`
- name: `?SvchostPushServiceGlobals@@YAXPEAU_SVCHOST_GLOBAL_DATA@@@Z`
- size: `8`
- prototype: `void __fastcall(struct _SVCHOST_GLOBAL_DATA *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(struct _SVCHOST_GLOBAL_DATA *a1)
{
  g_pSvchostGlobalData = a1;
}

```

## disassembly

```asm
0x1800050d0  mov     cs:?g_pSvchostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, rcx; _SVCHOST_GLOBAL_DATA * g_pSvchostGlobalData
0x1800050d7  retn
```
