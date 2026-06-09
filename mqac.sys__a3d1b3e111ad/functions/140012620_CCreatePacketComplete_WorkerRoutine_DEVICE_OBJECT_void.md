# CCreatePacketComplete::WorkerRoutine(_DEVICE_OBJECT *,void *)

- ea: `0x140012620`
- end: `0x14001263d`
- name: `?WorkerRoutine@CCreatePacketComplete@@CAXPEAU_DEVICE_OBJECT@@PEAX@Z`
- size: `29`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400120e4`

## pseudocode

```c
void __fastcall CCreatePacketComplete::WorkerRoutine(PDEVICE_OBJECT DeviceObject, PVOID Context)
{
  CCreatePacketComplete::CompleteCreatePacket(
    (CCreatePacketComplete *)((char *)DeviceObject->DeviceExtension + 432),
    DeviceObject);
}

```

## disassembly

```asm
0x140012620  sub     rsp, 28h
0x140012624  mov     rdx, rcx; struct _DEVICE_OBJECT *
0x140012627  mov     rcx, [rcx+40h]
0x14001262b  add     rcx, 1B0h; this
0x140012632  call    ?CompleteCreatePacket@CCreatePacketComplete@@AEAAXPEAU_DEVICE_OBJECT@@@Z; CCreatePacketComplete::CompleteCreatePacket(_DEVICE_OBJECT *)
0x140012637  add     rsp, 28h
0x14001263b  retn
```
