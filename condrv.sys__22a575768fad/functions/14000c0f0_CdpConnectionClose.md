# CdpConnectionClose

- ea: `0x14000c0f0`
- end: `0x14000c2db`
- name: `CdpConnectionClose`
- size: `491`
- prototype: `__int64 __fastcall(PVOID P, PIRP Irp)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a5e0`
- `0x14000bd90`
- `0x14000c0f0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c10d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c10d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c126`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000c126`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c150`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c27a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c150`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000c27a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c15c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c286`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c15c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c286`
- `ntoskrnl!IoFreeIrp` at `0x14000c24f`
- `ntoskrnl!IoFreeIrp` at `0x14000c24f`
- `ntoskrnl!IoAllocateIrp` at `0x14000c17f`
- `ntoskrnl!IoAllocateIrp` at `0x14000c17f`
- `ntoskrnl!IofCompleteRequest` at `0x14000c21e`
- `ntoskrnl!IofCompleteRequest` at `0x14000c29e`
- `ntoskrnl!IofCompleteRequest` at `0x14000c21e`
- `ntoskrnl!IofCompleteRequest` at `0x14000c29e`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000c1e5`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000c1e5`

## pseudocode

```c
__int64 __fastcall CdpConnectionClose(_QWORD *P, PIRP Irp)
{
  __int64 v4; // rax
  PIRP v5; // rax
  PIRP v6; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v8; // rcx
  struct _LIST_ENTRY *v9; // rdx
  __int64 v10; // rax
  int v11; // r14d
  __int64 v13; // rax

  if ( P[3] )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(P[3] + 216LL, 0);
    v4 = P[3];
    if ( *(_QWORD **)(v4 + 224) == P )
    {
      --*(_QWORD *)(v4 + 256);
      v13 = P[3];
      if ( *(_QWORD *)(v13 + 256) )
      {
        ExReleasePushLockSharedEx(v13 + 216, 0);
        KeLeaveCriticalRegion();
        Irp->IoStatus.Status = 0;
        Irp->IoStatus.Information = 0;
        IofCompleteRequest(Irp, 0);
        return 0;
      }
      *(_QWORD *)(v13 + 224) = 0;
    }
    ExReleasePushLockSharedEx(P[3] + 216LL, 0);
    KeLeaveCriticalRegion();
  }
  v5 = IoAllocateIrp(*(_BYTE *)(CdDeviceObject + 76), 0);
  v6 = v5;
  if ( v5 )
  {
    CurrentStackLocation = v5->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&CdCompleteRoutineFreeIrp;
    CurrentStackLocation[-1].Context = 0;
    CurrentStackLocation[-1].Control = -32;
  }
  else
  {
    v6 = Irp;
  }
  v8 = v6->Tail.Overlay.CurrentStackLocation;
  v9 = (struct _LIST_ENTRY *)P[5];
  v10 = P[3] + 64LL;
  *(_WORD *)&v8[-1].MajorFunction = 527;
  v8[-1].Parameters.WMI.ProviderId = v10;
  v8[-1].Parameters.QueryDirectory.FileName = 0;
  v8[-1].Parameters.Read.ByteOffset.QuadPart = 0;
  v8[-1].Parameters.CreatePipe.Parameters = 0;
  v6->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = v9;
  ZwAllocateLocallyUniqueId((PLUID)&v6->Tail.CompletionKey + 2);
  v11 = CdAddIoToPipe((__int64)v6);
  CdpFreeConnection(P);
  if ( v6 == Irp )
  {
    if ( v11 >= 0 )
      return 259;
  }
  else if ( v11 < 0 )
  {
    IoFreeIrp(v6);
  }
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  IofCompleteRequest(Irp, 0);
  return 0;
}

