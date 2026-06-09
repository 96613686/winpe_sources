# CJob::GetPage(_TASKPAGE,int,_PSP * *)

- ea: `0x18000b910`
- end: `0x18000b919`
- name: `?GetPage@CJob@@UEAAJW4_TASKPAGE@@HPEAPEAU_PSP@@@Z`
- size: `9`
- prototype: `__int64 __fastcall(CJob *__hidden this, enum _TASKPAGE, int, struct _PSP **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180010098`

## pseudocode

```c
__int64 __fastcall CJob::GetPage(struct ITask *this, enum _TASKPAGE a2, int a3, struct _PSP **a4)
{
  return I_GetTaskPage(this - 2, a2, a3, a4);
}

```

## disassembly

```asm
0x18000b910  add     rcx, 0FFFFFFFFFFFFFFF0h; struct ITask *
0x18000b914  jmp     ?I_GetTaskPage@@YAJPEAUITask@@W4_TASKPAGE@@HPEAPEAU_PSP@@@Z; I_GetTaskPage(ITask *,_TASKPAGE,int,_PSP * *)
```
