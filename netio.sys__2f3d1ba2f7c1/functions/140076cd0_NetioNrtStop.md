# NetioNrtStop

- ea: `0x140076cd0`
- end: `0x140076d2a`
- name: `NetioNrtStop`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140076ba0`

## callees

- `0x1400761d0`
- `0x140076cd0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x140076ce0`
- `ntoskrnl!IoDeleteDevice` at `0x140076ce0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076d0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076d0d`

## pseudocode

```c
void NetioNrtStop()
{
  if ( NrtDeviceObject )
  {
    IoDeleteDevice(NrtDeviceObject);
    NrtDeviceObject = 0;
  }
  NrtDestroyRecordSet();
  if ( NrtSecurityDescriptor )
    ExFreePoolWithTag(NrtSecurityDescriptor, 0x6473724Eu);
  NrtSecurityDescriptor = 0;
}

```

## disassembly

```asm
0x140076cd0  sub     rsp, 28h
0x140076cd4  mov     rcx, cs:NrtDeviceObject; DeviceObject
0x140076cdb  test    rcx, rcx
0x140076cde  jz      short loc_140076CF7
0x140076ce0  call    cs:__imp_IoDeleteDevice
0x140076ce7  nop     dword ptr [rax+rax+00h]
0x140076cec  mov     cs:NrtDeviceObject, 0
0x140076cf7  call    NrtDestroyRecordSet
0x140076cfc  mov     rcx, cs:NrtSecurityDescriptor; P
0x140076d03  test    rcx, rcx
0x140076d06  jz      short loc_140076D19
0x140076d08  mov     edx, 6473724Eh; Tag
0x140076d0d  call    cs:__imp_ExFreePoolWithTag
0x140076d14  nop     dword ptr [rax+rax+00h]
0x140076d19  mov     cs:NrtSecurityDescriptor, 0
0x140076d24  add     rsp, 28h
0x140076d28  retn
```
