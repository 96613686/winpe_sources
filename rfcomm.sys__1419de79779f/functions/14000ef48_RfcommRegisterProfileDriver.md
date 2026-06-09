# RfcommRegisterProfileDriver

- ea: `0x14000ef48`
- end: `0x14000f0b7`
- name: `RfcommRegisterProfileDriver`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400035cc`

## callees

- `0x14000ef48`
- `0x14001fd40`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000f025`
- `ntoskrnl!IofCallDriver` at `0x14000f025`
- `ntoskrnl!KeInitializeEvent` at `0x14000ef95`
- `ntoskrnl!KeInitializeEvent` at `0x14000ef95`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f047`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f047`
- `ntoskrnl!IoFreeIrp` at `0x14000f093`
- `ntoskrnl!IoFreeIrp` at `0x14000f093`
- `ntoskrnl!IoAllocateIrp` at `0x14000efaa`
- `ntoskrnl!IoAllocateIrp` at `0x14000efaa`

## pseudocode

```c
__int64 __fastcall RfcommRegisterProfileDriver(__int64 a1)
{
  unsigned int Status; // ebx
  PIRP Irp; // rax
  IRP *v4; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v6; // rax
  struct _KEVENT Event; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v9[9]; // [rsp+50h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( a1 )
  {
    memset(v9, 0, sizeof(v9));
    KeInitializeEvent(&Event, NotificationEvent, 0);
    Irp = IoAllocateIrp(*(_BYTE *)(*(_QWORD *)(a1 + 88) + 76LL), 0);
    v4 = Irp;
    if ( Irp )
    {
      CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation[-1].Parameters.WMI.ProviderId = (unsigned __int64)&GUID_BTHDDI_PROFILE_DRIVER_INTERFACE;
      CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = (__int64)v9;
      *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 2075;
      CurrentStackLocation[-1].Parameters.Create.Options = 33554504;
      CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = 0;
      v6 = v4->Tail.Overlay.CurrentStackLocation;
      v6[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))&ForwardAndWaitComplete;
      v6[-1].Context = &Event;
      v6[-1].Control = -32;
      v4->IoStatus.Status = -1073741637;
      IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 88), v4);
      if ( KeWaitForSingleObject(&Event, Executive, 0, 0, 0) >= 0 )
      {
        *(_QWORD *)(a1 + 312) = v9[4];
        *(_QWORD *)(a1 + 320) = v9[5];
        *(_QWORD *)(a1 + 328) = v9[6];
        *(_QWORD *)(a1 + 336) = v9[8];
      }
      Status = v4->IoStatus.Status;
      IoFreeIrp(v4);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return Status;
}

```

## disassembly

```asm
0x14000ef48  mov     [rsp+arg_0], rbx
0x14000ef4d  mov     [rsp+arg_8], rsi
0x14000ef52  push    rdi
0x14000ef53  sub     rsp, 0A0h
0x14000ef5a  xor     eax, eax
0x14000ef5c  xorps   xmm0, xmm0
0x14000ef5f  mov     [rsp+0A8h+Event.Header.WaitListHead.Blink], rax
0x14000ef64  mov     rbx, rcx
0x14000ef67  movups  xmmword ptr [rsp+0A8h+Event.Header.___u0], xmm0
0x14000ef6c  test    rcx, rcx
0x14000ef6f  jnz     short loc_14000EF7B
0x14000ef71  mov     ebx, 0C000000Dh
0x14000ef76  jmp     loc_14000F09F
0x14000ef7b  xor     edx, edx; Val
0x14000ef7d  lea     rcx, [rsp+0A8h+var_58]; void *
0x14000ef82  lea     r8d, [rdx+48h]; Size
0x14000ef86  call    memset
0x14000ef8b  xor     r8d, r8d; State
0x14000ef8e  lea     rcx, [rsp+0A8h+Event]; Event
0x14000ef93  xor     edx, edx; Type
0x14000ef95  call    cs:__imp_KeInitializeEvent
0x14000ef9c  nop     dword ptr [rax+rax+00h]
0x14000efa1  mov     rcx, [rbx+58h]
0x14000efa5  xor     edx, edx; ChargeQuota
0x14000efa7  mov     cl, [rcx+4Ch]; StackSize
0x14000efaa  call    cs:__imp_IoAllocateIrp
0x14000efb1  nop     dword ptr [rax+rax+00h]
0x14000efb6  mov     rdi, rax
0x14000efb9  test    rax, rax
0x14000efbc  jnz     short loc_14000EFC8
0x14000efbe  mov     ebx, 0C000009Ah
0x14000efc3  jmp     loc_14000F09F
0x14000efc8  mov     rax, [rax+0B8h]
0x14000efcf  lea     rcx, GUID_BTHDDI_PROFILE_DRIVER_INTERFACE
0x14000efd6  mov     rdx, rdi; Irp
0x14000efd9  mov     [rax-40h], rcx
0x14000efdd  lea     rcx, [rsp+0A8h+var_58]
0x14000efe2  mov     [rax-30h], rcx
0x14000efe6  lea     rcx, ForwardAndWaitComplete
0x14000efed  mov     word ptr [rax-48h], 81Bh
0x14000eff3  mov     dword ptr [rax-38h], 2000048h
0x14000effa  mov     qword ptr [rax-28h], 0
0x14000f002  mov     rax, [rdi+0B8h]
0x14000f009  mov     [rax-10h], rcx
0x14000f00d  lea     rcx, [rsp+0A8h+Event]
0x14000f012  mov     [rax-8], rcx
0x14000f016  mov     byte ptr [rax-45h], 0E0h
0x14000f01a  mov     dword ptr [rdi+30h], 0C00000BBh
0x14000f021  mov     rcx, [rbx+58h]; DeviceObject
0x14000f025  call    cs:__imp_IofCallDriver
0x14000f02c  nop     dword ptr [rax+rax+00h]
0x14000f031  xor     r9d, r9d; Alertable
0x14000f034  mov     [rsp+0A8h+Timeout], 0; Timeout
0x14000f03d  xor     r8d, r8d; WaitMode
0x14000f040  lea     rcx, [rsp+0A8h+Event]; Object
0x14000f045  xor     edx, edx; WaitReason
0x14000f047  call    cs:__imp_KeWaitForSingleObject
0x14000f04e  nop     dword ptr [rax+rax+00h]
0x14000f053  test    eax, eax
0x14000f055  js      short loc_14000F08D
0x14000f057  mov     rax, [rsp+0A8h+var_38]
0x14000f05c  mov     [rbx+138h], rax
0x14000f063  mov     rax, [rsp+0A8h+var_30]
0x14000f068  mov     [rbx+140h], rax
0x14000f06f  mov     rax, [rsp+0A8h+var_28]
0x14000f077  mov     [rbx+148h], rax
0x14000f07e  mov     rax, [rsp+0A8h+var_18]
0x14000f086  mov     [rbx+150h], rax
0x14000f08d  mov     ebx, [rdi+30h]
0x14000f090  mov     rcx, rdi; Irp
0x14000f093  call    cs:__imp_IoFreeIrp
0x14000f09a  nop     dword ptr [rax+rax+00h]
0x14000f09f  lea     r11, [rsp+0A8h+var_8]
0x14000f0a7  mov     eax, ebx
0x14000f0a9  mov     rbx, [r11+10h]
0x14000f0ad  mov     rsi, [r11+18h]
0x14000f0b1  mov     rsp, r11
0x14000f0b4  pop     rdi
0x14000f0b5  retn
```
