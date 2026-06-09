# CdpClientClose

- ea: `0x14000ae70`
- end: `0x14000afc8`
- name: `CdpClientClose`
- size: `344`
- prototype: `__int64 __fastcall(PVOID P, PIRP Irp)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a5e0`
- `0x14000ae70`
- `0x14000afd0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000afab`
- `ntoskrnl!IoFreeIrp` at `0x14000afab`
- `ntoskrnl!IoAllocateIrp` at `0x14000aea7`
- `ntoskrnl!IoAllocateIrp` at `0x14000aea7`
- `ntoskrnl!IofCompleteRequest` at `0x14000af48`
- `ntoskrnl!IofCompleteRequest` at `0x14000af84`
- `ntoskrnl!IofCompleteRequest` at `0x14000af48`
- `ntoskrnl!IofCompleteRequest` at `0x14000af84`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000af0f`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000af0f`

## pseudocode

```c
__int64 __fastcall CdpClientClose(struct _UNICODE_STRING **P, PIRP Irp)
{
  PIRP v4; // rax
  PIRP v5; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v7; // rcx
  struct _UNICODE_STRING *v8; // rdx
  __int64 v9; // rax
  int v10; // r14d

  if ( ((_DWORD)P[4] & 2) == 0 )
  {
    CdpFreeClient(P);
    Irp->IoStatus.Status = 0;
    Irp->IoStatus.Information = 0;
    IofCompleteRequest(Irp, 0);
    return 0;
  }
  v4 = IoAllocateIrp(*(_BYTE *)(CdDeviceObject + 76), 0);
  v5 = v4;
  if ( v4 )
  {
    CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CdCompleteRoutineFreeIrp;
    CurrentStackLocation[-1].Context = 0;
    CurrentStackLocation[-1].Control = -32;
  }
  else
  {
    v5 = Irp;
  }
  v7 = v5->Tail.Overlay.CurrentStackLocation;
  v8 = P[2];
  v9 = (__int64)&P[1][4];
  *(_WORD *)&v7[-1].MajorFunction = 1039;
  v7[-1].Parameters.WMI.ProviderId = v9;
  v7[-1].Parameters.QueryDirectory.FileName = v8;
  v7[-1].Parameters.Read.ByteOffset.QuadPart = 0;
  v7[-1].Parameters.CreatePipe.Parameters = 0;
  v5->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
  ZwAllocateLocallyUniqueId((PLUID)&v5->Tail.CompletionKey + 2);
  v10 = CdAddIoToPipe((__int64)v5);
  CdpFreeClient(P);
  if ( v5 == Irp )
  {
    if ( v10 >= 0 )
      return 259;
  }
  else if ( v10 < 0 )
  {
    IoFreeIrp(v5);
  }
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x14000ae70  mov     [rsp+arg_10], rbx
0x14000ae75  mov     [rsp+arg_18], rsi
0x14000ae7a  push    rdi
0x14000ae7b  sub     rsp, 20h
0x14000ae7f  mov     eax, [rcx+20h]
0x14000ae82  mov     rbx, rdx
0x14000ae85  mov     rdi, rcx
0x14000ae88  test    al, 2
0x14000ae8a  jz      loc_14000AF71
0x14000ae90  mov     rcx, cs:CdDeviceObject
0x14000ae97  xor     edx, edx; ChargeQuota
0x14000ae99  mov     [rsp+28h+arg_0], rbp
0x14000ae9e  mov     [rsp+28h+arg_8], r14
0x14000aea3  movzx   ecx, byte ptr [rcx+4Ch]; StackSize
0x14000aea7  call    cs:__imp_IoAllocateIrp
0x14000aeae  nop     dword ptr [rax+rax+00h]
0x14000aeb3  xor     esi, esi
0x14000aeb5  mov     rbp, rax
0x14000aeb8  test    rax, rax
0x14000aebb  jz      loc_14000AFB9
0x14000aec1  mov     rax, [rax+0B8h]
0x14000aec8  lea     rcx, CdCompleteRoutineFreeIrp
0x14000aecf  mov     [rax-10h], rcx
0x14000aed3  mov     [rax-8], rsi
0x14000aed7  mov     byte ptr [rax-45h], 0E0h
0x14000aedb  mov     rcx, [rbp+0B8h]
0x14000aee2  mov     rax, [rdi+8]
0x14000aee6  mov     rdx, [rdi+10h]
0x14000aeea  add     rax, 40h ; '@'
0x14000aeee  mov     word ptr [rcx-48h], 40Fh
0x14000aef4  mov     [rcx-40h], rax
0x14000aef8  mov     [rcx-38h], rdx
0x14000aefc  mov     [rcx-30h], rsi
0x14000af00  mov     [rcx-28h], rsi
0x14000af04  lea     rcx, [rbp+88h]; Luid
0x14000af0b  mov     [rbp+78h], rsi
0x14000af0f  call    cs:__imp_ZwAllocateLocallyUniqueId
0x14000af16  nop     dword ptr [rax+rax+00h]
0x14000af1b  mov     rcx, rbp
0x14000af1e  call    CdAddIoToPipe
0x14000af23  mov     rcx, rdi; P
0x14000af26  mov     r14d, eax
0x14000af29  call    CdpFreeClient
0x14000af2e  cmp     rbp, rbx
0x14000af31  jnz     short loc_14000AFA3
0x14000af33  test    r14d, r14d
0x14000af36  jns     loc_14000AFC1
0x14000af3c  xor     edx, edx; PriorityBoost
0x14000af3e  mov     [rbx+30h], esi
0x14000af41  mov     rcx, rbx; Irp
0x14000af44  mov     [rbx+38h], rsi
0x14000af48  call    cs:__imp_IofCompleteRequest
0x14000af4f  nop     dword ptr [rax+rax+00h]
0x14000af54  xor     eax, eax
0x14000af56  mov     rbp, [rsp+28h+arg_0]
0x14000af5b  mov     r14, [rsp+28h+arg_8]
0x14000af60  mov     rbx, [rsp+28h+arg_10]
0x14000af65  mov     rsi, [rsp+28h+arg_18]
0x14000af6a  add     rsp, 20h
0x14000af6e  pop     rdi
0x14000af6f  retn
0x14000af71  call    CdpFreeClient
0x14000af76  xor     esi, esi
0x14000af78  xor     edx, edx; PriorityBoost
0x14000af7a  mov     rcx, rbx; Irp
0x14000af7d  mov     [rbx+30h], esi
0x14000af80  mov     [rbx+38h], rsi
0x14000af84  call    cs:__imp_IofCompleteRequest
0x14000af8b  nop     dword ptr [rax+rax+00h]
0x14000af90  mov     rbx, [rsp+28h+arg_10]
0x14000af95  xor     eax, eax
0x14000af97  mov     rsi, [rsp+28h+arg_18]
0x14000af9c  add     rsp, 20h
0x14000afa0  pop     rdi
0x14000afa1  retn
0x14000afa3  test    r14d, r14d
0x14000afa6  jns     short loc_14000AF3C
0x14000afa8  mov     rcx, rbp; Irp
0x14000afab  call    cs:__imp_IoFreeIrp
0x14000afb2  nop     dword ptr [rax+rax+00h]
0x14000afb7  jmp     short loc_14000AF3C
0x14000afb9  mov     rbp, rbx
0x14000afbc  jmp     loc_14000AEDB
0x14000afc1  mov     eax, 103h
0x14000afc6  jmp     short loc_14000AF56
```
