# CPacketHandleToCPacket(_DEVICE_OBJECT *,CPacket *)

- ea: `0x140009adc`
- end: `0x140009aef`
- name: `?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAU_DEVICE_OBJECT@@PEAV1@@Z`
- size: `19`
- prototype: `struct CPacket *__fastcall(struct _DEVICE_OBJECT *, struct CPacket *)`
- caller_count: `21`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400041ac`
- `0x140004bc4`
- `0x140005e1c`
- `0x140005f08`
- `0x1400060c0`
- `0x1400061fc`
- `0x140006334`
- `0x14000648c`
- `0x14000669c`
- `0x140006e88`
- `0x1400078f4`
- `0x140007a88`
- `0x140007cb8`
- `0x140007e3c`
- `0x14000a2b8`
- `0x14000b28c`
- `0x140011e00`
- `0x1400120e4`
- `0x14001adac`
- `0x140020ebc`
- `0x140020f9c`

## callees

- `0x140009a54`

## pseudocode

```c
struct CPacket *__fastcall CPacketHandleToCPacket(struct _DEVICE_OBJECT *a1, struct CPacket *a2)
{
  return CPacketHandleToCPacket((struct CDeviceExt *)a1->DeviceExtension, a2);
}

```

## disassembly

```asm
0x140009adc  sub     rsp, 28h
0x140009ae0  mov     rcx, [rcx+40h]; struct CDeviceExt *
0x140009ae4  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAUCDeviceExt@@PEAX@Z; CPacketHandleToCPacket(CDeviceExt *,void *)
0x140009ae9  add     rsp, 28h
0x140009aed  retn
```
