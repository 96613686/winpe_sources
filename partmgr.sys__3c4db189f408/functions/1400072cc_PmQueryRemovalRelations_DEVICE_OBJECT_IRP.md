# PmQueryRemovalRelations(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1400072cc`
- end: `0x140007434`
- name: `?PmQueryRemovalRelations@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `360`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140022800`

## callees

- `0x1400072cc`
- `0x14000a014`
- `0x14000c14c`
- `0x14000c1b8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000739c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000739c`
- `ntoskrnl!IofCallDriver` at `0x1400073df`
- `ntoskrnl!IofCallDriver` at `0x1400073df`
- `ntoskrnl!IofCompleteRequest` at `0x1400073f7`
- `ntoskrnl!IofCompleteRequest` at `0x1400073f7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007374`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007374`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007307`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007307`

## pseudocode

```c
__int64 __fastcall PmQueryRemovalRelations(struct _DEVICE_OBJECT *a1, struct _IRP *a2, __int64 a3)
{
  unsigned int *DeviceExtension; // rsi
  NTSTATUS Status; // edi
  struct _LIST_ENTRY *v6; // rbp
  int v7; // r8d
  KIRQL v8; // r15
  struct _LIST_ENTRY *v9; // rcx
  int v10; // edx
  int v11; // ecx
  int v12; // r8d
  __int64 v13; // rcx
  __int64 v14; // r8

  DeviceExtension = (unsigned int *)a1->DeviceExtension;
  Status = 0;
  if ( (Microsoft_Windows_PartitionEnableBits & 4) != 0 )
    McTemplateK0qp_EtwWriteTransfer(a1, QueryRemovalRelationsEnter, a3, DeviceExtension[42], a2);
  v6 = (struct _LIST_ENTRY *)(DeviceExtension + 168);
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)DeviceExtension + 14);
  if ( v6->Flink != v6
    || (DeviceExtension[129] |= 0x800000u,
        Status = PmQueueNotificationWorkItem((struct _DEVICE_EXTENSION *)DeviceExtension, "PmQueryRemovalRelations", v7),
        Status >= 0) )
  {
    v9 = (struct _LIST_ENTRY *)*((_QWORD *)DeviceExtension + 85);
    if ( v9->Flink != v6 )
      __fastfail(3u);
    a2->Tail.Overlay.ListEntry.Flink = v6;
    a2->Tail.Overlay.ListEntry.Blink = v9;
    v9->Flink = &a2->Tail.Overlay.ListEntry;
    *((_QWORD *)DeviceExtension + 85) = &a2->Tail.Overlay.ListEntry;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)DeviceExtension + 14, v8);
  if ( Status < 0 )
    goto LABEL_13;
  KeWaitForSingleObject(DeviceExtension + 206, Executive, 0, 0, 0);
  Status = a2->IoStatus.Status;
  if ( (Microsoft_Windows_PartitionEnableBits & 4) != 0 )
    McTemplateK0qpd_EtwWriteTransfer(v11, v10, v12, DeviceExtension[42], (char)a2, a2->IoStatus.Status);
  if ( Status < 0 )
  {
LABEL_13:
    a2->IoStatus.Status = Status;
    IofCompleteRequest(a2, 0);
  }
  else
  {
    ++a2->CurrentLocation;
    ++a2->Tail.Overlay.CurrentStackLocation;
    Status = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
  }
  if ( (Microsoft_Windows_PartitionEnableBits & 4) != 0 )
    McTemplateK0qp_EtwWriteTransfer(v13, QueryRemovalRelationsExit, v14, DeviceExtension[42], a2);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400072cc  push    rbx
