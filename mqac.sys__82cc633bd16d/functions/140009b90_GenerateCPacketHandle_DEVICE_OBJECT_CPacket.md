# GenerateCPacketHandle(_DEVICE_OBJECT *,CPacket *)

- ea: `0x140009b90`
- end: `0x140009ba3`
- name: `?GenerateCPacketHandle@@YA_KPEAU_DEVICE_OBJECT@@PEAVCPacket@@@Z`
- size: `19`
- prototype: `unsigned __int64 __fastcall(struct _DEVICE_OBJECT *, struct CPacket *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140003f74`
- `0x14001569c`
- `0x140017884`
- `0x140017b04`
- `0x140017b90`
- `0x140017ca4`
- `0x140018410`
- `0x140018dc8`

## callees

- `0x140009af8`

## pseudocode

```c
unsigned __int64 __fastcall GenerateCPacketHandle(struct _DEVICE_OBJECT *a1, struct CPacket *a2)
{
  return GenerateCPacketHandle((struct CDeviceExt *)a1->DeviceExtension, a2);
}

```

## disassembly

```asm
0x140009b90  sub     rsp, 28h
0x140009b94  mov     rcx, [rcx+40h]; struct CDeviceExt *
0x140009b98  call    ?GenerateCPacketHandle@@YA_KPEAUCDeviceExt@@PEAVCPacket@@@Z; GenerateCPacketHandle(CDeviceExt *,CPacket *)
0x140009b9d  add     rsp, 28h
0x140009ba1  retn
```
