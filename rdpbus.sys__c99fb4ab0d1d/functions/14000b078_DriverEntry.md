# DriverEntry

- ea: `0x14000b078`
- end: `0x14000b14b`
- name: `DriverEntry`
- size: `211`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000b010`

## callees

- `0x1400020e4`
- `0x140008074`
- `0x1400080f8`
- `0x14000818c`
- `0x14000857c`
- `0x14000b078`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS v3; // edi

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport(DriverObject, RegistryPath);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)RdpBusUnload;
  DriverObject->DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)RdpBusPnPAddDevice;
  memset64(DriverObject->MajorFunction, (unsigned __int64)RdpBusDispatch, 0x1Cu);
  v3 = InitializeRdpBusSecurity();
  if ( v3 >= 0 )
    return 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids, (unsigned int)v3);
  WppCleanupKm();
  return v3;
}

```

## disassembly

```asm
0x14000b078  push    rdi
0x14000b07a  sub     rsp, 20h
0x14000b07e  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x14000b085  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14000b090  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14000b097  mov     rdi, rcx
0x14000b09a  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14000b0a5  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000b0b0  mov     cs:WPP_MAIN_CB.Timer, 1
0x14000b0bb  call    WppLoadTracingSupport
0x14000b0c0  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000b0cb  call    WppInitKm
0x14000b0d0  lea     rax, RdpBusUnload
0x14000b0d7  mov     [rdi+68h], rax
0x14000b0db  lea     rcx, ?RdpBusPnPAddDevice@@YAJPEAU_DRIVER_OBJECT@@PEAU_DEVICE_OBJECT@@@Z; RdpBusPnPAddDevice(_DRIVER_OBJECT *,_DEVICE_OBJECT *)
0x14000b0e2  mov     rax, [rdi+30h]
0x14000b0e6  add     rdi, 70h ; 'p'
0x14000b0ea  mov     [rax+8], rcx
0x14000b0ee  lea     rax, ?RdpBusDispatch@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; RdpBusDispatch(_DEVICE_OBJECT *,_IRP *)
0x14000b0f5  mov     ecx, 1Ch
0x14000b0fa  rep stosq
0x14000b0fd  call    InitializeRdpBusSecurity
0x14000b102  mov     edi, eax
0x14000b104  test    eax, eax
0x14000b106  jns     short loc_14000B142
0x14000b108  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b10f  lea     rax, WPP_GLOBAL_Control
0x14000b116  cmp     rcx, rax
0x14000b119  jz      short loc_14000B139
0x14000b11b  cmp     byte ptr [rcx+29h], 2
0x14000b11f  jb      short loc_14000B139
0x14000b121  mov     rcx, [rcx+18h]
0x14000b125  lea     r8, WPP_aa2742c9424e303f9b5b727f51c5aafc_Traceguids
0x14000b12c  mov     edx, 0Ah
0x14000b131  mov     r9d, edi
0x14000b134  call    WPP_SF_D
0x14000b139  call    WppCleanupKm
0x14000b13e  mov     eax, edi
0x14000b140  jmp     short loc_14000B144
0x14000b142  xor     eax, eax
0x14000b144  add     rsp, 20h
0x14000b148  pop     rdi
0x14000b149  retn
```
