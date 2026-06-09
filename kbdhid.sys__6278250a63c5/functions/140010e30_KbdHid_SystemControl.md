# KbdHid_SystemControl

- ea: `0x140010e30`
- end: `0x140010ec2`
- name: `KbdHid_SystemControl`
- size: `146`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140010e30`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140010e90`
- `ntoskrnl!IofCallDriver` at `0x140010e90`
- `ntoskrnl!IofCompleteRequest` at `0x140010ea3`
- `ntoskrnl!IofCompleteRequest` at `0x140010ea3`
- `WMILIB!WmiSystemControl` at `0x140010e60`
- `WMILIB!WmiSystemControl` at `0x140010e60`

## pseudocode

```c
NTSTATUS __fastcall KbdHid_SystemControl(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char *DeviceExtension; // rsi
  NTSTATUS result; // eax
  NTSTATUS v5; // ebx
  _SYSCTL_IRP_DISPOSITION IrpDisposition; // [rsp+30h] [rbp+8h] BYREF

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  IrpDisposition = IrpProcessed;
  result = WmiSystemControl((PWMILIB_CONTEXT)(DeviceExtension + 672), DeviceObject, Irp, &IrpDisposition);
  v5 = result;
  if ( IrpDisposition )
  {
    if ( IrpDisposition == IrpNotCompleted )
    {
      IofCompleteRequest(Irp, 0);
      return v5;
    }
    else
    {
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      return IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 1), Irp);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140010e30  mov     [rsp+arg_8], rbx
0x140010e35  mov     [rsp+arg_10], rsi
0x140010e3a  push    rdi
0x140010e3b  sub     rsp, 20h
0x140010e3f  mov     rsi, [rcx+40h]
0x140010e43  lea     r9, [rsp+28h+IrpDisposition]; IrpDisposition
0x140010e48  mov     rdi, rdx
0x140010e4b  mov     [rsp+28h+IrpDisposition], 0
0x140010e53  mov     rdx, rcx; DeviceObject
0x140010e56  mov     r8, rdi; Irp
0x140010e59  lea     rcx, [rsi+2A0h]; WmiLibInfo
0x140010e60  call    cs:__imp_WmiSystemControl
0x140010e67  nop     dword ptr [rax+rax+00h]
0x140010e6c  mov     edx, [rsp+28h+IrpDisposition]
0x140010e70  mov     ebx, eax
0x140010e72  test    edx, edx
0x140010e74  jz      short loc_140010EB1
0x140010e76  sub     edx, 1
0x140010e79  jz      short loc_140010E9E
0x140010e7b  inc     byte ptr [rdi+43h]
0x140010e7e  sub     edx, 1
0x140010e81  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140010e89  mov     rdx, rdi; Irp
0x140010e8c  mov     rcx, [rsi+8]; DeviceObject
0x140010e90  call    cs:__imp_IofCallDriver
0x140010e97  nop     dword ptr [rax+rax+00h]
0x140010e9c  jmp     short loc_140010EB1
0x140010e9e  xor     edx, edx; PriorityBoost
0x140010ea0  mov     rcx, rdi; Irp
0x140010ea3  call    cs:__imp_IofCompleteRequest
0x140010eaa  nop     dword ptr [rax+rax+00h]
0x140010eaf  mov     eax, ebx
0x140010eb1  mov     rbx, [rsp+28h+arg_8]
0x140010eb6  mov     rsi, [rsp+28h+arg_10]
0x140010ebb  add     rsp, 20h
0x140010ebf  pop     rdi
0x140010ec0  retn
```
