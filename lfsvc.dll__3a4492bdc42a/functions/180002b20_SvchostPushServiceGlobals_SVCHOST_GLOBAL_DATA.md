# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x180002b20`
- end: `0x180002b28`
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
  qword_180012450 = (__int64)a1;
}

```

## disassembly

```asm
0x180002b20  mov     cs:qword_180012450, rcx
0x180002b27  retn
```
