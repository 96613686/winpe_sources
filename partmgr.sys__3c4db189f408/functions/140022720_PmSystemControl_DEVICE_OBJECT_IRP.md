# PmSystemControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140022720`
- end: `0x1400227f9`
- name: `?PmSystemControl@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140022720`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14002279d`
- `ntoskrnl!IofCallDriver` at `0x14002279d`
- `ntoskrnl!IofCompleteRequest` at `0x1400227e8`
- `ntoskrnl!IofCompleteRequest` at `0x1400227e8`
- `WMILIB!WmiSystemControl` at `0x14002275d`
- `WMILIB!WmiSystemControl` at `0x14002275d`

## pseudocode

```c
NTSTATUS __fastcall PmSystemControl(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char *DeviceExtension; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  NTSTATUS v5; // edi
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rax
  _SYSCTL_IRP_DISPOSITION IrpDisposition; // [rsp+30h] [rbp+8h] BYREF

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  IrpDisposition = IrpForward;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->MinorFunction == 13 )
  {
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 16 )
    {
      Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
      if ( Parameters->NamedPipeType == 1 )
      {
        v5 = 0;
        *((_QWORD *)DeviceExtension + 89) = *(_QWORD *)&Parameters->CompletionMode;
      }
      else
      {
        v5 = -1073741637;
      }
    }
    else
    {
      v5 = -1073741820;
    }
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v5;
    goto LABEL_9;
  }
  v5 = WmiSystemControl((PWMILIB_CONTEXT)(DeviceExtension + 728), DeviceObject, Irp, &IrpDisposition);
  if ( IrpDisposition == IrpProcessed )
    return v5;
  if ( IrpDisposition == IrpNotCompleted )
  {
LABEL_9:
    IofCompleteRequest(Irp, 0);
    return v5;
  }
  ++Irp->CurrentLocation;
  ++Irp->Tail.Overlay.CurrentStackLocation;
  return IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), Irp);
}

```

## disassembly

```asm
0x140022720  mov     [rsp+arg_8], rbx
0x140022725  mov     [rsp+arg_10], rsi
0x14002272a  push    rdi
0x14002272b  sub     rsp, 20h
0x14002272f  mov     rsi, [rcx+40h]
0x140022733  mov     rbx, rdx
0x140022736  mov     [rsp+28h+IrpDisposition], 3
0x14002273e  mov     rdx, rcx; DeviceObject
0x140022741  mov     rax, [rbx+0B8h]
0x140022748  cmp     byte ptr [rax+1], 0Dh
0x14002274c  jz      short loc_1400227BA
0x14002274e  lea     rcx, [rsi+2D8h]; WmiLibInfo
0x140022755  mov     r8, rbx; Irp
0x140022758  lea     r9, [rsp+28h+IrpDisposition]; IrpDisposition
0x14002275d  call    cs:__imp_WmiSystemControl
0x140022764  nop     dword ptr [rax+rax+00h]
0x140022769  mov     edi, eax
0x14002276b  mov     eax, [rsp+28h+IrpDisposition]
0x14002276f  test    eax, eax
0x140022771  jnz     short loc_140022786
0x140022773  mov     eax, edi
0x140022775  mov     rbx, [rsp+28h+arg_8]
0x14002277a  mov     rsi, [rsp+28h+arg_10]
0x14002277f  add     rsp, 20h
0x140022783  pop     rdi
0x140022784  retn
0x140022786  cmp     eax, 1
0x140022789  jz      short loc_1400227E3
0x14002278b  inc     byte ptr [rbx+43h]
0x14002278e  mov     rdx, rbx; Irp
0x140022791  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x140022799  mov     rcx, [rsi+10h]; DeviceObject
0x14002279d  call    cs:__imp_IofCallDriver
0x1400227a4  nop     dword ptr [rax+rax+00h]
0x1400227a9  mov     rbx, [rsp+28h+arg_8]
0x1400227ae  mov     rsi, [rsp+28h+arg_10]
0x1400227b3  add     rsp, 20h
0x1400227b7  pop     rdi
0x1400227b8  retn
0x1400227ba  cmp     dword ptr [rax+18h], 10h
0x1400227be  jnz     loc_140028153
0x1400227c4  mov     rax, [rax+20h]
0x1400227c8  cmp     dword ptr [rax], 1
0x1400227cb  jnz     loc_14002814C
0x1400227d1  mov     rax, [rax+8]
0x1400227d5  xor     edi, edi
0x1400227d7  mov     [rsi+2C8h], rax
0x1400227de  jmp     loc_140028158
0x1400227e3  xor     edx, edx; PriorityBoost
0x1400227e5  mov     rcx, rbx; Irp
0x1400227e8  call    cs:__imp_IofCompleteRequest
0x1400227ef  nop     dword ptr [rax+rax+00h]
0x1400227f4  jmp     loc_140022773
0x14002814c  mov     edi, 0C00000BBh
0x140028151  jmp     short loc_140028158
0x140028153  mov     edi, 0C0000004h
0x140028158  mov     qword ptr [rbx+38h], 0
0x140028160  mov     [rbx+30h], edi
0x140028163  jmp     loc_1400227E3
```
