# ACDeleteDeviceObject(_DEVICE_OBJECT *)

- ea: `0x14000d3dc`
- end: `0x14000d423`
- name: `?ACDeleteDeviceObject@@YAXPEAU_DEVICE_OBJECT@@@Z`
- size: `71`
- prototype: `void __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x140020b40`
- `0x140020bf0`

## callees

- `0x14000ce0c`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000d40b`
- `ntoskrnl!IoDeleteDevice` at `0x14000d40b`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000d3f4`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14000d3f4`

## pseudocode

```c
void __fastcall ACDeleteDeviceObject(PDEVICE_OBJECT DeviceObject)
{
  char *DeviceExtension; // rbx

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  IoDeleteSymbolicLink((PUNICODE_STRING)(DeviceExtension + 1096));
  CDeviceExt::~CDeviceExt((CDeviceExt *)DeviceExtension);
  IoDeleteDevice(DeviceObject);
}

```

## disassembly

```asm
0x14000d3dc  mov     [rsp+arg_0], rbx
0x14000d3e1  push    rdi
0x14000d3e2  sub     rsp, 20h
0x14000d3e6  mov     rbx, [rcx+40h]
0x14000d3ea  mov     rdi, rcx
0x14000d3ed  lea     rcx, [rbx+448h]; SymbolicLinkName
0x14000d3f4  call    cs:__imp_IoDeleteSymbolicLink
0x14000d3fb  nop     dword ptr [rax+rax+00h]
0x14000d400  mov     rcx, rbx; this
0x14000d403  call    ??1CDeviceExt@@QEAA@XZ; CDeviceExt::~CDeviceExt(void)
0x14000d408  mov     rcx, rdi; DeviceObject
0x14000d40b  call    cs:__imp_IoDeleteDevice
0x14000d412  nop     dword ptr [rax+rax+00h]
0x14000d417  mov     rbx, [rsp+28h+arg_0]
0x14000d41c  add     rsp, 20h
0x14000d420  pop     rdi
0x14000d421  retn
```
