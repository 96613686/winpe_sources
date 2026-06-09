# DriverEntry

- ea: `0x14000d078`
- end: `0x14000d220`
- name: `DriverEntry`
- size: `424`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x14000d010`

## callees

- `0x140004ec0`
- `0x14000b044`
- `0x14000b0f8`
- `0x14000b1c0`
- `0x14000d078`
- `0x14000d228`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d172`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d172`
- `ntoskrnl!ExAllocatePool2` at `0x14000d127`
- `ntoskrnl!ExAllocatePool2` at `0x14000d127`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  void *Pool2; // rax
  NTSTATUS RegistryParameters; // edi

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_MouHidTraceGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  *(_OWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = 0;
  *(_OWORD *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
  WORD1(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) = RegistryPath->Length + 2;
  LOWORD(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine) = RegistryPath->Length;
  Pool2 = (void *)ExAllocatePool2(256, WORD1(WPP_MAIN_CB.Queue.Wcb.DeviceRoutine), 1215655757);
  WPP_MAIN_CB.Queue.Wcb.DeviceContext = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, RegistryPath->Buffer, RegistryPath->Length);
    RegistryParameters = MouHid_GetRegistryParameters((__int64)DriverObject);
    if ( RegistryParameters >= 0 )
    {
      DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)MouHid_Create;
      DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&MouHid_Close;
      DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)MouHid_IOCTL;
      DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)MouHid_PassThrough;
      DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)MouHid_Flush;
      DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)MouHid_PnP;
      DriverObject->MajorFunction[22] = (PDRIVER_DISPATCH)MouHid_Power;
      DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)MouHid_SystemControl;
      DriverObject->DriverUnload = (PDRIVER_UNLOAD)MouHid_Unload;
      DriverObject->DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)MouHid_AddDevice;
      return RegistryParameters;
    }
  }
  else
  {
    RegistryParameters = -1073741670;
  }
  if ( WPP_MAIN_CB.Queue.Wcb.DeviceContext )
    ExFreePoolWithTag(WPP_MAIN_CB.Queue.Wcb.DeviceContext, 0);
  WppCleanupKm(DriverObject);
  return RegistryParameters;
}

```

## disassembly

```asm
0x14000d078  mov     [rsp+arg_0], rbx
0x14000d07d  push    rdi
0x14000d07e  sub     rsp, 20h
0x14000d082  lea     rax, WPP_ThisDir_CTLGUID_MouHidTraceGuid
0x14000d089  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x14000d094  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14000d09b  mov     rdi, rdx
0x14000d09e  xor     eax, eax
0x14000d0a0  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14000d0ab  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x14000d0b1  mov     rbx, rcx
0x14000d0b4  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000d0bf  mov     cs:WPP_MAIN_CB.Timer, 1
0x14000d0ca  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x14000d0d5  call    WppLoadTracingSupport
0x14000d0da  mov     rdx, rdi; __annotation("TMC:", "bbbc2565-8272-486e-b5e5-2bc4630374ba", "MouHidTraceGuid", "TRACE_FLAG_CREATECLOSE", "TRACE_FLAG_READ", "TRACE_FLAG_IOCTL", "TRACE_FLAG_POWER", "TRACE_FLAG_PNP", "TRACE_FLAG_DRIVER", "PUBLIC_TMF:")
0x14000d0dd  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x14000d0e8  mov     rcx, rbx
0x14000d0eb  call    WppInitKm
0x14000d0f0  xorps   xmm0, xmm0
0x14000d0f3  mov     ecx, 100h
0x14000d0f8  movups  xmmword ptr cs:WPP_MAIN_CB.Queue+10h, xmm0
0x14000d0ff  mov     r8d, 48756F4Dh
0x14000d105  movups  xmmword ptr cs:WPP_MAIN_CB.Queue+20h, xmm0
0x14000d10c  movzx   eax, word ptr [rdi]
0x14000d10f  add     ax, 2
0x14000d113  movzx   edx, ax
0x14000d116  mov     word ptr cs:WPP_MAIN_CB.Queue+1Ah, dx
0x14000d11d  movzx   eax, word ptr [rdi]
0x14000d120  mov     word ptr cs:WPP_MAIN_CB.Queue+18h, ax
0x14000d127  call    cs:__imp_ExAllocatePool2
0x14000d12e  nop     dword ptr [rax+rax+00h]
0x14000d133  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, rax
0x14000d13a  test    rax, rax
0x14000d13d  jnz     short loc_14000D146
0x14000d13f  mov     edi, 0C000009Ah
0x14000d144  jmp     short loc_14000D164
0x14000d146  movzx   r8d, word ptr [rdi]; Size
0x14000d14a  mov     rcx, rax; void *
0x14000d14d  mov     rdx, [rdi+8]; Src
0x14000d151  call    memmove
0x14000d156  mov     rcx, rbx
0x14000d159  call    MouHid_GetRegistryParameters
0x14000d15e  mov     edi, eax
0x14000d160  test    eax, eax
0x14000d162  jns     short loc_14000D18B
0x14000d164  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h; P
0x14000d16b  test    rcx, rcx
0x14000d16e  jz      short loc_14000D17E
0x14000d170  xor     edx, edx; Tag
0x14000d172  call    cs:__imp_ExFreePoolWithTag
0x14000d179  nop     dword ptr [rax+rax+00h]
0x14000d17e  mov     rcx, rbx
0x14000d181  call    WppCleanupKm
0x14000d186  jmp     loc_14000D212
0x14000d18b  lea     rax, MouHid_Create
0x14000d192  mov     [rbx+70h], rax
0x14000d196  lea     rcx, MouHid_AddDevice
0x14000d19d  lea     rax, MouHid_Close
0x14000d1a4  mov     [rbx+80h], rax
0x14000d1ab  lea     rax, MouHid_IOCTL
0x14000d1b2  mov     [rbx+0E8h], rax
0x14000d1b9  lea     rax, MouHid_PassThrough
0x14000d1c0  mov     [rbx+0E0h], rax
0x14000d1c7  lea     rax, MouHid_Flush
0x14000d1ce  mov     [rbx+0B8h], rax
0x14000d1d5  lea     rax, MouHid_PnP
0x14000d1dc  mov     [rbx+148h], rax
0x14000d1e3  lea     rax, MouHid_Power
0x14000d1ea  mov     [rbx+120h], rax
0x14000d1f1  lea     rax, MouHid_SystemControl
0x14000d1f8  mov     [rbx+128h], rax
0x14000d1ff  lea     rax, MouHid_Unload
0x14000d206  mov     [rbx+68h], rax
0x14000d20a  mov     rax, [rbx+30h]
0x14000d20e  mov     [rax+8], rcx
0x14000d212  mov     rbx, [rsp+28h+arg_0]
0x14000d217  mov     eax, edi
0x14000d219  add     rsp, 20h
0x14000d21d  pop     rdi
0x14000d21e  retn
```