```

## disassembly

```asm
0x14000c0f0  mov     [rsp+arg_10], rbx
0x14000c0f5  mov     [rsp+arg_18], rsi
0x14000c0fa  push    rdi
0x14000c0fb  sub     rsp, 20h
0x14000c0ff  xor     edi, edi
0x14000c101  mov     rsi, rdx
0x14000c104  mov     rbx, rcx
0x14000c107  cmp     [rcx+18h], rdi
0x14000c10b  jz      short loc_14000C168
0x14000c10d  call    cs:__imp_KeEnterCriticalRegion
0x14000c114  nop     dword ptr [rax+rax+00h]
0x14000c119  mov     rcx, [rbx+18h]
0x14000c11d  xor     edx, edx
0x14000c11f  add     rcx, 0D8h
0x14000c126  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000c12d  nop     dword ptr [rax+rax+00h]
0x14000c132  mov     rax, [rbx+18h]
0x14000c136  cmp     [rax+0E0h], rbx
0x14000c13d  jz      loc_14000C25D
0x14000c143  mov     rcx, [rbx+18h]
0x14000c147  xor     edx, edx
0x14000c149  add     rcx, 0D8h
0x14000c150  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c157  nop     dword ptr [rax+rax+00h]
0x14000c15c  call    cs:__imp_KeLeaveCriticalRegion
0x14000c163  nop     dword ptr [rax+rax+00h]
0x14000c168  mov     rcx, cs:CdDeviceObject
0x14000c16f  xor     edx, edx; ChargeQuota
0x14000c171  mov     [rsp+28h+arg_0], rbp
0x14000c176  mov     [rsp+28h+arg_8], r14
0x14000c17b  movzx   ecx, byte ptr [rcx+4Ch]; StackSize
0x14000c17f  call    cs:__imp_IoAllocateIrp
0x14000c186  nop     dword ptr [rax+rax+00h]
0x14000c18b  mov     rbp, rax
0x14000c18e  test    rax, rax
0x14000c191  jz      loc_14000C2BD
0x14000c197  mov     rax, [rax+0B8h]
0x14000c19e  lea     rcx, CdCompleteRoutineFreeIrp
0x14000c1a5  mov     [rax-10h], rcx
0x14000c1a9  mov     [rax-8], rdi
0x14000c1ad  mov     byte ptr [rax-45h], 0E0h
0x14000c1b1  mov     rcx, [rbp+0B8h]
0x14000c1b8  mov     rax, [rbx+18h]
0x14000c1bc  mov     rdx, [rbx+28h]
0x14000c1c0  add     rax, 40h ; '@'
0x14000c1c4  mov     word ptr [rcx-48h], 20Fh
0x14000c1ca  mov     [rcx-40h], rax
0x14000c1ce  mov     [rcx-38h], rdi
0x14000c1d2  mov     [rcx-30h], rdi
0x14000c1d6  mov     [rcx-28h], rdi
0x14000c1da  lea     rcx, [rbp+88h]; Luid
0x14000c1e1  mov     [rbp+78h], rdx
0x14000c1e5  call    cs:__imp_ZwAllocateLocallyUniqueId
0x14000c1ec  nop     dword ptr [rax+rax+00h]
0x14000c1f1  mov     rcx, rbp
0x14000c1f4  call    CdAddIoToPipe
0x14000c1f9  mov     rcx, rbx; P
0x14000c1fc  mov     r14d, eax
0x14000c1ff  call    CdpFreeConnection
0x14000c204  cmp     rbp, rsi
0x14000c207  jnz     short loc_14000C247
0x14000c209  test    r14d, r14d
0x14000c20c  jns     loc_14000C2C5
0x14000c212  xor     edx, edx; PriorityBoost
0x14000c214  mov     [rsi+30h], edi
0x14000c217  mov     rcx, rsi; Irp
0x14000c21a  mov     [rsi+38h], rdi
0x14000c21e  call    cs:__imp_IofCompleteRequest
0x14000c225  nop     dword ptr [rax+rax+00h]
0x14000c22a  xor     eax, eax
0x14000c22c  mov     rbp, [rsp+28h+arg_0]
0x14000c231  mov     r14, [rsp+28h+arg_8]
0x14000c236  mov     rbx, [rsp+28h+arg_10]
0x14000c23b  mov     rsi, [rsp+28h+arg_18]
0x14000c240  add     rsp, 20h
0x14000c244  pop     rdi
0x14000c245  retn
0x14000c247  test    r14d, r14d
0x14000c24a  jns     short loc_14000C212
0x14000c24c  mov     rcx, rbp; Irp
0x14000c24f  call    cs:__imp_IoFreeIrp
0x14000c256  nop     dword ptr [rax+rax+00h]
0x14000c25b  jmp     short loc_14000C212
0x14000c25d  dec     qword ptr [rax+100h]
0x14000c264  mov     rax, [rbx+18h]
0x14000c268  cmp     [rax+100h], rdi
0x14000c26f  jbe     short loc_14000C2CF
0x14000c271  lea     rcx, [rax+0D8h]
0x14000c278  xor     edx, edx
0x14000c27a  call    cs:__imp_ExReleasePushLockSharedEx
0x14000c281  nop     dword ptr [rax+rax+00h]
0x14000c286  call    cs:__imp_KeLeaveCriticalRegion
0x14000c28d  nop     dword ptr [rax+rax+00h]
0x14000c292  xor     edx, edx; PriorityBoost
0x14000c294  mov     [rsi+30h], edi
0x14000c297  mov     rcx, rsi; Irp
0x14000c29a  mov     [rsi+38h], rdi
0x14000c29e  call    cs:__imp_IofCompleteRequest
0x14000c2a5  nop     dword ptr [rax+rax+00h]
0x14000c2aa  mov     rbx, [rsp+28h+arg_10]
0x14000c2af  xor     eax, eax
0x14000c2b1  mov     rsi, [rsp+28h+arg_18]
0x14000c2b6  add     rsp, 20h
0x14000c2ba  pop     rdi
0x14000c2bb  retn
0x14000c2bd  mov     rbp, rsi
0x14000c2c0  jmp     loc_14000C1B1
0x14000c2c5  mov     eax, 103h
0x14000c2ca  jmp     loc_14000C22C
0x14000c2cf  mov     [rax+0E0h], rdi
0x14000c2d6  jmp     loc_14000C143
```
