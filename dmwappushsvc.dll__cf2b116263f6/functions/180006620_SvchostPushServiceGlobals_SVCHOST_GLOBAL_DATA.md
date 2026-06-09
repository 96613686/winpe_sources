# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x180006620`
- end: `0x180006628`
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
  qword_18001C8A0 = (__int64)a1;
}

```

## disassembly

```asm
0x180006620  mov     cs:qword_18001C8A0, rcx
0x180006627  retn
```