0x1400072ce  push    rbp
0x1400072cf  push    rsi
0x1400072d0  push    rdi
0x1400072d1  push    r14
0x1400072d3  push    r15
0x1400072d5  sub     rsp, 38h
0x1400072d9  mov     rsi, [rcx+40h]
0x1400072dd  xor     edi, edi
0x1400072df  test    cs:Microsoft_Windows_PartitionEnableBits, 4
0x1400072e6  mov     rbx, rdx
0x1400072e9  jz      short loc_140007303
0x1400072eb  mov     r9d, [rsi+0A8h]
0x1400072f2  mov     [rsp+68h+Timeout], rdx
0x1400072f7  lea     rdx, QueryRemovalRelationsEnter
0x1400072fe  call    McTemplateK0qp_EtwWriteTransfer
0x140007303  lea     rcx, [rsi+70h]; SpinLock
0x140007307  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000730e  nop     dword ptr [rax+rax+00h]
0x140007313  lea     rbp, [rsi+2A0h]
0x14000731a  mov     r15b, al
0x14000731d  cmp     [rbp+0], rbp
0x140007321  jnz     short loc_140007348
0x140007323  mov     eax, [rsi+204h]
0x140007329  lea     rdx, aPmqueryremoval; "PmQueryRemovalRelations"
0x140007330  bts     eax, 17h
0x140007334  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x140007337  mov     [rsi+204h], eax
0x14000733d  call    ?PmQueueNotificationWorkItem@@YAJPEAU_DEVICE_EXTENSION@@PEBD@Z; PmQueueNotificationWorkItem(_DEVICE_EXTENSION *,char const *)
0x140007342  mov     edi, eax
0x140007344  test    eax, eax
0x140007346  js      short loc_14000736D
0x140007348  mov     rcx, [rbp+8]
0x14000734c  cmp     [rcx], rbp
0x14000734f  jz      short loc_140007358
0x140007351  mov     ecx, 3
0x140007356  int     29h; Win8: RtlFailFast(ecx)
0x140007358  lea     rax, [rbx+0A8h]
0x14000735f  mov     [rax], rbp
0x140007362  mov     [rax+8], rcx
0x140007366  mov     [rcx], rax
0x140007369  mov     [rbp+8], rax
0x14000736d  mov     dl, r15b; NewIrql
0x140007370  lea     rcx, [rsi+70h]; SpinLock
0x140007374  call    cs:__imp_KeReleaseSpinLock
0x14000737b  nop     dword ptr [rax+rax+00h]
0x140007380  test    edi, edi
0x140007382  js      short loc_1400073EF
0x140007384  lea     rcx, [rsi+338h]; Object
0x14000738b  mov     [rsp+68h+Timeout], 0; Timeout
0x140007394  xor     r9d, r9d; Alertable
0x140007397  xor     r8d, r8d; WaitMode
0x14000739a  xor     edx, edx; WaitReason
0x14000739c  call    cs:__imp_KeWaitForSingleObject
0x1400073a3  nop     dword ptr [rax+rax+00h]
0x1400073a8  test    cs:Microsoft_Windows_PartitionEnableBits, 4
0x1400073af  mov     edi, [rbx+30h]
0x1400073b2  jz      short loc_1400073C9
0x1400073b4  mov     r9d, [rsi+0A8h]
0x1400073bb  mov     [rsp+68h+var_40], edi
0x1400073bf  mov     [rsp+68h+Timeout], rbx
0x1400073c4  call    McTemplateK0qpd_EtwWriteTransfer
0x1400073c9  test    edi, edi
0x1400073cb  js      short loc_1400073EF
0x1400073cd  inc     byte ptr [rbx+43h]
0x1400073d0  mov     rdx, rbx; Irp
0x1400073d3  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x1400073db  mov     rcx, [rsi+10h]; DeviceObject
0x1400073df  call    cs:__imp_IofCallDriver
0x1400073e6  nop     dword ptr [rax+rax+00h]
0x1400073eb  mov     edi, eax
0x1400073ed  jmp     short loc_140007403
0x1400073ef  xor     edx, edx; PriorityBoost
0x1400073f1  mov     [rbx+30h], edi
0x1400073f4  mov     rcx, rbx; Irp
0x1400073f7  call    cs:__imp_IofCompleteRequest
0x1400073fe  nop     dword ptr [rax+rax+00h]
0x140007403  test    cs:Microsoft_Windows_PartitionEnableBits, 4
0x14000740a  jz      short loc_140007424
0x14000740c  mov     r9d, [rsi+0A8h]
0x140007413  lea     rdx, QueryRemovalRelationsExit
0x14000741a  mov     [rsp+68h+Timeout], rbx
0x14000741f  call    McTemplateK0qp_EtwWriteTransfer
0x140007424  mov     eax, edi
0x140007426  add     rsp, 38h
0x14000742a  pop     r15
0x14000742c  pop     r14
0x14000742e  pop     rdi
0x14000742f  pop     rsi
0x140007430  pop     rbp
0x140007431  pop     rbx
0x140007432  retn
```
