# PartitionIoctlQueryProperty(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140023ecc`
- end: `0x140023f31`
- name: `?PartitionIoctlQueryProperty@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `101`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140003110`

## callees

- `0x1400030a0`
- `0x140005a84`
- `0x14001c08c`
- `0x140023ecc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400281bc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400281bc`
- `ntoskrnl!IofCompleteRequest` at `0x140023f09`
- `ntoskrnl!IofCompleteRequest` at `0x140023f09`
- `ntoskrnl!KeReleaseMutex` at `0x140028226`
- `ntoskrnl!KeReleaseMutex` at `0x140028226`

## pseudocode

```c
__int64 __fastcall PartitionIoctlQueryProperty(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  struct _PARTITION_EXTENSION *DeviceExtension; // rbp
  NTSTATUS v5; // edi
  struct _IRP *MasterIrp; // rsi
  char v8; // r10
  unsigned __int64 v9; // rax
  __int64 v10; // r8

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->Parameters.Create.Options < 0xC )
  {
    v5 = -1073741820;
  }
  else
  {
    if ( *(_DWORD *)a2->AssociatedIrp.MasterIrp != 11 )
      return (unsigned int)PartitionPassThrough(a1, a2);
    DeviceExtension = (struct _PARTITION_EXTENSION *)a1->DeviceExtension;
    v5 = PartitionForwardIrpSynchronously(a1, a2);
    if ( v5 >= 0 && CurrentStackLocation->Parameters.Read.Length >= 0x28 )
    {
      MasterIrp = a2->AssociatedIrp.MasterIrp;
      if ( *(_QWORD *)&MasterIrp->Flags )
      {
        KeWaitForSingleObject((PVOID)(*((_QWORD *)DeviceExtension + 3) + 56LL), Executive, 0, 0, 0);
        PartitionOffset(DeviceExtension, 1u);
        PartitionOffset(DeviceExtension, 1u);
        LOBYTE(MasterIrp->MdlAddress) = v8 | 0x20;
        v9 = PartitionOffset(DeviceExtension, 1u);
        MasterIrp->AssociatedIrp.MasterIrp = (struct _IRP *)(v10 - v9);
        KeReleaseMutex((PRKMUTEX)(*((_QWORD *)DeviceExtension + 3) + 56LL), 0);
      }
    }
  }
  a2->IoStatus.Status = v5;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140023ecc  push    rbx
0x140023ece  push    rbp
0x140023ecf  push    rsi
0x140023ed0  push    rdi
0x140023ed1  sub     rsp, 38h
0x140023ed5  mov     rsi, [rdx+0B8h]
0x140023edc  mov     rbx, rdx
0x140023edf  cmp     dword ptr [rsi+10h], 0Ch
0x140023ee3  jb      short loc_140023F21
0x140023ee5  mov     rax, [rdx+18h]
0x140023ee9  cmp     dword ptr [rax], 0Bh
0x140023eec  jnz     short loc_140023F28
0x140023eee  mov     rbp, [rcx+40h]
0x140023ef2  call    ?PartitionForwardIrpSynchronously@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionForwardIrpSynchronously(_DEVICE_OBJECT *,_IRP *)
0x140023ef7  mov     edi, eax
0x140023ef9  test    eax, eax
0x140023efb  jns     loc_14002818A
0x140023f01  xor     edx, edx; PriorityBoost
0x140023f03  mov     [rbx+30h], edi
0x140023f06  mov     rcx, rbx; Irp
0x140023f09  call    cs:__imp_IofCompleteRequest
0x140023f10  nop     dword ptr [rax+rax+00h]
0x140023f15  mov     eax, edi
0x140023f17  add     rsp, 38h
0x140023f1b  pop     rdi
0x140023f1c  pop     rsi
0x140023f1d  pop     rbp
0x140023f1e  pop     rbx
0x140023f1f  retn
0x140023f21  mov     edi, 0C0000004h
0x140023f26  jmp     short loc_140023F01
0x140023f28  call    ?PartitionPassThrough@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; PartitionPassThrough(_DEVICE_OBJECT *,_IRP *)
0x140023f2d  mov     edi, eax
0x140023f2f  jmp     short loc_140023F15
0x14002818a  cmp     dword ptr [rsi+8], 28h ; '('
0x14002818e  jb      loc_140023F01
0x140028194  mov     rsi, [rbx+18h]
0x140028198  cmp     qword ptr [rsi+10h], 0
0x14002819d  jz      loc_140023F01
0x1400281a3  mov     rcx, [rbp+18h]
0x1400281a7  xor     r9d, r9d; Alertable
0x1400281aa  add     rcx, 38h ; '8'; Object
0x1400281ae  mov     [rsp+58h+Timeout], 0; Timeout
0x1400281b7  xor     r8d, r8d; WaitMode
0x1400281ba  xor     edx, edx; WaitReason
0x1400281bc  call    cs:__imp_KeWaitForSingleObject
0x1400281c3  nop     dword ptr [rax+rax+00h]
0x1400281c8  mov     r8, [rsi+10h]
0x1400281cc  mov     dl, 1; unsigned __int8
0x1400281ce  mov     rcx, rbp; struct _PARTITION_EXTENSION *
0x1400281d1  call    ?PartitionOffset@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionOffset(_PARTITION_EXTENSION *,uchar)
0x1400281d6  mov     r10b, [rsi+8]
0x1400281da  xor     edx, edx
0x1400281dc  mov     r9, rax
0x1400281df  div     r8
0x1400281e2  sub     r9, rdx
0x1400281e5  test    r10b, 20h
0x1400281e9  jz      short loc_1400281EF
0x1400281eb  add     r9, [rsi+18h]
0x1400281ef  mov     dl, 1; unsigned __int8
0x1400281f1  mov     rcx, rbp; struct _PARTITION_EXTENSION *
0x1400281f4  call    ?PartitionOffset@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionOffset(_PARTITION_EXTENSION *,uchar)
0x1400281f9  add     r8, r9
0x1400281fc  mov     dl, 1; unsigned __int8
0x1400281fe  cmp     r9, rax
0x140028201  mov     rcx, rbp; struct _PARTITION_EXTENSION *
0x140028204  cmovnb  r8, r9
0x140028208  or      r10b, 20h
0x14002820c  mov     [rsi+8], r10b
0x140028210  call    ?PartitionOffset@@YA_KPEAU_PARTITION_EXTENSION@@E@Z; PartitionOffset(_PARTITION_EXTENSION *,uchar)
0x140028215  sub     r8, rax
0x140028218  xor     edx, edx; Wait
0x14002821a  mov     [rsi+18h], r8
0x14002821e  mov     rcx, [rbp+18h]
0x140028222  add     rcx, 38h ; '8'; Mutex
0x140028226  call    cs:__imp_KeReleaseMutex
0x14002822d  nop     dword ptr [rax+rax+00h]
0x140028232  nop
0x140028233  jmp     loc_140023F01
```
