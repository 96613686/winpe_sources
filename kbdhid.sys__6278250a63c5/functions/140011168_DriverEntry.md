# DriverEntry

- ea: `0x140011168`
- end: `0x140011306`
- name: `DriverEntry`
- size: `414`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x140011100`

## callees

- `0x140007240`
- `0x14000f118`
- `0x14000f1cc`
- `0x14000f5bc`
- `0x140010cf0`
- `0x140011168`
- `0x140011660`
- `0x140011940`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140011223`
- `ntoskrnl!ExAllocatePool2` at `0x140011223`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  DRIVER_CONTROL *Pool2; // rax

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_KbdHidTraceGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  wil_InitializeFeatureStaging();
  *(_OWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = 0;
  *(_OWORD *)&WPP_MAIN_CB.Queue.Wcb.DeviceContext = 0;
  BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceContext) = 1;
  HIWORD(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels) = RegistryPath->Length + 2;
  LOWORD(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels) = RegistryPath->Length;
  Pool2 = (DRIVER_CONTROL *)ExAllocatePool2(256, HIWORD(WPP_MAIN_CB.Queue.Wcb.NumberOfChannels), 1214538315);
  WPP_MAIN_CB.Queue.Wcb.DeviceRoutine = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, RegistryPath->Buffer, RegistryPath->Length);
    Kbdhid_ServiceParameters((__int64)DriverObject, (const WCHAR *)WPP_MAIN_CB.Queue.Wcb.DeviceRoutine);
    DriverObject->MajorFunction[0] = (PDRIVER_DISPATCH)KbdHid_Create;
    DriverObject->MajorFunction[2] = (PDRIVER_DISPATCH)&KbdHid_Close;
    DriverObject->MajorFunction[15] = (PDRIVER_DISPATCH)KbdHid_IOCTL;
    DriverObject->MajorFunction[14] = (PDRIVER_DISPATCH)KbdHid_PassThrough;
    DriverObject->MajorFunction[9] = (PDRIVER_DISPATCH)KbdHid_Flush;
    DriverObject->MajorFunction[27] = (PDRIVER_DISPATCH)KbdHid_PnP;
    DriverObject->MajorFunction[22] = (PDRIVER_DISPATCH)KbdHid_Power;
    DriverObject->MajorFunction[23] = (PDRIVER_DISPATCH)KbdHid_SystemControl;
    DriverObject->DriverUnload = (PDRIVER_UNLOAD)KbdHid_Unload;
    DriverObject->DriverExtension->AddDevice = (PDRIVER_ADD_DEVICE)KbdHid_AddDevice;
    return 0;
  }
  else
  {
    wil_UninitializeFeatureStaging();
    WppCleanupKm(DriverObject);
    return -1073741670;
  }
}

```

## disassembly

```asm
0x140011168  mov     [rsp+arg_0], rbx
0x14001116d  push    rdi
0x14001116e  sub     rsp, 20h
0x140011172  lea     rax, WPP_ThisDir_CTLGUID_KbdHidTraceGuid
0x140011179  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x140011184  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14001118b  mov     rdi, rdx
0x14001118e  xor     eax, eax
0x140011190  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x14001119b  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x1400111a1  mov     rbx, rcx
0x1400111a4  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400111af  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400111ba  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1400111c5  call    WppLoadTracingSupport
0x1400111ca  mov     rdx, rdi; __annotation("TMC:", "b41b0a56-4483-48ef-a772-0b007cbea8c6", "KbdHidTraceGuid", "TRACE_FLAG_CREATECLOSE", "TRACE_FLAG_READ", "TRACE_FLAG_IOCTL", "TRACE_FLAG_POWER", "TRACE_FLAG_PNP", "TRACE_FLAG_DRIVER", "PUBLIC_TMF:")
0x1400111cd  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400111d8  mov     rcx, rbx
0x1400111db  call    WppInitKm
0x1400111e0  call    wil_InitializeFeatureStaging
0x1400111e5  xorps   xmm0, xmm0
0x1400111e8  mov     ecx, 100h
0x1400111ed  movups  xmmword ptr cs:WPP_MAIN_CB.Queue+10h, xmm0
0x1400111f4  mov     r8d, 4864624Bh
0x1400111fa  movups  xmmword ptr cs:WPP_MAIN_CB.Queue+20h, xmm0
0x140011201  mov     byte ptr cs:WPP_MAIN_CB.Queue+24h, 1
0x140011208  movzx   eax, word ptr [rdi]
0x14001120b  add     ax, 2
0x14001120f  movzx   edx, ax
0x140011212  mov     word ptr cs:WPP_MAIN_CB.Queue+12h, dx
0x140011219  movzx   eax, word ptr [rdi]
0x14001121c  mov     word ptr cs:WPP_MAIN_CB.Queue+10h, ax
0x140011223  call    cs:__imp_ExAllocatePool2
0x14001122a  nop     dword ptr [rax+rax+00h]
0x14001122f  mov     qword ptr cs:WPP_MAIN_CB.Queue+18h, rax
0x140011236  test    rax, rax
0x140011239  jnz     short loc_140011252
0x14001123b  call    wil_UninitializeFeatureStaging
0x140011240  mov     rcx, rbx
0x140011243  call    WppCleanupKm
0x140011248  mov     eax, 0C000009Ah
0x14001124d  jmp     loc_1400112FA
0x140011252  movzx   r8d, word ptr [rdi]; Size
0x140011256  mov     rcx, rax; void *
0x140011259  mov     rdx, [rdi+8]; Src
0x14001125d  call    memmove
0x140011262  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x140011269  mov     rcx, rbx
0x14001126c  call    Kbdhid_ServiceParameters
0x140011271  lea     rax, KbdHid_Create
0x140011278  mov     [rbx+70h], rax
0x14001127c  lea     rcx, KbdHid_AddDevice
0x140011283  lea     rax, KbdHid_Close
0x14001128a  mov     [rbx+80h], rax
0x140011291  lea     rax, KbdHid_IOCTL
0x140011298  mov     [rbx+0E8h], rax
0x14001129f  lea     rax, KbdHid_PassThrough
0x1400112a6  mov     [rbx+0E0h], rax
0x1400112ad  lea     rax, KbdHid_Flush
0x1400112b4  mov     [rbx+0B8h], rax
0x1400112bb  lea     rax, KbdHid_PnP
0x1400112c2  mov     [rbx+148h], rax
0x1400112c9  lea     rax, KbdHid_Power
0x1400112d0  mov     [rbx+120h], rax
0x1400112d7  lea     rax, KbdHid_SystemControl
0x1400112de  mov     [rbx+128h], rax
0x1400112e5  lea     rax, KbdHid_Unload
0x1400112ec  mov     [rbx+68h], rax
0x1400112f0  mov     rax, [rbx+30h]
0x1400112f4  mov     [rax+8], rcx
0x1400112f8  xor     eax, eax
0x1400112fa  mov     rbx, [rsp+28h+arg_0]
0x1400112ff  add     rsp, 20h
0x140011303  pop     rdi
0x140011304  retn
```
