# CStorageComplete::WorkerRoutine(_DEVICE_OBJECT *,void *)

- ea: `0x140021490`
- end: `0x1400214ad`
- name: `?WorkerRoutine@CStorageComplete@@CAXPEAU_DEVICE_OBJECT@@PEAX@Z`
- size: `29`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140021144`

## pseudocode

```c
void __fastcall CStorageComplete::WorkerRoutine(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  CStorageComplete::CompleteStorage((CStorageComplete *)((char *)DeviceObject->DeviceExtension + 384), DeviceObject);
}

```

## disassembly

```asm
0x140021490  sub     rsp, 28h
0x140021494  mov     rdx, rcx; struct _DEVICE_OBJECT *
0x140021497  mov     rcx, [rcx+40h]
0x14002149b  add     rcx, 180h; this
0x1400214a2  call    ?CompleteStorage@CStorageComplete@@AEAAXPEAU_DEVICE_OBJECT@@@Z; CStorageComplete::CompleteStorage(_DEVICE_OBJECT *)
0x1400214a7  add     rsp, 28h
0x1400214ab  retn
```
