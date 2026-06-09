# ClassCheckVerifyComplete

- ea: `0x140012e40`
- end: `0x140012f05`
- name: `ClassCheckVerifyComplete`
- size: `197`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005190`
- `0x140012e40`
- `0x1400134a0`
- `0x140026e04`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140012eb6`
- `ntoskrnl!IoFreeIrp` at `0x140012eb6`

## pseudocode

```c
__int64 __fastcall ClassCheckVerifyComplete(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _DWORD *DeviceExtension; // r9
  IRP *SecurityContext; // rbx
  _IRP *MasterIrp; // r8

  DeviceExtension = DeviceObject->DeviceExtension;
  SecurityContext = (IRP *)Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  MasterIrp = SecurityContext->AssociatedIrp.MasterIrp;
  *(_DWORD *)&MasterIrp->Type = DeviceExtension[174];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_dLL(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned int *)SecurityContext->AssociatedIrp.MasterIrp,
      MasterIrp,
      (unsigned int)DeviceExtension[147],
      DeviceExtension[174],
      *(_DWORD *)SecurityContext->AssociatedIrp.MasterIrp);
  }
  SecurityContext->IoStatus.Status = Irp->IoStatus.Status;
  SecurityContext->IoStatus.Information = 4;
  ClassReleaseRemoveLock(DeviceObject, SecurityContext);
  ClassCompleteRequest(DeviceObject, SecurityContext, 1);
  IoFreeIrp(Irp);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140012e40  mov     [rsp+arg_0], rbx
0x140012e45  mov     [rsp+arg_8], rsi
0x140012e4a  push    rdi
0x140012e4b  sub     rsp, 30h
0x140012e4f  mov     rax, [rdx+0B8h]
0x140012e56  mov     rdi, rdx
0x140012e59  mov     r9, [rcx+40h]
0x140012e5d  mov     rsi, rcx
0x140012e60  mov     rbx, [rax+8]
0x140012e64  mov     eax, [r9+2B8h]
0x140012e6b  mov     r8, [rbx+18h]
0x140012e6f  mov     [r8], eax
0x140012e72  mov     rcx, cs:WPP_GLOBAL_Control
0x140012e79  lea     rax, WPP_GLOBAL_Control
0x140012e80  cmp     rcx, rax
0x140012e83  jz      short loc_140012E8C
0x140012e85  mov     eax, [rcx+2Ch]
0x140012e88  test    al, 10h
0x140012e8a  jnz     short loc_140012ED8
0x140012e8c  mov     eax, [rdi+30h]
0x140012e8f  mov     rdx, rbx; Tag
0x140012e92  mov     rcx, rsi; DeviceObject
0x140012e95  mov     [rbx+30h], eax
0x140012e98  mov     qword ptr [rbx+38h], 4
0x140012ea0  call    ClassReleaseRemoveLock
0x140012ea5  mov     r8b, 1; PriorityBoost
0x140012ea8  mov     rdx, rbx; Irp
0x140012eab  mov     rcx, rsi; DeviceObject
0x140012eae  call    ClassCompleteRequest
0x140012eb3  mov     rcx, rdi; Irp
0x140012eb6  call    cs:__imp_IoFreeIrp
0x140012ebd  nop     dword ptr [rax+rax+00h]
0x140012ec2  mov     rbx, [rsp+38h+arg_0]
0x140012ec7  mov     eax, 0C0000016h
0x140012ecc  mov     rsi, [rsp+38h+arg_8]
0x140012ed1  add     rsp, 30h
0x140012ed5  pop     rdi
0x140012ed6  retn
0x140012ed8  cmp     byte ptr [rcx+29h], 4
0x140012edc  jb      short loc_140012E8C
0x140012ede  mov     rax, [rbx+18h]
0x140012ee2  mov     rcx, [rcx+18h]
0x140012ee6  mov     edx, [rax]
0x140012ee8  mov     eax, [r9+2B8h]
0x140012eef  mov     r9d, [r9+24Ch]
0x140012ef6  mov     [rsp+38h+var_10], edx
0x140012efa  mov     [rsp+38h+var_18], eax
0x140012efe  call    WPP_SF_dLL
0x140012f03  jmp     short loc_140012E8C
```
