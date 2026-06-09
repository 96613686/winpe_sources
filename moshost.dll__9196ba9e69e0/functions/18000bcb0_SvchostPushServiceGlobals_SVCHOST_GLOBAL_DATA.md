# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x18000bcb0`
- end: `0x18000bcb8`
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
  qword_180018668 = (__int64)a1;
}

```

## disassembly

```asm
0x18000bcb0  mov     cs:qword_180018668, rcx
0x18000bcb7  retn
```
