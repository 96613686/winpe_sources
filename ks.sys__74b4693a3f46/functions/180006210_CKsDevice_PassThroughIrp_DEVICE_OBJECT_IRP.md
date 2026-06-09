# CKsDevice::PassThroughIrp(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180006210`
- end: `0x18000632f`
- name: `?PassThroughIrp@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180006210`
- `0x1800073d0`
- `0x180011dcc`
- `0x180019c60`
- `0x1800481d0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18000625b`
- `ntoskrnl!KeWaitForSingleObject` at `0x18000625b`
- `ntoskrnl!IofCompleteRequest` at `0x1800062c2`
- `ntoskrnl!IofCompleteRequest` at `0x1800062c2`

## pseudocode

```c
NTSTATUS __fastcall CKsDevice::PassThroughIrp(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  __int64 v4; // rsi
  int v5; // eax
  __int64 v6; // r14

  v4 = *(_QWORD *)(*(_QWORD *)DeviceObject->DeviceExtension + 360LL);
  v5 = *(_DWORD *)(v4 + 56);
  v6 = v4 - 200;
  if ( Irp->RequestorMode == 1 )
  {
    if ( v5 != 1 )
      KeWaitForSingleObject((PVOID)(v6 + 1064), Executive, 0, 0, 0);
    return KsDispatchIrp(DeviceObject, Irp);
  }
  if ( v5 == 1 )
    return KsDispatchIrp(DeviceObject, Irp);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 40LL))(v4 - 200);
  if ( *(_DWORD *)(v4 + 56) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 48LL))(v4 - 200);
    return KsDispatchIrp(DeviceObject, Irp);
  }
  if ( (unsigned __int8)IsMapVRAMIrp(Irp) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 48LL))(v4 - 200);
    Irp->IoStatus.Status = -1073741101;
    IofCompleteRequest(Irp, 0);
    return -1073741101;
  }
  else
  {
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    KsAddIrpToCancelableQueue((PLIST_ENTRY)(v6 + 1040), (PKSPIN_LOCK)(v6 + 1056), Irp, KsListEntryTail, 0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 48LL))(v4 - 200);
    return 259;
  }
}

```

## disassembly

```asm
0x180006210  push    rbx
0x180006212  push    rsi
0x180006213  push    rdi
0x180006214  push    r14
0x180006216  sub     rsp, 38h
0x18000621a  mov     rax, [rcx+40h]
0x18000621e  mov     rbx, rdx
0x180006221  mov     rdi, rcx
0x180006224  cmp     byte ptr [rbx+40h], 1
0x180006228  mov     rdx, [rax]
0x18000622b  mov     rsi, [rdx+168h]
0x180006232  mov     eax, [rsi+38h]
0x180006235  lea     r14, [rsi-0C8h]
0x18000623c  jnz     short loc_18000627D
0x18000623e  cmp     eax, 1
0x180006241  jz      short loc_180006267
0x180006243  lea     rcx, [r14+428h]; Object
0x18000624a  mov     [rsp+58h+Timeout], 0; Timeout
0x180006253  xor     r9d, r9d; Alertable
0x180006256  xor     r8d, r8d; WaitMode
0x180006259  xor     edx, edx; WaitReason
0x18000625b  call    cs:__imp_KeWaitForSingleObject
0x180006262  nop     dword ptr [rax+rax+00h]
0x180006267  mov     rdx, rbx; Irp
0x18000626a  mov     rcx, rdi; DeviceObject
0x18000626d  call    KsDispatchIrp
0x180006272  add     rsp, 38h
0x180006276  pop     r14
0x180006278  pop     rdi
0x180006279  pop     rsi
0x18000627a  pop     rbx
0x18000627b  retn
0x18000627d  cmp     eax, 1
0x180006280  jz      short loc_180006267
0x180006282  mov     rax, [r14]
0x180006285  mov     rcx, r14
0x180006288  mov     rax, [rax+28h]
0x18000628c  call    _guard_dispatch_icall
0x180006291  cmp     dword ptr [rsi+38h], 1
0x180006295  jz      loc_18000631B
0x18000629b  mov     rcx, rbx
0x18000629e  call    IsMapVRAMIrp
0x1800062a3  test    al, al
0x1800062a5  jz      short loc_1800062D5
0x1800062a7  mov     rax, [r14]
0x1800062aa  mov     rcx, r14
0x1800062ad  mov     rax, [rax+30h]
0x1800062b1  call    _guard_dispatch_icall
0x1800062b6  xor     edx, edx; PriorityBoost
0x1800062b8  mov     dword ptr [rbx+30h], 0C00002D3h
0x1800062bf  mov     rcx, rbx; Irp
0x1800062c2  call    cs:__imp_IofCompleteRequest
0x1800062c9  nop     dword ptr [rax+rax+00h]
0x1800062ce  mov     eax, 0C00002D3h
0x1800062d3  jmp     short loc_180006272
0x1800062d5  mov     rax, [rbx+0B8h]
0x1800062dc  lea     rdx, [r14+420h]; SpinLock
0x1800062e3  lea     rcx, [r14+410h]; QueueHead
0x1800062ea  mov     [rsp+58h+Timeout], 0; DriverCancel
0x1800062f3  xor     r9d, r9d; ListLocation
0x1800062f6  mov     r8, rbx; Irp
0x1800062f9  or      byte ptr [rax+3], 1
0x1800062fd  call    KsAddIrpToCancelableQueue
0x180006302  mov     rax, [r14]
0x180006305  mov     rcx, r14
0x180006308  mov     rax, [rax+30h]
0x18000630c  call    _guard_dispatch_icall
0x180006311  mov     eax, 103h
0x180006316  jmp     loc_180006272
0x18000631b  mov     rax, [r14]
0x18000631e  mov     rcx, r14
0x180006321  mov     rax, [rax+30h]
0x180006325  call    _guard_dispatch_icall
0x18000632a  jmp     loc_180006267
```
