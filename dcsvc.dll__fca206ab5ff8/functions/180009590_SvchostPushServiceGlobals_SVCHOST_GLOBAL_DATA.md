# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x180009590`
- end: `0x180009598`
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
  qword_18001B6F0 = (__int64)a1;
}

```

## disassembly

```asm
0x180009590  mov     cs:qword_18001B6F0, rcx
0x180009597  retn
```
