# HbpPowerOnFinalizedDeviceIrp

- ea: `0x140001340`
- end: `0x1400013c0`
- name: `HbpPowerOnFinalizedDeviceIrp`
- size: `128`
- prototype: `void __fastcall(PDEVICE_OBJECT DeviceObject, UCHAR MinorFunction, POWER_STATE PowerState, IRP *Context, PIO_STATUS_BLOCK IoStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001340`
- `0x140001600`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001398`
- `ntoskrnl!IofCompleteRequest` at `0x140001398`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140001387`
- `ntoskrnl!PoStartNextPowerIrp` at `0x140001387`

## pseudocode

```c
void __fastcall HbpPowerOnFinalizedDeviceIrp(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        IRP *Context,
        PIO_STATUS_BLOCK IoStatus)
{
  if ( Context )
  {
    if ( IoStatus->Status < 0 )
      HbpTraceEvent(1, "HbpPowerOnFinalizedDeviceIrp", 460, "Device power IRP failed with 0x%x", IoStatus->Status);
    Context->IoStatus.Status = IoStatus->Status;
    PoStartNextPowerIrp(Context);
    IofCompleteRequest(Context, 0);
  }
}

```

## disassembly

```asm
0x140001340  test    r9, r9
0x140001343  jz      short locret_1400013AE
0x140001345  push    rbx
0x140001346  sub     rsp, 30h
0x14000134a  mov     [rsp+38h+arg_0], rdi
0x14000134f  mov     rbx, r9
0x140001352  mov     rdi, [rsp+38h+IoStatus]
0x140001357  mov     eax, [rdi]
0x140001359  test    eax, eax
0x14000135b  jns     short loc_14000137F
0x14000135d  lea     r9, aDevicePowerIrp; "Device power IRP failed with 0x%x"
0x140001364  mov     [rsp+38h+var_18], eax
0x140001368  mov     r8d, 1CCh
0x14000136e  lea     rdx, aHbppoweronfina; "HbpPowerOnFinalizedDeviceIrp"
0x140001375  mov     ecx, 1
0x14000137a  call    HbpTraceEvent
0x14000137f  mov     eax, [rdi]
0x140001381  mov     rcx, rbx; Irp
0x140001384  mov     [rbx+30h], eax
0x140001387  call    cs:__imp_PoStartNextPowerIrp
0x14000138e  nop     dword ptr [rax+rax+00h]
0x140001393  xor     edx, edx; PriorityBoost
0x140001395  mov     rcx, rbx; Irp
0x140001398  call    cs:__imp_IofCompleteRequest
0x14000139f  nop     dword ptr [rax+rax+00h]
0x1400013a4  mov     rdi, [rsp+38h+arg_0]
0x1400013a9  add     rsp, 30h
0x1400013ad  pop     rbx
0x1400013ae  retn
```
