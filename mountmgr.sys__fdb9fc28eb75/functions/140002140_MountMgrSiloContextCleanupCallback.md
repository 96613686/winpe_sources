# MountMgrSiloContextCleanupCallback

- ea: `0x140002140`
- end: `0x140002170`
- name: `MountMgrSiloContextCleanupCallback`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140001bec`
- `0x140002140`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000215d`
- `ntoskrnl!IoDeleteDevice` at `0x14000215d`

## pseudocode

```c
void __fastcall MountMgrSiloContextCleanupCallback(PDEVICE_OBJECT *a1)
{
  PDEVICE_OBJECT v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    MountMgrFreeSiloDeviceExtension(v2->DeviceExtension);
    IoDeleteDevice(*a1);
  }
}

```

## disassembly

```asm
0x140002140  push    rbx
0x140002142  sub     rsp, 20h
0x140002146  mov     rbx, rcx
0x140002149  mov     rcx, [rcx]
0x14000214c  test    rcx, rcx
0x14000214f  jz      short loc_140002169
0x140002151  mov     rcx, [rcx+40h]
0x140002155  call    MountMgrFreeSiloDeviceExtension
0x14000215a  mov     rcx, [rbx]; DeviceObject
0x14000215d  call    cs:__imp_IoDeleteDevice
0x140002164  nop     dword ptr [rax+rax+00h]
0x140002169  add     rsp, 20h
0x14000216d  pop     rbx
0x14000216e  retn
```
