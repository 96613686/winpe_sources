# I8xSystemControl

- ea: `0x140020170`
- end: `0x140020202`
- name: `I8xSystemControl`
- size: `146`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140020170`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400201d0`
- `ntoskrnl!IofCallDriver` at `0x1400201d0`
- `ntoskrnl!IofCompleteRequest` at `0x1400201e3`
- `ntoskrnl!IofCompleteRequest` at `0x1400201e3`
- `WMILIB!WmiSystemControl` at `0x1400201a0`
- `WMILIB!WmiSystemControl` at `0x1400201a0`

## pseudocode

```c
NTSTATUS __fastcall I8xSystemControl(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  PVOID DeviceExtension; // rsi
  NTSTATUS result; // eax
  NTSTATUS v5; // ebx
  _SYSCTL_IRP_DISPOSITION IrpDisposition; // [rsp+30h] [rbp+8h] BYREF

  DeviceExtension = DeviceObject->DeviceExtension;
  IrpDisposition = IrpProcessed;
  result = WmiSystemControl((PWMILIB_CONTEXT)DeviceExtension + 7, DeviceObject, Irp, &IrpDisposition);
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
      return IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 3), Irp);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140020170  mov     [rsp+arg_8], rbx
0x140020175  mov     [rsp+arg_10], rsi
0x14002017a  push    rdi
0x14002017b  sub     rsp, 20h
0x14002017f  mov     rsi, [rcx+40h]
0x140020183  lea     r9, [rsp+28h+IrpDisposition]; IrpDisposition
0x140020188  mov     rdi, rdx
0x14002018b  mov     [rsp+28h+IrpDisposition], 0
0x140020193  mov     rdx, rcx; DeviceObject
0x140020196  mov     r8, rdi; Irp
0x140020199  lea     rcx, [rsi+1C0h]; WmiLibInfo
0x1400201a0  call    cs:__imp_WmiSystemControl
0x1400201a7  nop     dword ptr [rax+rax+00h]
0x1400201ac  mov     edx, [rsp+28h+IrpDisposition]
0x1400201b0  mov     ebx, eax
0x1400201b2  test    edx, edx
0x1400201b4  jz      short loc_1400201F1
0x1400201b6  sub     edx, 1
0x1400201b9  jz      short loc_1400201DE
0x1400201bb  inc     byte ptr [rdi+43h]
0x1400201be  sub     edx, 1
0x1400201c1  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x1400201c9  mov     rdx, rdi; Irp
0x1400201cc  mov     rcx, [rsi+18h]; DeviceObject
0x1400201d0  call    cs:__imp_IofCallDriver
0x1400201d7  nop     dword ptr [rax+rax+00h]
0x1400201dc  jmp     short loc_1400201F1
0x1400201de  xor     edx, edx; PriorityBoost
0x1400201e0  mov     rcx, rdi; Irp
0x1400201e3  call    cs:__imp_IofCompleteRequest
0x1400201ea  nop     dword ptr [rax+rax+00h]
0x1400201ef  mov     eax, ebx
0x1400201f1  mov     rbx, [rsp+28h+arg_8]
0x1400201f6  mov     rsi, [rsp+28h+arg_10]
0x1400201fb  add     rsp, 20h
0x1400201ff  pop     rdi
0x140020200  retn
```
